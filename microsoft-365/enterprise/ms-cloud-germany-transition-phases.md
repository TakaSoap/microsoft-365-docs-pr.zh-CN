---
title: '迁移阶段操作和影响从 Microsoft 云德国迁移 (常规) '
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 01/26/2021
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
ms.openlocfilehash: 1da3ff6b3347d0e996b017aa1f6243fd724ffccd
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454403"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>迁移阶段操作和影响从 Microsoft 云德国迁移 (常规) 

从 Microsoft 云德国到 Microsoft Office 365 服务德国地区的租户迁移作为一组阶段及其针对每个工作负载的配置操作执行。 此图显示了迁移到新的德国数据中心的九个阶段。

![迁移到新德国数据中心的九个阶段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

阶段及其操作可确保将关键数据和体验迁移到 Office 365 服务。 将租户添加到迁移队列后，每个工作负载都将作为在后端服务上执行的一组步骤完成。 某些工作负载可能需要管理员或 (用户) 操作，或者迁移可能会影响执行和在如何组织迁移中讨论的阶段的 [使用情况？](ms-cloud-germany-transition.md#how-is-the-migration-organized)

以下各节包含迁移各个阶段中工作负荷的操作和效果。 查看表并确定哪些操作或效果适用于您的组织。 确保您已准备好按需要执行各个阶段中的步骤。 未能完成必要的步骤可能会导致服务中断，并可能延迟到 Office 365 服务的迁移完成。

## <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (阶段 4/9) 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| SharePoint 和 OneDrive 已转换。 | 在此阶段，SharePoint 和 OneDrive 从 Microsoft 云德国迁移到 Office 365 服务。 保留现有的 Microsoft 云德国 URL (例如 `contoso.sharepoint.de` ，) 。 由 Microsoft 云德国或 Office 365 服务颁发的令牌在转换期间有效。 | SharePoint 客户 | - 迁移期间，内容将在两个短暂时段内为只读。 在此期间，期望 SharePoint 中显示"无法编辑内容"横幅。 <br><br> - 不会保留搜索索引，可能需要最多 10 天才能重建。 <br><br> - 迁移期间，SharePoint/OneDrive 内容将在两个短暂时段内为只读。 在此期间，用户将短暂看到"你无法编辑内容"横幅。 <br><br> - 重建索引时，搜索索引可能不可用。 在此期间，搜索查询可能不会返回完整结果。 <br><br> - 保留现有网站。 |
|||||

其他注意事项：

- 在将 SharePoint Online 迁移到德国区域之后，会重新生成数据索引。 重建索引完成时，依赖搜索索引的功能可能会受到影响。

- 如果组织仍使用 SharePoint 2010 工作流，则它们在 2021 年 12 月 31 日之后将不再运行。 SharePoint 2013 工作流仍受支持，尽管新租户默认从 2020 年 11 月 1 日关闭。 迁移到 SharePoint Online 服务完成后，建议您移动到 Power Automate 或其他受支持的解决方案。

- 完成到德国地区的 OneDrive 迁移后，将重新生成数据索引。 当重建索引进行时，依赖搜索索引的功能可能会受到影响。

- SharePoint Online 实例尚未迁移的 Microsoft 云德国客户需要留在 SharePoint Online PowerShell 模块/Microsoft.SharePointOnline.CSOM 版本 16.0.20616.12000 或以下。 否则，通过 PowerShell 或客户端对象模型连接到 SharePoint Online 将失败。

- 迁移 SharePoint Online 实例的 Microsoft 云德国客户必须将 SharePoint Online PowerShell 模块/Microsoft.SharePointOnline.CSOM 更新到版本 16.0.20717.12000 或版本以上。 否则，通过 PowerShell 或客户端对象模型连接到 SharePoint Online 将失败。


## <a name="exchange-online-phase-5-of-9"></a>Exchange Online (阶段 5/9) 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 新的德国区域将添加到现有组织设置中，邮箱将移动到 Office 365 服务。 | Exchange Online 配置将新的德国本地区域添加到转换组织。 此 Office 365 服务区域设置为默认区域，这使内部负载平衡服务能够将邮箱重新分发到 Office 365 服务中的相应默认区域。 在此转换中，位于德国 (Office 365 服务) 位于同一组织中，并且可以使用任一 URL 终结点。 | Exchange Online | - 将用户和服务从旧德国 URL (outlook.office.de) 到新的 Office 365 服务 URL `https://outlook.office365.com` () 。 <br><br> - 在迁移过程中，用户可能会继续通过旧版德国 URL 访问服务，但需要在迁移完成后停止使用旧 URL。 <br><br> - 用户应转换为使用全球 Office 门户实现 Office Online 功能 (日历、邮件、人员) 。 在迁移到 Office 365 服务之前，导航到尚未迁移到 Office 365 服务的服务将无法正常工作。 <br><br> - Outlook Web App迁移期间不提供公用文件夹体验。 |
| 更新自动发现自定义 DNS 设置| 当前指向德国 Microsoft 云的自动发现的客户托管 DNS 设置需要进行更新，以在 Exchange Online 阶段 (阶段完成后指向 Office 365) 。 <br> 指向 CNAME 的现有 DNS 条目autodiscover-outlook.office.de更新为指向autodiscover.outlook.com。 | Exchange Online | 通过自动发现将可用性请求和服务发现调用直接指向 Office 365 服务。 迁移完成时，不执行这些 DNS 更新的客户可能会遇到自动发现服务问题。 |
|||||

其他注意事项：

- `myaccount.msft.com` 仅在 Office 365 进行转换后才能工作。 在此之前，链接将生成"出错"错误消息。

- 访问Outlook Web App环境中共享邮箱的用户 (例如，德国环境中的用户访问全局环境中共享邮箱) 系统将提示用户第二次进行身份验证。 用户必须先进行身份验证并访问其邮箱，然后打开位于 `outlook.office.de` 中的共享邮箱 `outlook.office365.com` 。 当访问在其他服务中托管的共享资源时，他们将需要第二次进行身份验证。

- 对于现有的 Microsoft 云德国客户或过渡中的客户，当使用文件 **> 信息 >** 添加帐户将共享邮箱添加到 Outlook 时，查看日历权限可能会失败 (Outlook 客户端尝试使用 Rest API .) 要添加帐户以查看日历权限的客户可以添加注册表项，如在 Outlook 中共享日历的用户体验更改中所述，以确保此操作成功。 `https://outlook.office.de/api/v2.0/Me/Calendars` [](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 可以使用组策略在组织范围内部署此注册表项。

- 在迁移阶段，使用 PowerShell cmdlets **New-migrationEndpoint、Set-MigrationEndpoint** 和 **Test-MigrationsServerAvailability** 可能会导致代理 (错误) 。  当仲裁邮箱已迁移到全球，但管理员邮箱未迁移或相反时，会发生此情况。 若要解决此问题，在创建租户 PowerShell 会话时，请使用仲裁邮箱作为 **ConnectionUri** 中的路由提示。 例如：`New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- 如果你使用的是 Exchange Online 混合：

    - 作为此转换的一部分，Exchange Online 混合客户 (HCW) 多次执行混合配置向导。 在迁移 **步骤阶段 5** 开始之前，任何 Exchange Online 混合客户都需要在 Office 365 Germany 模式下运行最新版本的 HCW，为迁移到 Office 365 全局部署准备本地配置。 完成迁移阶段 **5** (当消息中心通知发布) 时，您需要针对使用 Office 365 全球设置运行 HCW，以将本地系统指向全局服务。 如果使用自定义域，可能需要其他 DNS 更新。

若要详细了解组织在迁移和迁移 Exchange Online 资源后的差异，请查看迁移到新德国数据中心区域 [Office 365](ms-cloud-germany-transition-experience.md)服务期间客户体验的信息。

## <a name="exchange-online-protection-phase-6-of-9"></a>Exchange Online Protection (阶段 6/9) 

后端 Exchange Online Protection (EOP) 功能将复制到新的德国区域。 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| Exchange Online 路由和历史邮件详细信息的迁移。 | Exchange Online 支持从外部主机到 Office 365 的路由。 外部 MX 记录将转换为路由到 EOP 服务。 迁移租户配置和历史详细信息。 | Exchange Online 客户 | - Microsoft 管理的 DNS 条目从 Office 365 Germany EOP 更新为 Office 365 服务。 <br><br> - 客户应在 EOP 双写入后等待 30 天，以执行 EOP 迁移。 否则，可能会丢失数据。 |
|||||



## <a name="skype-for-business-online-phase-7-of-9"></a>Skype for Business Online (阶段 7/9) 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 将 Skype for Business 迁移到 Teams。 | 现有 Skype for Business 客户将迁移到欧洲 Office 365 服务，然后转换到 Office 365 服务德国地区的 Microsoft Teams。 | Skype for Business 客户 | - 用户将无法在迁移日期登录到 Skype for Business。 在迁移前 10 天，我们将发帖到管理中心，告知你何时进行迁移，以及何时开始迁移。 <br><br> - 策略配置已迁移。 <br><br> - 用户将迁移到 Teams，迁移后将不再拥有 Skype for Business。 <br><br> - 用户必须已安装 Teams 桌面客户端。 安装将在 10 天内通过 Skype for Business 基础结构上的策略进行，但如果失败，用户仍然需要下载客户端或与受支持的浏览器连接。 <br><br> - 联系人和会议将迁移到 Teams。 <br><br> - 在时间服务转换到 Office 365 服务期间，用户将无法登录到 Skype for Business，除非客户 DNS 条目已完成。 <br><br> - 联系人和现有会议将继续用作 Skype for Business 会议。 |
|||||


## <a name="office-apps-phase-8-of-9"></a>Office Apps (阶段 8/9) 

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 客户端、Office Online（Office 客户端转换期间）和 Azure AD 完成租户范围以指向 Office 365 服务。 | 此配置更改使 Office 客户端能够更新并指向 Office 365 服务终结点。 | 所有 Office 客户 | - 通知用户关闭 _所有_ Office 应用，然后重新登录 (或强制客户端重新启动，并强制用户登录) 以允许 Office 客户端选取更改。 <br><br> - 通知用户和技术支持人员，用户可能会看到一个 Office 横幅，提示他们在转换后 72 小时内重新激活 Office 应用。 <br><br> - 个人计算机上的所有 Office 应用程序必须关闭，用户必须注销，然后重新登录。 在黄色激活栏中，登录以针对 Office 365 服务重新激活。 <br><br> - 共享计算机需要类似于个人计算机的操作，并且不需要特殊过程。 <br><br> - 在移动设备上，用户必须注销应用、关闭应用，然后重新登录。 |
|||||


## <a name="office-services"></a>Office 服务

Office 中最近 (MRU) 服务是从德国服务到 Office 365 服务的转换，而不是迁移。 从 Office 365 服务端迁移后，只有 OFFICE 365 服务端中的 MRU 链接Office.com可见。 来自德国服务的 MRU 链接在 Office 365 服务中作为 MRU 链接不可见。 在 Office 365 中，只有租户迁移完成后，才能访问 MRU 链接。

## <a name="subscription"></a>订阅

| 步骤 (步骤)  | 说明 | 适用于 | 影响 |
|:-------|:-----|:-------|:-------|
| 未经同意，我们无法迁移客户。 | Microsoft 通过以下两种方式之一获得迁移权，这使 Microsoft 能够协调数据和服务到 Office 365 服务实例的转换。 <br> 管理员选择加入 Microsoft 驱动的迁移。 <br> 客户在 2020 年 5 月 1 日之后续订其 Microsoft 云德国租户的任何订阅。 我们将每月通知这些客户迁移，等待 30 天，让客户有机会取消迁移，然后直接选择加入，在 ICM 中跟踪。 | 所有 Office 客户 | - 租户标记为已同意迁移，管理中心显示确认。 <br><br> - 确认将发布至德国云消息中心租户。 服务配置将继续从 Microsoft 云德国终结点进行。 <br><br> - 监视消息中心，获取迁移阶段状态更新。 |
| 将转移订阅，并重新分配许可证。 | 租户转换为 Office 365 服务后，会为转移的 Microsoft 云德国订阅购买相应的 Office 365 服务订阅。 分配有 Microsoft 云德国许可证的用户将被分配 Office 365 服务许可证。 旧版 Microsoft 云德国订阅在完成后从 Office 365 服务租户中删除。 | 所有 Office 客户 | - 将阻止对现有订阅的更改 (例如，在此阶段中，不会) 订阅购买或席位计数更改。 <br><br> - 将阻止许可证分配更改。 <br><br> - Microsoft 云德国订阅将迁移到相应的 Office 365 服务订阅。 该订阅的 Office 365 服务由 Microsoft (_也称为_ 产品/服务映射) 。 <br><br> - Office 365 (提供) 计划的功能数量可以大于原始 Microsoft 云德国产品/服务。 Office 365 服务中的用户许可证将等效分配给类似的 Microsoft 云德国 (服务计划) 。 所有用户的用户许可证将自动分配给新功能。 管理员需要执行显式操作以禁用这些许可证（如果需要）。 <br><br> - 订阅迁移完成后，Office 365 服务和 Germany 订阅都将在 Office 365 管理门户中显示，并且德国订阅的状态为"已取消 _设置"。_ <br><br> - 将重新分配绑定到新 Office 365 服务订阅的用户许可证。 任何依赖德国订阅或 SKU GUID 的客户流程都将中断，并且需要通过 Office 365 服务产品进行修订。 <br><br> - Office 365 服务中的新订阅将随新术语 (每月/季度/每年) 一起购买，客户将收到 Microsoft 云德国订阅未使用余额按比例退款。 <br><br> - 不会迁移德国合作伙伴 Microsoft 云租户。 云解决方案提供商客户将迁移到同一合作伙伴的新 Office 365 服务租户下的 Office 365 服务。 客户迁移后，合作伙伴只能从 Office 365 服务租户管理此客户。 <br><br> - 其他功能 (例如，Microsoft Planner 和 Microsoft Flow) ，除非租户管理员禁用。若要了解如何禁用分配给用户许可证的服务计划，请参阅在分配用户许可证时禁用对 [Microsoft 365 服务的访问权限](disable-access-to-services-while-assigning-user-licenses.md)。  |
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
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)[和 AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
