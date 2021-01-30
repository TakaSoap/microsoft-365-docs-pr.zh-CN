---
title: 在应用程序级别设置客户密钥
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
ms.openlocfilehash: 057f20005e64a15ef18d076206394159d2690818
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058475"
---
# <a name="set-up-customer-key-at-the-application-level"></a>在应用程序级别设置客户密钥

使用客户密钥，可以控制组织的加密密钥，然后将 Microsoft 365 配置为使用这些密钥对 Microsoft 数据中心中的静态数据进行加密。 换句话说，客户密钥允许客户使用其密钥添加属于他们的加密层。 其余数据包括存储在邮箱中的 Exchange Online 和 Skype for Business 数据以及存储在 SharePoint Online 和 OneDrive for Business 中的文件。

必须先设置 Azure，然后才能使用 Office 365 的客户密钥。 本文介绍了创建和配置所需的 Azure 资源所需的步骤，然后提供在 Office 365 中设置客户密钥的步骤。 完成 Azure 设置后，确定要分配给组织中邮箱和文件的策略，以及要分配的密钥。 未为其分配策略的邮箱和文件将使用由 Microsoft 控制和管理的加密策略。 有关客户密钥或一般概述，请参阅 [Office 365](customer-key-overview.md)中具有客户密钥的服务加密。
  
> [!IMPORTANT]
> 强烈建议您遵循本文中的最佳实践。 这些称为 **提示和****重要。** 客户密钥使您可以控制其作用域可以与整个组织一样大的根加密密钥。 这意味着使用这些密钥所出错可能会产生广泛的影响，并可能导致服务中断或不可撤销的数据丢失。
  
## <a name="before-you-set-up-customer-key"></a>设置客户密钥之前

在开始使用之前，请确保你拥有适合你的组织的许可。 使用付费的已开票 Azure 订阅，企业协议云服务提供商。 客户密钥不支持使用即付即用计划或信用卡购买的 Azure 订阅。 从 2020 年 4 月 1 日起，Office 365 中的客户密钥在 Office 365 E5、M365 E5、M365 E5 合规性和 M365 E5 信息保护 & SUS 中提供。 Office 365 高级合规性 SKU 不再可用于购买新许可证。 现有 Office 365 高级合规性许可证将继续受支持。

若要了解本文中的概念和过程，请查看 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) 文档。 此外，请熟悉 Azure 中使用的术语，例如 [，Azure AD 租户](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)。

FastTrack 仅用于收集注册客户密钥所需的租户和服务配置信息。 客户密钥产品/服务通过 FastTrack 发布，以便你和我们的合作伙伴可以使用同一方法提交所需信息。 FastTrack 还便于存档你在产品/服务中提供的数据。
  
如果您需要文档以外的更多支持，请联系 Microsoft 咨询服务 (MCS) 、高级现场工程 (PFE) 或 Microsoft 合作伙伴寻求帮助。 若要提供有关客户密钥（包括文档）的反馈，请将你的想法、建议和角度customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>设置客户密钥的步骤概述

若要设置客户密钥，请按列出的顺序完成这些任务。 本文的其余部分提供了每个任务的详细说明，或指向过程中每个步骤的详细信息的链接。
  
**在 Azure 和 Microsoft FastTrack 中：**
  
你通过远程连接到 Azure PowerShell 完成大部分任务。 为了获得最佳结果，请使用版本 4.4.0 或更高版本的 Azure PowerShell。
  
- [创建两个新的 Azure 订阅](#create-two-new-azure-subscriptions)

- [注册 Azure 订阅以使用强制保留期](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  注册可能需要一到五个工作日。

- [提交激活 Office 365 客户密钥的请求](#submit-a-request-to-activate-customer-key-for-office-365)

创建两个新的 Azure 订阅后，你将需要通过完成 Microsoft FastTrack 门户中托管的 Web 表单来提交相应的客户密钥优惠请求。 **FastTrack 团队不提供有关客户密钥的帮助。Office 只是使用 FastTrack 门户允许你提交表单，并帮助我们跟踪客户密钥的相关产品/服务**。

- [在每个订阅中创建高级 Azure 密钥保管库](#create-a-premium-azure-key-vault-in-each-subscription)

- [为每个密钥保管库分配权限](#assign-permissions-to-each-key-vault)

- [启用密钥保管库，然后确认软删除](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [通过创建或导入密钥将密钥添加到每个密钥保管库](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [检查密钥的恢复级别](#check-the-recovery-level-of-your-keys)

- [备份 Azure 密钥保管库](#back-up-azure-key-vault)

- [验证 Azure 密钥保管库配置设置](#validate-azure-key-vault-configuration-settings)

- [获取每个 Azure 密钥保管库密钥的 URI](#obtain-the-uri-for-each-azure-key-vault-key)

**在 Office 365 中：**
  
Exchange Online 和 Skype for Business：
  
- [在 DEP (创建) 策略，以用于 Exchange Online 和 Skype for Business](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [将 DEP 分配给邮箱](#assign-a-dep-to-a-mailbox)

- [验证邮箱加密](#validate-mailbox-encryption)

SharePoint Online 和 OneDrive for Business：
  
- [为每个 SharePoint Online 和 OneDrive for Business (DEP) 数据加密策略](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [验证 SharePoint Online、OneDrive for Business 和 Teams 文件的文件加密](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>完成 Azure Key Vault 和 Microsoft FastTrack for Customer Key 中的任务

在 Azure 密钥保管库中完成这些任务。 无论是打算为 Exchange Online 和 Skype for Business、SharePoint Online、OneDrive for Business 和 Teams 文件设置客户密钥，还是为 Office 365 中所有受支持的服务设置客户密钥，都需要完成这些步骤。
  
### <a name="create-two-new-azure-subscriptions"></a>创建两个新的 Azure 订阅

客户密钥需要两个 Azure 订阅。 作为最佳实践，Microsoft 建议创建用于客户密钥的新 Azure 订阅。 Azure 密钥保管库密钥只能针对同一 Azure Active Directory (Microsoft Azure Active Directory) 租户中的应用程序授权，必须使用与分配 DEP 的组织一起使用的同一 Azure AD 租户创建新订阅。 例如，使用在组织中具有全局管理员权限的工作或学校帐户。 有关详细步骤，请参阅 [注册 Azure 作为组织](https://azure.microsoft.com/documentation/articles/sign-up-organization/)。
  
> [!IMPORTANT]
> 对于 DEP 策略的每个数据加密策略，客户密钥 (两) 。 为此，必须创建两个 Azure 订阅。 作为最佳实践，Microsoft 建议组织单独的成员在每个订阅中配置一个密钥。 你应仅使用这些 Azure 订阅来管理 Office 365 的加密密钥。 这样可保护你的组织，以防其中一个运营者意外、有意或恶意删除或以其他方式管理他们负责的密钥。
>

你可以为组织创建的 Azure 订阅数量没有实际限制。 遵循这些最佳做法将最大限度地减少人为错误的影响，同时有助于管理客户密钥使用的资源。
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>提交激活 Office 365 客户密钥的请求

完成 Azure 步骤后，你需要在 [Microsoft FastTrack](https://fasttrack.microsoft.com/)门户中提交产品/服务请求。 通过 FastTrack Web 门户提交请求后，Microsoft 会验证你提供的 Azure 密钥保管库配置数据和联系信息。 在产品/服务表单中就组织的授权官员做出的选择对于完成客户密钥注册至关重要且是必需的。 贵组织的官员确保撤销和销毁与客户密钥数据加密策略一同使用的所有密钥的任何请求的真实性。 你需要执行此步骤一次以激活 Exchange Online 和 Skype for Business 的客户密钥，第二次激活 SharePoint Online 和 OneDrive for Business 的客户密钥。
  
若要提交产品/服务以激活客户密钥，请完成以下步骤：
  
1. 使用在组织中具有全局管理员权限的工作或学校帐户，登录到 [Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。

2. 登录后，浏览到 **仪表板**。

3. 从 **导航** 栏中选择 **"部署"** 或选择 **"** 查看部署信息卡上的所有部署资源"，然后查看当前产品/服务的列表。

4. 选择适用于你的产品/服务的信息卡：

   - **Exchange Online 和 Skype for Business：** 选择 **Exchange Online 产品/服务的请求加密密钥** 帮助。

   - **SharePoint Online、OneDrive 和 Teams 文件：** 选择 **Sharepoint 和 OneDrive** 产品/服务的请求加密密钥帮助。

5. 查看产品/服务详细信息后，选择 **"继续步骤 2"。**

6. 填写产品/服务表单上的所有适用详细信息和请求的信息。 请特别注意你选择哪些组织官员有权批准永久和不可恢复的加密密钥和数据销毁。 完成表单后，选择"提交 **"。**

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>注册 Azure 订阅以使用强制保留期

根加密密钥的临时或永久丢失可能会中断甚至对服务操作造成灾难性影响，并可能导致数据丢失。 因此，与客户密钥一起使用的资源需要强大的保护。 用于客户密钥的所有 Azure 资源都提供默认配置以外的保护机制。 你可以标记或注册强制性保留期的 Azure *订阅*。 强制保留期可防止立即和不可撤销地取消 Azure 订阅。 若要为 Azure 订阅注册强制保留期所需的步骤，需要与 Microsoft 365 团队协作。 此过程可能需要一到五个工作日。 以前，强制保留期有时称为"不取消"。
  
在联系 Microsoft 365 团队之前，必须针对使用客户密钥的每个 Azure 订阅执行以下步骤。 在启动之前，请确保已安装 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 模块。
  
1. 使用 Azure PowerShell 登录。 有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. 运行 Register-AzProviderFeature cmdlet 注册订阅以使用强制保留期。 针对每个订阅完成此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. 请与 Microsoft 联系以完成此过程。 对于 SharePoint 和 OneDrive for Business 团队 [，请与](mailto:spock@microsoft.com)spock@microsoft.com。 对于 Exchange Online 和 Skype for Business，请联系[exock@microsoft.com。](mailto:exock@microsoft.com) 在电子邮件中包括以下信息：

   **主题**：客户密钥 \<*Your tenant's fully qualified domain name*\>

   **正文**：包括要完成其强制保留期的订阅 ID 以及每个订阅Get-AzProviderFeature输出。

   一旦 Microsoft 收到 (并验证) 你已注册订阅以使用强制保留期，完成此过程的服务级别协议 (SLA) 即为五个工作日。

4. 从 Microsoft 收到注册完成通知后，通过运行以下 Get-AzProviderFeature命令验证注册状态。 如果验证，则Get-AzProviderFeature返回 **注册** 状态 **属性的值"已注册"。** 针对每个订阅完成此步骤。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. 若要完成此过程，请运行Register-AzResourceProvider命令。 针对每个订阅完成此步骤。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每个订阅中创建高级 Azure 密钥保管库

[Azure](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)密钥保管库入门中记录了创建密钥保管库的步骤，这将指导你安装和启动 Azure PowerShell、连接到 Azure 订阅、创建资源组，以及创建该资源组中的关键保管库。
  
创建密钥保管库时，必须选择 SKU：Standard 或 Premium。 标准 SKU 允许 Azure 密钥保管库密钥受软件保护（没有硬件安全模块 (HSM) 密钥保护）并且高级 SKU 允许使用 HSM 来保护密钥保管库密钥。 客户密钥接受使用任一 SKU 的密钥保管库，但 Microsoft 强烈建议你仅使用高级 SKU。 由于使用任一类型的密钥的操作成本相同，因此成本的唯一差异是每个受 HSM 保护的密钥的每月成本。 有关详细信息 [，请参阅密钥保管](https://azure.microsoft.com/pricing/details/key-vault/) 库定价。
  
> [!IMPORTANT]
> 将高级 SKU 密钥保管库和受 HSM 保护的密钥用于生产数据，并且仅将标准 SKU 密钥保管库和密钥用于测试和验证目的。
  
对于将使用客户密钥的每个 Microsoft 365 服务，在创建的两个 Azure 订阅中分别创建一个密钥保管库。 例如，仅对于 Exchange Online 和 Skype for Business 或仅 SharePoint Online 和 OneDrive for Business，你将仅创建一对保管库。 若要同时为 Exchange Online 和 SharePoint Online 启用客户密钥，需要创建两对密钥保管库。
  
对密钥保管库使用命名约定，该约定反映您将与保管库关联的 DEP 的预定用途。 有关命名约定建议，请参阅下面的"最佳做法"部分。
  
为每个数据加密策略创建一组单独的配对保管库。 对于 Exchange Online，在将策略分配给邮箱时，将选择数据加密策略的范围。 邮箱只能分配一个策略，并且可以创建最多 50 个策略。 SharePoint Online 策略的范围包括组织中地理位置或地理位置内 _的所有数据_。

创建密钥保管库还需要创建 Azure 资源组，因为密钥保管库需要存储容量 (但小型) 和密钥保管库日志记录（如果启用）也会生成存储的数据。 作为最佳做法，Microsoft 建议使用单独的管理员来管理每个资源组，管理方式与将管理所有相关客户密钥资源的管理员集保持一致。
  
> [!IMPORTANT]
> 为了最大限度地提高可用性，密钥保管库应靠近 Microsoft 365 服务的区域。 例如，如果您的 Exchange Online 组织位于北美，则将密钥保管库放在北美。 如果您的 Exchange Online 组织位于欧洲，请在欧洲放置密钥保管库。
> 
> 对密钥保管库使用通用前缀，并包括密钥保管库和密钥 (的使用和范围的缩写，例如，对于位于北美的 Contoso SharePoint 服务，可能的名称对是 Contoso-O365SP-NA-VaultA1 和 Contoso-O365SP-NA-VaultA2。 保管库名称是 Azure 中的全局唯一字符串，因此你可能需要尝试所需名称的变体，以防其他 Azure 客户已声明所需的名称。 自 2017 年 7 月起，无法更改保管库名称，因此最佳做法是制定书面设置计划，并使用第二个人验证计划是否正确执行。
> 
> 如果可能，在非配对区域创建保管库。 配对的 Azure 区域跨服务失败域提供高可用性。 因此，可以将区域对视为彼此的备份区域。 这意味着放置在一个地区的 Azure 资源通过配对区域自动获得容错能力。 因此，为数据加密策略中使用的两个保管库选择区域（其中区域已配对）意味着总共只有两个可用区域在使用。 大多数地理位置只有两个区域，因此尚无法选择非配对区域。 如果可能，为用于数据加密策略的两个保管库选择两个非配对区域。 这从总共四个可用性区域中获益。 有关详细信息，请参阅 BCDR (业务连续性和灾难恢复 [) ：区域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 对当前列表的 Azure 配对区域。
  
### <a name="assign-permissions-to-each-key-vault"></a>为每个密钥保管库分配权限

您需要为每个密钥保管库定义三组单独的权限，具体取决于您的实现。 例如，您需要为以下各项定义一组权限：
  
- **对组织执行** 密钥保管库日常管理的关键保管库管理员。 这些任务包括备份、创建、获取、导入、列表和还原。

  > [!IMPORTANT]
  > 分配给密钥保管库管理员的权限集不包括删除密钥的权限。 这是有意的，也是一项重要的做法。 通常不删除加密密钥，因为这样做会永久破坏数据。 最佳做法是，默认情况下不要向密钥保管库管理员授予此权限。 相反，请保留给密钥保管库参与者，并且仅在明确了解后果后将其短期分配给管理员。
  
  若要向组织中用户分配这些权限，请通过 Azure PowerShell 登录 Azure 订阅。 有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

- 运行 Set-AzKeyVaultAccessPolicy cmdlet 以分配必要的权限。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   例如：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **可更改** Azure 密钥保管库本身权限的关键保管库参与者。 当员工离开或加入团队时，你需要更改这些权限。 在密钥保管库管理员合法需要删除或还原密钥的权限的极少数情况下，您还需要更改权限。 需要向这组密钥保管库参与者授予 **密钥** 保管库上的参与者角色。 可以使用 Azure 资源管理器分配此角色。 有关详细步骤，请参阅Role-Based [访问控制管理对 Azure 订阅资源的访问权限](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。 创建订阅的管理员具有隐式访问权限，并且能够将其他管理员分配到参与者角色。

- 如果你打算将客户密钥与 Exchange Online 和 Skype for Business 一同使用，则需要授予 Microsoft 365 代表 Exchange Online 和 Skype for Business 使用密钥保管库的权限。 同样，如果你打算将客户密钥用于 SharePoint Online 和 OneDrive for Business，则需要添加 Microsoft 365 代表 SharePoint Online 和 OneDrive for Business 使用密钥保管库的权限。 若要向 Microsoft 365 授予权限，请运行 **Set-AzKeyVaultAccessPolicy** cmdlet，使用以下语法：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   其中：

    - *保管* 库名称是创建的密钥保管库的名称。

    - 对于 Exchange Online 和 Skype for Business，将 *Office 365 appID 替换为*`00000002-0000-0ff1-ce00-000000000000`

    - 对于 SharePoint Online、OneDrive for Business 和 Teams 文件，将 *Office 365 appID 替换为*`00000003-0000-0ff1-ce00-000000000000`

  示例：设置 Exchange Online 和 Skype for Business 的权限：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  示例：设置 SharePoint Online、OneDrive for Business 和 Teams 文件的权限：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>启用密钥保管库，然后确认软删除

当你可以快速恢复密钥时，你不太可能因意外或恶意删除的密钥而遇到扩展的服务中断。 你需要启用此配置（称为"软删除"）才能将密钥与客户密钥一同使用。 启用软删除允许您在删除后 90 天内恢复密钥或保管库，而无需从备份中还原它们。
  
若要在密钥保管库上启用软删除，请完成以下步骤：
  
1. 使用帐户登录 Azure Windows PowerShell。 有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. 运行 [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet。 本示例中 *，保管库名称* 是要启用软删除的密钥保管库的名称：

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. 通过运行 **Get-AzKeyVault** cmdlet 确认为密钥保管库配置软删除。 如果为密钥保管库正确配置软删除，则 _"_ 软删除已启用"属性将返回 **值 True：**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>通过创建或导入密钥将密钥添加到每个密钥保管库

有两种方法可以将密钥添加到 Azure 密钥保管库;可以直接在密钥保管库中创建密钥，也可以导入密钥。 直接在 Key Vault 中创建密钥是不太复杂的方法，而导入密钥可提供对密钥生成方式的总控制。 使用 RSA 密钥。 Azure Key Vault 不支持使用椭圆曲线键环绕和取消环绕。
  
若要直接在密钥保管库中创建密钥，请运行 [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet，如下所示：
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

其中：

- *保管* 库名称是你想要创建密钥的密钥保管库的名称。

- *键* 名称是你想要提供新密钥的名称。

  > [!TIP]
  > 对密钥保管库使用与上述类似的命名约定命名密钥。 这样，在只显示键名称的工具中，字符串是自描述的。
  
如果打算使用 HSM 保护密钥，请确保将 **HSM** 指定为 _Destination_ 参数的值，否则请指定 **Software。**

例如，
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

若要将密钥直接导入密钥保管库，您需要具有 nCipher nShield 硬件安全模块。
  
一些组织倾向于使用此方法来建立其密钥的来源，然后此方法还提供以下证明：
  
- 用于导入的工具集包括 nCipher 的证明，表明用于加密生成的密钥的密钥 Exchange 密钥 (KEK) 不可导出，并且是在 nCipher 制造的真正 HSM 内生成的。

- 工具集包括 nCipher 的证明，表明 Azure 密钥保管库安全世界也在 nCipher 制造的真正 HSM 上生成。 此证明向你证明 Microsoft 也使用正版 nCipher 硬件。

请与安全组核实，确定是否需要上述证明。 有关在本地创建密钥并导入密钥保管库的详细步骤，请参阅如何为 Azure 密钥保管库生成和传输 [受 HSM 保护的密钥](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。 使用 Azure 说明在每个密钥保管库中创建密钥。
  
### <a name="check-the-recovery-level-of-your-keys"></a>检查密钥的恢复级别

Microsoft 365 要求 Azure Key Vault 订阅设置为"不取消"，并且客户密钥使用的密钥已启用软删除。 可以通过查看密钥的恢复级别来确认订阅设置。
  
若要检查密钥的恢复级别，请在 Azure PowerShell 中运行 Get-AzKeyVaultKey cmdlet，如下所示：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

如果恢复级别属性返回除 **"Recoverable+ProtectedSubscription"** 值外的其他值，请确保将订阅置于"不取消"列表中，并且已在每个密钥保管库上启用软删除。
  
### <a name="back-up-azure-key-vault"></a>备份 Azure 密钥保管库

创建或对密钥的任何更改后，立即执行备份并存储备份的副本（联机和脱机）。 脱机副本不应连接到任何网络，例如物理安全或商业存储设备中。 应至少将一个备份副本存储在发生灾难时可访问的位置。 如果密钥保管库密钥被永久销毁或无法操作，备份 blob 是还原密钥材料的唯一方法。 Azure 密钥保管库外部且已导入 Azure 密钥保管库的密钥不符合备份条件，因为客户密钥使用该密钥所需的元数据不存在于外部密钥中。 只有从 Azure 密钥保管库获取的备份可用于使用客户密钥执行还原操作。 因此，必须在上传或创建密钥后创建 Azure Key Vault 备份。
  
若要创建 Azure 密钥保管库密钥的备份，请 [运行 Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet，如下所示：

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

确保输出文件使用后缀 `.backup` 。
  
此 cmdlet 生成的输出文件已加密，不能在 Azure 密钥保管库外部使用。 只能将备份还原到进行备份的 Azure 订阅。
  
> [!TIP]
> 对于输出文件，选择保管库名称和密钥名称的组合。 这样一来，文件名就会自我描述。 它还将确保备份文件名不会发生冲突。
  
例如：
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>验证 Azure 密钥保管库配置设置

在 DEP 中使用密钥之前验证是可选的，但强烈建议这样做。 如果使用除本文所述步骤外的其他步骤设置密钥和保管库，请先验证 Azure 密钥保管库资源的运行状况，然后再配置客户密钥。
  
若要验证你的密钥是否已启用 `get` `wrapKey` 、和 `unwrapKey` 操作：
  
运行 [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

在输出中，查找访问策略和 Exchange Online 标识 (GUID) 或 SharePoint Online 标识 (GUID) 。 以上三种权限都必须显示在"密钥权限"下。
  
如果访问策略配置不正确，请Set-AzKeyVaultAccessPolicy cmdlet，如下所示：
  
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

若要验证未为密钥设置到期日期，请运行 [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

客户密钥不能使用过期密钥。 尝试使用过期密钥的操作将失败，并可能导致服务中断。 强烈建议用于客户密钥的密钥没有过期日期。 一旦设置过期日期，将无法删除，但可更改为其他日期。 如果必须使用设置了过期日期的密钥，将过期值更改为 12/31/9999。 到期日期设置为 12/31/9999 日期的密钥无法通过 Microsoft 365 验证。
  
若要更改已设置为除 12/31/9999 外的任何值的到期日期，请运行 [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 请勿对与客户密钥一同使用的加密密钥设置到期日期。
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>获取每个 Azure 密钥保管库密钥的 URI

设置密钥保管库并添加密钥后，运行以下命令，获取每个密钥保管库中密钥的 URI。 稍后创建和分配每个 DEP 时，将需要使用这些 URI，因此将此信息保存在一个安全的位置。 针对每个密钥保管库运行一次此命令。
  
在 Azure PowerShell 中：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365：设置 Exchange Online 和 Skype for Business 的客户密钥

开始之前，请确保你已完成设置 Azure 密钥保管库所需的任务。 有关 [信息，请参阅 Azure Key Vault 和 Microsoft FastTrack 中的完成任务，了解](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 客户密钥。
  
若要为 Exchange Online 和 Skype for Business 设置客户密钥，请通过远程连接到 Exchange Online 和 Windows PowerShell。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>在 DEP (创建) 策略，以用于 Exchange Online 和 Skype for Business

DEP 与 Azure 密钥保管库中存储的一组密钥相关联。 将 DEP 分配给 Microsoft 365 中的邮箱。 然后，Microsoft 365 将使用策略中标识的密钥来加密邮箱。 若要创建 DEP，您需要之前获取的密钥保管库 URI。 有关[说明，请参阅获取每个 Azure 密钥保管库密钥的 URI。](#obtain-the-uri-for-each-azure-key-vault-key)
  
请记住！ 创建 DEP 时，可以在两个不同的 Azure 密钥保管库中指定两个密钥。 在两个单独的 Azure 区域创建这些密钥，以确保地理位置冗余。
  
若要创建 DEP，请按照以下步骤操作：
  
1. 在本地计算机上，使用在组织中具有全局管理员权限的工作或学校帐户，在一个Windows PowerShell连接到[Exchange Online PowerShell。](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. 若要创建 DEP，请通过New-DataEncryptionPolicy命令使用 New-DataEncryptionPolicy cmdlet。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   其中：

   - *PolicyName* 是你想要用于策略的名称。 名称不能包含空格。 例如，USA_mailboxes。

   - *策略* 说明是策略的用户友好说明，可帮助你记住策略的用用。 可以在说明中包括空格。 例如，"美国及其区域邮箱的根密钥"。

   - *KeyVaultURI1* 是策略中第一个键的 URI。 例如，<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>。

   - *KeyVaultURI2* 是策略中第二个键的 URI。 例如，<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>。 用逗号和空格分隔这两个 URI。

   示例：
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

有关语法和参数的详细信息，请参阅 [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)。

### <a name="assign-a-dep-to-a-mailbox"></a>将 DEP 分配给邮箱

使用 Set-Mailbox cmdlet 将 DEP 分配给邮箱。 分配策略后，Microsoft 365 可以使用 DEP 中标识的密钥对邮箱进行加密。
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中 *MailboxIdParameter* 指定用户邮箱。 有关此 cmdlet Set-Mailbox，请参阅 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。

在混合环境中，可以将 DEP 分配给同步到 Exchange Online 租户中的本地邮箱数据。 若要为此同步的邮箱数据分配 DEP，请使用 Set-MailUser cmdlet。 有关混合环境中邮箱数据详细信息，请参阅使用 Outlook [for iOS](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)和 Outlook for Android 和混合新式验证本地邮箱。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中 *MailUserIdParameter* 指定邮件 (也称为启用邮件的用户) 。 有关此 cmdlet Set-MailUser，请参阅[Set-MailUser。](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)
  
### <a name="validate-mailbox-encryption"></a>验证邮箱加密

加密邮箱可能需要一些时间。 对于首次策略分配，邮箱还必须从一个数据库完全移动到另一个数据库，然后服务才能加密邮箱。 建议您在更改 DEP 或首次向邮箱分配 DEP 后等待 72 小时，然后再尝试验证加密。
  
使用 Get-MailboxStatistics cmdlet 可以确定邮箱是否加密。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果邮箱已加密，则 IsEncrypted 属性返回 **true** 值;如果邮箱未加密，则返回 false 值。 完成邮箱移动的时间取决于第一次为其分配 DEP 的邮箱数以及邮箱的大小。 如果邮箱自分配 DEP 起一周后尚未加密，请与 Microsoft 联系。

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365：设置 SharePoint Online、OneDrive for Business 和 Teams 文件的客户密钥

开始之前，请确保你已完成设置 Azure 密钥保管库所需的任务。 有关 [信息，请参阅 Azure Key Vault 和 Microsoft FastTrack 中的完成任务，了解](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 客户密钥。
  
若要为 SharePoint Online、OneDrive for Business 和 Teams 文件设置客户密钥，请通过远程连接到 SharePoint Online Windows PowerShell。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>为每个 SharePoint Online 和 OneDrive for Business (DEP) 数据加密策略

将 DEP 与 Azure 密钥保管库中存储的一组密钥关联。 将 DEP 应用于一个地理位置（也称为地理位置）的所有数据。 如果使用 Office 365 的多地理位置功能，可以为每个地理位置创建一个 DEP，并能够为每个地理位置使用不同的密钥。 如果不使用多地理位置，可以在组织中创建一个 DEP 以用于 SharePoint Online、OneDrive for Business 和 Teams 文件。 Microsoft 365 使用 DEP 中标识的密钥加密该地理位置的数据。 若要创建 DEP，您需要之前获取的密钥保管库 URI。 有关[说明，请参阅获取每个 Azure 密钥保管库密钥的 URI。](#obtain-the-uri-for-each-azure-key-vault-key)
  
请记住！ 创建 DEP 时，可以在两个不同的 Azure 密钥保管库中指定两个密钥。 在两个单独的 Azure 区域创建这些密钥，以确保地理位置冗余。
  
若要创建 DEP，您需要使用 Windows PowerShell 远程连接到 SharePoint Online。
  
1. 在本地计算机上，使用在组织中具有全局管理员权限的工作或学校帐户[，连接到 SharePoint Online PowerShell。](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps&preserve-view=true)

2. 在 Microsoft SharePoint Online 命令行管理程序 中，Register-SPODataEncryptionPolicy cmdlet，如下所示：

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   示例：
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   注册 DEP 时，对地理位置的数据开始加密。 加密可能需要一些时间。 有关使用此参数的信息，请参阅 [Register-SPODataEncryptionPolicy](https://docs.microsoft.com/powershell/module/sharepoint-online/register-spodataencryptionpolicy?view=sharepoint-ps&preserve-view=true)。

### <a name="validate-file-encryption"></a>验证文件加密

 若要验证 SharePoint Online、OneDrive for Business 和 Teams 文件的加密，请连接到 [SharePoint Online PowerShell，](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)然后使用 Get-SPODataEncryptionPolicy cmdlet 检查租户的状态。 如果 _启用了_ 客户 **密钥加密，** 并且所有站点中的所有文件已加密，则 State 属性将返回已注册的值。 如果加密仍在进行中，此 cmdlet 将返回注册 **的值**。

## <a name="related-articles"></a>相关文章

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [服务加密](office-365-service-encryption.md)
