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
description: 设置客户密钥后，了解如何通过还原 AKV 密钥来管理它，以及如何管理权限和数据加密策略。
ms.openlocfilehash: 284a8ff24fef2f7e8b807477c99e20aaf593552e
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394660"
---
# <a name="manage-customer-key"></a>管理客户密钥

为 Office 365 设置客户密钥后，可以管理密钥，如本文所述。 在相关主题中了解有关客户密钥的信息。

## <a name="restore-azure-key-vault-keys"></a>还原 Azure 密钥保管库密钥

在执行还原之前，请使用软删除提供的恢复功能。 必须启用软删除，才能使用客户密钥的所有密钥。 软删除的作用与回收站类似，允许恢复最多 90 天，而无需还原。 只有在极端或异常情况下（例如，密钥或密钥保管库丢失）才需要还原。 如果必须还原密钥以用于客户密钥，在 Azure PowerShell 中，Restore-AzureKeyVaultKey cmdlet，如下所示：
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

例如：
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

如果密钥保管库已包含同名密钥，则还原操作将失败。 Restore-AzKeyVaultKey还原密钥的所有密钥版本和元数据，包括密钥名称。
  
## <a name="manage-key-vault-permissions"></a>管理密钥保管库权限

可以使用多个 cmdlet 查看密钥保管库权限，并在必要时删除密钥保管库权限。 例如，当员工离开团队时，可能需要删除权限。 对于其中每个任务，你将使用 Azure PowerShell。 有关 Azure Powershell 的信息，请参阅 [Azure PowerShell 概述](/powershell/azure/)。

若要查看密钥保管库权限，请运行 Get-AzKeyVault cmdlet。

```powershell
Get-AzKeyVault -VaultName <vault name>
```

例如：

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

若要删除管理员的权限，请运行以下Remove-AzKeyVaultAccessPolicy cmdlet：
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

例如：

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>使用客户密钥 (数据加密策略) 数据加密策略

客户密钥在不同的服务之间以不同方式处理 DEP。 例如，您可以为不同的服务创建不同数量的 DESP。

**Exchange Online 和 Skype for Business：** 您可以创建最多 50 个 DESP。 有关说明，请参阅 [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)。

**SharePoint Online、OneDrive for Business 和 Teams 文件：** DEP 适用于一个地理位置（也称为地理位置） _的数据_。 如果使用 Office 365 的多地理位置功能，可以为每个地理位置创建一个 DEP。 如果不使用多地理位置，可以创建一个 DEP。 通常，在设置客户密钥时创建 DEP。 有关说明，请参阅 [为每个 SharePoint Online](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)和 OneDrive for Business (DEP) 创建数据加密策略。

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>查看为 Exchange Online 和 Skype for Business 创建的 DESP

若要查看使用 Get-DataEncryptionPolicy PowerShell cmdlet 为 Exchange Online 和 Skype for Business 创建的所有 DESP 的列表，请完成这些步骤。

1. 使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 若要返回组织的所有 DEP，请运行不带Get-DataEncryptionPolicy cmdlet。

   ```powershell
   Get-DataEncryptionPolicy
   ```

   有关此 cmdlet Get-DataEncryptionPolicy，请参阅 [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy)。

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>在将邮箱迁移到云之前分配 DEP

分配 DEP 时，Microsoft 365 在迁移过程中使用分配的 DEP 对邮箱内容进行加密。 此过程比迁移邮箱、分配 DEP，然后等待加密发生（可能需要数小时或数天）更有效。

若要在将 DEP 迁移到 Office 365 之前将其分配给邮箱，请运行 Exchange Online PowerShell Set-MailUser cmdlet：

1. 使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行 Set-MailUser cmdlet。

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   其中 *，GeneralMailboxOrMailUserIdParameter* 指定邮箱 *，DataEncryptionPolicyIdParameter* 是 DEP 的 ID。 有关此 cmdlet Set-MailUser，请参阅 [Set-MailUser](/powershell/module/exchange/set-mailuser)。

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>确定分配给邮箱的 DEP

若要确定分配给邮箱的 DEP，请使用 Get-MailboxStatistics cmdlet。 此 cmdlet 返回 GUID (的唯) 。
  
1. 使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   其中 *GeneralMailboxOrMailUserIdParameter* 指定邮箱，DataEncryptionPolicyID 返回 DEP 的 GUID。 有关此 cmdlet Get-MailboxStatistics，请参阅 [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics)。
  
2. 运行 Get-DataEncryptionPolicy cmdlet，查找邮箱分配到的 DEP 的友好名称。
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   其中 *GUID* 是上一步中 Get-MailboxStatistics cmdlet 返回的 GUID。

## <a name="verify-that-customer-key-has-finished-encryption"></a>确认客户密钥已完成加密

无论是刚刚汇总了客户密钥、分配了新的 DEP 还是迁移了邮箱，请使用本节中的步骤确保加密完成。

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>验证 Exchange Online 和 Skype for Business 的加密是否已完成

加密邮箱可能需要一些时间。 建议在更改 DEP 或首次向邮箱分配 DEP 后等待 72 小时，然后再尝试验证加密。
  
使用 Get-MailboxStatistics cmdlet 确定邮箱是否加密。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果邮箱已加密，则 IsEncrypted 属性返回 **true** 值;如果邮箱未加密，则返回 **false** 值。

完成邮箱移动的时间取决于邮箱的大小。 如果自分配新 DEP 起 72 小时后客户密钥尚未完全加密邮箱，请联系 Microsoft 支持人员寻求帮助。 此New-MoveRequest cmdlet 不再可用于本地邮箱移动。 有关其他 [信息，](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 请参阅此通知。

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>验证 SharePoint Online、OneDrive for Business 和 Teams 文件的加密是否完成

按如下所示运行 Get-SPODataEncryptionPolicy cmdlet 检查加密状态：

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

此 cmdlet 的输出包括：
  
- 主键的 URI。

- 辅助密钥的 URI。

- 地理位置的加密状态。 可能状态包括：

  - **注销：** 尚未应用客户密钥加密。

  - **注册：** 已应用客户密钥加密，你的文件正在加密中。 如果地理位置的密钥正在注册，还将显示有关地理位置中完成的网站百分比的信息，以便你可以监视加密进度。

  - **已注册：** 已应用客户密钥加密，并且所有网站中的所有文件已加密。

  - **滚动：** 密钥滚动正在进行中。 如果地理位置的密钥正在滚动，你还将看到有关完成密钥滚动操作的网站百分比的信息，以便你可以监视进度。

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>从客户密钥回滚到 Microsoft 托管密钥

对于租户级别的客户密钥，你需要通过客户密钥的"离开"请求联系 Microsoft。 该请求将由 On Call Engineering 团队处理。

对于应用程序级别的客户密钥，为此，可以使用 Set-mailbox PowerShell cmdlet 从邮箱取消分配 DEP，将 `DataEncryptionPolicy` 设置为 `$NULL` 。 运行此 cmdlet 可取消分配当前分配的 DEP，然后使用与默认 Microsoft 托管密钥关联的 DEP 重新加密邮箱。 不能取消分配 Microsoft 托管密钥使用的 DEP。 如果您不想使用 Microsoft 托管密钥，您可以为邮箱分配另一个客户密钥 DEP。

若要使用 PowerShell cmdlet 从邮箱取消Set-Mailbox DEP，请完成这些步骤。

1. 使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行 Set-Mailbox cmdlet。

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>撤销密钥并开始数据清除路径过程

控制所有根密钥（包括可用性密钥）的吊销。 客户密钥可控制法规要求的退出计划方面。 如果决定撤销密钥以清除数据并退出服务，则服务会在数据清除过程完成后删除可用性密钥。 无法对租户级别的策略执行数据清除。

Microsoft 365 审核并验证数据清除路径。 有关详细信息，请参阅服务信任门户上提供的 SSAE 18 SOC 2 [报告](https://servicetrust.microsoft.com/)。 此外，Microsoft 建议以下文档：

- [Microsoft 云中金融机构的风险评估和合规性指南](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 退出规划注意事项](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

不同服务之间的数据清除路径略有不同。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>撤销你的客户密钥和 Exchange Online 和 Skype for Business 的可用性密钥

为 Exchange Online 和 Skype for Business 启动数据清除路径时，会在 DEP 上设置永久数据清除请求。 这样做会永久删除分配给 DEP 的邮箱中的加密数据。

由于一次只能对一个 DEP 运行 PowerShell cmdlet，因此在启动数据清除路径之前，请考虑将单个 DEP 重新分配给所有邮箱。

> [!WARNING]
> 请勿使用数据清除路径删除邮箱的子集。 此过程仅适用于退出服务的客户。

若要启动数据清除路径，请完成以下步骤：

1. 从 Azure 密钥保管库删除"O365 Exchange Online"的自动换行和取消打包权限。

2. 使用在组织中具有全局管理员权限的工作或学校帐户，连接到 Exchange [Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

3. 对于包含要删除的邮箱的每个 DEP，运行 [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet，如下所示。

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   如果命令失败，请确保你已删除 Azure 密钥保管库中的两个密钥的 Exchange Online 权限，如此任务前面所述。使用 Set-DataEncryptionPolicy cmdlet 设置 PermanentDataPurgeRequested 开关后，将无法再将此 DEP 分配给邮箱。

4. 联系 Microsoft 支持人员并请求"数据清除"eDocument。

    根据你的请求，Microsoft 会向您发送一份法律文档，以确认和授权删除数据。 在载入期间在 FastTrack 产品/服务中注册为审批者的组织人员需要签署此文档。 通常，这是公司中经法律授权代表你的组织签署书面材料的公司主管或其他指定人员。

5. 在代表签署法律文档后，通常 (eDoc 签名文件将该文档) 。

    Microsoft 收到法律文档后，Microsoft 将运行 cmdlet 触发数据清除，首先删除策略，将邮箱标记为永久删除，然后删除可用性密钥。 数据清除过程完成后，数据已被清除，Exchange Online 无法访问数据，并且不可恢复。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>撤销 SharePoint Online、OneDrive for Business 和 Teams 文件的客户密钥和可用性密钥

若要启动 SharePoint Online、OneDrive for Business 和 Teams 文件的数据清除路径，请完成以下步骤：

1. 撤销 Azure 密钥保管库访问权限。 所有密钥保管库管理员都必须同意撤销访问权限。

   不要删除 SharePoint Online 的 Azure 密钥保管库。 密钥保管库可以在多个 SharePoint Online 租户和 DESP 之间共享。

2. 请与 Microsoft 联系以删除可用性密钥。

    当你联系 Microsoft 以删除可用性密钥时，我们将向您发送一份法律文档。 在载入期间在 FastTrack 产品/服务中注册为审批者的组织人员需要签署此文档。 通常，这是公司中法律授权代表你的组织签署书面材料的公司主管或其他指定人员。

3. 在代表签署法律文档后，通常 (eDoc 签名文件将该文档) 。

   Microsoft 收到法律文档后，我们运行 cmdlet 触发数据清除，以加密方式删除租户密钥、站点密钥以及所有单独每文档密钥，从而不可撤销地破坏密钥层次结构。 数据清除 cmdlet 完成后，数据即被清除。

## <a name="related-articles"></a>相关文章

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [设置客户密钥](customer-key-set-up.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [客户密码箱](customer-lockbox-requests.md)

- [服务加密](office-365-service-encryption.md)