---
title: 调查 Microsoft 365 Defender 中的警报
description: 调查跨设备、用户和邮箱看到的警报。
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
ms.openlocfilehash: a6e11aea14a7b8d99c0098b68951790328ec593e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782905"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="71207-104">调查 Microsoft 365 Defender 中的警报</span><span class="sxs-lookup"><span data-stu-id="71207-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="71207-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="71207-105">**Applies to:**</span></span>
- <span data-ttu-id="71207-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71207-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="71207-107">警报是所有事件的基础，指示环境中出现恶意或可疑事件。</span><span class="sxs-lookup"><span data-stu-id="71207-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="71207-108">警报通常是更广泛的攻击的一部分，并提供事件线索。</span><span class="sxs-lookup"><span data-stu-id="71207-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="71207-109">在 Microsoft 365 Defender 中，相关警报聚合在一起以形成[事件](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="71207-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="71207-110">事件将始终提供更广泛的攻击上下文，但是，如果需要更深入的分析，分析警报可能会非常有价值。</span><span class="sxs-lookup"><span data-stu-id="71207-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="71207-111">警报 **队列** 显示当前警报集。</span><span class="sxs-lookup"><span data-stu-id="71207-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="71207-112">在快速启动 Microsoft 365 安全中心 (security.microsoft.com) 时，你可以从事件&警报>警报["进入警报](https://security.microsoft.com)队列。</span><span class="sxs-lookup"><span data-stu-id="71207-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="警报队列示例":::

<span data-ttu-id="71207-114">来自不同 Microsoft 安全解决方案（如 Microsoft Defender for Endpoint、Microsoft Defender for Office 365 和 Microsoft 365 Defender）的警报显示在此处。</span><span class="sxs-lookup"><span data-stu-id="71207-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="71207-115">默认情况下，安全中心中的警报队列Microsoft 365最近 30 天的新警报和正在进行中的警报。</span><span class="sxs-lookup"><span data-stu-id="71207-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="71207-116">最新警报位于列表顶部，因此你可以先查看它。</span><span class="sxs-lookup"><span data-stu-id="71207-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="71207-117">从默认警报队列中，可以选择"筛选器"以查看"筛选器"窗格，可以从中指定警报的子集。</span><span class="sxs-lookup"><span data-stu-id="71207-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="71207-118">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="71207-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="警报队列的筛选器窗格示例":::

<span data-ttu-id="71207-120">你可以根据以下条件筛选警报：</span><span class="sxs-lookup"><span data-stu-id="71207-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="71207-121">严重性</span><span class="sxs-lookup"><span data-stu-id="71207-121">Severity</span></span>
- <span data-ttu-id="71207-122">状态</span><span class="sxs-lookup"><span data-stu-id="71207-122">Status</span></span>
- <span data-ttu-id="71207-123">Category</span><span class="sxs-lookup"><span data-stu-id="71207-123">Category</span></span>
- <span data-ttu-id="71207-124">检测源</span><span class="sxs-lookup"><span data-stu-id="71207-124">Detection source</span></span>
- <span data-ttu-id="71207-125">标记</span><span class="sxs-lookup"><span data-stu-id="71207-125">Tags</span></span>
- <span data-ttu-id="71207-126">策略</span><span class="sxs-lookup"><span data-stu-id="71207-126">Policy</span></span>
- <span data-ttu-id="71207-127">影响的资产</span><span class="sxs-lookup"><span data-stu-id="71207-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="71207-128">分析警报</span><span class="sxs-lookup"><span data-stu-id="71207-128">Analyze an alert</span></span>

<span data-ttu-id="71207-129">若要查看主警报页面，请选择警报的名称。</span><span class="sxs-lookup"><span data-stu-id="71207-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="71207-130">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="71207-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="安全中心内警报Microsoft 365示例":::

<span data-ttu-id="71207-132">您还可以从"管理 **警报"窗格中** 选择"打开主警报 **页面"** 操作。</span><span class="sxs-lookup"><span data-stu-id="71207-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="71207-133">警报页面由以下部分组成：</span><span class="sxs-lookup"><span data-stu-id="71207-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="71207-134">警报情景，它是与此警报相关的事件和警报链（按时间顺序）</span><span class="sxs-lookup"><span data-stu-id="71207-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="71207-135">摘要详细信息</span><span class="sxs-lookup"><span data-stu-id="71207-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="安全中心内警报Microsoft 365示例":::

<span data-ttu-id="71207-137">在整个警报页面中，可以选择任意实体旁边的省略号 (**...)** 以查看可用操作，例如打开警报页面或将警报链接到其他事件。</span><span class="sxs-lookup"><span data-stu-id="71207-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="alert-sources"></a><span data-ttu-id="71207-138">警报源</span><span class="sxs-lookup"><span data-stu-id="71207-138">Alert sources</span></span>
<span data-ttu-id="71207-139">Microsoft 365Defender 警报可能来自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365 和 Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="71207-139">Microsoft 365 Defender alerts may come from solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft Cloud App Security.</span></span> <span data-ttu-id="71207-140">你可能会注意到警报中具有预置字符的警报。</span><span class="sxs-lookup"><span data-stu-id="71207-140">You may notice alerts with prepended characters in the alert.</span></span> <span data-ttu-id="71207-141">下表提供了一些指南，可帮助你根据警报上的预pend字符了解警报源的映射。</span><span class="sxs-lookup"><span data-stu-id="71207-141">The following table provides guidance to help you understand the mapping of alert sources based on the prepended character on the alert.</span></span>

> [!NOTE]
> - <span data-ttu-id="71207-142">预置的 GUID 仅特定于统一体验，如统一警报队列、统一警报页面、统一调查和统一事件。</span><span class="sxs-lookup"><span data-stu-id="71207-142">The prepended GUIDs are specific only to unified experiences such as unified alerts queue, unified alerts page, unified investigation, and unified incident.</span></span><br>
> - <span data-ttu-id="71207-143">预置字符不会更改警报的 GUID。</span><span class="sxs-lookup"><span data-stu-id="71207-143">The prepended character does not change the GUID of the alert.</span></span> <span data-ttu-id="71207-144">对 GUID 的唯一更改是预置的组件。</span><span class="sxs-lookup"><span data-stu-id="71207-144">The only change to the GUID is the prepended component.</span></span><br>


<span data-ttu-id="71207-145">警报源</span><span class="sxs-lookup"><span data-stu-id="71207-145">Alert source</span></span> | <span data-ttu-id="71207-146">Prepended 字符</span><span class="sxs-lookup"><span data-stu-id="71207-146">Prepended character</span></span> 
:---|:---
<span data-ttu-id="71207-147">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="71207-147">Microsoft Defender for Office 365</span></span> | `fa{GUID}` <br> <span data-ttu-id="71207-148">例如：`fa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="71207-148">Example: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="71207-149">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="71207-149">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="71207-150">`da` 或 `ed` 用于自定义检测警报</span><span class="sxs-lookup"><span data-stu-id="71207-150">`da` or `ed` for custom detection alerts</span></span> <br> 
<span data-ttu-id="71207-151">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="71207-151">Microsoft Defender for Identity</span></span> | `aa{GUID}` <br> <span data-ttu-id="71207-152">例如：`aa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="71207-152">Example: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="71207-153">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="71207-153">Microsoft Cloud App Security</span></span> |`ca{GUID}` <br> <span data-ttu-id="71207-154">例如：`ca123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="71207-154">Example: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 



### <a name="analyze-affected-assets"></a><span data-ttu-id="71207-155">分析受影响的资产</span><span class="sxs-lookup"><span data-stu-id="71207-155">Analyze affected assets</span></span>

<span data-ttu-id="71207-156">" **已采取** 操作"部分包含受影响资产的列表，如受此警报影响的邮箱、设备和用户。</span><span class="sxs-lookup"><span data-stu-id="71207-156">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="71207-157">还可以选择"在操作中心 **中** 查看"以查看安全中心内操作中心的Microsoft 365选项卡。</span><span class="sxs-lookup"><span data-stu-id="71207-157">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="71207-158">跟踪警报情景中的警报角色</span><span class="sxs-lookup"><span data-stu-id="71207-158">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="71207-159">警报情景在进程树视图中显示与警报相关的所有资产或实体。</span><span class="sxs-lookup"><span data-stu-id="71207-159">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="71207-160">标题中的警报是首次登录所选警报的页面时聚焦的警报。</span><span class="sxs-lookup"><span data-stu-id="71207-160">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="71207-161">警报情景中的资源可展开且可单击。</span><span class="sxs-lookup"><span data-stu-id="71207-161">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="71207-162">它们提供其他信息，并允许你立即在警报页面上下文中采取措施，从而加快响应速度。</span><span class="sxs-lookup"><span data-stu-id="71207-162">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="71207-163">警报情景部分可能包含多个警报，与相同执行树相关的其他警报显示在所选警报之前或之后。</span><span class="sxs-lookup"><span data-stu-id="71207-163">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="71207-164">在详细信息页面上查看更多警报信息</span><span class="sxs-lookup"><span data-stu-id="71207-164">View more alert information on the details page</span></span>

<span data-ttu-id="71207-165">详细信息页面显示所选警报的详细信息，以及相关详细信息和操作。</span><span class="sxs-lookup"><span data-stu-id="71207-165">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="71207-166">如果在警报情景中选择任何受影响的资产或实体，详细信息页面将发生更改，以提供所选对象的上下文信息和操作。</span><span class="sxs-lookup"><span data-stu-id="71207-166">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="71207-167">选择感兴趣的实体后，详细信息页面将发生更改以显示有关所选实体类型的信息、可用时的历史信息以及直接从警报页面对此实体采取措施的选项。</span><span class="sxs-lookup"><span data-stu-id="71207-167">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="71207-168">管理警报</span><span class="sxs-lookup"><span data-stu-id="71207-168">Manage alerts</span></span>

<span data-ttu-id="71207-169">若要管理警报，请在警报队列中的行中选择警报，以查看"管理 **警报"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="71207-169">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="71207-170">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="71207-170">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="警报的摘要窗格示例":::

<span data-ttu-id="71207-172">" **管理警报** "窗格允许您指定：</span><span class="sxs-lookup"><span data-stu-id="71207-172">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="71207-173">警报状态 (新建、已解决、正在进行) 。</span><span class="sxs-lookup"><span data-stu-id="71207-173">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="71207-174">警报的分类 (未设置、真警报、假警报) 。</span><span class="sxs-lookup"><span data-stu-id="71207-174">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="71207-175">对于分类为真正的警报，为"确定"字段中警报 **的威胁** 类型。</span><span class="sxs-lookup"><span data-stu-id="71207-175">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="71207-176">对警报的注释。</span><span class="sxs-lookup"><span data-stu-id="71207-176">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="71207-177">通过标记管理警报的一种方法。</span><span class="sxs-lookup"><span data-stu-id="71207-177">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="71207-178">Microsoft Defender for Office 365 的标记功能正在逐步推出，目前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="71207-178">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="71207-179">目前，修改的标记名称仅适用于更新后 *创建的* 警报。</span><span class="sxs-lookup"><span data-stu-id="71207-179">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="71207-180">修改之前生成的通知不会反映更新的标记名称。</span><span class="sxs-lookup"><span data-stu-id="71207-180">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="71207-181">在此窗格中，您还可以执行以下附加操作：</span><span class="sxs-lookup"><span data-stu-id="71207-181">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="71207-182">打开主警报页面</span><span class="sxs-lookup"><span data-stu-id="71207-182">Open the main alert page</span></span>
- <span data-ttu-id="71207-183">咨询 Microsoft 威胁专家</span><span class="sxs-lookup"><span data-stu-id="71207-183">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="71207-184">查看提交</span><span class="sxs-lookup"><span data-stu-id="71207-184">View submission</span></span>
- <span data-ttu-id="71207-185">链接到其他事件</span><span class="sxs-lookup"><span data-stu-id="71207-185">Link to another incident</span></span>
- <span data-ttu-id="71207-186">在时间线中查看警报</span><span class="sxs-lookup"><span data-stu-id="71207-186">See the alert in a timeline</span></span>
- <span data-ttu-id="71207-187">创建抑制规则</span><span class="sxs-lookup"><span data-stu-id="71207-187">Create a suppression rule</span></span>

<span data-ttu-id="71207-188">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="71207-188">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="安全中心内警报Microsoft 365示例":::

<span data-ttu-id="71207-190">其他操作的列表取决于警报的类型。</span><span class="sxs-lookup"><span data-stu-id="71207-190">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="71207-191">解决警报</span><span class="sxs-lookup"><span data-stu-id="71207-191">Resolve an alert</span></span>

<span data-ttu-id="71207-192">分析完警报并可以解决后，请转到警报的"管理警报"窗格，将其状态标记为"已解决"，并分类为 **"False** 警报"或"**真警报"。** </span><span class="sxs-lookup"><span data-stu-id="71207-192">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="71207-193">对于真正的警报，在"确定"字段中指定警报 **的威胁** 类型。</span><span class="sxs-lookup"><span data-stu-id="71207-193">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="71207-194">对警报进行分类并指定它们的决定有助于Microsoft 365 Defender，以提供更多真实警报和更少的假警报。</span><span class="sxs-lookup"><span data-stu-id="71207-194">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="71207-195">后续步骤</span><span class="sxs-lookup"><span data-stu-id="71207-195">Next steps</span></span>

<span data-ttu-id="71207-196">如果需要处理内事件，请继续执行 [调查](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="71207-196">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="71207-197">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71207-197">See also</span></span>

- [<span data-ttu-id="71207-198">事件概述</span><span class="sxs-lookup"><span data-stu-id="71207-198">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="71207-199">管理事件</span><span class="sxs-lookup"><span data-stu-id="71207-199">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="71207-200">调查事件</span><span class="sxs-lookup"><span data-stu-id="71207-200">Investigate incidents</span></span>](investigate-incidents.md)
