---
title: 滚动或旋转客户密钥或可用性密钥
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解如何滚动存储在 Azure Key Vault 中与客户密钥一同使用的客户根密钥。 服务包括Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和 Teams 文件。
ms.openlocfilehash: 22cf7d1ee9635a92684d377d05a4c53a909eb4bb
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553960"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>滚动或旋转客户密钥或可用性密钥

> [!CAUTION]
> 只有在安全或合规性要求规定必须滚动密钥时，才能滚动用于客户密钥的加密密钥。 此外，不要删除任何与策略关联的密钥。 在滚动密钥时，将会有使用之前密钥加密的内容。 例如，虽然活动邮箱将频繁重新加密，但非活动、断开连接和禁用的邮箱仍可能使用以前的密钥进行加密。 SharePoint联机执行内容备份以用于还原和恢复，因此可能仍使用旧密钥存档内容。

## <a name="about-rolling-the-availability-key"></a>关于滚动可用性密钥

Microsoft 不会将可用性密钥的直接控制公开给客户。 例如，你只能滚动 (旋转) 你在 Azure Key Vault 中拥有密钥。 Microsoft 365在内部定义的计划上滚动可用性密钥。 对于这些关键回滚，没有面向客户的服务级别 (SLA) SLA。 Microsoft 365在自动化的非手动Microsoft 365使用服务代码来轮换可用性密钥。 Microsoft 管理员可以启动滚动过程。 使用自动机制回滚密钥，无需直接访问密钥存储。 对可用性密钥密钥存储的访问未预配给 Microsoft 管理员。 可用性密钥滚动利用最初生成密钥所使用的相同机制。 有关可用性密钥详细信息，请参阅 [了解可用性密钥](customer-key-availability-key-understand.md)。

> [!IMPORTANT]
> Exchange Online一Skype for Business DEP 的客户可以有效回滚所有可用性密钥，因为会为创建的每个 DEP 生成唯一的可用性密钥。 SharePoint Online、OneDrive for Business 和 Teams 文件的可用性密钥存在于林级别，并且跨 DEP 和客户共享，这意味着滚动仅在 Microsoft 内部定义的日程安排中发生。 为了降低每次新建 DEP、SharePoint、OneDrive 和 Teams 滚动租户中间密钥 (TIK) （客户根密钥和可用性密钥包装的密钥）每次创建一个新的 DEP 时不滚动可用性密钥的风险。

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>请求要滚动的每个现有根密钥的新版本

在滚动密钥时，将请求现有密钥的新版本。 若要请求现有密钥的新版本，请使用与最初创建密钥时相同的 cmdlet [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)语法。 完成滚动与数据加密策略 (DEP) 关联的任何密钥后，运行另一个 cmdlet 以确保客户密钥开始使用新密钥。 在每个 Azure 密钥保管库和 AKV (中) 。

例如：

1. 使用帐户登录 Azure Azure PowerShell。 有关说明，请参阅[使用 Azure PowerShell 登录](/powershell/azure/authenticate-azureps)。

2. 运行 Add-AzKeyVaultKey cmdlet，如以下示例所示：

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   本示例中，由于 **名为 Contoso-CK-EX-NA-VaultA1-Key001** 的密钥存在于 **Contoso-CK-EX-NA-VaultA1** 保管库中，因此该 cmdlet 会创建该密钥的新版本。 此操作在密钥的版本历史记录中保留以前的密钥版本。 您需要以前的密钥版本来解密它仍然加密的数据。 完成滚动与 DEP 关联的任何密钥后，运行额外的 cmdlet 以确保客户密钥开始使用新密钥。 以下各节更详细地介绍了 cmdlet。
  
## <a name="update-the-keys-for-multi-workload-deps"></a>更新多工作负载 DEP 的密钥

在滚动与用于多个工作负荷的 DEP 关联的任一 Azure 密钥保管库密钥时，必须更新 DEP 以指向新密钥。 此过程不会轮换可用性密钥。

若要指示客户密钥使用新密钥加密多个工作负载，请完成以下步骤：

1. 在本地计算机上，使用在组织中具有全局管理员或合规性管理员权限的工作或学校帐户，在 Windows PowerShell 窗口中连接到 Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 运行 Set-M365DataAtRestEncryptionPolicy cmdlet。
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

其中 *PolicyName* 是策略的名称或唯一 ID。 例如，Contoso_Global。

示例：

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a>更新 EXCHANGE ONLINE 的密钥

滚动与用于 Exchange Online 和 Skype for Business 的 DEP 关联的任一 Azure 密钥保管库密钥时，必须更新 DEP 以指向新密钥。 这不会旋转可用性密钥。

若要指示客户密钥使用新密钥加密邮箱，请Set-DataEncryptionPolicy cmdlet：

1. 在Set-DataEncryptionPolicy中运行 Azure PowerShell：
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. 若要检查邮箱的 DataEncryptionPolicyID 属性的值，请使用De determine the [DEP assigned to a mailbox 中的步骤](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)。 此服务应用更新的密钥后，此属性的值将发生更改。
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>更新 SharePoint Online、OneDrive for Business 和 Teams 文件的密钥

SharePoint联机仅允许你一次滚动一个键。 如果要在密钥保管库中滚动这两个密钥，请等待第一个操作完成。 Microsoft 建议你错开操作，以避免此问题。 滚动与用于 SharePoint Online 和 OneDrive for Business 的 DEP 关联的任一 Azure 密钥保管库密钥时，必须更新 DEP 以指向新密钥。 这不会旋转可用性密钥。

1. 运行 Update-SPODataEncryptionPolicy cmdlet，如下所示：
  
   ```powershell
   Update-SPODataEncryptionPolicy  <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   当此 cmdlet 启动 SharePoint Online 和 OneDrive for Business 键滚动操作时，该操作不会立即完成。

2. To see the progress of the key roll operation， run the Get-SPODataEncryptionPolicy cmdlet as follows：

   ```powershell
   Get-SPODataEncryptionPolicy  <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>相关文章

- [使用客户密钥进行服务加密Office 365](customer-key-overview.md)

- [设置 Office 365 的客户密钥](customer-key-set-up.md)

- [管理 Office 365 的客户密钥](customer-key-manage.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)
