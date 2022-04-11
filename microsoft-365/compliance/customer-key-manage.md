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
ms.openlocfilehash: 1f3124930df88113d4c75401db21d7fc87c6616c
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64762246"
---
# <a name="manage-customer-key"></a>管理客户密钥

为Office 365设置客户密钥后，需要 (DEP) 创建和分配一个或多个数据加密策略。 分配 DEP 后，可以按照本文中所述管理密钥。 在相关主题中详细了解客户密钥。

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>为所有租户用户创建用于多个工作负载的 DEP

在开始之前，请确保已完成设置客户所需的任务。 有关信息，请参阅 [“设置客户密钥](customer-key-set-up.md)”。 若要创建 DEP，需要在设置过程中获得的密钥保管库 URI。 有关信息，请参阅[获取每个 Azure 密钥保管库密钥的 URI](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。

若要创建多工作负荷 DEP，请执行以下步骤：
  
1. 在本地计算机上，使用在组织中拥有全局管理员或合规性管理员权限的工作或学校帐户，在Windows PowerShell窗口中[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 若要创建 DEP，请使用New-M365DataAtRestEncryptionPolicy cmdlet。

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   其中：

   - *PolicyName* 是要用于策略的名称。 名称不能包含空格。 例如，Contoso_Global。

   - *KeyVaultURI1* 是策略中第一个密钥的 URI。 例如，<https://contosoWestUSvault1.vault.azure.net/keys/Key_01>。

   - *KeyVaultURI2* 是策略中第二个密钥的 URI。 例如，<https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>。 用逗号和空格分隔两个 URI。

   - *策略说明* 是策略的用户友好说明，可帮助你记住策略的用处。 可以在说明中包含空格。 例如，“租户中所有用户的多个工作负荷的根策略”。

示例：

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>分配多工作负荷策略

使用Set-M365DataAtRestEncryptionPolicyAssignment cmdlet 分配 DEP。 分配策略后，Microsoft 365使用 DEP 中标识的密钥对数据进行加密。

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 其中 *PolicyName* 是策略的名称。 例如，Contoso_Global。

示例：

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>创建用于Exchange Online邮箱的 DEP

在开始之前，请确保已完成设置 Azure 密钥保管库 所需的任务。 有关信息，请参阅 [“设置客户密钥](customer-key-set-up.md)”。 你将通过使用Windows PowerShell远程连接到Exchange Online来完成这些步骤。

DEP 与存储在 Azure 密钥保管库 中的一组密钥相关联。 将 DEP 分配到Microsoft 365中的邮箱。 然后，Microsoft 365将使用策略中标识的密钥来加密邮箱。 若要创建 DEP，需要在设置过程中获得的密钥保管库 URI。 有关信息，请参阅[获取每个 Azure 密钥保管库密钥的 URI](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。

记得！ 创建 DEP 时，请在两个不同的 Azure Key Vault 中指定两个密钥。 在两个单独的 Azure 区域中创建这些密钥，以确保异地冗余。

若要创建用于邮箱的 DEP，请执行以下步骤：
  
1. 在本地计算机上，使用在组织中拥有全局管理员或Exchange Online管理员权限的工作或学校帐户，在Windows PowerShell窗口中[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 若要创建 DEP，请键入以下命令来使用New-DataEncryptionPolicy cmdlet。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   其中：

   - *PolicyName* 是要用于策略的名称。 名称不能包含空格。 例如，USA_mailboxes。

   - *策略说明* 是策略的用户友好说明，可帮助你记住策略的用处。 可以在说明中包含空格。 例如，“美国邮箱及其领土的根密钥”。

   - *KeyVaultURI1* 是策略中第一个密钥的 URI。 例如，<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>。

   - *KeyVaultURI2* 是策略中第二个密钥的 URI。 例如，<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>。 用逗号和空格分隔两个 URI。

   示例：
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

有关详细语法和参数信息，请参阅 [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy)。

### <a name="assign-a-dep-to-a-mailbox"></a>将 DEP 分配到邮箱

使用Set-Mailbox cmdlet 将 DEP 分配到邮箱。 分配策略后，Microsoft 365可以使用 DEP 中标识的密钥加密邮箱。
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中 *MailboxIdParameter* 指定用户邮箱。 有关Set-Mailbox cmdlet 的详细信息，请参 [阅 Set-Mailbox](/powershell/module/exchange/set-mailbox)。

在混合环境中，可以将 DEP 分配给同步到Exchange Online租户的本地邮箱数据。 若要将 DEP 分配给此同步邮箱数据，请使用Set-MailUser cmdlet。 有关混合环境中邮箱数据的详细信息，请参阅[使用 Outlook for iOS 和 Android 和混合新式身份验证的本地邮箱](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中 *MailUserIdParameter* 指定邮件用户 (也称为启用邮件的用户) 。 有关Set-MailUser cmdlet 的详细信息，请参阅 [Set-MailUser](/powershell/module/exchange/set-mailuser)。

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>创建用于联机SharePoint、OneDrive for Business和Teams文件的 DEP

在开始之前，请确保已完成设置 Azure 密钥保管库 所需的任务。 有关信息，请参阅 [“设置客户密钥](customer-key-set-up.md)”。
  
若要为 SharePoint Online、OneDrive for Business 和 Teams 文件设置客户密钥，请通过远程连接到 Windows PowerShell 的 SharePoint Online 来完成这些步骤。
  
将 DEP 与存储在 Azure 密钥保管库 中的一组密钥相关联。 将 DEP 应用于一个地理位置（也称为地理位置）中的所有数据。 如果使用Office 365的多地理位置功能，则可以为每个地理位置创建一个 DEP，并能够使用每个地理位置的不同密钥。 如果不使用多地理位置，可在组织中创建一个 DEP，用于SharePoint联机、OneDrive for Business和Teams文件。 Microsoft 365使用 DEP 中标识的密钥来加密该地理位置中的数据。 若要创建 DEP，需要在设置过程中获得的密钥保管库 URI。 有关信息，请参阅[获取每个 Azure 密钥保管库密钥的 URI](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。
  
记得！ 创建 DEP 时，请在两个不同的 Azure Key Vault 中指定两个密钥。 在两个单独的 Azure 区域中创建这些密钥，以确保异地冗余。
  
若要创建 DEP，需要使用Windows PowerShell远程连接到 SharePoint Online。
  
1. 在本地计算机上，使用组织中具有全局管理员权限的工作或学校帐户[，连接SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)。

2. 在 Microsoft Office SharePoint Online Management Shell 中，按如下所示运行Register-SPODataEncryptionPolicy cmdlet：

   ```powershell
   Register-SPODataEncryptionPolicy -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   示例：
  
   ```powershell
   Register-SPODataEncryptionPolicy -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a'
   ```

   注册 DEP 时，加密将从地理位置中的数据开始。 加密可能需要一些时间。 有关使用此参数的详细信息，请参阅 [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)。

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>查看为Exchange Online邮箱创建的 DEP

若要查看为邮箱创建的所有 DEP 的列表，请使用 Get-DataEncryptionPolicy PowerShell cmdlet。

1. 使用组织中具有全局管理员权限的工作或学校帐户[，连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 若要返回组织中的所有 DEP，请在没有任何参数的情况下运行Get-DataEncryptionPolicy cmdlet。

   ```powershell
   Get-DataEncryptionPolicy
   ```

   有关Get-DataEncryptionPolicy cmdlet 的详细信息，请参阅 [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy)。

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>在将邮箱迁移到云之前分配 DEP

分配 DEP 时，Microsoft 365在迁移过程中使用分配的 DEP 加密邮箱的内容。 此过程比迁移邮箱、分配 DEP，然后等待加密发生（可能需要数小时或数天）更高效。

若要在将 DEP 迁移到Office 365之前将其分配到邮箱，请在 Exchange Online PowerShell 中运行Set-MailUser cmdlet：

1. 使用组织中具有全局管理员权限的工作或学校帐户[，连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行Set-MailUser cmdlet。

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   其中 *GeneralMailboxOrMailUserIdParameter* 指定邮箱， *DataEncryptionPolicyIdParameter* 是 DEP 的 ID。 有关Set-MailUser cmdlet 的详细信息，请参阅 [Set-MailUser](/powershell/module/exchange/set-mailuser)。

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>确定分配给邮箱的 DEP

若要确定分配给邮箱的 DEP，请使用Get-MailboxStatistics cmdlet。 该 cmdlet 返回唯一标识符 (GUID) 。
  
1. 使用组织中具有全局管理员权限的工作或学校帐户[，连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   其中 *GeneralMailboxOrMailUserIdParameter* 指定邮箱，DataEncryptionPolicyID 返回 DEP 的 GUID。 有关Get-MailboxStatistics cmdlet 的详细信息，请参阅 [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics)。
  
2. 运行Get-DataEncryptionPolicy cmdlet，找出邮箱分配到的 DEP 的友好名称。
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   *其中 GUID* 是上一步中Get-MailboxStatistics cmdlet 返回的 GUID。

## <a name="verify-that-customer-key-has-finished-encryption"></a>验证客户密钥是否已完成加密

无论是滚动客户密钥、分配了新的 DEP 还是迁移了邮箱，请使用本部分中的步骤来确保加密完成。

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>验证Exchange Online邮箱的加密是否已完成

加密邮箱可能需要一些时间。 首次加密时，邮箱还必须从一个数据库完全移动到另一个数据库，然后服务才能加密邮箱。
  
使用Get-MailboxStatistics cmdlet 确定是否已加密邮箱。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果邮箱已加密，则 IsEncrypted 属性返回 **true** 值，如果未加密邮箱，则返回 **false** 值。 完成邮箱移动的时间取决于您首次向其分配 DEP 的邮箱数目，以及邮箱的大小。 如果邮箱在分配 DEP 一周后未加密，请联系 Microsoft。

New-MoveRequest cmdlet 不再可用于本地邮箱移动。 有关其他信息，请参阅 [此公告](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 。

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>验证SharePoint联机、OneDrive for Business和Teams文件的加密是否已完成

通过运行Get-SPODataEncryptionPolicy cmdlet 来检查加密状态，如下所示：

```PowerShell
   Get-SPODataEncryptionPolicy <SPOAdminSiteUrl>
```

此 cmdlet 的输出包括：
  
- 主键的 URI。

- 辅助密钥的 URI。

- 地理位置的加密状态。 可能的状态包括：

  - **注册：** 客户密钥加密尚未应用。

  - **注册：** 客户密钥加密已应用，文件正在加密过程中。 如果地理位置的密钥正在注册，你还将看到有关该地理位置的完成百分比的信息，以便可以监视加密进度。

  - **注册：** 客户密钥加密已应用，所有站点中的所有文件都已加密。

  - **滚动：** 正在进行密钥滚动。 如果地理位置的密钥正在滚动，你还将显示有关已完成密钥滚动操作的站点百分比的信息，以便可以监视进度。

- 它还会输出载入的站点的百分比。

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>获取与多个工作负载一起使用的 DEP 的详细信息

若要获取有关已创建用于多个工作负荷的所有 DEP 的详细信息，请完成以下步骤：

1. 在本地计算机上，使用在组织中拥有全局管理员或合规性管理员权限的工作或学校帐户，在Windows PowerShell窗口中[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

   - 若要返回组织中所有多工作负荷 DEP 的列表，请运行此命令。

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - 若要返回有关特定 DEP 的详细信息，请运行此命令。 此示例返回名为“Contoso_Global”的 DEP 的详细信息。

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>获取多工作负荷 DEP 分配信息

若要了解当前分配给租户的 DEP，请执行以下步骤。 

1. 在本地计算机上，使用在组织中拥有全局管理员或合规性管理员权限的工作或学校帐户，在Windows PowerShell窗口中[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 键入此命令。

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>禁用多工作负荷 DEP

在禁用多工作负荷 DEP 之前，请从租户中的工作负荷中取消分配 DEP。 若要禁用与多个工作负载一起使用的 DEP，请完成以下步骤：

1. 在本地计算机上，使用在组织中拥有全局管理员或合规性管理员权限的工作或学校帐户，在Windows PowerShell窗口中[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行Set-M365DataAtRestEncryptionPolicy cmdlet。
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

其中 *PolicyName* 是策略的名称或唯一 ID。 例如，Contoso_Global。

示例：

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>还原 Azure 密钥保管库密钥

执行还原之前，请使用软删除提供的恢复功能。 与客户密钥一起使用的所有密钥都需要启用软删除。 软删除类似于回收站，允许恢复长达 90 天，无需还原。 仅在极端或异常情况下（例如，如果密钥或密钥保管库丢失）才需要还原。 如果必须还原用于 Customer Key 的密钥，请在Azure PowerShell中运行Restore-AzureKeyVaultKey cmdlet，如下所示：
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

例如：
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

如果密钥保管库已包含具有相同名称的密钥，则还原操作将失败。 Restore-AzKeyVaultKey还原密钥的所有密钥版本和所有元数据，包括密钥名称。
  
## <a name="manage-key-vault-permissions"></a>管理密钥保管库权限

可使用多个 cmdlet 查看密钥保管库权限，并在必要时删除密钥保管库权限。 可能需要删除权限，例如，当员工离开团队时。 对于这些任务，你将使用Azure PowerShell。 有关Azure PowerShell的信息，请参阅[Azure PowerShell概述](/powershell/azure/)。

若要查看密钥保管库权限，请运行Get-AzKeyVault cmdlet。

```powershell
Get-AzKeyVault -VaultName <vault name>
```

例如：

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

若要删除管理员的权限，请运行Remove-AzKeyVaultAccessPolicy cmdlet：
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

例如：

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>从客户密钥回滚到 Microsoft 托管密钥

如果需要还原到 Microsoft 托管的密钥，可以。 卸载时，将使用每个单个工作负载支持的默认加密重新加密数据。 例如，Exchange Online支持使用 Microsoft 托管密钥进行默认加密。

> [!IMPORTANT]
> 卸载与数据清除不同。 数据清除会从Microsoft 365中永久加密删除组织的数据，但不这样做。 不能对多个工作负荷策略执行数据清除。

如果决定不再使用客户密钥分配多工作负载 DEP，则需要向 Microsoft 支持部门提出从客户密钥“卸载”的请求。 要求支持团队针对Microsoft 365客户密钥团队提出服务请求。 如果有任何问题，请联系 m365-ck@service.microsoft.com。

如果不想再使用邮箱级别的 DEP 加密单个邮箱，则可以从所有邮箱中取消分配邮箱级别的 DEP。

若要取消分配邮箱 DEP，请使用 Set-Mailbox PowerShell cmdlet。

1. 使用组织中具有全局管理员权限的工作或学校帐户[，连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行Set-Mailbox cmdlet。

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

运行此 cmdlet 会取消分配当前分配的 DEP，并使用与默认 Microsoft 托管密钥关联的 DEP 重新加密邮箱。 无法取消分配 Microsoft 托管密钥使用的 DEP。 如果不想使用 Microsoft 托管的密钥，可以将另一个客户密钥 DEP 分配到邮箱。

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>撤销密钥并启动数据清除路径过程

可以控制所有根密钥（包括可用性密钥）的吊销。 客户密钥可控制监管要求的退出规划方面。 如果决定撤消密钥以清除数据并退出服务，则在数据清除过程完成后，该服务将删除可用性密钥。 分配给单个邮箱的客户密钥 DEP 支持此功能。

Microsoft 365审核和验证数据清除路径。 有关详细信息，请参阅 [服务信任门户](https://servicetrust.microsoft.com/)上提供的 SSAE 18 SOC 2 报告。 此外，Microsoft 建议使用以下文档：

- [Microsoft 云中金融机构的风险评估和合规性指南](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 退出规划注意事项](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Microsoft 365客户密钥不支持清除多工作负荷 DEP。 多工作负荷 DEP 用于跨所有租户用户的多个工作负荷加密数据。 清除此类 DEP 将导致来自多个工作负荷的数据变得不可访问。 如果决定完全退出Microsoft 365服务，则可以根据记录的过程执行租户删除路径。 了解[如何在Azure Active Directory中删除租户](/azure/active-directory/enterprise-users/directory-delete-howto)。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>撤消客户密钥和Exchange Online和Skype for Business的可用性密钥

为Exchange Online和Skype for Business启动数据清除路径时，会在 DEP 上设置永久数据清除请求。 这样做会永久删除分配给该 DEP 的邮箱中的加密数据。

由于一次只能针对一个 DEP 运行 PowerShell cmdlet，因此在启动数据清除路径之前，请考虑将单个 DEP 重新分配到所有邮箱。

> [!WARNING]
> 请勿使用数据清除路径删除邮箱的子集。 此过程仅适用于退出服务的客户。

若要启动数据清除路径，请完成以下步骤：

1. 从 Azure Key Vault 中删除“O365 Exchange Online”的包装和解包权限。

2. 使用组织中具有全局管理员权限的工作或学校帐户[，连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

3. 对于包含要删除的邮箱的每个 DEP，请按如下所示运行 [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet。

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   如果该命令失败，请确保已从 Azure 密钥保管库中前面指定的两个密钥中删除了Exchange Online权限。 使用 Set-DataEncryptionPolicy cmdlet 设置 PermanentDataPurgeRequested 开关后，将无法再将此 DEP 分配到邮箱。

4. 联系 Microsoft 支持部门并请求数据清除 eDocument。

    在您的请求下，Microsoft 会向你发送一份法律文档，以确认并授权数据删除。 组织中在加入过程中注册为FastTrack产品/服务审批者的人需要签署此文档。 通常，这是公司中的高管或其他指定人员，他们有权代表你的组织在文书工作上签名。

5. 代表签署法律文档后，通常通过 eDoc 签名) 将其返回到 Microsoft (。

    一旦 Microsoft 收到法律文档，Microsoft 将运行 cmdlet 以触发数据清除，该清除首先删除策略，标记用于永久删除的邮箱，然后删除可用性密钥。 数据清除过程完成后，数据已清除，无法Exchange Online且无法恢复。

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>撤消客户密钥和SharePoint联机、OneDrive for Business和Teams文件的可用性密钥

若要启动SharePoint联机、OneDrive for Business和Teams文件的数据清除路径，请完成以下步骤：

1. 撤消 Azure 密钥保管库访问权限。 所有密钥保管库管理员都必须同意撤销访问权限。

   不删除适用于 SharePoint Online 的 Azure 密钥保管库。 密钥保管库可在多个SharePoint联机租户和 DEP 之间共享。

2. 请联系 Microsoft 删除可用性密钥。

    当你联系 Microsoft 删除可用性密钥时，我们将向你发送一份法律文档。 组织中在加入过程中注册为FastTrack产品/服务审批者的人需要签署此文档。 通常，这是公司中有权代表组织签署文书工作的高管或其他指定人员。

3. 代表签署法律文档后，通常通过 eDoc 签名) 将其返回到 Microsoft (。

   Microsoft 收到法律文档后，我们将运行 cmdlet 来触发数据清除，以执行对租户密钥、站点密钥和所有单个每个文档密钥的加密删除，从而不可撤销地中断密钥层次结构。 数据清除 cmdlet 完成后，数据就会被清除。

## <a name="related-articles"></a>相关文章

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [设置客户密钥](customer-key-set-up.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [客户密码箱](customer-lockbox-requests.md)

- [服务加密](office-365-service-encryption.md)
