---
title: 确定 Microsoft 365 Defender 中事件的优先级
description: 了解如何在 Microsoft 365 Defender 中筛选事件队列中的事件
keywords: 事件, 队列, 概述, 设备, 标识, 用户, 邮箱, 电子邮件, 事件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929290"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="5b732-104">确定 Microsoft 365 Defender 中事件的优先级</span><span class="sxs-lookup"><span data-stu-id="5b732-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5b732-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5b732-105">**Applies to:**</span></span>
- <span data-ttu-id="5b732-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b732-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="5b732-107">Microsoft 365 Defender 应用相关分析，将不同产品的所有相关警报和调查聚合到一个事件中。</span><span class="sxs-lookup"><span data-stu-id="5b732-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="5b732-108">Microsoft 365 Defender 还会触发有关仅可以标识为恶意活动的唯一警报，因为 Microsoft 365 Defender 在整个资产和产品套件中具有端到端可见性。</span><span class="sxs-lookup"><span data-stu-id="5b732-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="5b732-109">此视图为安全运营分析师提供了更广泛的攻击案例，帮助他们更好地了解并处理整个组织的复杂威胁。</span><span class="sxs-lookup"><span data-stu-id="5b732-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="5b732-110">“事件队列”显示在设备、用户和邮箱中标记的事件的集合。</span><span class="sxs-lookup"><span data-stu-id="5b732-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="5b732-111">它可以帮助你对事件进行排序，从而确定优先级并制定明智的网络安全响应决策。</span><span class="sxs-lookup"><span data-stu-id="5b732-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![事件队列的图像](../../media/incidents-queue.png) 

<span data-ttu-id="5b732-113">默认情况下，Microsoft 365 安全中心中的队列显示最近 30 天内看到的事件。</span><span class="sxs-lookup"><span data-stu-id="5b732-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="5b732-114">最近的事件位于列表顶部，以便你可以先看到它。</span><span class="sxs-lookup"><span data-stu-id="5b732-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="5b732-115">事件队列公开可自定义的列，可让你了解事件或包含的实体的不同特征。</span><span class="sxs-lookup"><span data-stu-id="5b732-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="5b732-116">这有助于你做出有关要处理的事件优先顺序的明智决定。</span><span class="sxs-lookup"><span data-stu-id="5b732-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="5b732-117">为了一目了然，自动事件命名根据警报属性（如受影响的终结点数量、受影响的用户数、检测源或类别）生成事件名称。</span><span class="sxs-lookup"><span data-stu-id="5b732-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="5b732-118">这使您可以快速了解事件的范围。</span><span class="sxs-lookup"><span data-stu-id="5b732-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="5b732-119">例如： *多个源报告的多个终结点上的多阶段事件。*</span><span class="sxs-lookup"><span data-stu-id="5b732-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="5b732-120">在推出自动事件命名之前已存在的事件不会更改其名称。</span><span class="sxs-lookup"><span data-stu-id="5b732-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="5b732-121">事件队列还会公开多个筛选选项，在应用这些选项时，您可以对环境中的所有现有事件执行广泛扫描，或决定专注于特定方案或威胁。</span><span class="sxs-lookup"><span data-stu-id="5b732-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="5b732-122">在事件队列中应用筛选器可帮助确定需要立即关注的事件。</span><span class="sxs-lookup"><span data-stu-id="5b732-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="5b732-123">可用筛选器</span><span class="sxs-lookup"><span data-stu-id="5b732-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="5b732-124">分配到</span><span class="sxs-lookup"><span data-stu-id="5b732-124">Assigned to</span></span>
<span data-ttu-id="5b732-125">你可以选择显示分配给你或由自动化处理警报的警报。</span><span class="sxs-lookup"><span data-stu-id="5b732-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="5b732-126">类别</span><span class="sxs-lookup"><span data-stu-id="5b732-126">Categories</span></span>
<span data-ttu-id="5b732-127">选择类别以专注于看到的特定策略、技术或攻击组件。</span><span class="sxs-lookup"><span data-stu-id="5b732-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="5b732-128">分类</span><span class="sxs-lookup"><span data-stu-id="5b732-128">Classification</span></span>
<span data-ttu-id="5b732-129">根据相关警报的集分类筛选事件。</span><span class="sxs-lookup"><span data-stu-id="5b732-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="5b732-130">值包括真警报、假警报或未设置。</span><span class="sxs-lookup"><span data-stu-id="5b732-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="5b732-131">数据敏感性</span><span class="sxs-lookup"><span data-stu-id="5b732-131">Data sensitivity</span></span>
<span data-ttu-id="5b732-132">某些攻击主要针对容易泄露或有价值的数据。</span><span class="sxs-lookup"><span data-stu-id="5b732-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="5b732-133">通过应用筛选器查看事件中是否涉及敏感数据，可以快速确定敏感信息是否可能已泄露，并优先解决这些事件。</span><span class="sxs-lookup"><span data-stu-id="5b732-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="5b732-134">仅适用于已启用 Microsoft 信息保护的情况。</span><span class="sxs-lookup"><span data-stu-id="5b732-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="5b732-135">设备组</span><span class="sxs-lookup"><span data-stu-id="5b732-135">Device group</span></span>
<span data-ttu-id="5b732-136">按定义的设备组进行筛选。</span><span class="sxs-lookup"><span data-stu-id="5b732-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="5b732-137">调查状态</span><span class="sxs-lookup"><span data-stu-id="5b732-137">Investigation state</span></span>
<span data-ttu-id="5b732-138">按自动调查的状态筛选事件。</span><span class="sxs-lookup"><span data-stu-id="5b732-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="5b732-139">多个类别</span><span class="sxs-lookup"><span data-stu-id="5b732-139">Multiple categories</span></span> 
<span data-ttu-id="5b732-140">你可以选择仅查看已映射到多个类别并因此可能导致更多损害的事件。</span><span class="sxs-lookup"><span data-stu-id="5b732-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="5b732-141">多个服务源</span><span class="sxs-lookup"><span data-stu-id="5b732-141">Multiple service sources</span></span> 
<span data-ttu-id="5b732-142">筛选以仅查看包含来自不同源的警报的事件 (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 。</span><span class="sxs-lookup"><span data-stu-id="5b732-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="5b732-143">操作系统平台</span><span class="sxs-lookup"><span data-stu-id="5b732-143">OS platform</span></span>
<span data-ttu-id="5b732-144">按操作系统限制事件队列视图。</span><span class="sxs-lookup"><span data-stu-id="5b732-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="5b732-145">服务源</span><span class="sxs-lookup"><span data-stu-id="5b732-145">Service sources</span></span>
<span data-ttu-id="5b732-146">通过选择特定来源，可以集中精力处理包含至少一个来自该选定来源的警报的事件。</span><span class="sxs-lookup"><span data-stu-id="5b732-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="5b732-147">Severity</span><span class="sxs-lookup"><span data-stu-id="5b732-147">Severity</span></span>
<span data-ttu-id="5b732-148">事件的严重性表明它可以对资产产生的影响。</span><span class="sxs-lookup"><span data-stu-id="5b732-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="5b732-149">严重性越高，影响越大，通常需要最直接的注意。</span><span class="sxs-lookup"><span data-stu-id="5b732-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="5b732-150">状态</span><span class="sxs-lookup"><span data-stu-id="5b732-150">Status</span></span>
<span data-ttu-id="5b732-151">可以根据事件的状态选择限制所显示事件的列表，以查看哪些事件处于活动状态/已解决状态。</span><span class="sxs-lookup"><span data-stu-id="5b732-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="5b732-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5b732-152">Next steps</span></span>
<span data-ttu-id="5b732-153">确定哪个事件需要最高优先级后，可继续对事件执行进一步的调查工作。</span><span class="sxs-lookup"><span data-stu-id="5b732-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="5b732-154">调查事件</span><span class="sxs-lookup"><span data-stu-id="5b732-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="5b732-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b732-155">See also</span></span>
- [<span data-ttu-id="5b732-156">事件概述</span><span class="sxs-lookup"><span data-stu-id="5b732-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5b732-157">调查事件</span><span class="sxs-lookup"><span data-stu-id="5b732-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="5b732-158">管理事件</span><span class="sxs-lookup"><span data-stu-id="5b732-158">Manage incidents</span></span>](manage-incidents.md)
