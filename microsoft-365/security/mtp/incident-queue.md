---
title: 在 Microsoft 威胁防护中确定事件的优先级
description: 了解如何在 Microsoft 威胁防护中确定事件队列中事件的优先级
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 90f7aaf7eb4425dadeb27699654656c86d2b6263
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087293"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="d487c-104">在 Microsoft 威胁防护中确定事件的优先级</span><span class="sxs-lookup"><span data-stu-id="d487c-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="d487c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d487c-105">**Applies to:**</span></span>
- <span data-ttu-id="d487c-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="d487c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d487c-107">Microsoft 威胁防护应用相关性分析，将来自不同产品的所有相关警报和调查汇总到一个事件中。</span><span class="sxs-lookup"><span data-stu-id="d487c-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="d487c-108">鉴于 Microsoft 威胁防护在整个产品和产品套件中具有的端到端可见性，Microsoft 威胁防护还会针对仅识别为“恶意”的活动触发唯一警报。</span><span class="sxs-lookup"><span data-stu-id="d487c-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="d487c-109">通过执行此操作，Microsoft 威胁防护可以描述更详尽的攻击事件，使安全操作分析人员能够理解和处理整个组织中的复杂威胁。</span><span class="sxs-lookup"><span data-stu-id="d487c-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="d487c-110">“事件队列”\*\*\*\* 显示在设备、用户和邮箱中标记的事件的集合。</span><span class="sxs-lookup"><span data-stu-id="d487c-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="d487c-111">它可以帮助你对事件进行排序，从而确定优先级并制定明智的网络安全响应决策。</span><span class="sxs-lookup"><span data-stu-id="d487c-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![事件队列的图像](../../media/incidents-queue.png) 

<span data-ttu-id="d487c-113">默认情况下，Microsoft 365 安全中心中的队列显示最近 30 天看到的事件，最新事件显示在列表的顶部，方便用户首先查看最新事件。</span><span class="sxs-lookup"><span data-stu-id="d487c-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="d487c-114">事件队列会公开可自定义的列，可让你深入了解事件或所含实体的不同特征，从而帮助你就待处理事件的优先级做出明智的决策。</span><span class="sxs-lookup"><span data-stu-id="d487c-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span> 

<span data-ttu-id="d487c-115">事件队列中还会显示多个筛选选项，应用这些选项后，可以选择大范围扫描环境中的所有现有事件，也可以决定专注于特定的情形或威胁。</span><span class="sxs-lookup"><span data-stu-id="d487c-115">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="d487c-116">在事件队列中应用筛选器可帮助确定需要立即关注的事件。</span><span class="sxs-lookup"><span data-stu-id="d487c-116">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="d487c-117">可用筛选器</span><span class="sxs-lookup"><span data-stu-id="d487c-117">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="d487c-118">状态</span><span class="sxs-lookup"><span data-stu-id="d487c-118">Status</span></span>
<span data-ttu-id="d487c-119">可以根据事件的状态选择限制所显示事件的列表，以查看哪些事件处于活动状态/已解决状态。</span><span class="sxs-lookup"><span data-stu-id="d487c-119">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="d487c-120">严重性</span><span class="sxs-lookup"><span data-stu-id="d487c-120">Severity</span></span>
<span data-ttu-id="d487c-121">事件的严重性表明了它可能对资产产生的影响。</span><span class="sxs-lookup"><span data-stu-id="d487c-121">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="d487c-122">严重性越高，影响越大，通常需要最直接的关注。</span><span class="sxs-lookup"><span data-stu-id="d487c-122">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="d487c-123">分配给（所有者）</span><span class="sxs-lookup"><span data-stu-id="d487c-123">Assigned to (owner)</span></span>
<span data-ttu-id="d487c-124">可选择通过选择分配给任何人/分配给你的人来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="d487c-124">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="d487c-125">多个警报</span><span class="sxs-lookup"><span data-stu-id="d487c-125">Multiple alerts</span></span> 
<span data-ttu-id="d487c-126">筛选以仅查看包含多个警报的事件。</span><span class="sxs-lookup"><span data-stu-id="d487c-126">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="d487c-127">这可能表示攻击更为复杂或在杀伤链中进行了攻击。</span><span class="sxs-lookup"><span data-stu-id="d487c-127">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="d487c-128">多个服务源</span><span class="sxs-lookup"><span data-stu-id="d487c-128">Multiple service sources</span></span> 
<span data-ttu-id="d487c-129">筛选以仅显示包含来自不同来源（Microsoft Defender ATP、Microsoft Cloud App Security、Azure ATP、Office 365 ATP）的警报的事件</span><span class="sxs-lookup"><span data-stu-id="d487c-129">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="d487c-130">服务源</span><span class="sxs-lookup"><span data-stu-id="d487c-130">Service sources</span></span>
<span data-ttu-id="d487c-131">通过选择特定来源，可以集中精力处理包含至少一个来自该选定来源的警报的事件。</span><span class="sxs-lookup"><span data-stu-id="d487c-131">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="d487c-132">多个类别</span><span class="sxs-lookup"><span data-stu-id="d487c-132">Multiple categories</span></span> 
<span data-ttu-id="d487c-133">可选择仅显示已映射到杀伤链的多个类别，并可能导致更严重损坏的事件。</span><span class="sxs-lookup"><span data-stu-id="d487c-133">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="d487c-134">类别</span><span class="sxs-lookup"><span data-stu-id="d487c-134">Categories</span></span>
<span data-ttu-id="d487c-135">选择特定类别，专注于杀伤链中的特定步骤</span><span class="sxs-lookup"><span data-stu-id="d487c-135">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="d487c-136">数据敏感性</span><span class="sxs-lookup"><span data-stu-id="d487c-136">Data sensitivity</span></span>
<span data-ttu-id="d487c-137">某些攻击主要针对容易泄露或有价值的数据。</span><span class="sxs-lookup"><span data-stu-id="d487c-137">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="d487c-138">通过应用筛选器查看事件中是否涉及敏感数据，可以快速确定敏感信息是否可能已泄露，并优先解决这些事件。</span><span class="sxs-lookup"><span data-stu-id="d487c-138">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="d487c-139">仅适用于已启用 Microsoft 信息保护的情况。</span><span class="sxs-lookup"><span data-stu-id="d487c-139">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="d487c-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d487c-140">Next steps</span></span>
<span data-ttu-id="d487c-141">确定哪个事件需要最高优先级后，可继续对事件执行进一步的调查工作。</span><span class="sxs-lookup"><span data-stu-id="d487c-141">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="d487c-142">调查事件</span><span class="sxs-lookup"><span data-stu-id="d487c-142">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="d487c-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="d487c-143">Related topics</span></span>
- [<span data-ttu-id="d487c-144">事件概述</span><span class="sxs-lookup"><span data-stu-id="d487c-144">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d487c-145">调查事件</span><span class="sxs-lookup"><span data-stu-id="d487c-145">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="d487c-146">管理事件</span><span class="sxs-lookup"><span data-stu-id="d487c-146">Manage incidents</span></span>](manage-incidents.md)
