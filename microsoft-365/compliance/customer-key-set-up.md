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
description: 了解如何为适用于 Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business 和团队文件的 Microsoft 365 设置客户密钥。
ms.openlocfilehash: 94403e1d76fbc6fdf06d784fbb7bb9025dc06fc0
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324208"
---
# <a name="set-up-customer-key"></a>设置客户密钥

使用 "客户密钥"，可以控制组织的加密密钥，然后将 Microsoft 365 配置为使用它们在 Microsoft 数据中心中对静态数据进行加密。 换言之，客户密钥允许客户添加属于其密钥的加密层。 静态数据包含来自 Exchange Online 和 Skype for Business 的数据，这些数据存储在存储在 SharePoint Online 和 OneDrive for business 中的邮箱和文件中。

您必须先安装 Azure，然后才能使用适用于 Office 365 的客户密钥。 本主题介绍了创建和配置所需 Azure 资源时需要遵循的步骤，然后提供在 Office 365 中设置客户密钥的步骤。 完成 Azure 安装后，确定要为组织中的邮箱和文件分配的策略，并因此确定哪些项。 未分配策略的邮箱和文件将使用由 Microsoft 控制和管理的加密策略。 有关客户密钥的详细信息，或有关一般概述的详细信息，请参阅 [Office 365 中的使用客户密钥的服务加密](customer-key-overview.md)。
  
> [!IMPORTANT]
> 强烈建议您遵循本主题中的最佳实践。 这些信息称为 **提示** 和 **重要**。 通过 "客户密钥"，您可以控制其作用域与整个组织一样大的根加密密钥。 这意味着，使用这些密钥进行的错误可能会产生很大影响，并且可能会导致数据中断或无法挽回的数据丢失。
  
## <a name="before-you-set-up-customer-key"></a>设置客户密钥之前

在开始之前，请确保您有适合您的组织的许可。 2006年4月1日，2020，Office 365 中的客户密钥在 Office 365 E5、M365 E5、M365 E5 合规性和 M365 E5 信息保护 & 调控 Sku 中提供。 Office 365 高级合规性 SKU 不再可用于采购新的许可证。 现有 Office 365 高级合规性许可证将继续受支持。

若要了解本主题中的概念和过程，请参阅 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) 文档。 此外，还应熟悉 Azure 中使用的术语（例如， [AZURE AD 租户](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)）。

FastTrack 仅用于收集用于注册客户密钥所需的租户和服务配置信息。 客户密钥提供通过 FastTrack 发布，以便您和我们的合作伙伴可以使用相同的方法提交所需的信息。 FastTrack 还使您可以轻松地将提供的数据存档。
  
如果您需要文档之外的其他支持，请联系 Microsoft 咨询服务 (MCS) 、Premier Field 工程 (PFE) 或 Microsoft 合作伙伴寻求协助。 若要提供有关客户密钥的反馈（包括文档），请将你的想法、建议和观点发送到 customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>设置客户密钥的步骤概述

若要设置客户密钥，请按列出的顺序完成这些任务。 本文的其余部分提供有关每个任务的详细说明，或链接到过程中每个步骤的详细信息。
  
**在 Azure 和 Microsoft FastTrack 中：**
  
你将通过远程连接到 Azure PowerShell 来完成大部分这些任务。 为获得最佳结果，请使用版本4.4.0 或更高版本的 Azure PowerShell。
  
- [创建两个新的 Azure 订阅](#create-two-new-azure-subscriptions)

- [注册 Azure 订阅以使用强制保留期](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  注册可能需要一到五个工作日的时间。

- [提交为激活 Office 365 的客户密钥的请求](#submit-a-request-to-activate-customer-key-for-office-365)

创建了这两个新的 Azure 订阅后，您需要通过完成 Microsoft FastTrack 门户中承载的 web 表单来提交相应的客户密钥提供请求。 **FastTrack 团队不会向客户密钥提供帮助。Office 只是使用 FastTrack 门户来允许您提交表单并帮助我们跟踪客户密钥的相关优惠**。

- [在每个订阅中创建高级 Azure 密钥保管库](#create-a-premium-azure-key-vault-in-each-subscription)

- [将权限分配给每个密钥存储库](#assign-permissions-to-each-key-vault)

- [启用然后确认密钥电子仓库上的软删除](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [通过创建或导入密钥将密钥添加到每个密钥存储库](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [检查密钥的恢复级别](#check-the-recovery-level-of-your-keys)

- [备份 Azure 密钥存储库](#back-up-azure-key-vault)

- [验证 Azure Key Vault 配置设置](#validate-azure-key-vault-configuration-settings)

- [获取每个 Azure Key Vault 密钥的 URI](#obtain-the-uri-for-each-azure-key-vault-key)

**在 Office 365 中：**
  
Exchange Online 和 Skype for Business：
  
- [创建 (DEP) 的数据加密策略，以便与 Exchange Online 和 Skype for business 一起使用](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [将 DEP 分配给邮箱](#assign-a-dep-to-a-mailbox)

- [验证邮箱加密](#validate-mailbox-encryption)

SharePoint Online 和 OneDrive for Business：
  
- [为每个 SharePoint Online 和 OneDrive for business 地域创建 (DEP) 的数据加密策略](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [验证 SharePoint Online、OneDrive for Business 和团队文件的文件加密](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>在 Azure Key Vault 和 Microsoft FastTrack 中完成对客户密钥的任务

在 Azure Key Vault 中完成这些任务。 您需要完成这些步骤，而不管您打算为 Exchange Online 和 Skype for business 或 SharePoint Online、OneDrive for Business 和团队文件设置客户密钥，还是 Office 365 中的所有受支持的服务。
  
### <a name="create-two-new-azure-subscriptions"></a>创建两个新的 Azure 订阅

客户密钥需要两个 Azure 订阅。 作为一种最佳做法，Microsoft 建议您创建新的 Azure 订阅以用于客户密钥。 Azure Key Vault 密钥只能在 Microsoft Azure Active Directory) 租户 (同一 Azure Active Directory 中的应用程序中进行授权。您必须使用将向其分配 DEPs 的组织所使用的相同的 Azure AD 租户创建新订阅。 例如，在您的组织中使用具有全局管理员权限的工作或学校帐户。 有关详细步骤，请参阅 [将 Azure 注册为组织](https://azure.microsoft.com/documentation/articles/sign-up-organization/)。
  
> [!IMPORTANT]
> 客户密钥需要 (DEP) 的每个数据加密策略的两个密钥。 若要实现此目的，必须创建两个 Azure 订阅。 作为一种最佳做法，Microsoft 建议您的组织的各个成员在每个订阅中配置一个密钥。 此外，这些 Azure 订阅应仅用于管理 Office 365 的加密密钥。 这将保护您的组织，以防您在某个操作员意外、有意或恶意删除或以其他方式 mismanages 它们所负责的密钥。 <br/> 我们建议您设置新的 Azure 订阅，这些订阅仅用于管理 Azure Key Vault 资源，以便与客户密钥配合使用。 您可以为您的组织创建的 Azure 订阅数没有实际限制。 按照这些最佳做法，可以最大限度地减少人为错误的影响，同时帮助管理由客户密钥使用的资源。
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>提交为激活 Office 365 的客户密钥的请求

完成 Azure 步骤后，你需要在 [Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)中提交服务请求。 通过 FastTrack web 门户提交请求后，Microsoft 将验证您提供的 Azure 密钥 Vault 配置数据和联系人信息。 您在 "产品" 窗体中所做的有关组织的授权监察官的选择对完成客户密钥注册至关重要且必需。 您在表单中选择的您组织的监察官将用于确保任何请求吊销的真实性，并销毁与客户密钥数据加密策略一起使用的所有密钥。 您需要执行此步骤一次，激活 Exchange Online 和 Skype for business 覆盖的客户密钥，并再次激活适用于 SharePoint Online 和 OneDrive for business 的客户密钥。
  
若要提交用于激活客户密钥的服务，请完成以下步骤：
  
1. 在您的组织中使用具有全局管理员权限的工作或学校帐户，登录到 [Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。

2. 登录后，请浏览到 **仪表板**。

3. 从导航栏中选择 "**部署**"，**或**选择 "在**部署**信息卡上**查看所有部署资源**"，并查看当前提供的列表。

4. 选择适用于你的产品的信息卡片：

   - **Exchange Online 和 Skype For business：****为 Exchange online 提供程序选择 "请求加密密钥帮助**"。

   - **SharePoint Online、OneDrive 和团队文件：** 选择 " **请求加密密钥帮助" 和 "Sharepoint" 和 "OneDrive** 提供"。

5. 查看提供详细信息后，选择 " **继续执行步骤 2**"。

6. 填写 "产品" 窗体上的所有适用详细信息和请求的信息。 特别注意您的组织中要授权的监察官，以批准永久和不可恢复的加密密钥和数据的销毁。 完成表单后，选择 " **提交**"。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>注册 Azure 订阅以使用强制保留期

临时或永久丢失根加密密钥可能会非常中断，甚至会导致服务操作发生故障，并可能导致数据丢失。 出于此原因，使用客户密钥的资源需要加强保护。 与客户密钥结合使用的所有 Azure 资源在默认配置之外提供保护机制。 可以通过阻止即时和不可撤销取消的方式对 Azure 订阅进行标记或注册。 这称为注册强制保留期。 为强制保留期注册 Azure 订阅所需的步骤需要与 Microsoft 365 团队进行协作。 此过程可能需要一至五个工作日。 以前，这有时称为 "不取消"。
  
在联系 Microsoft 365 团队之前，必须为每个用于客户密钥的 Azure 订阅执行以下步骤。 在开始之前，请确保已安装 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 模块。
  
1. 使用 Azure PowerShell 登录。 有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. 运行 AzProviderFeature cmdlet 以注册你的订阅，以使用强制保留期。 对每个订阅执行此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. 请与 Microsoft 联系以完成此过程。 对于 SharePoint 和 OneDrive for Business 团队，请联系 [spock@microsoft.com](mailto:spock@microsoft.com)。 对于 Exchange Online 和 Skype for Business，请联系 [exock@microsoft.com](mailto:exock@microsoft.com)。 在您的电子邮件中包括以下内容：

   **Subject**：客户密钥 \<*Your tenant's fully-qualified domain name*\>

   **正文**：要为其完成强制保留期的订阅 id。
   每个订阅的 AzProviderFeature 的输出。

   完成此过程的服务级别协议 (SLA) 在收到 Microsoft 通知 (和确认之后) 注册了订阅才能使用强制保留期。

4. 收到 Microsoft 注册已完成的通知后，通过运行 AzProviderFeature 命令来验证注册的状态，如下所示。 如果经过验证，AzProviderFeature 命令将返回注册**状态**属性的**注册**值。 对每个订阅执行此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. 若要完成此过程，请运行 AzResourceProvider 命令。 对每个订阅执行此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每个订阅中创建高级 Azure 密钥保管库

创建密钥存储库的步骤在 [开始使用 Azure Key vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)时进行了介绍，此步骤将指导您完成安装和启动 azure PowerShell，连接到 azure 订阅，创建资源组，以及在该资源组中创建密钥存储库。
  
创建密钥存储库时，必须选择 SKU：标准版或高级存储库。 标准 SKU 允许 Azure Key Vault 密钥受软件保护-没有硬件安全模块 (HSM) 密钥保护-并且 Premium SKU 允许使用 Hsm 来保护关键保管库密钥。 客户密钥接受使用任何 SKU 的密钥电子仓库，尽管 Microsoft 强烈建议您仅使用高级 SKU。 无论是哪种类型的键的运算开销都是一样的，因此，每个受 HSM 保护的密钥的成本的唯一区别是每个月的成本。 有关详细信息，请参阅 [主要保管库定价](https://azure.microsoft.com/pricing/details/key-vault/) 。
  
> [!IMPORTANT]
> 对生产数据使用 Premium SKU 密钥电子仓库和受 HSM 保护的密钥，并且仅使用标准 SKU 密钥电子仓库和密钥进行测试和验证。
  
对于每个将使用客户密钥的 Microsoft 365 服务，在您创建的两个 Azure 订阅中创建一个密钥存储库。 例如，仅针对 Exchange Online 和 Skype for business 或 SharePoint Online 和 OneDrive for Business，你将仅创建一对电子仓库。 若要同时为 Exchange Online 和 SharePoint Online 启用客户密钥，您将创建两对主要电子仓库。
  
对密钥库使用命名约定，以反映将与保管库关联的数据加密策略的预期用途。 请参阅下面的 "最佳实践" 部分，了解命名约定建议。
  
为每个数据加密策略创建一组单独的、成对的电子仓库。 对于 Exchange Online，当您将策略分配给邮箱时，会选择数据加密策略的范围。 一个邮箱只能分配一个策略，并且最多可以创建50个策略。 对于 SharePoint Online，策略的范围是组织内的所有数据（地理 _位置或地理_位置）。

创建密钥存储库还需要创建 Azure 资源组，因为关键电子仓库需要存储容量 (尽管非常小的) 和密钥存储日志记录（如果启用）也会生成存储的数据。 作为一种最佳做法，Microsoft 建议使用单独的管理员来管理每个资源组，并将管理与将管理所有相关客户密钥资源的一组管理员相一致。
  
> [!IMPORTANT]
> 若要最大限度地提高可用性，你的密钥电子仓库应位于 Microsoft 365 服务附近的区域。 例如，如果您的 Exchange Online 组织在北美，请将您的密钥电子仓库放在北美。 如果你的 Exchange Online 组织在欧洲，请将你的密钥电子仓库放在欧洲。<br/>对密钥存储库使用公用前缀，并包含主要保管库和密钥的使用和作用域的缩写， (例如，对于将在北美使用电子仓库的 Contoso SharePoint 服务，可能的名称对是 Contoso-O365SP-VaultA1 和 Contoso-O365SP-VaultA2。 保管库名称在 Azure 中是全局唯一的字符串，因此，如果所需名称已由其他 Azure 客户声明，则可能需要尝试其他名称的变体。 从7月2017电子仓库名称无法更改，因此最佳做法是为设置编写计划，并使用第二个人验证是否正确执行了计划。<br/>如果可能，请在非配对区域中创建您的电子仓库。 配对的 Azure 区域在服务故障域之间提供高可用性。 因此，可以将区域对视为彼此的备份区域。 这意味着，放置在一个区域中的 Azure 资源将自动获得配对区域的容错能力。 出于此原因，在区域为成对的数据加密策略中使用的两个存储库的区域选择区域意味着仅有两个可用性区域处于使用状态。 大多数地理位置仅有两个区域，因此尚不能选择非配对区域。 如果可能，请为用于数据加密策略的两个电子仓库选择两个非配对区域。 这从总共四个可用区域获益。 有关详细信息，请参阅 [业务连续性和灾难恢复 (BCDR) ：](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 当前区域对列表的 Azure 配对区域。
  
### <a name="assign-permissions-to-each-key-vault"></a>将权限分配给每个密钥存储库

对于每个密钥存储库，您将需要为客户密钥定义三组不同的权限，具体取决于您的实现。 例如，您需要为以下各项定义一组权限：
  
- 将对您的组织执行关键电子仓库的日常管理的**主要保管库管理员**。 这些任务包括备份、创建、获取、导入、列出和还原。

  > [!IMPORTANT]
  > 分配给主要保管库管理员的权限集不包含删除密钥的权限。 这是有意和重要的做法。 通常情况下，删除加密密钥不会完成，因为这样做会永久破坏数据。 作为一种最佳做法，默认情况下不要向主要保管库管理员授予此权限。 相反，请为重要的保管库参与者预留此权限，并在清楚了解结果的情况下，仅在短期内将其分配给管理员。
  
  若要将这些权限分配给组织中的用户，请使用 Azure PowerShell 登录 Azure 订阅。 有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

- 运行 AzKeyVaultAccessPolicy cmdlet 以分配所需的权限。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   例如：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- 可以更改 Azure 密钥存储库本身权限的**主要保管库参与者**。 您需要更改这些权限，因为员工离开或加入团队，或者在极少数情况下，主要保管库管理员合法需要删除或还原密钥的权限。 需要在密钥保管库中向此组密钥 vault 参与者授予 **参与者** 角色。 您可以使用 Azure 资源管理器分配此角色。 有关详细步骤，请参阅 [使用基于角色的访问控制管理对 Azure 订阅资源的访问权限](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。 创建订阅的管理员将隐式拥有此访问权限，以及将其他管理员分配给参与者角色的能力。

- 如果打算将客户密钥用于 Exchange Online 和 Skype for business，则需要向 Microsoft 365 授予对代表 Exchange Online 和 Skype for business 使用密钥保管库的权限。 同样，如果您打算将客户密钥与 SharePoint Online 和 OneDrive for business 结合使用，则需要添加 Microsoft 365 的权限，以代表 SharePoint Online 和 OneDrive for business 使用密钥存储库。 若要向 Microsoft 365 授予权限，请使用以下语法运行 **AzKeyVaultAccessPolicy** cmdlet： 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   其中：

    - *保管库名称* 是您创建的密钥存储库的名称。

    - 对于 Exchange Online 和 Skype for Business，请将  *Office 365 appID* 替换为 `00000002-0000-0ff1-ce00-000000000000`

    - 对于 SharePoint Online、OneDrive for Business 和团队文件，请将  *Office 365 appID* 替换为 `00000003-0000-0ff1-ce00-000000000000`

  示例：设置 Exchange Online 和 Skype for business 的权限：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  示例：设置 SharePoint Online、OneDrive for Business 和团队文件的权限：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>启用然后确认密钥电子仓库上的软删除

如果可以快速恢复密钥，则由于意外或恶意删除的密钥而遇到的扩展服务故障的可能性较小。 您需要先启用此配置（称为 "软删除"），然后才能在 "客户密钥" 中使用密钥。 启用软删除允许您在删除90天内恢复密钥或电子仓库，而无需从备份中还原它们。
  
若要在密钥保管库上启用软删除，请完成以下步骤：
  
1. 使用 Windows Powershell 登录到你的 Azure 订阅。 有关说明，请参阅 [使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. 运行 [AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet。 在此示例中， *保管库名称* 是要为其启用软删除的密钥保管库的名称：

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. 通过运行 **AzKeyVault** cmdlet，确认已为密钥存储库配置了软删除。 如果为密钥存储库正确配置了软删除，则 " _已启用软删除_ " 属性将返回值 **True**：

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>通过创建或导入密钥将密钥添加到每个密钥存储库

有两种方法可以将密钥添加到 Azure Key Vault;可以直接在密钥保管库中创建密钥，也可以导入密钥。 直接在 "密钥存储库" 中创建密钥是不太复杂的方法，而导入密钥提供了对如何生成密钥的总体控制。
  
若要直接在密钥保管库中创建密钥，请运行 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet，如下所示：
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

其中：

- *保管库名称* 是要在其中创建密钥的密钥保管库的名称。

- *键名称* 是要赋予新键的名称。

  > [!TIP]
  > 使用上面的密钥库的命名约定命名键。 这样一来，在仅显示密钥名称的工具中，字符串是自我描述的。
  
- 如果打算使用 HSM 保护密钥，请确保将 **HSM** 指定为 _Destination_ 参数的值，否则指定 " **软件**"。

例如，
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

若要将密钥直接导入到密钥存储库中，您需要具有 nCipher nShield 硬件安全模块。
  
某些组织首选使用此方法来建立其密钥的 provenance，然后此方法还提供以下内容：
  
- 用于导入的工具集包括 nCipher 中的认证密钥 () KEK 的密钥交换密钥不能导出，并在 nCipher 制造的正版 HSM 中生成。

- 该工具集包括来自 nCipher 的证明，这些安全世界也是在由 nCipher 生产的正版 HSM 上生成的。 此认证向你证明 Microsoft 也在使用正版 nCipher 硬件。

检查安全组以确定是否需要上述 attestations。 有关在本地创建密钥并将其导入到密钥保管库的详细步骤，请参阅 how [to 为 Azure Key vault 生成和传输受 HSM 保护的密钥](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。 使用 Azure 说明在每个密钥存储库中创建密钥。
  
### <a name="check-the-recovery-level-of-your-keys"></a>检查密钥的恢复级别

Microsoft 365 要求将 Azure Key Vault 订阅设置为 "不取消"，并且客户密钥使用的密钥启用了 "软删除"。 你可以通过查看密钥上的恢复级别来确认这一点。
  
若要检查注册表项的恢复级别，请在 Azure PowerShell 中运行 AzKeyVaultKey cmdlet，如下所示：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

如果 _恢复级别_ 属性返回的值不是 **可恢复 + ProtectedSubscription**的值，则需要查看本主题，并确保已按照所有步骤将订阅放在 "不要取消" 列表中，并且已在每个密钥保管库上启用软删除。
  
### <a name="back-up-azure-key-vault"></a>备份 Azure 密钥存储库

立即完成创建或对某个键的任何更改，执行备份并存储联机和脱机的备份副本。 脱机副本不应连接到任何网络，例如在物理安全或商业存储设施中。 至少应将备份的一个副本存储在灾难发生时可访问的位置。 备份 blob 是恢复密钥材料的唯一方法（应永久销毁密钥保管库密钥），或以其他方式呈现为不可操作。 Azure Key Vault 外部的密钥和已导入到 Azure Key Vault 的密钥不能作为备份，因为客户密钥使用密钥所需的元数据在外部密钥中不存在。 只有从 Azure 密钥存储库中获取的备份才能用于使用客户密钥的还原操作。 因此，在上载或创建密钥时，应创建 Azure 密钥存储库的备份，这一点非常重要。
  
若要创建 Azure Key Vault 密钥的备份，请运行 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet，如下所示：

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

确保输出文件使用后缀 `.backup` 。
  
此 cmdlet 生成的输出文件已加密，不能在 Azure 密钥保管库外部使用。 只能将备份还原到从中获取备份的 Azure 订阅。
  
> [!TIP]
> 对于输出文件，选择您的电子仓库名称和密钥名称的组合。 这将使文件名自我描述。 它还将确保备份文件名称不会发生冲突。
  
例如：
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>验证 Azure Key Vault 配置设置

在 DEP 中使用密钥之前执行验证是可选的，但强烈建议这样做。 特别是，如果您使用步骤设置了除本主题中所述的密钥和电子仓库之外的密钥和电子仓库，则应在配置客户密钥之前验证 Azure Key Vault 资源的运行状况。
  
若要验证您的密钥是否启用了 get、wrapKey 和 unwrapKey 操作，请执行以下操作：
  
运行 [AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

在 "输出" 中，查找访问策略和 Exchange Online 标识 (GUID) 或 SharePoint Online 标识 (GUID) 相应的 GUID。 所有三个权限都必须显示在 "键的权限" 下。
  
如果访问策略配置不正确，请运行 AzKeyVaultAccessPolicy cmdlet，如下所示：
  
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

若要验证没有为你的密钥设置到期日期，请运行 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

已过期的密钥不能由客户密钥使用，尝试使用过期密钥的操作将会失败，并且可能会导致服务中断。 强烈建议使用与客户密钥一起使用的密钥不具有过期日期。 过期日期一旦设置，便无法删除，但可以更改为不同的日期。 如果必须使用具有过期日期设置的密钥，请将 "过期" 值更改为 "12/31/9999"。 过期日期设置为12/31/9999 以外的密钥将不会通过 Microsoft 365 验证。
  
若要更改已设置为12/31/9999 以外的任何其他值的过期日期，请运行 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 不要在与客户密钥结合使用的加密密钥上设置到期日期。
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>获取每个 Azure Key Vault 密钥的 URI

完成 Azure 中的所有步骤以设置密钥存储库并添加密钥后，运行以下命令以获取每个密钥存储库中的密钥的 URI。 在稍后创建和分配每个 DEP 时，需要使用这些 Uri，将此信息保存在安全的位置。 请务必为每个密钥保管库运行一次此命令。
  
在 Azure PowerShell 中：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365：设置 Exchange Online 和 Skype for business 的客户密钥

在开始之前，请确保您已完成设置 Azure Key Vault 所需的任务。 有关信息，请参阅 [Azure Key Vault 和 Microsoft FastTrack 中的 "完成任务" 以获取客户密钥](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 。
  
若要设置 Exchange Online 和 Skype for business 的客户密钥，你将需要通过 Windows PowerShell 远程连接到 Exchange Online 来执行这些步骤。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>创建 (DEP) 的数据加密策略，以便与 Exchange Online 和 Skype for business 一起使用

一个 DEP 与 Azure Key Vault 中存储的一组密钥相关联。 您在 Microsoft 365 中向邮箱分配了一个 DEP。 然后，Microsoft 365 将使用在策略中标识的密钥来加密邮箱。 若要创建 DEP，您需要之前获取的主要保管库 Uri。 有关说明，请参阅 [获取每个 Azure Key Vault 密钥的 URI](#obtain-the-uri-for-each-azure-key-vault-key) 。
  
还! 创建 DEP 时，请指定驻留在两个不同的 Azure Key 保管库中的两个密钥。 确保这些项位于两个单独的 Azure 区域中，以确保地域冗余。
  
若要创建 DEP，请按照以下步骤操作：
  
1. 在您的本地计算机上，在您的组织中使用具有全局管理员权限的工作或学校帐户，在 Windows PowerShell 窗口中 [连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。

2. 若要创建 DEP，请通过键入以下命令来使用 DataEncryptionPolicy cmdlet。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   其中：

   - *PolicyName* 是要用于策略的名称。 名称不能包含空格。 例如，USA_mailboxes。

   - *策略说明* 是一种用户友好的策略说明，可帮助您记住该策略的用途。 您可以在说明中包含空格。 例如，"适用于美国的邮箱的根键及其区域"。

   - *KeyVaultURI1* 是策略中的第一个项的 URI。 例如，<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>。

   - *KeyVaultURI2* 是策略中的第二个项的 URI。 例如，<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>。 用逗号和空格分隔两个 Uri。

   示例：
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

有关语法和参数的详细信息，请参阅 [DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)。

### <a name="assign-a-dep-to-a-mailbox"></a>将 DEP 分配给邮箱

使用 "设置邮箱" cmdlet 将 DEP 分配给邮箱。 一旦分配了策略，Microsoft 365 就可以使用 DEP 中指定的密钥对邮箱进行加密。
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中 *MailboxIdParameter* 指定邮箱。 有关设置邮箱 cmdlet 的详细信息，请参阅 [set-邮箱](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。

对于 [使用具有混合新式身份验证的 Outlook For iOS 和 Outlook For Android 的本地邮箱](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)，同步到 Exchange Online 租户的本地邮箱数据可以使用 MailUser CMDLET 分配 DEP。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中， *MailUserIdParameter* 指定邮件用户 (也称为已启用邮件的用户) 。 有关 MailUser cmdlet 的详细信息，请参阅 [MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)。
  
### <a name="validate-mailbox-encryption"></a>验证邮箱加密

对邮箱加密可能需要一段时间。 首次分配策略时，该邮箱还必须完全从一个数据库移动到另一个数据库，然后服务才能对邮箱加密。 建议您在更改 DEP 或首次将 DEP 分配到邮箱之后，先等待72小时，再尝试验证加密。
  
使用 Get-mailboxstatistics cmdlet 可以确定邮箱是否已加密。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果邮箱已加密，则 IsEncrypted 属性返回 **true** ，如果邮箱未加密，则返回 **false** 值。

完成邮箱移动的时间取决于第一次为其分配 DEP 的邮箱数以及邮箱的大小。 如果邮箱在您分配 DEP 的时间之后没有加密过，请与 Microsoft 联系。

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365：为 SharePoint Online、OneDrive for Business 和团队文件设置客户密钥

在开始之前，请确保您已完成设置 Azure Key Vault 所需的任务。 有关信息，请参阅 [Azure Key Vault 和 Microsoft FastTrack 中的 "完成任务" 以获取客户密钥](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 。
  
若要为 SharePoint Online、OneDrive for Business 和团队文件设置客户密钥，您将需要通过使用 Windows PowerShell 远程连接到 SharePoint Online 来执行这些步骤。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>为每个 SharePoint Online 和 OneDrive for business 地域创建 (DEP) 的数据加密策略

将 DEP 与 Azure Key Vault 中存储的一组密钥相关联。 您将 DEP 应用于一个地理位置（也称为地理位置）中的所有数据。 如果使用 Office 365 的多地理位置功能，可以为每个地理位置创建一个 DEP，以便每个地区使用不同的密钥。 如果不使用多地理位置，则可以在组织中创建一个 DEP，以便与 SharePoint Online、OneDrive for Business 和团队文件一起使用。 Microsoft 365 使用在 DEP 中标识的密钥来加密该地理位置中的数据。 若要创建 DEP，您需要之前获取的主要保管库 Uri。 有关说明，请参阅 [获取每个 Azure Key Vault 密钥的 URI](#obtain-the-uri-for-each-azure-key-vault-key) 。
  
还! 创建 DEP 时，请指定驻留在两个不同的 Azure Key 保管库中的两个密钥。 确保这些项位于两个单独的 Azure 区域中，以确保地域冗余。
  
若要创建 DEP，您需要使用 Windows PowerShell 远程连接到 SharePoint Online。
  
1. 在您的本地计算机上，在您的组织中使用具有全局管理员权限的工作或学校帐户， [连接到 SharePoint Online Powershell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

2. 在 Microsoft SharePoint Online 命令行管理程序中，运行 SPODataEncryptionPolicy cmdlet，如下所示：

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   注册 DEP 时，会开始对 geo 中的数据进行加密。 这可能需要一些时间。

### <a name="validate-file-encryption"></a>验证文件加密

 若要验证 SharePoint Online、OneDrive for Business 和团队文件的加密，请 [连接到 Sharepoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)，然后使用 SPODataEncryptionPolicy cmdlet 检查租户的状态。 如果启用了客户密钥加密且所有站点中的所有文件均已加密，则 _State_ 属性将返回一个 **注册** 值。 如果仍在进行加密，则此 cmdlet 提供有关已完成的网站百分比的信息。

## <a name="related-articles"></a>相关文章

- [使用客户密钥进行服务加密](customer-key-overview.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [服务加密](office-365-service-encryption.md)
