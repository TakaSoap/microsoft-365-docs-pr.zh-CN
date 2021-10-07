---
title: 管理客户密钥
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
description: 设置客户密钥后，了解如何通过还原 AKV 密钥、管理权限以及创建和分配数据加密策略来管理它。
ms.openlocfilehash: 2329df5a7bb7fac7a6013e1236024ba0a4a31567
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172451"
---
# <a name="manage-customer-key"></a>管理客户密钥

为用户设置客户密钥Office 365，需要在 DEP 策略中创建和分配一个或多个 (加密) 。 分配 DESP 后，你可以管理密钥，如本文中所述。 在相关主题中了解有关客户密钥的信息。

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>创建一个 DEP 以用于所有租户用户的多个工作负载

开始之前，请确保已完成设置 Customer 所需的任务。 有关信息，请参阅 [设置客户密钥](customer-key-set-up.md)。 若要创建 DEP，您需要在安装期间获取的密钥保管库 URI。 有关信息，请参阅[获取每个 Azure 密钥保管库密钥的 URI。](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)

若要创建多工作负荷 DEP，请按照以下步骤操作：
  
1. 在本地计算机上，使用在组织中具有全局管理员或合规性管理员权限的工作或学校帐户，Exchange Online窗口中连接到 Windows PowerShell [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 若要创建 DEP，请使用 New-M365DataAtRestEncryptionPolicy cmdlet。

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   其中：

   - *PolicyName* 是你想要用于策略的名称。 名称不能包含空格。 例如，Contoso_Global。

   - *KeyVaultURI1* 是策略中第一个密钥的 URI。 例如，<https://contosoWestUSvault1.vault.azure.net/keys/Key_01>。

   - *KeyVaultURI2* 是策略中第二个密钥的 URI。 例如，<https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>。 用逗号和空格分隔这两个 URI。

   - *策略* 说明是策略的用户友好说明，有助于你记住策略用于什么。 可以在说明中包括空格。 例如，"租户中所有用户的多个工作负荷的根策略"。

示例：

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>分配多工作负荷策略

使用 cmdlet 分配 deP Set-M365DataAtRestEncryptionPolicyAssignment cmdlet。 分配策略后，Microsoft 365 DEP 中标识的密钥加密数据。

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 其中 *PolicyName* 是策略的名称。 例如，Contoso_Global。

示例：

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>创建一个 DEP 以用于Exchange Online邮箱

开始之前，请确保已完成设置 Azure 密钥保管库所需的任务。 有关信息，请参阅 [设置客户密钥](customer-key-set-up.md)。 通过远程连接到具有远程连接Exchange Online完成Windows PowerShell。

DEP 与 Azure Key Vault 中存储的一组密钥相关联。 您将 DEP 分配给邮箱中的Microsoft 365。 Microsoft 365将使用策略中标识的密钥来加密邮箱。 若要创建 DEP，您需要在安装期间获取的密钥保管库 URI。 有关信息，请参阅[获取每个 Azure 密钥保管库密钥的 URI。](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)

请记住！ 创建 DEP 时，可以在两个不同的 Azure 密钥保管库中指定两个密钥。 在两个独立的 Azure 区域创建这些密钥以确保地理位置冗余。

若要创建用于邮箱的 DEP，请按照以下步骤操作：
  
1. 在本地计算机上，使用在组织中具有全局管理员或 Exchange Online 管理员权限的工作或学校帐户，在 Windows PowerShell 窗口中连接到 Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 若要创建 DEP，请通过New-DataEncryptionPolicy命令使用命令行管理 cmdlet。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   其中：

   - *PolicyName* 是你想要用于策略的名称。 名称不能包含空格。 例如，USA_mailboxes。

   - *策略* 说明是策略的用户友好说明，有助于你记住策略用于什么。 可以在说明中包括空格。 例如，"美国及其区域邮箱的根密钥"。

   - *KeyVaultURI1* 是策略中第一个密钥的 URI。 例如，<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>。

   - *KeyVaultURI2* 是策略中第二个密钥的 URI。 例如，<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>。 用逗号和空格分隔这两个 URI。

   示例：
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

有关语法和参数的详细信息，请参阅 [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy)。

### <a name="assign-a-dep-to-a-mailbox"></a>将 DEP 分配给邮箱

使用 cmdlet 将 DEP 分配给Set-Mailbox cmdlet。 分配策略后，Microsoft 365使用 DEP 中标识的密钥加密邮箱。
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中 *MailboxIdParameter* 指定用户邮箱。 有关此 cmdlet Set-Mailbox，请参阅 [Set-Mailbox](/powershell/module/exchange/set-mailbox)。

在混合环境中，您可以将 DEP 分配给同步到您的 Exchange Online 租户中的内部部署邮箱数据。 若要为此同步的邮箱数据分配 DEP，请使用 Set-MailUser cmdlet。 有关混合环境中邮箱数据详细信息，请参阅使用混合新式验证的 Outlook [for iOS 和 Android 本地邮箱](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中 *MailUserIdParameter* 指定邮件 (也称为启用邮件的用户) 。 有关该 cmdlet Set-MailUser，请参阅 [Set-MailUser](/powershell/module/exchange/set-mailuser)。

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>创建 DEP 以用于 SharePoint Online、OneDrive for Business 和 Teams 文件

开始之前，请确保已完成设置 Azure 密钥保管库所需的任务。 有关信息，请参阅 [设置客户密钥](customer-key-set-up.md)。
  
若要为 SharePoint Online、OneDrive for Business 和 Teams 文件设置客户密钥，可以使用 Windows PowerShell 远程连接到 SharePoint Online 来完成Windows PowerShell。
  
将 DEP 与 Azure Key Vault 中存储的一组密钥关联。 将 DEP 应用于一个地理位置（也称为地理位置）的所有数据。 如果你使用多地理位置功能Office 365，你可以为每个地理位置创建一个 DEP，并能够为每个地理位置使用不同的密钥。 如果不使用多地理位置，可以在组织中创建一个 DEP 以用于 SharePoint Online、OneDrive for Business 和 Teams 文件。 Microsoft 365使用 DEP 中标识的密钥加密该地理位置的数据。 若要创建 DEP，您需要在安装期间获取的密钥保管库 URI。 有关信息，请参阅[获取每个 Azure 密钥保管库密钥的 URI。](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)
  
请记住！ 创建 DEP 时，可以在两个不同的 Azure 密钥保管库中指定两个密钥。 在两个独立的 Azure 区域创建这些密钥以确保地理位置冗余。
  
若要创建 DEP，你需要使用 SharePoint Online 远程Windows PowerShell。
  
1. 在本地计算机上，使用在组织中具有全局管理员权限的工作或学校帐户，连接 SharePoint Online [PowerShell。](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)

2. 在命令行Microsoft Office SharePoint Online命令行管理程序中，Register-SPODataEncryptionPolicy cmdlet，如下所示：

   ```powershell
   Register-SPODataEncryptionPolicy <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   示例：
  
   ```powershell
   Register-SPODataEncryptionPolicy  https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   注册 DEP 时，加密从地理位置数据开始。 加密可能需要一些时间。 有关使用此参数的信息，请参阅 [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)。

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>查看为邮箱创建的 EXCHANGE ONLINE报告

若要查看为邮箱创建的所有 DESP 的列表，请使用 Get-DataEncryptionPolicy PowerShell cmdlet。

1. 使用在组织中具有全局管理员权限的工作或学校帐户，Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 若要返回组织的所有 DEP，请运行不带Get-DataEncryptionPolicy cmdlet。

   ```powershell
   Get-DataEncryptionPolicy
   ```

   有关此 cmdlet Get-DataEncryptionPolicy，请参阅 [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy)。

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>在将邮箱迁移到云之前分配 DEP

分配 DEP 时，Microsoft 365迁移期间使用分配的 DEP 对邮箱内容进行加密。 此过程比迁移邮箱、分配 DEP，然后等待加密发生（可能需要数小时或几天时间）更有效。

若要在将 DEP 迁移到邮箱之前将其分配给Office 365，Set-MailUser PowerShell 中运行 Exchange Online cmdlet：

1. 使用在组织中具有全局管理员权限的工作或学校帐户，Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 运行 Set-MailUser cmdlet。

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   其中 *，GeneralMailboxOrMailUserIdParameter* 指定邮箱 *，DataEncryptionPolicyIdParameter* 是 DEP 的 ID。 有关此 cmdlet Set-MailUser，请参阅 [Set-MailUser](/powershell/module/exchange/set-mailuser)。

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>确定分配给邮箱的 DEP

若要确定分配给邮箱的 DEP，请使用 Get-MailboxStatistics cmdlet。 此 cmdlet 返回 GUID (的唯) 。
  
1. 使用在组织中具有全局管理员权限的工作或学校帐户，Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   其中 *GeneralMailboxOrMailUserIdParameter* 指定邮箱，DataEncryptionPolicyID 返回 DEP 的 GUID。 有关此 cmdlet Get-MailboxStatistics，请参阅 [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics)。
  
2. 运行 Get-DataEncryptionPolicy cmdlet，查找邮箱分配到的 DEP 的友好名称。
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   其中 GUID 是上一步中 Get-MailboxStatistics cmdlet 返回的 *GUID。*

## <a name="verify-that-customer-key-has-finished-encryption"></a>确认客户密钥已完成加密

无论是已汇总客户密钥、分配了新的 DEP 还是迁移了邮箱，请使用本节中的步骤确保加密完成。

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>验证加密是否Exchange Online邮箱

加密邮箱可能需要一些时间。 对于首次加密，邮箱还必须从一个数据库完全移动到另一个数据库，服务才能加密邮箱。
  
使用 Get-MailboxStatistics cmdlet 确定邮箱是否加密。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果邮箱已加密，则 IsEncrypted 属性返回 **true** 值;如果邮箱未加密，则返回 **false** 值。 完成邮箱移动的时间取决于第一次为其分配 DEP 的邮箱数以及邮箱的大小。 如果邮箱自分配 DEP 起一周后未加密，请与 Microsoft 联系。

New-MoveRequest cmdlet 不再可用于本地邮箱移动。 有关其他 [信息，](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 请参阅此通知。

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>验证加密是否SharePoint Online、OneDrive for Business和Teams文件

按如下所示运行 Get-SPODataEncryptionPolicy cmdlet 检查加密状态：

```PowerShell
   Get-SPODataEncryptionPolicy <SPOAdminSiteUrl>
```

此 cmdlet 的输出包括：
  
- 主键的 URI。

- 辅助密钥的 URI。

- 地理位置的加密状态。 可能状态包括：

  - **注销：** 尚未应用客户密钥加密。

  - **注册：** 已应用客户密钥加密，你的文件正在加密中。 如果地理位置的密钥正在注册，还将显示有关地理位置中完成的网站百分比的信息，以便你可以监视加密进度。

  - **已注册：** 已应用客户密钥加密，并且所有网站中的所有文件已加密。

  - **滚动：** 密钥滚动正在进行中。 如果地理位置的密钥正在滚动，你还将看到有关完成密钥滚动操作的网站百分比的信息，以便你可以监视进度。

- 它还将输出已载入网站的百分比。

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>获取有关用于多个工作负载的 DEP 的详细信息

若要获取有关已创建用于多个工作负荷的所有 DESP 的详细信息，请完成以下步骤：

1. 在本地计算机上，使用在组织中具有全局管理员或合规性管理员权限的工作或学校帐户，Exchange Online窗口中连接到 Windows PowerShell [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

   - 若要返回组织中所有多工作负荷 DEP 的列表，请运行此命令。

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - 要返回有关特定 DEP 的详细信息，请运行此命令。 此示例返回名为"Contoso_Global"的 DEP 的详细信息。

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>获取多工作负载 DEP 分配信息

若要了解当前分配给租户的 DEP，请按照以下步骤操作。 

1. 在本地计算机上，使用在组织中具有全局管理员或合规性管理员权限的工作或学校帐户，Exchange Online窗口中连接到 Windows PowerShell [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 键入此命令。

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>禁用多工作负荷 DEP

在禁用多工作负荷 DEP 之前，请从租户中的工作负荷中取消分配 DEP。 若要禁用用于多个工作负荷的 DEP，请完成以下步骤：

1. 在本地计算机上，使用在组织中具有全局管理员或合规性管理员权限的工作或学校帐户，Exchange Online窗口中连接到 Windows PowerShell [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 运行 Set-M365DataAtRestEncryptionPolicy cmdlet。
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

其中 *PolicyName* 是策略的名称或唯一 ID。 例如，Contoso_Global。

示例：

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>还原 Azure 密钥保管库密钥

在执行还原之前，请使用软删除提供的恢复功能。 必须启用软删除，才能使用客户密钥的所有密钥。 软删除的作用与回收站类似，允许恢复最多 90 天，而无需还原。 只有在极端或异常情况下（例如，密钥或密钥保管库丢失）才需要还原。 如果必须还原用于客户密钥的密钥，Azure PowerShell运行 Restore-AzureKeyVaultKey cmdlet，如下所示：
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

例如：
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

如果密钥保管库已包含同名密钥，则还原操作将失败。 Restore-AzKeyVaultKey还原键的所有密钥版本和元数据，包括密钥名称。
  
## <a name="manage-key-vault-permissions"></a>管理密钥保管库权限

可以使用多个 cmdlet 查看密钥保管库权限，并在必要时删除密钥保管库权限。 例如，当员工离开团队时，可能需要删除权限。 对于其中每个任务，将使用Azure PowerShell。 有关 Azure PowerShell 的信息，请参阅[Azure PowerShell](/powershell/azure/)概述。

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

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>从客户密钥回滚到 Microsoft 托管密钥

如果需要还原到 Microsoft 管理的密钥，可以。 当你离开时，你的数据会使用每个工作负荷支持的默认加密重新加密。 例如，Exchange Online Microsoft 管理的密钥支持默认加密。

> [!IMPORTANT]
> 载出与数据清除不同。 数据清除会永久加密删除组织的数据，Microsoft 365，但无法从中删除。 无法对多个工作负荷策略执行数据清除。

如果你决定不使用客户密钥分配多工作负荷 DEP，则需要通过从客户密钥请求"退出"来联系 Microsoft 支持人员。 要求支持团队针对客户关键Microsoft 365提出服务请求。 如果你有任何问题 m365-ck@service.microsoft.com 联系他们。

如果不想再使用邮箱级别 DEPS 加密单个邮箱，可以取消分配所有邮箱的邮箱级别 DEP。

若要取消分配邮箱 DEP，请使用 Set-Mailbox PowerShell cmdlet。

1. 使用在组织中具有全局管理员权限的工作或学校帐户，Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 运行 Set-Mailbox cmdlet。

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

运行此 cmdlet 可取消分配当前分配的 DEP，然后使用与默认 Microsoft 托管密钥关联的 DEP 重新加密邮箱。 不能取消分配 Microsoft 托管密钥使用的 DEP。 如果您不想使用 Microsoft 管理的密钥，您可以为邮箱分配另一个客户密钥 DEP。

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>撤销密钥并开始数据清除路径过程

控制所有根密钥（包括可用性密钥）的吊销。 客户密钥可控制法规要求的退出计划方面。 如果决定撤销密钥以清除数据并退出服务，则服务会在数据清除过程完成后删除可用性密钥。 分配给各个邮箱的客户密钥 DEP 支持此功能。

Microsoft 365审核并验证数据清除路径。 有关详细信息，请参阅服务信任门户上提供的 SSAE 18 SOC 2 [报告](https://servicetrust.microsoft.com/)。 此外，Microsoft 建议以下文档：

- [Microsoft 云中金融机构的风险评估和合规性指南](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 退出规划注意事项](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

客户密钥不支持清除多Microsoft 365 DEP。 多工作负载 DEP 用于跨所有租户用户的多个工作负载加密数据。 清除此类 DEP 将导致无法访问来自多个工作负载的数据。 如果决定完全退出Microsoft 365服务，可以按记录的过程采取租户删除路径。 请参阅[如何在租户中删除Azure Active Directory。](/azure/active-directory/enterprise-users/directory-delete-howto)

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>吊销你的客户密钥和用于Exchange Online Skype for Business

当您启动数据清除路径以执行Exchange Online Skype for Business，您将在 DEP 上设置永久数据清除请求。 这样做会永久删除分配给 DEP 的邮箱中的加密数据。

由于一次只能对一个 DEP 运行 PowerShell cmdlet，因此在启动数据清除路径之前，请考虑将单个 DEP 重新分配给所有邮箱。

> [!WARNING]
> 请勿使用数据清除路径删除邮箱的子集。 此过程仅适用于退出服务的客户。

若要启动数据清除路径，请完成以下步骤：

1. 从 Azure 密钥保管库中删除"O365 Exchange Online的自动换行和取消打包权限。

2. 使用在组织中具有全局管理员权限的工作或学校帐户，Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

3. 对于包含要删除的邮箱的每个 DEP，运行 [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet，如下所示。

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   如果命令失败，请确保你已从 Azure 密钥保管库中的Exchange Online项删除权限，如此任务前面所述。使用 Set-DataEncryptionPolicy cmdlet 设置 PermanentDataPurgeRequested 开关后，将无法再将此 DEP 分配给邮箱。

4. 联系 Microsoft 支持人员并请求"数据清除"eDocument。

    根据你的请求，Microsoft 会向您发送一份法律文档，以确认和授权删除数据。 你组织中在载入期间以FastTrack审批者注册的人需要签署此文档。 通常，这是公司中经法律授权代表你的组织签署书面材料的公司主管或其他指定人员。

5. 在代表签署法律文档后，通常 (eDoc 签名文件将该文档) 。

    Microsoft 收到法律文档后，Microsoft 将运行 cmdlet 触发数据清除，首先删除策略，将邮箱标记为永久删除，然后删除可用性密钥。 数据清除过程完成后，数据已被清除、无法访问Exchange Online且不可恢复。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>吊销你的客户密钥和 SharePoint Online、OneDrive for Business 和 Teams 密钥

若要启动 SharePoint Online、OneDrive for Business 和 Teams 文件的数据清除路径，请完成以下步骤：

1. 撤销 Azure 密钥保管库访问权限。 所有密钥保管库管理员都必须同意撤销访问权限。

   不要删除适用于 SharePoint Online 的 Azure 密钥保管库。 密钥保管库可以在多个 SharePoint Online 租户和 DESP 之间共享。

2. 请与 Microsoft 联系以删除可用性密钥。

    当你联系 Microsoft 以删除可用性密钥时，我们将向您发送一份法律文档。 你组织中在载入期间以FastTrack审批者注册的人需要签署此文档。 通常，这是公司中法律授权代表你的组织签署书面材料的公司主管或其他指定人员。

3. 在代表签署法律文档后，通常 (eDoc 签名文件将该文档) 。

   Microsoft 收到法律文档后，我们运行 cmdlet 触发数据清除，以加密方式删除租户密钥、站点密钥以及所有单独每文档密钥，从而不可撤销地破坏密钥层次结构。 数据清除 cmdlet 完成后，数据即被清除。

## <a name="related-articles"></a>相关文章

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [设置客户密钥](customer-key-set-up.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [客户密码箱](customer-lockbox-requests.md)

- [服务加密](office-365-service-encryption.md)
