---
title: 管理客户密钥
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
description: 在设置客户密钥之后，请了解如何通过还原 AKV 密钥以及管理权限和数据加密策略来管理它。
ms.openlocfilehash: 8f5f23fa1b8ce8baa8fafd3f29ca5fb8905887a1
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324254"
---
# <a name="manage-customer-key"></a>管理客户密钥

在设置了 Office 365 的客户密钥之后，您可以按本文所述管理密钥。 有关详细信息，请参阅相关主题中的客户密钥。

## <a name="restore-azure-key-vault-keys"></a>还原 Azure Key Vault 密钥

在执行还原之前，请使用由软删除提供的恢复功能。 需要使用与客户密钥一起使用的所有密钥才能启用软删除。 软删除操作类似于回收站，允许恢复最长为90天，而无需进行还原。 只有在极端或异常情况下才需要还原，例如，密钥或密钥存储库丢失。 如果您必须还原密钥以用于客户密钥，请在 Azure PowerShell 中运行 AzureKeyVaultKey cmdlet，如下所示：
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

例如：
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

如果密钥保管库已包含具有相同名称的密钥，还原操作将失败。 Restore-AzKeyVaultKey 还原密钥的所有密钥版本和所有元数据，包括密钥名称。
  
## <a name="manage-key-vault-permissions"></a>管理密钥存储库权限

提供了多个 cmdlet，以便你可以查看并在必要时删除密钥保管库权限（如有必要）。 您可能需要删除权限，例如，当员工离开团队时。 对于这些任务中的每一项，都将使用 Azure PowerShell。 有关 Azure Powershell 的信息，请参阅 [Azure Powershell 概述](https://docs.microsoft.com/powershell/azure/)。

若要查看密钥存储区权限，请运行 AzKeyVault cmdlet。

```powershell
Get-AzKeyVault -VaultName <vault name>
```

例如：

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

若要删除管理员权限，请运行 AzKeyVaultAccessPolicy cmdlet：
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

例如：

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>使用客户密钥管理 (DEPs) 的数据加密策略

客户密钥处理不同服务之间的 DEPs 不同。 例如，您可以为不同的服务创建不同数量的 DEPs。

**Exchange Online 和 Skype For business：** 最高可创建 50 DEPs。 有关说明，请参阅 [Create a data encryption policy (DEP) 以用于 Exchange Online 和 Skype For business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)。

**SharePoint Online、OneDrive For business 和团队文件：** DEP 适用于一个地理位置（也称为 _地理_位置）中的数据。 如果使用 Office 365 的多地理位置功能，则可以为每个地理位置创建一个 DEP。 如果您不使用多地理位置，则可以创建一个 DEP。 通常情况下，在设置 "客户密钥" 时创建 DEP。 有关说明，请参阅 [Create a data encryption policy (DEP) for Each SharePoint Online 和 OneDrive For business 地域](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)。

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>查看您为 Exchange Online 和 Skype for Business 创建的 DEPs

若要查看您使用 DataEncryptionPolicy PowerShell cmdlet 为 Exchange Online 和 Skype for business 创建的所有 DEPs 的列表，请完成以下步骤。

1. 使用组织中具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

2. 若要返回组织中的所有 DEPs，请运行不带任何参数的 DataEncryptionPolicy cmdlet。

   ```powershell
   Get-DataEncryptionPolicy
   ```

   有关 DataEncryptionPolicy cmdlet 的详细信息，请参阅 [DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps)。

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>在将邮箱迁移到云中之前分配一个 DEP

分配 DEP 时，Microsoft 365 会在迁移过程中使用分配的 DEP 对邮箱的内容进行加密。 此过程比迁移邮箱、分配 DEP 并等待进行加密更高效，这可能需要数小时或数天。

若要在将 DEP 迁移到 Office 365 之前将其分配给邮箱，请在 Exchange Online PowerShell 中运行 MailUser cmdlet：

1. 使用组织中具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

2. 运行 MailUser cmdlet。

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   其中 *GeneralMailboxOrMailUserIdParameter* 指定邮箱， *DataEncryptionPolicyIdParameter* 是 DEP 的 ID。 有关 MailUser cmdlet 的详细信息，请参阅 [MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps)。

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>确定分配给邮箱的 DEP

若要确定分配给邮箱的 DEP，请使用 Get-mailboxstatistics cmdlet。 Cmdlet 返回 (GUID) 的唯一标识符。
  
1. 使用组织中具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   其中 *GeneralMailboxOrMailUserIdParameter* 指定邮箱和 DATAENCRYPTIONPOLICYID 返回 DEP 的 GUID。 有关 Get-mailboxstatistics cmdlet 的详细信息，请参阅 [get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps)。
  
2. 运行 DataEncryptionPolicy cmdlet 以查找邮箱分配到的 DEP 的友好名称。
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   其中 *guid* 是上一步中的 get-mailboxstatistics cmdlet 返回的 guid。

## <a name="verify-that-customer-key-has-finished-encryption"></a>验证客户密钥是否已完成加密

无论您是仅滚动了客户密钥、分配了新的 DEP 还是迁移了邮箱，都可以使用本节中的步骤来确保加密完成。

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>验证 Exchange Online 和 Skype for business 的加密是否已完成

对邮箱加密可能需要一段时间。 建议您在更改 DEP 或首次将 DEP 分配到邮箱之后，先等待72小时，再尝试验证加密。
  
使用 Get-mailboxstatistics cmdlet 可以确定邮箱是否已加密。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果邮箱已加密，则 IsEncrypted 属性返回 **true** ，如果邮箱未加密，则返回 **false** 值。

完成邮箱移动的时间取决于邮箱的大小。 如果客户密钥尚未在72小时后从分配新的 DEP 中完全加密邮箱，请与 Microsoft 支持部门联系以获取帮助。 New-moverequest cmdlet 不再可用于本地邮箱移动。 有关详细信息，请参阅本次 [通知](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 。

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>验证 SharePoint Online、OneDrive for Business 和团队文件的加密是否已完成

通过运行 SPODataEncryptionPolicy cmdlet 检查加密状态，如下所示：

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

此 cmdlet 的输出包括：
  
- 主键的 URI。

- 辅助密钥的 URI。

- 地理位置的加密状态。 可能的状态包括：

  - 未**注册：** 尚未应用客户密钥加密。

  - **注册：** 客户密钥加密已应用，并且您的文件正在被加密。 如果正在注册 geo 的密钥，还会显示有关 geo 中的多少个网站的完成百分比的信息，以便您可以监视加密进度。

  - **注册：** 客户密钥加密已应用，并且所有网站中的所有文件均已加密。

  - **滚动：** 正在进行密钥滚动。 如果正在滚动 geo 的键，则还会显示有关已完成密钥滚动操作的网站百分比的信息，以便您可以监视进度。

## <a name="unassign-a-dep-from-a-mailbox"></a>从邮箱中取消分配 DEP

您可以使用 "设置邮箱 PowerShell" cmdlet 从邮箱中取消分配 DEP，并将设置 `DataEncryptionPolicy` 为 `$NULL` 。 运行此 cmdlet 取消分配当前分配的 DEP，并使用与默认 Microsoft 管理密钥关联的 DEP reencrypts 邮箱。 无法取消分配 Microsoft 托管密钥使用的 DEP。 如果不想使用 Microsoft 托管密钥，可以为邮箱分配另一个 DEP。

若要使用设置邮箱 PowerShell cmdlet 从邮箱中取消分配 DEP，请完成以下步骤。

1. 使用组织中具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

2. 运行 "设置邮箱" cmdlet。

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>废除你的密钥并启动数据清除路径过程

您可以控制所有根项（包括可用性密钥）的吊销。 客户密钥为您提供管理法规要求的退出规划方面的控制权。 如果您决定撤销密钥以清除数据并退出服务，则在数据清除过程完成后，服务将删除可用性密钥。

Microsoft 365 审核并验证数据清除路径。 有关详细信息，请参阅 [服务信任门户](https://servicetrust.microsoft.com/)上提供的 SSAE 18 SOC 2 报告。 此外，Microsoft 建议采用以下文档：

- [Microsoft 云中的金融机构风险评估和合规性指南](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 退出规划注意事项](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

不同服务之间的数据清除路径略有不同。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>吊销客户密钥和 Exchange Online 和 Skype for business 的可用性密钥

启动 Exchange Online 和 Skype for business 的数据清除路径时，请在 DEP 上设置永久的数据清除请求。 这样做会永久删除为其分配了该 DEP 的邮箱中的加密数据。

由于您一次只能对一个 DEP 运行 PowerShell cmdlet，因此请考虑先将一个 DEP 分配给所有邮箱，然后再启动数据清除路径。

> [!WARNING]
> 请勿使用数据清除路径删除邮箱的子集。 此过程仅适用于正在退出该服务的客户。

若要启动数据清除路径，请完成以下步骤：

1. 从 Azure 密钥保管库中删除 "O365 Exchange Online" 的包装和解包权限。

2. 在您的组织中使用具有全局管理员权限的工作或学校帐户， [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

3. 对于包含要删除的邮箱的每个 DEP，请运行 [DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet，如下所示。

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   如果该命令失败，请确保已从 Azure Key Vault 中的两个密钥中删除了 Exchange Online 权限，如本任务前面所述。使用 DataEncryptionPolicy cmdlet 设置 PermanentDataPurgeRequested 开关后，您将无法再将此 DEP 分配给邮箱。

4. 请联系 Microsoft 支持部门并请求数据清除 eDocument。

    在你请求时，Microsoft 会向你发送法律文档以确认和授权数据删除。 您组织中在 FastTrack 提供的审批者注册的人员需要对此文档进行签名。 通常情况下，这是公司中有权代表你的组织签署文书工作的行政或其他指定人员。

5. 在你的代表签署法律文档后，通常通过 eDoc 签名) 将其返回到 Microsoft (。

    一旦 Microsoft 收到法律文档，Microsoft 将运行 cmdlet 以触发数据清除，这会先删除策略，将邮箱标记为永久删除，然后删除可用性密钥。 数据清除过程完成后，Exchange Online 中的数据将被清除，不可恢复，且不可恢复。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>吊销客户密钥和 SharePoint Online、OneDrive for Business 和团队文件的可用性密钥

若要启动 SharePoint Online、OneDrive for Business 和团队文件的数据清除路径，请完成以下步骤：

1. 吊销 Azure Key Vault 访问权限。 所有密钥保管库管理员必须同意撤销访问权限。

   您不会删除 SharePoint Online 的 Azure Key Vault。 主要电子仓库可在多个 SharePoint Online 租户和 DEPs 之间共享。

2. 请与 Microsoft 联系以删除可用性密钥。

    当你与 Microsoft 联系删除可用性密钥时，我们会向你发送法律文档。 您组织中在 FastTrack 提供的审批者注册的人员需要对此文档进行签名。 通常情况下，这是公司中有权代表你的组织签署文书工作的行政或其他指定人员。

3. 在你的代表签署法律文档后，通常通过 eDoc 签名) 将其返回到 Microsoft (。

   在 Microsoft 收到法律文档后，我们将运行 cmdlet 以触发数据清除，这将对租户密钥、网站密钥和所有单个文档的密钥执行加密删除，irrevocably 破坏密钥层次结构。 数据清除 cmdlet 完成后，你的数据已被清除。

## <a name="related-articles"></a>相关文章

- [使用客户密钥进行服务加密](customer-key-overview.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [设置客户密钥](customer-key-set-up.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [客户密码箱](customer-lockbox-requests.md)

- [服务加密](office-365-service-encryption.md)
