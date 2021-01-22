---
title: '迁移阶段操作和影响从 Microsoft 云德国 (一般) '
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
description: 摘要：了解从德国 Microsoft 云 (德国 Microsoft 云) 迁移到新的德国数据中心地区的 Office 365 服务的迁移阶段操作和影响。
ms.openlocfilehash: f0c81813522be1f9d759980df98995f1adb261c5
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921618"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>迁移阶段操作和影响从 Microsoft 云德国 (一般) 

从德国 Microsoft 云到 Microsoft Office 365 服务的德国地区的租户迁移作为一组阶段及其针对每个工作负载的配置操作执行。 此图显示了迁移到新的德国数据中心的九个阶段。

![迁移到新德国数据中心的九个阶段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

阶段及其操作可确保将关键数据和体验迁移到 Office 365 服务。 将租户添加到迁移队列后，每个工作负载都将作为在后端服务上执行的一组步骤完成。 某些工作负载可能需要管理员或 (用户) 操作，或者迁移可能会影响执行和在如何组织迁移中讨论的阶段的 [使用情况？](ms-cloud-germany-transition.md#how-is-the-migration-organized)

以下各节包含迁移各个阶段中工作负荷的操作和效果。 查看这些表并确定哪些操作或效果适用于您的组织。 确保你已准备好按需要执行各个阶段中的步骤。 未能完成必要的步骤可能会导致服务中断，并可能延迟到 Office 365 服务的迁移完成。

## <a name="exchange-online"></a>Exchange Online

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 新的德国区域将添加到现有组织设置中，邮箱将移动到 Office 365 服务。 | Exchange Online 配置将新的德国本地区域添加到转换组织。 此 Office 365 服务区域设置为默认区域，这使内部负载平衡服务能够将邮箱重新分发到 Office 365 服务中的相应默认区域。 在此转换中，位于德国 (Office 365 服务) 位于同一组织中，并且可以使用任一 URL 终结点。 | Exchange Online | - 将用户和服务从德国 URL 转换为 Office 365 服务 URL `https://outlook.office365.com` () 。 <br><br> - 迁移期间，用户将继续通过旧版德国 URL 访问服务。 无需立即操作。 <br><br> - 用户应开始使用 Office Online office.com门户， (日历、邮件、人员) 。 在迁移之前，导航到尚未迁移到 Office 365 服务的服务将无法正常工作。 <br><br> - Outlook Web App迁移期间不提供公用文件夹体验。 |
|||||

其他注意事项：

- `myaccount.msft.com` 仅在 Office 365 进行切换后才能工作。 到该时间之前，链接将生成"出错"错误消息。

- 访问Outlook Web App环境中共享邮箱的用户 (例如，德国环境中的用户访问全局环境中共享邮箱) 系统将提示用户第二次进行身份验证。 用户必须先进行身份验证并访问其邮箱， `outlook.office.de` 然后打开位于 中的共享邮箱 `outlook.office365.com` 。 当访问在其他服务中托管的共享资源时，他们将需要第二次进行身份验证。

- 对于现有 Microsoft 云德国客户或过渡中的客户，当使用文件 **> 信息 >** 添加帐户将共享邮箱添加到 Outlook 时，查看日历权限可能会失败 (Outlook 客户端尝试使用 Rest API .) 要添加帐户以查看日历权限的客户可以添加注册表项，如在 Outlook 中共享日历的用户体验更改中所述，以确保此操作 `https://outlook.office.de/api/v2.0/Me/Calendars` 成功 [](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec)。 可以使用组策略在组织范围内部署此注册表项。

- 在迁移阶段，使用 PowerShell cmdlets **New-migrationEndpoint、Set-MigrationEndpoint** 和 **Test-MigrationsServerAvailability** 可能会导致代理 (错误) 。  当仲裁邮箱已迁移到全球，但管理员邮箱没有或相反的情况时，会发生此情况。 若要解决此问题，在创建租户 PowerShell 会话时，请使用仲裁邮箱作为 **ConnectionUri** 中的路由提示。 例如：`New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- 如果你使用的是 Exchange Online 混合：

    - 您必须重新运行混合配置向导 (HCW) 才能在转换之前针对 Microsoft 云德国更新本地配置，在清理 Office 365 服务后重新运行 HCW。 如果使用自定义域，可能需要其他 DNS 更新。

若要详细了解组织在迁移和迁移 Exchange Online 资源后的区别，请查看迁移到新的德国数据中心区域的 [Office 365](ms-cloud-germany-transition-experience.md)服务期间客户体验的信息。

## <a name="exchange-online-protection"></a>Exchange Online Protection

后端 Exchange Online Protection (EOP) 功能复制到新的德国区域。 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| Exchange Online 路由和历史邮件详细信息的迁移。 | Exchange Online 支持从外部主机到 Office 365 的路由。 外部 MX 记录将转换为路由到 EOP 服务。 迁移租户配置和历史详细信息。 | Exchange Online 客户 | - Microsoft 管理的 DNS 条目从 Office 365 Germany EOP 更新到 Office 365 服务。 <br><br> - 客户应在 EOP 双写入后等待 30 天，以执行 EOP 迁移。 否则，可能会丢失数据。 |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| SharePoint 和 OneDrive 已转换。 | 在此阶段，SharePoint 和 OneDrive 从 Microsoft 云德国迁移到 Office 365 服务。 保留现有的 Microsoft 云德国 URL (例如 `contoso.sharepoint.de` ，) 。 由德国 Microsoft 云或 Office 365 服务颁发的令牌在转换期间有效。 | SharePoint 客户 | - 迁移期间，内容将在两个简短时段内为只读。 在此期间，预期 SharePoint 中会显示"无法编辑内容"横幅。 <br><br> - 不会保留搜索索引，可能需要 10 天才能重新生成。 <br><br> - 迁移期间，SharePoint/OneDrive 内容将在两小段时间内为只读。 在此期间，用户将短暂看到"你无法编辑内容"横幅。 <br><br> - 重建索引时，搜索索引可能不可用。 在此期间，搜索查询可能不会返回完整结果。 <br><br> - 保留现有网站。 |
|||||

其他注意事项：

- 在将 SharePoint Online 迁移到德国区域之后，会重新生成数据索引。 重建索引完成时，依赖搜索索引的功能可能会受到影响。

- 如果组织仍使用 SharePoint 2010 工作流，则它们在 2021 年 12 月 31 日之后将不再运行。 SharePoint 2013 工作流仍受支持，尽管新租户默认从 2020 年 11 月 1 日关闭。 迁移到 SharePoint Online 服务完成后，建议迁移到 Power Automate 或其他受支持的解决方案。

- OneDrive 迁移到德国区域后，将重新生成数据索引。 当重建索引进行时，依赖搜索索引的功能可能会受到影响。

- 尚未迁移 SharePoint Online 实例的 Microsoft 云德国客户需要留在 SharePoint Online PowerShell 模块/Microsoft.SharePointOnline.CSOM 版本 16.0.20616.12000 或以下。 否则，通过 PowerShell 或客户端对象模型连接到 SharePoint Online 将失败。

- 迁移 SharePoint Online 实例的德国 Microsoft 云客户必须将 SharePoint Online PowerShell 模块/Microsoft.SharePointOnline.CSOM 更新为版本 16.0.20717.12000 或版本。 否则，通过 PowerShell 或客户端对象模型连接到 SharePoint Online 将失败。


## <a name="skype-for-business-online"></a>Skype for Business Online

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 将 Skype for Business 迁移到 Teams。 | 现有 Skype for Business 客户将迁移到欧洲 Office 365 服务，然后转换到 Office 365 服务德国地区的 Microsoft Teams。 | Skype for Business 客户 | - 用户将无法在迁移日期登录到 Skype for Business。 在迁移前 10 天，我们将发帖到管理中心，告知你何时进行迁移，以及何时开始迁移。 <br><br> - 迁移策略配置。 <br><br> - 用户将迁移到 Teams，迁移后将不再拥有 Skype for Business。 <br><br> - 用户必须已安装 Teams 桌面客户端。 安装将在 10 天内通过 Skype for Business 基础结构上的策略进行，但如果失败，用户仍然需要下载客户端或与受支持的浏览器连接。 <br><br> - 联系人和会议将迁移到 Teams。 <br><br> - 在时间服务转换到 Office 365 服务期间，用户将无法登录 Skype for Business，除非客户 DNS 条目已完成。 <br><br> - 联系人和现有会议将继续用作 Skype for Business 会议。 |
|||||

## <a name="office-services"></a>Office 服务

Office 中最近 (MRU) 服务是从德国服务到 Office 365 服务的转换，而不是迁移。 从 Office 365 服务端迁移后，只有来自 Office 365 服务端OFFICE.COM可见。 来自德国服务的 MRU 链接在 Office 365 服务中作为 MRU 链接不可见。 在 Office 365 中，只有租户迁移完成后，才能访问 MRU 链接。

## <a name="subscription"></a>订阅

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 未经同意，我们无法迁移客户。 | Microsoft 通过以下两种方式之一获得迁移权，这使 Microsoft 能够安排数据和服务到 Office 365 服务实例的转换。 <br> 管理员选择加入 Microsoft 驱动的迁移。 <br> 客户在 2020 年 5 月 1 日之后续订其 Microsoft 云德国租户的任何订阅。 我们每月会通知这些客户迁移，等待 30 天，让客户有机会取消迁移，然后直接选择加入，在ICM。 | 所有 Office 客户 | - 租户标记为已同意迁移，并且管理中心显示确认。 <br><br> - 确认将张贴到德国云消息中心租户。 服务配置从德国 Microsoft 云终结点继续。 <br><br> - 监视消息中心，获取有关迁移阶段状态的更新。 |
| 将转移订阅，并重新分配许可证。 | 租户转换为 Office 365 服务后，会为已转移的 Microsoft 云德国订阅购买相应的 Office 365 服务订阅。 已分配有德国 Microsoft 云许可证的用户将被分配 Office 365 服务许可证。 旧版 Microsoft 云德国订阅在完成时从 Office 365 服务租户中删除。 | 所有 Office 客户 | - 将阻止对现有订阅的更改 (例如，在此阶段不会) 订阅购买或席位计数更改。 <br><br> - 将阻止许可证分配更改。 <br><br> - Microsoft 云德国订阅将迁移到相应的 Office 365 服务订阅。 该订阅的 Office 365 服务由 Microsoft (也称为产品/服务映射) 。 <br><br> - Office 365 (提供) 计划的功能数量可以大于原始 Microsoft 云德国产品/服务。 Office 365 服务中的用户许可证将等效分配给类似的 Microsoft 云德国功能 (服务计划) 。 所有用户的用户许可证将自动分配给新功能。 如果需要，管理员需要执行显式操作来禁用这些许可证。 <br><br> - 订阅迁移完成后，Office 365 服务和 Germany 订阅都将在 Office 365 管理门户中显示，并取消设置德国订阅 _的状态_。 <br><br> - 将重新分配绑定到新 Office 365 服务订阅的许可证。 任何依赖德国订阅或 SKU GUID 的客户流程都将中断，并且需要通过 Office 365 服务产品/服务进行修订。 <br><br> - Office 365 服务中的新订阅将按新术语 (每月/季度/每年) 购买，客户将收到 Microsoft 云德国订阅未使用余额按比例退款。 <br><br> - 不会迁移德国 Microsoft 云合作伙伴租户。 云解决方案提供商客户将迁移到同一合作伙伴的新 Office 365 服务租户下的 Office 365 服务。 客户迁移后，合作伙伴只能从 Office 365 服务租户管理此客户。 <br><br> - 其他功能 (例如，Microsoft Planner 和 Microsoft Flow) ，除非租户管理员禁用。若要了解如何禁用分配给用户许可证的服务计划，请参阅分配用户许可证时禁用 [对 Microsoft 365 服务的访问权限](disable-access-to-services-while-assigning-user-licenses.md)。  |
|||||

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
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
