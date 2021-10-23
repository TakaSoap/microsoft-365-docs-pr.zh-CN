---
title: '迁移阶段操作和影响从德国 Microsoft 云迁移) '
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 10/21/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：了解从德国 Microsoft 云迁移到德国 microsoft 云 (到德国) Office 365服务的迁移阶段操作和影响。
ms.openlocfilehash: fc113b0d81312a199282a5b2f0ec652ffd8cad8d
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60554632"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland"></a>迁移阶段从德国 Microsoft 云迁移的操作和影响

从德国 Microsoft 云 (MCD) 到 Microsoft Office 365 全球服务的区域"德国"的租户迁移作为一组阶段执行，并针对每个工作负载配置操作。 此图显示了迁移到新的德国数据中心的十个阶段。

[![迁移到新德国数据中心的十个阶段。](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)](../media/ms-cloud-germany-migration-opt-in/migration-organization.png#lightbox)

迁移过程将在几周内完成，具体取决于组织的总体大小和复杂性。 在迁移过程中，用户和管理员能够继续利用服务，并对此文档进行详细介绍，并做出显著更改。 图形和表定义迁移期间阶段和步骤。

> [!NOTE]
> Azure 服务的迁移不是本文档的一部分。 有关该信息，请参阅 Azure [德国的迁移指南](/azure/germany/germany-migration-main)。

<br>

****

|步骤 () |期限|负责方|说明|
|---|---|---|---|
|Opt-In|工作时间|客户|选择你的组织加入迁移。|
|预工作|天|客户|完成为迁移准备用户、工作站和网络所需的工作。|
|Azure Active Directory (Azure AD) |1-2 天|Microsoft|将Azure AD迁移到全球。|
|Azure|周|客户|创建新的全球 Azure 订阅并 [转换 Azure 服务](/azure/azure-resource-manager/management/move-resource-group-and-subscription)。|
|订阅&许可证转换|1-2 天|Microsoft|购买全球订阅、取消德国 Microsoft 云订阅和转换用户许可证。|
|SharePoint 和 OneDrive|15 天以上|Microsoft|迁移SharePoint和OneDrive for Business内容，保留 sharepoint.de URL。|
|Exchange Online|15 天以上|Microsoft|迁移Exchange Online内容并转换到全球 URL。|
|安全与合规|1-2 天|Microsoft|转换安全&合规性策略和内容。|
|Skype for Business|1-2 天|Microsoft|从 Skype for Business 转换为 Microsoft Teams。|
|Power BI & Dynamics 365|15 天以上|Microsoft|迁移 Power BI 和 Dynamics 365 内容。|
|完成Azure AD|1-2 天|Microsoft|将租户完全转换到全球。|
|Clean-Up|1-2 天|客户|清理到德国 Microsoft 云的旧连接，例如 Active Directory 联合身份验证服务 (AD FS) 信赖方信任、Azure AD 连接 和 Office 客户端重新启动。|
|终结点已禁用|30 天|Microsoft|完成迁移后 30 Azure AD，德国 Microsoft 云Azure AD服务将停止对已转换组织的终结点访问。 从此时开始，针对德国 Microsoft 云服务的终结点请求（如身份验证）将失败。 在链接到德国 Microsoft 云服务Office 365实例中运行 Azure 工作负载的客户稍后将移至最终迁移阶段。|
|

阶段及其操作可确保将关键数据和体验迁移到 Office 365 全局服务。 将租户添加到迁移队列后，每个工作负载都将作为在后端服务上执行的一组步骤完成。 某些工作负载可能需要管理员或 (用户) ，或者迁移可能会影响执行和在如何组织迁移中讨论的阶段的 [使用情况？](ms-cloud-germany-transition.md#how-is-the-migration-organized)

以下各节包含工作负载在迁移的不同阶段过程中的操作和效果。 查看这些表，并确定哪些操作或效果适用于您的组织。 确保你已准备好按需要执行各个阶段中的步骤。 未能完成必要的步骤可能会导致服务中断，并可能延迟到 Office 365 服务的迁移。

## <a name="phase-opt-in"></a>阶段：Opt-In

适用于：在 Microsoft 云德国 (MCD) Microsoft 托管的 Office 365 租户的所有客户未经同意Office 365无法迁移 MCD 中托管的 Office 365 租户。

<br>

****

|步骤 () |说明|影响|
|---|---|---|
|**客户任务**：授予迁移许可|客户授予迁移同意，以便 Microsoft 获得迁移数据和服务以及安排数据和服务到全局服务实例Office 365的权利。 有两种方法： <ol><li>租户Office 365选择加入 Microsoft 驱动的迁移。</li><li>客户在 2020 年 5 月 1 日Office 365 MCD 租户中续订了任何订阅。 Microsoft 每月向这些客户通知迁移时间，等待 30 天，让客户有机会取消迁移，然后直接选择加入。</li></ol>|<ul><li>租户标记为已同意迁移，并且管理中心显示确认。</li><li>Acknowledgment 将张贴到Office 365消息中心。 服务配置从德国 Microsoft 云终结点继续。</li></ul>
|**租户管理员**：监视邮件|租户管理员必须监视Office 365消息中心，以从此时开始更新迁移阶段状态。|客户可以实时执行必要的任务。
|

## <a name="phase-1-before-the-migration-starts"></a>阶段 1：开始迁移之前

确保您熟悉适用于所有客户的迁移 [准备步骤](ms-cloud-germany-transition-add-pre-work.md)。

如果你拥有一个或多个 DNS 命名空间中设置了名为 _msoid_ 的 DNS CNAME，必须删除 CNAME，直到最晚阶段 8 结束。 可以在阶段 8 结束之前随时删除 CNAME _msoid。_ 请参阅 [DNS 的预工作](ms-cloud-germany-transition-add-pre-work.md#dns-entries-for-custom-domains)。

如果你对德国 Microsoft 云实例中的 Office 365 和 Azure 使用单一登录，则必须相应地准备和计划 Azure 订阅迁移。 确保你了解[Microsoft Azure。](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure)

### <a name="azure-ad-connect-with-ad-fs-federation"></a>Azure AD 连接 AD FS 联盟

**适用于：** 使用 AD FS 联合身份验证的客户

**应用时**：在阶段 2 启动之前

如果使用 Active Directory 联合身份验证服务 (AD FS) ，请确保在阶段 2 开始之前为 Office 365 全局服务添加信赖方信任之前和之后备份[ADFS](ms-cloud-germany-transition-add-adfs.md) 配置。

## <a name="phase-2-azure-ad-migration"></a>阶段 2：Azure AD迁移

在此阶段，Azure Active Directory迁移到新的数据中心区域，并变为活动状态。 旧的Azure AD终结点仍将可用。

### <a name="exchange-online-hybrid---modify-authserver-on-premises"></a>Exchange Online混合 - 修改本地 AuthServer

**适用于：** 使用活动混合配置的所有Exchange混合配置Exchange本地服务器

**应用时**：阶段 2 结束后

迁移完成后，本地 AuthServer 必须指向全局安全令牌服务 (STS) 进行身份验证Azure AD身份验证。
这可确保对来自迁移状态（面向混合本地环境）的用户Exchange可用性请求的身份验证请求进行身份验证以访问本地服务。 同样，这将确保对从本地到全局服务终结点Office 365身份验证。
完成Azure AD迁移 (阶段 2) 后，本地 Exchange (混合) 拓扑的管理员必须为 Office 365 全局服务添加新的身份验证服务终结点。

通过 PowerShell 中的Exchange，将 替换为你组织的租户 ID，该 ID 位于 Azure Active Directory `<TenantID>` 上的 Azure 门户中。

```powershell
New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantID>/metadata/json/1
```

未能完成此任务可能会导致混合忙/闲请求无法为从 Microsoft 云德国迁移到德国的邮箱用户提供Office 365信息。

## <a name="phase-3-subscription-transfer"></a>阶段 3：订阅转移

**适用于：** 拥有托管在德国 Microsoft 云Office 365 MCD 租户的所有 (客户) 

<br>

****

|步骤 (步骤) |说明|影响|
|---|---|---|
|订阅已转移|Microsoft 云德国订阅将迁移到相应的全球Office 365服务订阅。 <ul><li>该Office 365的全局服务服务由 Microsoft (也称为产品/服务映射) 。 </li><li> 在Office 365德国 Microsoft 云的 Office 365 全局实例中购买相应的全局服务订阅。</li><li>完成时，将从 Office 365 服务租户中删除德国旧版 Microsoft 云订阅。</li></ul>|<ul><li>更改现有订阅将 (例如，在此阶段不会更改新订阅) 席位计数。</li><li>许可证分配更改将被阻止。</li><li>订阅迁移完成后，Office 365 服务和德国 Microsoft 云订阅都将在 Office 365 Admin 门户中可见，状态为"Microsoft 云德国订阅已取消预配 _"。_</li><li>依赖德国 Microsoft 云订阅或 SKU GUID 的任何客户流程都将中断，并且需要根据 Office 365 服务产品进行修改。</li><li>Office 365 服务中的新订阅将在新术语 (monthly/quarterly/year) 中购买，客户将收到 Microsoft 云德国订阅未使用余额的按比例退款。</li></ul>|
|重新分配许可证|已分配有德国 Microsoft 云许可证的用户将在全局实例中Office 365许可证。|<ul><li>用户将被重新分配到新订阅服务订阅Office 365许可证。 所有用户的用户许可证将自动分配给新功能。</li><li>由德国 (提供) 计划Office 365的功能数可能大于原始 Microsoft 云德国产品/服务计划中的功能数。 企业服务中的Office 365许可证将等效分配给类似的 Microsoft 云德国功能 (服务计划) 。</li></ul>|
|**管理任务** 禁用功能|如果需要，管理员需要执行显式操作来禁用这些功能。|<ul><li>用户在门户中看到新的未知服务</li><li>其他功能 (，例如 Microsoft Planner 和 Power Automate) ，除非租户管理员已禁用。</li></ul> <p> 若要了解如何禁用分配给用户许可证的服务计划，请参阅在分配用户许可证Microsoft 365禁用对服务[的访问权限](disable-access-to-services-while-assigning-user-licenses.md)。</li></ul>|
|**管理任务**|使用 Microsoft 云服务产品修改依赖 Microsoft 德国云订阅或 SKU GUID 的任何Office 365流程|客户流程继续工作。|
|

**适用于：** 使用 Microsoft 合作伙伴门户Office 365 Microsoft 合作伙伴

在第 2 阶段至第 3 阶段之间，合作伙伴门户可能无法访问。 在此期间，合作伙伴可能无法访问合作伙伴门户上的租户信息。 由于每次迁移都不同，因此辅助功能的持续时间可能为小时。

合作伙伴租户迁移 中提供了云解决方案 [提供商的其他信息](ms-cloud-germany-transition-add-csp.md#partner-tenant-migration)。

## <a name="phase-4-sharepoint-online"></a>第 4 阶段：SharePoint Online

**适用于：** 使用 SharePoint Online 的所有客户

如果您仍在使用 SharePoint 2013 工作流，请限制 SharePoint Online 迁移期间使用 SharePoint 2013 工作流。

<br>

****

|步骤 (步骤) |说明|影响|
|---|---|---|
|SharePoint和OneDrive转换|SharePoint联机和OneDrive for Business在此阶段从德国 Microsoft 云Office 365全球服务。 <ul><li>保留现有的德国 Microsoft 云 URL (例如 `contoso.sharepoint.de` ，) 。</li><li>保留现有网站。</li><li>由德国 Microsoft 云或 Office 365 全局服务实例中的安全令牌服务 (STS) 颁发的客户端身份验证令牌在转换期间有效。</li></ul>|<ul><li>迁移期间，内容将在两个短暂时段内为只读。 在此期间，预期"你无法编辑内容"横幅在SharePoint。</li><li>不会保留搜索索引，可能需要 10 天才能重建。</li><li>SharePoint联机OneDrive for Business内容在迁移期间将保持只读状态两小段时间。 在此期间，用户将短暂看到"你无法编辑内容"横幅。</li><li>完成 SharePoint Online 迁移后，SharePoint Online 和 OneDrive for Business 内容的搜索结果可能在重建索引时不可用。 在此期间，搜索查询可能不会返回完整结果。 重建索引完成时，依赖于搜索索引的功能（如 SharePoint Online News）可能会受到影响。</li><li>SharePoint 2013 工作流将在迁移过程中中断，并且必须在迁移后重新发布。</li></ul>|
|**SPO 管理员**：重新发布SharePoint 2013 工作流|SharePoint Online 管理员在迁移SharePoint重新发布 SharePoint 2013 工作流。|这是一项必需操作。 如果不这样做，可能会导致用户混淆、技术支持呼叫和工作效率降低。|
|**PowerShell 用户**：更新到新模块|完成 SharePoint Online 迁移后，SharePoint Online PowerShell 模块的所有用户都需要将模块/Microsoft.SharePointOnline.CSOM 更新到版本 16.0.20717.12000 或版本 12000。 完成在消息中心中传达。|SharePoint通过 PowerShell 或客户端对象模型联机将不再失败。|
|

其他注意事项：

- 如果您的组织仍使用 SharePoint 2010 工作流，则它们在 2021 年 12 月 31 日之后将不再工作。 SharePoint 2013 工作流仍将受支持，尽管新租户默认从 2020 年 11 月 1 日开始关闭。 迁移到 SharePoint Online 服务后，我们建议你移动到 Power Automate 或其他支持的解决方案。
- 其 SharePoint Online 实例尚未迁移的德国 Microsoft 云客户需要留在 SharePoint Online PowerShell 模块/Microsoft.SharePointOnline.CSOM 版本 16.0.20616.12000 或以下版本上。 否则，SharePoint PowerShell 或客户端对象模型连接到联机连接将失败。
- 在此阶段中，将更改SharePoint URL 后面的 IP 地址。 转换到 Office 365 全局服务后，保留的租户 URL 的地址 (例如，) 将更改为全球 Microsoft 365 URL 和 IP 地址范围 (SharePoint Online 和 `contoso.sharepoint.de` `contoso-my.sharepoint.de` [OneDrive for Business) ](/microsoft-365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business)。
- 虽然SharePoint和OneDrive服务进行转换，Office Online 可能无法如期工作。
- 如果已应用自定义搜索配置，则完成转换后导入搜索配置。 在转换前必须导出搜索配置，如 SharePoint Online 的迁移前[步骤中所述](ms-cloud-germany-transition-add-pre-work.md#sharepoint-online)。

> [!NOTE]
> 如果使用电子数据展示，请确保了解电子 [数据展示迁移体验](ms-cloud-germany-transition-add-scc.md)。

## <a name="phase-5-exchange-online"></a>第 5 阶段：Exchange Online

从第 5 阶段Exchange Online，邮箱从德国 Microsoft 云Office 365全局服务。

全局Office 365区域设置为默认，这使内部负载平衡服务能够将邮箱重新分发到 Office 365 服务中的相应默认区域。 在此转换中，使用 MCD (全局服务) 位于同一组织中，并且可以使用任一 URL 终结点。

新区域"Germany"将添加到组织设置中。 Exchange Online配置将新的德国本地区域添加到转换组织。

- 将用户和服务从旧式 MCD URL () 新的 Office 365 `https://outlook.office.de` 服务 URL `https://outlook.office365.com` () 。
- 新的Exchange Online区域 (Outlook Web 访问Exchange管理中心) 服务将在此阶段提供，之前不可用。
- 在迁移过程中，用户可能会继续通过旧 MCD URL 访问服务，但需要在迁移完成后停止使用旧 URL。
- 用户应过渡到使用全球 Office 门户Office日历、 (邮件、) 。 导航到尚未迁移到 Office 365服务在迁移之前将无法正常工作。
- 此限制也适用于后台服务，如"我的帐户"。 完成第 9 阶段后，"我的全局帐户"服务将变为可用。 在此之前，用户必须使用 MCD 门户来管理其帐户设置。
- 迁移Outlook Web App无法提供公用文件夹体验。

如果要在阶段 5 中修改用户照片，请参阅第 5 阶段Exchange Online [PowerShell - Set-UserPhoto用户照片](#exchange-online-powershell)。

### <a name="dns-record-for-autodiscover-in-exchange-online"></a>dns Record for Autodiscover in Exchange Online

**适用于：** 使用自定义Exchange Online自定义域的客户

当前指向德国 Microsoft 云的自动发现的客户托管 DNS 设置需要进行更新，以在 Exchange Online 阶段第 (阶段完成后引用 Office 365 全局终结点) 。

指向 CNAME 的现有 DNS 条目 autodiscover-outlook.office.de 更新为指向 **autodiscover.outlook.com。**

完成迁移阶段 **9** 后不执行这些 DNS 更新的客户在迁移完成后可能会遇到服务问题。

> [!NOTE]
> 可以忽略"自动发现"条目的自定义域管理中心中的验证错误。 只有在 CNAME 记录更改为"已设置"时，服务 autodiscover.outlook.com。

### <a name="exchange-online-powershell"></a>Exchange Online PowerShell

**适用于：Exchange Online** PowerShell Exchange Online管理员

在迁移阶段，使用 PowerShell cmdlet **New-MigrationEndpoint、Set-MigrationEndpoint** 和 **Test-MigrationsServerAvailability** 可能会导致代理 (错误) 。  当仲裁邮箱已迁移到全球，但管理员邮箱没有或相反的情况时，将发生这种情况。 若要解决此问题，在创建租户 PowerShell 会话时，请使用仲裁邮箱作为 **ConnectionUri 中的路由提示**。 例如：

```powershell
New-PSSession
    -ConfigurationName Microsoft.Exchange
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@<tenant>.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

如果用户邮箱已迁移，但尚未迁移管理员邮箱，则使用 PowerShell cmdlet **Set-UserPhoto** 会导致错误，反之亦然。 在这种情况下，管理员必须在创建租户 PowerShell 会话时传递需要更改其照片的用户 `ConnectionUri` 的电子邮件 ID：

```powershell
-ConnectionUri "https://outlook.office.de/powershell-liveid?email=<user_email>"
```

其中 `<user_email>` 是用户邮箱的电子邮件 ID 的占位符。

其他注意事项：

- 访问Outlook Web App环境中共享邮箱的用户 (例如，MCD 环境中的用户访问全局环境中共享邮箱的) 将提示他们第二次进行身份验证。 用户必须先进行身份验证，然后在 中访问其邮箱 `outlook.office.de` ，然后打开 中的共享邮箱 `outlook.office365.com` 。 在访问在其他服务中托管的共享资源时，他们将需要第二次进行身份验证。
- 对于现有的德国 Microsoft 云客户或转换中的客户，当使用文件 **> 信息 >** 添加帐户将共享邮箱添加到 Outlook 时，查看日历权限可能会失败 (Outlook 客户端尝试使用 Rest API `https://outlook.office.de/api/v2.0/Me/Calendars`) 。 希望添加帐户以查看日历权限的客户可以添加注册表项，如在[Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec)中共享日历的用户体验更改中所述，以确保此操作成功。 可以使用组策略在组织范围内部署此注册表项。
- 使用活动 Exchange 混合配置的所有客户均无法将邮箱从本地 Exchange Server 移动到 Exchange Online，既不能移动到德国 Microsoft 云，也无法将邮箱移动到德国的新数据中心区域。 客户需要确保在阶段 5 之前已完成正在进行的邮箱移动，并且将在完成此阶段后恢复。
- 在从德国 Microsoft 云迁移到 Exchange迁移期间运行 `Test-MigrationServerAvailabiilty` PowerShell cmdlet Office 365服务可能不起作用。 但是，迁移完成后它将正常工作。
- 如果客户端在迁移邮箱后遇到凭据或授权问题，请通过运行 或通过使用 Exchange 控制面板 (ECP) 重新输入迁移终结点中的本地管理员 `Set-MigrationEndpoint -Identity <endpointName> -Credential $(Get-Credential)` 凭据。
- 确保为设备使用旧版协议 (POP3/IMAP4/SMTP) 的所有用户都准备好在 Exchange 邮箱移动到新的德国数据中心区域后更改其客户端中的终结点，如 Exchange Online 的迁移前步骤[中所述](ms-cloud-germany-transition-add-pre-work.md#exchange-online)。
- 迁移Skype for Business后，Outlook Web App中安排会议不再可用。 如有必要，用户必须改为使用Outlook。

若要详细了解组织在迁移中和迁移 Exchange Online 资源后的区别，请查看迁移到新的德国数据中心区域 Office 365 服务期间客户体验[中的信息](ms-cloud-germany-transition-experience.md)。

## <a name="phase-6-exchange-online-protection--security-and-compliance"></a>第 6 阶段Exchange Online Protection/安全性和合规性

**适用于：** 所有使用 Exchange Online

EOP Exchange Online Protection (功能) 复制到新区域"Germany"。 Exchange Online允许从外部主机Office 365迁移历史租户详细信息，其中还包括用于安全性和合规性功能的后端服务。

使用Exchange Online功能的客户 (非混合) 无需在此阶段关注。

### <a name="exchange-online-hybrid-deployments"></a>Exchange Online混合部署

**适用于：** 使用活动混合配置的所有Exchange混合配置Exchange本地服务器

确保在迁移 [Exchange](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-customers) **5** 开始之前应用了预工作。 Exchange Online混合客户必须在"Office 365 Germany"模式下运行最新版本的 Exchange 混合配置向导 (HCW) ，以准备本地配置以迁移到 Office 365 全局服务。

**管理员操作：**

- 从开始迁移阶段 6 到完成迁移阶段 9 (发布消息中心通知) 时，你需要使用 Office 365 全球设置再次运行 HCW，以将本地系统指向 Office 365 全球服务。 未能在阶段 9 [迁移完成] 之前完成此任务可能会导致本地部署和部署之间路由邮件的 EXCHANGE NDR Office 365。
- 停止或删除任何载入或载出邮箱移动，即不要在本地和 Exchange 之间移动Exchange Online。  这可确保邮箱移动请求不会失败并出现错误。 如果不这样做，可能会导致服务或客户端Office失败。
- 除了 HCW 创建的连接器之外创建的、面向 Exchange Online 的其他 Send-Connectors 必须在执行 HCW 运行后立即在此阶段进行更新，否则它们将停止工作。 必须为这些发送连接器更新 TLS 域。

  若要更新 TLS 域，请使用以下 PowerShell 命令在Exchange Server环境中：

  ```powershell
  Set-SendConnector -Identity <SendConnectorName> -TlsDomain "mail.protection.outlook.com"
  ```

## <a name="phase-7-skype-for-business-online---transition-to-microsoft-teams"></a>第 7 阶段：Skype for Business Online - 转换到 Microsoft Teams

**适用于：** 使用 Skype for Business Online 的所有客户

查看[联机迁移的Skype for Business，](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online)并确保你已完成所有步骤。
在此阶段，Skype for Business迁移到Microsoft Teams。 现有Skype for Business客户将迁移到Office 365全球服务，然后根据租户的注册国家/地区迁移到地区的[Microsoft Teams。](o365-data-locations.md)

- 用户将无法在迁移Skype for Business登录。
- 迁移策略配置。
- 用户将被迁移到Teams迁移后将无法再Skype for Business用户。
- 用户必须已安装Microsoft Teams客户端。 安装将在 10 天内通过 Skype for Business 基础结构上的策略进行，但如果失败，用户仍然需要下载客户端或与受支持的浏览器连接。
- 联系人和会议将迁移到Microsoft Teams。
- 在服务转换到 Skype for Business 之间，用户将无法登录Office 365，除非客户 DNS 条目已完成。
- 联系人和现有会议将继续作为会议Skype for Business工作。

当为域配置虚域Skype for Business，必须更新 DNS 条目。 请参阅[域中的Microsoft 365 管理中心](https://admin.microsoft.com/Adminportal/Home#/Domains)并应用 DNS 配置中的更改。

如果迁移阶段 9 完成后，Skype for Business PowerShell 连接到 Skype for Business Online，请使用以下 PowerShell 代码进行连接：

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential
```

### <a name="known-limitations-until-finalizing-azure-ad-migration"></a>完成迁移前已知Azure AD限制
Microsoft Teams使用 Azure AD。 虽然迁移Azure AD迁移，但迁移Microsoft Teams功能并不完全可用。 在第 9 阶段之后，Azure AD迁移完成之后，以下功能将完全可用：

- 无法在管理中心管理Microsoft Teams应用。
- 只能在新客户端中创建新Microsoft Teams，Teams管理员限制用户创建新团队的权限。 无法在管理中心内Microsoft Teams团队。
- Web 版本的Microsoft Teams不可用。

## <a name="phase-8-dynamics-365"></a>阶段 8：Dynamics 365

**适用于：** 使用 Microsoft Dynamics 365 的所有客户

确保您熟悉 [Microsoft Dynamics 365](ms-cloud-germany-transition-add-pre-work.md#dynamics-365) 安装过程前期工作。

使用 Dynamics 365 的客户需要额外的参与，以独立迁移组织的 Dynamics 组织。

<br>

****

|步骤 (步骤) |说明|影响|
|---|---|---|
|Microsoft Dynamics 资源|Microsoft 工程或 Microsoft FastTrack将 Microsoft Dynamics 365 Office 365全局服务实例。\*|<ul><li>迁移后，管理员验证组织。</li><li>管理员在必要时修改工作流。</li><li>管理员会在适当时清除 AdminOnly 模式。</li><li>管理员根据情况从 _沙_ 盒更改组织类型</li><li>通知最终用户新 URL 以访问组织 (实例) 。</li><li>将任何入站连接更新到新的终结点 URL。</li><li>在转换期间，用户无法使用 Dynamics 服务。</li><li>用户需要在每个组织迁移后验证组织运行状况和功能。</li></ul>|
|

\* (使用 Microsoft Dynamics 365) 客户必须按照提供的迁移过程定义，在此迁移方案中采取措施。  (ii) 客户采取操作失败意味着 Microsoft 无法完成迁移。  (iii) 当 Microsoft 因客户的不作为无法完成迁移时，客户的订阅将于 2021 年 10 月 29 日到期。

## <a name="phase-8-power-bi"></a>第 8 阶段：Power BI

**适用于：** 使用 Microsoft PBI Power BI (客户) 

<br>

****

|步骤 (步骤) |说明|影响|
|---|---|---|
|迁移Power BI资源|使用 Microsoft Power BI (PBI) 的客户将在手动触发现有 PBI 迁移工具以将 Power BI 转换为 Office 365 全球服务实例后，由 Microsoft 工程或 Microsoft FastTrack 参与。\*\*|<ul><li>以下Power BI项目 _将不会_ 转换，并且必须重新创建它们：<</li><li>实时数据集 (，例如流式处理或推送) 。</li><li>Power BI本地数据网关配置和数据源。</li><li>基于实时数据集构建的报告在迁移后将不可用，并且需要重新创建。</li><li>Power BI期间，用户无法使用服务。 服务的不可用时间不应超过 24 小时。</li><li>迁移后，用户需要为数据源及其本地数据网关重新配置Power BI服务。  在执行此操作之前，用户将无法使用这些数据源来针对这些数据源执行计划刷新和/或直接查询。</li><li>无法迁移容量和高级工作区。 客户需要在迁移之前删除所有容量，在迁移后重新创建它们。 将工作区移回所需的容量。</li></ul>|
|

\*\* () Microsoft Power BI的客户必须按照提供的迁移过程所定义的在此迁移方案中采取措施。  (ii) 客户采取操作失败意味着 Microsoft 无法完成迁移。  (iii) 当 Microsoft 因客户的不作为无法完成迁移时，客户的订阅将于 2021 年 10 月 29 日到期。

## <a name="phase-9-office-apps"></a>第 9 阶段：Office应用

**适用于：** 所有使用桌面Office应用程序 (Word、Excel、PowerPoint、Outlook、OneDrive...) 

在此阶段中，所有客户端应用程序和 Office Online 都执行客户端切换。 Azure AD租户范围以指向 Office 365 服务和相关终结点。

迁移到"德国"地区的 Office 365 租户要求所有用户在租户迁移到达阶段 9 后关闭、注销 Office 365，然后重新登录所有 Office 桌面应用程序 (Word、Excel、PowerPoint、Outlook 等 ) 和 OneDrive for Business 客户端。 通过登录和登录，Office服务从全局身份验证服务获取Azure AD令牌。

如果从Office执行退出和登录后，Office 桌面应用程序将不起作用，我们强烈建议在受影响的计算机上运行 Office 客户端转换工具[ (OCCT) ](https://github.com/microsoft/OCCT)来解决此问题。

如果 Office 客户端转换工具[ (OCCT) ](https://github.com/microsoft/OCCT)已提前在 Windows 客户端上部署和计划，则不需要执行注销/登录过程。

通过使用最新的应用程序，可确保最佳Office体验。 企业应考虑使用每月频道Enterprise频道。

确保您已完成移动设备 [的前期工作](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) 过程。

其他注意事项：

- 通知用户关闭所有 Office 应用，然后重新登录 (或强制客户端重新启动，并强制用户登录) 以使 Office 客户端能够选取更改。
- 通知用户和技术支持人员，用户可能会看到Office横幅，提示他们在转换后 72 小时内Office重新激活应用。
- 必须Office个人计算机上的所有应用程序，用户必须注销然后重新登录。 在黄色激活栏中，登录以重新激活Office 365服务。
- 共享计算机需要类似于个人计算机的操作，并且不需要特殊过程。
- 在移动设备上，用户必须注销应用，关闭它们，然后重新登录。

## <a name="phase-9-line-of-business-apps"></a>阶段 9：业务线应用

**适用于：** 使用连接到业务线应用的所有Office 365

如果你拥有业务线应用，请确保已完成业务线应用过程 [前期](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) 工作。

## <a name="phase-9--10-azure-ad-finalization"></a>阶段 9 & 10：Azure AD完成

**适用于：** 所有客户

当 Office 365 租户完成迁移的最后步骤 (阶段 9：Azure AD最终) ，所有服务将转换到全球。 任何应用程序或用户都不应针对任何 Microsoft 云德国终结点访问租户的资源。 自动完成 30 天后，Microsoft 德国云服务Azure AD将停止对已转换租户的终结点访问。 从此时开始，针对德国 Microsoft 云服务的终结点请求（如身份验证）将失败。

Microsoft Azure租户完成到全球的迁移后，客户必须按照 Azure 迁移操作手册中所述的步骤转换其[Azure](/azure/germany/germany-migration-main)工作负载 (第 9 阶段) 。

<br>

****

|步骤 (步骤) |说明|影响|
|---|---|---|
|更新用户终结点|确保所有用户使用正确的 Microsoft 全球终结点访问服务|迁移完成 30 天后，德国 Microsoft 云终结点将停止处理请求;客户端或应用程序流量将失败。|
|更新Azure AD应用程序终结点|必须将应用程序的身份验证、Azure Active Directory (Azure AD) Graph和 MS Graph更新为 Microsoft Worldwide 服务的终结点。|迁移完成 30 天后，德国 Microsoft 云终结点将停止处理请求;客户端或应用程序流量将失败。|
|迁移 Azure 工作负载|Azure 服务客户必须为 Azure 服务预配新的全球订阅，并按 [Azure 迁移手册 执行迁移](/azure/germany/germany-migration-main)。|完全过渡到全球服务 (阶段 10) ，客户将不再能够访问 Microsoft 德国 Microsoft 云 Azure 门户中的 Azure 工作负载。|
|

**适用于：** 拥有已Azure AD或已加入设备的客户

第 9 阶段完成后，Azure AD已注册和已加入的设备必须连接到新的德国数据中心Azure AD转换的设备实例。
未重新加入Azure AD设备可能在阶段 10 结束时不再运行。 有关详细说明和更多详细信息，请参阅 [有关设备的其他信息](ms-cloud-germany-transition-add-devices.md)。

### <a name="azure-ad-connect"></a>Azure AD Connect

**适用于：** 所有客户通过连接Azure AD标识

<br>

****

|步骤 (步骤) |说明|影响|
|---|---|---|
|更新Azure AD 连接。|完成到Azure AD后，组织将完全使用 Office 365 服务，并且不再连接到德国 Microsoft 云。 此时，客户需要确保增量同步过程已完成，然后，在注册表路径 中将字符串值从 `AzureInstance` 3 (Microsoft Cloud Deutschschland) 更改为 0。 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect`|更改 注册表 `AzureInstance` 项 的值。 如果不这样做，将导致在 Microsoft 云德国终结点不再可用后对象无法同步。|
|

## <a name="post-migration"></a>迁移后

请务必阅读迁移 [后活动文章并](ms-cloud-germany-transition-add-experience.md) 相应地执行它们。
