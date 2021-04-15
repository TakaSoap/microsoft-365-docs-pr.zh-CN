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
ms.openlocfilehash: 601a8674327c424592c65014793599dc19b2bcd3
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51759428"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="feb90-104">调查 Microsoft 365 Defender 中的警报</span><span class="sxs-lookup"><span data-stu-id="feb90-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="feb90-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="feb90-105">**Applies to:**</span></span>
- <span data-ttu-id="feb90-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="feb90-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="feb90-107">警报是所有事件的基础，指示环境中出现恶意或可疑事件。</span><span class="sxs-lookup"><span data-stu-id="feb90-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="feb90-108">警报通常是更广泛的攻击的一部分，并提供有关事件的线索片段。</span><span class="sxs-lookup"><span data-stu-id="feb90-108">Alerts are typically part of a broader attack and provide pieces of clues about an incident.</span></span>

<span data-ttu-id="feb90-109">在 Microsoft 365 Defender 中，相关警报聚合在一起以形成事件。</span><span class="sxs-lookup"><span data-stu-id="feb90-109">In Microsoft 365 Defender, related alerts are aggregated together to form incidents.</span></span> <span data-ttu-id="feb90-110">事件将始终提供攻击的更广泛的上下文，但是，当需要深入分析时，调查警报可能非常有价值。</span><span class="sxs-lookup"><span data-stu-id="feb90-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 



## <a name="using-alert-pages-in-investigations"></a><span data-ttu-id="feb90-111">在调查中使用警报页面</span><span class="sxs-lookup"><span data-stu-id="feb90-111">Using alert pages in investigations</span></span>

<span data-ttu-id="feb90-112">从任何事件页面的"警报"选项卡中，选择警报将您带到各个警报页面。</span><span class="sxs-lookup"><span data-stu-id="feb90-112">From the Alerts tab of any incident page, selecting an alert brings you to the individual alert pages.</span></span> <span data-ttu-id="feb90-113">警报页面由三个部分组成：受影响的资产、警报情景和详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="feb90-113">An alert page is composed of three sections: affected assets, alert story, and the details pane.</span></span>

![示例警报页面的图像](../../media/new-alert-page2.png)

<span data-ttu-id="feb90-115">在整个警报页面中，可以选择任何实体旁边的三点 (**...) ，** 以便你可以查看可用的操作，如打开特定资产页面或执行特定的修正步骤。</span><span class="sxs-lookup"><span data-stu-id="feb90-115">Throughout an alert page, you can select the three-dot icon (**...**) beside any entity so you can see available actions like opening the specific asset page or doing specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="feb90-116">分析受影响的资产</span><span class="sxs-lookup"><span data-stu-id="feb90-116">Analyze affected assets</span></span>
<span data-ttu-id="feb90-117">"受影响的资产"部分列出了受此警报影响的邮箱、设备和用户。</span><span class="sxs-lookup"><span data-stu-id="feb90-117">The affected assets section lists mailboxes, devices, and users affected by this alert.</span></span> <span data-ttu-id="feb90-118">选择任意资产卡会向详细信息侧窗格填充信息，包括涉及资产的其他警报（如果有）。</span><span class="sxs-lookup"><span data-stu-id="feb90-118">Selecting any of the asset cards populates the details side pane with information, including other alerts that occurred involving the assets, if any.</span></span>


### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="feb90-119">跟踪警报情景中的警报角色</span><span class="sxs-lookup"><span data-stu-id="feb90-119">Trace an alert's role in the alert story</span></span>
<span data-ttu-id="feb90-120">警报情景在进程树视图中显示与警报相关的所有资产或实体。</span><span class="sxs-lookup"><span data-stu-id="feb90-120">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="feb90-121">标题中的警报是首次登录所选警报的页面时聚焦的警报。</span><span class="sxs-lookup"><span data-stu-id="feb90-121">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="feb90-122">警报情景中的资源可展开且可单击。</span><span class="sxs-lookup"><span data-stu-id="feb90-122">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="feb90-123">它们通过允许您在警报页面上下文中采取措施来提供其他信息并加快响应速度。</span><span class="sxs-lookup"><span data-stu-id="feb90-123">They provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="feb90-124">警报情景部分可能包含多个警报，与相同执行树相关的其他警报显示在所选警报之前或之后。</span><span class="sxs-lookup"><span data-stu-id="feb90-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-in-the-details-pane"></a><span data-ttu-id="feb90-125">在详细信息窗格中查看更多警报信息</span><span class="sxs-lookup"><span data-stu-id="feb90-125">View more alert information in the details pane</span></span>

<span data-ttu-id="feb90-126">细节窗格首先显示所选警报的详细信息，以及相关详细信息和操作。</span><span class="sxs-lookup"><span data-stu-id="feb90-126">The details pane shows the details of the selected alert at first, with details and actions related to it.</span></span> <span data-ttu-id="feb90-127">如果在警报情景中选择任何受影响的资产或实体，详细信息窗格将发生更改，以提供所选对象的上下文信息和操作。</span><span class="sxs-lookup"><span data-stu-id="feb90-127">If you select any of the affected assets or entities in the alert story, the details pane changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="feb90-128">选择感兴趣的实体后，详细信息窗格将发生更改，以显示有关所选实体类型的信息、可用时的历史信息以及直接从警报页面对此实体采取措施的选项。</span><span class="sxs-lookup"><span data-stu-id="feb90-128">Once you've selected an entity of interest, the details pane changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

### <a name="manage-alerts"></a><span data-ttu-id="feb90-129">管理警报</span><span class="sxs-lookup"><span data-stu-id="feb90-129">Manage alerts</span></span>

<span data-ttu-id="feb90-130">调查完警报后，可以返回到开始使用的警报，将警报状态标记为"已解决"，然后将其分类为"False 警报"或"真警报"。</span><span class="sxs-lookup"><span data-stu-id="feb90-130">Once you're done investigating the alerts, you can go back to the alert you started with, mark the alert's status as Resolved and classify it as either a False alert or True alert.</span></span> <span data-ttu-id="feb90-131">对警报进行分类有助于调整产品，以提供更多真实警报和更少的假警报。</span><span class="sxs-lookup"><span data-stu-id="feb90-131">Classifying alerts helps tune your product to provide more true alerts and less false alerts.</span></span>

> [!NOTE]
> <span data-ttu-id="feb90-132">通过标记管理警报的一种方法。</span><span class="sxs-lookup"><span data-stu-id="feb90-132">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="feb90-133">Microsoft Defender for Office 365 的标记功能正在逐步推出，目前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="feb90-133">The tagging capability for Microsoft Defender for Office 365 in incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="feb90-134">目前，修改的标记名称仅适用于更新后 *创建的* 警报。</span><span class="sxs-lookup"><span data-stu-id="feb90-134">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="feb90-135">修改之前生成的通知不会反映更新的标记名称。</span><span class="sxs-lookup"><span data-stu-id="feb90-135">Alerts that were generated prior to the modification will not reflect the updated tag name.</span></span> 


## <a name="manage-the-unified-alert-queue"></a><span data-ttu-id="feb90-136">管理统一警报队列</span><span class="sxs-lookup"><span data-stu-id="feb90-136">Manage the unified alert queue</span></span>

<span data-ttu-id="feb90-137">选择 Microsoft 365 安全中心导航窗格中&警报"下的"警报"，可进入统一警报队列。</span><span class="sxs-lookup"><span data-stu-id="feb90-137">Selecting Alerts under Incidents & Alerts in the Microsoft 365 security center navigation pane brings you to the unified alert queue.</span></span> <span data-ttu-id="feb90-138">本部分中将显示来自不同 Microsoft 安全解决方案（如 Microsoft Defender for Endpoint、Microsoft Defender for Office 365 和 Microsoft 365 Defender）的警报。</span><span class="sxs-lookup"><span data-stu-id="feb90-138">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear in this section.</span></span> 

![示例警报页面的图像](../../media/unified-alert-queue.png)

<span data-ttu-id="feb90-140">警报队列显示网络中标记的警报列表。</span><span class="sxs-lookup"><span data-stu-id="feb90-140">The Alerts queue shows a list of alerts that were flagged in your network.</span></span> <span data-ttu-id="feb90-141">默认情况下，队列显示最近 30 天内看到的警报。</span><span class="sxs-lookup"><span data-stu-id="feb90-141">By default, the queue displays alerts seen in the last 30 days.</span></span> <span data-ttu-id="feb90-142">最新警报显示在列表顶部，有助于你先查看最新警报。</span><span class="sxs-lookup"><span data-stu-id="feb90-142">The most recent alerts are shown at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="feb90-143">在启动时，统一警报队列将只有 7 天的 Microsoft Defender for Office 365 警报可用。</span><span class="sxs-lookup"><span data-stu-id="feb90-143">At the time of launch, the unified alerts queue will only have 7 days’ worth of Microsoft Defender for Office 365 alerts available.</span></span> <span data-ttu-id="feb90-144">随着时间的推移，队列将继续构建。</span><span class="sxs-lookup"><span data-stu-id="feb90-144">The queue will continue to build over time.</span></span> <span data-ttu-id="feb90-145">如果需要在启动统一警报队列之前对警报进行会审，请使用安全与合规 [中心中的警报队列](https://protection.office.com/viewalerts)。</span><span class="sxs-lookup"><span data-stu-id="feb90-145">If you need to triage alerts prior to the launch of the unified alerts queue, use the alerts queue in the [Security and Compliance Center](https://protection.office.com/viewalerts).</span></span>


<span data-ttu-id="feb90-146">在顶部导航上，您可以：</span><span class="sxs-lookup"><span data-stu-id="feb90-146">On the top navigation, you can:</span></span>

- <span data-ttu-id="feb90-147">应用筛选器</span><span class="sxs-lookup"><span data-stu-id="feb90-147">Apply filters</span></span>
- <span data-ttu-id="feb90-148">自定义列以添加或删除列</span><span class="sxs-lookup"><span data-stu-id="feb90-148">Customize columns to add or remove columns</span></span>
- <span data-ttu-id="feb90-149">导出数据</span><span class="sxs-lookup"><span data-stu-id="feb90-149">Export data</span></span>

<span data-ttu-id="feb90-150">您还可以根据不同的条件筛选警报：</span><span class="sxs-lookup"><span data-stu-id="feb90-150">You can also filter alerts according to different criteria:</span></span>

- <span data-ttu-id="feb90-151">Severity</span><span class="sxs-lookup"><span data-stu-id="feb90-151">Severity</span></span>
- <span data-ttu-id="feb90-152">状态</span><span class="sxs-lookup"><span data-stu-id="feb90-152">Status</span></span>
- <span data-ttu-id="feb90-153">类别</span><span class="sxs-lookup"><span data-stu-id="feb90-153">Category</span></span>
- <span data-ttu-id="feb90-154">检测源</span><span class="sxs-lookup"><span data-stu-id="feb90-154">Detection source</span></span>
- <span data-ttu-id="feb90-155">Policy</span><span class="sxs-lookup"><span data-stu-id="feb90-155">Policy</span></span>
- <span data-ttu-id="feb90-156">影响的资产</span><span class="sxs-lookup"><span data-stu-id="feb90-156">Impacted assets</span></span>
- <span data-ttu-id="feb90-157">第一个活动</span><span class="sxs-lookup"><span data-stu-id="feb90-157">First activity</span></span>
- <span data-ttu-id="feb90-158">最后一次活动</span><span class="sxs-lookup"><span data-stu-id="feb90-158">Last activity</span></span>


<span data-ttu-id="feb90-159">若要开始调查事件，请阅读调查[Microsoft 365 Defender](investigate-incidents.md)中的事件</span><span class="sxs-lookup"><span data-stu-id="feb90-159">To start an investigation on an incident, read [Investigate incidents in Microsoft 365 Defender](investigate-incidents.md)</span></span>
## <a name="see-also"></a><span data-ttu-id="feb90-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="feb90-160">See also</span></span>

- [<span data-ttu-id="feb90-161">事件概述</span><span class="sxs-lookup"><span data-stu-id="feb90-161">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="feb90-162">调查事件</span><span class="sxs-lookup"><span data-stu-id="feb90-162">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="feb90-163">管理事件</span><span class="sxs-lookup"><span data-stu-id="feb90-163">Manage incidents</span></span>](manage-incidents.md)
