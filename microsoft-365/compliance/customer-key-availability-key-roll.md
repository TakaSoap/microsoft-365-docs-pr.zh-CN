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
description: 了解如何滚动存储在 Azure Key Vault 中与客户密钥一同使用的客户根密钥。 服务包括 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和 Teams 文件。
ms.openlocfilehash: 980d6b198b326cb75bb2b4ef4d2c980f605f23e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923328"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>滚动或旋转客户密钥或可用性密钥

> [!CAUTION]
> 只有在安全或合规性要求规定必须滚动密钥时，才能滚动用于客户密钥的加密密钥。 此外，不要删除任何与策略关联的密钥。 在滚动密钥时，将会有使用之前密钥加密的内容。 例如，虽然活动邮箱将频繁重新加密，但非活动、断开连接和禁用的邮箱仍可能会使用以前的密钥进行加密。 SharePoint Online 出于还原和恢复目的执行内容备份，因此可能仍有使用旧密钥的存档内容。

## <a name="about-rolling-the-availability-key"></a>关于滚动可用性密钥

Microsoft 不会将可用性密钥的直接控制公开给客户。 例如，你只能滚动 (旋转) 你在 Azure Key Vault 中拥有密钥。 Microsoft 365 按内部定义的计划滚动可用性密钥。 对于这些关键滚动，没有面向客户的服务级别协议 (SLA) SLA。 Microsoft 365 在自动的非手动过程中使用 Microsoft 365 服务代码轮换可用性密钥。 Microsoft 管理员可以启动滚动过程。 使用自动机制回滚密钥，无需直接访问密钥存储。 对可用性密钥密钥存储的访问未预配给 Microsoft 管理员。 可用性密钥滚动利用最初生成密钥所使用的相同机制。 有关可用性密钥详细信息，请参阅 [了解可用性密钥](customer-key-availability-key-understand.md)。

> [!IMPORTANT]
> 客户创建新 DEP 可以有效地回滚 Exchange Online 和 Skype for Business 可用性密钥，因为会为创建的每个 DEP 生成唯一的可用性密钥。 SharePoint Online、OneDrive for Business 和 Teams 文件的可用性密钥存在于林级别，并且跨 DEP 和客户共享，这意味着滚动仅按照 Microsoft 内部定义的计划进行。 为了降低每次新建 DEP 时不滚动可用性密钥的风险，SharePoint、OneDrive 和 Teams 会滚动租户中间密钥 (TIK) ，每次创建一个新的 DEP 时，该密钥由客户根密钥和可用性密钥包装。

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>请求要滚动的每个现有根密钥的新版本

在滚动密钥时，将请求现有密钥的新版本。 若要请求现有密钥的新版本，请使用与最初创建密钥时相同的 cmdlet [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)语法。 完成滚动与数据加密策略 (DEP) 关联的任何密钥后，运行另一个 cmdlet 以确保客户密钥开始使用新密钥。 在每个 Azure 密钥保管库和 AKV (中) 。

例如：

1. 使用 Azure PowerShell 登录 Azure 订阅。 有关说明，请参阅 [使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。

2. 运行 Add-AzKeyVaultKey cmdlet，如以下示例所示：

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   本示例中 **，由于名为 Contoso-O365EX-NA-VaultA1-Key001** 的密钥存在于 **Contoso-O365EX-NA-VaultA1** 保管库中，因此该 cmdlet 会创建该密钥的新版本。 此操作在密钥的版本历史记录中保留以前的密钥版本。 您需要以前的密钥版本来解密它仍然加密的数据。 完成滚动与 DEP 关联的任何密钥后，运行额外的 cmdlet 以确保客户密钥开始使用新密钥。 以下各节更详细地介绍了 cmdlet。
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>更新 Exchange Online 和 Skype for Business 的客户密钥

在滚动与用于 Exchange Online 和 Skype for Business 的 DEP 关联的任一 Azure 密钥保管库密钥时，必须更新 DEP 以指向新密钥。 这不会旋转可用性密钥。

若要指示客户密钥使用新密钥加密邮箱，请Set-DataEncryptionPolicy cmdlet：

1. 在 Azure PowerShell Set-DataEncryptionPolicy cmdlet：
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   在 72 小时内，与此 DEP 关联的活动邮箱将用新密钥加密。

2. 若要检查邮箱的 DataEncryptionPolicyID 属性的值，请使用De determine the [DEP assigned to a mailbox 中的步骤](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)。 此服务应用更新的密钥后，此属性的值将发生更改。
  
## <a name="update-the-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>更新 SharePoint Online、OneDrive for Business 和 Teams 文件的客户密钥

SharePoint Online 只允许一次滚动一个密钥。 如果要在密钥保管库中滚动这两个密钥，请等待第一个操作完成。 Microsoft 建议你错开操作，以避免此问题。 滚动与用于 SharePoint Online 和 OneDrive for Business 的 DEP 关联的任一 Azure 密钥保管库密钥时，必须更新 DEP 以指向新密钥。 这不会旋转可用性密钥。

1. 运行 Update-SPODataEncryptionPolicy cmdlet，如下所示：
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   此 cmdlet 启动 SharePoint Online 和 OneDrive for Business 的密钥滚动操作时，该操作不会立即完成。

2. To see the progress of the key roll operation， run the Get-SPODataEncryptionPolicy cmdlet as follows：

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>相关文章

- [使用 Office 365 客户密钥进行服务加密](customer-key-overview.md)

- [设置 Office 365 的客户密钥](customer-key-set-up.md)

- [管理 Office 365 的客户密钥](customer-key-manage.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)