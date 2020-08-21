---
title: 设置客户密钥
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
description: 了解如何为 Microsoft 365 for Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和 Teams 文件设置客户密钥。
ms.openlocfilehash: 87c18c1695d2963fc8a0c064d34d2b6cdc14199c
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845830"
---
# <a name="set-up-customer-key"></a>设置客户密钥

使用客户密钥，你可以控制组织的加密密钥，然后配置 Microsoft 365 以使用它们加密 Microsoft 的数据中心内的静态数据。 换句话说，客户密钥允许客户将属于他们的加密层与密钥一起添加。 具有处于唯一状态的 Exchange Online 和 Skype for Business 中的数据，这些数据存储在 SharePoint Online 和 OneDrive for Business 中的邮箱和文件中。

必须先设置 Azure，然后才能将客户密钥用于 Office 365。 本主题介绍创建和配置所需 Azure 资源需遵循的步骤，然后提供在 Office 365 中设置客户密钥的步骤。 完成 Azure 设置后，你将确定要分配给组织中邮箱和文件的策略以及哪些密钥。 未为其分配策略的邮箱和文件将使用由 Microsoft 进行控制和管理的加密策略。 有关客户密钥或常规概述的详细信息，请参阅 [Office 365 中使用客户密钥进行服务加密](customer-key-overview.md)。
  
> [!IMPORTANT]
> 强烈建议您遵循本主题中的最佳做法。 这些被称为**TIP 和** **IMPORTANT。** 客户密钥使你可以控制其作用域可能在整个组织范围内的根加密密钥。 这意味着，使用这些关键所做的错误可能会对你造成广泛影响，并且可能会导致数据服务中断或无法撤消丢失数据。
  
## <a name="before-you-set-up-customer-key"></a>设置客户密钥之前

在开始之前，请确保您具有适合你的组织的相应许可。 Office 365 E5 或高级合规 SKU 中提供 Microsoft 365 中的客户密钥。 若要了解本主题中的概念和过程，请查看 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) 文档。 同时，您也熟悉 Azure 中使用的条款，例如 [租户](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100))。

FastTrack 仅用于收集用于注册客户密钥的必需租户和服务配置信息。 客户密钥优惠通过 FastTrack 发布，便于你和我们的合作伙伴使用相同方法提交所需信息。 FastTrack 还便于存档在产品/服务中提供的数据。
  
如果还需要文档以外的其他支持，请与 Microsoft 咨询服务 (MCS) Premier Field Engineering (PFE) 或 Microsoft 合作伙伴获取帮助。 要提供有关客户密钥的反馈，包括文档、向你的想点、建议和customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>设置客户密钥的步骤概述

若要设置客户密钥，请按列出的顺序完成这些任务。 本文的其余部分提供了每个任务的详细说明，或链接指向该过程中每个步骤的详细信息。
  
**在 Azure 和 Microsoft FastTrack 中：**
  
您将通过远程连接到 Azure PowerShell 来完成大部分这些任务。 为了获得最佳结果，请使用 Azure PowerShell 的 4.4.0 版本或更高版本。
  
- [创建两个新的 Azure 订阅](#create-two-new-azure-subscriptions)

- [注册 Azure 订阅以使用强制保留期](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  注册可能需要一到五个工作日。

- [提交请求以激活 Office 365 客户密钥](#submit-a-request-to-activate-customer-key-for-office-365)

创建两个新的 Azure 订阅后，你将需要通过完成 Microsoft FastTrack 门户中承载的 Web 表单提交相应的客户密钥/服务请求。 **FastTrack 团队不协助客户密钥。Office 只需使用 FastTrack 门户提交表单，并帮助我们跟踪与客户密钥的相关产品/服务**。

- [在每个订阅中创建高级 Azure Key Vault](#create-a-premium-azure-key-vault-in-each-subscription)

- [向每个密钥保管人分配权限](#assign-permissions-to-each-key-vault)

- [启用密钥保管库后进行确认删除](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [通过创建或导入密钥为每个密钥保管库添加密钥](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [检查密钥的恢复级别](#check-the-recovery-level-of-your-keys)

- [备份 Azure Key Vault](#back-up-azure-key-vault)

- [验证 Azure Key Vault 配置设置](#validate-azure-key-vault-configuration-settings)

- [获取每个 Azure 密钥保管库密钥的 URI](#obtain-the-uri-for-each-azure-key-vault-key)

**在 Office 365 中：**
  
Exchange Online 和 Skype for Business：
  
- [创建数据加密策略 (DEP) 用于 Exchange Online 和 Skype for Business](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [为邮箱分配 DEP](#assign-a-dep-to-a-mailbox)

- [验证邮箱加密](#validate-mailbox-encryption)

SharePoint Online 和 OneDrive for Business：
  
- [为每个 SharePoint Online (OneDrive for Business) 创建数据加密策略](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [验证 SharePoint Online、OneDrive for Business 和 Teams 文件的文件加密](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>在 Azure 密钥保管库和适用于客户密钥的 Microsoft FastTrack 中完成任务

在 Azure 密钥保管库中完成这些任务。 无论是要为 Exchange Online 和 Skype for Business 设置了"客户密钥"，还是为 SharePoint Online、OneDrive for Business 和 Teams 文件设置了"客户密钥"，或 Office 365 中所有受支持的服务，都需要完成这些步骤。
  
### <a name="create-two-new-azure-subscriptions"></a>创建两个新的 Azure 订阅

客户密钥需要两个 Azure 订阅。 作为最佳做法，Microsoft 建议创建新的 Azure 订阅以用于客户密钥。 Azure Key Vault 密钥只能被授予同一 Azure Active Directory (AAD) 租户中的应用程序，你必须使用与将分配 DeSP 的组织所用的相同 Azure AD 租户创建新订阅。 例如，使用在组织中拥有全局管理员权限的工作或学校帐户。 有关详细步骤，[请参阅"注册作为组织"的 Azure。](https://azure.microsoft.com/documentation/articles/sign-up-organization/)
  
> [!IMPORTANT]
> 客户密钥要求每个数据加密策略需要两个密钥 (DEP) 。 为此，你必须创建两个 Azure 订阅。 作为最佳做法，Microsoft 建议在每个订阅中配置组织的单独成员。 此外，这些 Azure 订阅应仅用于管理 Office 365 的加密密钥。 这将在防止你的组织意外、有意删除或恶意删除时受到保护，否则不对其负责的密钥进行管理。 <br/> 建议设置新的 Azure 订阅，这些订阅仅用于管理 Azure 密钥保管库资源，以便用于客户密钥。 对于可为组织创建的 Azure 订阅数没有实际限制。 遵循这些最佳做法可最大限度地减少人为错误的影响，同时帮助管理客户密钥使用的资源。
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>提交请求以激活 Office 365 客户密钥

完成 Azure 步骤后，你将需要在 Microsoft FastTrack 门户中提交优 [惠请求](https://fasttrack.microsoft.com/)。 一经通过 FastTrack Web 门户提交请求后，Microsoft 将验证你提供的 Azure Key Vault 配置数据和联系人信息。 您在产品/服务表单中所做的有关组织的授权主管的选择至关重要，并且这是完成客户密钥注册所必需的。 表单中选择的组织主管将用于确保撤销和销销用于客户密钥数据加密策略的所有密钥的任何请求的真实性。 一步只需执行一次才能激活 Exchange Online 和 Skype for Business 的客户密钥，并需要第二次才能激活 SharePoint Online 和 OneDrive for Business 的客户密钥。
  
要提交用于激活客户密钥的产品/服务，请完成以下步骤：
  
1. 使用在组织中拥有全局管理员权限的工作或学校帐户登录到 [Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。

2. 登录后，浏览到 **仪表板**。

3. 从**导航**栏选择"部署 **"或**选择 **"在'部署信息卡****上查看'部署'** 资源"，然后查看当前产品/服务列表。

4. 选择适用于您的优惠的信息卡：

   - **Exchange Online 和 Skype for Business：** 为 **Exchange Online 产品选择请求加密密钥帮助** 。

   - **SharePoint Online、OneDrive 和 Teams 文件：** 为 **Sharepoint 和 OneDrive 产品选择请求加密密钥** 帮助。

5. 查看优惠详细信息后，选择"继续**执行第 2 步"。**

6. 填写所有适用的详细信息，并在优惠表单上填写请求的信息。 特别注意你所选择的选择，您希望向组织内人员授权批准加密密钥和数据的永久及不可恢复销销。 完成表单后，选择"**提交"。**

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>注册 Azure 订阅以使用强制保留期

根加密密钥的临时或永久丢失可能非常中断，甚至可能会导致服务操作的统计性问题，并且会导致数据丢失。 因此，与客户密钥一起使用的资源需要强有强的保护。 用于客户密钥的所有 Azure 资源都提供一些不在默认配置的保护机制。 可以标记或注册 Azure 订阅，从而阻止立即和不可撤销。 这称为注册强制保留期。 为强制保留期注册 Azure 订阅所需的步骤需要与 Microsoft 365 团队进行协作。 此过程可能花费一到五个工作日。 以前，这有时称为"不取消"。
  
联系 Microsoft 365 团队之前，必须为用于客户密钥的每个 Azure 订阅执行以下步骤。 在开始之前， [请确保已安装 Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 模块。
  
1. 使用 Azure PowerShell 登录。 有关说明，请参阅["使用 Azure PowerShell 登录"。](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. 运行 Register-AzProviderFeature cmdlet 注册订阅，以使用强制保留期。 为每个订阅执行此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. 请联系 Microsoft 以完成该过程。 对于 SharePoint 和 OneDrive for Business 团队，[请与spock@microsoft.com。](mailto:spock@microsoft.com) 对于 Exchange Online 和 Skype for Business，[请联系exock@microsoft.com。](mailto:exock@microsoft.com) 在电子邮件中包括以下项：

   **Subject：Customer**Key for \<*Your tenant's fully-qualified domain name*\>

   **正文**：已完成强制保留期的订阅 ID。
   每个订阅的 Get-AzProviderFeature 的输出。

   一年的 (协议 (SLA) 完成此过程的过程是 5 个工作日，一则表示 Microsoft 已被 (并且已验证) 你已注册你的订阅以使用强制保留期。

4. 收到 Microsoft 发送的注册注册通知完成的通知后，按如下所示运行 Get-AzProviderFeature 命令以验证注册状态。 如果已验证，Get-AzProviderFeature 命令将返回注册**状态属性的值"已****注册"。** 为每个订阅执行此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. 若要完成此过程，请运行 Register-AzResourceProvider 命令。 为每个订阅执行此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每个订阅中创建高级 Azure Key Vault

创建密钥保管库的步骤会记录在 Azure Key [Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)入门中。Azure Key Vault 安装和启动 Azure PowerShell、连接到 Azure 订阅、创建资源组和在该资源组中创建密钥保管库的步骤。
  
创建密钥保管库时，必须选择 SKU：标准版或高级版。 标准 SKU 允许使用软件保护 Azure 密钥保管库密钥（没有硬件安全模块 (HSM) 密钥保护），并且高级 SKU 允许使用 HSM 保护密钥保管密钥。 客户密钥接受使用任一 SKU 的密钥保管，但 Microsoft 强烈建议你仅使用高级 SKU。 两种类型的运营的成本都相同，因此，唯一的成本差异是每个受 HSM 保护的密钥的每月成本。 有关详细信息 [，请参阅密钥保管库定](https://azure.microsoft.com/pricing/details/key-vault/) 价。
  
> [!IMPORTANT]
> 将高级 SKU 密钥保管库和受 HSM 保护的密钥用于生产数据，仅使用标准 SKU 密钥和密钥进行测试和验证。
  
对于将使用客户密钥的每个 Microsoft 365 服务，在你创建的两个 Azure 订阅中创建一个密钥保管库。 例如，对于 Exchange Online 和仅 Skype for Business，或仅限 SharePoint Online 和 OneDrive for Business，你只会创建一对保管库。 若要同时为 Exchange Online 和 SharePoint Online 启用客户密钥，您需要创建两对密钥保管库。
  
应对反映要使用的数据加密策略与之关联的数据加密策略的密钥保管进行命名约定。 请参阅下面的"最佳实践"部分，了解命名约定建议。
  
为每个数据加密策略创建一组单独的成对保管的存储库。 对于 Exchange Online，当您向邮箱分配策略时，将选择数据加密策略的作用域。 一个邮箱只能分配一个策略，并且最多可以创建 50 个策略。 对于 SharePoint Online，策略的范围是地理位置或地理位置的组织内 _的所有数据_。

创建密钥保管库也需要创建 Azure 资源组，因为关键保管库需要存储容量 (尽管平均小的) 和密钥保管库进行日志记录（如果启用，则还会生成存储的数据）。 作为最佳做法，Microsoft 建议使用不同的管理员来管理每个资源组，并且管理与将管理所有相关客户主要资源的管理员集相一对。
  
> [!IMPORTANT]
> 为了最大限度地提高可用性，你的关键保管库应位于 Microsoft 365 服务接近的区域中。 例如，如果您的 Exchange Online 组织位于北美，请将关键保管库置于北美。 如果您的 Exchange Online 组织在欧洲，请将关键保管人分于欧洲。<br/>对密钥保管库使用一个公用前缀， 并对保管人和 (项的使用和范围（例如，对于在北美洲托管的 Contoso SharePoint 服务的话，可能的一对名为 Contoso-O365SP-NA-VaultA1 和 Contoso-O365SP-NAultA2）的使用和范围。这包括有关这些保管人的使用和范围的缩写。 存储库名称是 Azure 中的全局唯一字符串，因此可能需要尝试对期名称的变体，以防其他 Azure 客户已经声明了所需的名称。 由于无法更改 2017 年 7 月的存储库名称，因此最佳做法是，使用书面编写计划设置并使用第二个人验证计划是否正确执行。<br/>如果可能，请在非配对区域中创建你的保管者。 配对的 Azure 区域在服务故障域中提供高可用性。 因此，可以要求将区域对作为对应的备份区域。 这意味着放置在一个区域中的 Azure 资源将通过配对区域自动获取容错。 因此，选择在一个数据加密策略中使用的两个保管区域，其中区域是成对的表示仅使用共有两个可用性区域。 大多数地理区域只有两个区域，因此，尚未选择非配对区域。 如果可能，请为用于数据加密策略的两个保管库选择两个非配对地区。 这一总可用性从四个区域中受益。 有关详细信息，请参阅 ["业务连续性和灾难恢复 (BCDR) ：Azure 配对区域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) "以获取区域对列表。
  
### <a name="assign-permissions-to-each-key-vault"></a>向每个密钥保管人分配权限

对于每个关键保管库，您需要根据你的实施定义客户密钥定义三个单独的权限集。 例如，您需要为以下每个对象定义一个权限集：
  
- **将对组织的密钥** 保管库进行日常管理的关键保管者。 这些任务包括备份、创建、获取、导入、列表和还原。

  > [!IMPORTANT]
  > 分配给关键保管库管理员的权限集不包括删除键的权限。 这个重要做法是重要的做法， 通常不会删除加密密钥，因为这样操作会永久销销数据。 作为最佳实践，默认情况下不要将此权限授予密钥保管库管理员。 而是要保留此功能以供主要保管人参与者使用，并且只在清楚了解后果后只将它分配给管理员。
  
  若要将这些权限分配给组织用户，请使用 Azure PowerShell 登录到 Azure 订阅。 有关说明，请参阅["使用 Azure PowerShell 登录"。](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

- 运行 Set-AzKeyVaultAccessPolicy cmdlet 以分配必要的权限。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   例如：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **可更改 Azure Key Vault** 本身的权限的密钥保管者。 在员工离开或加入团队时，你需要更改这些权限，或在几大少数情况下，大家保管管理员自行需要删除或还原密钥的权限。 需向此保管库明的参与者授予这组关键保管者。 **Contributor** 你可以使用 Azure 资源管理器分配此角色。 有关详细步骤，请参阅 ["使用基于角色的访问控制"管理对 Azure 订阅资源的访问权限](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。 创建订阅的管理员隐式具有此访问权限，并具有向参与者角色分配其他管理员的功能。

- 如果你计划将客户密钥用于 Exchange Online 和 Skype for Business，需要授予 Microsoft 365 权限，以代表 Exchange Online 和 Skype for Business 使用密钥保管库。 同样，如果你计划对 SharePoint Online 和 OneDrive for Business 使用客户密钥，则需要添加 Microsoft 365 的权限，以代表 SharePoint Online 和 OneDrive for Business 使用密钥保管库。 若要授予 Microsoft 365 的权限，请使用以下 **语法运行 Set-AzKeyVaultAccessPolicy** cmdlet： 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   其中：

    - *存储库名称* 是你创建的密钥保管库的名称。

    - 对于 Exchange Online 和 Skype for Business，将*Office 365 appID 替换为*`00000002-0000-0ff1-ce00-000000000000`

    - 对于 SharePoint Online、OneDrive for Business 和 Teams 文件，将*Office 365 appID 替换为*`00000003-0000-0ff1-ce00-000000000000`

  示例：为 Exchange Online 和 Skype for Business 设置权限：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  示例：为 SharePoint Online、OneDrive for Business 和 Teams 文件设置权限：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>启用密钥保管库后进行确认删除

当你可以快速恢复密钥时，你可能因意外或恶意删除的密钥而体验到长时间的服务中断。 您需要启用此配置（称为"自动删除"）后才可以将密钥与客户密钥一起使用。 启用"Soft Delete"允许您在删除后 90 天内恢复密钥或保管库，而无需从备份中还原密钥或附件。
  
若要启用密钥保管库上的"Soft Delete"，请完成以下步骤：
  
1. 通过 Windows Powershell 登录到 Azure 订阅。 有关说明，请参阅["使用 Azure PowerShell 登录"。](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. 运行 [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet。 在此示例中， *被保管人名称* 为你启用了"soft delete"的密钥保管库的名称：

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. 通过运行 **Get-AzKeyVault** cmdlet 确认已为密钥保管库配置了"soft delete"。 如果为密钥保管库正确配置了"soft delete"，_则"Soft Delete Enabled"_ 属性的值为**True：**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>通过创建或导入密钥为每个密钥保管库添加密钥

有两种方法可以向 Azure 密钥保管库中添加密钥;可直接在密钥保管库中创建密钥，也可以导入密钥。 直接在键保管库中创建键是不太复杂的方法，而导入密钥可提供对生成密钥方式的总控制。
  
若要直接在密钥保管库中创建密钥，请运行 [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet，如下所示：
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

其中：

- *存储库名称* 是你希望在其中创建密钥的密钥保管库的名称。

- *项名称* 是要为新项命名的名称。

  > [!TIP]
  > 使用类似的命名约定命名密钥，如上所述对于密钥保管库。 这样，在仅显示密钥名称的工具中，字符串为自描述。
  
- 如果要使用 HSM 保护该密钥，请确保将 **HSM 指定** 为 _Destination 参数的值_ ，否则请指定 **Software**。

例如，
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

若要直接将密钥导入密钥保管库，需要有一个嵌套硬件安全模块。
  
一些组织首选这种方法来建立密钥的验证，然后此方法还提供以下方法：
  
- 用于导入的工具集包括来自用于加密所生成的密钥的 Exchange 密钥 (KEK) 的证明，并且该密钥是在由 nCipher 制造的一个定型 HSM 内生成的。

- 该工具集包括来自 nCipher 的证明，Azure Key Vault 安全性世界也是在 nCipher 的一种形型 HSM 制造中生成的。 此证明向你证明 Microsoft 也使用正版 NCipher 硬件。

与你的安全组进行检查，以确定是否需要上面的证明。 有关在内部创建密钥并将其导入关键保管库的详细步骤，请参阅["如何为 Azure 密钥保管库生成并传输受 HSM 保护的密钥"。](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/) 使用 Azure 说明在每个密钥保管库中创建密钥。
  
### <a name="check-the-recovery-level-of-your-keys"></a>检查密钥的恢复级别

Microsoft 365 要求 Azure 密钥保管库订阅被设置为"不取消"，并且客户密钥使用的密钥已启用了"已自动删除"。 你可以通过查看密钥上的恢复级别进行确认。
  
若要检查密钥的恢复级别，请在 Azure PowerShell 中运行 Get-AzKeyVaultKey cmdlet，如下所示：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

如果 _恢复级别属性返回_ 除 **"可恢复 - ProtectedSubscription"的值之外的任何值**，则需要查看本主题并确保你已遵循所有将订阅置于"不取消"列表上的步骤，并且已在每个密钥保管库上启用了"已自动删除"。
  
### <a name="back-up-azure-key-vault"></a>备份 Azure Key Vault

创建之后或对密钥的任何更改后，立即执行备份的备份和存储副本（联机和脱机）。 脱机副本不应该连接到任何网络，例如物理安全或商业存储设施。 至少应将一个备份副本存储在发生灾难时可以访问的位置中。 备份 blob 是还原密钥材料唯一的方法，这应该是密钥保证密钥永久损坏或以其他方式呈现的不可操作。 Azure Key Vault 外部的且已导入到 Azure 密钥保管库的密钥不限定为备份，因为客户密钥使用所需的元数据在外部密钥中不存在。 只有 Azure 密钥 Vault 进行的备份可用于通过客户密钥执行还原操作。 因此，一定要在上传或创建密钥后创建 Azure 密钥保管库的备份。
  
若要创建 Azure 密钥保管库的备份，请 [运行 Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet，如下所示：

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

确保输出文件使用后缀 `.backup` 。
  
此 cmdlet 产生的输出文件将进行加密，不能在 Azure 密钥保管库外部使用。 备份只能还原到从中获取备份的 Azure 订阅。
  
> [!TIP]
> 对于输出文件，选择存储库名称和项名的组合。 这将使文件名自描述。 同时，它还可以确保备份文件名不会被合并。
  
例如：
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>验证 Azure Key Vault 配置设置

在 DEP 中使用密钥之前执行验证是可选的，但强烈建议使用。 特别是，如果您使用步骤设置您的密钥和存储库（而不是本主题中介绍的盘）来设置密钥和存储库，应在配置客户密钥之前验证 Azure Key Vault 资源的运行状况。
  
验证是否已启用获取、wrapKey 和 unwrapKey 操作：
  
运行 [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

在输出中，查找访问策略以及 Exchange Online 标识 (GUID)  (GUID 或 SharePoint Online 标识 (GUID) 。 所有这三个权限必须在"密钥的权限"下显示。
  
如果访问策略配置不正确，请运行 Set-AzKeyVaultAccessPolicy cmdlet，如下所示：
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

例如，对于 Exchange Online 和 Skype for Business：
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

例如，对于 SharePoint Online 和 OneDrive for Business：
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

若要验证未为密钥设置过期日期，请运行 [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

客户密钥无法使用过期密钥，并且尝试通过过期密钥的操作将失败，并且可能导致服务中断。 强烈建议用于客户密钥的密钥没有到期日期。 一个已设置、无法删除过期日期，但可以更改为不同的日期。 如果必须使用设置了过期日期的某个项，请将过期值更改为 12/31/9999/ 12。 过期日期为 9999 年 2 月 31 日以外的密钥无法通过 Microsoft 365 验证。
  
若要更改已设置为 1999 年 12 月 31 日以外的任何值的到期日期，请运行 [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 不要对用于客户密钥的加密密钥设置到期日期。
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>获取每个 Azure 密钥保管库密钥的 URI

在 Azure 中完成所有用于设置密钥保管库并添加密钥的步骤后，运行以下命令来获取每个密钥保管库中密钥的 URI。 稍后创建和分配每个 DEP 时需要使用这些 URI，因此请将此信息保存到安全的位置。 请记住针对每个密钥保管库运行一次此命令。
  
在 Azure PowerShell 中：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365：为 Exchange Online 和 Skype for Business 设置客户密钥

在开始之前，请确保已完成安装 Azure 密钥保管库所需的任务。 有关 [信息，请参阅 Azure Key Vault 和 Microsoft FastTrack 中的完成](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 任务。
  
要为 Exchange Online 和 Skype for Business 设置客户密钥，需要通过远程连接到 Exchange Online 的工具来执行这些Windows PowerShell。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>创建数据加密策略 (DEP) 用于 Exchange Online 和 Skype for Business

DEP 与 Azure Key Vault 中存储的一组密钥相关联。 为 Microsoft 365 中的邮箱分配 DEP。 Microsoft 365 随后使用策略中标识的密钥对邮箱进行加密。 若要创建 DEP，您需要之前获得的密钥保管库 URI。 有关[说明，请参阅"获取每个 Azure 密钥保管库密钥的 URI"。](#obtain-the-uri-for-each-azure-key-vault-key)
  
记住！ 创建 DEP 时，需指定驻留在两个不同 Azure Key Vault 中的两个密钥。 确保这些密钥位于两个单独的 Azure 区域，以确保地域冗余。
  
若要创建 DEP，请按照下列步骤操作：
  
1. 在本地计算机上，使用在组织中拥有全局管理员权限的工作或学校帐户[，在 Windows PowerShell 窗口中连接到 Exchange Online PowerShell。](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. 若要创建 DEP，请键入以下命令来使用 New-DataEncryptionPolicy cmdlet。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   其中：

   - *PolicyName* 是您要用于策略的名称。 名称不能包含空格。 例如，USA_mailboxes。

   - *策略描述* 是策略的用户友好描述，有助于您记住策略的用法。 您可以在描述中包含空格。 例如"美国亚库的邮箱的根键"。

   - *KeyVaultURI1* 是策略中第一个密钥的 URI。 例如，<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>。

   - *KeyVaultURI2* 是策略中第二个键的 URI。 例如，<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>。 两个 URI 之间用逗号和空格分隔。

   示例：
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

有关语法和参数的详细信息，请参阅[New-DataEncryptionPolicy。](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)

### <a name="assign-a-dep-to-a-mailbox"></a>为邮箱分配 DEP

使用 Set-Mailbox cmdlet 为邮箱分配 DEP。 分配策略后，Microsoft 365 可以使用 DEP 中指定的密钥加密邮箱。
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

*其中，MailboxIdParameter*指定邮箱。 有关 Set-Mailbox cmdlet 的详细信息，请参阅[Set-Mailbox。](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)

对于 [将 Outlook for iOS 和 Outlook for Android 与混合新式验证一](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)起使用的本地邮箱，同步到 Exchange Online 租户的本地邮箱数据可以使用 Set-MailUser cmdlet 分配 DEP。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中 *MailUserIdParameter* 指定邮件用户 (一个也称为启用邮件) 。 有关 Set-MailUser cmdlet 的详细信息，请参阅 [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)。
  
### <a name="validate-mailbox-encryption"></a>验证邮箱加密

加密邮箱可能需要一些时间。 对于首次分配策略，邮箱还必须将它从一个数据库完全移动到另一个数据库，服务才能加密邮箱。 建议你等待 72 小时，然后再在更改 DEP 或首次为邮箱分配 DEP 之后尝试验证加密。
  
使用 Get-MailboxStatistics cmdlet 可确定邮箱是否加密。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果邮箱已加密，则 IsEncrypted 属性返回 **true** 值;如果邮箱未 **加密，则** 返回 false 值。

完成邮箱移动的时间取决于首次向其分配 DEP 的邮箱数以及邮箱的大小。 如果从分配 DEP 指定的一周后未对邮箱加密，请与 Microsoft 联系。

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365：为 SharePoint Online、OneDrive for Business 和 Teams 文件设置客户密钥

在开始之前，请确保已完成安装 Azure 密钥保管库所需的任务。 有关 [信息，请参阅 Azure Key Vault 和 Microsoft FastTrack 中的完成](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 任务。
  
若要设置 SharePoint Online、OneDrive for Business 和 Teams 文件的客户密钥，需要通过远程连接到 SharePoint Online 和 Windows PowerShell 来执行这些步骤。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>为每个 SharePoint Online (OneDrive for Business) 创建数据加密策略

将 DEP 与 Azure Key Vault 中存储的一组密钥相关联。 你可以将 DEP 应用于位于一个地理位置（也称为"地理"）中的所有数据。 如果使用 Office 365 多地理位置功能，可以为每个地理位置创建一个 DEP，使每个地理位置使用不同的密钥。 如果你未使用多地理位置，则可在组织中创建一个 DEP 以用于 SharePoint Online、OneDrive for Business 和 Teams 文件。 Microsoft 365 使用 DEP 中标识的密钥对该地理位置中的数据进行加密。 若要创建 DEP，您需要之前获得的密钥保管库 URI。 有关[说明，请参阅"获取每个 Azure 密钥保管库密钥的 URI"。](#obtain-the-uri-for-each-azure-key-vault-key)
  
记住！ 创建 DEP 时，需指定驻留在两个不同 Azure Key Vault 中的两个密钥。 确保这些密钥位于两个单独的 Azure 区域，以确保地域冗余。
  
若要创建 DEP，需要使用 Windows PowerShell 远程连接到 SharePoint Online。
  
1. 在本地计算机上，使用在组织中拥有全局管理员权限的工作或学校帐户[连接到 SharePoint Online Powershell。](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. 在 Microsoft SharePoint Online 命令行管理程序中，运行 Register-SPODataEncryptionPolicy cmdlet，如下所示：

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   注册 DEP 时，加密将从地理位置中的数据开始。 这可能需要一些时间。

### <a name="validate-file-encryption"></a>验证文件加密

 若要验证 SharePoint Online、OneDrive for Business 和 Teams 文件的加密 [，请连接到 SharePoint Online PowerShell，](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)然后使用 Get-SPODataEncryptionPolicy cmdlet 检查租户的状态。 如果 _启用_ 了客户密钥加密 **且所有** 网站中的所有文件均已加密，则 State 属性返回注册的值。 如果加密仍在进行中，此 cmdlet 则提供有关网站完成百分比的信息。

## <a name="related-articles"></a>相关文章

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [服务加密](office-365-service-encryption.md)
