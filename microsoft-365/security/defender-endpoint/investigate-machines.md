---
title: 调查 Defender for Endpoint Devices 列表中的设备
description: 通过查看警报、网络连接信息、添加设备标记和组以及检查服务运行状况来调查受影响的设备。
keywords: 设备， 标记， 组， 终结点， 警报队列， 警报， 设备名称， 域， 上次看到时间， 内部 IP， 活动警报， 威胁类别， 筛选器， 排序， 查看警报， 网络， 连接， 类型， 密码窃取程序， 勒索软件， 攻击， 威胁， 低严重性， 服务运行状况
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c1e572910ad311daba18a8b0f5eeb546ffe36956
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929105"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="7b023-104">调查 Microsoft Defender 终结点设备列表中的设备</span><span class="sxs-lookup"><span data-stu-id="7b023-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7b023-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="7b023-105">**Applies to:**</span></span>
- [<span data-ttu-id="7b023-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7b023-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7b023-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b023-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7b023-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="7b023-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7b023-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="7b023-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="7b023-110">调查特定设备上引发警报的详细信息，以确定与警报或潜在泄露范围相关的其他行为或事件。</span><span class="sxs-lookup"><span data-stu-id="7b023-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="7b023-111">作为调查或响应过程的一部分，你可以从设备收集调查包。</span><span class="sxs-lookup"><span data-stu-id="7b023-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="7b023-112">操作说明： [从设备收集调查包](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices)。</span><span class="sxs-lookup"><span data-stu-id="7b023-112">Here's how: [Collect investigation package from devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="7b023-113">只要在门户中看到受影响的设备，就可以单击它们，以打开有关该设备的详细报告。</span><span class="sxs-lookup"><span data-stu-id="7b023-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="7b023-114">受影响的设备在以下方面进行标识：</span><span class="sxs-lookup"><span data-stu-id="7b023-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="7b023-115">设备列表</span><span class="sxs-lookup"><span data-stu-id="7b023-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="7b023-116">警报队列</span><span class="sxs-lookup"><span data-stu-id="7b023-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="7b023-117">安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="7b023-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="7b023-118">任何单个警报</span><span class="sxs-lookup"><span data-stu-id="7b023-118">Any individual alert</span></span>
- <span data-ttu-id="7b023-119">任何单个文件详细信息视图</span><span class="sxs-lookup"><span data-stu-id="7b023-119">Any individual file details view</span></span>
- <span data-ttu-id="7b023-120">任何 IP 地址或域详细信息视图</span><span class="sxs-lookup"><span data-stu-id="7b023-120">Any IP address or domain details view</span></span>

<span data-ttu-id="7b023-121">调查特定设备时，你将看到：</span><span class="sxs-lookup"><span data-stu-id="7b023-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="7b023-122">设备详细信息</span><span class="sxs-lookup"><span data-stu-id="7b023-122">Device details</span></span>
- <span data-ttu-id="7b023-123">响应操作</span><span class="sxs-lookup"><span data-stu-id="7b023-123">Response actions</span></span>
- <span data-ttu-id="7b023-124">选项卡 (概述、警报、时间线、安全建议、软件清单、发现的漏洞、缺少的) </span><span class="sxs-lookup"><span data-stu-id="7b023-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="7b023-125">卡片 (活动警报、已登录用户、安全评估) </span><span class="sxs-lookup"><span data-stu-id="7b023-125">Cards (active alerts, logged on users, security assessment)</span></span>

![设备视图的图像](images/specific-device.png)

## <a name="device-details"></a><span data-ttu-id="7b023-127">设备详细信息</span><span class="sxs-lookup"><span data-stu-id="7b023-127">Device details</span></span>

<span data-ttu-id="7b023-128">设备详细信息部分提供诸如设备的域、操作系统和运行状况等信息。</span><span class="sxs-lookup"><span data-stu-id="7b023-128">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="7b023-129">如果设备上有可用的调查包，你将看到一个链接，允许你下载该程序包。</span><span class="sxs-lookup"><span data-stu-id="7b023-129">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="7b023-130">响应操作</span><span class="sxs-lookup"><span data-stu-id="7b023-130">Response actions</span></span>

<span data-ttu-id="7b023-131">响应操作沿着特定设备页面的顶部运行，包括：</span><span class="sxs-lookup"><span data-stu-id="7b023-131">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="7b023-132">管理标签</span><span class="sxs-lookup"><span data-stu-id="7b023-132">Manage tags</span></span>
- <span data-ttu-id="7b023-133">隔离设备</span><span class="sxs-lookup"><span data-stu-id="7b023-133">Isolate device</span></span>
- <span data-ttu-id="7b023-134">限制应用执行</span><span class="sxs-lookup"><span data-stu-id="7b023-134">Restrict app execution</span></span>
- <span data-ttu-id="7b023-135">运行防病毒扫描</span><span class="sxs-lookup"><span data-stu-id="7b023-135">Run antivirus scan</span></span>
- <span data-ttu-id="7b023-136">收集调查程序包</span><span class="sxs-lookup"><span data-stu-id="7b023-136">Collect investigation package</span></span>
- <span data-ttu-id="7b023-137">启动实时响应会话</span><span class="sxs-lookup"><span data-stu-id="7b023-137">Initiate Live Response Session</span></span>
- <span data-ttu-id="7b023-138">启动自动调查</span><span class="sxs-lookup"><span data-stu-id="7b023-138">Initiate automated investigation</span></span>
- <span data-ttu-id="7b023-139">咨询威胁专家</span><span class="sxs-lookup"><span data-stu-id="7b023-139">Consult a threat expert</span></span>
- <span data-ttu-id="7b023-140">操作中心</span><span class="sxs-lookup"><span data-stu-id="7b023-140">Action center</span></span>

<span data-ttu-id="7b023-141">可以在操作中心、特定设备页或特定文件页中执行响应操作。</span><span class="sxs-lookup"><span data-stu-id="7b023-141">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="7b023-142">若要详细了解如何在设备上采取操作，请参阅 [在设备上执行响应操作](respond-machine-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="7b023-142">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="7b023-143">有关详细信息，请参阅调查 [用户实体](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="7b023-143">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="7b023-144">选项卡</span><span class="sxs-lookup"><span data-stu-id="7b023-144">Tabs</span></span>

<span data-ttu-id="7b023-145">选项卡提供与设备相关的安全和威胁防护信息。</span><span class="sxs-lookup"><span data-stu-id="7b023-145">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="7b023-146">在每个选项卡中，可以通过从列标题上方的栏中选择"自定义列"来自定义显示的列。</span><span class="sxs-lookup"><span data-stu-id="7b023-146">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="7b023-147">概述</span><span class="sxs-lookup"><span data-stu-id="7b023-147">Overview</span></span>
<span data-ttu-id="7b023-148">" **概述** "选项卡 [显示活动](#cards) 警报、已登录用户和安全评估的卡片。</span><span class="sxs-lookup"><span data-stu-id="7b023-148">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![设备页面上概述选项卡的图像](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="7b023-150">警报</span><span class="sxs-lookup"><span data-stu-id="7b023-150">Alerts</span></span>

<span data-ttu-id="7b023-151">警报 **选项卡** 提供与设备关联的警报列表。</span><span class="sxs-lookup"><span data-stu-id="7b023-151">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="7b023-152">此列表是警报队列的筛选版本，显示[](alerts-queue.md)警报、严重性 (高、中、低、信息) 、队列 (中的状态、新、正在进行、已解决) 、分类 (未设置、false 警报、真警报) 、调查状态、警报类别、解决警报的人和上次活动。</span><span class="sxs-lookup"><span data-stu-id="7b023-152">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="7b023-153">您还可以筛选警报。</span><span class="sxs-lookup"><span data-stu-id="7b023-153">You can also filter the alerts.</span></span>

![与设备相关的警报的图像](images/alerts-device.png)

<span data-ttu-id="7b023-155">当选择警报左侧的圆圈图标时，将出现一个飞出。</span><span class="sxs-lookup"><span data-stu-id="7b023-155">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="7b023-156">从此面板中，你可以管理警报并查看更多详细信息，如事件编号和相关设备。</span><span class="sxs-lookup"><span data-stu-id="7b023-156">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="7b023-157">可以一次选择多个警报。</span><span class="sxs-lookup"><span data-stu-id="7b023-157">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="7b023-158">若要查看警报的完整页面视图，包括事件图和进程树，请选择警报的标题。</span><span class="sxs-lookup"><span data-stu-id="7b023-158">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="7b023-159">日程表</span><span class="sxs-lookup"><span data-stu-id="7b023-159">Timeline</span></span>

<span data-ttu-id="7b023-160">" **时间线** "选项卡提供设备上已观测到的事件和相关警报的时间顺序视图。</span><span class="sxs-lookup"><span data-stu-id="7b023-160">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="7b023-161">这可以帮助你关联与设备相关的任何事件、文件和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7b023-161">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="7b023-162">时间线还使您能够有选择地深入到给定时段内发生的事件。</span><span class="sxs-lookup"><span data-stu-id="7b023-162">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="7b023-163">你可以查看所选时段内在设备上发生的事件的时间序列。</span><span class="sxs-lookup"><span data-stu-id="7b023-163">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="7b023-164">若要进一步控制视图，可以按事件组进行筛选或自定义列。</span><span class="sxs-lookup"><span data-stu-id="7b023-164">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="7b023-165">若要显示防火墙事件，你需要启用审核策略，请参阅审核 [筛选平台连接](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection)。</span><span class="sxs-lookup"><span data-stu-id="7b023-165">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="7b023-166">防火墙涵盖以下事件</span><span class="sxs-lookup"><span data-stu-id="7b023-166">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="7b023-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - 防火墙服务已停止</span><span class="sxs-lookup"><span data-stu-id="7b023-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="7b023-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - 阻止应用程序接受网络上传入的连接</span><span class="sxs-lookup"><span data-stu-id="7b023-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="7b023-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - 阻止连接</span><span class="sxs-lookup"><span data-stu-id="7b023-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![包含事件的设备时间线的图像](images/timeline-device.png)

<span data-ttu-id="7b023-171">一些功能包括：</span><span class="sxs-lookup"><span data-stu-id="7b023-171">Some of the functionality includes:</span></span>

- <span data-ttu-id="7b023-172">搜索特定事件</span><span class="sxs-lookup"><span data-stu-id="7b023-172">Search for specific events</span></span>
  - <span data-ttu-id="7b023-173">使用搜索栏查找特定的时间线事件。</span><span class="sxs-lookup"><span data-stu-id="7b023-173">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="7b023-174">筛选特定日期的事件</span><span class="sxs-lookup"><span data-stu-id="7b023-174">Filter events from a specific date</span></span>
  - <span data-ttu-id="7b023-175">选择表左上角的日历图标，以显示过去一天、一周、30 天或自定义范围中的事件。</span><span class="sxs-lookup"><span data-stu-id="7b023-175">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="7b023-176">默认情况下，设备时间线设置为显示过去 30 天的事件。</span><span class="sxs-lookup"><span data-stu-id="7b023-176">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="7b023-177">使用时间线通过突出显示部分跳转到特定时刻。</span><span class="sxs-lookup"><span data-stu-id="7b023-177">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="7b023-178">时间线上的箭头定位自动调查</span><span class="sxs-lookup"><span data-stu-id="7b023-178">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="7b023-179">导出详细的设备时间线事件</span><span class="sxs-lookup"><span data-stu-id="7b023-179">Export detailed device timeline events</span></span>
  - <span data-ttu-id="7b023-180">导出当前日期或指定日期范围（最多七天）的设备时间线。</span><span class="sxs-lookup"><span data-stu-id="7b023-180">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="7b023-181">有关特定事件的更多详细信息，请参阅"其他信息 **"** 部分。</span><span class="sxs-lookup"><span data-stu-id="7b023-181">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="7b023-182">这些详细信息因事件类型而异，例如：</span><span class="sxs-lookup"><span data-stu-id="7b023-182">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="7b023-183">包含在应用程序防护中 - Web 浏览器事件受隔离容器限制</span><span class="sxs-lookup"><span data-stu-id="7b023-183">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="7b023-184">检测到的活动威胁 - 威胁检测在威胁运行时发生</span><span class="sxs-lookup"><span data-stu-id="7b023-184">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="7b023-185">修正失败 - 尝试修正检测到的威胁已调用，但失败</span><span class="sxs-lookup"><span data-stu-id="7b023-185">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="7b023-186">修正成功 - 已停止并清理检测到的威胁</span><span class="sxs-lookup"><span data-stu-id="7b023-186">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="7b023-187">用户绕过的警告 - Windows Defender SmartScreen 警告已消除且已被用户覆盖</span><span class="sxs-lookup"><span data-stu-id="7b023-187">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="7b023-188">检测到可疑脚本 - 发现有潜在恶意脚本正在运行</span><span class="sxs-lookup"><span data-stu-id="7b023-188">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="7b023-189">警报类别 - 如果事件导致生成警报，则警报类别 ("横向移动"，例如) 警报</span><span class="sxs-lookup"><span data-stu-id="7b023-189">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="7b023-190">事件详情</span><span class="sxs-lookup"><span data-stu-id="7b023-190">Event details</span></span>
<span data-ttu-id="7b023-191">选择一个事件以查看有关该事件的相关详细信息。</span><span class="sxs-lookup"><span data-stu-id="7b023-191">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="7b023-192">将显示一个面板以显示常规事件信息。</span><span class="sxs-lookup"><span data-stu-id="7b023-192">A panel displays to show general event information.</span></span> <span data-ttu-id="7b023-193">如果适用且数据可用，还将显示显示相关实体及其关系的图形。</span><span class="sxs-lookup"><span data-stu-id="7b023-193">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="7b023-194">若要进一步检查事件和相关事件，可以通过为相关事件选择"[](advanced-hunting-overview.md)搜寻"来 **快速运行高级搜寻查询**。</span><span class="sxs-lookup"><span data-stu-id="7b023-194">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="7b023-195">查询将返回所选事件以及同一终结点上同时发生的其他事件的列表。</span><span class="sxs-lookup"><span data-stu-id="7b023-195">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![事件详细信息面板的图像](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="7b023-197">安全性建议</span><span class="sxs-lookup"><span data-stu-id="7b023-197">Security recommendations</span></span>

<span data-ttu-id="7b023-198">**安全建议** 由 Microsoft Defender 针对终结点的威胁和漏洞& [功能](tvm-dashboard-insights.md) 生成。</span><span class="sxs-lookup"><span data-stu-id="7b023-198">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="7b023-199">选择建议将显示一个面板，您可以在其中查看相关详细信息，如建议说明和与不实施建议相关的潜在风险。</span><span class="sxs-lookup"><span data-stu-id="7b023-199">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="7b023-200">有关详细信息 [，请参阅安全](tvm-security-recommendation.md) 建议。</span><span class="sxs-lookup"><span data-stu-id="7b023-200">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![安全建议选项卡的图像](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="7b023-202">软件清单</span><span class="sxs-lookup"><span data-stu-id="7b023-202">Software inventory</span></span>

<span data-ttu-id="7b023-203">借助 **"软件** 清单"选项卡，可以查看设备上的软件，以及任何漏洞或威胁。</span><span class="sxs-lookup"><span data-stu-id="7b023-203">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="7b023-204">选择软件名称后，您将访问软件详细信息页，您可以在其中查看安全建议、发现的漏洞、已安装的设备以及版本分发。</span><span class="sxs-lookup"><span data-stu-id="7b023-204">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="7b023-205">有关详细信息 [，请参阅](tvm-software-inventory.md) 软件清单</span><span class="sxs-lookup"><span data-stu-id="7b023-205">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![软件清单选项卡的图像](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="7b023-207">发现的漏洞</span><span class="sxs-lookup"><span data-stu-id="7b023-207">Discovered vulnerabilities</span></span>

<span data-ttu-id="7b023-208">" **发现的漏洞"** 选项卡显示设备上发现的漏洞的名称、严重性和威胁见解。</span><span class="sxs-lookup"><span data-stu-id="7b023-208">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="7b023-209">选择特定漏洞将显示说明和详细信息。</span><span class="sxs-lookup"><span data-stu-id="7b023-209">Selecting specific vulnerabilities will show a description and details.</span></span>

![已发现漏洞选项卡的图像](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="7b023-211">缺少 KB</span><span class="sxs-lookup"><span data-stu-id="7b023-211">Missing KBs</span></span>
<span data-ttu-id="7b023-212">" **缺少的 KB"** 选项卡列出了设备缺少的安全更新。</span><span class="sxs-lookup"><span data-stu-id="7b023-212">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![缺少 kbs 选项卡的图像](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="7b023-214">卡</span><span class="sxs-lookup"><span data-stu-id="7b023-214">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="7b023-215">活动警报</span><span class="sxs-lookup"><span data-stu-id="7b023-215">Active alerts</span></span>

<span data-ttu-id="7b023-216">**如果已启用 Microsoft** Defender for Identity 功能，并且存在任何活动警报，Azure 高级威胁防护卡片将显示与设备及其风险级别相关的警报的高级概述。</span><span class="sxs-lookup"><span data-stu-id="7b023-216">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Microsoft Defender for Identity feature, and there are any active alerts.</span></span> <span data-ttu-id="7b023-217">"警报"向下钻取中提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="7b023-217">More information is available in the "Alerts" drill down.</span></span>

![活动警报卡片的图像](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="7b023-219">你需要在 Microsoft Defender for Identity 和 Defender for Endpoint 上启用集成才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="7b023-219">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="7b023-220">在 Defender for Endpoint 中，可以在高级功能中启用此功能。</span><span class="sxs-lookup"><span data-stu-id="7b023-220">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="7b023-221">若要详细了解如何启用高级功能，请参阅 [启用高级功能](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="7b023-221">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="7b023-222">已登录用户</span><span class="sxs-lookup"><span data-stu-id="7b023-222">Logged on users</span></span>

<span data-ttu-id="7b023-223">**"已登录用户"** 卡片显示过去 30 天内登录的用户数，以及最多且最不频繁的用户。</span><span class="sxs-lookup"><span data-stu-id="7b023-223">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="7b023-224">选择"查看所有用户"链接将打开详细信息窗格，其中显示诸如用户类型、登录类型以及首次看到用户和最后一次看到用户时的信息。</span><span class="sxs-lookup"><span data-stu-id="7b023-224">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="7b023-225">有关详细信息，请参阅调查 [用户实体](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="7b023-225">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![用户详细信息窗格的图像](images/logged-on-users.png)

### <a name="security-assessments"></a><span data-ttu-id="7b023-227">安全评估</span><span class="sxs-lookup"><span data-stu-id="7b023-227">Security assessments</span></span>

<span data-ttu-id="7b023-228">安全 **评估卡片** 显示总体曝光级别、安全建议、已安装的软件和发现的漏洞。</span><span class="sxs-lookup"><span data-stu-id="7b023-228">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="7b023-229">设备的曝光级别由待定安全建议累积影响决定。</span><span class="sxs-lookup"><span data-stu-id="7b023-229">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![安全评估卡的图像](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="7b023-231">相关主题</span><span class="sxs-lookup"><span data-stu-id="7b023-231">Related topics</span></span>

- [<span data-ttu-id="7b023-232">查看和组织 Microsoft Defender 终结点警报队列</span><span class="sxs-lookup"><span data-stu-id="7b023-232">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="7b023-233">管理 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="7b023-233">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="7b023-234">调查 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="7b023-234">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="7b023-235">调查与 Defender for Endpoint 警报关联的文件</span><span class="sxs-lookup"><span data-stu-id="7b023-235">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="7b023-236">调查与 Defender for Endpoint 警报关联的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="7b023-236">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="7b023-237">调查与 Defender for Endpoint 警报关联的域</span><span class="sxs-lookup"><span data-stu-id="7b023-237">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="7b023-238">调查 Defender for Endpoint 中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="7b023-238">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="7b023-239">安全建议</span><span class="sxs-lookup"><span data-stu-id="7b023-239">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="7b023-240">软件库存</span><span class="sxs-lookup"><span data-stu-id="7b023-240">Software inventory</span></span>](tvm-software-inventory.md)
