---
title: 容量规划和负载测试 SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
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
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: 本文介绍如何部署到 SharePoint Online，而无需执行传统的负载测试，因为它是不允许的。
ms.openlocfilehash: 8792c59ef96ef97cc36d0908100fd9ebb330857a
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807004"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>容量规划和负载测试 SharePoint Online
本文介绍如何在没有传统负载测试SharePoint部署到 SharePoint Online，因为不允许在 SharePoint Online 上执行负载测试。 SharePoint Online 是一项云服务，该服务中的负载功能、运行状况和总体平衡由 Microsoft 管理。
  
确保成功启动网站的最佳方法是遵循门户启动推出计划中突出显示的指导原则、实践 [和建议](planportallaunchroll-out.md)。

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>联机版SharePoint容量规划的概述 
与本地部署SharePoint Online 的主要好处之一是云弹性和分布式区域用户的优化。 我们的大型环境设置为每天为数百万用户提供服务，因此，我们通过平衡和扩展服务器场来有效处理容量非常重要。
  
尽管对于任何一个服务器场中的任一租户，增长通常不可预测，但随着时间的推移，总请求总和是可预测的。 通过确定 SharePoint Online 的增长趋势，我们可以规划未来的扩展。
  
为了高效地使用容量并应对意外增长，在任何服务器场中，我们都有用于跟踪和监视服务的各种元素的自动化。 利用多个指标，其中一个主要指标是 CPU 负载，它用作向上扩展前端服务器的信号。 此外，我们还建议使用分阶段[/](planportallaunchroll-out.md)wave 方法，因为 SQL 环境将随着时间的负载和增长进行扩展，并且遵循阶段和波允许该负载和增长的正确分布。 

容量不仅仅是为了持续添加更多硬件，还涉及管理和控制该容量以确保其为有效负载请求提供服务。 我们建议客户遵循推荐的指南，以确保他们获得最佳体验。 它还意味着我们具有限制模式和控件，以确保我们不允许服务中出现"滥用"行为。 尽管并非所有"不良"行为都是有意为之，但我们必须确保限制该行为的影响。 有关限制以及如何避免限制的进一步信息，请查看如何避免受限制的 [指南](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) 文章。

## <a name="why-you-cannot-load-test-sharepoint-online"></a>无法联机加载测试SharePoint的原因
对于本地环境，负载测试用于验证扩展假设并最终找到服务器场的断点;通过使负载饱和。 

使用 SharePoint Online，我们需要以不同方式执行一些操作，因为缩放相对流畅，并基于某些启发性调整、限制和控制负载。 作为这样的大型多租户环境，我们必须保护同一服务器场中的所有租户，以便自动限制任何负载测试。 但是，如果您尝试加载测试，除了受到限制之外，您会收到令人误解的结果，因为当前测试的服务器场在测试窗口或测试后几个小时内可能会发生更改，因为将定期执行缩放和服务器场平衡操作。

不要尝试将测试SharePoint作为服务加载，而是专注于遵循建议的做法，并按照创建、启动和维护正常的[门户指南](/sharepoint/portal-health)操作。