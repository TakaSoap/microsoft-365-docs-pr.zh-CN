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
description: 了解如何滚动存储在 Azure 密钥保管库中的客户根密钥，这些密钥与客户密钥一起使用。 服务包括Exchange Online、Skype for Business、SharePoint联机、OneDrive for Business和Teams文件。
ms.openlocfilehash: 81d82f49c056f5a6ec9b8731b549aee68d5d658b
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64761342"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>滚动或旋转客户密钥或可用性密钥

> [!CAUTION]
> 只有在安全性或合规性要求规定必须滚动密钥时，才会滚动使用客户密钥的加密密钥。 此外，请勿删除任何与策略相关联或与策略关联的密钥。 滚动密钥时，会有使用以前的密钥加密的内容。 例如，虽然活动邮箱将频繁重新加密，但非活动邮箱、断开连接邮箱和禁用邮箱仍可能使用以前的密钥进行加密。 SharePoint联机执行内容备份以进行还原和恢复，因此可能仍使用旧密钥存档内容。

## <a name="about-rolling-the-availability-key"></a>关于滚动可用性密钥

Microsoft 不会向客户公开对可用性密钥的直接控制。 例如，只能滚动 () Azure 密钥保管库中拥有的密钥轮换。 Microsoft 365在内部定义的计划中滚动显示可用性密钥。 对于这些密钥卷，没有面向客户的服务级别协议 (SLA) 。 Microsoft 365在自动化的非手动进程中使用Microsoft 365服务代码轮换可用性密钥。 Microsoft 管理员可以启动滚动过程。 该密钥是使用自动化机制滚动的，而无需直接访问密钥存储。 对可用性密钥机密存储的访问权限未预配给 Microsoft 管理员。 可用性密钥滚动利用最初用于生成密钥的相同机制。 有关可用性密钥的详细信息，请 [参阅“了解可用性密钥](customer-key-availability-key-understand.md)”。

> [!IMPORTANT]
> 创建新 DEP 的客户可以有效地滚动Exchange Online和Skype for Business可用性密钥，因为将为创建的每个 DEP 生成唯一的可用性密钥。 SharePoint联机、OneDrive for Business和Teams文件的可用性密钥存在于林级别，并且在 DEP 和客户之间共享，这意味着仅在 Microsoft 内部定义的计划中进行滚动。 为了降低每次创建新的 DEP 时不滚动可用性密钥的风险，SharePoint、OneDrive和Teams将租户中间密钥 (TIK) （每次创建新的 DEP 时由客户根密钥和可用性密钥包装的密钥）滚动。

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>请求要滚动的每个现有根密钥的新版本

滚动密钥时，将请求现有密钥的新版本。 若要请求现有密钥的新版本，请使用相同的 cmdlet [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)，其语法与最初创建密钥时所用的语法相同。 完成与数据加密策略 (DEP) 关联的任何密钥滚动后，运行另一个 cmdlet 以确保客户密钥开始使用新密钥。 在每个 Azure 密钥保管库 (AKV) 中执行此步骤。

例如：

1. 使用Azure PowerShell登录到 Azure 订阅。 有关说明，请参阅[使用Azure PowerShell登录](/powershell/azure/authenticate-azureps)。

2. 运行Add-AzKeyVaultKey cmdlet，如以下示例所示：

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   在此示例中，由于 **Contoso-CK-EX-NA-VaultA1-Key001** 的密钥存在于 **Contoso-CK-EX-NA-VaultA1 保管** 库中，因此该 cmdlet 会创建新版本的密钥。 此操作在密钥的版本历史记录中保留以前的密钥版本。 需要以前的密钥版本来解密它仍然加密的数据。 完成与 DEP 关联的任何密钥滚动后，请运行额外的 cmdlet 以确保客户密钥开始使用新密钥。 以下部分更详细地介绍了 cmdlet。
  
## <a name="update-the-keys-for-multi-workload-deps"></a>更新多工作负荷 DEP 的密钥

滚动与多个工作负荷使用的 DEP 关联的任一 Azure 密钥保管库密钥时，必须更新 DEP 以指向新密钥。 此过程不会轮换可用性密钥。

若要指示客户密钥使用新密钥加密多个工作负荷，请完成以下步骤：

1. 在本地计算机上，使用在组织中拥有全局管理员或合规性管理员权限的工作或学校帐户，在Windows PowerShell窗口中[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行Set-M365DataAtRestEncryptionPolicy cmdlet。
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

其中 *PolicyName* 是策略的名称或唯一 ID。 例如，Contoso_Global。

示例：

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a>更新Exchange Online DEP 的密钥

滚动与用于Exchange Online和Skype for Business的 DEP 关联的任一 Azure 密钥保管库密钥时，必须更新 DEP 以指向新密钥。 这不会轮换可用性密钥。

若要指示客户密钥使用新密钥加密邮箱，请运行Set-DataEncryptionPolicy cmdlet，如下所示：

1. 在Azure PowerShell中运行Set-DataEncryptionPolicy cmdlet：
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. 若要检查邮箱的 DataEncryptionPolicyID 属性的值，请使用 [“确定分配给邮箱的 DEP](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)”中的步骤。 服务应用更新的密钥后，此属性的值将更改。
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>更新SharePoint联机、OneDrive for Business和Teams文件的密钥

SharePoint联机仅允许一次滚动一个密钥。 如果要在密钥保管库中滚动两个密钥，请等待第一个操作完成。 Microsoft 建议错开操作以避免此问题。 滚动与与 SharePoint Online 和 OneDrive for Business 一起使用的 DEP 关联的任一 Azure 密钥保管库密钥时，必须更新 DEP 以指向新密钥。 这不会轮换可用性密钥。

1. 按如下所示运行Update-SPODataEncryptionPolicy cmdlet：
  
   ```powershell
   Update-SPODataEncryptionPolicy  <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   虽然此 cmdlet 为 SharePoint Online 和 OneDrive for Business 启动密钥滚动操作，但操作不会立即完成。

2. 若要查看密钥滚动操作的进度，请运行Get-SPODataEncryptionPolicy cmdlet，如下所示：

   ```powershell
   Get-SPODataEncryptionPolicy <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>相关文章

- [使用客户密钥进行服务加密Office 365](customer-key-overview.md)

- [设置 Office 365 的客户密钥](customer-key-set-up.md)

- [管理 Office 365 的客户密钥](customer-key-manage.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)
