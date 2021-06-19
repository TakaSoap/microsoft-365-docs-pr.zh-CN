---
title: 事件Microsoft 365 Defender
description: 调查在 Microsoft 365 Defender 门户中跨设备、用户和邮箱Microsoft 365 Defender事件。
keywords: 事件， 警报， 调查， 分析， 响应， 相关， 攻击， 计算机， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击
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
ms.openlocfilehash: 3dac22afb074a58ea2afdf842a9a62c6cee77dcc
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022766"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="4fe24-104">事件Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4fe24-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4fe24-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4fe24-105">**Applies to:**</span></span>
- <span data-ttu-id="4fe24-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4fe24-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="4fe24-107">希望体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="4fe24-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="4fe24-108">你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="4fe24-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="4fe24-109">事件Microsoft 365 Defender是关联警报和关联数据的集合，这些警报和关联数据是攻击事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="4fe24-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="4fe24-110">Microsoft 365服务和应用在检测到可疑或恶意事件或活动时创建警报。</span><span class="sxs-lookup"><span data-stu-id="4fe24-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="4fe24-111">个别警报提供有关已完成或持续攻击的有价值的线索。</span><span class="sxs-lookup"><span data-stu-id="4fe24-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="4fe24-112">但是，攻击通常对不同类型的实体（如设备、用户和邮箱）使用各种技术。</span><span class="sxs-lookup"><span data-stu-id="4fe24-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="4fe24-113">结果是租户中多个实体收到多个警报。</span><span class="sxs-lookup"><span data-stu-id="4fe24-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="4fe24-114">由于将各个警报分组在一起以深入了解攻击可能非常困难且耗时，Microsoft 365 Defender自动将警报及其相关信息聚合到事件中。</span><span class="sxs-lookup"><span data-stu-id="4fe24-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="如何将Microsoft 365 Defender事件与事件关联":::

<span data-ttu-id="4fe24-116">观看此简短事件概述，Microsoft 365 Defender (4 分钟内) 。</span><span class="sxs-lookup"><span data-stu-id="4fe24-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="4fe24-117">将相关警报分组到事件可为你提供攻击的全面视图。</span><span class="sxs-lookup"><span data-stu-id="4fe24-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="4fe24-118">例如，可以看到：</span><span class="sxs-lookup"><span data-stu-id="4fe24-118">For example, you can see:</span></span>

- <span data-ttu-id="4fe24-119">攻击的开始位置。</span><span class="sxs-lookup"><span data-stu-id="4fe24-119">Where the attack started.</span></span>
- <span data-ttu-id="4fe24-120">使用了哪些策略。</span><span class="sxs-lookup"><span data-stu-id="4fe24-120">What tactics were used.</span></span>
- <span data-ttu-id="4fe24-121">攻击已进入你的租户多远。</span><span class="sxs-lookup"><span data-stu-id="4fe24-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="4fe24-122">攻击范围，如影响的设备、用户和邮箱数量。</span><span class="sxs-lookup"><span data-stu-id="4fe24-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="4fe24-123">与攻击关联的所有数据。</span><span class="sxs-lookup"><span data-stu-id="4fe24-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="4fe24-124">如果[启用](m365d-enable.md)，Microsoft 365 Defender[可以通过自动化和](m365d-autoir.md)人工智能自动调查和解决警报。</span><span class="sxs-lookup"><span data-stu-id="4fe24-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="4fe24-125">还可以执行其他修正步骤来解决攻击。</span><span class="sxs-lookup"><span data-stu-id="4fe24-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="4fe24-126">Microsoft 365 Defender 门户中的事件和警报</span><span class="sxs-lookup"><span data-stu-id="4fe24-126">Incidents and alerts in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="4fe24-127">在快速启动 >  & (security.microsoft.com) 时，你可以管理事件Microsoft 365 Defender警报) 。 [](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4fe24-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="4fe24-128">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="4fe24-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件门户中的Microsoft 365 Defender页面":::

<span data-ttu-id="4fe24-130">选择事件名称将显示事件摘要，并提供对包含其他信息的选项卡的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4fe24-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="事件门户中事件的&quot;摘要&quot;Microsoft 365 Defender示例":::

<span data-ttu-id="4fe24-132">事件的其他选项卡包括：</span><span class="sxs-lookup"><span data-stu-id="4fe24-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="4fe24-133">警报</span><span class="sxs-lookup"><span data-stu-id="4fe24-133">Alerts</span></span> 

  <span data-ttu-id="4fe24-134">与事件及其信息相关的所有警报。</span><span class="sxs-lookup"><span data-stu-id="4fe24-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="4fe24-135">设备</span><span class="sxs-lookup"><span data-stu-id="4fe24-135">Devices</span></span>

  <span data-ttu-id="4fe24-136">标识为事件的一部分或与事件相关的所有设备。</span><span class="sxs-lookup"><span data-stu-id="4fe24-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4fe24-137">用户</span><span class="sxs-lookup"><span data-stu-id="4fe24-137">Users</span></span>

  <span data-ttu-id="4fe24-138">标识为事件的一部分或与事件相关的所有用户。</span><span class="sxs-lookup"><span data-stu-id="4fe24-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4fe24-139">邮箱</span><span class="sxs-lookup"><span data-stu-id="4fe24-139">Mailboxes</span></span>

  <span data-ttu-id="4fe24-140">已标识为事件的一部分或与事件相关的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="4fe24-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4fe24-141">调查</span><span class="sxs-lookup"><span data-stu-id="4fe24-141">Investigations</span></span>

  <span data-ttu-id="4fe24-142">事件 [警报](m365d-autoir.md) 触发的所有自动调查。</span><span class="sxs-lookup"><span data-stu-id="4fe24-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="4fe24-143">证据和响应</span><span class="sxs-lookup"><span data-stu-id="4fe24-143">Evidence and Response</span></span>

  <span data-ttu-id="4fe24-144">事件警报中支持的所有事件和可疑实体。</span><span class="sxs-lookup"><span data-stu-id="4fe24-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="4fe24-145">Graph (预览版) </span><span class="sxs-lookup"><span data-stu-id="4fe24-145">Graph (in preview)</span></span>

  <span data-ttu-id="4fe24-146">显示警报与组织中受影响资产的连接的图。</span><span class="sxs-lookup"><span data-stu-id="4fe24-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="4fe24-147">下面是事件及其数据与事件门户中事件选项卡Microsoft 365 Defender关系。</span><span class="sxs-lookup"><span data-stu-id="4fe24-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="事件及其数据与事件门户中事件选项卡Microsoft 365 Defender关系":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="4fe24-149">事件响应工作流示例Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4fe24-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="4fe24-150">下面是一个工作流示例，用于通过 Microsoft 365 门户Microsoft 365 Defender事件。</span><span class="sxs-lookup"><span data-stu-id="4fe24-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="事件的事件响应工作流示例Microsoft 365":::

<span data-ttu-id="4fe24-152">持续确定事件队列中用于分析和解决的最高优先级事件，并使它们做好响应准备。</span><span class="sxs-lookup"><span data-stu-id="4fe24-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="4fe24-153">这是以下两者的组合：</span><span class="sxs-lookup"><span data-stu-id="4fe24-153">This is a combination of:</span></span>

- <span data-ttu-id="4fe24-154">[通过](incident-queue.md) 筛选和事件队列排序来确定最高优先级事件的会审。</span><span class="sxs-lookup"><span data-stu-id="4fe24-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="4fe24-155">[通过](manage-incidents.md) 修改事件的标题、将其分配给分析员以及添加标签和注释来管理事件。</span><span class="sxs-lookup"><span data-stu-id="4fe24-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="4fe24-156">对于每个事件，开始 [攻击和警报调查和分析](investigate-incidents.md)：</span><span class="sxs-lookup"><span data-stu-id="4fe24-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   1. <span data-ttu-id="4fe24-157">查看事件的摘要，了解事件的范围和严重性以及受影响实体 ("摘要"选项卡) 。 </span><span class="sxs-lookup"><span data-stu-id="4fe24-157">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   1. <span data-ttu-id="4fe24-158">开始分析警报，了解警报的来源、范围和严重性 (**警报** 选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="4fe24-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   1. <span data-ttu-id="4fe24-159">根据需要，在"设备、用户"和"邮箱"选项卡上 (受影响的设备、用户和) 。  </span><span class="sxs-lookup"><span data-stu-id="4fe24-159">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   1. <span data-ttu-id="4fe24-160">请参阅Microsoft 365 Defender"调查 ["](m365d-autoir.md)选项卡 (自动 **解决某些**) 。</span><span class="sxs-lookup"><span data-stu-id="4fe24-160">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   1. <span data-ttu-id="4fe24-161">根据需要，使用事件数据集中的信息获取"证据和 (**响应** "选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="4fe24-161">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="4fe24-162">在分析之后或分析过程中，执行抑制，以减少攻击和安全威胁的任何额外影响。</span><span class="sxs-lookup"><span data-stu-id="4fe24-162">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="4fe24-163">尽可能将租户资源还原到事件发生前的状态，从而从攻击中恢复。</span><span class="sxs-lookup"><span data-stu-id="4fe24-163">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="4fe24-164">[解决](manage-incidents.md#resolve-an-incident) 事件并花时间了解事件后情况：</span><span class="sxs-lookup"><span data-stu-id="4fe24-164">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="4fe24-165">了解攻击的类型及其影响。</span><span class="sxs-lookup"><span data-stu-id="4fe24-165">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="4fe24-166">研究威胁分析 [和安全](threat-analytics.md) 社区中的攻击，以寻找安全攻击趋势。</span><span class="sxs-lookup"><span data-stu-id="4fe24-166">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="4fe24-167">重新调用用于解决事件的工作流，并根据需要更新标准工作流、流程、策略和操作手册。</span><span class="sxs-lookup"><span data-stu-id="4fe24-167">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="4fe24-168">确定是否需要更改安全配置，并实施这些更改。</span><span class="sxs-lookup"><span data-stu-id="4fe24-168">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="4fe24-169">如果你是安全分析的新增人员，请参阅第一[](incidents-overview.md)个事件响应简介，了解其他信息并逐步查看示例事件。</span><span class="sxs-lookup"><span data-stu-id="4fe24-169">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="4fe24-170">示例安全操作Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4fe24-170">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="4fe24-171">下面是一个安全操作示例Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="4fe24-171">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="安全操作示例Microsoft 365 Defender":::

<span data-ttu-id="4fe24-173">日常任务可能包括：</span><span class="sxs-lookup"><span data-stu-id="4fe24-173">Daily tasks can include:</span></span>

- <span data-ttu-id="4fe24-174">[管理](manage-incidents.md) 事件</span><span class="sxs-lookup"><span data-stu-id="4fe24-174">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="4fe24-175">查看 [操作中心中的 AIR (AIR) ](m365d-action-center.md) 操作自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="4fe24-175">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="4fe24-176">查看最新的 [威胁分析](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="4fe24-176">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="4fe24-177">[响应](investigate-incidents.md) 事件</span><span class="sxs-lookup"><span data-stu-id="4fe24-177">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="4fe24-178">每月任务可能包括：</span><span class="sxs-lookup"><span data-stu-id="4fe24-178">Monthly tasks can include:</span></span>

- <span data-ttu-id="4fe24-179">查看 [AIR 设置](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="4fe24-179">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="4fe24-180">查看[安全分数和](microsoft-secure-score-improvement-actions.md)[威胁&漏洞管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="4fe24-180">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="4fe24-181">报告给 IT 安全管理链</span><span class="sxs-lookup"><span data-stu-id="4fe24-181">Reporting to your IT security management chain</span></span>

<span data-ttu-id="4fe24-182">季度任务可包括向 CISO (首席信息安全官报告并) 。</span><span class="sxs-lookup"><span data-stu-id="4fe24-182">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="4fe24-183">年度任务可能包括执行重大事件或泄露练习，以测试员工、系统和流程。</span><span class="sxs-lookup"><span data-stu-id="4fe24-183">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="4fe24-184">每日、每月、季度和年度任务可用于更新或优化流程、策略和安全配置。</span><span class="sxs-lookup"><span data-stu-id="4fe24-184">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4fe24-185">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4fe24-185">Next steps</span></span>

<span data-ttu-id="4fe24-186">**如果你是安全分析和** 事件响应的新增人员：</span><span class="sxs-lookup"><span data-stu-id="4fe24-186">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="4fe24-187">请参阅[响应你的](first-incident-overview.md)第一个事件演练，获取有关 Microsoft 365 Defender 门户中分析、修正和事后评审的典型流程的引导教程，并查看攻击示例。</span><span class="sxs-lookup"><span data-stu-id="4fe24-187">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 Defender portal with an example of an attack.</span></span>

<span data-ttu-id="4fe24-188">**如果你有安全分析和** 事件响应的经验：</span><span class="sxs-lookup"><span data-stu-id="4fe24-188">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="4fe24-189">从事件门户的"事件 **"页面开始** Microsoft 365 Defender队列。</span><span class="sxs-lookup"><span data-stu-id="4fe24-189">Get started with the incident queue from the **Incidents** page of the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="4fe24-190">在这里，你可以:</span><span class="sxs-lookup"><span data-stu-id="4fe24-190">From here, you can:</span></span>

  - <span data-ttu-id="4fe24-191">查看应基于严重性 [和](incident-queue.md) 其他因素对哪些事件进行优先排序。</span><span class="sxs-lookup"><span data-stu-id="4fe24-191">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="4fe24-192">[管理事件](manage-incidents.md)，其中包括重命名、分配、分类以及根据事件管理工作流添加标记和注释。</span><span class="sxs-lookup"><span data-stu-id="4fe24-192">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="4fe24-193">[执行事件](investigate-incidents.md)调查。</span><span class="sxs-lookup"><span data-stu-id="4fe24-193">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="4fe24-194">请参阅 [这些事件响应手册，](/security/compass/incident-response-playbooks) 获取网络钓鱼、密码加密以及应用许可授予攻击的详细指南。</span><span class="sxs-lookup"><span data-stu-id="4fe24-194">See these [incident response playbooks](/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

