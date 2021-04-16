---
title: 调查 Microsoft 365 Defender 中的警报
description: 调查跨设备、用户和邮箱看到的警报。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
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
ms.openlocfilehash: 77b30e8a8eee70470115bcd61f081863fa5a41ee
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861982"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="0b17f-104">调查 Microsoft 365 Defender 中的警报</span><span class="sxs-lookup"><span data-stu-id="0b17f-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0b17f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0b17f-105">**Applies to:**</span></span>
- <span data-ttu-id="0b17f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b17f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0b17f-107">警报是所有事件的基础，指示环境中出现恶意或可疑事件。</span><span class="sxs-lookup"><span data-stu-id="0b17f-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="0b17f-108">警报通常是更广泛的攻击的一部分，并提供事件线索。</span><span class="sxs-lookup"><span data-stu-id="0b17f-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="0b17f-109">在 Microsoft 365 Defender 中，相关警报聚合在一起以形成 [事件](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0b17f-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="0b17f-110">事件将始终提供攻击的更广泛的上下文，但是，当需要深入分析时，调查警报可能非常有价值。</span><span class="sxs-lookup"><span data-stu-id="0b17f-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="0b17f-111">警报 **队列** 显示当前警报集。</span><span class="sxs-lookup"><span data-stu-id="0b17f-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="0b17f-112">在 microsoft 365安全中心 & > () 快速启动时，你可以从事件和警报[ (security.microsoft.com) 。](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0b17f-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="警报队列示例":::

<span data-ttu-id="0b17f-114">来自不同 Microsoft 安全解决方案（如 Microsoft Defender for Endpoint、Microsoft Defender for Office 365 和 Microsoft 365 Defender）的警报显示在此处。</span><span class="sxs-lookup"><span data-stu-id="0b17f-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="0b17f-115">默认情况下，Microsoft 365 安全中心中的警报队列显示过去 30 天内的新警报和正在进行中的警报。</span><span class="sxs-lookup"><span data-stu-id="0b17f-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="0b17f-116">最新警报位于列表顶部，因此你可以先查看它。</span><span class="sxs-lookup"><span data-stu-id="0b17f-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="0b17f-117">从默认警报队列中，可以选择"筛选器"以查看"筛选器"窗格，可以从中指定警报的子集。</span><span class="sxs-lookup"><span data-stu-id="0b17f-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="0b17f-118">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="0b17f-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="警报队列的筛选器窗格示例":::

<span data-ttu-id="0b17f-120">你可以根据以下条件筛选警报：</span><span class="sxs-lookup"><span data-stu-id="0b17f-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="0b17f-121">Severity</span><span class="sxs-lookup"><span data-stu-id="0b17f-121">Severity</span></span>
- <span data-ttu-id="0b17f-122">状态</span><span class="sxs-lookup"><span data-stu-id="0b17f-122">Status</span></span>
- <span data-ttu-id="0b17f-123">类别</span><span class="sxs-lookup"><span data-stu-id="0b17f-123">Category</span></span>
- <span data-ttu-id="0b17f-124">检测源</span><span class="sxs-lookup"><span data-stu-id="0b17f-124">Detection source</span></span>
- <span data-ttu-id="0b17f-125">标记</span><span class="sxs-lookup"><span data-stu-id="0b17f-125">Tags</span></span>
- <span data-ttu-id="0b17f-126">Policy</span><span class="sxs-lookup"><span data-stu-id="0b17f-126">Policy</span></span>
- <span data-ttu-id="0b17f-127">影响的资产</span><span class="sxs-lookup"><span data-stu-id="0b17f-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="0b17f-128">分析警报</span><span class="sxs-lookup"><span data-stu-id="0b17f-128">Analyze an alert</span></span>

<span data-ttu-id="0b17f-129">若要查看主警报页面，请选择警报的名称。</span><span class="sxs-lookup"><span data-stu-id="0b17f-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="0b17f-130">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="0b17f-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 安全中心中警报的详细信息页面示例":::

<span data-ttu-id="0b17f-132">您还可以从"管理 **警报"窗格中** 选择"打开主警报 **页面"** 操作。</span><span class="sxs-lookup"><span data-stu-id="0b17f-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="0b17f-133">警报页面由以下部分组成：</span><span class="sxs-lookup"><span data-stu-id="0b17f-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="0b17f-134">警报情景</span><span class="sxs-lookup"><span data-stu-id="0b17f-134">Alert story</span></span>
- <span data-ttu-id="0b17f-135">采取 (包括受影响资产) </span><span class="sxs-lookup"><span data-stu-id="0b17f-135">Actions taken (including impacted assets)</span></span>
- <span data-ttu-id="0b17f-136">相关事件</span><span class="sxs-lookup"><span data-stu-id="0b17f-136">Related events</span></span>
- <span data-ttu-id="0b17f-137">摘要详细信息</span><span class="sxs-lookup"><span data-stu-id="0b17f-137">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 安全中心中警报的详细信息页面示例":::

<span data-ttu-id="0b17f-139">在整个警报页面中，可以选择任何实体 **(...")** 查看可用操作，例如打开特定资产页面或执行特定的修正步骤。</span><span class="sxs-lookup"><span data-stu-id="0b17f-139">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the specific asset page or taking specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="0b17f-140">分析受影响的资产</span><span class="sxs-lookup"><span data-stu-id="0b17f-140">Analyze affected assets</span></span>

<span data-ttu-id="0b17f-141">" **已采取** 操作"部分包含受影响资产的列表，如受此警报影响的邮箱、设备和用户。</span><span class="sxs-lookup"><span data-stu-id="0b17f-141">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="0b17f-142">还可以选择"在操作中心 **中** 查看"以查看Microsoft 365 安全中心操作中心的"历史记录"选项卡。 </span><span class="sxs-lookup"><span data-stu-id="0b17f-142">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="0b17f-143">跟踪警报情景中的警报角色</span><span class="sxs-lookup"><span data-stu-id="0b17f-143">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="0b17f-144">警报情景在进程树视图中显示与警报相关的所有资产或实体。</span><span class="sxs-lookup"><span data-stu-id="0b17f-144">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="0b17f-145">标题中的警报是首次登录所选警报的页面时聚焦的警报。</span><span class="sxs-lookup"><span data-stu-id="0b17f-145">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="0b17f-146">警报情景中的资源可展开且可单击。</span><span class="sxs-lookup"><span data-stu-id="0b17f-146">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="0b17f-147">它们提供其他信息，并允许你立即在警报页面上下文中采取措施，从而加快响应速度。</span><span class="sxs-lookup"><span data-stu-id="0b17f-147">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="0b17f-148">警报情景部分可能包含多个警报，与相同执行树相关的其他警报显示在所选警报之前或之后。</span><span class="sxs-lookup"><span data-stu-id="0b17f-148">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="0b17f-149">在详细信息页面上查看更多警报信息</span><span class="sxs-lookup"><span data-stu-id="0b17f-149">View more alert information on the details page</span></span>

<span data-ttu-id="0b17f-150">详细信息页面显示所选警报的详细信息，以及相关详细信息和操作。</span><span class="sxs-lookup"><span data-stu-id="0b17f-150">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="0b17f-151">如果在警报情景中选择任何受影响的资产或实体，详细信息页面将发生更改，以提供所选对象的上下文信息和操作。</span><span class="sxs-lookup"><span data-stu-id="0b17f-151">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="0b17f-152">选择感兴趣的实体后，详细信息页面将发生更改以显示有关所选实体类型的信息、可用时的历史信息以及直接从警报页面对此实体采取措施的选项。</span><span class="sxs-lookup"><span data-stu-id="0b17f-152">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="0b17f-153">管理警报</span><span class="sxs-lookup"><span data-stu-id="0b17f-153">Manage alerts</span></span>

<span data-ttu-id="0b17f-154">若要管理警报，请在警报队列中的行中选择警报，以查看"管理 **警报"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="0b17f-154">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="0b17f-155">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="0b17f-155">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="警报的摘要窗格示例":::

<span data-ttu-id="0b17f-157">" **管理警报** "窗格允许您指定：</span><span class="sxs-lookup"><span data-stu-id="0b17f-157">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="0b17f-158">警报状态 (新建、已解决、正在进行) 。</span><span class="sxs-lookup"><span data-stu-id="0b17f-158">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="0b17f-159">警报的分类 (未设置、真警报、假警报) 。</span><span class="sxs-lookup"><span data-stu-id="0b17f-159">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="0b17f-160">对于分类为真正的警报，为"确定"字段中警报 **的威胁** 类型。</span><span class="sxs-lookup"><span data-stu-id="0b17f-160">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="0b17f-161">对警报的注释。</span><span class="sxs-lookup"><span data-stu-id="0b17f-161">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="0b17f-162">通过标记管理警报的一种方法。</span><span class="sxs-lookup"><span data-stu-id="0b17f-162">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="0b17f-163">Microsoft Defender for Office 365 的标记功能正在逐步推出，目前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="0b17f-163">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="0b17f-164">目前，修改的标记名称仅适用于更新后 *创建的* 警报。</span><span class="sxs-lookup"><span data-stu-id="0b17f-164">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="0b17f-165">修改之前生成的通知不会反映更新的标记名称。</span><span class="sxs-lookup"><span data-stu-id="0b17f-165">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="0b17f-166">在此窗格中，您还可以执行以下附加操作：</span><span class="sxs-lookup"><span data-stu-id="0b17f-166">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="0b17f-167">打开主警报页面</span><span class="sxs-lookup"><span data-stu-id="0b17f-167">Open the main alert page</span></span>
- <span data-ttu-id="0b17f-168">咨询 Microsoft 威胁专家</span><span class="sxs-lookup"><span data-stu-id="0b17f-168">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="0b17f-169">查看提交</span><span class="sxs-lookup"><span data-stu-id="0b17f-169">View submission</span></span>
- <span data-ttu-id="0b17f-170">链接到其他事件</span><span class="sxs-lookup"><span data-stu-id="0b17f-170">Link to another incident</span></span>
- <span data-ttu-id="0b17f-171">在时间线中查看警报</span><span class="sxs-lookup"><span data-stu-id="0b17f-171">See the alert in a timeline</span></span>
- <span data-ttu-id="0b17f-172">创建抑制规则</span><span class="sxs-lookup"><span data-stu-id="0b17f-172">Create a suppression rule</span></span>

<span data-ttu-id="0b17f-173">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="0b17f-173">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Microsoft 365 安全中心中警报的操作示例":::

<span data-ttu-id="0b17f-175">其他操作的列表取决于警报的类型。</span><span class="sxs-lookup"><span data-stu-id="0b17f-175">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="0b17f-176">解决警报</span><span class="sxs-lookup"><span data-stu-id="0b17f-176">Resolve an alert</span></span>

<span data-ttu-id="0b17f-177">调查完警报并可以解决后，请转到警报的"管理警报"窗格，将其状态标记为"已解决"，然后将其分类为 **"False 警报**"或"**真警报"。**</span><span class="sxs-lookup"><span data-stu-id="0b17f-177">Once you're done investigating an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="0b17f-178">对于真正的警报，在"确定"字段中指定警报 **的威胁** 类型。</span><span class="sxs-lookup"><span data-stu-id="0b17f-178">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="0b17f-179">对警报进行分类并指定它们的决定有助于调整 Microsoft 365 Defender，以提供更真实的警报和更少的假警报。</span><span class="sxs-lookup"><span data-stu-id="0b17f-179">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b17f-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b17f-180">See also</span></span>

- [<span data-ttu-id="0b17f-181">事件概述</span><span class="sxs-lookup"><span data-stu-id="0b17f-181">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="0b17f-182">调查事件</span><span class="sxs-lookup"><span data-stu-id="0b17f-182">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="0b17f-183">管理事件</span><span class="sxs-lookup"><span data-stu-id="0b17f-183">Manage incidents</span></span>](manage-incidents.md)
