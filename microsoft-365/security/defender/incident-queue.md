---
title: 确定 defender 中事件的Microsoft 365优先级
description: 了解如何在 Defender 中筛选事件队列中Microsoft 365事件
keywords: 事件， 队列， 概述， 设备， 标识， 用户， 邮箱， 电子邮件， 事件， 分析， 响应
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: df2d2660267c38dccf5ef09fa4955615d3a78141
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636262"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="27cdf-104">确定 defender 中事件的Microsoft 365优先级</span><span class="sxs-lookup"><span data-stu-id="27cdf-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="27cdf-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="27cdf-105">**Applies to:**</span></span>
- <span data-ttu-id="27cdf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27cdf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="27cdf-107">Microsoft 365Defender 应用相关分析，将来自不同产品的相关警报和自动调查聚合到事件中。</span><span class="sxs-lookup"><span data-stu-id="27cdf-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="27cdf-108">Microsoft 365在 Defender 在整个产品套件中具有的端到端可见性Microsoft 365，Defender 还会触发有关仅可标识为恶意活动的唯一警报。</span><span class="sxs-lookup"><span data-stu-id="27cdf-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="27cdf-109">此视图为安全分析师提供了更广泛的攻击案例，帮助他们更好地了解并处理整个组织的复杂威胁。</span><span class="sxs-lookup"><span data-stu-id="27cdf-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="27cdf-110">**事件队列** 显示跨设备、用户和邮箱创建的事件集合。</span><span class="sxs-lookup"><span data-stu-id="27cdf-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="27cdf-111">它可以帮助你对事件进行排序，从而确定优先级并制定明智的网络安全响应决策。</span><span class="sxs-lookup"><span data-stu-id="27cdf-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="27cdf-112">在快速启动 Microsoft 365 **>** 安全中心&事件 (security.microsoft.com) ，你可以进入 [事件队列。](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="27cdf-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="27cdf-113">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="27cdf-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件队列示例":::

<span data-ttu-id="27cdf-115">" **最近的事件和警报** "部分显示过去 24 小时内收到的警报数和创建的事件数的图。</span><span class="sxs-lookup"><span data-stu-id="27cdf-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="27cdf-116">默认情况下，安全中心内的事件Microsoft 365显示过去六个月看到的事件。</span><span class="sxs-lookup"><span data-stu-id="27cdf-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="27cdf-117">最近的事件位于列表顶部，以便你可以先看到它。</span><span class="sxs-lookup"><span data-stu-id="27cdf-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="27cdf-118">事件队列具有可自定义 (选择"选择) 列"，可让你查看事件或受影响实体的不同特征。</span><span class="sxs-lookup"><span data-stu-id="27cdf-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="27cdf-119">这可以帮助您就事件的优先顺序做出明智的决策进行分析。</span><span class="sxs-lookup"><span data-stu-id="27cdf-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="27cdf-120">为了一目了然，自动事件命名根据警报属性（如受影响的终结点数量、受影响的用户数、检测源或类别）生成事件名称。</span><span class="sxs-lookup"><span data-stu-id="27cdf-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="27cdf-121">这使您可以快速了解事件的范围。</span><span class="sxs-lookup"><span data-stu-id="27cdf-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="27cdf-122">例如： *多个源报告的多个终结点上的多阶段事件。*</span><span class="sxs-lookup"><span data-stu-id="27cdf-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="27cdf-123">在推出自动事件命名之前已存在的事件不会更改其名称。</span><span class="sxs-lookup"><span data-stu-id="27cdf-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="27cdf-124">事件队列还公开了多个筛选选项，在应用这些选项时，您可以对环境中的所有现有事件执行广泛扫描，或决定重点关注特定方案或威胁。</span><span class="sxs-lookup"><span data-stu-id="27cdf-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="27cdf-125">在事件队列中应用筛选器可帮助确定需要立即关注的事件。</span><span class="sxs-lookup"><span data-stu-id="27cdf-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="27cdf-126">可用筛选器</span><span class="sxs-lookup"><span data-stu-id="27cdf-126">Available filters</span></span>

<span data-ttu-id="27cdf-127">从默认事件队列中，可以选择"筛选器"以查看"筛选器"窗格，可以从中查看一组已筛选的事件。</span><span class="sxs-lookup"><span data-stu-id="27cdf-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="27cdf-128">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="27cdf-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="事件队列的筛选器窗格示例":::

<span data-ttu-id="27cdf-130">此表列出了可用的筛选器名称。</span><span class="sxs-lookup"><span data-stu-id="27cdf-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="27cdf-131">筛选器名称</span><span class="sxs-lookup"><span data-stu-id="27cdf-131">Filter name</span></span> | <span data-ttu-id="27cdf-132">说明</span><span class="sxs-lookup"><span data-stu-id="27cdf-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="27cdf-133">分配到</span><span class="sxs-lookup"><span data-stu-id="27cdf-133">Assigned to</span></span> | <span data-ttu-id="27cdf-134">你可以选择显示分配给你或由自动化处理警报的警报。</span><span class="sxs-lookup"><span data-stu-id="27cdf-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="27cdf-135">类别</span><span class="sxs-lookup"><span data-stu-id="27cdf-135">Categories</span></span> | <span data-ttu-id="27cdf-136">选择类别以专注于特定的策略、技术或看到的攻击组件。</span><span class="sxs-lookup"><span data-stu-id="27cdf-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="27cdf-137">分类</span><span class="sxs-lookup"><span data-stu-id="27cdf-137">Classification</span></span> | <span data-ttu-id="27cdf-138">根据相关警报的集分类筛选事件。</span><span class="sxs-lookup"><span data-stu-id="27cdf-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="27cdf-139">值包括真警报、假警报或未设置。</span><span class="sxs-lookup"><span data-stu-id="27cdf-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="27cdf-140">数据敏感性</span><span class="sxs-lookup"><span data-stu-id="27cdf-140">Data sensitivity</span></span> | <span data-ttu-id="27cdf-141">某些攻击主要针对容易泄露或有价值的数据。</span><span class="sxs-lookup"><span data-stu-id="27cdf-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="27cdf-142">通过应用筛选器查看事件中是否涉及敏感数据，可以快速确定敏感信息是否可能已泄露，并优先解决这些事件。</span><span class="sxs-lookup"><span data-stu-id="27cdf-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="27cdf-143">仅适用于已启用 Microsoft 信息保护的情况。</span><span class="sxs-lookup"><span data-stu-id="27cdf-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="27cdf-144">设备组</span><span class="sxs-lookup"><span data-stu-id="27cdf-144">Device group</span></span> | <span data-ttu-id="27cdf-145">按定义的设备组进行筛选。</span><span class="sxs-lookup"><span data-stu-id="27cdf-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="27cdf-146">调查状态</span><span class="sxs-lookup"><span data-stu-id="27cdf-146">Investigation state</span></span> | <span data-ttu-id="27cdf-147">按自动调查的状态筛选事件。</span><span class="sxs-lookup"><span data-stu-id="27cdf-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="27cdf-148">多个类别</span><span class="sxs-lookup"><span data-stu-id="27cdf-148">Multiple categories</span></span> | <span data-ttu-id="27cdf-149">可以选择仅查看映射到多个类别并因此可能导致更多损坏的事件。</span><span class="sxs-lookup"><span data-stu-id="27cdf-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="27cdf-150">多个服务源</span><span class="sxs-lookup"><span data-stu-id="27cdf-150">Multiple service sources</span></span>  | <span data-ttu-id="27cdf-151">筛选以仅查看包含来自不同来源的警报的事件 (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 。</span><span class="sxs-lookup"><span data-stu-id="27cdf-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="27cdf-152">操作系统平台</span><span class="sxs-lookup"><span data-stu-id="27cdf-152">OS platform</span></span> | <span data-ttu-id="27cdf-153">按操作系统限制事件队列视图。</span><span class="sxs-lookup"><span data-stu-id="27cdf-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="27cdf-154">服务源</span><span class="sxs-lookup"><span data-stu-id="27cdf-154">Service sources</span></span> | <span data-ttu-id="27cdf-155">通过选择特定来源，可以集中精力处理包含至少一个来自该选定来源的警报的事件。</span><span class="sxs-lookup"><span data-stu-id="27cdf-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="27cdf-156">严重性</span><span class="sxs-lookup"><span data-stu-id="27cdf-156">Severity</span></span> | <span data-ttu-id="27cdf-157">事件的严重性表明它可以对资产产生的影响。</span><span class="sxs-lookup"><span data-stu-id="27cdf-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="27cdf-158">严重性越高，影响越大，通常需要最直接的关注。</span><span class="sxs-lookup"><span data-stu-id="27cdf-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="27cdf-159">状态</span><span class="sxs-lookup"><span data-stu-id="27cdf-159">Status</span></span> | <span data-ttu-id="27cdf-160">可以根据事件的状态选择限制所显示事件的列表，以查看哪些事件处于活动状态/已解决状态。</span><span class="sxs-lookup"><span data-stu-id="27cdf-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-steps"></a><span data-ttu-id="27cdf-161">后续步骤</span><span class="sxs-lookup"><span data-stu-id="27cdf-161">Next steps</span></span>

<span data-ttu-id="27cdf-162">确定哪个事件需要最高优先级后，选择它并：</span><span class="sxs-lookup"><span data-stu-id="27cdf-162">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="27cdf-163">[管理](manage-incidents.md) 事件的属性，包括标记、分配、误报事件的即时解决和注释。</span><span class="sxs-lookup"><span data-stu-id="27cdf-163">[Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.</span></span>
- <span data-ttu-id="27cdf-164">开始 [调查](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="27cdf-164">Begin your [investigations](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="27cdf-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27cdf-165">See also</span></span>
- [<span data-ttu-id="27cdf-166">事件概述</span><span class="sxs-lookup"><span data-stu-id="27cdf-166">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="27cdf-167">管理事件</span><span class="sxs-lookup"><span data-stu-id="27cdf-167">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="27cdf-168">调查事件</span><span class="sxs-lookup"><span data-stu-id="27cdf-168">Investigate incidents</span></span>](investigate-incidents.md)
