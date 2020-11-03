---
title: 优先考虑 Microsoft 365 Defender 中的事件
description: 了解如何在 Microsoft 365 Defender 中优先处理事件队列中的事件
keywords: 事件, 队列, 概述, 设备, 标识, 用户, 邮箱, 电子邮件, 事件
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f681d02cc4af8bd56ba945a3d944798e545bf93c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846708"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="e2e57-104">优先考虑 Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="e2e57-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e2e57-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e2e57-105">**Applies to:**</span></span>
- <span data-ttu-id="e2e57-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2e57-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="e2e57-107">Microsoft 365 Defender 应用相关分析，并将来自不同产品的所有相关警报和调查聚合到一个事件中。</span><span class="sxs-lookup"><span data-stu-id="e2e57-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="e2e57-108">Microsoft 365 Defender 还会触发针对活动的唯一警报，这些活动仅在 Microsoft 365 Defender 跨整个房地产和产品套件提供的端到端可见性时，才会被标识为恶意活动。</span><span class="sxs-lookup"><span data-stu-id="e2e57-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="e2e57-109">通过执行此操作，Microsoft 365 Defender narrates 了更广泛的攻击情景，使安全操作分析员能够了解并处理整个组织中的复杂威胁。</span><span class="sxs-lookup"><span data-stu-id="e2e57-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="e2e57-110">“事件队列”显示在设备、用户和邮箱中标记的事件的集合。</span><span class="sxs-lookup"><span data-stu-id="e2e57-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="e2e57-111">它可以帮助你对事件进行排序，从而确定优先级并制定明智的网络安全响应决策。</span><span class="sxs-lookup"><span data-stu-id="e2e57-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![事件队列的图像](../../media/incidents-queue.png) 

<span data-ttu-id="e2e57-113">默认情况下，Microsoft 365 安全中心中的队列显示最近 30 天看到的事件，最新事件显示在列表的顶部，方便用户首先查看最新事件。</span><span class="sxs-lookup"><span data-stu-id="e2e57-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="e2e57-114">事件队列会公开可自定义的列，可让你深入了解事件或所含实体的不同特征，从而帮助你就待处理事件的优先级做出明智的决策。</span><span class="sxs-lookup"><span data-stu-id="e2e57-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="e2e57-115">若要一目了然，自动事件命名功能将根据警报属性（如受影响的终结点数、受影响的终结点数、检测源或类别）生成事件名称。</span><span class="sxs-lookup"><span data-stu-id="e2e57-115">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="e2e57-116">这使您可以快速了解事件的范围。</span><span class="sxs-lookup"><span data-stu-id="e2e57-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="e2e57-117">例如：多 *个源报告的多个终结点上的多阶段事件。*</span><span class="sxs-lookup"><span data-stu-id="e2e57-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="e2e57-118">在自动事件命名的首次部署之前已存在的事件将不会更改其名称。</span><span class="sxs-lookup"><span data-stu-id="e2e57-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="e2e57-119">事件队列中还会显示多个筛选选项，应用这些选项后，可以选择大范围扫描环境中的所有现有事件，也可以决定专注于特定的情形或威胁。</span><span class="sxs-lookup"><span data-stu-id="e2e57-119">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="e2e57-120">在事件队列中应用筛选器可帮助确定需要立即关注的事件。</span><span class="sxs-lookup"><span data-stu-id="e2e57-120">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="e2e57-121">可用筛选器</span><span class="sxs-lookup"><span data-stu-id="e2e57-121">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="e2e57-122">状态</span><span class="sxs-lookup"><span data-stu-id="e2e57-122">Status</span></span>
<span data-ttu-id="e2e57-123">可以根据事件的状态选择限制所显示事件的列表，以查看哪些事件处于活动状态/已解决状态。</span><span class="sxs-lookup"><span data-stu-id="e2e57-123">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="e2e57-124">严重性</span><span class="sxs-lookup"><span data-stu-id="e2e57-124">Severity</span></span>
<span data-ttu-id="e2e57-125">事件的严重性表明了它可能对资产产生的影响。</span><span class="sxs-lookup"><span data-stu-id="e2e57-125">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="e2e57-126">严重性越高，影响越大，通常需要最直接的关注。</span><span class="sxs-lookup"><span data-stu-id="e2e57-126">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="e2e57-127">分配给（所有者）</span><span class="sxs-lookup"><span data-stu-id="e2e57-127">Assigned to (owner)</span></span>
<span data-ttu-id="e2e57-128">可选择通过选择分配给任何人/分配给你的人来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="e2e57-128">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="e2e57-129">多个警报</span><span class="sxs-lookup"><span data-stu-id="e2e57-129">Multiple alerts</span></span> 
<span data-ttu-id="e2e57-130">筛选以仅查看包含多个警报的事件。</span><span class="sxs-lookup"><span data-stu-id="e2e57-130">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="e2e57-131">这可能表示攻击更为复杂或在杀伤链中进行了攻击。</span><span class="sxs-lookup"><span data-stu-id="e2e57-131">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="e2e57-132">多个服务源</span><span class="sxs-lookup"><span data-stu-id="e2e57-132">Multiple service sources</span></span> 
<span data-ttu-id="e2e57-133">筛选器仅查看包含来自不同源的警报的事件 (Microsoft Defender for Endpoint、Microsoft 云应用安全性、Microsoft Defender for Identity、Microsoft Defender for Office 365) </span><span class="sxs-lookup"><span data-stu-id="e2e57-133">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365)</span></span>
### <a name="service-sources"></a><span data-ttu-id="e2e57-134">服务源</span><span class="sxs-lookup"><span data-stu-id="e2e57-134">Service sources</span></span>
<span data-ttu-id="e2e57-135">通过选择特定来源，可以集中精力处理包含至少一个来自该选定来源的警报的事件。</span><span class="sxs-lookup"><span data-stu-id="e2e57-135">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="e2e57-136">多个类别</span><span class="sxs-lookup"><span data-stu-id="e2e57-136">Multiple categories</span></span> 
<span data-ttu-id="e2e57-137">可选择仅显示已映射到杀伤链的多个类别，并可能导致更严重损坏的事件。</span><span class="sxs-lookup"><span data-stu-id="e2e57-137">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="e2e57-138">类别</span><span class="sxs-lookup"><span data-stu-id="e2e57-138">Categories</span></span>
<span data-ttu-id="e2e57-139">选择特定类别，专注于杀伤链中的特定步骤</span><span class="sxs-lookup"><span data-stu-id="e2e57-139">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="e2e57-140">数据敏感性</span><span class="sxs-lookup"><span data-stu-id="e2e57-140">Data sensitivity</span></span>
<span data-ttu-id="e2e57-141">某些攻击主要针对容易泄露或有价值的数据。</span><span class="sxs-lookup"><span data-stu-id="e2e57-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="e2e57-142">通过应用筛选器查看事件中是否涉及敏感数据，可以快速确定敏感信息是否可能已泄露，并优先解决这些事件。</span><span class="sxs-lookup"><span data-stu-id="e2e57-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="e2e57-143">仅适用于已启用 Microsoft 信息保护的情况。</span><span class="sxs-lookup"><span data-stu-id="e2e57-143">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="e2e57-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e2e57-144">Next steps</span></span>
<span data-ttu-id="e2e57-145">确定哪个事件需要最高优先级后，可继续对事件执行进一步的调查工作。</span><span class="sxs-lookup"><span data-stu-id="e2e57-145">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="e2e57-146">调查事件</span><span class="sxs-lookup"><span data-stu-id="e2e57-146">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="e2e57-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="e2e57-147">Related topics</span></span>
- [<span data-ttu-id="e2e57-148">事件概述</span><span class="sxs-lookup"><span data-stu-id="e2e57-148">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e2e57-149">调查事件</span><span class="sxs-lookup"><span data-stu-id="e2e57-149">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="e2e57-150">管理事件</span><span class="sxs-lookup"><span data-stu-id="e2e57-150">Manage incidents</span></span>](manage-incidents.md)
