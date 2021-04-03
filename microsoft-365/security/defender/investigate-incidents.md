---
title: 调查 Microsoft 365 Defender 中的事件
description: 分析与设备、用户和邮箱相关的事件。
keywords: 事件, 多个事件, 计算机, 设备, 用户, 标识, 邮件, 电子邮件, 邮箱, 调查, 图表, 证据
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
ms.openlocfilehash: f6b085f200d3b0c71bb3608f8e5ba9ed85632676
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500325"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="11645-104">调查 Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="11645-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="11645-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="11645-105">**Applies to:**</span></span>

- <span data-ttu-id="11645-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11645-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="11645-107">Microsoft 365 Defender 聚合来自你的设备、用户和邮箱的所有用户的相关警报、资产、调查和证据，以便全面了解整个攻击范围。</span><span class="sxs-lookup"><span data-stu-id="11645-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="11645-108">调查影响网络的警报，了解其含义，整理与事件相关的证据，以便可以制定出有效的补救计划。</span><span class="sxs-lookup"><span data-stu-id="11645-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="11645-109">调查事件</span><span class="sxs-lookup"><span data-stu-id="11645-109">Investigate an incident</span></span>

1. <span data-ttu-id="11645-110">从事件队列中选择一个事件。</span><span class="sxs-lookup"><span data-stu-id="11645-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="11645-111">侧面板将打开，并预览重要信息，如状态、严重性、类别和影响的实体。</span><span class="sxs-lookup"><span data-stu-id="11645-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![事件侧面板的图像](../../media/incident-side-panel.png)

2. <span data-ttu-id="11645-113">选择“**打开事件页面**”。</span><span class="sxs-lookup"><span data-stu-id="11645-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="11645-114">这将打开事件页面，您可以在其中找到事件详细信息、注释和操作、选项卡 (概述、警报、设备、用户、调查、证据) 。</span><span class="sxs-lookup"><span data-stu-id="11645-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="11645-115">查看警报、设备、用户、其它涉及事件的实体。</span><span class="sxs-lookup"><span data-stu-id="11645-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="11645-116">事件概述</span><span class="sxs-lookup"><span data-stu-id="11645-116">Incident overview</span></span>

<span data-ttu-id="11645-117">"概述" 页面提供有关事件的最需要注意事项的概览信息。</span><span class="sxs-lookup"><span data-stu-id="11645-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

!["事件概述" 页面图像](../../media/incidents-overview.png)

<span data-ttu-id="11645-119">攻击类别可直观和数字地了解攻击对击杀链的进度。</span><span class="sxs-lookup"><span data-stu-id="11645-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="11645-120">与其他 Microsoft 安全产品一样，Microsoft 365 Defender 与[MITRE ATT&&trade; CK](https://attack.mitre.org/)框架一致。</span><span class="sxs-lookup"><span data-stu-id="11645-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="11645-121">“范围” 部分提供了属于此事件的最受影响的资产列表。</span><span class="sxs-lookup"><span data-stu-id="11645-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="11645-122">如果存在有关此资产的具体信息（例如风险级别、调查优先级以及资产上的任何标记），也将在本节中显示。</span><span class="sxs-lookup"><span data-stu-id="11645-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="11645-123">“警报”时间线能够提前了解警报发生的时间顺序以及警报与此事件关联的原因。</span><span class="sxs-lookup"><span data-stu-id="11645-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="11645-124">最后“证据部分”汇总了事件中包含的项目数量和修正状态，因此能够立即确定是否需要采取措施。</span><span class="sxs-lookup"><span data-stu-id="11645-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="11645-125">此概述可通过深入了解事件的首要特征，有助于了解事件的初始会审。</span><span class="sxs-lookup"><span data-stu-id="11645-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="11645-126">警报</span><span class="sxs-lookup"><span data-stu-id="11645-126">Alerts</span></span>

<span data-ttu-id="11645-127">你可以查看与事件相关的所有警报及其其他信息，例如严重性、警报中涉及的实体、警报的来源 (Microsoft Defender for Identity、Microsoft Defender for Endpoint、Microsoft Defender for Office 365) 以及它们链接在一起的原因。</span><span class="sxs-lookup"><span data-stu-id="11645-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![事件警报页面图像](../../media/incident-alerts.png)

<span data-ttu-id="11645-129">警报默认按时间顺序排序，可以首先查看攻击如何随时间推移。</span><span class="sxs-lookup"><span data-stu-id="11645-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="11645-130">单击每个警报将引导你进入相关警报页面，你可以在这里对此警报进行深入调查。</span><span class="sxs-lookup"><span data-stu-id="11645-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span> <span data-ttu-id="11645-131">在调查警报中了解如何使用警报页面和 [统一警报队列](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="11645-131">Learn how to use alert pages and the unified alert queue in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="11645-132">设备</span><span class="sxs-lookup"><span data-stu-id="11645-132">Devices</span></span>

<span data-ttu-id="11645-133">"设备" 选项卡列出了出现与事件相关警报的所有设备。</span><span class="sxs-lookup"><span data-stu-id="11645-133">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="11645-134">单击执行攻击的计算机的名称，导航至计算机页面，可在其中查看触发的警报和有助于调查的相关事件。</span><span class="sxs-lookup"><span data-stu-id="11645-134">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![事件“计算机”选项卡图像](../../media/incident-machines.png)

<span data-ttu-id="11645-136">选择 "时间线" 选项卡，将能够在计算机时间线之间滚动，并按时间顺序查看计算机上观察到的所有事件和行为，并与引发的警报交错。</span><span class="sxs-lookup"><span data-stu-id="11645-136">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="11645-137">用户</span><span class="sxs-lookup"><span data-stu-id="11645-137">Users</span></span>

<span data-ttu-id="11645-138">查看标记为属于事件或与事件相关的邮箱。</span><span class="sxs-lookup"><span data-stu-id="11645-138">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="11645-139">单击用户名，将导航至用户的 Cloud App Security 页面，可在此进行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="11645-139">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![事件“用户”选项卡图像](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="11645-141">邮箱</span><span class="sxs-lookup"><span data-stu-id="11645-141">Mailboxes</span></span>

<span data-ttu-id="11645-142">调查标记为属于事件或与事件相关的邮箱。</span><span class="sxs-lookup"><span data-stu-id="11645-142">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="11645-143">若要执行进一步的调查工作，选择与邮件相关的警报将打开 Microsoft Defender for Office 365，可在其中执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="11645-143">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![事件“邮箱”选项卡图像](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="11645-145">调查</span><span class="sxs-lookup"><span data-stu-id="11645-145">Investigations</span></span>

<span data-ttu-id="11645-146">选择 **"** 调查"以查看此事件中的警报触发的所有自动调查。</span><span class="sxs-lookup"><span data-stu-id="11645-146">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="11645-147">调查将执行修正操作或等待分析员批准操作，具体取决于如何将自动调查配置为在 Microsoft Defender for Endpoint 和 Defender for Office 365 中运行。</span><span class="sxs-lookup"><span data-stu-id="11645-147">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![事件“调查”选项卡图像](../../media/incident-investigations.png)

<span data-ttu-id="11645-149">选择“调查”，以导航到调查详细信息页面，获取有关调查和修复状态的完整信息。</span><span class="sxs-lookup"><span data-stu-id="11645-149">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="11645-150">如果有作为调查的一部分等待审批的任何操作，它们将显示在"挂起的操作"选项卡中。采取操作作为事件修正的一部分。</span><span class="sxs-lookup"><span data-stu-id="11645-150">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="11645-151">证据</span><span class="sxs-lookup"><span data-stu-id="11645-151">Evidence</span></span>

<span data-ttu-id="11645-152">Microsoft 365 Defender 自动调查警报中所有事件支持的事件和可疑实体，从而自动响应和有关重要文件、流程、服务、电子邮件等的信息。</span><span class="sxs-lookup"><span data-stu-id="11645-152">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="11645-153">这有助于快速检测并阻止事件中的潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="11645-153">This helps quickly detect and block potential threats in the incident.</span></span>

![事件“证据”选项卡图像](../../media/incident-evidence.png)

<span data-ttu-id="11645-155">每一被分析的实体都将标记有裁定（恶意、可疑和清除）以及修正状态。</span><span class="sxs-lookup"><span data-stu-id="11645-155">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="11645-156">这可有助于解整个事件的修正状态，以及执行进一步补救的后续步骤。</span><span class="sxs-lookup"><span data-stu-id="11645-156">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="11645-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="11645-157">Related topics</span></span>

- [<span data-ttu-id="11645-158">事件概述</span><span class="sxs-lookup"><span data-stu-id="11645-158">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="11645-159">确定事件优先级</span><span class="sxs-lookup"><span data-stu-id="11645-159">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="11645-160">管理事件</span><span class="sxs-lookup"><span data-stu-id="11645-160">Manage incidents</span></span>](manage-incidents.md)

