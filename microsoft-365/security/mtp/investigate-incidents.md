---
title: 调查 Microsoft 威胁防护中的事件
description: 分析与设备、用户和邮箱相关的事件。
keywords: 事件, 多个事件, 计算机, 设备, 用户, 标识, 邮件, 电子邮件, 邮箱, 调查, 图表, 证据
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 716feb3317989ebcc89593c89d05a6717b4ca0ee
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910877"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="a2e7c-104">调查 Microsoft 威胁防护中的事件</span><span class="sxs-lookup"><span data-stu-id="a2e7c-104">Investigate incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="a2e7c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a2e7c-105">**Applies to:**</span></span>
- <span data-ttu-id="a2e7c-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="a2e7c-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]


<span data-ttu-id="a2e7c-107">Microsoft 威胁防护将从所有设备、用户和邮箱聚合所有相关的警报、资产、调查和证据，让你全面了解完整的攻击范围。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-107">Microsoft Threat Protection aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span> 

<span data-ttu-id="a2e7c-108">调查影响网络的警报，了解其含义，整理与事件相关的证据，以便可以制定出有效的补救计划。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span> 

## <a name="investigate-an-incident"></a><span data-ttu-id="a2e7c-109">调查事件</span><span class="sxs-lookup"><span data-stu-id="a2e7c-109">Investigate an incident</span></span>

1. <span data-ttu-id="a2e7c-110">从事件队列中选择一个事件。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="a2e7c-111">此操作将打开侧面板并显示重要信息（如状态、严重性、类别和受影响的实体）的预览。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-111">This opens a side panel and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![事件侧面板的图像](../images/incident-side-panel.png)

2. <span data-ttu-id="a2e7c-113">选择“**打开事件页面**”。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="a2e7c-114">此操作将打开 "事件" 页面，可在其中找到更多信息事件详情、批注和操作、选项卡（概述、警报、设备、用户、调查、证据）。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-114">This opens the incident page where you'll find more information incident details, comments and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="a2e7c-115">查看警报、设备、用户、其它涉及事件的实体。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="a2e7c-116">事件概述</span><span class="sxs-lookup"><span data-stu-id="a2e7c-116">Incident overview</span></span> 
<span data-ttu-id="a2e7c-117">"概述" 页面提供有关事件的最需要注意事项的概览信息。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>


!["事件概述" 页面图像](../images/incidents-overview.png)


<span data-ttu-id="a2e7c-119">攻击类别提供了有关如何在攻击链中获得高级攻击进度的直观和数字视图。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-119">The attack categories give you visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="a2e7c-120">与其他 Microsoft 安全产品一样，Microsoft 威胁防护与 [MITRE ATT & CK&trade;](https://attack.mitre.org/) 框架一致。 </span><span class="sxs-lookup"><span data-stu-id="a2e7c-120">As with other Microsoft security products, Microsoft Threat Protection is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span> 

<span data-ttu-id="a2e7c-121">“范围” 部分提供了属于此事件的最受影响的资产列表。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="a2e7c-122">如果存在有关此资产的具体信息（例如风险级别、调查优先级以及资产上的任何标记），也将在本节中显示。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="a2e7c-123">“警报”时间线能够提前了解警报发生的时间顺序以及警报与此事件关联的原因。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="a2e7c-124">最后“证据部分”汇总了事件中包含的项目数量和修正状态，因此能够立即确定是否需要采取措施。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span> 

<span data-ttu-id="a2e7c-125">此概述可通过深入了解事件的首要特征，有助于了解事件的初始会审。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span> 


## <a name="alerts"></a><span data-ttu-id="a2e7c-126">警报</span><span class="sxs-lookup"><span data-stu-id="a2e7c-126">Alerts</span></span> 
<span data-ttu-id="a2e7c-127">可查看事件相关的所有警报和其他信息，如严重性、涉及警报的实体、警报来源（Azure ATP、Microsoft Defender ATP、Office  365 ATP）和关联原因。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Azure ATP, Microsoft Defender ATP , Office  365 ATP) and the reason they were linked together.</span></span> 

![事件警报页面图像](../images/incident-alerts.png)

<span data-ttu-id="a2e7c-129">警报默认按时间顺序排序，可以首先查看攻击如何随时间推移。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="a2e7c-130">点击各警报，将导航至相关警报页面，可在此对警报进行深入调查。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in depth investigation of that alert.</span></span> 

## <a name="devices"></a><span data-ttu-id="a2e7c-131">设备</span><span class="sxs-lookup"><span data-stu-id="a2e7c-131">Devices</span></span> 
<span data-ttu-id="a2e7c-132">"设备" 选项卡列出了出现与事件相关警报的所有设备。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span> 

<span data-ttu-id="a2e7c-133">单击执行攻击的计算机的名称，导航至计算机页面，可在其中查看触发的警报和有助于调查的相关事件。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span> 

![事件“计算机”选项卡图像](../images/incident-machines.png)

<span data-ttu-id="a2e7c-135">选择 "时间线" 选项卡，将能够在计算机时间线之间滚动，并按时间顺序查看计算机上观察到的所有事件和行为，并与引发的警报交错。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span> 


## <a name="users"></a><span data-ttu-id="a2e7c-136">用户</span><span class="sxs-lookup"><span data-stu-id="a2e7c-136">Users</span></span> 
<span data-ttu-id="a2e7c-137">查看标记为属于事件或与事件相关的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-137">See users that have been identified to be part of, or related to a given incident.</span></span> 

<span data-ttu-id="a2e7c-138">单击用户名，将导航至用户的 Cloud App Security 页面，可在此进行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>


![事件“用户”选项卡图像](../images/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="a2e7c-140">邮箱</span><span class="sxs-lookup"><span data-stu-id="a2e7c-140">Mailboxes</span></span>
<span data-ttu-id="a2e7c-141">调查标记为属于事件或与事件相关的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="a2e7c-142">若要执行进一步调查工作，选择邮件相关通知将 Office 365 打开高级威胁防护，可在此执行补救操作。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-142">To do further investigative work, selecting the mail related alert will open Office 365 Advanced Threat Protection where you can take remediation actions.</span></span>


![事件“邮箱”选项卡图像](../images/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="a2e7c-144">调查</span><span class="sxs-lookup"><span data-stu-id="a2e7c-144">Investigations</span></span>
<span data-ttu-id="a2e7c-145">选择“**调查**”，查看此事件中警报触发的自动调查。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-145">Select **Investigations** to see all the automated investigation striggered by alerts in this incident.</span></span> <span data-ttu-id="a2e7c-146">调查将执行补救操作或等待分析员批准操作，具体取决于如何配置自动化调查，以在 Microsoft Defender ATP 和 Office 365 高级威胁防护中运行。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender ATP and Office 365 Advanced Threat Protection.</span></span>

![事件“调查”选项卡图像](../images/incident-investigations.png)


<span data-ttu-id="a2e7c-148">选择“调查”，以导航到调查详细信息页面，获取有关调查和修复状态的完整信息。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="a2e7c-149">如果在调查过程中有任何待审批的操作，将在 "待定操作" 选项卡中显示。采取作为事件补救措施的操作。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-149">If there are any actions pending for approval as part of the investigation they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>


## <a name="evidence"></a><span data-ttu-id="a2e7c-150">证据</span><span class="sxs-lookup"><span data-stu-id="a2e7c-150">Evidence 2</span></span>
<span data-ttu-id="a2e7c-151">Microsoft 威胁防护自动调查警报中所有事件支持的事件和可疑实体，提供有关重要文件、流程、服务、电子邮件等的信息。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-151">Microsoft Threat Protection automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with auto-response and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="a2e7c-152">这有助于快速检测并阻止事件中的潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-152">This helps quickly detect and block potential threats in the incident.</span></span> 

![事件“证据”选项卡图像](../images/incident-evidence.png)

<span data-ttu-id="a2e7c-154">每一被分析的实体都将标记有裁定（恶意、可疑和清除）以及修正状态。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="a2e7c-155">这可有助于解整个事件的修正状态，以及执行进一步补救的后续步骤。</span><span class="sxs-lookup"><span data-stu-id="a2e7c-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a2e7c-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="a2e7c-156">Related topics</span></span>
- [<span data-ttu-id="a2e7c-157">事件概述</span><span class="sxs-lookup"><span data-stu-id="a2e7c-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a2e7c-158">确定事件优先级</span><span class="sxs-lookup"><span data-stu-id="a2e7c-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="a2e7c-159">管理事件</span><span class="sxs-lookup"><span data-stu-id="a2e7c-159">Manage incidents</span></span>](manage-incidents.md)