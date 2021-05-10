---
title: Microsoft 365 Defender 中的事件
description: 调查在安全中心内跨设备、用户和邮箱Microsoft 365的事件。
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
ms.openlocfilehash: 93751a8297e61a969e0049e27a847324a3d16872
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300009"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="6fcbc-104">Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="6fcbc-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6fcbc-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6fcbc-105">**Applies to:**</span></span>
- <span data-ttu-id="6fcbc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6fcbc-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="6fcbc-107">希望体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="6fcbc-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="6fcbc-108">你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="6fcbc-109">Microsoft 365 Defender 中的事件是关联警报和关联数据的集合，这些警报和关联数据是攻击案例的一部分。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="6fcbc-110">Microsoft 365服务和应用在检测到可疑或恶意事件或活动时创建警报。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="6fcbc-111">个别警报提供有关已完成或持续攻击的有价值的线索。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="6fcbc-112">但是，攻击通常对不同类型的实体（如设备、用户和邮箱）使用各种技术。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="6fcbc-113">结果是租户中多个实体收到多个警报。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="6fcbc-114">由于将各个警报分组在一起以深入了解攻击可能非常困难且耗时，Microsoft 365 Defender 会自动将警报及其相关信息聚合到事件中。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Defender Microsoft 365将实体中的事件关联到事件":::

<span data-ttu-id="6fcbc-116">观看此有关 Microsoft 365 Defender 中事件的简短 (4 分钟) 。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="6fcbc-117">将相关警报分组到事件可为你提供攻击的全面视图。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="6fcbc-118">例如，可以看到：</span><span class="sxs-lookup"><span data-stu-id="6fcbc-118">For example, you can see:</span></span>

- <span data-ttu-id="6fcbc-119">攻击的开始位置。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-119">Where the attack started.</span></span>
- <span data-ttu-id="6fcbc-120">使用了哪些策略。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-120">What tactics were used.</span></span>
- <span data-ttu-id="6fcbc-121">攻击已进入你的租户多远。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="6fcbc-122">攻击范围，如影响的设备、用户和邮箱数量。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="6fcbc-123">与攻击关联的所有数据。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="6fcbc-124">如果[启用](m365d-enable.md)，Microsoft 365 Defender[可以通过自动化和](m365d-autoir.md)人工智能自动调查和解决警报。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="6fcbc-125">还可以执行其他修正步骤来解决攻击。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="6fcbc-126">安全中心内Microsoft 365和警报</span><span class="sxs-lookup"><span data-stu-id="6fcbc-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="6fcbc-127">在快速启动 Microsoft 365安全中心&事件>事件 (security.microsoft.com) 。 [](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="6fcbc-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="6fcbc-128">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="安全中心内Microsoft 365页面":::

<span data-ttu-id="6fcbc-130">选择事件名称将显示事件摘要，并提供对包含其他信息的选项卡的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="安全中心内事件的&quot;摘要&quot;Microsoft 365示例":::

<span data-ttu-id="6fcbc-132">事件的其他选项卡包括：</span><span class="sxs-lookup"><span data-stu-id="6fcbc-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="6fcbc-133">警报</span><span class="sxs-lookup"><span data-stu-id="6fcbc-133">Alerts</span></span> 

  <span data-ttu-id="6fcbc-134">与事件及其信息相关的所有警报。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="6fcbc-135">设备</span><span class="sxs-lookup"><span data-stu-id="6fcbc-135">Devices</span></span>

  <span data-ttu-id="6fcbc-136">标识为事件的一部分或与事件相关的所有设备。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="6fcbc-137">用户</span><span class="sxs-lookup"><span data-stu-id="6fcbc-137">Users</span></span>

  <span data-ttu-id="6fcbc-138">标识为事件的一部分或与事件相关的所有用户。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="6fcbc-139">邮箱</span><span class="sxs-lookup"><span data-stu-id="6fcbc-139">Mailboxes</span></span>

  <span data-ttu-id="6fcbc-140">已标识为事件的一部分或与事件相关的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="6fcbc-141">调查</span><span class="sxs-lookup"><span data-stu-id="6fcbc-141">Investigations</span></span>

  <span data-ttu-id="6fcbc-142">事件 [警报](m365d-autoir.md) 触发的所有自动调查。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="6fcbc-143">证据和响应</span><span class="sxs-lookup"><span data-stu-id="6fcbc-143">Evidence and Response</span></span>

  <span data-ttu-id="6fcbc-144">事件警报中支持的所有事件和可疑实体。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="6fcbc-145">Graph (预览版) </span><span class="sxs-lookup"><span data-stu-id="6fcbc-145">Graph (in preview)</span></span>

  <span data-ttu-id="6fcbc-146">显示警报与组织中受影响资产的连接的图。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="6fcbc-147">下面是事件及其数据与安全中心内事件选项卡Microsoft 365关系。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="事件及其数据与安全中心内事件选项卡Microsoft 365关系":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="6fcbc-149">Microsoft 365 Defender 的事件响应工作流示例</span><span class="sxs-lookup"><span data-stu-id="6fcbc-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="6fcbc-150">下面是响应安全中心内Microsoft 365事件Microsoft 365工作流。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="事件的事件响应工作流示例Microsoft 365":::

<span data-ttu-id="6fcbc-152">持续确定事件队列中用于分析和解决的最高优先级事件，并使它们做好响应准备。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="6fcbc-153">这是以下两者的组合：</span><span class="sxs-lookup"><span data-stu-id="6fcbc-153">This is a combination of:</span></span>

- <span data-ttu-id="6fcbc-154">[通过](incident-queue.md) 筛选和事件队列排序来确定最高优先级事件的会审。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="6fcbc-155">[通过](manage-incidents.md) 修改事件的标题、将其分配给分析员以及添加标签和注释来管理事件。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="6fcbc-156">对于每个事件，开始 [攻击和警报调查和分析](investigate-incidents.md)：</span><span class="sxs-lookup"><span data-stu-id="6fcbc-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   <span data-ttu-id="6fcbc-157">a.</span><span class="sxs-lookup"><span data-stu-id="6fcbc-157">a.</span></span> <span data-ttu-id="6fcbc-158">查看事件的摘要，了解事件的范围和严重性以及受影响实体 ("摘要"选项卡) 。 </span><span class="sxs-lookup"><span data-stu-id="6fcbc-158">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="6fcbc-159">b.</span><span class="sxs-lookup"><span data-stu-id="6fcbc-159">b.</span></span> <span data-ttu-id="6fcbc-160">开始分析警报，了解警报的来源、范围和严重性 (**警报** 选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-160">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="6fcbc-161">c.</span><span class="sxs-lookup"><span data-stu-id="6fcbc-161">c.</span></span> <span data-ttu-id="6fcbc-162">根据需要，在"设备、用户"和"邮箱"选项卡上 (受影响的设备、用户和) 。  </span><span class="sxs-lookup"><span data-stu-id="6fcbc-162">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="6fcbc-163">d.</span><span class="sxs-lookup"><span data-stu-id="6fcbc-163">d.</span></span> <span data-ttu-id="6fcbc-164">查看 Microsoft 365 Defender 如何 [自动解决某些](m365d-autoir.md)警报 **("调查**"选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-164">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="6fcbc-165">e.</span><span class="sxs-lookup"><span data-stu-id="6fcbc-165">e.</span></span> <span data-ttu-id="6fcbc-166">根据需要，使用事件数据集中的信息获取"证据和 (**响应** "选项卡) 。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-166">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="6fcbc-167">在分析之后或分析过程中，执行抑制，以减少攻击和安全威胁的任何额外影响。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-167">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="6fcbc-168">尽可能将租户资源还原到事件发生前的状态，从而从攻击中恢复。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-168">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="6fcbc-169">[解决](manage-incidents.md#resolve-incident) 事件并花时间了解事件后情况：</span><span class="sxs-lookup"><span data-stu-id="6fcbc-169">[Resolve](manage-incidents.md#resolve-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="6fcbc-170">了解攻击的类型及其影响。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-170">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="6fcbc-171">研究威胁分析 [和安全](threat-analytics.md) 社区中的攻击，以寻找安全攻击趋势。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-171">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="6fcbc-172">重新调用用于解决事件的工作流，并根据需要更新标准工作流、流程、策略和操作手册。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-172">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="6fcbc-173">确定是否需要更改安全配置，并实施这些更改。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-173">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="6fcbc-174">如果你是安全分析的新增人员，请参阅第一[](incidents-overview.md)个事件响应简介，了解其他信息并逐步查看示例事件。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-174">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="6fcbc-175">Microsoft 365 Defender 的安全操作示例</span><span class="sxs-lookup"><span data-stu-id="6fcbc-175">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="6fcbc-176">下面是适用于 defender 的安全操作Microsoft 365示例。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-176">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Micosoft 365 Defender 的安全操作示例":::

<span data-ttu-id="6fcbc-178">日常任务可能包括：</span><span class="sxs-lookup"><span data-stu-id="6fcbc-178">Daily tasks can include:</span></span>

- <span data-ttu-id="6fcbc-179">[管理](manage-incidents.md) 事件</span><span class="sxs-lookup"><span data-stu-id="6fcbc-179">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="6fcbc-180">查看 [操作中心中的 AIR (AIR) ](m365d-action-center.md) 操作自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="6fcbc-180">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="6fcbc-181">查看最新的 [威胁分析](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="6fcbc-181">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="6fcbc-182">[响应](investigate-incidents.md) 事件</span><span class="sxs-lookup"><span data-stu-id="6fcbc-182">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="6fcbc-183">每月任务可能包括：</span><span class="sxs-lookup"><span data-stu-id="6fcbc-183">Monthly tasks can include:</span></span>

- <span data-ttu-id="6fcbc-184">查看 [AIR 设置](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="6fcbc-184">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="6fcbc-185">查看[安全分数和](microsoft-secure-score-improvement-actions.md)[威胁&漏洞管理](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="6fcbc-185">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="6fcbc-186">报告给 IT 安全管理链</span><span class="sxs-lookup"><span data-stu-id="6fcbc-186">Reporting to your IT security management chain</span></span>

<span data-ttu-id="6fcbc-187">季度任务可包括向 CISO (首席信息安全官报告并) 。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-187">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="6fcbc-188">年度任务可能包括执行重大事件或泄露练习，以测试员工、系统和流程。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-188">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="6fcbc-189">每日、每月、季度和年度任务可用于更新或优化流程、策略和安全配置。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-189">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6fcbc-190">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6fcbc-190">Next steps</span></span>

<span data-ttu-id="6fcbc-191">**如果你是安全分析和** 事件响应的新增人员：</span><span class="sxs-lookup"><span data-stu-id="6fcbc-191">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="6fcbc-192">请参阅[响应你的](first-incident-overview.md)第一个事件演练，获取有关 Microsoft 365 安全中心中分析、修正和事后评审的典型流程的引导教程，并查看攻击示例。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-192">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 security center with an example of an attack.</span></span>

<span data-ttu-id="6fcbc-193">**如果你有安全分析和** 事件响应的经验：</span><span class="sxs-lookup"><span data-stu-id="6fcbc-193">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="6fcbc-194">从安全中心的事件 **页面开始Microsoft 365** 队列。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-194">Get started with the incident queue from the **Incidents** page of the Microsoft 365 security center.</span></span> <span data-ttu-id="6fcbc-195">在这里，你可以：</span><span class="sxs-lookup"><span data-stu-id="6fcbc-195">From here, you can:</span></span>

  - <span data-ttu-id="6fcbc-196">查看应基于严重性 [和](incident-queue.md) 其他因素对哪些事件进行优先排序。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-196">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="6fcbc-197">[管理事件](manage-incidents.md)，其中包括重命名、分配、分类以及根据事件管理工作流添加标记和注释。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-197">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="6fcbc-198">[执行事件](investigate-incidents.md)调查。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-198">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="6fcbc-199">请参阅 [这些事件响应手册，](https://docs.microsoft.com/security/compass/incident-response-playbooks) 获取网络钓鱼、密码加密以及应用许可授予攻击的详细指南。</span><span class="sxs-lookup"><span data-stu-id="6fcbc-199">See these [incident response playbooks](https://docs.microsoft.com/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

