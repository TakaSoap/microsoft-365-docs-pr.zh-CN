---
title: Microsoft Defender 安全中心安全操作仪表板
description: 使用仪表板识别处于风险中的设备，跟踪服务状态，并查看有关设备和警报的统计信息和信息。
keywords: 仪表板， 警报， 新， 正在进行， 已解决， 风险， 处于风险中的设备， 感染， 报告， 统计信息， 图表， 图形， 运行状况， 活动恶意软件检测， 威胁类别， 类别， 密码窃取程序， 勒索软件， 攻击， 威胁， 低严重性， 活动恶意软件
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055621"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a><span data-ttu-id="6ac14-104">Microsoft Defender 安全中心安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="6ac14-104">Microsoft Defender Security Center Security operations dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6ac14-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6ac14-105">**Applies to:**</span></span>
- [<span data-ttu-id="6ac14-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6ac14-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="6ac14-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6ac14-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6ac14-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6ac14-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

<span data-ttu-id="6ac14-109">安全 **操作仪表板** 是显示终结点检测和响应功能的地方。</span><span class="sxs-lookup"><span data-stu-id="6ac14-109">The **Security operations dashboard** is where the endpoint detection and response capabilities are surfaced.</span></span> <span data-ttu-id="6ac14-110">它提供了发现检测位置的简要概述，并突出显示了需要响应操作的地方。</span><span class="sxs-lookup"><span data-stu-id="6ac14-110">It provides a high level overview of where detections were seen and highlights where response actions are needed.</span></span> 

<span data-ttu-id="6ac14-111">仪表板显示以下项的快照：</span><span class="sxs-lookup"><span data-stu-id="6ac14-111">The dashboard displays a snapshot of:</span></span>

- <span data-ttu-id="6ac14-112">活动警报</span><span class="sxs-lookup"><span data-stu-id="6ac14-112">Active alerts</span></span>
- <span data-ttu-id="6ac14-113">处于风险之中的设备</span><span class="sxs-lookup"><span data-stu-id="6ac14-113">Devices at risk</span></span>
- <span data-ttu-id="6ac14-114">传感器运行状况</span><span class="sxs-lookup"><span data-stu-id="6ac14-114">Sensor health</span></span>
- <span data-ttu-id="6ac14-115">服务运行状况</span><span class="sxs-lookup"><span data-stu-id="6ac14-115">Service health</span></span>
- <span data-ttu-id="6ac14-116">每日设备报告</span><span class="sxs-lookup"><span data-stu-id="6ac14-116">Daily devices reporting</span></span>
- <span data-ttu-id="6ac14-117">主动自动调查</span><span class="sxs-lookup"><span data-stu-id="6ac14-117">Active automated investigations</span></span>
- <span data-ttu-id="6ac14-118">自动调查统计信息</span><span class="sxs-lookup"><span data-stu-id="6ac14-118">Automated investigations statistics</span></span>
- <span data-ttu-id="6ac14-119">处于风险之中的用户</span><span class="sxs-lookup"><span data-stu-id="6ac14-119">Users at risk</span></span>
- <span data-ttu-id="6ac14-120">可疑活动</span><span class="sxs-lookup"><span data-stu-id="6ac14-120">Suspicious activities</span></span>


![安全操作仪表板的图像](images/atp-sec-ops-dashboard.png)

<span data-ttu-id="6ac14-122">你可以浏览和调查警报和设备，以快速确定网络中是否、何处以及何时发生可疑活动，以帮助你了解它们出现的上下文。</span><span class="sxs-lookup"><span data-stu-id="6ac14-122">You can explore and investigate alerts and devices to quickly determine if, where, and when suspicious activities occurred in your network to help you understand the context they appeared in.</span></span>

<span data-ttu-id="6ac14-123">从 **安全操作仪表板** 中，你将看到聚合事件，以便于识别设备上的重要事件或行为。</span><span class="sxs-lookup"><span data-stu-id="6ac14-123">From the **Security operations dashboard** you will see aggregated events to facilitate the identification of significant events or behaviors on a device.</span></span> <span data-ttu-id="6ac14-124">还可以深入到粒度事件和低级别指示器。</span><span class="sxs-lookup"><span data-stu-id="6ac14-124">You can also drill down into granular events and low-level indicators.</span></span>

<span data-ttu-id="6ac14-125">它还具有可单击的磁贴，可直观提示组织的整体运行状况。</span><span class="sxs-lookup"><span data-stu-id="6ac14-125">It also has clickable tiles that give visual cues on the overall health state of your organization.</span></span> <span data-ttu-id="6ac14-126">每个磁贴将打开相应概述的详细视图。</span><span class="sxs-lookup"><span data-stu-id="6ac14-126">Each tile opens a detailed view of the corresponding overview.</span></span>

## <a name="active-alerts"></a><span data-ttu-id="6ac14-127">活动警报</span><span class="sxs-lookup"><span data-stu-id="6ac14-127">Active alerts</span></span>
<span data-ttu-id="6ac14-128">你可以从磁贴查看最近 30 天内网络的活动警报的个数。</span><span class="sxs-lookup"><span data-stu-id="6ac14-128">You can view the overall number of active alerts from the last 30 days in your network from the tile.</span></span> <span data-ttu-id="6ac14-129">警报分为"**新建"和**"**正在进行"。**</span><span class="sxs-lookup"><span data-stu-id="6ac14-129">Alerts are grouped into **New** and **In progress**.</span></span>

![单击每个切片或严重性以查看过去 30 天内的警报列表](images/active-alerts-tile.png)

<span data-ttu-id="6ac14-131">每个组进一步细分为相应的警报严重性级别。</span><span class="sxs-lookup"><span data-stu-id="6ac14-131">Each group is further sub-categorized into their corresponding alert severity levels.</span></span> <span data-ttu-id="6ac14-132">单击每个警报圈内的警报数，以查看该类别的队列的已排序视图 **("** 新建"或"正在进行) "。 </span><span class="sxs-lookup"><span data-stu-id="6ac14-132">Click the number of alerts inside each alert ring to see a sorted view of that category's queue (**New** or **In progress**).</span></span>

<span data-ttu-id="6ac14-133">有关详细信息，请参阅 [警报概述](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="6ac14-133">For more information see, [Alerts overview](alerts-queue.md).</span></span>

<span data-ttu-id="6ac14-134">每行包括警报严重性类别和警报的简短说明。</span><span class="sxs-lookup"><span data-stu-id="6ac14-134">Each row includes an alert severity category and a short description of the alert.</span></span> <span data-ttu-id="6ac14-135">你可以单击警报以查看其详细视图。</span><span class="sxs-lookup"><span data-stu-id="6ac14-135">You can click an alert to see its detailed view.</span></span> <span data-ttu-id="6ac14-136">有关详细信息，请参阅调查  [适用于终结点的 Microsoft Defender](investigate-alerts.md) 警报 [和警报概述](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="6ac14-136">For more information see,  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).</span></span>


## <a name="devices-at-risk"></a><span data-ttu-id="6ac14-137">处于风险之中的设备</span><span class="sxs-lookup"><span data-stu-id="6ac14-137">Devices at risk</span></span>
<span data-ttu-id="6ac14-138">此磁贴显示活动警报数最高的设备列表。</span><span class="sxs-lookup"><span data-stu-id="6ac14-138">This tile shows you a list of devices with the highest number of active alerts.</span></span> <span data-ttu-id="6ac14-139">每个设备的警报总数在设备名称旁的圆圈中显示，然后按严重级别进一步分类到磁贴 (悬停在每个严重性栏的末尾以查看其标签) 。</span><span class="sxs-lookup"><span data-stu-id="6ac14-139">The total number of alerts for each device is shown in a circle next to the device name, and then further categorized by severity levels at the far end of the tile (hover over each severity bar to see its label).</span></span>

!["处于风险中的设备"图块显示警报数最高的设备列表，以及警报严重性的细目](images/devices-at-risk-tile.png)

<span data-ttu-id="6ac14-141">单击设备名称以查看有关该设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6ac14-141">Click the name of the device to see details about that device.</span></span> <span data-ttu-id="6ac14-142">有关详细信息，请参阅调查 [Microsoft Defender 终结点设备列表中的设备](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="6ac14-142">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

<span data-ttu-id="6ac14-143">还可以单击磁贴 **顶部的**"设备"列表，直接转到"设备"列表（按活动警报数排序）。</span><span class="sxs-lookup"><span data-stu-id="6ac14-143">You can also click **Devices list** at the top of the tile to go directly to the **Devices list**, sorted by the number of active alerts.</span></span> <span data-ttu-id="6ac14-144">有关详细信息，请参阅调查 [Microsoft Defender 终结点设备列表中的设备](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="6ac14-144">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

## <a name="devices-with-sensor-issues"></a><span data-ttu-id="6ac14-145">具有传感器问题的设备</span><span class="sxs-lookup"><span data-stu-id="6ac14-145">Devices with sensor issues</span></span>
<span data-ttu-id="6ac14-146">" **具有传感器问题的设备** "图块提供有关单个设备向 Microsoft Defender for Endpoint 服务提供传感器数据的能力的信息。</span><span class="sxs-lookup"><span data-stu-id="6ac14-146">The **Devices with sensor issues** tile provides information on the individual device’s ability to provide sensor data to the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="6ac14-147">它报告需要关注的设备数，并帮助你识别有问题的设备。</span><span class="sxs-lookup"><span data-stu-id="6ac14-147">It reports how many devices require attention and helps you identify problematic devices.</span></span>

![具有传感器问题的设备图块](images/atp-tile-sensor-health.png)

<span data-ttu-id="6ac14-149">有两个状态指示器提供有关未正确报告给服务的设备数量的信息：</span><span class="sxs-lookup"><span data-stu-id="6ac14-149">There are two status indicators that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="6ac14-150">**错误配置** – 这些设备可能部分向 Microsoft Defender for Endpoint 服务报告传感器数据，并且可能有需要更正的配置错误。</span><span class="sxs-lookup"><span data-stu-id="6ac14-150">**Misconfigured** – These devices might partially be reporting sensor data to the Microsoft Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="6ac14-151">**非** 活动 - 在过去一个月内停止向 Microsoft Defender for Endpoint 服务报告超过七天的设备。</span><span class="sxs-lookup"><span data-stu-id="6ac14-151">**Inactive** - Devices that have stopped reporting to the Microsoft Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="6ac14-152">当你单击任何组时，你将定向到设备列表，根据你的选择进行筛选。</span><span class="sxs-lookup"><span data-stu-id="6ac14-152">When you click any of the groups, you’ll be directed to devices list, filtered according to your choice.</span></span> <span data-ttu-id="6ac14-153">有关详细信息，请参阅检查[传感器状态和](check-sensor-status.md)[调查设备](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="6ac14-153">For more information, see [Check sensor state](check-sensor-status.md) and [Investigate devices](investigate-machines.md).</span></span>

## <a name="service-health"></a><span data-ttu-id="6ac14-154">服务运行状况</span><span class="sxs-lookup"><span data-stu-id="6ac14-154">Service health</span></span>
<span data-ttu-id="6ac14-155">服务 **运行状况** 磁贴会通知服务是否处于活动状态或是否有问题。</span><span class="sxs-lookup"><span data-stu-id="6ac14-155">The **Service health** tile informs you if the service is active or if there are issues.</span></span>

!["服务运行状况"磁贴显示服务的整体指示器](images/status-tile.png)

<span data-ttu-id="6ac14-157">有关服务运行状况详细信息，请参阅 [检查 Microsoft Defender 终结点服务运行状况](service-status.md)。</span><span class="sxs-lookup"><span data-stu-id="6ac14-157">For more information on the service health, see [Check the Microsoft Defender for Endpoint service health](service-status.md).</span></span>


## <a name="daily-devices-reporting"></a><span data-ttu-id="6ac14-158">每日设备报告</span><span class="sxs-lookup"><span data-stu-id="6ac14-158">Daily devices reporting</span></span>
<span data-ttu-id="6ac14-159">" **每日设备报告** "磁贴显示一个条形图，表示过去 30 天内每天报告的设备数。</span><span class="sxs-lookup"><span data-stu-id="6ac14-159">The **Daily devices reporting** tile shows a bar graph that represents the number of devices reporting daily in the last 30 days.</span></span> <span data-ttu-id="6ac14-160">将鼠标悬停在图形上的个别条形上，查看每天报告的具体设备数。</span><span class="sxs-lookup"><span data-stu-id="6ac14-160">Hover over individual bars on the graph to see the exact number of devices reporting in each day.</span></span>

![每日设备报告磁贴的图像](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a><span data-ttu-id="6ac14-162">主动自动调查</span><span class="sxs-lookup"><span data-stu-id="6ac14-162">Active automated investigations</span></span>
<span data-ttu-id="6ac14-163">你可以从"活动自动调查"磁贴中查看最近 30 天内网络中自动 **调查的个数** 。</span><span class="sxs-lookup"><span data-stu-id="6ac14-163">You can view the overall number of automated investigations from the last 30 days in your network from the **Active automated investigations** tile.</span></span> <span data-ttu-id="6ac14-164">调查分为"挂起 **操作"、"\*\*\*\*等待设备"** 和"正在运行 **"。**</span><span class="sxs-lookup"><span data-stu-id="6ac14-164">Investigations are grouped into **Pending action**, **Waiting for device**, and **Running**.</span></span>

![活动自动调查的一系列信息](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a><span data-ttu-id="6ac14-166">自动调查统计信息</span><span class="sxs-lookup"><span data-stu-id="6ac14-166">Automated investigations statistics</span></span>
<span data-ttu-id="6ac14-167">此图块显示最近七天内与自动调查相关的统计信息。</span><span class="sxs-lookup"><span data-stu-id="6ac14-167">This tile shows statistics related to automated investigations in the last seven days.</span></span> <span data-ttu-id="6ac14-168">它显示完成的调查数、成功修正调查的数量、启动调查所花费的平均待定时间、修正警报的平均时间、调查的警报数以及从典型手动调查保存的自动化小时数。</span><span class="sxs-lookup"><span data-stu-id="6ac14-168">It shows the number of investigations completed, the number of successfully remediated investigations, the average pending time it takes for an investigation to be initiated, the average time it takes to remediate an alert, the number of alerts investigated, and the number of hours of automation saved from a typical manual investigation.</span></span> 

![自动调查统计信息的图像](images/atp-automated-investigations-statistics.png)

<span data-ttu-id="6ac14-170">你可以单击自动 **调查**、**修正** 调查和调查的警报，以导航到按相应类别筛选的"调查"页面。</span><span class="sxs-lookup"><span data-stu-id="6ac14-170">You can click on **Automated investigations**, **Remediated investigations**, and **Alerts investigated** to navigate to the **Investigations** page, filtered by the appropriate category.</span></span> <span data-ttu-id="6ac14-171">这样，你可以查看上下文中调查的详细说明。</span><span class="sxs-lookup"><span data-stu-id="6ac14-171">This lets you see a detailed breakdown of investigations in context.</span></span>

## <a name="users-at-risk"></a><span data-ttu-id="6ac14-172">处于风险之中的用户</span><span class="sxs-lookup"><span data-stu-id="6ac14-172">Users at risk</span></span>
<span data-ttu-id="6ac14-173">磁贴显示具有最活跃警报的用户帐户列表，以及在高、中或低警报上看到的警报数。</span><span class="sxs-lookup"><span data-stu-id="6ac14-173">The tile shows you a list of user accounts with the most active alerts and the number of alerts seen on high, medium, or low alerts.</span></span> 

![处于风险中的用户帐户图块显示具有最高警报数的用户帐户列表和警报严重性的细目](images/atp-users-at-risk.png)

<span data-ttu-id="6ac14-175">单击用户帐户以查看有关用户帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6ac14-175">Click the user account to see details about the user account.</span></span> <span data-ttu-id="6ac14-176">有关详细信息，请参阅 [调查用户帐户](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="6ac14-176">For more information see [Investigate a user account](investigate-user.md).</span></span>

><span data-ttu-id="6ac14-177">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6ac14-177">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6ac14-178">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6ac14-178">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="6ac14-179">相关主题</span><span class="sxs-lookup"><span data-stu-id="6ac14-179">Related topics</span></span>
- [<span data-ttu-id="6ac14-180">了解适用于终结点的 Microsoft Defender 门户</span><span class="sxs-lookup"><span data-stu-id="6ac14-180">Understand the Microsoft Defender for Endpoint portal</span></span>](use.md)
- [<span data-ttu-id="6ac14-181">门户概述</span><span class="sxs-lookup"><span data-stu-id="6ac14-181">Portal overview</span></span>](portal-overview.md)
- [<span data-ttu-id="6ac14-182">查看威胁&漏洞管理仪表板</span><span class="sxs-lookup"><span data-stu-id="6ac14-182">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="6ac14-183">查看威胁分析仪表板，采取建议的缓解操作</span><span class="sxs-lookup"><span data-stu-id="6ac14-183">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
