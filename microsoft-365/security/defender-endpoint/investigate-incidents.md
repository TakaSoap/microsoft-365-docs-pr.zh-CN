---
title: 调查 Microsoft Defender for Endpoint 中的事件
description: 查看关联警报、管理事件和查看警报元数据，帮助你调查事件
keywords: 调查， 事件， 警报， 元数据， 风险， 检测来源， 受影响的设备， 模式， 相关
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
ms.openlocfilehash: 0b52b6f9b457dbe1a5984c3d68c7077f7037d498
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845074"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="da689-104">调查 Microsoft Defender for Endpoint 中的事件</span><span class="sxs-lookup"><span data-stu-id="da689-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="da689-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="da689-105">**Applies to:**</span></span>
- [<span data-ttu-id="da689-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="da689-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="da689-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da689-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="da689-108">调查影响网络的事件，了解这些事件的含义，并整理证据以解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="da689-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="da689-109">调查事件时，你将看到：</span><span class="sxs-lookup"><span data-stu-id="da689-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="da689-110">事件详细信息</span><span class="sxs-lookup"><span data-stu-id="da689-110">Incident details</span></span>
- <span data-ttu-id="da689-111">事件注释和操作</span><span class="sxs-lookup"><span data-stu-id="da689-111">Incident comments and actions</span></span>
- <span data-ttu-id="da689-112">选项卡 (警报、设备、调查、证据、图形) </span><span class="sxs-lookup"><span data-stu-id="da689-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="da689-113">分析事件详细信息</span><span class="sxs-lookup"><span data-stu-id="da689-113">Analyze incident details</span></span> 
<span data-ttu-id="da689-114">单击事件以查看"事件 **"窗格**。</span><span class="sxs-lookup"><span data-stu-id="da689-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="da689-115">选择 **"打开事件页面** "，查看事件详细信息和相关信息 (警报、设备、调查、证据、图形) 。</span><span class="sxs-lookup"><span data-stu-id="da689-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![事件详细信息的图像1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="da689-117">警报</span><span class="sxs-lookup"><span data-stu-id="da689-117">Alerts</span></span>
<span data-ttu-id="da689-118">你可以调查警报，并查看它们在事件中是如何链接在一起的。</span><span class="sxs-lookup"><span data-stu-id="da689-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="da689-119">根据以下原因，将警报分组为事件：</span><span class="sxs-lookup"><span data-stu-id="da689-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="da689-120">自动调查 - 自动调查在调查原始警报时触发了链接警报</span><span class="sxs-lookup"><span data-stu-id="da689-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="da689-121">文件特征 - 与警报关联的文件具有相似的特征</span><span class="sxs-lookup"><span data-stu-id="da689-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="da689-122">手动关联 - 用户手动链接警报</span><span class="sxs-lookup"><span data-stu-id="da689-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="da689-123">代理时间 - 在特定时间范围内在同一设备上触发警报</span><span class="sxs-lookup"><span data-stu-id="da689-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="da689-124">同一文件 - 与警报关联的文件完全相同</span><span class="sxs-lookup"><span data-stu-id="da689-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="da689-125">同一 URL - 触发警报的 URL 完全相同</span><span class="sxs-lookup"><span data-stu-id="da689-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![警报选项卡图像，包含事件详细信息页面，显示警报在事件中链接在一起的原因](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="da689-127">还可以管理警报并查看警报元数据以及其他信息。</span><span class="sxs-lookup"><span data-stu-id="da689-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="da689-128">有关详细信息，请参阅调查 [警报](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="da689-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="da689-129">设备</span><span class="sxs-lookup"><span data-stu-id="da689-129">Devices</span></span>
<span data-ttu-id="da689-130">还可以调查属于给定事件或与给定事件相关的设备。</span><span class="sxs-lookup"><span data-stu-id="da689-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="da689-131">有关详细信息，请参阅 [调查设备](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="da689-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![事件详细信息页中的"设备"选项卡图像](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="da689-133">调查</span><span class="sxs-lookup"><span data-stu-id="da689-133">Investigations</span></span>
<span data-ttu-id="da689-134">选择 **"** 调查"以查看系统为响应事件警报而启动的所有自动调查。</span><span class="sxs-lookup"><span data-stu-id="da689-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![事件详细信息页面中"调查"选项卡的图像](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="da689-136">浏览证据</span><span class="sxs-lookup"><span data-stu-id="da689-136">Going through the evidence</span></span>
<span data-ttu-id="da689-137">Microsoft Defender for Endpoint 自动调查警报中所有事件支持的事件和可疑实体，从而自动响应和有关重要文件、流程、服务等的信息。</span><span class="sxs-lookup"><span data-stu-id="da689-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="da689-138">分析的每个实体将被标记为已感染、已修复或可疑。</span><span class="sxs-lookup"><span data-stu-id="da689-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![事件详细信息页中证据选项卡的图像](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="da689-140">可视化关联的网络安全威胁</span><span class="sxs-lookup"><span data-stu-id="da689-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="da689-141">Microsoft Defender for Endpoint 将威胁信息聚合到事件中，以便你可以查看来自各种数据点的模式和相关。</span><span class="sxs-lookup"><span data-stu-id="da689-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="da689-142">可以通过事件图查看此类关联。</span><span class="sxs-lookup"><span data-stu-id="da689-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="da689-143">事件图</span><span class="sxs-lookup"><span data-stu-id="da689-143">Incident graph</span></span>
<span data-ttu-id="da689-144">此 **Graph** 将介绍网络安全攻击的情景。</span><span class="sxs-lookup"><span data-stu-id="da689-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="da689-145">例如，它显示入口点是什么，哪个指示在哪个设备上观察到了泄露或活动。</span><span class="sxs-lookup"><span data-stu-id="da689-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="da689-146">等。</span><span class="sxs-lookup"><span data-stu-id="da689-146">etc.</span></span>

![事件图的图像](images/atp-incident-graph-tab.png)

<span data-ttu-id="da689-148">你可以单击事件图上的圆圈来查看恶意文件的详细信息、关联的文件检测、全球有多少实例，以及在你的组织中是否观测到它，如果是，则查看实例数。</span><span class="sxs-lookup"><span data-stu-id="da689-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![事件详细信息的图像](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="da689-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="da689-150">Related topics</span></span>
- [<span data-ttu-id="da689-151">事件队列</span><span class="sxs-lookup"><span data-stu-id="da689-151">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="da689-152">调查 Microsoft Defender for Endpoint 中的事件</span><span class="sxs-lookup"><span data-stu-id="da689-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="da689-153">管理 Microsoft Defender 终结点事件</span><span class="sxs-lookup"><span data-stu-id="da689-153">Manage Microsoft Defender for Endpoint incidents</span></span>](/microsoft-365/security/defender-endpoint/manage-incidents)
