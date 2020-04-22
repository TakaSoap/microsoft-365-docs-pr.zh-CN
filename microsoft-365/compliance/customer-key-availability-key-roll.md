---
title: 滚动或旋转客户密钥或可用性密钥
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解如何滚动存储在 Azure Key Vault （与客户密钥一起使用）中存储的客户根键。 服务包括 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和团队文件。
ms.openlocfilehash: 29a36636253f5f01181f231941d0c3a9e26abacc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633639"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>滚动或旋转客户密钥或可用性密钥

> [!CAUTION]
> 当您的安全或合规性要求规定必须滚动密钥时，仅滚动与客户密钥配合使用的加密密钥。 此外，请勿删除与策略关联的或与之相关联的任何密钥。 在滚动键时，会使用以前的密钥对内容进行加密。 例如，虽然活动邮箱将被频繁地重新加密，但非活动邮箱、断开连接和已禁用邮箱仍可以使用以前的密钥进行加密。 SharePoint Online 执行用于还原和恢复目的的内容备份，因此可能仍有存档的内容使用旧密钥。

## <a name="about-rolling-the-availability-key"></a>关于滚动可用性密钥

Microsoft 不会向客户公开对可用性密钥的直接控制。 例如，您只能在 Azure Key Vault 中滚动（旋转）您拥有的密钥。 Microsoft 365 按内部定义的计划对可用性密钥进行回滚。 没有面向客户的服务级别协议（SLA），这些密钥将会回滚。 Microsoft 365 在自动、非手动过程中使用 Microsoft 365 服务代码旋转可用性密钥。 Microsoft 管理员可能会启动滚动过程。 使用自动机制对密钥进行滚动，而无需直接访问密钥存储。 无法为 Microsoft 管理员预配对可用性密钥机密存储的访问权限。 可用性密钥滚动利用用于最初生成密钥的相同机制。 有关可用性密钥的详细信息，请参阅[了解可用性密钥](customer-key-availability-key-understand.md)。

> [!IMPORTANT]
> 客户可以通过创建新的 DEP 来有效地滚动 Exchange Online 和 Skype for business 可用性密钥，因为为您创建的每个 DEP 生成唯一的可用性密钥。 SharePoint Online、OneDrive for Business 和团队文件的可用性密钥在林级别存在，并在 DEPs 和客户之间共享，这意味着仅在 Microsoft 内部定义的计划中进行滚动。 若要降低在每次创建新的 DEP 时不滚动可用性密钥的风险，SharePoint、OneDrive 和团队滚动租户中间密钥（TIK），每次创建新的 DEP 时，都会按客户根密钥和可用性密钥包装每个密钥。

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>请求要滚动的每个现有根密钥的新版本

在滚动某个键时，将请求现有项的新版本。 若要请求现有密钥的新版本，请使用相同的 cmdlet （ [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey)），其语法与您在第一个位置创建密钥时使用的语法相同。 在完成了与数据加密策略（DEP）关联的任何键的滚动后，请运行另一个 cmdlet，以确保客户密钥开始使用新密钥。 在每个 Azure Key Vault （AKV）中执行此步骤。

例如：

1. 使用 Azure PowerShell 登录到你的 Azure 订阅。 有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. 运行 AzKeyVaultKey cmdlet，如以下示例所示：

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   在此示例中，由于在**contoso-O365EX-** O365EX 保管库中存在名为**Contoso-VaultA1-Key001**的键，因此 cmdlet 会创建新版本的密钥。 此操作将保留密钥的版本历史记录中的以前的密钥版本。 您需要以前的密钥版本来解密它仍加密的数据。 在完成所有与 DEP 相关的键的滚动后，请运行额外的 cmdlet，以确保客户密钥开始使用新密钥。 以下各节更详细地介绍了 cmdlet。
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>更新 Exchange Online 和 Skype for business 的客户密钥

当您滚动与 Exchange Online 和 Skype for business 使用的 DEP 相关联的任何 Azure Key Vault 密钥时，您必须更新 DEP 以指向新密钥。 这不会旋转可用性密钥。

若要指示客户密钥使用新密钥加密邮箱，请运行 DataEncryptionPolicy cmdlet，如下所示：

1. 在 Azure PowerShell 中运行 DataEncryptionPolicy cmdlet：
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   在72小时内，与此 DEP 相关联的活动邮箱将使用新密钥进行加密。

2. 若要检查邮箱的 DataEncryptionPolicyID 属性的值，请按照[确定分配给邮箱的 DEP](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)中的步骤操作。 一旦服务应用了更新的密钥，此属性的值就会更改。
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>更新 SharePoint Online、OneDrive for Business 和团队文件的客户密钥

SharePoint Online 仅允许您一次滚动一个项。 如果要将密钥存储库中的两个密钥一起滚动，请等待第一个操作完成。 Microsoft 建议您错开操作以避免此问题。 当您滚动与 SharePoint Online 和 OneDrive for Business 使用的 DEP 相关联的任何 Azure Key Vault 密钥时，您必须更新 DEP 以指向新密钥。 这不会旋转可用性密钥。

1. 运行 SPODataEncryptionPolicy cmdlet，如下所示：
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   虽然此 cmdlet 启动 SharePoint Online 和 OneDrive for business 的密钥滚动操作，但操作不会立即完成。

2. 若要查看密钥滚动操作的进度，请运行 SPODataEncryptionPolicy cmdlet，如下所示：

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>相关文章

- [使用 Office 365 的客户密钥进行服务加密](customer-key-overview.md)

- [设置 Office 365 的客户密钥](customer-key-set-up.md)

- [管理 Office 365 的客户密钥](customer-key-manage.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)
