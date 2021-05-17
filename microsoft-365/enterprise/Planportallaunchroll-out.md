---
title: 在 SharePoint Online 中规划门户启动推出计划
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: 本文介绍了如何在 SharePoint Online 中规划门户启动，以及成功启动要执行的步骤
ms.openlocfilehash: d77baac6209a4002bb1c27513d5ccfdf5c4ac28a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905688"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>在 SharePoint Online 中规划门户启动推出计划

门户是 Intranet 上的一个 SharePoint 网站，其中包含大量使用网站内容的网站查看者。 在大型组织中，可能有几种；例如公司门户和人力资源门户。 通常，门户创建和创作网站及其内容的人员相对较少。 门户的大多数访问者仅读取和使用内容。

本文介绍如何规划部署和推出计划以使用 SharePoint Online。 它还提供了遵循的方法，因为系统不允许在 SharePoint Online 上执行传统负载测试。 SharePoint联机是一项云服务，负载功能、服务负载的运行状况和总体平衡由 Microsoft 管理。

为了帮助创建成功的门户，请遵循创建、启动和维护正常运行的门户中详述的 [指导原则、实践和建议](/sharepoint/portal-health) 

下面重点介绍了部署方法。

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>SharePoint Online 中的容量规划概述
为了高效地使用容量并应对意外增长，在任何服务器场中，我们都有用于跟踪特定使用方案的自动化。 尽管任何一个服务器场中的任一租户的确切增长不可预测，但随着时间的推移，请求总数是可预测的。 通过确定 SharePoint Online 的增长趋势，我们可以规划未来的扩展。 有关 Capacity [planning and load testing SharePoint Online （ 联机容量SharePoint的信息](capacity-planning-and-load-testing-sharepoint-online.md)。

成功启动的关键部分是下面详述的"wave"或"阶段性推出"方法。 

## <a name="can-i-load-test-sharepoint-online"></a>能否加载测试SharePoint Online？
SharePoint联机是一个共享的多租户环境，它跨服务器场进行平衡，并定期调整规模。 负载测试环境（如 SharePoint Online）的扩展会不断更改，不仅会获得意外结果，而且不允许进行。 

了解更多信息[：Capacity planning and load testing SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>按照建议的准则优化页面
本地部署中的页面不应简单地被移动，因为它们位于 SharePoint Online 上，而不根据针对 SharePoint Online 的建议准则进行查看。 最佳方法是始终为 SharePoint 中任何网站或门户优化任何主页，因为这是组织中大多数用户将作为网站网站 (的起点访问) 。

应考虑一些基本因素：
- 本地部署可以利用传统的服务器端缓存，如对象缓存、输出缓存和 blob 缓存。 由于云中的拓扑差异，这些选项不一定可用，因为范围差异使这些方法不太可行。
- 对于用于云使用的任何页面/功能/自定义，应针对更高的延迟以及用户的分布式位置进行优化，以便不同区域或区域的用户拥有更加一致的体验。 云提供内容交付网络 (CDN) 等优化，以针对分布式用户群和新式 SharePoint 进行优化，我们的开箱即用 (OOTB) Web 部件利用上一个已知的良好 (LKG) 。

### <a name="what-to-do"></a>要执行哪些工作：
 - 对于 SharePoint Online 中的所有网站页面，请使用[](./page-diagnostics-for-spo.md)页面诊断工具，该工具是一个Chromium扩展，可帮助分析和提供指导。 网站所有者、编辑者、管理员和开发人员可以使用此功能，因为它旨在作为分析和优化的起点。
 - 开发人员还应在新式页面上使用开发工具（如 F12 浏览器开发人员工具）以及浏览器中的 Ctrl-F12。 [Fiddler](https://www.telerik.com/download/fiddler) 还可用于查看大小权重 (页面的大小（以 MB 为单位）) 以及影响整个页面负载的调用和元素数。 

本节是优化页面的简短摘要。  若要了解更多信息，请参阅：  [创建、启动和维护正常运行的门户](/sharepoint/portal-health)。

## <a name="follow-a-wave--phased-roll-out-approach"></a>遵循 Wave/分阶段推出方法
网站启动的传统重大方法不允许验证自定义项、外部源、服务或流程是否经过适当的测试。 这并不意味着启动需要几个月的时间，但建议至少几天时间，这取决于您的组织规模。 因此，按照一波推出计划，您可以选择在继续下一阶段之前暂停并解决问题，从而降低受任何问题影响的潜在用户数。 SharePoint服务根据使用情况和预测的使用情况扩展容量，尽管我们不需要你通知我们你的启动，你应该遵循指南以确保成功。
  
如下图所示，受邀用户的数量通常明显高于实际使用该网站的用户数。 此图显示了如何推出版本的策略。 此方法可帮助确定大多数用户SharePoint网站之前改进该网站的方法。
  
![显示受邀并且处于活动状态的用户的图形](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
在试点阶段，应该从用户反馈组织信任并知道将参与。 这样，可以评估系统的使用方式以及系统执行方式。
  
在每个阶段中，收集用户有关功能以及每波部署期间的性能的反馈。 这有一个优势，即随着系统的使用变慢，系统引入缓慢并进行了改进。 这还允许我们在向越来越多的用户推出网站时对增加的负载做出反应，并结合遵循页面优化指南，以确保为用户带来积极的体验。

### <a name="what-to-do"></a>要执行哪些工作：
- 确定每个阶段的时间，并确保您具有应变/暂停机会（在继续之前需要进行调整）
- 规划要启用的第一组用户，以确保收到继续工作所需的反馈。 这意味着，在可能的情况下，选择一组将及时提供反馈的活动用户
- 在规划每一波时，请尝试从少于 5000 位用户 (用户开始) ，然后在继续每一波时增加组大小。 这有助于创建错开的方法，并允许所需的更轻松的暂停机会。