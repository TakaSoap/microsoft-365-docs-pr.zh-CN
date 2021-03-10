---
title: '迁移阶段操作和影响从 Microsoft 云德国迁移 (常规) '
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
description: 摘要：了解从德国 Microsoft 云 (德国 Microsoft 云) 迁移到新的德国数据中心区域 Office 365 服务的迁移阶段操作和影响。
ms.openlocfilehash: 045e29cba293dd74d3a77beae80d78380eaa4147
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50604004"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>迁移阶段操作和影响从 Microsoft 云德国迁移 (常规) 

从 Microsoft 云德国 (MCD) 到 Microsoft Office 365 全局服务的区域"Germany"的租户迁移作为一组阶段执行，并针对每个工作负载执行其配置的操作。 此图显示了迁移到新的德国数据中心的九个阶段。

![迁移到新德国数据中心的九个阶段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

迁移过程将在几周内完成，具体取决于组织的总体大小和复杂性。 在迁移进行过程中，用户和管理员能够继续利用服务，并在此文档中详细介绍了明显的更改。 图形和表定义迁移期间阶段和步骤。

|步骤|持续时间|负责人|说明|
|:--------|:--------|:--------|:--------|
|Opt-In|工作时间|客户|选择你的组织加入迁移。|
|预工作|天数|客户|完成为迁移准备用户、工作站和网络所需的工作。|
|Azure Active Directory (Azure AD) |1-2 天|Microsoft|将 Azure AD 组织迁移到全球。|
|Azure|周数|客户|创建新的全球 Azure 订阅并转换 Azure 服务。|
|订阅&许可证转换|1-2 天|Microsoft|购买全球订阅、取消德国 Microsoft 云订阅和转换用户许可证。|
|SharePoint 和 OneDrive|15 天以上|Microsoft|迁移 SharePoint 和 OneDrive for Business 内容，保留sharepoint.de URL。|
|Exchange Online|15 天以上|Microsoft|迁移 Exchange Online 内容并转换到全球 URL。|
|安全与合规|1-2 天|Microsoft|转换安全&合规性策略和内容。|
|Skype for Business|1-2 天|Microsoft|从 Skype for Business 过渡到 Microsoft Teams。|
|Power BI & Dynamics 365|15 天以上|Microsoft|迁移 Power BI 和 Dynamics 365 内容。|
|完成 Azure AD|1-2 天|Microsoft|完成到全球的租户转换。|
|Clean-Up|1-2 天|客户|清理到德国 Microsoft 云的旧连接，例如 Active Directory 联合身份验证服务 (AD FS) 信赖方信任、Azure AD Connect 和 Office 客户端重新启动。|

阶段及其操作可确保将关键数据和体验迁移到 Office 365 全局服务。 将租户添加到迁移队列后，每个工作负载都将作为在后端服务上执行的一组步骤完成。 某些工作负载可能需要管理员或 (用户) 操作，或者迁移可能会影响执行并讨论了如何组织迁移的阶段的 [使用情况？](ms-cloud-germany-transition.md#how-is-the-migration-organized)

以下各节包含迁移各个阶段中工作负荷的操作和效果。 查看表并确定哪些操作或效果适用于您的组织。 确保您已准备好按需要执行各个阶段中的步骤。 未能完成必要的步骤可能会导致服务中断，并可能延迟到 Office 365 服务的迁移完成。

## <a name="opt-in"></a>Opt-In

**适用于：** 拥有 Office 365 租户的所有客户托管在 Microsoft 云德国 (MCD) 
| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-----|:-------|
| 未经同意，无法迁移在 MCD 中托管的 Office 365 租户。 | Microsoft 通过以下两种方式之一获得迁移权，这使 Microsoft 能够协调数据和服务到 Office 365 全局服务实例的转换。 <ol><li>Office 365 租户管理员选择加入 Microsoft 驱动的迁移。 </li><li> 客户在 2020 年 5 月 1 日之后续订其 MCD Office 365 租户的任何订阅。 我们将每月通知这些客户迁移，等待 30 天，让客户有机会取消迁移，然后直接选择加入。</li></ol> | <ul><li>租户标记为已同意迁移，管理中心显示确认。 </li><li>确认将发布至 Office 365 租户消息中心。 服务配置将继续从 Microsoft 云德国终结点进行。 </li><li>租户管理员必须监视 Office 365 消息中心，以更新 igration 阶段状态。 </li></ul>|

## <a name="subscription-phase-3"></a>订阅 (阶段 3) 

**适用于：** 拥有 Office 365 租户的所有客户托管在 Microsoft 云德国 (MCD) 

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 将转移订阅，并重新分配许可证。 | 相应的 Office 365 全局服务订阅在已转移的 Microsoft 云德国订阅的 Office 365 全局实例中购买。 分配有 Microsoft 云德国许可证的用户将在 Office 365 全局实例中分配许可证。 旧版 Microsoft 云德国订阅在完成后从 Office 365 服务租户中删除。| <ul><li>将阻止对现有订阅的更改 (例如，在此阶段中，不会) 订阅购买或席位计数更改。</li><li>许可证分配更改将被阻止。</li><li>Microsoft 云德国订阅将迁移到相应的 Office 365 全球服务订阅。 该订阅的 Office 365 全局服务由 Microsoft (_也称为_ 产品/服务映射) 。</li><li>Office 365 (提供) 计划的功能数量可以大于原始 Microsoft 云德国产品/服务。 Office 365 服务中的用户许可证将等效分配给类似的 Microsoft 云德国 (服务计划) 。 所有用户的用户许可证将自动分配给新功能。 管理员需要执行显式操作以禁用这些许可证（如果需要）。 </li><li>订阅迁移完成后，Office 365 服务和 Microsoft 云德国订阅都将在 Office 365 管理门户中显示，Microsoft 云德国订阅的状态为已取消 _设置。_ </li><li>用户将被重新分配到新的 Office 365 服务订阅的许可证。 依赖 MCD 订阅或 SKU GUID 的任何客户流程都将中断，并且需要通过 Office 365 服务产品进行修订。 </li><li>Office 365 服务中的新订阅将随新术语 (每月/季度/每年) 一起购买，客户将收到 Microsoft 云德国订阅未使用余额按比例退款。 </li><li>不会迁移德国合作伙伴 Microsoft 云租户。 云解决方案提供商客户将迁移到同一合作伙伴的新 Office 365 服务租户下的 Office 365 服务。 客户迁移后，合作伙伴只能从 Office 365 服务租户管理此客户。 </li><li>其他功能 (例如，Microsoft Planner 和 Microsoft Flow) ，除非租户管理员禁用。若要了解如何禁用分配给用户许可证的服务计划，请参阅分配用户许可证时禁用 [对 Microsoft 365 服务的访问权限](disable-access-to-services-while-assigning-user-licenses.md)。</li></ul> |
||||

## <a name="sharepoint-online-phase-4"></a>SharePoint Online (阶段 4) 

**适用于：** 使用 SharePoint Online 的所有客户

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-----|:-------|
| SharePoint 和 OneDrive 已转换 | 在此阶段，SharePoint Online 和 OneDrive for Business 从 Microsoft 云德国迁移到 Office 365 全局服务。<br><ul><li>保留现有的 Microsoft 云德国 URL (例如 `contoso.sharepoint.de` ，) 。</li><li>保留现有网站。</li><li>由 Microsoft 云德国或 Office 365 全局服务实例中的安全令牌服务 (STS) 颁发的客户端身份验证令牌在转换期间有效。</li></ul>|<ul><li>迁移期间，内容将在两个短暂时段内为只读。 在此期间，需要 SharePoint 中的"无法编辑内容"横幅。</li><li>搜索索引不会保留，可能需要最多 10 天才能重建。</li><li>迁移期间，SharePoint Online 和 OneDrive for Business 内容将在两个短暂时段内为只读。 在此期间，用户将短暂看到"你无法编辑内容"横幅。</li><li>SharePoint Online 迁移完成后，重建索引时，SharePoint Online 和 OneDrive for Business 内容的搜索结果可能不可用。 在此期间，搜索查询可能不会返回完整结果。 重建索引完成时，依赖搜索索引的功能（如 SharePoint Online 新闻）可能会受到影响。</li></ul>|
||||

其他注意事项：

- 如果组织仍使用 SharePoint 2010 工作流，则它们在 2021 年 12 月 31 日之后将不再运行。 SharePoint 2013 工作流仍受支持，尽管新租户默认从 2020 年 11 月 1 日关闭。 迁移到 SharePoint Online 服务完成后，建议您移动到 Power Automate 或其他受支持的解决方案。

- SharePoint Online 实例尚未迁移的 Microsoft 云德国客户需要留在 SharePoint Online PowerShell 模块/Microsoft.SharePointOnline.CSOM 版本 16.0.20616.12000 或以下。 否则，通过 PowerShell 或客户端对象模型连接到 SharePoint Online 将失败。

- 迁移 SharePoint Online 实例的 Microsoft 云德国客户必须将 SharePoint Online PowerShell 模块/Microsoft.SharePointOnline.CSOM 更新为版本 16.0.20717.12000 或版本。 否则，通过 PowerShell 或客户端对象模型连接到 SharePoint Online 将失败。

## <a name="exchange-online-phase-5"></a>Exchange Online (阶段 5) 

**适用于：** 使用 Exchange Online 的所有客户

如果你使用的是 Exchange Online 混合：Exchange Online 混合管理员必须执行混合配置向导 ( **HCW**) 多次作为此转换的一部分。 请参阅 Exchange [的预工作高级迁移步骤](ms-cloud-germany-transition-add-experience.md#Exchange-Online-before-phase-5)

如迁移准备工作中所述，[](ms-cloud-germany-transition-add-pre-work.md#exchange-online)在迁移步骤 **5** 开始之前，Exchange Online 混合客户需要在"Office 365 Germany"模式下运行最新版本的 Exchange 混合配置向导 (HCW) ，以准备本地配置以迁移到 Office 365 全局服务。

完成迁移阶段 **5** (当消息中心通知发布) 时，您需要再次使用 Office 365 全球范围设置运行 HCW，以将本地系统指向 Office 365 全局服务。 如果使用自定义域，可能需要其他 DNS 更新。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| Exchange Online 邮箱从 Microsoft 云德国移动到 Office 365 全局服务。| Exchange Online 配置将新的德国本地区域添加到转换组织。 Office 365 全局服务区域设置为默认，这使内部负载平衡服务能够将邮箱重新分发到 Office 365 服务中的相应默认区域。 在此转换中，位于 MCD (全局服务) 位于同一组织中，并且可以使用任一 URL 终结点。 |<ul><li>将用户和服务从旧 MCD URL (outlook.office.de) 新 Office 365 服务 URL `https://outlook.office365.com` () 。</li><li>在迁移过程中，用户可能会继续通过旧 MCD URL 访问服务，但需要在迁移完成后停止使用旧 URL。</li><li>用户应过渡到使用全球 Office 门户实现 Office Online 功能， (日历、邮件、人员) 。 在迁移到 Office 365 服务之前，导航到尚未迁移到 Office 365 服务的服务将无法正常工作。 </li><li>迁移Outlook Web App不会提供公用文件夹体验。 </li></ul>|
| 更新自动发现自定义 DNS 设置| 当前指向德国 Microsoft 云的自动发现的客户托管 DNS 设置需要更新，以在 Exchange Online 阶段 5) 阶段完成后引用 Office 365 全局终结点 (。 <br> 指向 CNAME 的现有 DNS 条目autodiscover-outlook.office.de更新为指向autodiscover.outlook.com。 |  通过自动发现将可用性请求和服务发现调用直接指向 Office 365 服务。 迁移完成时，不执行这些 DNS 更新的客户可能会遇到自动发现服务问题。 |
||||

其他注意事项：
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?
-->

- `myaccount.microsoft.com` 仅在第 9 阶段中的租户转换之后才能工作。 在此之前，链接将生成"出错"错误消息。

- 访问Outlook Web App环境中共享邮箱的用户 (例如，MCD 环境中的用户访问全局环境中共享邮箱) 系统将提示用户第二次进行身份验证。 用户必须先进行身份验证并访问其邮箱，然后打开位于 `outlook.office.de` 中的共享邮箱 `outlook.office365.com` 。 当访问在其他服务中托管的共享资源时，他们将需要第二次进行身份验证。

- 对于现有的 Microsoft 云德国客户或过渡中的客户，当使用文件 **> 信息 >** 添加帐户将共享邮箱添加到 Outlook 时，查看日历权限可能会失败 (Outlook 客户端尝试使用 Rest API .) 客户想要添加帐户以查看日历权限，可以添加注册表项，如在 Outlook 中共享日历的用户体验更改中所述，以确保此操作成功。 `https://outlook.office.de/api/v2.0/Me/Calendars` [](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 可以使用组策略在组织范围内部署此注册表项。

- 在迁移阶段，使用 PowerShell cmdlets **New-migrationEndpoint、Set-MigrationEndpoint** 和 **Test-MigrationsServerAvailability** 可能会导致代理 (错误) 。  当仲裁邮箱已迁移到全球，但管理员邮箱未迁移或相反时，会发生此情况。 若要解决此问题，在创建租户 PowerShell 会话时，请使用仲裁邮箱作为 **ConnectionUri** 中的路由提示。 例如：

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

若要了解有关组织在迁移和迁移 Exchange Online 资源后之间的差异，请查看迁移到新德国数据中心区域的 [Office 365](ms-cloud-germany-transition-experience.md)服务期间客户体验信息。

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Exchange Online Protection/安全性和合规性 (阶段 6) 

**适用于：** 使用 Exchange Online 的所有客户<br>

后端 Exchange Online Protection (EOP) 功能将复制到新区域"Germany"。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| Exchange Online 路由和历史邮件详细信息的迁移。 | Exchange Online 支持从外部主机到 Office 365 的路由。 外部 MX 记录将转换为路由到 EOP 服务。 迁移租户配置和历史详细信息。 |<ul><li>Microsoft 管理的 DNS 条目从 Office 365 Germany EOP 更新为 Office 365 服务。</li><li>客户应在 EOP 双写入后等待 30 天，以执行 EOP 迁移。 否则，可能会丢失数据。</li></ul>|
||||

## <a name="skype-for-business-online-phase-7"></a>Skype for Business Online (阶段 7) 

**适用于：** 使用 SharePoint Online 的所有客户

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->
| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 将 Skype for Business 迁移到 Teams。 | 现有 Skype for Business 客户将迁移到欧洲 Office 365 全球服务，然后迁移到 Office 365 服务区域"Germany"中的 Microsoft Teams。 |<ul><li>用户将无法在迁移日期登录到 Skype for Business。 在迁移前 10 天，我们将发帖到管理中心，告知你何时进行迁移，以及何时开始迁移。</li><li> 策略配置已迁移。 </li><li>用户将迁移到 Teams，迁移后将不再拥有 Skype for Business。 </li><li>用户必须已安装 Teams 桌面客户端。 安装将在 10 天内通过 Skype for Business 基础结构上的策略进行，但如果失败，用户仍然需要下载客户端或与受支持的浏览器连接。 </li><li>联系人和会议将迁移到 Teams。</li><li>在服务转换到 Office 365 服务之间的时间服务转换期间，用户将无法登录 Skype for Business，除非客户 DNS 条目已完成。 </li><li>联系人和现有会议将继续用作 Skype for Business 会议。 </li><li>PowerShell 将用于管理租户和用户的设置和策略。 连接到 PowerShell 会话时，添加以下内容： <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"`</li></ul>|
||||

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (阶段 8) 

**适用于：** 使用 Microsoft Dynamics 365 的所有客户

使用 Dynamics 365 的客户需要额外的参与度，以独立迁移组织的 Dynamics 组织。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| Microsoft Dynamics 资源 | 使用 Microsoft Dynamics 的客户将参与 Microsoft 工程或 Microsoft FastTrack，以将 Microsoft Dynamics 365 转换为 Office 365 全局服务实例。* |<ul><li>迁移后，管理员验证组织。 <</li><li>管理员在必要时修改工作流。 </li><li>管理员会在适当时清除 AdminOnly 模式。</li><li>管理员根据情况从 _沙_ 盒更改组织类型</li><li>通知最终用户新 URL，以访问组织 (实例) 。</li><li>更新到新终结点 URL 的任何入站连接。 </li><li>在转换期间，Dynamics 服务将不可用。 </li><li>用户需要在每个组织迁移后验证组织运行状况和功能。</li></ul>|
|||||

\* () Microsoft Dynamics 365 的客户必须按照提供的迁移过程定义，在此迁移方案中采取措施。  (ii) 操作失败将意味着 Microsoft 无法完成迁移。  (iii) 如果 Microsoft 由于客户的不作为无法完成迁移，则客户的订阅将于 2021 年 10 月 29 日到期。

## <a name="power-bi-phase-8-of-9"></a>Power BI (阶段 8/9) 

**适用于：** 所有使用 Microsoft Power BI (PBI) 

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| Power BI 资源的迁移 | 使用 Microsoft Power BI (PBI) 的客户将在手动触发现有 PBI 迁移工具以将 Power BI 转换为 Office 365 全局服务实例后由 Microsoft 工程或 Microsoft FastTrack 参与。\*\* |<ul><li>以下 Power BI 项目 _将不会_ 转换，并且必须重新创建：<</li><li>实时数据集 (流式处理或推送) 。 </li><li>Power BI 本地数据网关配置和数据源。 </li><li>基于实时数据集构建的报告在迁移后将不可用，需要重新创建。 </li><li>Power BI 服务在转换期间将不可用。 服务的不可用时间不应超过 24 小时。</li><li>迁移后，用户需要使用 Power BI 服务重新配置数据源及其本地数据网关。  在执行此操作之前，用户将无法使用这些数据源来针对这些数据源执行计划刷新和/或直接查询。 </li><li>无法迁移容量和高级工作区。 客户需要在迁移之前删除所有容量，在迁移后重新创建它们。 将工作区移回所需的容量。</li></ul>  |
||||

\*\* (我) Microsoft Power BI 的客户必须按照提供的迁移过程定义，在此迁移方案中采取措施。  (ii) 操作失败将意味着 Microsoft 无法完成迁移。  (iii) 如果 Microsoft 由于客户的不作为无法完成迁移，则客户的订阅将于 2021 年 10 月 29 日到期。

## <a name="office-apps"></a>Office 应用

**适用于：** 使用 Office 桌面应用程序的所有客户 (Word、Excel、PowerPoint、Outlook、...) 

迁移到区域"Germany"的 Office 365 租户要求所有用户在租户迁移达到阶段 9 后关闭、从 Office 365 注销并返回所有 Office 桌面应用程序 (Word、Excel、PowerPoint、Outlook 等 ) 和 OneDrive for Business 客户端。 通过退出和登录，Office 服务可以获取来自全局 Azure AD 服务的新身份验证令牌。

| 步骤 (步骤)  | 说明 | 影响 |
|:-------|:-------|:-------|
| 客户端、Office Online（Office 客户端转换期间）和 Azure AD 完成租户范围以指向 Office 365 服务。 | 此配置更改使 Office 客户端能够更新并指向 Office 365 服务终结点。 | <ul><li>通知用户关闭 _所有_ Office 应用，然后重新登录 (或强制客户端重新启动，并强制用户登录) 以使 Office 客户端能够选取更改。 </li><li>通知用户和技术支持人员，用户可能会看到一个 Office 横幅，提示他们在转换后 72 小时内重新激活 Office 应用。 </li><li>个人计算机上的所有 Office 应用程序必须关闭，用户必须注销，然后重新登录。 在黄色激活栏中，登录以针对 Office 365 服务重新激活。</li><li>共享计算机需要类似于个人计算机的操作，并且不需要特殊过程。 </li><li>在移动设备上，用户必须注销应用，关闭应用，然后重新登录。 </li></ul>|
||||

## <a name="office-services"></a>Office 服务

Office 中最近 (MRU) 服务是从 MCD 转换到 Office 365 全局服务，而不是迁移。 从 Office 365 全局服务端迁移后，只有 OFFICE 365 全局服务端中的 MRU 链接Office.com可见。 MCD 中的 MRU 链接在 Office 365 全局服务中作为 MRU 链接不可见。 在 Office 365 全局服务中，MRU 链接仅在租户迁移到达阶段 9 之后才能访问。

## <a name="next-step"></a>后续步骤

[执行其他预工作](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>更多信息

入门：

- [从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移期间客户体验](ms-cloud-germany-transition-experience.md)

在转换过程中移动：

- [其他预工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)[和 AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
