---
title: 容量规划和负载测试 SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
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
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: 本文介绍如何部署到 SharePoint Online，而无需执行传统的负载测试，因为它是不允许的。
ms.openlocfilehash: fb54864168b35fed290ccb1139cb6c607969820d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905220"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a><span data-ttu-id="748b7-103">容量规划和负载测试 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="748b7-103">Capacity planning and load testing SharePoint Online</span></span>
<span data-ttu-id="748b7-104">本文介绍如何在没有传统负载测试SharePoint部署到 SharePoint Online，因为不允许在 SharePoint Online 上执行负载测试。</span><span class="sxs-lookup"><span data-stu-id="748b7-104">This article describes how you can deploy to SharePoint Online without traditional load testing, since load-testing is not permitted on SharePoint Online.</span></span> <span data-ttu-id="748b7-105">SharePoint联机是一种云服务，负载功能、服务中的负载运行状况和总体平衡由 Microsoft 管理。</span><span class="sxs-lookup"><span data-stu-id="748b7-105">SharePoint Online is a cloud service and the load capabilities, health and overall balance of load in the service is managed by Microsoft.</span></span>
  
<span data-ttu-id="748b7-106">确保成功启动网站的最佳方法是遵循在门户启动推出计划中突出显示的指导原则、实践 [和建议](planportallaunchroll-out.md)。</span><span class="sxs-lookup"><span data-stu-id="748b7-106">The best approach to ensuring the success of launching your site is to follow basic principles, practices and recommendations which are highlighted in the [plan your portal launch roll-out](planportallaunchroll-out.md).</span></span>

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a><span data-ttu-id="748b7-107">联机版SharePoint容量规划的概述</span><span class="sxs-lookup"><span data-stu-id="748b7-107">Overview of how SharePoint Online performs Capacity planning</span></span> 
<span data-ttu-id="748b7-108">与本地部署SharePoint Online 的主要好处之一是云的弹性以及分布式区域用户的优化。</span><span class="sxs-lookup"><span data-stu-id="748b7-108">One of the main benefits of SharePoint Online over an on-premises deployment is the elasticity of the cloud as well as optimizations for users in distributed regions.</span></span> <span data-ttu-id="748b7-109">我们的大型环境每天设置为为数百万用户提供服务，因此，我们通过平衡和扩展服务器场有效处理容量非常重要。</span><span class="sxs-lookup"><span data-stu-id="748b7-109">Our large scale environment is set up to service millions of users on a daily basis, so it is important that we handle capacity effectively by balancing and expanding farms.</span></span>
  
<span data-ttu-id="748b7-110">尽管对于任何一个服务器场中的任一租户，增长通常不可预测，但随着时间的推移，总请求总和是可预测的。</span><span class="sxs-lookup"><span data-stu-id="748b7-110">While the growth is often unpredictable for any one tenant in any one farm, the aggregated sum of requests is predictable over time.</span></span> <span data-ttu-id="748b7-111">通过确定 SharePoint Online 的增长趋势，我们可以规划未来的扩展。</span><span class="sxs-lookup"><span data-stu-id="748b7-111">By identifying the growth trends in SharePoint Online, we can plan for future expansion.</span></span>
  
<span data-ttu-id="748b7-112">为了高效地使用容量并应对意外增长，在任何服务器场中，我们都有用于跟踪和监视服务的各种元素的自动化功能。</span><span class="sxs-lookup"><span data-stu-id="748b7-112">In order to efficiently use capacity and deal with unexpected growth, in any farm, we have automation that tracks and monitors various elements of the service.</span></span> <span data-ttu-id="748b7-113">利用多个指标，其中一个主要指标是 CPU 负载，它用作向上扩展前端服务器的信号。</span><span class="sxs-lookup"><span data-stu-id="748b7-113">Multiple metrics are utilized, with one of the main ones being CPU load, which is used as a signal to scale-up front end servers.</span></span> <span data-ttu-id="748b7-114">此外，我们建议采用分阶段[/wave](planportallaunchroll-out.md)方法，因为 SQL 环境将随着时间的负载和增长进行扩展，并且遵循阶段和波允许该负载和增长的正确分布。</span><span class="sxs-lookup"><span data-stu-id="748b7-114">Additionally to this we recommend a [phased / wave approach](planportallaunchroll-out.md), as SQL environments will scale according to load and growth over time, and following the phases and waves allows for the correct distribution of that load and growth.</span></span> 

<span data-ttu-id="748b7-115">容量不仅仅是为了持续添加更多硬件，还涉及管理和控制该容量以确保其为有效负载请求提供服务。</span><span class="sxs-lookup"><span data-stu-id="748b7-115">Capacity is more than just about adding more hardware on a continuous basis but it also pertains to managing and controlling that capacity to ensure it is servicing valid load requests.</span></span> <span data-ttu-id="748b7-116">我们建议客户遵循推荐的指南，以确保他们获得最佳体验。</span><span class="sxs-lookup"><span data-stu-id="748b7-116">We recommend that customers follow the recommended guidance to ensure they have the best experience.</span></span> <span data-ttu-id="748b7-117">它还意味着我们具有限制模式和控件，以确保我们不允许服务中出现"滥用"行为。</span><span class="sxs-lookup"><span data-stu-id="748b7-117">It also means that we have throttling patterns and controls in place to ensure we do not allow "abusive" behavior in the service.</span></span> <span data-ttu-id="748b7-118">尽管并不是所有"不良"行为都是有意为之，但我们必须确保限制该行为的影响。</span><span class="sxs-lookup"><span data-stu-id="748b7-118">Whilst not all "bad" behavior is intentional, we do have to ensure that we limit the effect of that behavior.</span></span> <span data-ttu-id="748b7-119">有关限制以及如何避免限制的进一步信息，请查看如何避免受限制的 [指南](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) 文章。</span><span class="sxs-lookup"><span data-stu-id="748b7-119">For further information on throttling and how to avoid it, review the [how to avoid being throttled guidance](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) article.</span></span>

## <a name="why-you-cannot-load-test-sharepoint-online"></a><span data-ttu-id="748b7-120">无法联机加载测试SharePoint的原因</span><span class="sxs-lookup"><span data-stu-id="748b7-120">Why you cannot load test SharePoint Online</span></span>
<span data-ttu-id="748b7-121">对于本地环境，负载测试用于验证扩展假设并最终找到服务器场的断点;通过使负载饱和。</span><span class="sxs-lookup"><span data-stu-id="748b7-121">With on-premises environments, load testing is used to validate scale assumption and ultimately find the breaking point of a farm; by saturating it with load.</span></span> 

<span data-ttu-id="748b7-122">使用 SharePoint Online，我们需要执行不同的操作，因为缩放是相对流畅的，并基于某些启发式调整、限制和控制负载。</span><span class="sxs-lookup"><span data-stu-id="748b7-122">With SharePoint Online we need to do things differently because the scale is relatively fluid and adjusts, throttles and controls load, based on certain heuristics.</span></span> <span data-ttu-id="748b7-123">作为如此大规模的多租户环境，我们必须保护同一服务器场中的所有租户，以便自动限制任何负载测试。</span><span class="sxs-lookup"><span data-stu-id="748b7-123">Being such a large scale multi-tenant environment, we must protect all tenants in the same farm, so we will automatically throttle any load tests.</span></span> <span data-ttu-id="748b7-124">但是，如果您尝试加载测试，除了受到限制之外，您会收到令人误解的结果，因为当前测试的服务器场在测试窗口或测试后几个小时内可能会发生更改，因为将定期执行缩放和服务器场平衡操作。</span><span class="sxs-lookup"><span data-stu-id="748b7-124">If you do however attempt to load test, besides being throttled, you will receive disappointing and potentially misleading results because the farm you tested today will probably have had scale changes during the testing window or within hours after testing, as scale and farm balancing actions are performed on an on-going basis.</span></span>

<span data-ttu-id="748b7-125">不要尝试将测试SharePoint作为服务加载，而是专注于遵循建议的做法，并按照创建、启动和维护正常的[门户指南](/sharepoint/portal-health)操作。</span><span class="sxs-lookup"><span data-stu-id="748b7-125">Instead of trying to load test SharePoint as a service, rather focus on following the recommended practices and follow the [Creating, launching and maintaining a healthy portal](/sharepoint/portal-health) guidance.</span></span>