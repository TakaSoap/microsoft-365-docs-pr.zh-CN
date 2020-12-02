---
title: 迁移阶段的操作和影响
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 摘要：了解在 microsoft 云德国) 到新的德国数据中心区域中的 Office 365 服务中 (移动的迁移阶段的操作和影响。
ms.openlocfilehash: 9ffdb0bbe60bdb96d6e110ac08cba4030272c7e9
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551653"
---
# <a name="migration-phases-actions-and-impacts"></a>迁移阶段的操作和影响

从 Microsoft 云德国到德国地区的 microsoft Office 365 服务的租户迁移作为一组针对每个工作负荷的配置操作执行。 这些操作可确保关键数据和体验迁移到 Office 365 服务。 将租户添加到迁移队列后，每个工作负荷都将作为在后端服务上执行的一组步骤完成。 某些工作负载可能需要管理员 (或用户) 的操作，否则迁移可能会影响在[迁移迁移的方式](ms-cloud-germany-transition.md#how-is-the-migration-organized)中执行和讨论的阶段的使用情况。

以下各节包含工作负荷在迁移的各个阶段进行过程中的操作和影响。 查看表并确定哪些操作或效果适用于您的组织。 确保您已准备好在需要时执行各自阶段中的步骤。 如果无法完成必要的步骤，可能会导致服务中断，并可能会延迟完成迁移到 Office 365 服务。

## <a name="exchange-online"></a>Exchange Online

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 将新的德国区域添加到现有的组织设置中，并将邮箱移动到 Office 365 服务。 | Exchange Online 配置将新的本地德语区域添加到正在转换的组织中。 此 Office 365 服务区域设置为默认值，这使内部负载平衡服务能够将邮箱重新分配到 Office 365 服务中的相应默认区域。 在此转换中，任何一侧 (德国或 Office 365 服务) 的用户都在同一组织中，并且可以使用 URL 终结点。 | Exchange Online | -将德国 Url 中的用户和服务转换为 Office 365 服务 Url (`https://outlook.office365.com`) 。 <br><br> -在迁移过程中，用户将继续通过旧的德国 Url 访问服务。 无需立即执行任何操作。 <br><br> -用户应开始使用 Office Online 功能的 office.com 门户 (日历、邮件、用户) 。 导航到尚未迁移到 Office 365 服务的服务在迁移之前不会运行。 <br><br> -Outlook Web App 在迁移过程中不会提供公用文件夹体验。 |
|||||

若要详细了解迁移中的组织和迁移 Exchange Online 资源后的差异，请参阅在 [新的德国数据中心区域迁移到 Office 365 服务期间的客户体验](ms-cloud-germany-transition-experience.md)中的信息。

## <a name="exchange-online-protection"></a>Exchange Online Protection

后端 Exchange Online Protection (EOP) 功能将复制到新的德国地区。 

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| Exchange Online 路由和历史邮件详细信息的迁移。 | Exchange Online 支持从外部主机到 Office 365 的路由。 外部 MX 记录转换为路由到 EOP 服务。 迁移租户配置和历史详细信息。 | Exchange Online 客户 | -Microsoft-托管 DNS 条目是从 Office 365 德国 EOP 更新到 Office 365 服务。 <br><br> -客户应在 EOP 双重写入为 EOP 迁移后等待30天。 否则，可能会丢失数据。 |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

<!--

| Step(s) | Description | Applies to | Impact |
|:-------|:-----|:-------|:-------|
| SharePoint and OneDrive are transitioned. | SharePoint and OneDrive are migrated from Microsoft Cloud Deutschland to Office 365 services in this phase. Existing Microsoft Cloud Deutschland URLs are preserved (for example, `contoso.sharepoint.de`). Tokens that were issued by Microsoft Cloud Deutschland or Office 365 services are valid during the transition. | SharePoint customers | - Content will be read-only for two brief periods (less than x minutes) during migration. During this time, expect a "you can't edit content" banner in SharePoint. <br><br> - The search index won't be preserved, and may take up to 10 days to be rebuilt. <br><br> - SharePoint/OneDrive content will be read-only for two brief periods (less than x minutes) during migration. Users will see a "you can't edit content" banner briefly during this time. <br><br> - The search index may be unavailable while the index is rebuilt. During this period, search queries might not return complete results. <br><br> - Existing sites are preserved. |
|||||

--> 

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| SharePoint 和 OneDrive 已转换。 | 在此阶段中，SharePoint 和 OneDrive 将从 Microsoft 云德国迁移到 Office 365 服务。 保留现有的 Microsoft 云德国 Url (例如， `contoso.sharepoint.de`) 。 由 Microsoft 云德国或 Office 365 服务颁发的令牌在转换过程中有效。 | SharePoint 客户 | -在迁移过程中的两个短时间段的内容将为只读。 在这段时间内，预计 SharePoint 中会出现 "无法编辑内容" 标题。 <br><br> -搜索索引不会被保留，可能需要长达10天的时间才能重建。 <br><br> -SharePoint/OneDrive 内容将在迁移过程中的两个简短时段为只读。 在此期间，用户将看到 "你不能编辑内容" 标题。 <br><br> -重建索引时，搜索索引可能不可用。 在此期间，搜索查询可能不会返回完整的结果。 <br><br> -保留现有网站。 |
|||||


## <a name="skype-for-business-online"></a>Skype for Business Online

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 将 Skype for Business 迁移到团队。 | 现有的 Skype for Business 客户将迁移到欧洲的 Office 365 服务，并在 Office 365 服务的德国地区转换为 Microsoft 团队。 | Skype for Business 客户 | -用户将无法在迁移日期登录到 Skype for Business。 迁移前的10天，我们将在 Skype for Business 客户端上通过带内的频带通知最终用户，他们将升级到团队。 我们还将在管理中心发布，这些更改将在10天后发生。 <br><br> -迁移策略配置。 <br><br> -用户将迁移到团队，并且在迁移后将不再拥有 Skype for Business。 <br><br> -用户必须安装了团队桌面客户端。 将通过 Skype for Business 基础结构上的策略在10天内进行安装，但如果此操作失败，则用户仍需下载客户端或使用支持的浏览器进行连接。 <br><br> -联系人和会议将迁移到团队。 <br><br> -用户将无法在时间服务转换到 Office 365 服务时登录到 Skype for Business，不能在客户 DNS 条目完成前登录。 <br><br> -联系人和现有会议将继续充当 Skype for Business 会议。 |
|||||
        
## <a name="subscription"></a>订阅

| 步骤 (s)  | 说明 | 适用对象 | 影响 |
|:-------|:-----|:-------|:-------|
| 未经同意，我们无法迁移客户。 | Microsoft 获得以两种方式之一迁移的权利，这使 Microsoft 能够将数据和服务的转换安排到 Office 365 服务实例。 <br> 管理员将加入到 Microsoft 驱动的迁移中。 <br> 客户在2020年5月1日之后续订其 Microsoft 云德国租户中的任何订阅。 我们将每月向这些客户通知迁移，等待30天，让客户有机会取消，然后直接选择加入，在 ICM 中进行跟踪。 | 所有 Office 客户 | -租户被标记为 "同意迁移"，管理中心将显示 "确认"。 <br><br> -向云德国消息中心租户发布确认。 服务配置将从 Microsoft 云德国终结点继续进行。 <br><br> -监视消息中心以了解有关迁移阶段状态的更新。 |
| 将传输订阅，并重新分配许可证。 | 将租户转换为 Office 365 服务后，将为已迁移的 Microsoft 云德国订阅购买相应的 Office 365 服务订阅。 已分配 Microsoft 云德国许可证的用户将被分配 Office 365 服务许可证。 旧版 Microsoft 云德国订阅将在完成时从 Office 365 服务租户中删除。 | 所有 Office 客户 | -将阻止对现有订阅所做的更改 (例如，在此阶段不会) 购买新订阅或座位计数更改。 <br><br> -将阻止许可证分配更改。 <br><br> -Microsoft 云德国订阅将迁移到相应的 Office 365 服务订阅。 该订阅的 Office 365 服务提供由 Microsoft (定义（也称为 " _提供映射_) "）。 <br><br> -Office 365 服务提供的 (服务计划) 的功能数量可能大于原始 Microsoft 云德国提供的功能。 Office 365 服务中的用户许可证将与类似的 Microsoft 云德国功能 (服务计划) 的功能等效。 所有用户的用户许可证都将自动分配给新功能。 如果需要，管理员需要执行显式操作以禁用这些许可证。 <br><br> -订阅迁移完成后，office 365 服务和德国订阅将在 Office 365 管理门户中可见，并且 "德国订阅" 状态为 " _deprovisioned_"。 <br><br> -将重新分配用户与新的 Office 365 服务订阅相关联的许可证。 对德国订阅或 SKU Guid 具有依赖关系的任何客户流程将会断开，并且需要使用 Office 365 服务产品进行修订。 <br><br> -Office 365 服务中的新订阅将随新术语一起购买， (每月/季度/年度) ，并且客户将收到一份按比例退款的 Microsoft 云德国订阅余额。 <br><br> -不会迁移合作伙伴 Microsoft 云德国租户。 CSP 客户将迁移到同一合作伙伴的新 Office 365 服务租户下的 Office 365 服务。 客户迁移后，合作伙伴只能从 Office 365 服务租户管理此客户。 <br><br> -其他功能可 (例如，Microsoft Planner 和 Microsoft Flow) ，除非租户管理员禁用。有关如何禁用分配给用户许可证的服务计划的信息，请参阅 [在分配用户许可证时禁用对 Microsoft 365 服务的访问](disable-access-to-services-while-assigning-user-licenses.md)。  |
|||||

## <a name="next-step"></a>后续步骤

[执行其他预备工作](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>详细信息

入门：

- [从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移过程中的客户体验](ms-cloud-germany-transition-experience.md)

在转换中移动：

- [其他预备工作](ms-cloud-germany-transition-add-pre-work.md)
- [服务](ms-cloud-germany-transition-add-general.md)、[设备](ms-cloud-germany-transition-add-devices.md)、[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他信息。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
