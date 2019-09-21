---
title: Office 365 中的自动化调查和响应（空气）
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解 Office 365 高级威胁防护中的自动化调查和响应功能。
ms.openlocfilehash: 1e600a7a392acc34fac2547a3daa17c0058322b5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "37075080"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="f94dc-103">Office 365 中的自动化调查和响应（空气）</span><span class="sxs-lookup"><span data-stu-id="f94dc-103">Automated investigation and response (AIR) in Office 365</span></span>

<span data-ttu-id="f94dc-104">自动化调查和响应（空中）功能（包括在[Office 365 高级威胁防护](office-365-atp.md)计划2中）使您能够运行自动调查过程，以应对目前存在的已知威胁。</span><span class="sxs-lookup"><span data-stu-id="f94dc-104">Automated investigation and response (AIR) capabilities (included in [Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2) enable you to run automated investigation processes in response to well known threats that exist today.</span></span> <span data-ttu-id="f94dc-105">空中可帮助您的安全操作团队更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="f94dc-105">AIR can help your security operations team operate more efficiently and effectively.</span></span>
- <span data-ttu-id="f94dc-106">若要了解空气的工作原理，请使用本文。</span><span class="sxs-lookup"><span data-stu-id="f94dc-106">To get an overview how AIR works, use this article.</span></span>
- <span data-ttu-id="f94dc-107">若要开始使用 AIR，请参阅[在 Office 365 中自动调查和响应威胁](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="f94dc-107">To get started using AIR, see [Automatically investigate and respond to threats in Office 365](office-365-air.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f94dc-108">您必须是全局管理员、安全管理员、安全操作员或安全读者才能访问空中功能。</span><span class="sxs-lookup"><span data-stu-id="f94dc-108">You must be a global administrator, security administrator, security operator, or security reader to access AIR capabilities.</span></span> <span data-ttu-id="f94dc-109">若要了解有关这些权限的详细信息，请参阅[Microsoft 365 安全中心：角色和权限](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。</span><span class="sxs-lookup"><span data-stu-id="f94dc-109">To learn more about these permissions, see [Microsoft 365 security center: roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="f94dc-110">空气的整体流动</span><span class="sxs-lookup"><span data-stu-id="f94dc-110">The overall flow of AIR</span></span>

<span data-ttu-id="f94dc-111">从较高的层次来看，空气流的工作原理如下所示：</span><span class="sxs-lookup"><span data-stu-id="f94dc-111">At a high level, the AIR flow works like this:</span></span>

|<span data-ttu-id="f94dc-112">阶段</span><span class="sxs-lookup"><span data-stu-id="f94dc-112">Phase</span></span>  |<span data-ttu-id="f94dc-113">涉及的内容</span><span class="sxs-lookup"><span data-stu-id="f94dc-113">What's involved</span></span>  |
|---------|---------|
|<span data-ttu-id="f94dc-114">1</span><span class="sxs-lookup"><span data-stu-id="f94dc-114">1</span></span>     |<span data-ttu-id="f94dc-115">触发的[警报](#alerts)，以及[安全行动手册](#security-playbooks)启动。</span><span class="sxs-lookup"><span data-stu-id="f94dc-115">An [alert](#alerts) that is triggered, and a [security playbook](#security-playbooks) initiates.</span></span>         |
|<span data-ttu-id="f94dc-116">双面</span><span class="sxs-lookup"><span data-stu-id="f94dc-116">2</span></span>     |<span data-ttu-id="f94dc-117">根据特定的警报和安全行动手册，[自动调查立即开始](#example-a-user-reported-phish-message-launches-an-investigation-playbook)。</span><span class="sxs-lookup"><span data-stu-id="f94dc-117">Depending on the particular alert and security playbook, [automated investigation begins immediately](#example-a-user-reported-phish-message-launches-an-investigation-playbook).</span></span> <span data-ttu-id="f94dc-118">（或者，安全分析员可以[手动开始进行自动调查](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)，从报告中的值（如[Explorer](threat-explorer.md)）。</span><span class="sxs-lookup"><span data-stu-id="f94dc-118">(Alternately, a security analyst can [start an automated investigation manually](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer), from a value in a report such as [Explorer](threat-explorer.md).)</span></span>         |
|<span data-ttu-id="f94dc-119">第三章</span><span class="sxs-lookup"><span data-stu-id="f94dc-119">3</span></span>     |<span data-ttu-id="f94dc-120">自动调查运行时，其范围可能会随着新的相关警报的触发而增加。</span><span class="sxs-lookup"><span data-stu-id="f94dc-120">While an automated investigation runs, its scope can increase as new, related alerts are triggered.</span></span>         |
|<span data-ttu-id="f94dc-121">4</span><span class="sxs-lookup"><span data-stu-id="f94dc-121">4</span></span>     |<span data-ttu-id="f94dc-122">在自动调查期间和之后，可以查看[详细信息和结果](#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="f94dc-122">During and after an automated investigation, [details and results](#investigation-graph) are available to view.</span></span> <span data-ttu-id="f94dc-123">结果包括[建议的操作](#recommended-actions)，可采取这些操作来响应和修正发现的任何威胁。</span><span class="sxs-lookup"><span data-stu-id="f94dc-123">Results include [recommended actions](#recommended-actions) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="f94dc-124">此外，还可以使用[行动手册日志](#playbook-log)来跟踪所有调查活动。</span><span class="sxs-lookup"><span data-stu-id="f94dc-124">In addition, a [playbook log](#playbook-log) is available that tracks all investigation activity.</span></span><br/><span data-ttu-id="f94dc-125">如果您的组织使用的是自定义报告解决方案或第三方解决方案，则可以[使用 Office 365 管理活动 API](office-365-air.md#use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions)来查看有关自动调查和威胁的信息。</span><span class="sxs-lookup"><span data-stu-id="f94dc-125">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](office-365-air.md#use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions) to view information about automated investigations and threats.</span></span>         |
|<span data-ttu-id="f94dc-126">5</span><span class="sxs-lookup"><span data-stu-id="f94dc-126">5</span></span>     |<span data-ttu-id="f94dc-127">您的安全操作团队将检查结果和建议，并批准修正操作。</span><span class="sxs-lookup"><span data-stu-id="f94dc-127">Your security operations team reviews the results and recommendations, and approves remediation actions.</span></span> <span data-ttu-id="f94dc-128">在 Office 365 中，仅在组织的安全团队批准时才采取更正措施。</span><span class="sxs-lookup"><span data-stu-id="f94dc-128">In Office 365, remediation actions are taken only upon approval by your organization's security team.</span></span>         |

<span data-ttu-id="f94dc-129">以下各节提供了有关空中的更多详细信息，包括有关警报、安全行动手册和调查详细信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f94dc-129">The following sections provide more details about AIR, including details about alerts, security playbooks, and investigation details.</span></span> <span data-ttu-id="f94dc-130">此外，本文还介绍了如何提供空中工作的两个示例。</span><span class="sxs-lookup"><span data-stu-id="f94dc-130">In addition, two examples of how AIR works are included in this article.</span></span> <span data-ttu-id="f94dc-131">若要开始使用 AIR，请参阅[在 Office 365 中自动调查和响应威胁](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="f94dc-131">To get started using AIR, see [Automatically investigate and respond to threats in Office 365](office-365-air.md).</span></span>

## <a name="alerts"></a><span data-ttu-id="f94dc-132">警报</span><span class="sxs-lookup"><span data-stu-id="f94dc-132">Alerts</span></span>

<span data-ttu-id="f94dc-133">[警报](../../compliance/alert-policies.md#viewing-alerts)表示用于事件响应的安全操作团队工作流的触发器。</span><span class="sxs-lookup"><span data-stu-id="f94dc-133">[Alerts](../../compliance/alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="f94dc-134">确定要调查的正确通知集的优先级，同时确保没有威胁是 unaddressed 的挑战。</span><span class="sxs-lookup"><span data-stu-id="f94dc-134">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="f94dc-135">在手动对通知进行调查时，安全操作团队必须在威胁的风险下对实体（例如，内容、设备和用户）进行搜寻和关联。</span><span class="sxs-lookup"><span data-stu-id="f94dc-135">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="f94dc-136">此类任务和工作流非常耗时，并涉及多个工具和系统。</span><span class="sxs-lookup"><span data-stu-id="f94dc-136">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="f94dc-137">通过空气、调查和响应自动化到关键安全和威胁管理警报，可自动触发安全响应行动手册。</span><span class="sxs-lookup"><span data-stu-id="f94dc-137">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="f94dc-138">在空中的初始发行版（2019年4月开始），根据以下单个事件通知策略生成的警报将自动调查。</span><span class="sxs-lookup"><span data-stu-id="f94dc-138">In the initial release of AIR (beginning April 2019), alerts generated from following single events alert policies are auto-investigated.</span></span> 

- <span data-ttu-id="f94dc-139">检测到潜在的恶意 URL 单击</span><span class="sxs-lookup"><span data-stu-id="f94dc-139">A potentially malicious URL click was detected</span></span>

- <span data-ttu-id="f94dc-140">用户报告为网络钓鱼的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="f94dc-140">Email reported by user as phish\*</span></span>

- <span data-ttu-id="f94dc-141">包含在传递后删除的恶意软件的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="f94dc-141">Email messages containing malware removed after delivery\*</span></span>

- <span data-ttu-id="f94dc-142">包含在传递后删除的网络钓鱼 Url 的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="f94dc-142">Email messages containing phish URLs removed after delivery\*</span></span>

> [!NOTE]
> <span data-ttu-id="f94dc-143">在安全 & 合规性中心（电子邮件通知已关闭）的相应警报策略中，会为标有星号的警报分配一个*信息性*严重性。</span><span class="sxs-lookup"><span data-stu-id="f94dc-143">The alerts marked with an asterisk are assigned an *Informational* severity in the respective alert policies within the Security & Compliance Center, with email notifications turned off.</span></span> <span data-ttu-id="f94dc-144">可以通过[报警策略配置](../../compliance/alert-policies.md#alert-policy-settings)启用电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="f94dc-144">Email notifications can be turned on through [Alert policy configuration](../../compliance/alert-policies.md#alert-policy-settings).</span></span>

<span data-ttu-id="f94dc-145">若要查看警报，请在安全 & 合规性中心中，选择 "**通知** > " "**查看警报**"。</span><span class="sxs-lookup"><span data-stu-id="f94dc-145">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="f94dc-146">选择一个警报以查看其详细信息，然后在那里使用 "**查看调查**" 链接转到相应的[调查](#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="f94dc-146">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span> <span data-ttu-id="f94dc-147">请注意，默认情况下通知视图中隐藏了信息警报。</span><span class="sxs-lookup"><span data-stu-id="f94dc-147">Note that informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="f94dc-148">若要查看它们，您需要更改警报筛选以包含信息警报。</span><span class="sxs-lookup"><span data-stu-id="f94dc-148">To see them, you need to change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="f94dc-149">如果您的组织通过警报管理系统、服务管理系统或安全信息和事件管理（SIEM）系统管理安全警报，则可以通过电子邮件通知或通过[电子邮件通知将 Office 365 警报发送到该系统。Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="f94dc-149">If your organization manages your security alerts through a alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send Office 365 alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="f94dc-150">通过电子邮件或 API 的调查通知通知包括访问安全 & 合规性中心中的警报的链接，使分配的安全管理员能够快速导航到调查。</span><span class="sxs-lookup"><span data-stu-id="f94dc-150">The investigation alert notifications via email or API include links to access the alerts in the Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![链接到调查的警报](../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a><span data-ttu-id="f94dc-152">安全行动手册</span><span class="sxs-lookup"><span data-stu-id="f94dc-152">Security playbooks</span></span>

<span data-ttu-id="f94dc-153">安全行动手册是在 Microsoft 威胁防护中处于自动化的中心的后端策略。</span><span class="sxs-lookup"><span data-stu-id="f94dc-153">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="f94dc-154">AIR 中提供的安全行动手册基于常见的实际安全方案。</span><span class="sxs-lookup"><span data-stu-id="f94dc-154">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="f94dc-155">当您的组织中触发一个警报时，将自动启动安全行动手册。</span><span class="sxs-lookup"><span data-stu-id="f94dc-155">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="f94dc-156">通知触发后，关联的行动手册将自动运行。</span><span class="sxs-lookup"><span data-stu-id="f94dc-156">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="f94dc-157">行动手册将运行调查，查看所有关联的元数据（包括电子邮件、用户、主题、发件人等）。</span><span class="sxs-lookup"><span data-stu-id="f94dc-157">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="f94dc-158">根据行动手册的发现，AIR 推荐了您的组织的安全团队可采取的一组操作来控制和缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="f94dc-158">Based on the playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="f94dc-159">你将使用空中获取的安全行动手册旨在解决组织目前面临的最常见威胁。</span><span class="sxs-lookup"><span data-stu-id="f94dc-159">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="f94dc-160">它们基于安全操作和事件响应团队的输入，包括帮助保护 Microsoft 和客户资产的人员。</span><span class="sxs-lookup"><span data-stu-id="f94dc-160">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="f94dc-161">安全行动手册在几个阶段推出</span><span class="sxs-lookup"><span data-stu-id="f94dc-161">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="f94dc-162">作为空气的一部分，安全行动手册将分阶段推出。</span><span class="sxs-lookup"><span data-stu-id="f94dc-162">As part of AIR, security playbooks are rolling out in phases.</span></span> <span data-ttu-id="f94dc-163">在第1阶段（预览在4月2019开始推出），发布了多个行动手册，其中包含安全管理员查看和批准的操作的建议：</span><span class="sxs-lookup"><span data-stu-id="f94dc-163">During Phase 1 (the preview began rolling out in April 2019), several playbooks were released that include recommendations for actions that security administrators review and approve:</span></span>
- <span data-ttu-id="f94dc-164">用户报告的网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="f94dc-164">User-reported phish message</span></span>
- <span data-ttu-id="f94dc-165">URL 单击 "判定更改"</span><span class="sxs-lookup"><span data-stu-id="f94dc-165">URL click verdict change</span></span> 
- <span data-ttu-id="f94dc-166">恶意软件检测到送达后（恶意软件 ZAP）</span><span class="sxs-lookup"><span data-stu-id="f94dc-166">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="f94dc-167">网络钓鱼检测到传递后的 ZAP （网络钓鱼 ZAP）</span><span class="sxs-lookup"><span data-stu-id="f94dc-167">Phish detected post-delivery ZAP (Phish ZAP)</span></span>

<span data-ttu-id="f94dc-168">第1阶段还包括手动电子邮件调查（使用[威胁资源管理器](threat-explorer.md)）。</span><span class="sxs-lookup"><span data-stu-id="f94dc-168">Phase 1 also includes manual e-mail investigations (using [Threat Explorer](threat-explorer.md)).</span></span>

<span data-ttu-id="f94dc-169">目前正在进行阶段2。</span><span class="sxs-lookup"><span data-stu-id="f94dc-169">Phase 2 is in progress now.</span></span> <span data-ttu-id="f94dc-170">访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)以查看计划和即将推出的其他内容。</span><span class="sxs-lookup"><span data-stu-id="f94dc-170">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what else is planned and coming soon.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="f94dc-171">行动手册包括调查和建议</span><span class="sxs-lookup"><span data-stu-id="f94dc-171">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="f94dc-172">在空中，每个安全行动手册包括：</span><span class="sxs-lookup"><span data-stu-id="f94dc-172">In AIR, each security playbook includes:</span></span> 
- <span data-ttu-id="f94dc-173">根调查</span><span class="sxs-lookup"><span data-stu-id="f94dc-173">a root investigation,</span></span> 
- <span data-ttu-id="f94dc-174">确定并关联其他潜在威胁所需的步骤，以及</span><span class="sxs-lookup"><span data-stu-id="f94dc-174">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="f94dc-175">建议的威胁补救措施。</span><span class="sxs-lookup"><span data-stu-id="f94dc-175">recommended threat remediation actions.</span></span>

<span data-ttu-id="f94dc-176">每个高级别步骤都包含多个执行的子步骤，以提供对威胁的深入、详细和详尽的响应。</span><span class="sxs-lookup"><span data-stu-id="f94dc-176">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="automated-investigations"></a><span data-ttu-id="f94dc-177">自动调查</span><span class="sxs-lookup"><span data-stu-id="f94dc-177">Automated investigations</span></span>

<span data-ttu-id="f94dc-178">"自动调查" 页面显示您的组织的调查及其当前状态。</span><span class="sxs-lookup"><span data-stu-id="f94dc-178">The automated investigations page shows your organization's investigations and their current states.</span></span>

![空气的主要调查页面](../media/air-maininvestigationpage.png) 
  
<span data-ttu-id="f94dc-180">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f94dc-180">You can:</span></span>
- <span data-ttu-id="f94dc-181">直接导航到调查（选择**调查 ID**）。</span><span class="sxs-lookup"><span data-stu-id="f94dc-181">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="f94dc-182">应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="f94dc-182">Apply filters.</span></span> <span data-ttu-id="f94dc-183">从**调查类型**、**时间范围**、**状态**或这些情况的组合中进行选择。</span><span class="sxs-lookup"><span data-stu-id="f94dc-183">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="f94dc-184">将数据导出到 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-184">Export the data to a .csv file.</span></span>

<span data-ttu-id="f94dc-185">调查状态指示分析和操作的进度。</span><span class="sxs-lookup"><span data-stu-id="f94dc-185">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="f94dc-186">在调查运行时，状态更改以指示是否发现威胁，以及是否已批准操作。</span><span class="sxs-lookup"><span data-stu-id="f94dc-186">As the investigation runs, status changes to indicate whether threats were found, and whether actions have been approved.</span></span> 
- <span data-ttu-id="f94dc-187">**启动**：调查已排入队列，以便尽快开始</span><span class="sxs-lookup"><span data-stu-id="f94dc-187">**Starting**: The investigation is queued to begin soon</span></span>
- <span data-ttu-id="f94dc-188">**正在运行**：调查已开始，正在进行分析</span><span class="sxs-lookup"><span data-stu-id="f94dc-188">**Running**: The investigation has started and is conducting its analysis</span></span>
- <span data-ttu-id="f94dc-189">**未找到威胁**：调查已完成其分析，未发现任何威胁</span><span class="sxs-lookup"><span data-stu-id="f94dc-189">**No Threats Found**: The investigation has completed its analysis and no threats were found</span></span>
- <span data-ttu-id="f94dc-190">已**由系统终止**：调查未关闭并在7天后过期</span><span class="sxs-lookup"><span data-stu-id="f94dc-190">**Terminated By System**: The investigation was not closed and expired after 7 days</span></span>
- <span data-ttu-id="f94dc-191">**待处理操作**：调查发现存在建议操作的威胁</span><span class="sxs-lookup"><span data-stu-id="f94dc-191">**Pending Action**: The investigation found threats with actions recommended</span></span>
- <span data-ttu-id="f94dc-192">**发现的威胁**：调查发现威胁，但威胁没有在空中可用的操作</span><span class="sxs-lookup"><span data-stu-id="f94dc-192">**Threats Found**: The investigation found threats, but the threats do not have actions available within AIR</span></span>
- <span data-ttu-id="f94dc-193">已**修正**：调查已完成且已完全修正（已批准所有操作）</span><span class="sxs-lookup"><span data-stu-id="f94dc-193">**Remediated**: The investigation finished and was fully remediated (all actions were approved)</span></span>
- <span data-ttu-id="f94dc-194">**部分修正**：调查已完成，某些建议的操作已获得批准</span><span class="sxs-lookup"><span data-stu-id="f94dc-194">**Partially Remediated**: The investigation finished and some of the recommended actions were approved</span></span>
- <span data-ttu-id="f94dc-195">已**被用户终止**：管理员终止了调查</span><span class="sxs-lookup"><span data-stu-id="f94dc-195">**Terminated By User**: An admin terminated the investigation</span></span>
- <span data-ttu-id="f94dc-196">**失败**：调查过程中出现错误，使其无法达到威胁的结论</span><span class="sxs-lookup"><span data-stu-id="f94dc-196">**Failed**: An error occurred during the investigation that prevented it from reaching a conclusion on threats</span></span>
- <span data-ttu-id="f94dc-197">**按限制排队**：调查因系统处理限制而正在等待分析（以保护服务性能）</span><span class="sxs-lookup"><span data-stu-id="f94dc-197">**Queued By Throttling**: The investigation is waiting for analysis due to system processing limitations (to protect service performance)</span></span>
- <span data-ttu-id="f94dc-198">**由限制终止**：由于调查卷和系统处理限制，无法在足够的时间内完成调查。</span><span class="sxs-lookup"><span data-stu-id="f94dc-198">**Terminated By Throttling**: The investigation could not be completed in sufficient time due to investigation volume and system processing limitations.</span></span> <span data-ttu-id="f94dc-199">您可以通过在资源管理器中选择电子邮件并选择调查操作来重新触发调查。</span><span class="sxs-lookup"><span data-stu-id="f94dc-199">You can re-trigger the investigation by selecting the email in Explorer and selecting the Investigate action.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="f94dc-200">调查图形</span><span class="sxs-lookup"><span data-stu-id="f94dc-200">Investigation graph</span></span>

<span data-ttu-id="f94dc-201">当您打开特定调查时，您将看到 "调查图形" 页。</span><span class="sxs-lookup"><span data-stu-id="f94dc-201">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="f94dc-202">此页面显示所有不同的实体：电子邮件、用户（及其活动）以及自动调查为触发的警报一部分的设备。</span><span class="sxs-lookup"><span data-stu-id="f94dc-202">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![空中调查图形页面](../media/air-investigationgraphpage.png)

<span data-ttu-id="f94dc-204">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f94dc-204">You can:</span></span>
- <span data-ttu-id="f94dc-205">获取当前调查的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f94dc-205">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="f94dc-206">查看调查持续时间的摘要。</span><span class="sxs-lookup"><span data-stu-id="f94dc-206">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="f94dc-207">在可视化中选择一个节点以查看该节点的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f94dc-207">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="f94dc-208">在顶部选择一个选项卡以查看该选项卡的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f94dc-208">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="f94dc-209">通知调查</span><span class="sxs-lookup"><span data-stu-id="f94dc-209">Alert investigation</span></span>

<span data-ttu-id="f94dc-210">在调查的 "**通知**" 选项卡上，您可以查看与调查相关的警报。</span><span class="sxs-lookup"><span data-stu-id="f94dc-210">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="f94dc-211">详细信息包括触发调查的警报以及与调查相关的其他警报（如有风险的登录、成批下载等）。</span><span class="sxs-lookup"><span data-stu-id="f94dc-211">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="f94dc-212">在此页面中，安全分析员还可以查看各个通知的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="f94dc-212">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![空气警报页面](../media/air-investigationalertspage.png)

<span data-ttu-id="f94dc-214">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f94dc-214">You can:</span></span>
- <span data-ttu-id="f94dc-215">获取当前触发警报和任何关联警报的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f94dc-215">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="f94dc-216">在列表中选择一个警报，打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="f94dc-216">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="f94dc-217">电子邮件调查</span><span class="sxs-lookup"><span data-stu-id="f94dc-217">Email investigation</span></span>

<span data-ttu-id="f94dc-218">在调查的 "**电子邮件**" 选项卡上，您可以查看标识为调查一部分的电子邮件的所有群集。</span><span class="sxs-lookup"><span data-stu-id="f94dc-218">On the **Email** tab for an investigation, you can see all the clusters of email identified as part of the investigation.</span></span> 

<span data-ttu-id="f94dc-219">由于组织中的用户发送和接收的电子邮件数量巨大，因此</span><span class="sxs-lookup"><span data-stu-id="f94dc-219">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="f94dc-220">根据邮件头、正文、URL 和附件中的类似属性对电子邮件进行群集化;</span><span class="sxs-lookup"><span data-stu-id="f94dc-220">clustering email messages based on similar attributes from a message header, body, URL and attachments;</span></span> 
- <span data-ttu-id="f94dc-221">将恶意电子邮件与优质电子邮件分开;并</span><span class="sxs-lookup"><span data-stu-id="f94dc-221">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="f94dc-222">对恶意电子邮件采取操作</span><span class="sxs-lookup"><span data-stu-id="f94dc-222">taking action on malicious email messages</span></span> 

<span data-ttu-id="f94dc-223">可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="f94dc-223">can take many hours.</span></span> <span data-ttu-id="f94dc-224">现在，AIR 可以自动执行此过程，从而节省了贵组织的安全团队的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="f94dc-224">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="f94dc-225">电子邮件分析步骤中可能会标识两种不同类型的电子邮件群集：相似性群集和指示器群集。</span><span class="sxs-lookup"><span data-stu-id="f94dc-225">Two different types of email clusters may be identified during the email analysis step: similarity clusters and indicator clusters.</span></span> 
- <span data-ttu-id="f94dc-226">相似性群集是包含相似的发件人和内容属性的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-226">Similarity clusters are email messages that contain similar sender and content attributes.</span></span> <span data-ttu-id="f94dc-227">根据原始检测结果评估这些群集中的恶意内容。</span><span class="sxs-lookup"><span data-stu-id="f94dc-227">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="f94dc-228">包含足够恶意检测的电子邮件群集被认为是恶意的。</span><span class="sxs-lookup"><span data-stu-id="f94dc-228">Email clusters that contain enough malicious detections are considered malicious.</span></span>
- <span data-ttu-id="f94dc-229">指示器群集是包含来自原始电子邮件的指示器实体（文件哈希或 URL）的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-229">Indicator clusters are email messages that contain the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="f94dc-230">将原始文件/URL 实体标识为恶意时，AIR 会将指示器判定为包含该实体的电子邮件的整个群集。</span><span class="sxs-lookup"><span data-stu-id="f94dc-230">When the original file/URL entity is identified as malicious, AIR applies the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="f94dc-231">作为恶意软件识别的文件意味着包含该文件的电子邮件群集被视为恶意软件电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-231">As a file identified as malware means that the cluster of email messages containing that file are treated as malware email messages.</span></span>

<span data-ttu-id="f94dc-232">群集的目标是查找与攻击或市场活动的一部分由同一发件人发送的其他相关电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-232">The goal of clustering is to find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>

<span data-ttu-id="f94dc-233">"**电子邮件**" 选项卡还显示与调查相关的电子邮件项目，例如用户报告的电子邮件详细信息、报告的原始电子邮件、电子邮件 zapped （由于恶意软件/网络钓鱼诈骗等）。</span><span class="sxs-lookup"><span data-stu-id="f94dc-233">The **Email** tab also shows email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

<span data-ttu-id="f94dc-234">"电子邮件" 选项卡上标识的电子邮件计数当前代表 "**电子邮件**" 选项卡上显示的所有电子邮件的总数。由于电子邮件存在于多个群集中，因此标识的电子邮件的实际总数（并受修正操作影响）是所有群集和原始收件人的电子邮件中显示的唯一电子邮件的计数。</span><span class="sxs-lookup"><span data-stu-id="f94dc-234">The email count identified on the email tab currently represents the sum total of all email messages shown on the **Email** tab. Because email messages are present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) is the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span> 

<span data-ttu-id="f94dc-235">由于每个收件人的安全 verdicts、操作和传递位置各不相同，因此每个收件人的资源管理器和空中计数电子邮件都会有所不同。</span><span class="sxs-lookup"><span data-stu-id="f94dc-235">Both Explorer and AIR count email messages on a per recipient basis, since the security verdicts, actions, and delivery locations vary on a per recipient basis.</span></span> <span data-ttu-id="f94dc-236">因此，发送给三个用户的原始电子邮件总共计为三封电子邮件，而不是一封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-236">Thus an original email sent to three users count as a total of three email messages instead of one email.</span></span> <span data-ttu-id="f94dc-237">注释可能会出现两次或多次计数电子邮件的情况，因为电子邮件可能会对其进行多个操作，并且在发生所有操作后，可能会有多个电子邮件副本。</span><span class="sxs-lookup"><span data-stu-id="f94dc-237">Note there may be cases where an email gets counted two or more times, since the email may have multiple actions on it and there may be multiple copies of the email once all actions occur.</span></span> <span data-ttu-id="f94dc-238">例如，在传递时检测到的恶意软件电子邮件可能会导致阻止（隔离）的电子邮件和替换的电子邮件（受警告文件替换的威胁文件，然后传递到用户的邮箱）。</span><span class="sxs-lookup"><span data-stu-id="f94dc-238">For example a malware email that is detected at delivery may result in both a blocked (quarantined) email and a replaced email (threat file replaced with an warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="f94dc-239">由于在系统中有电子邮件的两个副本，因此这两个副本可能会在群集计数中进行计数。</span><span class="sxs-lookup"><span data-stu-id="f94dc-239">Since there are literally two copies of the email in the system - these may both be counted in cluster counts.</span></span> 

<span data-ttu-id="f94dc-240">电子邮件计数是在调查时计算的，当您打开调查 flyouts 时，会重新计算一些计数（基于基础查询）。</span><span class="sxs-lookup"><span data-stu-id="f94dc-240">Email counts are calculated at the time of the investigation and some counts are re-calculated when you open investigation flyouts (based on an underlying query).</span></span> <span data-ttu-id="f94dc-241">"电子邮件" 选项卡上显示的电子邮件群集的电子邮件计数以及在调查时将计算在 "群集浮出控件" 上显示的电子邮件数量值。</span><span class="sxs-lookup"><span data-stu-id="f94dc-241">The email counts shown for the email clusters on the email tab and the email quantity value shown on cluster flyout are calculated at the time of investigation.</span></span> <span data-ttu-id="f94dc-242">在 "群集" 浮出控件的 "电子邮件" 选项卡底部显示的电子邮件计数，资源管理器中显示的电子邮件计数反映在调查的初始分析之后收到的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-242">The email count shown at the bottom of the email tab of the cluster flyout, and the count of email messages shown in Explorer reflect email messages received after the investigation's initial analysis.</span></span> <span data-ttu-id="f94dc-243">因此，显示原始数量10封电子邮件的电子邮件群集会在调查分析阶段和管理员审查调查时，显示总的电子邮件列表15个电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-243">Thus an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when 5 more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span> <span data-ttu-id="f94dc-244">在不同的视图中显示这两个计数将完成，以指示调查时的电子邮件影响和当前的影响，直到运行补救时间为止。</span><span class="sxs-lookup"><span data-stu-id="f94dc-244">Showing both counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

<span data-ttu-id="f94dc-245">例如，请考虑以下方案。</span><span class="sxs-lookup"><span data-stu-id="f94dc-245">As an example, consider the following scenario.</span></span> <span data-ttu-id="f94dc-246">三封电子邮件的第一个群集被认为是网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="f94dc-246">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="f94dc-247">找到具有相同 IP 和主题的类似邮件的另一个群集，并被视为恶意邮件，因为在初始检测过程中将其部分标识为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="f94dc-247">Another cluster of similar messages with the same IP and subject was found and considered malicious, as some of them were identified as phish during initial detection.</span></span> 

![空中电子邮件调查页面](../media/air-investigationemailpage.png)

<span data-ttu-id="f94dc-249">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f94dc-249">You can:</span></span>
- <span data-ttu-id="f94dc-250">获取当前群集结果和发现的威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f94dc-250">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="f94dc-251">单击 "群集" 实体或威胁列表打开显示完整警报详细信息的弹出页面。</span><span class="sxs-lookup"><span data-stu-id="f94dc-251">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="f94dc-252">单击 "电子邮件群集详细信息" 选项卡顶部的 "在资源管理器中打开" 链接进一步调查电子邮件群集</span><span class="sxs-lookup"><span data-stu-id="f94dc-252">Further investigate the email cluster by clicking the 'Open in Explorer' link at the top of the 'Email cluster details' tab</span></span>

![使用浮出控件详细信息的航空调查电子邮件](../media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="f94dc-254">\* 注意：在电子邮件上下文中，您可能会在调查过程中看到一个卷异常威胁曲面。</span><span class="sxs-lookup"><span data-stu-id="f94dc-254">\*Note: In the context of email, you may see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="f94dc-255">卷异常表明调查事件时间与之前的时间框架相比，与调查事件的类似电子邮件中的峰值。</span><span class="sxs-lookup"><span data-stu-id="f94dc-255">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="f94dc-256">这种具有类似特征（例如，subject 和发件人域、正文相似性和发件人 IP）的电子邮件通信的峰值是电子邮件宣传活动或攻击的典型启动。</span><span class="sxs-lookup"><span data-stu-id="f94dc-256">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span> <span data-ttu-id="f94dc-257">但是，批量、垃圾邮件和合法电子邮件活动通常共享这些特征。</span><span class="sxs-lookup"><span data-stu-id="f94dc-257">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span> <span data-ttu-id="f94dc-258">由于使用反病毒引擎、沙箱或恶意信誉识别的恶意软件或网络钓鱼威胁相比，大量异常会带来潜在的威胁，因此可能会降低严重程度。</span><span class="sxs-lookup"><span data-stu-id="f94dc-258">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="f94dc-259">用户调查</span><span class="sxs-lookup"><span data-stu-id="f94dc-259">User investigation</span></span>

<span data-ttu-id="f94dc-260">在 "**用户**" 选项卡上，您可以看到标识为调查的一部分的所有用户。</span><span class="sxs-lookup"><span data-stu-id="f94dc-260">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="f94dc-261">当存在事件或指示这些用户帐户可能受到影响或受到威胁时，用户帐户将出现在调查中。</span><span class="sxs-lookup"><span data-stu-id="f94dc-261">User accounts appear in the investigation when there is an event or indication that those user accounts might be affected or compromised.</span></span>

<span data-ttu-id="f94dc-262">例如，在下图中，空气根据创建的新收件箱规则确定了安全指标和异常情况。</span><span class="sxs-lookup"><span data-stu-id="f94dc-262">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="f94dc-263">可通过此选项卡中的详细视图查看调查的其他详细信息（证据）。损坏的迹象和异常也可能包含来自[Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)的异常检测。</span><span class="sxs-lookup"><span data-stu-id="f94dc-263">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies may also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![空中调查用户页](../media/air-investigationuserspage.png)

<span data-ttu-id="f94dc-265">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f94dc-265">You can:</span></span>
- <span data-ttu-id="f94dc-266">获取已确定的用户结果和发现的风险的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f94dc-266">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="f94dc-267">选择用户以打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="f94dc-267">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="f94dc-268">机器调查</span><span class="sxs-lookup"><span data-stu-id="f94dc-268">Machine investigation</span></span>

<span data-ttu-id="f94dc-269">在 "**计算机**" 选项卡上，您可以看到标识为调查的一部分的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="f94dc-269">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![空中调查计算机页面](../media/air-investigationmachinepage.png)

<span data-ttu-id="f94dc-271">作为调查的一部分，空中将电子邮件威胁与设备相关联。</span><span class="sxs-lookup"><span data-stu-id="f94dc-271">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="f94dc-272">例如，调查会将恶意文件哈希传递到[Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
)以进行调查。</span><span class="sxs-lookup"><span data-stu-id="f94dc-272">For example, an investigation passes a malicious file hash across to [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="f94dc-273">这样，就可以为您的用户自动调查相关的计算机，以帮助确保在云中和终结点上解决威胁。</span><span class="sxs-lookup"><span data-stu-id="f94dc-273">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span> 

<span data-ttu-id="f94dc-274">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f94dc-274">You can:</span></span>
- <span data-ttu-id="f94dc-275">获取发现的当前计算机和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f94dc-275">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="f94dc-276">选择一台计算机以打开在 Microsoft Defender 安全中心的相关[Microsoft DEFENDER ATP 调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)中的视图。</span><span class="sxs-lookup"><span data-stu-id="f94dc-276">Select a machine to open a view that into the related [Microsoft Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="f94dc-277">实体调查</span><span class="sxs-lookup"><span data-stu-id="f94dc-277">Entity investigation</span></span>

<span data-ttu-id="f94dc-278">在 "**实体**" 选项卡上，您可以看到标识为调查的一部分的所有实体。</span><span class="sxs-lookup"><span data-stu-id="f94dc-278">On the **Entities** tab, you can see all the entities identified as part of the investigation.</span></span> 

<span data-ttu-id="f94dc-279">在这里，您可以查看调查的实体和实体类型的详细信息，例如电子邮件、群集、IP 地址、用户等。</span><span class="sxs-lookup"><span data-stu-id="f94dc-279">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="f94dc-280">您还可以查看已分析的实体数以及与每个实体相关联的威胁。</span><span class="sxs-lookup"><span data-stu-id="f94dc-280">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

!["航空调查实体" 页](../media/air-investigationentitiespage.png)

<span data-ttu-id="f94dc-282">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f94dc-282">You can:</span></span>
- <span data-ttu-id="f94dc-283">获取发现的调查实体和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f94dc-283">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="f94dc-284">选择一个实体以打开显示相关实体详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="f94dc-284">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![空中调查实体详细信息](../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="f94dc-286">行动手册日志</span><span class="sxs-lookup"><span data-stu-id="f94dc-286">Playbook log</span></span>

<span data-ttu-id="f94dc-287">在 "**日志**" 选项卡上，您可以查看调查过程中的所有操作手册步骤。</span><span class="sxs-lookup"><span data-stu-id="f94dc-287">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="f94dc-288">该日志将捕获由 Office 365 自动调查功能作为空气的一部分完成的所有操作的完整清单。</span><span class="sxs-lookup"><span data-stu-id="f94dc-288">The log captures a complete inventory of all actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="f94dc-289">它提供了所执行的所有步骤的清晰视图，包括操作本身、说明以及实际 "开始到完成" 的持续时间。</span><span class="sxs-lookup"><span data-stu-id="f94dc-289">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span> 

![航空调查日志页](../media/air-investigationlogpage.png)

<span data-ttu-id="f94dc-291">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f94dc-291">You can:</span></span>
- <span data-ttu-id="f94dc-292">获取有关执行操作手册步骤的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f94dc-292">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="f94dc-293">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-293">Export the results to a CSV file.</span></span>
- <span data-ttu-id="f94dc-294">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="f94dc-294">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="f94dc-295">建议的操作</span><span class="sxs-lookup"><span data-stu-id="f94dc-295">Recommended actions</span></span>

<span data-ttu-id="f94dc-296">在 "**操作**" 选项卡上，您可以查看在调查完成后建议用于修正的所有操作手册操作。</span><span class="sxs-lookup"><span data-stu-id="f94dc-296">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="f94dc-297">操作会捕获 Microsoft 建议在调查结束时执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="f94dc-297">Actions capture the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="f94dc-298">您可以通过选择一个或多个操作来采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="f94dc-298">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="f94dc-299">单击 "**批准**" 可开始进行修正。</span><span class="sxs-lookup"><span data-stu-id="f94dc-299">Clicking **Approve** allows remediation to begin.</span></span> <span data-ttu-id="f94dc-300">（需要适当的权限-需要 "搜索和清除" 角色才能从资源管理器和 AIR 运行操作）。</span><span class="sxs-lookup"><span data-stu-id="f94dc-300">(Appropriate permissions are needed - the 'Search And Purge' role is required to run actions from Explorer and AIR).</span></span> <span data-ttu-id="f94dc-301">例如，安全读者可以查看操作但不能批准。</span><span class="sxs-lookup"><span data-stu-id="f94dc-301">For example, a Security Reader can view actions but not approve them.</span></span> <span data-ttu-id="f94dc-302">注意-您无需批准每个操作。</span><span class="sxs-lookup"><span data-stu-id="f94dc-302">Note - you do not have to approve every action.</span></span> <span data-ttu-id="f94dc-303">如果您不同意建议的操作，或者您的组织不选择特定类型的操作，则可以选择**拒绝**这些操作，也可以仅忽略它们，不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="f94dc-303">If you do not agree with the recommended action or your organization does not choose certain types of actions - then you can either choose to **Reject** the actions or simply ignore them and take no action.</span></span> <span data-ttu-id="f94dc-304">通过批准和/或拒绝所有操作，可以完全关闭调查，同时保留某些操作不完整将导致调查状态更改为 "部分修正" 状态。</span><span class="sxs-lookup"><span data-stu-id="f94dc-304">Approving and/or rejecting all actions let the investigation fully close, while leaving some actions incomplete results in the investigation status changing to a partially remediated state.</span></span>

![航空调查操作页](../media/air-investigationactionspage.png)

<span data-ttu-id="f94dc-306">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f94dc-306">You can:</span></span>
- <span data-ttu-id="f94dc-307">获取对操作手册建议的操作的直观概述。</span><span class="sxs-lookup"><span data-stu-id="f94dc-307">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="f94dc-308">选择一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="f94dc-308">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="f94dc-309">使用注释批准或拒绝建议的操作。</span><span class="sxs-lookup"><span data-stu-id="f94dc-309">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="f94dc-310">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-310">Export the results to a CSV file.</span></span>
- <span data-ttu-id="f94dc-311">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="f94dc-311">Filter the view.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="f94dc-312">示例：用户报告的网络钓鱼邮件启动调查行动手册</span><span class="sxs-lookup"><span data-stu-id="f94dc-312">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="f94dc-313">当组织中的用户提交电子邮件并使用[outlook 或 Outlook Web Access 的报告邮件加载项](enable-the-report-message-add-in.md)将其报告给 Microsoft 时，该报告也会发送到您的系统，并在用户报告的视图中显示在资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="f94dc-313">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md), the report is also sent to your system and is visible in Explorer in the User-reported view.</span></span> <span data-ttu-id="f94dc-314">此用户报告的消息现在会触发基于系统的信息警报，这将自动启动调查行动手册。</span><span class="sxs-lookup"><span data-stu-id="f94dc-314">This user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="f94dc-315">在根调查阶段，会评估电子邮件的各个方面。</span><span class="sxs-lookup"><span data-stu-id="f94dc-315">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="f94dc-316">具体包括：</span><span class="sxs-lookup"><span data-stu-id="f94dc-316">These include:</span></span>
- <span data-ttu-id="f94dc-317">确定它可能属于哪种类型的威胁;</span><span class="sxs-lookup"><span data-stu-id="f94dc-317">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="f94dc-318">发件人数;</span><span class="sxs-lookup"><span data-stu-id="f94dc-318">Who sent it;</span></span>
- <span data-ttu-id="f94dc-319">发送电子邮件的位置（发送基础结构）;</span><span class="sxs-lookup"><span data-stu-id="f94dc-319">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="f94dc-320">是否已传递或阻止电子邮件的其他实例;</span><span class="sxs-lookup"><span data-stu-id="f94dc-320">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="f94dc-321">我们分析家中的一种评估;</span><span class="sxs-lookup"><span data-stu-id="f94dc-321">An assessment from our analysts;</span></span>
- <span data-ttu-id="f94dc-322">电子邮件是否与任何已知的市场活动相关联;</span><span class="sxs-lookup"><span data-stu-id="f94dc-322">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="f94dc-323">等等。</span><span class="sxs-lookup"><span data-stu-id="f94dc-323">and more.</span></span>

<span data-ttu-id="f94dc-324">根调查完成后，行动手册提供了要对其关联的原始电子邮件和实体执行的建议操作的列表。</span><span class="sxs-lookup"><span data-stu-id="f94dc-324">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="f94dc-325">接下来，执行以下几个威胁调查和搜寻步骤：</span><span class="sxs-lookup"><span data-stu-id="f94dc-325">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="f94dc-326">搜索其他电子邮件群集中的类似电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-326">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="f94dc-327">该信号与其他平台（如[Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共享。</span><span class="sxs-lookup"><span data-stu-id="f94dc-327">The signal is shared with other platforms, such as [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="f94dc-328">确定是否有用户通过可疑电子邮件中的任何恶意链接单击过。</span><span class="sxs-lookup"><span data-stu-id="f94dc-328">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="f94dc-329">跨 Office 365 Exchange Online Protection （[EOP](exchange-online-protection-eop.md)）和 Office 365 高级威胁防护（[ATP](office-365-atp.md)）执行检查以查看用户是否报告了任何其他类似的消息。</span><span class="sxs-lookup"><span data-stu-id="f94dc-329">A check is done across Office 365 Exchange Online Protection ([EOP](exchange-online-protection-eop.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="f94dc-330">将执行检查以查看是否已泄露用户。</span><span class="sxs-lookup"><span data-stu-id="f94dc-330">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="f94dc-331">此检查在[Microsoft 云应用安全](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)中利用信号，关联任何相关的用户活动异常。</span><span class="sxs-lookup"><span data-stu-id="f94dc-331">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span> 

<span data-ttu-id="f94dc-332">在搜寻阶段，会为各种搜寻步骤分配风险和威胁。</span><span class="sxs-lookup"><span data-stu-id="f94dc-332">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="f94dc-333">修正是行动手册的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="f94dc-333">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="f94dc-334">在此阶段中，将根据调查和搜寻阶段采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="f94dc-334">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="f94dc-335">示例：安全管理员触发来自威胁资源管理器的调查</span><span class="sxs-lookup"><span data-stu-id="f94dc-335">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="f94dc-336">除了由警报触发的自动调查之外，组织的安全操作团队可以通过[威胁资源管理器](threat-explorer.md)中的视图触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="f94dc-336">In addition to automatic investigations that are triggered by an alert, your organization's security operations team can trigger an automatic investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>

<span data-ttu-id="f94dc-337">例如，假设您正在查看资源管理器中有关用户报告的消息的数据。</span><span class="sxs-lookup"><span data-stu-id="f94dc-337">For example, suppose that you are viewing data in Explorer about user-reported messages.</span></span> <span data-ttu-id="f94dc-338">您可以在结果列表中选择一个项目，然后单击 "**调查**"。</span><span class="sxs-lookup"><span data-stu-id="f94dc-338">You can select an item in the list of results, and then click **Investigate**.</span></span>

![使用调查按钮的资源管理器中的用户报告的消息](../media/Explorer-UserReported-Investigate.png)

<span data-ttu-id="f94dc-340">作为另一个示例，假设您要查看检测为包含恶意软件的电子邮件的数据，并且有几封电子邮件被检测为包含恶意软件。</span><span class="sxs-lookup"><span data-stu-id="f94dc-340">As another example, suppose you are viewing data about email messages detected as containing malware, and there are several email messages detected as containing malware.</span></span> <span data-ttu-id="f94dc-341">您可以选择 "**电子邮件**" 选项卡，选择一个或多个电子邮件，然后在 "**操作**" 菜单上选择 "**调查**"。</span><span class="sxs-lookup"><span data-stu-id="f94dc-341">You can select the **Email** tab, select one or more email messages, and then, on the **Actions** menu, select **Investigate**.</span></span> 

![在资源管理器中开始调查恶意软件](../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="f94dc-343">与由警报触发的行动手册类似，通过资源管理器中的视图触发的自动调查包括根调查、标识和关联威胁的步骤以及缓解这些威胁的建议操作。</span><span class="sxs-lookup"><span data-stu-id="f94dc-343">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="f94dc-344">如何获取空中</span><span class="sxs-lookup"><span data-stu-id="f94dc-344">How to get AIR</span></span>

<span data-ttu-id="f94dc-345">Office 365 AIR 包括在以下订阅中：</span><span class="sxs-lookup"><span data-stu-id="f94dc-345">Office 365 AIR are included in the following subscriptions:</span></span>

- <span data-ttu-id="f94dc-346">Microsoft 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="f94dc-346">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="f94dc-347">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="f94dc-347">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="f94dc-348">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="f94dc-348">Microsoft Threat Protection</span></span>
- <span data-ttu-id="f94dc-349">Office 365 高级威胁防护计划2</span><span class="sxs-lookup"><span data-stu-id="f94dc-349">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="f94dc-350">如果你没有这些订阅，请[启动免费试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US)。</span><span class="sxs-lookup"><span data-stu-id="f94dc-350">If you don't have any of these subscriptions, [start a free trial](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US).</span></span>

<span data-ttu-id="f94dc-351">若要了解有关功能可用性的详细信息，请访问[跨高级威胁防护（ATP）计划的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="f94dc-351">To learn more about feature availability, visit the [Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f94dc-352">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f94dc-352">Next steps</span></span>

[<span data-ttu-id="f94dc-353">开始使用 Office 365 中的 AIR</span><span class="sxs-lookup"><span data-stu-id="f94dc-353">Get started using AIR in Office 365</span></span>](office-365-air.md)

[<span data-ttu-id="f94dc-354">了解 Microsoft Defender ATP 中的空气</span><span class="sxs-lookup"><span data-stu-id="f94dc-354">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 

[<span data-ttu-id="f94dc-355">访问 Microsoft 365 路线图以了解即将推出和推出的内容</span><span class="sxs-lookup"><span data-stu-id="f94dc-355">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)