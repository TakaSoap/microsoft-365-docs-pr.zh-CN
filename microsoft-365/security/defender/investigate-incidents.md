---
title: 调查 Microsoft 365 Defender 中的事件
description: 调查与设备、用户和邮箱相关的事件。
keywords: 事件， 事件， 分析， 响应， 计算机， 设备， 用户， 标识， 邮件， 电子邮件， 邮箱， 调查， 图形， 证据
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
ms.openlocfilehash: 7abc99a14ec538afea8cdbd4d8f3b4940bcccd9f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300081"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="748a2-104">调查 Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="748a2-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="748a2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="748a2-105">**Applies to:**</span></span>

- <span data-ttu-id="748a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="748a2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="748a2-107">Microsoft 365 Defender 将来自你的设备、用户和邮箱的所有用户的相关警报、资产、调查和证据聚合到事件中，让你全面了解整个攻击范围。</span><span class="sxs-lookup"><span data-stu-id="748a2-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="748a2-108">在事件内，分析影响网络的警报，了解它们的含义，并整理证据，以便制定有效的修正计划。</span><span class="sxs-lookup"><span data-stu-id="748a2-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="748a2-109">初始调查</span><span class="sxs-lookup"><span data-stu-id="748a2-109">Initial investigation</span></span>

<span data-ttu-id="748a2-110">在深入讨论详细信息之前，请看一下事件的属性和摘要。</span><span class="sxs-lookup"><span data-stu-id="748a2-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="748a2-111">你可以从选中标记列中选择事件开始。</span><span class="sxs-lookup"><span data-stu-id="748a2-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="748a2-112">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="748a2-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="从选中标记列中选择事件的示例":::

<span data-ttu-id="748a2-114">当你这样做时，将打开一个摘要窗格，其中包含有关事件的关键信息，如严重性、分配到该事件的人以及事件的[MITRE ATT &trade; ](https://attack.mitre.org/)&CK 类别。</span><span class="sxs-lookup"><span data-stu-id="748a2-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="748a2-115">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="748a2-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="事件的摘要窗格示例":::

<span data-ttu-id="748a2-117">从此处，可以选择"打开 **事件页面"。**</span><span class="sxs-lookup"><span data-stu-id="748a2-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="748a2-118">这将打开事件的主页，你将在此找到警报、设备、用户、调查和证据的更多摘要信息和选项卡。</span><span class="sxs-lookup"><span data-stu-id="748a2-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="748a2-119">您还可以通过从事件队列中选择事件名称来打开事件的主页。</span><span class="sxs-lookup"><span data-stu-id="748a2-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="748a2-120">摘要</span><span class="sxs-lookup"><span data-stu-id="748a2-120">Summary</span></span>

<span data-ttu-id="748a2-121">通过 **"摘要** "页面，您可以快速查看有关事件的顶部注意事项。</span><span class="sxs-lookup"><span data-stu-id="748a2-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 安全中心内事件的&quot;摘要&quot;页面示例":::

<span data-ttu-id="748a2-123">攻击类别可直观和数字地了解攻击对击杀链的进度。</span><span class="sxs-lookup"><span data-stu-id="748a2-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="748a2-124">与其他 Microsoft 安全产品一样，Microsoft 365 Defender 与[MITRE ATT&&trade; CK](https://attack.mitre.org/)框架一致。</span><span class="sxs-lookup"><span data-stu-id="748a2-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="748a2-125">“范围” 部分提供了属于此事件的最受影响的资产列表。</span><span class="sxs-lookup"><span data-stu-id="748a2-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="748a2-126">如果存在有关此资产的具体信息（例如风险级别、调查优先级以及资产上的任何标记），也将在本节中显示。</span><span class="sxs-lookup"><span data-stu-id="748a2-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="748a2-127">警报时间线可快速了解警报发生的时间顺序，以及这些警报链接到此事件的原因。</span><span class="sxs-lookup"><span data-stu-id="748a2-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="748a2-128">最后 ， 证据部分提供事件中包含的不同项目及其修正状态的摘要，以便你可以立即确定你是否需要任何操作。</span><span class="sxs-lookup"><span data-stu-id="748a2-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="748a2-129">本概述可通过深入了解应了解的事件主要特征，帮助对事件进行初始会审。</span><span class="sxs-lookup"><span data-stu-id="748a2-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="748a2-130">警报</span><span class="sxs-lookup"><span data-stu-id="748a2-130">Alerts</span></span>

<span data-ttu-id="748a2-131">在 **"警报** "选项卡上，您可以查看警报队列，了解与事件相关的警报及其其他信息，例如：</span><span class="sxs-lookup"><span data-stu-id="748a2-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="748a2-132">严重性。</span><span class="sxs-lookup"><span data-stu-id="748a2-132">Severity.</span></span>
- <span data-ttu-id="748a2-133">警报中涉及的实体。</span><span class="sxs-lookup"><span data-stu-id="748a2-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="748a2-134">Microsoft Defender for Identity、Microsoft Defender for Endpoint、Microsoft Defender for Office 365 (警报的来源) 。</span><span class="sxs-lookup"><span data-stu-id="748a2-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="748a2-135">链接在一起的原因。</span><span class="sxs-lookup"><span data-stu-id="748a2-135">The reason they were linked together.</span></span>

<span data-ttu-id="748a2-136">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="748a2-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="事件的警报页面示例":::

<span data-ttu-id="748a2-138">默认情况下，警报按时间顺序排序，以便查看事件如何随着时间的推移而播放。</span><span class="sxs-lookup"><span data-stu-id="748a2-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="748a2-139">选择每个警报将你访问警报的主页，你可以在这里对此警报进行深入分析。</span><span class="sxs-lookup"><span data-stu-id="748a2-139">Selecting each alert takes you to the alert's main page where you can conduct an in-depth analysis of that alert.</span></span> 

<span data-ttu-id="748a2-140">了解如何在调查警报中使用警报队列 [和警报页面](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="748a2-140">Learn how to use the alert queue and alert pages in [investigate alerts](investigate-alerts.md).</span></span>

## <a name="devices"></a><span data-ttu-id="748a2-141">设备</span><span class="sxs-lookup"><span data-stu-id="748a2-141">Devices</span></span>

<span data-ttu-id="748a2-142">" **设备** "选项卡列出了与事件相关的所有设备。</span><span class="sxs-lookup"><span data-stu-id="748a2-142">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="748a2-143">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="748a2-143">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="事件的设备页面示例":::

<span data-ttu-id="748a2-145">可以选择设备的选中标记以查看设备、目录数据、活动警报和登录用户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="748a2-145">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="748a2-146">选择设备名称以查看 Microsoft Defender for Endpoints 设备清单中的设备详细信息。</span><span class="sxs-lookup"><span data-stu-id="748a2-146">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="适用于终结点的 Microsoft Defender 的设备页面示例":::

<span data-ttu-id="748a2-148">从设备页面，你可以收集有关设备的其他信息，例如其所有警报、时间线和安全建议。</span><span class="sxs-lookup"><span data-stu-id="748a2-148">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="748a2-149">例如，从"时间线"选项卡中，你可以滚动浏览计算机时间线，并按时间顺序查看计算机上观测到的所有事件和行为，与所发出警报的交错。</span><span class="sxs-lookup"><span data-stu-id="748a2-149">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="748a2-150">可以在设备页面上执行按需扫描。</span><span class="sxs-lookup"><span data-stu-id="748a2-150">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="748a2-151">In the Microsoft 365 security center， choose **Endpoints > Device inventory**.</span><span class="sxs-lookup"><span data-stu-id="748a2-151">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="748a2-152">选择具有警报的设备，然后运行防病毒扫描。</span><span class="sxs-lookup"><span data-stu-id="748a2-152">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="748a2-153">防病毒扫描等操作会进行跟踪，并且显示在"设备清单 **"页上。**</span><span class="sxs-lookup"><span data-stu-id="748a2-153">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="748a2-154">若要了解更多信息，请参阅 [在设备上运行 Microsoft Defender 防病毒扫描](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)。</span><span class="sxs-lookup"><span data-stu-id="748a2-154">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="748a2-155">用户</span><span class="sxs-lookup"><span data-stu-id="748a2-155">Users</span></span>

<span data-ttu-id="748a2-156">" **用户** "选项卡列出了标识为事件的一部分或与事件相关的所有用户。</span><span class="sxs-lookup"><span data-stu-id="748a2-156">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="748a2-157">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="748a2-157">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的用户页面示例":::

<span data-ttu-id="748a2-159">可以选择用户的选中标记以查看用户帐户威胁、曝光和联系人信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="748a2-159">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="748a2-160">选择用户名以查看其他用户帐户详细信息。</span><span class="sxs-lookup"><span data-stu-id="748a2-160">Select the user name to see additional user account details.</span></span>

## <a name="mailboxes"></a><span data-ttu-id="748a2-161">邮箱</span><span class="sxs-lookup"><span data-stu-id="748a2-161">Mailboxes</span></span>

<span data-ttu-id="748a2-162">" **邮箱** "选项卡列出了标识为事件的一部分或与事件相关的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="748a2-162">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="748a2-163">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="748a2-163">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="事件的&quot;邮箱&quot;页面示例":::

<span data-ttu-id="748a2-165">您可以选择邮箱的选中标记以查看活动警报列表。</span><span class="sxs-lookup"><span data-stu-id="748a2-165">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="748a2-166">选择邮箱名称以查看适用于 Office 365 的 Microsoft Defender 的资源管理器页面上的其他邮箱详细信息。</span><span class="sxs-lookup"><span data-stu-id="748a2-166">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="748a2-167">调查</span><span class="sxs-lookup"><span data-stu-id="748a2-167">Investigations</span></span>

<span data-ttu-id="748a2-168">"**调查**"选项卡列出了此事件中的 [](m365d-autoir.md)警报触发的所有自动调查。</span><span class="sxs-lookup"><span data-stu-id="748a2-168">The **Investigations** tab lists all the [automated investigations](m365d-autoir.md) triggered by alerts in this incident.</span></span> <span data-ttu-id="748a2-169">调查将执行修正操作或等待分析员批准操作，具体取决于如何将自动调查配置为在 Microsoft Defender for Endpoint 和 Defender for Office 365 中运行。</span><span class="sxs-lookup"><span data-stu-id="748a2-169">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="事件的调查页面示例":::

<span data-ttu-id="748a2-171">选择“调查”，以导航到调查详细信息页面，获取有关调查和修复状态的完整信息。</span><span class="sxs-lookup"><span data-stu-id="748a2-171">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="748a2-172">如果有作为调查的一部分等待审批的任何操作，它们将显示在"挂起的操作"选项卡中。采取操作作为事件修正的一部分。</span><span class="sxs-lookup"><span data-stu-id="748a2-172">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

<span data-ttu-id="748a2-173">有关详细信息，请参阅 [Microsoft 365 Defender](m365d-autoir.md)中的自动调查和响应。</span><span class="sxs-lookup"><span data-stu-id="748a2-173">For more information, see [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="748a2-174">证据和响应</span><span class="sxs-lookup"><span data-stu-id="748a2-174">Evidence and Response</span></span>

<span data-ttu-id="748a2-175">" **证据和响应** "选项卡显示事件警报中所有受支持的事件和可疑实体。</span><span class="sxs-lookup"><span data-stu-id="748a2-175">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="748a2-176">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="748a2-176">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="事件的证据和响应页面示例":::

<span data-ttu-id="748a2-178">Microsoft 365 Defender 自动调查警报中所有事件支持的事件和可疑实体，并提供有关重要电子邮件、文件、流程、服务、IP 地址等的信息。</span><span class="sxs-lookup"><span data-stu-id="748a2-178">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="748a2-179">这可以帮助您快速检测和阻止事件中的潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="748a2-179">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="748a2-180">每个被分析的实体都标记为"恶意 (可疑、) 清理"和修正状态。</span><span class="sxs-lookup"><span data-stu-id="748a2-180">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="748a2-181">这可以帮助您了解整个事件的修正状态以及可以采取哪些下一步操作。</span><span class="sxs-lookup"><span data-stu-id="748a2-181">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="graph-in-preview"></a><span data-ttu-id="748a2-182">预览 (中的图形) </span><span class="sxs-lookup"><span data-stu-id="748a2-182">Graph (in preview)</span></span>

<span data-ttu-id="748a2-183">借助 **预览版** 中 (") "选项卡，你可以看到：</span><span class="sxs-lookup"><span data-stu-id="748a2-183">With the new **Graph** tab (in preview), you can see:</span></span>

- <span data-ttu-id="748a2-184">警报与组织中受影响资产的连接。</span><span class="sxs-lookup"><span data-stu-id="748a2-184">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="748a2-185">哪些实体与哪些警报相关，以及它们如何成为攻击的一部分。</span><span class="sxs-lookup"><span data-stu-id="748a2-185">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="748a2-186">事件的警报。</span><span class="sxs-lookup"><span data-stu-id="748a2-186">The alerts for the incident.</span></span>

<span data-ttu-id="748a2-187">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="748a2-187">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-graph.png" alt-text="事件的 Graph 页示例":::

<span data-ttu-id="748a2-189">事件图通过将属于攻击的不同可疑实体连接到其相关资产（如用户、设备和邮箱）来帮助您快速了解攻击的完整范围。</span><span class="sxs-lookup"><span data-stu-id="748a2-189">The incident graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="748a2-190">现在，你可以了解攻击在一段时间是如何通过网络的、开始位置以及攻击发生的时间。</span><span class="sxs-lookup"><span data-stu-id="748a2-190">Now you can understand how the attack spread through your network over time, where it started, and how far the attack went.</span></span>

## <a name="next-steps"></a><span data-ttu-id="748a2-191">后续步骤</span><span class="sxs-lookup"><span data-stu-id="748a2-191">Next steps</span></span>

<span data-ttu-id="748a2-192">根据需要：</span><span class="sxs-lookup"><span data-stu-id="748a2-192">As needed:</span></span>

- [<span data-ttu-id="748a2-193">调查事件警报</span><span class="sxs-lookup"><span data-stu-id="748a2-193">Investigate the alerts of an incident</span></span>](investigate-alerts.md)
- [<span data-ttu-id="748a2-194">调查事件的用户</span><span class="sxs-lookup"><span data-stu-id="748a2-194">Investigate the users of an incident</span></span>](investigate-users.md)

## <a name="see-also"></a><span data-ttu-id="748a2-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="748a2-195">See also</span></span>

- [<span data-ttu-id="748a2-196">事件概述</span><span class="sxs-lookup"><span data-stu-id="748a2-196">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="748a2-197">确定事件优先级</span><span class="sxs-lookup"><span data-stu-id="748a2-197">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="748a2-198">管理事件</span><span class="sxs-lookup"><span data-stu-id="748a2-198">Manage incidents</span></span>](manage-incidents.md)

