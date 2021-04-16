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
ms.openlocfilehash: 8acd8d85826d7bda399c03cc60f2806af954c6c3
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861599"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="1fa9c-104">确定 Microsoft 365 Defender 中事件的优先级</span><span class="sxs-lookup"><span data-stu-id="1fa9c-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1fa9c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1fa9c-105">**Applies to:**</span></span>
- <span data-ttu-id="1fa9c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fa9c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1fa9c-107">Microsoft 365 Defender 应用相关分析，将来自不同产品的相关警报和自动调查聚合到事件中。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="1fa9c-108">在 Microsoft 365 Defender 在整个产品套件中具有端到端可见性时，Microsoft 365 Defender 还会触发有关仅可标识为恶意活动的唯一警报。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="1fa9c-109">此视图为安全分析师提供了更广泛的攻击案例，帮助他们更好地了解并处理整个组织的复杂威胁。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="1fa9c-110">**事件队列** 显示跨设备、用户和邮箱创建的事件集合。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="1fa9c-111">它可以帮助你对事件进行排序，从而确定优先级并制定明智的网络安全响应决策。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="1fa9c-112">在快速启动 Microsoft 365 安全中心 & 事件>事件和事件，你可以进入事件队列 (security.microsoft.com) 。 [](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1fa9c-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件队列示例":::

<span data-ttu-id="1fa9c-114">默认情况下，Microsoft 365 安全中心内的事件队列显示过去六个月看到的事件。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-114">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="1fa9c-115">最近的事件位于列表顶部，以便你可以先看到它。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="1fa9c-116">事件队列具有可自定义 (选择"选择) 列"，可让你查看事件或受影响实体的不同特征。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="1fa9c-117">这可以帮助您就事件的优先顺序做出明智的决策进行分析。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-117">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="1fa9c-118">为了一目了然，自动事件命名根据警报属性（如受影响的终结点数量、受影响的用户数、检测源或类别）生成事件名称。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="1fa9c-119">这使您可以快速了解事件的范围。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="1fa9c-120">例如： *多个源报告的多个终结点上的多阶段事件。*</span><span class="sxs-lookup"><span data-stu-id="1fa9c-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="1fa9c-121">在推出自动事件命名之前已存在的事件不会更改其名称。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="1fa9c-122">事件队列还公开了多个筛选选项，在应用这些选项时，您可以对环境中的所有现有事件执行广泛扫描，或决定重点关注特定方案或威胁。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="1fa9c-123">在事件队列中应用筛选器可帮助确定需要立即关注的事件。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="1fa9c-124">可用筛选器</span><span class="sxs-lookup"><span data-stu-id="1fa9c-124">Available filters</span></span>

<span data-ttu-id="1fa9c-125">从默认事件队列中，可以选择"筛选器"以查看"筛选器"窗格，可以从中查看一组已筛选的事件。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="1fa9c-126">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="事件队列的筛选器窗格示例":::

<span data-ttu-id="1fa9c-128">此表列出了可用的筛选器名称。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="1fa9c-129">筛选器名称</span><span class="sxs-lookup"><span data-stu-id="1fa9c-129">Filter name</span></span> | <span data-ttu-id="1fa9c-130">说明</span><span class="sxs-lookup"><span data-stu-id="1fa9c-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="1fa9c-131">分配到</span><span class="sxs-lookup"><span data-stu-id="1fa9c-131">Assigned to</span></span> | <span data-ttu-id="1fa9c-132">你可以选择显示分配给你或由自动化处理警报的警报。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="1fa9c-133">类别</span><span class="sxs-lookup"><span data-stu-id="1fa9c-133">Categories</span></span> | <span data-ttu-id="1fa9c-134">选择类别以专注于特定的策略、技术或看到的攻击组件。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="1fa9c-135">分类</span><span class="sxs-lookup"><span data-stu-id="1fa9c-135">Classification</span></span> | <span data-ttu-id="1fa9c-136">根据相关警报的集分类筛选事件。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="1fa9c-137">值包括真警报、假警报或未设置。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="1fa9c-138">数据敏感性</span><span class="sxs-lookup"><span data-stu-id="1fa9c-138">Data sensitivity</span></span> | <span data-ttu-id="1fa9c-139">某些攻击主要针对容易泄露或有价值的数据。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="1fa9c-140">通过应用筛选器查看事件中是否涉及敏感数据，可以快速确定敏感信息是否可能已泄露，并优先解决这些事件。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="1fa9c-141">仅适用于已启用 Microsoft 信息保护的情况。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="1fa9c-142">设备组</span><span class="sxs-lookup"><span data-stu-id="1fa9c-142">Device group</span></span> | <span data-ttu-id="1fa9c-143">按定义的设备组进行筛选。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="1fa9c-144">调查状态</span><span class="sxs-lookup"><span data-stu-id="1fa9c-144">Investigation state</span></span> | <span data-ttu-id="1fa9c-145">按自动调查的状态筛选事件。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="1fa9c-146">多个类别</span><span class="sxs-lookup"><span data-stu-id="1fa9c-146">Multiple categories</span></span> | <span data-ttu-id="1fa9c-147">可以选择仅查看映射到多个类别并因此可能导致更多损坏的事件。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="1fa9c-148">多个服务源</span><span class="sxs-lookup"><span data-stu-id="1fa9c-148">Multiple service sources</span></span>  | <span data-ttu-id="1fa9c-149">筛选以仅查看包含来自不同来源的警报的事件 (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="1fa9c-150">操作系统平台</span><span class="sxs-lookup"><span data-stu-id="1fa9c-150">OS platform</span></span> | <span data-ttu-id="1fa9c-151">按操作系统限制事件队列视图。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="1fa9c-152">服务源</span><span class="sxs-lookup"><span data-stu-id="1fa9c-152">Service sources</span></span> | <span data-ttu-id="1fa9c-153">通过选择特定来源，可以集中精力处理包含至少一个来自该选定来源的警报的事件。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="1fa9c-154">Severity</span><span class="sxs-lookup"><span data-stu-id="1fa9c-154">Severity</span></span> | <span data-ttu-id="1fa9c-155">事件的严重性表明它可以对资产产生的影响。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="1fa9c-156">严重性越高，影响越大，通常需要最直接的关注。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="1fa9c-157">状态</span><span class="sxs-lookup"><span data-stu-id="1fa9c-157">Status</span></span> | <span data-ttu-id="1fa9c-158">可以根据事件的状态选择限制所显示事件的列表，以查看哪些事件处于活动状态/已解决状态。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="incident-response-workflow"></a><span data-ttu-id="1fa9c-159">事件响应工作流</span><span class="sxs-lookup"><span data-stu-id="1fa9c-159">Incident response workflow</span></span>

<span data-ttu-id="1fa9c-160">下面是响应事件的典型工作流：</span><span class="sxs-lookup"><span data-stu-id="1fa9c-160">Here is the typical workflow for responding to incidents:</span></span>

1. <span data-ttu-id="1fa9c-161">确定并会审最高优先级的事件，以便进行调查和解决。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-161">Identify and triage the highest priority incidents for investigation and resolution.</span></span>
2. <span data-ttu-id="1fa9c-162">对于每个高优先级事件，开始 [调查](investigate-incidents.md)：</span><span class="sxs-lookup"><span data-stu-id="1fa9c-162">For each high-priority incident, begin an [investigation](investigate-incidents.md):</span></span>

   <span data-ttu-id="1fa9c-163">a.</span><span class="sxs-lookup"><span data-stu-id="1fa9c-163">a.</span></span> <span data-ttu-id="1fa9c-164">查看事件摘要，了解事件的范围、受影响的实体以及 (**摘要** 选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-164">View the summary of the incident to understand it's scope, what entities are affected, and severity (the **Summary** tab).</span></span>

   <span data-ttu-id="1fa9c-165">b.</span><span class="sxs-lookup"><span data-stu-id="1fa9c-165">b.</span></span> <span data-ttu-id="1fa9c-166">开始查看警报以了解警报的来源、范围和严重性 (**警报** 选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-166">Begin looking at the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="1fa9c-167">c.</span><span class="sxs-lookup"><span data-stu-id="1fa9c-167">c.</span></span> <span data-ttu-id="1fa9c-168">根据需要，在"设备、用户"和"邮箱"选项卡上 (受影响的设备、用户和) 。  </span><span class="sxs-lookup"><span data-stu-id="1fa9c-168">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="1fa9c-169">d.</span><span class="sxs-lookup"><span data-stu-id="1fa9c-169">d.</span></span> <span data-ttu-id="1fa9c-170">请参阅 Microsoft 365 Defender 如何自动解决"调查"选项卡 (**警报**) 。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-170">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="1fa9c-171">e.</span><span class="sxs-lookup"><span data-stu-id="1fa9c-171">e.</span></span> <span data-ttu-id="1fa9c-172">根据需要，使用事件数据集中的信息获取"证据和 (**响应** "选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-172">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

<span data-ttu-id="1fa9c-173">调查时，应关注：</span><span class="sxs-lookup"><span data-stu-id="1fa9c-173">As you investigate, you should be concerned with:</span></span>

- <span data-ttu-id="1fa9c-174">包含：减少对租户的任何额外影响。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-174">Containment: Reducing any additional impact on your tenant.</span></span>
- <span data-ttu-id="1fa9c-175">小安：删除安全威胁。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-175">Eradication: Removing the security threat.</span></span>
- <span data-ttu-id="1fa9c-176">恢复：将租户资源还原到攻击前的状态。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-176">Recovery: Restoring your tenant resources to the state they were in before the attack.</span></span>

<span data-ttu-id="1fa9c-177">解决事件后，请花些时间了解一下：</span><span class="sxs-lookup"><span data-stu-id="1fa9c-177">After you resolve the incident, take a moment to learn from it to:</span></span>

- <span data-ttu-id="1fa9c-178">了解攻击的类型及其影响。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-178">Understand the type of the attack and its impact.</span></span>
- <span data-ttu-id="1fa9c-179">研究安全社区中的攻击，以寻找安全攻击趋势。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-179">Research the attack in the security community for a security attack trend.</span></span>
- <span data-ttu-id="1fa9c-180">重新调用用于解决事件的工作流，并根据需要更新标准工作流和手册。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-180">Recall the workflow you used to resolve the incident and update your standard workflows and playbooks as needed.</span></span>

<span data-ttu-id="1fa9c-181">以下是基本过程的摘要。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-181">Here's a summary of the basic process.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="调查事件的基本过程":::

## <a name="next-step"></a><span data-ttu-id="1fa9c-183">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1fa9c-183">Next step</span></span>

<span data-ttu-id="1fa9c-184">确定哪个事件需要最高优先级后，选择它并开始 [调查](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="1fa9c-184">After you've determined which incident requires the highest priority, select it and begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1fa9c-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fa9c-185">See also</span></span>
- [<span data-ttu-id="1fa9c-186">事件概述</span><span class="sxs-lookup"><span data-stu-id="1fa9c-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1fa9c-187">调查事件</span><span class="sxs-lookup"><span data-stu-id="1fa9c-187">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="1fa9c-188">管理事件</span><span class="sxs-lookup"><span data-stu-id="1fa9c-188">Manage incidents</span></span>](manage-incidents.md)
