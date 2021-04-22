---
title: Microsoft 365 Defender 中的事件
description: 调查在 Microsoft 365 安全中心内跨设备、用户和邮箱看到的事件。
keywords: 事件， 警报， 调查， 分析， 响应， 关联， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365
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
ms.openlocfilehash: 890e64367c49c24c8c70e2cbda9869a5d0797219
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939574"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="9825b-104">Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="9825b-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9825b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9825b-105">**Applies to:**</span></span>
- <span data-ttu-id="9825b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9825b-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="9825b-107">希望体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="9825b-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="9825b-108">你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="9825b-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="9825b-109">Microsoft 365 Defender 中的事件是关联警报和关联数据的集合，这些警报和关联数据是攻击案例的一部分。</span><span class="sxs-lookup"><span data-stu-id="9825b-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="9825b-110">Microsoft 365 服务和应用在检测到可疑或恶意事件或活动时创建警报。</span><span class="sxs-lookup"><span data-stu-id="9825b-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="9825b-111">个别警报提供有关已完成或持续攻击的有价值的线索。</span><span class="sxs-lookup"><span data-stu-id="9825b-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="9825b-112">但是，攻击通常对不同类型的实体（如设备、用户和邮箱）使用各种技术。</span><span class="sxs-lookup"><span data-stu-id="9825b-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="9825b-113">结果是租户中多个实体收到多个警报。</span><span class="sxs-lookup"><span data-stu-id="9825b-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="9825b-114">由于将各个警报分组在一起以深入了解攻击可能非常困难且耗时，因此 Microsoft 365 Defender 会自动将警报及其相关信息聚合到事件中。</span><span class="sxs-lookup"><span data-stu-id="9825b-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender 如何将实体中的事件关联到事件中":::

<span data-ttu-id="9825b-116">观看此简短概述，了解 Microsoft 365 Defender (4 分钟) 。</span><span class="sxs-lookup"><span data-stu-id="9825b-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="9825b-117">将相关警报分组到事件可为你提供攻击的全面视图。</span><span class="sxs-lookup"><span data-stu-id="9825b-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="9825b-118">例如，可以看到：</span><span class="sxs-lookup"><span data-stu-id="9825b-118">For example, you can see:</span></span>

- <span data-ttu-id="9825b-119">攻击的开始位置。</span><span class="sxs-lookup"><span data-stu-id="9825b-119">Where the attack started.</span></span>
- <span data-ttu-id="9825b-120">使用了哪些策略。</span><span class="sxs-lookup"><span data-stu-id="9825b-120">What tactics were used.</span></span>
- <span data-ttu-id="9825b-121">攻击已进入你的租户多远。</span><span class="sxs-lookup"><span data-stu-id="9825b-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="9825b-122">攻击范围，如影响的设备、用户和邮箱数量。</span><span class="sxs-lookup"><span data-stu-id="9825b-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="9825b-123">与攻击关联的所有数据。</span><span class="sxs-lookup"><span data-stu-id="9825b-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="9825b-124">如果 [启用，Microsoft](m365d-enable.md)365 Defender 可以通过自动化和人工智能自动调查和解决警报。</span><span class="sxs-lookup"><span data-stu-id="9825b-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="9825b-125">还可以执行其他修正步骤来解决攻击。</span><span class="sxs-lookup"><span data-stu-id="9825b-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="9825b-126">Microsoft 365 安全中心中的事件和警报</span><span class="sxs-lookup"><span data-stu-id="9825b-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="9825b-127">在快速启动 Microsoft  365 安全中心&事件>事件或事件管理事件 (security.microsoft.com) 。 [](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9825b-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="9825b-128">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="9825b-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 安全中心中的&quot;事件&quot;页面":::

<span data-ttu-id="9825b-130">选择事件名称将显示事件摘要，并提供对包含其他信息的选项卡的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9825b-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 安全中心内事件的&quot;摘要&quot;页面示例":::

<span data-ttu-id="9825b-132">事件的其他选项卡包括：</span><span class="sxs-lookup"><span data-stu-id="9825b-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="9825b-133">警报</span><span class="sxs-lookup"><span data-stu-id="9825b-133">Alerts</span></span> 

  <span data-ttu-id="9825b-134">与事件及其信息相关的所有警报。</span><span class="sxs-lookup"><span data-stu-id="9825b-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="9825b-135">设备</span><span class="sxs-lookup"><span data-stu-id="9825b-135">Devices</span></span>

  <span data-ttu-id="9825b-136">标识为事件的一部分或与事件相关的所有设备。</span><span class="sxs-lookup"><span data-stu-id="9825b-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="9825b-137">用户</span><span class="sxs-lookup"><span data-stu-id="9825b-137">Users</span></span>

  <span data-ttu-id="9825b-138">标识为事件的一部分或与事件相关的所有用户。</span><span class="sxs-lookup"><span data-stu-id="9825b-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="9825b-139">邮箱</span><span class="sxs-lookup"><span data-stu-id="9825b-139">Mailboxes</span></span>

  <span data-ttu-id="9825b-140">已标识为事件的一部分或与事件相关的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="9825b-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="9825b-141">调查</span><span class="sxs-lookup"><span data-stu-id="9825b-141">Investigations</span></span>

  <span data-ttu-id="9825b-142">事件警报触发的所有自动调查。</span><span class="sxs-lookup"><span data-stu-id="9825b-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="9825b-143">证据和响应</span><span class="sxs-lookup"><span data-stu-id="9825b-143">Evidence and Response</span></span>

  <span data-ttu-id="9825b-144">事件警报中支持的所有事件和可疑实体。</span><span class="sxs-lookup"><span data-stu-id="9825b-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="9825b-145">下面是 Microsoft 365 安全中心内事件及其数据与事件选项卡之间的关系。</span><span class="sxs-lookup"><span data-stu-id="9825b-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Microsoft 365 安全中心内事件及其数据与事件选项卡的关系":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="9825b-147">Microsoft 365 Defender 事件响应工作流示例</span><span class="sxs-lookup"><span data-stu-id="9825b-147">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="9825b-148">下面是使用 Microsoft 365 安全中心响应 Microsoft 365 中的事件的示例工作流。</span><span class="sxs-lookup"><span data-stu-id="9825b-148">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Microsoft 365 的事件响应工作流示例":::

<span data-ttu-id="9825b-150">持续确定事件队列中用于分析和解决的最高优先级事件，并使它们做好响应准备。</span><span class="sxs-lookup"><span data-stu-id="9825b-150">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="9825b-151">这是以下两者的组合：</span><span class="sxs-lookup"><span data-stu-id="9825b-151">This is a combination of:</span></span>

- <span data-ttu-id="9825b-152">[通过](incident-queue.md) 筛选和事件队列排序来确定最高优先级事件的会审。</span><span class="sxs-lookup"><span data-stu-id="9825b-152">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="9825b-153">[通过](manage-incidents.md) 修改事件的标题、将其分配给分析员以及添加标签和注释来管理事件。</span><span class="sxs-lookup"><span data-stu-id="9825b-153">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="9825b-154">对于每个事件，开始 [攻击和警报分析](investigate-incidents.md)：</span><span class="sxs-lookup"><span data-stu-id="9825b-154">For each incident, begin an [attack and alert analysis](investigate-incidents.md):</span></span>

   <span data-ttu-id="9825b-155">a.</span><span class="sxs-lookup"><span data-stu-id="9825b-155">a.</span></span> <span data-ttu-id="9825b-156">查看事件的摘要，了解事件的范围和严重性以及受影响实体 ("摘要"选项卡) 。 </span><span class="sxs-lookup"><span data-stu-id="9825b-156">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="9825b-157">b.</span><span class="sxs-lookup"><span data-stu-id="9825b-157">b.</span></span> <span data-ttu-id="9825b-158">开始分析警报，了解警报的来源、范围和严重性 (**警报** 选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="9825b-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="9825b-159">c.</span><span class="sxs-lookup"><span data-stu-id="9825b-159">c.</span></span> <span data-ttu-id="9825b-160">根据需要，在"设备、用户"和"邮箱"选项卡上 (受影响的设备、用户和) 。  </span><span class="sxs-lookup"><span data-stu-id="9825b-160">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="9825b-161">d.</span><span class="sxs-lookup"><span data-stu-id="9825b-161">d.</span></span> <span data-ttu-id="9825b-162">请参阅 Microsoft 365 Defender 如何自动解决"调查"选项卡 (**警报**) 。</span><span class="sxs-lookup"><span data-stu-id="9825b-162">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="9825b-163">e.</span><span class="sxs-lookup"><span data-stu-id="9825b-163">e.</span></span> <span data-ttu-id="9825b-164">根据需要，使用事件数据集中的信息获取"证据和 (**响应** "选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="9825b-164">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="9825b-165">在分析之后或分析过程中，解决抑制问题，以减少攻击和安全威胁的更多影响。</span><span class="sxs-lookup"><span data-stu-id="9825b-165">After or during your analysis, address containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="9825b-166">尽可能将租户资源还原到事件发生前的状态，从而从攻击中恢复。</span><span class="sxs-lookup"><span data-stu-id="9825b-166">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="9825b-167">[解决](manage-incidents.md#resolve-incident) 事件并花时间了解事件后情况：</span><span class="sxs-lookup"><span data-stu-id="9825b-167">[Resolve](manage-incidents.md#resolve-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="9825b-168">了解攻击的类型及其影响。</span><span class="sxs-lookup"><span data-stu-id="9825b-168">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="9825b-169">研究威胁分析 [和安全](threat-analytics.md) 社区中的攻击，以寻找安全攻击趋势。</span><span class="sxs-lookup"><span data-stu-id="9825b-169">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="9825b-170">重新调用用于解决事件的工作流，并根据需要更新标准工作流、流程、策略和操作手册。</span><span class="sxs-lookup"><span data-stu-id="9825b-170">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="9825b-171">确定是否需要更改安全配置，并实施这些更改。</span><span class="sxs-lookup"><span data-stu-id="9825b-171">Determine whether changes in your security configuration are needed and implement them.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="9825b-172">Microsoft 365 Defender 的安全操作示例</span><span class="sxs-lookup"><span data-stu-id="9825b-172">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="9825b-173">下面是 Microsoft 365 Defender 的安全操作示例。</span><span class="sxs-lookup"><span data-stu-id="9825b-173">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Micosoft 365 Defender 的安全操作示例":::

<span data-ttu-id="9825b-175">日常任务可能包括：</span><span class="sxs-lookup"><span data-stu-id="9825b-175">Daily tasks can include:</span></span>

- <span data-ttu-id="9825b-176">[管理](manage-incidents.md) 事件</span><span class="sxs-lookup"><span data-stu-id="9825b-176">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="9825b-177">查看 [AIR (操作) 调查和 ](m365d-action-center.md) 响应</span><span class="sxs-lookup"><span data-stu-id="9825b-177">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions</span></span>
- <span data-ttu-id="9825b-178">查看最新的 [威胁分析](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="9825b-178">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="9825b-179">[响应](investigate-incidents.md) 事件</span><span class="sxs-lookup"><span data-stu-id="9825b-179">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="9825b-180">每月任务可能包括：</span><span class="sxs-lookup"><span data-stu-id="9825b-180">Monthly tasks can include:</span></span>

- <span data-ttu-id="9825b-181">查看 [AIR 设置](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="9825b-181">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="9825b-182">查看[安全分数和](microsoft-secure-score-improvement-actions.md)[威胁&漏洞管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="9825b-182">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="9825b-183">报告给 IT 安全管理链</span><span class="sxs-lookup"><span data-stu-id="9825b-183">Reporting to your IT security management chain</span></span>

<span data-ttu-id="9825b-184">季度任务可包括向 CISO (首席信息安全官报告并) 。</span><span class="sxs-lookup"><span data-stu-id="9825b-184">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="9825b-185">年度任务可能包括执行重大事件或泄露练习，以测试员工、系统和流程。</span><span class="sxs-lookup"><span data-stu-id="9825b-185">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="9825b-186">每日、每月、季度和年度任务可用于更新或优化流程、策略和安全配置。</span><span class="sxs-lookup"><span data-stu-id="9825b-186">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9825b-187">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9825b-187">Next steps</span></span>

<span data-ttu-id="9825b-188">"事件"页 **中的事件** 队列列出了最近事件。</span><span class="sxs-lookup"><span data-stu-id="9825b-188">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="9825b-189">在这里，你可以：</span><span class="sxs-lookup"><span data-stu-id="9825b-189">From here, you can:</span></span>

- <span data-ttu-id="9825b-190">查看应基于严重性 [和](incident-queue.md) 其他因素对哪些事件进行优先排序。</span><span class="sxs-lookup"><span data-stu-id="9825b-190">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="9825b-191">[管理事件](manage-incidents.md)，其中包括重命名、分配、分类以及添加标记和注释以用于事件管理工作流。</span><span class="sxs-lookup"><span data-stu-id="9825b-191">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments for your incident management workflow.</span></span>
- <span data-ttu-id="9825b-192">执行 [事件](investigate-incidents.md) 分析。</span><span class="sxs-lookup"><span data-stu-id="9825b-192">Perform an [analysis](investigate-incidents.md) of an incident.</span></span>
