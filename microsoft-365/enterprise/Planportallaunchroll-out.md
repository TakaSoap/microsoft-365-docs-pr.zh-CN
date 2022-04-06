---
title: 在 SharePoint Online 中规划门户启动推出计划
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.openlocfilehash: c31a77f516aad7a58d908f47ee09dac353872283
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569484"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>在 SharePoint Online 中规划门户启动推出计划

门户是 Intranet 上的SharePoint网站，许多网站查看者使用网站上的内容。 大型组织可能有几个门户。 例如，公司门户和 HR 门户。 通常，门户创建和创作网站及其内容的人员相对较少。 门户的大多数访问者仅读取和使用内容。

本文介绍如何规划部署和部署计划以使用 SharePoint Online。 它还提供了遵循的方法，因为系统不允许在 SharePoint Online 上执行传统负载测试。 SharePoint Online 是一项云服务，并且该服务中的负载功能、运行状况和总体平衡由 Microsoft 管理。

为了帮助创建成功的门户，请遵循创建、启动和维护正常运行的门户中详述的指导原则、实践 [和建议](/sharepoint/portal-health)

下面重点介绍了部署方法。

## <a name="portal-launch-scheduler"></a>门户启动计划程序

使用门户启动计划程序在计划阶段向组织用户发布门户。 了解更多：

![日历图标。](../media/calendar.png) [门户启动计划程序](/microsoft-365/enterprise/portallaunchscheduler)

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>SharePoint Online 中的容量规划概述

为了高效地使用容量并应对意外增长，在任何服务器场中，我们都有用于跟踪特定使用方案的自动化。 尽管任何一个服务器场中的任一租户的确切增长不可预测，但随着时间的推移，请求总数是可预测的。 通过确定 SharePoint Online 的增长趋势，我们可以规划未来的扩展。 有关联机容量[规划和负载测试SharePoint详细信息](capacity-planning-and-load-testing-sharepoint-online.md)。

成功启动的关键部分是下面详述的"wave"或"阶段性推出"方法。

## <a name="can-i-load-test-sharepoint-online"></a>能否加载测试SharePoint Online？

SharePoint Online 是一个共享的多租户环境，跨服务器场和规模进行平衡，并根据需要进行调整。 负载测试环境（如 SharePoint Online）的扩展会不断更改，不仅会获得意外结果，而且不允许进行。

了解更多信息：[SharePoint Online 的容量规划和负载测试](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>按照建议的准则优化页面

本地部署中的页面不应简单地被移动，因为它们位于 SharePoint Online 上，而不根据针对 SharePoint Online 的建议准则查看它们。 最佳方法是始终为 SharePoint 中任何网站或门户优化任何主页，因为这是组织中大多数用户将作为网站网站 (的起点) 。

应考虑一些基本因素：

- 本地部署可以使用传统的服务器端缓存，如对象缓存、输出缓存和 blob 缓存。 由于云中的拓扑差异，这些选项不一定可用，因为范围差异使这些方法不太可行。
- 对于用于云使用的任何页面/功能/自定义，应针对更高的延迟和用户的分布式位置进行优化，以便不同区域或区域的用户拥有更加一致的体验。 云提供内容交付网络 (CDN) 等优化，以针对分布式用户群和新式 SharePoint 进行优化，我们的开箱即用 (OOTB) Web 部件利用上一个已知的良好 (LKG) 。

**要执行哪些工作**：

- 对于 SharePoint Online 中的所有网站页面，请使用页面诊断[](./page-diagnostics-for-spo.md)工具，该工具是一个Chromium扩展，可帮助分析和提供指导。 网站所有者、编辑者、管理员和开发人员可以使用此功能，因为它旨在作为分析和优化的起点。
- 开发人员还应在新式页面上的浏览器中使用 F12 浏览器开发人员工具和 CTRL-F12 等开发工具。 [Fiddler](https://www.telerik.com/download/fiddler) 还可用于查看大小权重 (页面的大小（以 MB 为单位）) 以及影响整个页面负载的调用和元素数。

本节是优化页面的简短摘要。  若要了解更多信息，请参阅：  [创建、启动和维护正常运行的门户](/sharepoint/portal-health)。

## <a name="follow-a-wave--phased-roll-out-approach"></a>遵循 Wave/分阶段推出方法

网站启动的传统重大方法不允许验证自定义项、外部源、服务或流程是否经过适当的测试。 此方法并不意味着需要几个月时间启动，但建议至少几天时间，这取决于您的组织规模。 因此，按照一波推出计划，可以选择在继续下一阶段之前暂停并解决问题，从而降低受任何问题影响的潜在用户数。 SharePoint服务根据使用情况和预测的使用情况扩展容量，尽管我们不需要你通知我们你的启动，你应该遵循指南以确保成功。

如下图所示，受邀用户的数量通常明显高于实际使用该网站的用户数。 此图显示了如何推出版本的策略。 此方法可帮助确定在大多数用户看到网站SharePoint改进网站的方法。

![Graph邀请的用户和活跃用户。](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)

在试点阶段，应该从用户反馈组织信任并知道将参与。 这样，可以测量系统的使用方式及其执行方式。

在每个阶段中，收集用户在每个部署阶段的功能和性能反馈。 收集反馈有一个优势，即系统使用缓慢，并且随着系统的使用而改进。 这还允许我们在向更多用户推出网站时对增加的负载做出反应，并结合遵循页面优化指南，以确保为用户带来积极的体验。

**要执行哪些工作**：

- 确定每个阶段的时间，并确保您具有应变/暂停机会（在继续之前需要进行调整）
- 规划要启用的第一组用户，以确保收到需要推进的反馈。  如果可能，选择将及时提供反馈的活动用户组
- 在规划每一波时，尝试从少于 5000 位用户 (用户群) 。 在继续每一波时增加组大小。 通过创建错开的方法，可根据需要更轻松地提供暂停机会。
