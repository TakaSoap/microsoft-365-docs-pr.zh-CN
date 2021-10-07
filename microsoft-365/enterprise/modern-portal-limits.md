---
title: SharePoint联机新式门户网站限制
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
description: 了解 SharePoint Online 中新式网站的性能建议，例如限制对 SharePoint 和外部终结点的调用。
ms.openlocfilehash: 6d09af30f5bdc8866b44047771060ced86362565
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60214185"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePoint联机新式门户网站限制

本文为 SharePoint Online 中的新式门户网站提供了性能建议。 使用本文中的指南优化新式门户网站性能并避免常见的性能问题。

## <a name="performance-considerations-for-modern-portal-sites"></a>新式门户网站的性能注意事项

从性能优化的角度看，新式门户网站具有一些独特之处。 SharePoint Online 中协作和门户网站之间的主要区别在于规模。 通常，与协作网站相比，门户网站向更多的用户提供页面视图，并且可能包含更多静态内容和更少的可编辑资源。 此外，新式网站的体系结构与经典网站的体系结构不同，因为呈现页面和执行代码所涉及的大部分处理都发生在客户端而不是服务器上。

新式门户网站的性能优化主要侧重于几个总体目标：

- 减小每个网站页面的组件总大小
- 将常见静态文件（如图像、样式表和脚本）的托管卸载到CDN
- 仅SharePoint终结点和外部终结点的调用
- 避免对相同内容重复请求

本文中的许多指南侧重于最大程度地减少和优化对 SharePoint Online 的调用。 每次加载页面时重复调用将影响用户的性能，因为每次从服务检索信息时，即使信息未发生更改。 因此，对SharePoint的请求可以归为所有用户的常见呼叫或每个用户所需的呼叫。 应缓存这两个呼叫类别的结果，以优化用户体验。

>[!NOTE]
>使用[适用于](./page-diagnostics-for-spo.md)SharePoint 的页面诊断工具作为起点来分析 SharePoint Online 网站页面上的特定性能指标。

## <a name="modern-portal-site-limits-and-recommendations"></a>新式门户网站限制和建议

|**限制**|**建议的最大值**|**备注**|
|:-----|:-----|:-----|:-----|
|页面和新闻项  <br/> |每个网站 5,000 个  <br/> |我们建议将新式门户网站中的页面和新闻项数量限制在 5，000 以下。  <br/> |
|页面上的 Web 部件  <br/> |每页 20 个  <br/> |我们建议每个页面使用 20 个或更少的 Web 部件，包括开箱即用 Microsoft Web 部件和自定义 Web 部件。 <br/> 有关详细信息，请参阅优化 SharePoint [Online 新式网站页面中的 Web 部件性能](modern-web-part-optimization.md)。  <br/> |
|页面上的动态 Web 部件  <br/> |每页 4 个  <br/> |对要获取最新数据SharePoint查询的动态 Web 部件应限制为每页 4 个。 新闻 Web 部件是动态 Web 部件的示例。 <br/> 有关详细信息，请参阅优化 SharePoint [Online 新式网站页面中的 Web 部件性能](modern-web-part-optimization.md)。    <br/> |
|安全组  <br/> |每个站点 20 个  <br/> |安全组的数量会影响新式门户网站中许多查询的规模。 建议您将安全组的数量限制为尽可能小一组，每个网站不超过 20 个。  <br/> |
|网站导航中的项目  <br/> |每个站点 100 个  <br/> |我们建议向网站导航中添加少于 100 个项目，并且使用开箱即用导航控件。  <br/> 有关详细信息，请参阅优化[SharePoint Online 新式网站页面中的页面权重](modern-page-weight-optimization.md)。 <br/> |
|最大图像大小  <br/> |每个图像 300 Kb  <br/> |我们建议将图像大小限制在 300kb 或更小，CDN用于托管图像、样式表和脚本。 <br/>有关详细信息，请参阅优化[SharePoint Online](modern-image-optimization.md)新式网站页面中的图像和使用 Office 365 内容分发网络 (CDN) [Online SharePoint图像](use-microsoft-365-cdn-with-spo.md)。  <br/> |
|具有编辑权限的用户  <br/> |每个网站 200 个用户  <br/> |SharePoint门户网站已针对查看和使用内容进行了优化。 门户上的编辑权限应限制为受限的一组用户，因为编辑权限会下载其他控件，因此这些用户的执行速度将会变慢。 因此，具有编辑权限的用户过多会影响整体体验。 <br/> |
|第三方 iFrame  <br/> |每页 2 个  <br/> |iFrame 的速度不可预测，因为它们加载一个单独的外部页面，包括所有关联的内容，如 javascript、CSS 和框架元素。 如果必须使用 iFrame，请限制其数量为每页 2 个或更少。<br/> 有关详细信息，请参阅优化[SharePoint Online 新式和经典发布网站页面中的 iFrame。](modern-iframe-optimization.md) <br/> |
|对 UPA 服务的呼叫  <br/> |每个用户每小时 1 个  <br/> |建议您不要对 UPA _或 User_ Profile Application (服务进行) 调用。 [Microsoft Graph API](/graph/call-api)和[PageContext](/javascript/api/sp-page-context/pagecontext)可用于查询用户信息。  <br/> 如果需要 UPA 服务调用，请在必要时进行一次调用，然后缓存信息以在同一会话中重复使用。 |
|对分类服务的调用  <br/> |每个用户每小时 5 个  <br/> |建议您不要对分类 _服务_ 进行每个请求调用。 如果需要分类服务调用，请缓存信息以在同一会话中重复使用。 <br/> 有关详细信息，请参阅优化[SharePoint Online 新式和经典发布网站页面中的页面调用](modern-page-call-optimization.md)。 <br/> |

## <a name="related-topics"></a>相关主题

[创建正常的SharePoint门户](/sharepoint/portal-health)

[优化 SharePoint Online 性能](tune-sharepoint-online-performance.md)

[优化 Office 365 性能](tune-microsoft-365-performance.md)

[SharePoint Online 限制](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[新式 SharePoint 体验中的性能](/sharepoint/modern-experience-performance)

[SharePoint Online 门户性能指南](/sharepoint/dev/solution-guidance/portal-performance)
