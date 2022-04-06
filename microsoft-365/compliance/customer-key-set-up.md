---
title: 设置客户密钥
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
description: 了解如何为用户设置客户密钥Microsoft 365。
ms.openlocfilehash: f3d7da27e0c9a5e27f0c3e7bcc3adb48dad5d42c
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634506"
---
# <a name="set-up-customer-key"></a>设置客户密钥

使用客户密钥，可以控制组织的加密密钥，然后将Microsoft 365配置为使用这些密钥加密 Microsoft 数据中心中的静态数据。 换句话说，客户密钥允许客户使用其密钥添加属于他们的加密层。

设置 Azure，然后你才能使用客户密钥进行Office 365。 本文介绍创建和配置所需 Azure 资源所需的步骤，然后提供在 Office 365 中设置客户密钥的步骤。 设置 Azure 后，可确定要分配哪个策略（以及哪些密钥）来加密组织中各种Microsoft 365数据。 有关客户密钥或一般概述的信息，请参阅使用客户密钥在[Office 365。](customer-key-overview.md)
  
> [!IMPORTANT]
> 我们强烈建议您遵循本文中的最佳实践。 这些被称为"提示 **"和"****重要"**。 客户密钥可让你控制其作用域可以与整个组织一样大的根加密密钥。 这意味着，使用这些密钥所导致错误可能会产生广泛影响，并可能导致服务中断或数据的不可撤消丢失。
  
## <a name="before-you-set-up-customer-key"></a>设置客户密钥之前

在开始使用之前，请确保你拥有适合你的组织的 Azure 订阅和许可。 使用付费 Azure 订阅，企业协议云服务提供商。 不接受基于信用卡的付款。 批准并设置帐户开票需求。 你通过免费、试用、支持、MSDN 订阅和旧版支持下获取的订阅不符合资格。

Office 365 E5、Microsoft 365 E5、Microsoft 365 E5 合规 和 Microsoft 365 E5 信息保护 & SK 提供客户密钥。 Office 365 高级合规版 SKU 不再可用于购买新许可证。 现有Office 365 高级合规版许可证将继续受支持。

若要了解本文中的概念和过程，请查看 [Azure](/azure/key-vault/) 密钥保管库文档。 此外，请熟悉 Azure 中使用的术语，例如，Azure AD[租户](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)。
  
如果您需要文档之外更多的支持，请联系 Microsoft 咨询服务 (MCS) 、顶级现场工程 (PFE) 或 Microsoft 合作伙伴寻求帮助。 若要提供有关客户密钥（包括文档）的反馈，请将你的想法、建议和观点 customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>设置客户密钥的步骤概述

若要设置客户密钥，请按列出的顺序完成这些任务。 本文的其余部分提供了每个任务的详细说明，或链接到过程中每个步骤的详细信息。
  
**在 Azure 和 Microsoft FastTrack：**
  
通过远程连接到远程连接，可以完成大部分Azure PowerShell。 为了获得最佳结果，请使用版本 4.4.0 或更高版本的 Azure PowerShell。
  
- [创建两个新的 Azure 订阅](#create-two-new-azure-subscriptions)

- [提交请求以激活客户密钥Office 365](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [注册 Azure 订阅以使用强制保留期](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  此注册过程需要 5 个工作日才能完成。

- [在每个订阅密钥保管库高级 Azure 服务](#create-a-premium-azure-key-vault-in-each-subscription)

- [为每个密钥保管库分配权限](#assign-permissions-to-each-key-vault)

- [确保在密钥保管库上启用软删除](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [通过创建或导入密钥将密钥添加到每个密钥保管库](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [检查密钥的恢复级别](#check-the-recovery-level-of-your-keys)

- [备份 Azure 密钥保管库](#back-up-azure-key-vault)

- [验证 Azure 密钥保管库配置设置](#validate-azure-key-vault-configuration-settings)

- [获取每个 Azure 帐户密钥密钥保管库 URI](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>在 Azure 密钥保管库 中完成任务Microsoft FastTrack客户密钥

在 Azure 密钥保管库 中密钥保管库。 你需要为使用客户密钥的所有 DEP 完成这些步骤。
  
### <a name="create-two-new-azure-subscriptions"></a>创建两个新的 Azure 订阅

客户密钥需要两个 Azure 订阅。 作为最佳做法，Microsoft 建议创建用于客户密钥的新 Azure 订阅。 Azure 密钥保管库 密钥只能针对同一 Azure Active Directory (Microsoft Azure Active Directory) 租户中的应用程序授权，你必须使用分配 DEP 的组织所使用的同一 Azure AD 租户创建新订阅。 例如，使用在组织中具有全局管理员权限的工作或学校帐户。 有关详细步骤，请参阅 [注册 Azure 作为组织](/azure/active-directory/fundamentals/sign-up-organization)。
  
> [!IMPORTANT]
> 客户密钥要求 DEP 策略中每个数据加密策略 (两) 。 为此，必须创建两个 Azure 订阅。 最佳做法是，Microsoft 建议你组织单独的成员在每个订阅中配置一个密钥。 你应仅使用这些 Azure 订阅来管理 Office 365。 这可保护你的组织，以防其中一个运营者意外、有意或恶意删除或以其他方式管理他们负责的密钥。

对于你可以为组织创建的 Azure 订阅数没有实际限制。 遵循这些最佳做法将最大限度地减少人为错误的影响，同时有助于管理客户密钥使用的资源。
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>提交请求以激活客户密钥Office 365

创建两个新的 Azure 订阅后，你需要在客户门户中提交相应的客户密钥[Microsoft FastTrack请求](https://fasttrack.microsoft.com/)。 在产品/服务表单中就组织中授权指定进行的选择对于完成客户密钥注册至关重要且必要。 贵组织中那些选定角色中的官员确保撤消和销毁用于客户密钥数据加密策略的所有密钥的请求的真实性。 对于要用于组织的每个客户密钥 DEP 类型，需要执行一次此步骤。

**FastTrack团队不提供有关客户密钥的帮助。Office 365只需使用 FastTrack 门户来提交表单，并帮助我们跟踪客户密钥的相关产品/服务。提交客户加入FastTrack后，联系相应的客户密钥载入团队以开始载入过程。**
  
若要提交产品/服务以激活客户密钥，请完成以下步骤：
  
1. 使用在组织中具有全局管理员权限的工作或学校帐户，登录到Microsoft FastTrack[门户](https://fasttrack.microsoft.com/)。

2. 登录后，选择相应的域。

3. 对于所选域 **，从顶部** 导航栏中选择"请求服务"，然后查看可用产品/服务的列表。

4. 选择适用于你的产品/服务的信息卡：

   - **多个Microsoft 365工作负载：** 选择请求 **加密密钥帮助，以Microsoft 365** 服务。

   - **Exchange Online和Skype for Business：** 选择请求 **加密密钥帮助，Exchange** 服务。

   - **SharePoint Online、OneDrive 和 Teams 文件**：选择请求加密密钥帮助 **，SharePoint和** OneDrive for Business服务。

5. 查看产品/服务详细信息后，选择" **继续"以执行步骤 2**。

6. 在产品/服务表单上填写所有适用的详细信息和请求的信息。 请特别注意要授权贵组织的哪个官员批准对加密密钥和数据进行永久且不可恢复的销毁的选择。 完成表单后，选择"提交 **"**。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>注册 Azure 订阅以使用强制保留期

根加密密钥的临时或永久丢失可能会导致服务操作中断甚至出现灾难性问题，并可能导致数据丢失。 因此，用于客户密钥的资源需要强大的保护。 与客户密钥一起使用的所有 Azure 资源都提供默认配置以外的保护机制。 你可以为 Azure 订阅标记或注册强制 *保留期*。 强制保留期可阻止立即和不可撤销地取消 Azure 订阅。 若要将 Azure 订阅注册为强制保留期所需的步骤，需要与团队Microsoft 365协作。 此过程需要 5 个工作日才能完成。 以前，强制保留期有时称为"不取消"。
  
在联系 Microsoft 365团队之前，你必须对使用客户密钥的每个 Azure 订阅执行以下步骤。 在启动之前，[Azure PowerShell安装 Az](/powershell/azure/new-azureps-module-az) 模块。
  
1. 使用 Azure PowerShell 登录。 有关说明，请参阅[使用 Azure PowerShell](/powershell/azure/authenticate-azureps)。

2. 运行 Register-AzProviderFeature cmdlet 注册订阅以使用强制保留期。 针对每个订阅完成此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. 请与 Microsoft 联系以完成此过程。

   - 若要启用客户密钥以将 DEP 分配给各个Exchange Online，请联系 [exock@microsoft.com](mailto:exock@microsoft.com)。

   - 若要启用客户密钥以分配 DEP 以加密 SharePoint Online 和 OneDrive for Business 内容 (包括Teams文件) 租户用户，请联系 [spock@microsoft.com。](mailto:spock@microsoft.com)

   - 若要启用客户密钥以分配 DESP 以加密所有租户 (Exchange Online、Teams、Microsoft 信息保护) 的多个 Microsoft 365 工作负载中的内容，请联系 [m365-ck@service.microsoft.com。](mailto:m365-ck@service.microsoft.com)

   - 在电子邮件中包括以下信息：

     **主题**：客户密钥 \<*Your tenant's fully qualified domain name*\>

     **正文**：包括要完成其强制保留期的订阅 ID 以及每个订阅Get-AzProviderFeature输出。

     一旦通知 Microsoft (并验证) 你已注册订阅以使用强制保留期，则服务级别协议 (SLA) 完成此过程需要 5 个工作日。

4. 从 Microsoft 收到注册完成通知后，通过运行 Get-AzProviderFeature命令验证注册状态，如下所示。 如果已验证，Get-AzProviderFeature返回 Registration **State** 属性的值 **Registered**。 针对每个订阅完成此步骤。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. 若要完成此过程，请运行 Register-AzResourceProvider 命令。 针对每个订阅完成此步骤。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每个订阅密钥保管库高级 Azure 服务

[Azure 密钥保管库 的 入门](/azure/key-vault/general/overview) 中记录了创建密钥保管库的步骤，这些步骤将指导你安装和启动 Azure PowerShell、连接到 Azure 订阅、创建资源组，以及创建该资源组中的关键保管库。
  
创建密钥保管库时，必须选择 SKU：Standard 或 高级版。 标准 SKU 允许 Azure 密钥保管库 密钥受软件保护（没有硬件安全模块 (HSM) 密钥保护）并且 高级版 SKU 允许使用 HSM 来保护 密钥保管库 密钥。 客户密钥接受使用任一 SKU 的密钥保管库，但 Microsoft 强烈建议你仅将密钥高级版 SKU。 使用任一类型的密钥的操作成本相同，因此成本的唯一差别是每个受 HSM 保护的密钥的每月成本。 有关详细信息[密钥保管库定价](https://azure.microsoft.com/pricing/details/key-vault/)。
  
> [!IMPORTANT]
> 将 高级版 SKU 密钥保管库和 HSM 保护的密钥用于生产数据，并且仅将标准 SKU 密钥保管库和密钥用于测试和验证目的。
  
对于Microsoft 365使用客户密钥的每个服务，在创建的两个 Azure 订阅中分别创建一个密钥保管库。 例如，若要使客户密钥能够将 DESP 用于 Exchange Online、SharePoint Online 和多工作负载方案，需要创建三对密钥保管库。
  
对密钥保管库使用命名约定，反映您将与保管库关联的 DEP 的预定用途。 有关命名约定建议，请参阅下面的最佳做法部分。
  
为每个数据加密策略创建一组单独的配对保管库。 例如Exchange Online，在将策略分配给邮箱时，将选择数据加密策略的范围。 邮箱只能分配一个策略，并且可以创建最多 50 个策略。 SharePoint Online 策略的范围包括组织中地理位置或地理位置内 _的所有数据_。 多工作负荷策略的范围包括所有用户支持的工作负荷的所有数据。

创建密钥保管库还需要创建 Azure 资源组，因为密钥保管库需要存储容量 (但较小的) 和 密钥保管库 日志记录（如果启用）也会生成存储的数据。 作为最佳实践，Microsoft 建议使用单独的管理员来管理每个资源组，其管理与将管理所有相关客户密钥资源的一组管理员保持一致。
  
> [!IMPORTANT]
> 若要最大化可用性，将密钥保管库放在 Microsoft 365 服务附近区域。例如，如果您的 Exchange Online 组织位于 北美 中，将密钥保管库放在 北美。 如果Exchange Online位于欧洲，请在欧洲放置密钥保管库。
>
> 对密钥保管库使用通用前缀，并包括密钥保管库和密钥 (的使用和范围的缩写，例如，对于保管库将位于 北美 中的 Contoso SharePoint 服务，可能的名称对是 Contoso-CK-SP-NA-VaultA1 和 Contoso-CK-SP-NA-VaultA2。 保管库名称是 Azure 中的全局唯一字符串，因此你可能需要尝试所需名称的变体，以防其他 Azure 客户已声明所需的名称。 自 2017 年 7 日起，无法更改保管库名称，因此最佳做法是制定一份书面设置计划，并使用第二个人验证计划是否正确执行。
>
> 如果可能，在非配对区域创建保管库。 成对的 Azure 区域跨服务失败域提供高可用性。 因此，可以将区域对视为彼此的备份区域。 这意味着，放置在一个地区的 Azure 资源通过配对区域自动获得容错能力。 出于此原因，选择数据加密策略（其中两个区域已配对）中使用的两个保管库的区域意味着总共只有两个可用性区域在使用。 大多数地理位置只有两个区域，因此尚无法选择非配对区域。 如果可能，请为与数据加密策略一同使用的两个保管库选择两个非配对区域。 这从共四个可用性区域中获益。 有关详细信息，请参阅 BCDR (业务连续性和灾难恢复 [) ：Azure 配对](/azure/best-practices-availability-paired-regions) 区域，了解区域对的当前列表。
  
### <a name="assign-permissions-to-each-key-vault"></a>为每个密钥保管库分配权限

你将需要为每个密钥保管库定义三组单独的权限，具体取决于你的实现。 例如，您需要为以下各项定义一组权限：
  
- **对组织执行** 密钥保管库日常管理的关键保管库管理员。 这些任务包括备份、创建、获取、导入、列表和还原。

  > [!IMPORTANT]
  > 分配给密钥保管库管理员的权限集不包括删除密钥的权限。 这是有意为之，也是一项重要的做法。 通常不删除加密密钥，因为这样做会永久破坏数据。 作为最佳实践，默认情况下不要向密钥保管库管理员授予此权限。 相反，请为密钥保管库参与者保留此策略，并且仅在明确了解后果后将其短期分配给管理员。
  
  若要向贵组织的用户分配这些权限，请通过 Azure PowerShell 登录 Azure 订阅。 有关说明，请参阅[使用 Azure PowerShell](/powershell/azure/authenticate-azureps)。

- 运行 Set-AzKeyVaultAccessPolicy cmdlet 以分配必要的权限。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   例如：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **可更改 Azure** 帐户本身对 Azure 密钥保管库参与者。 当员工离开或加入团队时，你需要更改这些权限。 在密钥保管库管理员合法需要删除或还原密钥的极少数情况下，您还需要更改权限。 需要向这组密钥保管库参与者授予密钥保管 **库上的参与者** 角色。 可以使用 Azure 角色分配此资源管理器。 有关详细步骤，请参阅[使用 Role-Based 访问控制 管理对 Azure 订阅资源的访问权限](/azure/active-directory/role-based-access-control-configure)。 创建订阅的管理员具有隐式访问权限，并且能够将其他管理员分配到参与者角色。

- **您Microsoft 365** 客户密钥使用每个密钥保管库的应用程序的权限，您需要授予 wrapKey、unwrapKey 和获取对相应 Microsoft 365 服务主体的权限。 

  若要向服务主体Microsoft 365权限，请运行 **Set-AzKeyVaultAccessPolicy** cmdlet，使用下列语法：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   其中：

   - *保管库* 名称是创建的密钥保管库的名称。
   - 对于 Exchange Online 和 Skype for Business，Office 365 *appID* 替换为`00000002-0000-0ff1-ce00-000000000000`
   - 对于 SharePoint Online、OneDrive for Business 和 Teams 文件，请将 *Office 365 appID* 替换为`00000003-0000-0ff1-ce00-000000000000`
   - 对于适用于所有租户 (Exchange、Teams、Microsoft 信息保护) 的多工作负荷策略，请将 Office 365 *appID* 替换为`c066d759-24ae-40e7-a56f-027002b5d3e4`

  示例：设置Exchange Online和Skype for Business：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  示例：为 SharePoint Online、OneDrive for Business 和 Teams 设置权限：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a>确保在密钥保管库上启用软删除

如果可以快速恢复密钥，不太可能因意外或恶意删除密钥而遇到服务中断。 启用此配置（称为软删除）后，才能将密钥与客户密钥一同使用。 启用软删除后，您可以在删除后 90 天内恢复密钥或保管库，而无需从备份中还原它们。
  
若要在密钥保管库上启用软删除，请完成以下步骤：
  
1. 使用帐户登录 Azure Windows PowerShell。 有关说明，请参阅[使用 Azure PowerShell](/powershell/azure/authenticate-azureps)。

2. 运行 [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet。 本示例中 *，保管库* 名称是要启用软删除的密钥保管库的名称：

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. 通过运行 **Get-AzKeyVault** cmdlet 确认为密钥保管库配置了软删除。 如果为密钥保管库正确配置了软删除，则"启用 _软_ 删除"属性将返回 **值 True**：

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>通过创建或导入密钥将密钥添加到每个密钥保管库

有两种方法可以将密钥添加到 Azure 密钥保管库;可以直接在 密钥保管库 创建密钥，也可以导入密钥。 直接在密钥保管库项并不复杂，但导入密钥可完全控制密钥的生成方式。 使用 RSA 密钥。 Azure 密钥保管库不支持使用椭圆曲线键换行和取消环绕。
  
若要直接在密钥保管库中创建密钥，请运行 [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet，如下所示：
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

其中：

- *保管* 库名称是你想要创建密钥的密钥保管库的名称。

- *key name* 是你想要提供新密钥的名称。

  > [!TIP]
  > 使用与上述密钥保管库类似的命名约定命名密钥。 这样，在只显示键名称的工具中，字符串是自描述的。
  
如果要使用 HSM 保护密钥，请确保将 **HSM** 指定为 _Destination_ 参数的值，否则请指定 **Software**。

例如：
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

若要将密钥直接导入密钥保管库，您需要具有 nCipher nShield 硬件安全模块。
  
一些组织倾向于使用此方法来建立其密钥的验证，然后此方法还提供以下证明：
  
- 用于导入的工具集包括来自 nCipher 的证明，证明用于加密生成的密钥的密钥 Exchange Key (KEK) 不可导出，并且是在 nCipher 制造的真正 HSM 内生成的。

- 工具集包括 nCipher 的证明，密钥保管库安全世界是在 nCipher 制造的真正 HSM 上生成的。 此证明证明 Microsoft 也使用正版 nCipher 硬件。

请与安全组核实，确定是否需要上述证明。 有关在本地创建密钥并导入密钥保管库的详细步骤，请参阅如何生成和传输[受 HSM](/azure/key-vault/keys/hsm-protected-keys) 保护的 Azure 密钥保管库。 使用 Azure 说明在每个密钥保管库中创建密钥。
  
### <a name="check-the-recovery-level-of-your-keys"></a>检查密钥的恢复级别

Microsoft 365 Azure 密钥保管库 订阅设置为"不取消"，并且客户密钥使用的密钥已启用软删除。 可以通过查看密钥上的恢复级别来确认订阅设置。
  
若要检查密钥的恢复级别，请在 Azure PowerShell 中Get-AzKeyVaultKey cmdlet，如下所示：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

如果"恢复级别"属性返回除 **"Recoverable+ProtectedSubscription**"值外的其他值，请确保将订阅置于"不取消"列表中，并且已在每个密钥保管库上启用软删除。
  
### <a name="back-up-azure-key-vault"></a>备份 Azure 密钥保管库

创建或更改密钥后，立即执行备份并存储备份副本（联机和脱机）。 不要将脱机副本连接到任何网络。 而是将它们存储在脱机位置，例如物理安全或商业存储设备中。 应至少将一份备份副本存储在发生灾难时可访问的位置。 备份 blob 是还原密钥材料的唯一方法，密钥保管库密钥被永久销毁或呈现为不可操作。 Azure 密钥保管库 外部且导入到 Azure 密钥保管库 的密钥不限定为备份，因为客户密钥使用该密钥所需的元数据不存在于外部密钥中。 只有从 Azure 密钥保管库的备份可以使用客户密钥执行还原操作。 因此，在上传或创建密钥密钥保管库必须创建 Azure 应用程序备份。
  
若要创建 Azure 帐户密钥密钥保管库，请运行 [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet，如下所示：

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

确保输出文件使用后缀 `.backup`。
  
此 cmdlet 生成的输出文件已加密，不能在 Azure 密钥保管库。 备份只能还原到进行备份的 Azure 订阅。
  
> [!TIP]
> 对于输出文件，选择保管库名称和密钥名称的组合。 这将使文件名自描述。 它还将确保备份文件名不会发生冲突。
  
例如：
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>验证 Azure 密钥保管库配置设置

在 DEP 中使用密钥之前验证是可选的，但强烈建议这样做。 如果使用除本文所述步骤外的步骤设置密钥和保管库，请验证 Azure 密钥保管库 资源的运行状况，然后再配置客户密钥。
  
若要验证密钥是否已启用 `get`、 `wrapKey`和 `unwrapKey` 操作：
  
运行 [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

在输出中，查找访问策略和 Exchange Online GUID (GUID) 或 SharePoint Online 标识 (GUID) 。 以上所有三种权限都必须显示在"密钥权限"下。
  
如果访问策略配置不正确，请Set-AzKeyVaultAccessPolicy cmdlet，如下所示：
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

例如，对于 Exchange Online 和 Skype for Business：
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

例如，对于 SharePoint Online 和 OneDrive for Business：
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

若要验证未为密钥设置到期日期，请运行 [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

客户密钥不能使用过期密钥。 尝试使用过期密钥的操作将失败，并可能导致服务中断。 我们强烈建议用于客户密钥的密钥没有过期日期。 一旦设置过期日期，就无法删除，但可以更改为其他日期。 如果必须使用设置了过期日期的密钥，将过期值更改为 12/31/9999。 到期日期设置为 12/31/9999 外的日期的密钥无法通过Microsoft 365验证。
  
若要更改已设置为 12/31/9999 外的任何值的到期日期，请运行 [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 不要设置与客户密钥一同使用的加密密钥的到期日期。
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>获取每个 Azure 帐户密钥密钥保管库 URI

设置密钥保管库并添加密钥后，运行以下命令，获取每个密钥保管库中密钥的 URI。 稍后创建和分配每个 DEP 时，你将使用这些 URI，因此将此信息保存在一个安全的位置。 针对每个密钥保管库运行一次此命令。
  
在Azure PowerShell：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a>后续步骤

完成本文中的步骤后，即可创建和分配 DEP。 有关说明，请参阅 [管理客户密钥](customer-key-manage.md)。

## <a name="related-articles"></a>相关文章

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [服务加密](office-365-service-encryption.md)