---
title: '迁移阶段对从德国 Microsoft 云迁移的操作和) '
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/05/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：了解从德国 Microsoft 云 (德国) 迁移到新的德国数据中心区域 Office 365 服务的迁移阶段操作和影响。
ms.openlocfilehash: e3ed1d76a755ce6326ac6ae53b990136a10b564a
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644712"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland"></a>迁移阶段从德国 Microsoft 云迁移的操作和影响

从德国 Microsoft 云 (MCD) 到 Microsoft Office 365 全球服务"德国"地区的租户迁移作为一组阶段执行，并针对每个工作负载配置操作。 此图显示了迁移到新的德国数据中心的十个阶段。

![迁移到新德国数据中心的十个阶段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

迁移过程将在几周内完成，具体取决于组织的总体大小和复杂性。 在迁移过程中，用户和管理员能够继续利用服务，并对此文档进行详细介绍，并做出显著更改。 图形和表定义迁移期间阶段和步骤。

|步骤|持续时间|负责方|说明|
|:--------|:--------|:--------|:--------|
|Opt-In|工作时间|客户|选择你的组织加入迁移。|
|预工作|天|客户|完成为迁移准备用户、工作站和网络所需的工作。|
|Azure Active Directory (Azure AD) |1-2 天|Microsoft|将 Azure AD 组织迁移到全球。|
|Azure|周|客户|创建新的全球 Azure 订阅并转换 Azure 服务。|
|订阅&许可证转换|1-2 天|Microsoft|购买全球订阅、取消德国 Microsoft 云订阅和转换用户许可证。|
|SharePoint 和 OneDrive|15 天以上|Microsoft|迁移 SharePoint 和 OneDrive for Business 内容，保留 sharepoint.de URL。|
|Exchange Online|15 天以上|Microsoft|迁移 Exchange Online 内容并转换到全球 URL。|
|安全与合规|1-2 天|Microsoft|转换安全&合规性策略和内容。|
|Skype for Business|1-2 天|Microsoft|从 Skype for Business 过渡到 Microsoft Teams。|
|Power BI & Dynamics 365|15 天以上|Microsoft|迁移 Power BI 和 Dynamics 365 内容。|
|完成 Azure AD|1-2 天|Microsoft|将租户完全转换到全球。|
|Clean-Up|1-2 天|客户|清理到德国 Microsoft 云的旧连接，例如 Active Directory 联合身份验证服务 (AD FS) 信赖方信任、Azure AD Connect 和 Office 客户端重新启动。|
|终结点已禁用|30 天|Microsoft|Azure AD 完成 30 天后，德国 Microsoft 云 Azure AD 服务将停止对已转换组织的终结点访问。 从此时开始，针对德国 Microsoft 云服务的终结点请求（如身份验证）将失败。 |


阶段及其操作可确保将关键数据和体验迁移到 Office 365 全球服务。 将租户添加到迁移队列后，每个工作负载都将作为在后端服务上执行的一组步骤完成。 某些工作负载可能需要管理员或 (用户) ，或者迁移可能会影响执行和在如何组织迁移中讨论的阶段的 [使用情况？](ms-cloud-germany-transition.md#how-is-the-migration-organized)

以下各节包含工作负载在迁移的不同阶段过程中的操作和效果。 查看这些表，并确定哪些操作或效果适用于您的组织。 确保你已准备好按需要执行各个阶段中的步骤。 未能完成必要的步骤可能会导致服务中断，并可能延迟到 Office 365 服务的迁移完成。

## <a name="phase-opt-in"></a>阶段：Opt-In

适用于：在 Microsoft 云德国 (MCD 中托管 Office 365 租户的所有客户) 未经同意，Microsoft 无法迁移 MCD 中托管的 Office 365 租户。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-----|:-------|
|**客户任务**：授予迁移许可| 客户同意迁移，以便 Microsoft 获得迁移和安排数据和服务到 Office 365 全局服务实例的转换的权利。 有两种方法 <ol><li>Office 365 租户管理员选择加入 Microsoft 推动的迁移。 </li><li> 客户在 2020 年 5 月 1 日之后续订了 MCD Office 365 租户的任何订阅。 Microsoft 每月向这些客户通知迁移时间，等待 30 天，让客户有机会取消迁移，然后直接选择加入。</li></ol> | <ul><li>租户标记为已同意迁移，管理中心将显示确认。 </li><li>Acknowledgment 将张贴到 Office 365 租户消息中心。 服务配置从德国 Microsoft 云终结点继续。 </li><li> </li></ul>
|**租户管理员**：监视邮件|租户管理员必须监视 Office 365 消息中心，以从此时开始更新迁移阶段状态。|客户可以实时执行必要的任务。
||||

## <a name="phase-1-before-the-migration-starts"></a>阶段 1：开始迁移之前

确保您熟悉适用于所有客户的 [迁移准备步骤](ms-cloud-germany-transition-add-pre-work.md)。

如果你拥有一个或多个 DNS 命名空间中设置了名为 _msoid_ 的 DNS CNAME，必须删除 CNAME，直到最晚阶段 8 结束。 可以在阶段 8 结束之前随时删除 CNAME _msoid。_ 请参阅 [DNS 的预工作](ms-cloud-germany-transition-add-pre-work.md#dns-entries-for-custom-domains)。

如果你对 Microsoft 云德国实例中的 Office 365 和 Azure 使用单一登录，则必须相应地准备和计划 Azure 订阅迁移。 确保你了解 Microsoft [Azure 的前期工作](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure)。

### <a name="azure-ad-connect-with-ad-fs-federation"></a>使用 AD FS 联合身份验证的 Azure AD Connect
**适用于：** 使用 AD FS 联合身份验证的客户

**应用时**：在阶段 2 启动之前

如果使用的是 Active Directory 联合身份验证服务 (AD FS) ，请确保在阶段 2 开始之前为 Office 365 全局服务添加信赖方信任之前和之后备份 [ADFS](ms-cloud-germany-transition-azure-ad.md)配置。

## <a name="phase-2-azure-ad-migration"></a>阶段 2：Azure AD 迁移
在此阶段，Azure Active Directory 将迁移到新的数据中心区域并变为活动状态。 旧的 Azure AD 终结点仍然可用。

## <a name="phase-3-subscription-transfer"></a>阶段 3：订阅转移

**适用于：Office** 365 租户托管在德国 Microsoft 云场中 (客户) 

不会迁移德国 Microsoft 云合作伙伴租户。 云解决方案提供商客户将迁移到同一合作伙伴的新 Office 365 服务租户下的 Office 365 服务。 客户迁移后，合作伙伴只能从 Office 365 服务租户管理此客户。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 订阅已转移| Microsoft 云德国订阅将迁移到相应的 Office 365 全球服务订阅。 <ul><li>该订阅的 Office 365 全局服务由 Microsoft (也称为产品/服务 _映射) 。_</li><li> 相应的 Office 365 全局服务订阅在已转移的德国 Microsoft 云的 Office 365 全局实例中购买。</li><li>完成时，将从 Office 365 服务租户中删除德国旧版 Microsoft 云订阅。</li></ul>| <ul><li>更改现有订阅将 (例如，在此阶段不会更改新订阅) 席位计数。</li><li>许可证分配更改将被阻止。</li><li>订阅迁移完成后，Office 365 服务和德国 Microsoft 云订阅都将在 Office 365 管理门户中可见，状态为"Microsoft 云德国订阅已取消预配 _"。_ </li><li>依赖德国 Microsoft 云订阅或 SKU GUID 的任何客户流程都将中断，并且需要通过 Office 365 服务产品进行修订。 </li><li>Office 365 服务中的新订阅将在新术语 (monthly/quarterly/year) 中购买，客户将收到 Microsoft 云德国订阅未使用余额的按比例退款。 </li></ul> |
|重新分配许可证|在 Office 365 全局实例中，将为具有德国 Microsoft 云许可证的用户分配许可证。|<ul><li>用户将被重新分配到新 Office 365 服务订阅的许可证。 所有用户的用户许可证将自动分配给新功能。</li><li>Office 365 (所提供的) 计划的功能数可以大于原始 Microsoft 云德国产品/服务计划中的功能数。 Office 365 服务中的用户许可证将等效分配给类似的 Microsoft 云德国功能 (服务计划) 。 </li></ul> 
|**管理任务** 禁用功能|如果需要，管理员需要执行显式操作来禁用这些功能。 |<ul><li>用户在门户中看到新的未知服务</li><li>其他功能可用于 (，例如 Microsoft Planner 和 Microsoft Flow) ，除非租户管理员已禁用。若要了解如何禁用分配给用户许可证的服务计划，请参阅在分配用户许可证时禁用对 [Microsoft 365 服务的访问权限](disable-access-to-services-while-assigning-user-licenses.md)。</li></ul>
|**管理任务**|通过 Office 365 服务产品修改依赖 Microsoft 德国 Microsoft 云订阅或 SKU GUID 的任何客户流程|客户流程继续工作。
||||

**适用于：** 使用 Office 365 合作伙伴门户的 Microsoft 合作伙伴

在第 2 阶段至第 3 阶段之间，合作伙伴门户可能无法访问。 在此期间，合作伙伴可能无法访问合作伙伴门户上的租户信息。 由于每次迁移都不同，因此辅助功能的持续时间可能为小时。


## <a name="phase-4-sharepoint-online"></a>第 4 阶段：SharePoint Online

**适用于：** 使用 SharePoint Online 的所有客户

如果您仍在使用 SharePoint 2013 工作流，请限制 SharePoint Online 迁移期间使用 SharePoint 2013 工作流。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-----|:-------|
| SharePoint 和 OneDrive 已转换 | 在此阶段，SharePoint Online 和 OneDrive for Business 从德国 Microsoft 云迁移到 Office 365 全球服务。<br><ul><li>保留现有的德国 Microsoft 云 URL (例如 `contoso.sharepoint.de` ，) 。</li><li>保留现有网站。</li><li>由德国 Microsoft 云或 Office 365 全局服务实例中的安全令牌服务 (STS) 颁发的客户端身份验证令牌在转换期间有效。</li></ul>|<ul><li>迁移期间，内容将在两个短暂时段内为只读。 在此期间，期望 SharePoint 中显示"无法编辑内容"横幅。</li><li>不会保留搜索索引，可能需要 10 天才能重建。</li><li>迁移期间，SharePoint Online 和 OneDrive for Business 内容将在两小段时间内为只读。 在此期间，用户将短暂看到"你无法编辑内容"横幅。</li><li>SharePoint Online 迁移完成后，重建索引时，SharePoint Online 和 OneDrive for Business 内容的搜索结果可能不可用。 在此期间，搜索查询可能不会返回完整结果。 重建索引完成时，依赖搜索索引的功能（如 SharePoint Online 新闻）可能会受到影响。</li><li>SharePoint 2013 工作流将在迁移过程中中断，并且必须在迁移后重新发布。</li></ul>
|**SPO 管理员**：重新发布 SharePoint 2013 工作流| SharePoint Online 管理员在迁移后重新发布 SharePoint 2013 工作流。|SharePoint 2013 工作流可用。
|**PowerShell 用户**：更新到新模块| SharePoint Online Powershell 模块的所有用户都需要在 SharePoint Online 迁移完成后将模块/Microsoft.SharePointOnline.CSOM 更新到版本 16.0.20717.12000 或版本以上。 完成在消息中心中传达。| 通过 PowerShell 或客户端对象模型的 SharePoint Online 将不再失败。
||||

其他注意事项：

- 如果组织仍使用 SharePoint 2010 工作流，则它们在 2021 年 12 月 31 日之后将不再工作。 SharePoint 2013 工作流仍受支持，尽管新租户默认从 2020 年 11 月 1 日开始关闭。 迁移到 SharePoint Online 服务完成后，建议移动到 Power Automate 或其他受支持的解决方案。

- 其 SharePoint Online 实例尚未迁移的 Microsoft 云德国客户需要留在 SharePoint Online PowerShell 模块/Microsoft.SharePointOnline.CSOM 版本 16.0.20616.12000 或以下。 否则，通过 PowerShell 或客户端对象模型连接到 SharePoint Online 将失败。


> [!NOTE]
> 如果使用电子数据展示，请确保了解电子 [数据展示迁移体验](ms-cloud-germany-transition-add-experience.md)。

## <a name="phase-5-exchange-online"></a>第 5 阶段：Exchange Online 

**适用于：** 使用 Exchange Online 的所有客户

如果你使用的是 Exchange Online 混合：Exchange Online 混合管理员必须执行混合配置向导， ( **HCW**) 多次作为此转换的一部分。 在 [迁移步骤 5](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-customers)开始之前应用 Exchange **预工作**。 Exchange Online 混合客户必须在"Office 365 Germany"模式下运行最新版本的 Exchange 混合配置向导 (HCW) ，以准备本地配置以迁移到 Office 365 全局服务。

完成迁移阶段 **9** (当消息中心通知发布) 时，你需要使用 Office 365 全球设置再次运行 HCW，以将本地系统指向 Office 365 全球服务。

如果要在阶段 5 期间修改用户照片，请参阅 [Exchange Online Set-UserPhoto阶段](#exchange-online-powershell)

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
|**管理员**：停止邮箱移动|停止或删除任何载入或载出邮箱移动，即不在本地 Exchange 和 Exchange Online 之间移动邮箱。  | 这可确保邮箱移动请求不会失败并出现错误。 如果不这样做，可能会导致服务或 Office 客户端失败。 |
| 新区域"Germany"将添加到组织设置中。 | Exchange Online 配置将新的德国本地区域添加到转换组织。 | |
| Exchange Online 邮箱从德国 Microsoft 云移动到 Office 365 全局服务。| Office 365 全局服务区域设置为默认区域，这使内部负载平衡服务能够将邮箱重新分发到 Office 365 服务中的相应默认区域。 在此转换中，使用 MCD (全局服务) 位于同一组织中，并且可以使用任一 URL 终结点。 |<ul><li>将用户和服务从旧式 MCD URL (outlook.office.de) 新的 Office 365 服务 URL `https://outlook.office365.com` () 。</li><li>在迁移过程中，用户可能会继续通过旧 MCD URL 访问服务，但需要在迁移完成后停止使用旧 URL。</li><li>用户应过渡到使用全球 Office 门户，以使用 Office Online 功能， (日历、邮件、) 。 在迁移到 Office 365 服务之前，导航到尚未迁移到 Office 365 服务的服务将无法正常工作。 </li><li>迁移Outlook Web App无法提供公用文件夹体验。 </li></ul>|
| **管理员**：更新自动发现的自定义 DNS 设置| 当前指向德国 Microsoft 云的自动发现的客户托管 DNS 设置需要进行更新，以在 Exchange Online 阶段 (阶段 5) 完成时引用 Office 365 全局终结点。 <br> 指向 CNAME 的现有 DNS autodiscover-outlook.office.de 需要进行更新以指向 autodiscover.outlook.com。 |  通过自动发现的可用性请求和服务发现调用直接指向 Office 365 服务。 迁移完成时，不执行这些 DNS 更新的客户可能会遇到自动发现服务问题。 |
||||

### <a name="exchange-online-powershell"></a>Exchange Online PowerShell
**适用于：** 使用 Exchange Online PowerShell 的 Exchange Online 管理员

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
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?


- `myaccount.microsoft.com` will only work after the tenant cutover in phase 9. Links will produce "something went wrong" error messages until that time.
-->
- 访问Outlook Web App环境中共享邮箱的用户 (例如，MCD 环境中的用户访问全局环境中共享邮箱的) 将提示他们第二次进行身份验证。 用户必须先进行身份验证，然后在 中访问其邮箱 `outlook.office.de` ，然后打开 中的共享邮箱 `outlook.office365.com` 。 在访问在其他服务中托管的共享资源时，他们将需要第二次进行身份验证。

- 对于现有的德国 Microsoft 云客户或转换中的客户，当使用文件 **> 信息 >** 添加帐户将共享邮箱添加到 Outlook 时，查看日历权限可能会失败 (Outlook 客户端尝试使用 Rest API `https://outlook.office.de/api/v2.0/Me/Calendars`) 。 希望添加帐户以查看日历权限的客户可以添加注册表项，如在 [Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 中共享日历的用户体验更改中所述，以确保此操作成功。 可以使用组策略在组织范围内部署此注册表项。

若要详细了解组织在迁移和迁移 Exchange Online 资源后的区别，请查看迁移到新的德国数据中心区域 [Office 365](ms-cloud-germany-transition-experience.md)服务期间客户体验信息。


## <a name="phase-6-exchange-online-protection--security-and-compliance"></a>第 6 阶段：Exchange Online Protection /安全性和合规性

**适用于：** 使用 Exchange Online 的所有客户<br>

后端 Exchange Online Protection (EOP) 功能复制到新区域"Germany"。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| Exchange Online 路由的迁移和历史邮件详细信息。 | Exchange Online 支持从外部主机到 Office 365 的路由。 外部 MX 记录将转换为路由到 EOP 服务。 迁移租户配置和历史详细信息。 |<ul><li>Microsoft 管理的 DNS 条目从 Office 365 Germany EOP 更新为 Office 365 服务。</li><li>客户应在 EOP 双写迁移后等待 30 天。 否则，可能会丢失数据。</li></ul>|
||||

## <a name="phase-7-skype-for-business-online"></a>第 7 阶段：Skype for Business Online

**适用于：** 使用 Skype for Business Online 的所有客户

确保你熟悉 Skype for [Business Online](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online) 迁移过程前期工作。

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 将 Skype for Business 迁移到 Teams。 | 现有 Skype for Business 客户迁移到欧洲 Office 365 全球服务，然后转换到 Office 365 服务"德国"地区的 Microsoft Teams。 |<ul><li>用户将无法在迁移日期登录到 Skype for Business。 在迁移前 10 天，我们将向管理中心发布信息，告知你何时进行迁移，以及何时开始迁移。</li><li> 迁移策略配置。 </li><li>用户将被迁移到 Teams，迁移后将不再拥有 Skype for Business。 </li><li>用户必须已安装 Teams 桌面客户端。 安装将在 10 天内通过 Skype for Business 基础结构上的策略进行，但如果失败，用户仍然需要下载客户端或与受支持的浏览器连接。 </li><li>联系人和会议将迁移到 Teams。</li><li>在时间服务转换到 Office 365 服务之间，用户将无法登录 Skype for Business，除非客户 DNS 条目已完成。 </li><li>联系人和现有会议将继续用作 Skype for Business 会议。 </li></ul>|
||||

如果迁移阶段 9 完成后，你必须使用 PowerShell 连接到 Skype for Business Online，请使用以下代码进行连接：

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential -OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"
```

## <a name="phase-8-dynamics-365"></a>阶段 8：Dynamics 365

**适用于：** 使用 Microsoft Dynamics 365 的所有客户

确保您熟悉 [Microsoft Dynamics 365](ms-cloud-germany-transition-add-pre-work.md#dynamics365) 安装过程前期工作。

使用 Dynamics 365 的客户需要额外的参与，以独立迁移组织的 Dynamics 组织。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| Microsoft Dynamics 资源 | 使用 Microsoft Dynamics 的客户将参与 Microsoft 工程或 Microsoft FastTrack，以将 Microsoft Dynamics 365 转换到 Office 365 全局服务实例。* |<ul><li>迁移后，管理员验证组织。 <</li><li>管理员在必要时修改工作流。 </li><li>管理员会在适当时清除 AdminOnly 模式。</li><li>管理员根据情况从 _沙_ 盒更改组织类型</li><li>通知最终用户新 URL 以访问组织 (实例) 。</li><li>将任何入站连接更新到新的终结点 URL。 </li><li>在转换期间，用户无法使用 Dynamics 服务。 </li><li>用户需要在每个组织迁移后验证组织运行状况和功能。</li></ul>|
||||

\* () Microsoft Dynamics 365 的客户必须按照提供的迁移过程定义，在此迁移方案中采取措施。  (ii) 客户采取操作失败意味着 Microsoft 无法完成迁移。  (iii) 当 Microsoft 因客户的不作为无法完成迁移时，客户的订阅将于 2021 年 10 月 29 日到期。

## <a name="phase-8-power-bi"></a>第 8 阶段：Power BI

**适用于：** 所有使用 Microsoft Power BI (PBI) 

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| Power BI 资源的迁移 | 使用 Microsoft Power BI (PBI) 的客户将在手动触发现有 PBI 迁移工具以将 Power BI 转换为 Office 365 全局服务实例后，由 Microsoft 工程或 Microsoft FastTrack 参与。\*\* |<ul><li>以下 Power BI 项目 _不会_ 转换，必须重新创建：<</li><li>实时数据集 (，例如流式处理或推送) 。 </li><li>Power BI 本地数据网关配置和数据源。 </li><li>基于实时数据集构建的报告在迁移后将不可用，并且需要重新创建。 </li><li>Power BI 服务在转换期间将不可用。 服务的不可用时间不应超过 24 小时。</li><li>迁移后，用户需要使用 Power BI 服务重新配置数据源及其本地数据网关。  在执行此操作之前，用户将无法使用这些数据源来针对这些数据源执行计划刷新和/或直接查询。 </li><li>无法迁移容量和高级工作区。 客户需要在迁移之前删除所有容量，在迁移后重新创建它们。 将工作区移回所需的容量。</li></ul>  |
||||

\*\* (使用 Microsoft Power BI) 客户必须按照提供的迁移过程定义，在此迁移方案中采取措施。  (ii) 客户采取操作失败意味着 Microsoft 无法完成迁移。  (iii) 当 Microsoft 因客户的不作为无法完成迁移时，客户的订阅将于 2021 年 10 月 29 日到期。

## <a name="phase-9--10-azure-ad-finalization"></a>第 9 & 10 阶段：Azure AD 最终完成

**适用于：** 所有客户

当 Office 365 租户完成迁移的最后步骤 [Azure AD 最终完成 (第 9) 阶段]时，所有服务将转换到全球。 任何应用程序或用户都不应针对任何 Microsoft 云德国终结点访问租户的资源。 自动完成 30 天后，Microsoft 云德国 Azure AD 服务将自动停止对已转换租户的终结点访问。 从此时开始，针对德国 Microsoft 云服务的终结点请求（如身份验证）将失败。 

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 更新用户终结点 | 确保所有用户使用正确的 Microsoft 全球终结点访问服务 |迁移完成 30 天后，德国 Microsoft 云终结点将停止处理请求;客户端或应用程序流量将失败。  |
| 更新 Azure AD 应用程序终结点 | 必须将应用程序的身份验证、Azure Active Directory (Azure AD) Graph 和 MS Graph 终结点更新为 Microsoft Worldwide 服务的终结点。 | 迁移完成 30 天后，德国 Microsoft 云终结点将停止处理请求;客户端或应用程序流量将失败。 |
||||

## <a name="office-apps"></a>Office 应用

**适用于：** 使用 Office 桌面应用程序的所有客户 (Word、Excel、PowerPoint、Outlook、...) 

迁移到"德国"地区的 Office 365 租户要求所有用户在租户迁移到达阶段 9 后关闭、注销 Office 365，然后重新登录所有 Office 桌面应用程序 (Word、Excel、PowerPoint、Outlook 等 ) 和 OneDrive for Business 客户端。 通过登录和登录，Office 服务可以获取来自全局 Azure AD 服务的新身份验证令牌。

确保您已完成移动设备 [的前期工作](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) 过程。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 客户端、Office Online 和 Office 客户端切换期间，Azure AD 将完成租户范围以指向 Office 365 服务。 | 此配置更改允许 Office 客户端更新并指向 Office 365 服务终结点。 | <ul><li>通知用户关闭 _所有_ Office 应用，然后重新登录 (或强制客户端重新启动，并强制用户登录) 以使 Office 客户端能够选取更改。 </li><li>通知用户和技术支持人员，用户可能会看到一个 Office 横幅，提示他们在转换后 72 小时内重新激活 Office 应用。 </li><li>个人计算机上的所有 Office 应用程序都必须关闭，用户必须注销然后重新登录。 在黄色激活栏中，登录以重新激活 Office 365 服务。</li><li>共享计算机需要类似于个人计算机的操作，并且不需要特殊过程。 </li><li>在移动设备上，用户必须注销应用，关闭它们，然后重新登录。</li></ul>|
||||

## <a name="phase-9-line-of-business-apps"></a>阶段 9：业务线应用

如果你拥有业务线应用，请确保已完成业务线应用过程 [前期](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) 工作。

## <a name="post-migration"></a>迁移后

请务必阅读迁移 [后活动文章并](ms-cloud-germany-transition-add-experience.md) 相应地执行它们。
