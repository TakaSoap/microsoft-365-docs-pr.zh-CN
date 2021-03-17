---
title: 租户级 Microsoft 365 客户密钥（公共预览版）
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/17/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: 了解如何为 Microsoft 365 租户内的所有数据设置客户密钥。
ms.openlocfilehash: 2fed4730e79f6e2ace827eab338bf9da8fe55260
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838237"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>租户级别的 Microsoft 365 客户密钥概述 (公共预览版) 

使用你提供的密钥，可以在 DEP (创建) 策略并将其分配给租户。 DEP 为以下工作负载加密租户内的数据：

- Teams 聊天消息 (一对一聊天、群聊、会议聊天和频道对话) 
- Teams 媒体消息 (图像、代码段、视频消息、音频消息、wiki 图像) 
- Teams 存储中存储的 Teams 通话和会议录像
- Teams 聊天通知
- Cortana 的 Teams 聊天建议
- Teams 状态消息
- Exchange Online 的用户和信号信息
- 在应用程序级别未加密客户密钥 DEP 的 Exchange Online 邮箱

对于 Microsoft Teams，租户级别的客户密钥从 DEP 分配给租户时对新数据进行加密。 公共预览版不支持加密过去的数据。 对于 Exchange Online，客户密钥会加密所有现有和新数据。

你可以为每个租户创建多个 DEP，但在任何时间点只能分配一个 DEP。 分配 DEP 时，加密将自动开始，但可能需要一段时间才能完成，具体取决于租户的大小。

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>租户级别策略为 Microsoft 365 的客户密钥添加了更广泛的控制

如果你已设置 Exchange Online 和 Sharepoint Online 的客户密钥，下面将说明新的租户级别公共预览的适用方式。

你创建的租户级加密策略对 Microsoft 365 中的 Microsoft Teams 和 Exchange Online 工作负载的所有数据进行加密。 但是，对于 Exchange Online，如果已经将客户密钥 DEP 分配给各个邮箱，租户级别的策略将不会覆盖这些 DECP。 租户级别的策略将仅加密未分配邮箱级别的客户密钥 DEP 的邮箱。

例如，保存在 OneDrive for Business 和 SharePoint 中的 Microsoft Teams 文件和一些 Teams 通话和会议录像由 SharePoint Online DEP 加密。 单个 SharePoint Online DEP 对单个地理位置中的内容进行加密。

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>在租户级别设置客户密钥 (公共预览版) 

这些步骤与在应用程序级别设置客户密钥的步骤类似，但不完全相同。 应仅将此公共预览版与测试租户中的测试数据一同使用。 不要将此版本与生产数据或生产环境一同使用。 如果你已经拥有客户密钥的生产部署，请使用以下步骤在测试环境中在租户级别设置客户密钥。 向租户分配租户级别 DEP 后，你可以启动验证过程，并联系你 m365ck@microsoft.com 任何问题或问题。 还可以在 [Microsoft 365](https://aka.ms/CustomerKey/PublicPreviewValidation)静态加密的验证说明的公共预览中查找记录验证步骤。

你通过远程连接到 Azure PowerShell 完成大部分任务。 为了获得最佳结果，请使用版本 4.4.0 或更高版本的 Azure PowerShell。

在开始使用之前，请确保执行以下操作：

- 你需要使用具有合规性管理员角色的工作或学校帐户在租户级别设置客户密钥。
- 确保你的组织具有适当的许可。 使用付费的、已开票的 Azure 订阅，企业协议云服务提供商。 客户密钥不支持使用即付即用计划或信用卡购买的 Azure 订阅。 从 2020 年 4 月 1 日起，Office 365 中的客户密钥在 Office 365 E5、M365 E5、M365 E5 合规性和 M365 E5 信息保护 & SK 中提供。 Office 365 高级合规性 SKU 不再可用于购买新许可证。 现有 Office 365 高级合规性许可证将继续受支持。 虽然该服务可以在具有相应许可证的租户下至少具有一个许可证进行启用，但仍应确保从该服务受益的所有用户都有相应的许可证。

### <a name="create-two-new-azure-subscriptions"></a>创建两个新的 Azure 订阅

客户密钥要求 DEP 策略中每个数据加密策略 (两) 。 为此，你必须创建两个 Azure 订阅。 最佳做法是，Microsoft 建议你组织单独的成员在每个订阅中配置一个密钥。 仅使用这些 Azure 订阅来管理 Microsoft 365 的加密密钥。 这可保护你的组织，以防你的其中一个运营者意外、有意或恶意删除或以其他方式管理他们负责的密钥。

对于你可以为组织创建的 Azure 订阅数没有实际限制。 遵循此最佳做法有助于最大限度地减少人为错误的影响，同时有助于管理客户密钥使用的资源。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>注册 Azure 订阅以使用强制保留期

根加密密钥的临时或永久丢失可能会导致服务操作中断甚至出现灾难性问题，并可能导致数据丢失。 因此，用于客户密钥的资源需要强大的保护。 与客户密钥一起使用的所有 Azure 资源都提供除默认配置以外的保护机制。 Azure 订阅可以通过防止立即和不可撤销取消的方式进行标记或注册。 这称为注册强制保留期。 为 Azure 订阅注册强制保留期所需的步骤需要与 Microsoft 协作。 此过程最多可能需要 5 个工作日。 以前，这有时称为"不取消"。
  
在联系 Microsoft 365 团队之前，你必须对使用客户密钥的每个 Azure 订阅执行以下步骤。 在启动之前，请确保已安装 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 模块。

1. 使用 Azure PowerShell 登录。 有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. 运行 Register-AzProviderFeature cmdlet 注册订阅以使用强制保留期。 对于每个订阅执行此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. 请与 Microsoft 联系，让该过程在 m365ck@microsoft.com[完成。](mailto:m365ck@microsoft.com) 在电子邮件中包括以下内容：

   **主题**：客户密钥 \<*Your tenant's fully-qualified domain name*\>

   **正文**：要完成其强制保留期的订阅 ID。
   每个订阅Get-AzProviderFeature的订阅输出。

   完成此过程的服务级别协议 (SLA) 在向 Microsoft 通知 (并验证) 你已注册订阅以使用强制保留期后，5 个工作日。

4. 从 Microsoft 收到注册完成通知后，通过运行 Get-AzProviderFeature 命令验证注册状态。 如果已验证，Get-AzProviderFeature返回 Registration **State** 属性的值 **Registered。** 对于每个订阅执行此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. 若要完成此过程，请运行 Register-AzResourceProvider 命令。 对于每个订阅执行此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每个订阅中创建高级 Azure 密钥保管库

[Azure](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)密钥保管库入门中记录了创建密钥保管库的步骤，可指导你完成安装和启动 Azure PowerShell、连接到 Azure 订阅、创建资源组以及创建该资源组中密钥保管库的步骤。
  
创建密钥保管库时，必须选择 SKU：Standard 或 Premium。 标准 SKU 允许使用软件保护 Azure 密钥保管库密钥（没有硬件安全模块 (HSM) 密钥保护）并且高级 SKU 允许使用 HSM 来保护密钥保管库密钥。 客户密钥接受使用任一 SKU 的密钥保管库，但 Microsoft 强烈建议你仅使用高级 SKU。 使用任一类型的密钥的操作成本相同，因此成本的唯一差别是每个受 HSM 保护的密钥的每月成本。 有关详细信息 [，请参阅密钥保管](https://azure.microsoft.com/pricing/details/key-vault/) 库定价。
  
> [!IMPORTANT]
> 将高级 SKU 密钥保管库和 HSM 保护的密钥用于生产数据，并且仅将标准 SKU 密钥保管库和密钥用于测试和验证目的。

对密钥保管库使用通用前缀，并包括密钥保管库和密钥的使用和范围的缩写。 例如，对于保管库将位于北美的 Contoso 服务，可能的名称对是 Contoso-O365-NA-VaultA1 和 Contoso-O365-NA-VaultA2。 保管库名称是 Azure 中的全局唯一字符串，因此你可能需要尝试所需名称的变体，以防其他 Azure 客户已声明所需的名称。 配置后，无法更改保管库名称，因此最佳做法是制定一份书面设置计划，并使用第二个人验证计划是否正确执行。

如果可能，在非配对区域创建保管库。 成对的 Azure 区域跨服务失败域提供高可用性。 因此，可以将区域对视为彼此的备份区域。 这意味着，放置在一个地区的 Azure 资源通过配对区域自动获得容错能力。 因此，为数据加密策略中使用的两个保管库选择区域（这些区域已配对）意味着总共只有两个可用性区域在使用。 大多数地理位置只有两个区域，因此尚无法选择非配对区域。 如果可能，请为与数据加密策略一同使用的两个保管库选择两个非配对区域。 这从共四个可用性区域中获益。 有关详细信息，请参阅 BCDR (业务连续性和灾难恢复 [) ：当前](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 区域对列表的 Azure 配对区域。

### <a name="assign-permissions-to-each-key-vault"></a>为每个密钥保管库分配权限

对于每个密钥保管库，你将需要为客户密钥定义三组单独的权限，具体取决于你的实现。 例如，您需要为以下各项定义一组权限：
  
- **将为组织执行** 密钥保管库日常管理的关键保管库管理员。 这些任务包括备份、创建、获取、导入、列表和还原。

  > [!IMPORTANT]
  > 分配给密钥保管库管理员的权限集不包括删除密钥的权限。 这是有意为之，也是一项重要的做法。 通常不删除加密密钥，因为这样做会永久破坏数据。 作为最佳实践，默认情况下不要向密钥保管库管理员授予此权限。 相反，请为密钥保管库参与者保留此策略，并且仅在明确了解后果后将其短期分配给管理员。
  
  若要向贵组织的用户分配这些权限，请通过 Azure PowerShell 登录 Azure 订阅。 有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

   运行 Set-AzKeyVaultAccessPolicy cmdlet 以分配必要的权限。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   例如：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **可以更改 Azure** 密钥保管库本身权限的密钥保管库参与者。 当员工离开或加入团队时，或者当密钥保管库管理员合法需要删除或还原密钥的极少数情况下，你将需要更改这些权限。 需要向这组密钥保管库参与者授予密钥保管库上的参与者角色。 可以使用 Azure 资源管理器分配此角色。 有关详细步骤，请参阅使用 [Role-Based访问控制](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) 管理对 Azure 订阅资源的访问权限。 默认情况下，创建订阅的管理员具有此访问权限，并且能够将其他管理员分配到参与者角色。

- **Microsoft 365** 静态数据加密服务，该服务在租户级别处理客户密钥的工作。 若要向 Microsoft 365 授予权限，请运行 **Set-AzKeyVaultAccessPolicy** cmdlet，使用下列语法：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  其中：

  - *保管库* 名称是创建的密钥保管库的名称。

  示例：对于 Microsoft 365 静态数据加密服务，将 *Microsoft 365 appID 替换为*`c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>启用密钥保管库，然后确认软删除

如果可以快速恢复密钥，不太可能因意外或恶意删除密钥而遇到服务中断。 启用此配置（称为软删除）后，才能将密钥与客户密钥一同使用。 启用软删除后，您可以在删除后 90 天内恢复密钥或保管库，而无需从备份中还原它们。
  
若要在密钥保管库上启用软删除，请完成以下步骤：
  
1. 使用 Windows PowerShell 登录 Azure 订阅。 有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. 运行 [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet。 本示例中， *保管库* 名称是要启用软删除的密钥保管库的名称：

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. 通过运行 **Get-AzKeyVault** cmdlet 确认为密钥保管库配置了软删除。 如果为密钥保管库正确配置了软删除，则"启用 _软_ 删除"属性将返回值 **True**：

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>通过创建或导入密钥将密钥添加到每个密钥保管库

有两种方法可以将密钥添加到 Azure 密钥保管库;可以直接在密钥保管库中创建密钥，也可以导入密钥。 直接在密钥保管库中创建密钥是不太复杂的方法，而导入密钥可提供对密钥生成方式的总控制。 使用 RSA 密钥。 Azure Key Vault 不支持使用椭圆曲线键换行和取消环绕。
  
若要直接在密钥保管库中创建密钥，请运行 [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet，如下所示：
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

其中：

- *保管* 库名称是你想要创建密钥的密钥保管库的名称。

- *key name* 是你想要提供新密钥的名称。

  > [!TIP]
  > 使用与上述密钥保管库类似的命名约定命名密钥。 这样，在只显示键名称的工具中，字符串是自描述的。
  
如果要使用 HSM 保护密钥，请确保将 **HSM** 指定为 _Destination_ 参数的值，否则请指定 **Software**。

例如，
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>检查密钥的恢复级别

Microsoft 365 要求 Azure 密钥保管库订阅设置为"不取消"，并且客户密钥使用的密钥已启用软删除。 可以通过查看密钥的恢复级别来确认这一点。
  
若要检查密钥的恢复级别，请在 Azure PowerShell 中运行 Get-AzKeyVaultKey cmdlet，如下所示：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

如果恢复级别属性返回除 **Recoverable+ProtectedSubscription** 值外的其他值，则需要查看本文，并确保已遵循所有步骤将订阅置于"不取消"列表，并且在每个密钥保管库上启用了"软删除"。 接下来，将 电子邮件中的 输出屏幕截图 `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` 发送到 m365ck@microsoft.com。

### <a name="back-up-azure-key-vault"></a>备份 Azure Key Vault

创建或更改密钥后，立即执行备份并存储备份副本（联机和脱机）。 不要将脱机副本连接到任何网络。 相反，将它们存储在物理安全或商业存储设备中。 应至少将一份备份副本存储在发生灾难时可访问的位置。 如果密钥保管库密钥被永久销毁或呈现为不可操作，备份 blob 是还原密钥材料的唯一方法。 Azure 密钥保管库外部且已导入 Azure 密钥保管库的密钥不符合备份条件，因为外部密钥中不存在客户密钥使用该密钥所需的元数据。 只有从 Azure 密钥保管库获取的备份可用于使用客户密钥执行还原操作。 因此，在上载或创建密钥后对 Azure 密钥保管库进行备份至关重要。
  
若要创建 Azure 密钥保管库密钥的备份，请运行 [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet，如下所示：

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

确保输出文件使用后缀 `.backup` 。
  
此 cmdlet 生成的输出文件已加密，不能在 Azure Key Vault 外部使用。 备份只能还原到进行备份的 Azure 订阅。
  
例如：
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>验证 Azure 密钥保管库配置设置

在 DEP 中使用密钥之前执行验证是可选的，但强烈建议这样做。 特别是，如果使用除本主题中所述的步骤外的其他步骤设置密钥和保管库，应在配置客户密钥之前验证 Azure Key Vault 资源的运行状况。
  
若要验证密钥是否已启用 get、wrapKey 和 unwrapKey 操作：
  
运行 [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

在输出中，查找访问策略，并查找适用于 GUID (的 Microsoft 365) ID。 所有三个操作（get、wrapKey 和 unwrapKey）都必须显示在"密钥权限"下。
  
如果访问策略配置不正确，请Set-AzKeyVaultAccessPolicy cmdlet，如下所示：
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

示例：对于 Microsoft 365 静态数据加密服务，将 *Microsoft 365 appID 替换为*`c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

若要验证未为密钥设置到期日期，请运行 [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

客户密钥无法使用过期密钥，尝试使用过期密钥的操作将失败，并可能导致服务中断。 我们强烈建议用于客户密钥的密钥没有过期日期。 一旦设置过期日期，就无法删除，但可以更改为其他日期。 如果必须使用设置了过期日期的密钥，将过期值更改为 12/31/9999。 到期日期设置为 12/31/9999 外日期的密钥无法通过 Microsoft 365 验证。
  
若要更改已设置为 12/31/9999 外的任何值的到期日期，请运行 [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>获取每个 Azure 密钥保管库密钥的 URI

完成 Azure 中设置密钥保管库并添加密钥的所有步骤后，运行以下命令，获取每个密钥保管库中密钥的 URI。 稍后创建和分配每个 DEP 时，将需要使用这些 URI，因此将此信息保存在一个安全的位置。 请记住，针对每个密钥保管库运行一次此命令。
  
在 Azure PowerShell 中：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>为租户设置客户密钥加密策略

您需获得权限，然后才能运行这些 cmdlet。 虽然本文列出了 cmdlet 的所有参数，但如果这些参数未包含在分配给您的权限中，则您可能无法访问这些参数。 若要查找在贵组织中运行任何 cmdlet 或参数所需的权限，请参阅 [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)。

### <a name="create-policy"></a>创建策略

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

说明：允许合规性管理员使用两个 AKV 根密钥 (DEP) 数据加密策略。 创建策略后，可以使用 cmdlet 分配Set-M365DataAtRestEncryptionPolicyAssignment策略。 第一次分配密钥或旋转密钥后，新密钥可能需要 24 小时才能生效。 如果新的 DEP 需要 24 小时以上才能生效，请与 Microsoft 联系。

示例：

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

参数：

| 名称 | 说明 | 可选 (Y/N)  |
|----------|----------|---------|
|名称|数据加密策略的友好名称|网络|
|AzureKeyIDs|指定 Azure 密钥保管库密钥的两个 URI 值（用逗号分隔）以与数据加密策略关联|网络|
|描述|数据加密策略的说明|网络|

### <a name="assign-policy"></a>分配策略

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "<Default_PolicyName or Default_PolicyID>"
```

说明：此 cmdlet 用于配置默认数据加密策略。 然后，此策略将用于加密所有支持工作负载的数据。 

示例：

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Default_PolicyName"
```

参数：

| 名称 | 说明 | 可选 (Y/N)  |
|----------|----------|---------|
-DataEncryptionPolicy|指定需要分配的数据加密策略;指定策略名称或策略 ID。|网络|

### <a name="modify-or-refresh-policy"></a>修改或刷新策略

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

说明：该 cmdlet 可用于修改或刷新现有策略。 它还可用于启用或禁用策略。 第一次分配密钥或旋转密钥后，新密钥可能需要 24 小时才能生效。 如果新的 DEP 需要 24 小时以上才能生效，请与 Microsoft 联系。

示例：

禁用数据加密策略。

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

刷新数据加密策略。

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "EUR Policy" -Refresh
```

参数：

| 名称 | 说明 | 可选 (Y/N)  |
|----------|----------|---------|
|-Identity|指定要修改的数据加密策略。|网络|
|-Refresh|在 Azure Key Vault 中旋转任意关联密钥后，使用 Refresh 开关更新数据加密策略。 不必为此开关指定值。|Y|
|- 已启用|Enabled 参数启用或禁用数据加密策略。 在禁用策略之前，必须从租户取消分配它。 有效值为：</br > $true：策略已启用</br > $true：启用此策略。此为默认值。
|Y|
|-Name|Name 参数指定数据加密策略的唯一名称。|Y|
|-Description|Description 参数指定数据加密策略的可选说明。|Y|

### <a name="get-policy-details"></a>获取策略详细信息

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

说明：此 cmdlet 列出了为租户创建的所有 M365DataAtRest 加密策略或有关特定策略的详细信息。

示例：

本示例返回组织中 M365DatAtRest 加密策略的摘要列表。

```powershell
Get-M365DataAtRestEncryptionPolicy
```

此示例返回名为"NAM Policy"的数据加密策略的详细信息。

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

参数：

| 名称 | 说明 | 可选 (Y/N)  |
|----------|----------|---------|
|-Identity|指定要列出其详细信息的数据加密策略。|Y|

### <a name="get-policy-assignment-info"></a>获取策略分配信息

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

说明：此 cmdlet 列出当前分配给租户的策略。

## <a name="offboarding-from-customer-key"></a>从客户密钥中载出

如果需要恢复为 Microsoft 管理的密钥，可以。 当你离开时，你的数据会使用每个工作负荷支持的默认加密重新加密。 例如，Exchange Online 支持使用 Microsoft 管理的密钥进行默认加密。

如果你决定从租户级别的客户密钥退出租户，请通过电子邮件请求联系 Microsoft，以"禁用 ["](mailto:m365ck@microsoft.com)租户服务，m365ck@microsoft.com。

> [!IMPORTANT]
> 载出与数据清除不同。 数据清除会从 Microsoft 365 中永久加密删除组织的数据，但无法从载出中删除。 无法对租户级别的策略执行数据清除。 有关数据清除路径的信息，请参阅 [撤销密钥并开始数据清除路径过程](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。

## <a name="about-the-availability-key"></a>关于可用性密钥

有关可用性密钥的信息，请参阅 [了解可用性密钥](customer-key-availability-key-understand.md)。

## <a name="key-rotation"></a>密钥旋转

有关旋转或滚动客户密钥使用密钥的信息，请参阅滚动或旋转 [客户密钥或可用性密钥](customer-key-availability-key-roll.md)。 更新 DEP 以使用新版本的密钥时，将运行 Set-M365DataAtRestEncryptionPolicy cmdlet，如本文前面所述。

## <a name="related-articles"></a>相关文章：

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [服务加密](office-365-service-encryption.md)
