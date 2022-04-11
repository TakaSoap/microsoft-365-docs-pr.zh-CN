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
description: 了解如何为Microsoft 365设置客户密钥。
ms.openlocfilehash: 38b8a73a1c4654e1922f4f8e4600727a978af431
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759957"
---
# <a name="set-up-customer-key"></a>设置客户密钥

借助客户密钥，可以控制组织的加密密钥，然后将Microsoft 365配置为使用它们来加密 Microsoft 数据中心中的静态数据。 换句话说，客户密钥允许客户使用其密钥添加属于他们的加密层。

设置 Azure，然后才能将客户密钥用于Office 365。 本文介绍创建和配置所需的 Azure 资源所需的步骤，然后提供在Office 365中设置客户密钥的步骤。 设置 Azure 后，确定要分配哪些策略（以及哪些密钥）来加密组织中各种Microsoft 365工作负荷的数据。 有关客户密钥或常规概述的详细信息，请参阅[Office 365中客户密钥的服务加密](customer-key-overview.md)。
  
> [!IMPORTANT]
> 强烈建议遵循本文中的最佳做法。 这些被标为 **提示** 和 **重要**。 使用客户密钥可以控制根加密密钥，其范围可以与整个组织一样大。 这意味着，这些密钥所犯的错误可能会产生广泛影响，并可能导致服务中断或不可撤销的数据丢失。
  
## <a name="before-you-set-up-customer-key"></a>在设置客户密钥之前

在开始之前，请确保组织拥有适当的 Azure 订阅和 M365/O365 许可。 必须使用付费 Azure 订阅。 通过免费、试用、赞助、MSDN 订阅和旧版支持下的订阅不符合条件。

> [!IMPORTANT]
> 提供 M365 客户密钥的有效 M365/O365 许可证包括：
>
> - Office 365 E5
> - Microsoft 365 E5
> - Microsoft 365 E5 合规
> - Microsoft 365 E5 信息保护 &治理 SKU
> - Microsoft 365 FLW 的安全性和符合性

将继续支持现有Office 365 高级合规版许可证。

若要了解本文中的概念和过程，请查看 [Azure 密钥保管库](/azure/key-vault/)文档。 此外，熟悉 Azure 中使用的术语，例如[，Azure AD租户](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)。
  
如果需要文档以外的更多支持，请联系 Microsoft 咨询服务 (MCS) 、Premier Field Engineering (PFE) 或 Microsoft 合作伙伴以获取帮助。 若要提供有关客户密钥（包括文档）的反馈，请将你的想法、建议和观点发送到 customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>设置客户密钥的步骤概述

若要设置客户密钥，请按列出的顺序完成这些任务。 本文的其余部分提供每个任务的详细说明，或链接到进程中每个步骤的详细信息。
  
**在 Azure 和Microsoft FastTrack中：**
  
你将通过远程连接到Azure PowerShell来完成其中的大部分任务。 为了获得最佳结果，请使用版本 4.4.0 或更高版本的Azure PowerShell。
  
- [创建两个新的 Azure 订阅](#create-two-new-azure-subscriptions)

- [提交请求以激活客户密钥Office 365](#submit-a-request-to-activate-customer-key-for-office-365)

- [注册 Azure 订阅以使用强制保留期](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  此注册过程需要五个工作日才能完成。
- [请联系相应的 Microsoft 别名以继续此过程](#contact-the-corresponding-microsoft-alias-to-proceed-with-the-process)

- [在每个订阅中创建高级 Azure 密钥保管库](#create-a-premium-azure-key-vault-in-each-subscription)

- [为每个密钥保管库分配权限](#assign-permissions-to-each-key-vault)

- [确保在密钥保管库上启用软删除](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [通过创建或导入密钥向每个密钥保管库添加密钥](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [验证密钥的过期日期](#verify-expiration-date-of-your-keys)

- [检查密钥的恢复级别](#check-the-recovery-level-of-your-keys)

- [备份 Azure 密钥保管库](#back-up-azure-key-vault)

- [获取每个 Azure 密钥保管库密钥的 URI](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>在 Azure 密钥保管库和客户密钥Microsoft FastTrack中完成任务

在 Azure 密钥保管库中完成这些任务。 你需要为与客户密钥一起使用的所有 DEP 完成这些步骤。
  
### <a name="create-two-new-azure-subscriptions"></a>创建两个新的 Azure 订阅

客户密钥需要两个 Azure 订阅。 作为最佳做法，Microsoft 建议创建新的 Azure 订阅以与客户密钥一起使用。 Azure 密钥保管库密钥只能为同一Azure Active Directory (Microsoft Azure Active Directory) 租户中的应用程序授权，必须使用与组织一起使用的同一Azure AD租户创建新订阅，其中将分配 DEP。 例如，使用组织中具有全局管理员权限的工作或学校帐户。 有关详细步骤，请参阅以 [组织身份注册 Azure](/azure/active-directory/fundamentals/sign-up-organization)。
  
> [!IMPORTANT]
> 客户密钥需要每个数据加密策略的两个密钥 (DEP) 。 为此，必须创建两个 Azure 订阅。 作为最佳做法，Microsoft 建议组织中的单独成员在每个订阅中配置一个密钥。 应仅使用这些 Azure 订阅来管理Office 365的加密密钥。 如果某个操作员意外、有意或恶意删除或以其他方式不当管理其负责的密钥，这将保护组织。

可以为组织创建的 Azure 订阅数量没有实际限制。 遵循这些最佳做法可最大程度地减少人为错误的影响，同时帮助管理客户密钥使用的资源。
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>提交请求以激活客户密钥Office 365

创建两个新的 Azure 订阅后，需要在[Microsoft FastTrack门户](https://fasttrack.microsoft.com/)中提交相应的客户密钥产品/服务请求。 在产品/服务表单中对组织内的授权指定所做的选择对于完成客户密钥注册至关重要，也是必需的。 组织中那些选定角色的官员确保任何撤销和销毁与客户密钥数据加密策略一起使用的所有密钥的请求的真实性。 对于要用于组织的每个客户密钥 DEP 类型，需要执行一次此步骤。

**FastTrack团队不提供客户密钥的帮助。Office 365只需使用FastTrack门户即可提交表单，并帮助我们跟踪客户密钥的相关产品/服务。提交FastTrack请求后，请联系相应的客户密钥加入团队，开始加入过程。**
  
若要提交激活客户密钥的产品/服务，请完成以下步骤：
  
1. 使用组织中具有全局管理员权限的工作或学校帐户登录到[Microsoft FastTrack门户](https://fasttrack.microsoft.com/)。

2. 登录后，选择相应的域。

3. 对于所选域，请从顶部导航栏中选择 **请求服务** ，并查看可用产品/服务列表。

4. 选择适用于你的产品/服务的信息卡：

   - **多个Microsoft 365工作负荷：为Microsoft 365** 产品/服务选择 **请求加密密钥帮助**。

   - **Exchange Online和Skype for Business：** 为Exchange产品/服务选择 **请求加密密钥帮助**。

   - **SharePoint联机、OneDrive和Teams文件：** 为SharePoint和OneDrive for Business产品/服务选择 **请求加密密钥帮助**。

5. 查看产品/服务详细信息后，选择 **“继续”步骤 2**。

6. 填写产品/服务表单上的所有适用详细信息和请求的信息。 特别注意你选择的组织官员要授权批准对加密密钥和数据进行永久和不可逆的销毁。 完成窗体后，选择“ **提交**”。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>注册 Azure 订阅以使用强制保留期

根加密密钥的暂时性或永久性丢失可能会对服务操作造成破坏性甚至灾难性影响，并可能导致数据丢失。 因此，与客户密钥一起使用的资源需要强大的保护。 与客户密钥产品/服务保护机制一起使用的所有 Azure 资源超出了默认配置。 可以在 *强制保留期内* 标记或注册 Azure 订阅。 强制保留期可防止立即取消和不可撤销的 Azure 订阅。 在强制保留期内注册 Azure 订阅所需的步骤需要与Microsoft 365团队协作。 此过程需要五个工作日才能完成。 以前，强制保留期有时称为“不取消”。
  
> [!IMPORTANT]
> 在联系Microsoft 365团队之前，必须针对与 Customer Key 一起使用的 **每个** Azure 订阅执行以下步骤。 在开始之前，请确保已安装[Azure PowerShell Az](/powershell/azure/new-azureps-module-az) 模块。

1. 使用Azure PowerShell登录。 有关说明，请参阅[使用Azure PowerShell登录](/powershell/azure/authenticate-azureps)。

2. 运行Register-AzProviderFeature cmdlet 注册订阅以使用强制保留期。 为每个订阅完成此操作。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

### <a name="contact-the-corresponding-microsoft-alias-to-proceed-with-the-process"></a>请联系相应的 Microsoft 别名以继续此过程

>[!NOTE]
> 在联系相应的 Microsoft 别名之前，请验证是否已完成 M365 客户密钥的FastTrack请求。

- 若要启用客户密钥以将 DEP 分配到各个Exchange Online邮箱，请联系 [exock@microsoft.com](mailto:exock@microsoft.com)。

- 若要启用客户密钥以分配 DEP 来加密联机SharePoint和OneDrive for Business内容 (包括所有租户用户) Teams文件，请联系 [spock@microsoft.com](mailto:spock@microsoft.com)。

- 若要启用客户密钥，以便为所有租户用户分配用于加密多个Microsoft 365工作 (Exchange Online负荷中的内容，请联系 m365-ck@service.microsoft.com Teams、MIP EDM [) ](mailto:m365-ck@service.microsoft.com)。

- 在电子邮件中包含以下信息：

     **主题**：客户密钥 \<*Your tenant's fully qualified domain name*\>

     **正文**：包括要加入到的 **每个** 客户密钥服务的FastTrack请求 ID 和订阅 ID。 这些订阅 ID 是你想要完成的必需保留期以及每个订阅的Get-AzProviderFeature输出。

完成此过程的服务级别协议 (SLA) 为 5 个工作日，一旦 Microsoft 收到通知 (并验证) 你已注册订阅以使用强制保留期。

### <a name="verify-the-status-of-each-your-azure-subscriptions"></a>验证每个 Azure 订阅的状态

从 Microsoft 收到注册已完成的通知后，请按如下所示运行Get-AzProviderFeature命令来验证注册状态。 如果已验证，则Get-AzProviderFeature命令返回注册 **状态** 属性的 **“已注册**”值。 为 **每个** 订阅完成此步骤。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

若要完成此过程，请运行Register-AzResourceProvider命令。 为 **每个** 订阅完成此步骤。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   ```

   ```powershell
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

> [!TIP]
> 在继续操作之前，请确保“RegistrationState”设置为“已注册”，如下图所示。
>
> ![强制保留期](../media/MandatoryRetentionPeriod.png)

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每个订阅中创建高级 Azure 密钥保管库

使用 [Azure 密钥保管库](/azure/key-vault/general/overview)入门记录创建密钥保管库的步骤，指导你完成安装和启动Azure PowerShell、连接到 Azure 订阅、创建资源组以及在该资源组中创建密钥保管库。
  
创建密钥保管库时，必须选择 SKU：标准或高级版。 标准 SKU 允许使用软件保护 Azure 密钥保管库密钥-没有硬件安全模块 (HSM) 密钥保护 - 高级版 SKU 允许使用 HSM 保护密钥保管库密钥。 客户密钥接受使用任一 SKU 的密钥保管库，但 Microsoft 强烈建议仅使用高级版 SKU。 具有任一类型的密钥的操作成本相同，因此成本的唯一差异是每个受 HSM 保护的密钥每月的成本。 有关详细信息，请参阅[密钥保管库定价](https://azure.microsoft.com/pricing/details/key-vault/)。
  
> [!IMPORTANT]
> 将高级版 SKU 密钥保管库和受 HSM 保护的密钥用于生产数据，并且仅使用标准 SKU 密钥保管库和密钥进行测试和验证。
  
对于将使用 Customer Key 的每个Microsoft 365服务，请在创建的两个 Azure 订阅中的每一个创建一个密钥保管库。 例如，若要使客户密钥能够将 DEP 用于Exchange Online、SharePoint联机和多工作负荷方案，你将创建三对密钥保管库。
  
对密钥保管库使用命名约定，该约定反映要与保管库关联的 DEP 的预期用途。 有关命名约定建议，请参阅下面的最佳做法部分。
  
为每个数据加密策略创建单独的配对保管库集。 对于Exchange Online，将策略分配到邮箱时，将选择数据加密策略的范围。 邮箱只能分配一个策略，最多可以创建 50 个策略。 SharePoint联机策略的范围包括组织内地理位置或 *地理* 位置中的所有数据。 多工作负荷策略的范围包括所有用户支持的工作负荷中的所有数据。

创建密钥保管库还需要创建 Azure 资源组，因为密钥保管库需要存储容量 (，但小) 和密钥保管库日志记录（如果启用）也会生成存储数据。 作为最佳做法，Microsoft 建议使用单独的管理员来管理每个资源组，其管理权限与管理所有相关客户密钥资源的管理员集保持一致。
  
### <a name="assign-permissions-to-each-key-vault"></a>为每个密钥保管库分配权限

需要为每个密钥保管库定义三组单独的权限，具体取决于实现。 例如，需要为以下每个权限定义一组权限：
  
- 对组织的密 **钥保管库进行日常管理的密钥保管库管理员**。 这些任务包括备份、创建、获取、导入、列表和还原。

  > [!IMPORTANT]
  > 分配给密钥保管库管理员的权限集不包括删除密钥的权限。 这是有意的，也是一个重要的做法。 通常不会删除加密密钥，因为这样做会永久销毁数据。 最佳做法是，默认情况下不要向密钥保管库管理员授予此权限。 相反，请将此保留给密钥保管库参与者，并且只有在了解了对后果的明确了解后，才将其分配给管理员。
  
  若要将这些权限分配给组织中的用户，请使用Azure PowerShell登录到 Azure 订阅。 有关说明，请参阅[使用Azure PowerShell登录](/powershell/azure/authenticate-azureps)。

  - 运行Set-AzKeyVaultAccessPolicy cmdlet 以分配所需的权限。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   例如：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- 可以更改 Azure 密钥保管库本身权限的 **密钥保管库参与者**。 当员工离开或加入团队时，需要更改这些权限。 在极少数情况下，密钥保管库管理员合法地需要权限来删除或还原密钥，你还需要更改权限。 需要为这组密钥保管库参与者授予密钥保管库的 **参与者** 角色。 可以使用 Azure 资源管理器分配此角色。 有关详细步骤，请参阅[“使用Role-Based 访问控制管理对 Azure 订阅资源的访问权限](/azure/active-directory/role-based-access-control-configure)。 创建订阅的管理员隐式具有此访问权限，并且能够将其他管理员分配到参与者角色。

- 对用于客户密钥的每个密钥保管库 **Microsoft 365** 应用程序的权限，需要授予 wrapKey、unwrapKey 以及获取对相应Microsoft 365服务主体的权限。

  若要授予Microsoft 365服务主体的权限，请使用以下语法运行 **Set-AzKeyVaultAccessPolicy** cmdlet：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   其中：
   - *保管库名称* 是创建的密钥保管库的名称。
   - 对于Exchange Online和Skype for Business，请将 *Office 365 appID* 替换为`00000002-0000-0ff1-ce00-000000000000`
   - 对于 SharePoint Online、OneDrive for Business 和 Teams 文件，请将 *Office 365 appID* 替换为`00000003-0000-0ff1-ce00-000000000000`
   - 对于适用于所有租户用户的多工作负荷策略 (Exchange Teams Microsoft 信息保护) ，*请将 Office 365 appID* 替换为`c066d759-24ae-40e7-a56f-027002b5d3e4`

  示例：设置Exchange Online和Skype for Business的权限：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  示例：设置SharePoint联机、OneDrive for Business和Teams文件的权限：

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

  通过运行 *Get-AzKeyVault* cmdlet，确认向 **每个** 密钥保管库授予 *Get、wrapKey 和 unwrapKey*。

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```  

> [!Tip]
> 在继续操作之前，请确保为密钥保管库正确配置权限，对 *密钥的权限* 将返回 **wrapKey、unwrapKey、get**。
> 请确保更正你要加入的正确服务的权限。 下面列出了每个服务的 *显示名称* ：  
  >
  > - Exchange Online和Skype for Business：*Office 365 Exchange Online*
  > - SharePoint联机、OneDrive和Teams文件：*Office 365 SharePoint联机*
  > - 多个Microsoft 365工作负荷：*M365DataAtRestEncryption*
  >  
  > 例如，下面的代码片段是确保为 M365DataAtRestEncryption 配置权限的示例。 以下包含名为 *mmcexchangevault* 的保管库的 cmdlet 将显示以下字段。
  >
  > ```powershell
  >   Get-AzKeyVault -VaultName mmcexchangevault | fl
  >   ```  
  >
  >
  > ![Exchange Online客户密钥的加密密码。](../media/KeyVaultPermissions.png)

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a>确保在密钥保管库上启用软删除

如果可以快速恢复密钥，则不太可能因为意外或恶意删除密钥而导致服务中断。 在将密钥与客户密钥配合使用之前，请启用此配置（称为软删除）。 启用软删除可在删除后 90 天内恢复密钥或保管库，而无需从备份还原密钥或保管库。
  
若要在密钥保管库上启用软删除，请完成以下步骤：
  
1. 使用Windows PowerShell登录到 Azure 订阅。 有关说明，请参阅[使用Azure PowerShell登录](/powershell/azure/authenticate-azureps)。

2. 运行 [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet。 在此示例中， *保管库名称* 是要为其启用软删除的密钥保管库的名称：

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. 通过运行 **Get-AzKeyVault** cmdlet，确认为密钥保管库配置了软删除。 如果为密钥保管库正确配置了软删除，则 *Soft Delete Enabled* 属性将返回 **True** 值：

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

> [!TIP]
> 在继续操作之前，请确保“已启用软删除？” 设置为“True”，如下图所示。
>
> <img src="../media/SoftDeleteEnabled.png" alt="SoftDelete" width="400"/>

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>通过创建或导入密钥向每个密钥保管库添加密钥

可通过两种方法将密钥添加到 Azure 密钥保管库;可以直接在密钥保管库中创建密钥，也可以导入密钥。 直接在密钥保管库中创建密钥并不复杂，但导入密钥可以完全控制密钥的生成方式。 使用 RSA 密钥。 Azure 密钥保管库不支持使用椭圆曲线键进行包装和解包。

有关向每个保管库添加密钥的说明，请参阅 [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)。

 有关在本地创建密钥并将其导入密钥保管库的详细步骤，请参阅[如何为 Azure 密钥保管库生成和传输受 HSM 保护的密钥](/azure/key-vault/keys/hsm-protected-keys)。 使用 Azure 说明在每个密钥保管库中创建密钥。

### <a name="verify-expiration-date-of-your-keys"></a>验证密钥的过期日期

若要验证密钥是否未设置过期日期，请运行 [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet，如下所示：
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

客户密钥不能使用过期的密钥。 尝试使用过期密钥的操作将失败，并可能导致服务中断。 强烈建议与客户密钥一起使用的密钥没有过期日期。 无法删除过期日期（一旦设置），但可以更改为其他日期。 如果必须使用设置过期日期的密钥，请将过期值更改为 12/31/9999。 到期日期设置为 12/31/9999 以外的日期的密钥不会通过Microsoft 365验证。
  
若要更改已设置为 12/31/9999 以外的任何值的到期日期，请运行 [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet，如下所示：
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 请勿在与客户密钥一起使用的加密密钥上设置过期日期。  

### <a name="check-the-recovery-level-of-your-keys"></a>检查密钥的恢复级别

Microsoft 365要求将 Azure 密钥保管库订阅设置为“不取消”，并且客户密钥使用的密钥已启用软删除。 可以通过查看密钥上的恢复级别来确认订阅设置。
  
若要检查密钥的恢复级别，请在Azure PowerShell中运行Get-AzKeyVaultKey cmdlet，如下所示：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

> [!Tip]
> 在继续操作之前，如果 *恢复级别* 属性返回的值与 **Recoveryable+ProtectedSubscription** 的值不同，请确保已在订阅上注册了 *MandatoryRetentionPeriodEnabled* 功能，并且已在每个密钥保管库上启用了软删除。
>
>    <img src="../media/RecoveryLevel.png" alt="drawing" width="500"/>

### <a name="back-up-azure-key-vault"></a>备份 Azure 密钥保管库

创建密钥或对密钥进行任何更改后，立即执行备份并在线和脱机存储备份的副本。
若要创建 Azure 密钥保管库密钥的备份，请运行 [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet。

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>获取每个 Azure 密钥保管库密钥的 URI

设置密钥保管库并添加密钥后，运行以下命令以获取每个密钥保管库中密钥的 URI。 稍后创建并分配每个 DEP 时，将使用这些 URI，因此请将此信息保存在安全的位置。 为每个密钥保管库运行一次此命令。
  
在Azure PowerShell中：
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a>后续步骤

完成本文中的步骤后，即可创建和分配 DEP。 有关说明，请参阅 [“管理客户密钥](customer-key-manage.md)”。

## <a name="related-articles"></a>相关文章

- [使用客户密钥执行服务加密](customer-key-overview.md)

- [管理客户密钥](customer-key-manage.md)

- [滚动或旋转客户密钥或可用性密钥](customer-key-availability-key-roll.md)

- [了解可用性密钥](customer-key-availability-key-understand.md)

- [服务加密](office-365-service-encryption.md)
