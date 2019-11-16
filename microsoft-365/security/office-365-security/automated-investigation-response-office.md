---
title: Office 365 中的自动事件响应（空气）
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 11/15/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 概述 Office 365 高级威胁防护计划2中的自动化调查和响应功能。
ms.openlocfilehash: 18da20491f9641b8313304e350f9c224b63cc5d9
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673398"
---
# <a name="automated-incident-response-air-in-office-365"></a><span data-ttu-id="34859-103">Office 365 中的自动事件响应（空气）</span><span class="sxs-lookup"><span data-stu-id="34859-103">Automated incident response (AIR) in Office 365</span></span>

<span data-ttu-id="34859-104">自动化事件响应（空中）功能使您能够运行自动化的调查过程，以应对目前存在的已知威胁。</span><span class="sxs-lookup"><span data-stu-id="34859-104">Automated incident response (AIR) capabilities enable you to run automated investigation processes in response to well known threats that exist today.</span></span> <span data-ttu-id="34859-105">空中可帮助您的安全操作团队更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="34859-105">AIR can help your security operations team operate more efficiently and effectively.</span></span>
- <span data-ttu-id="34859-106">若要了解空气的工作原理，请使用本文。</span><span class="sxs-lookup"><span data-stu-id="34859-106">To get an overview how AIR works, use this article.</span></span>
- <span data-ttu-id="34859-107">若要开始使用 AIR，请参阅[在 Office 365 中自动调查和响应威胁](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="34859-107">To get started using AIR, see [Automatically investigate and respond to threats in Office 365](office-365-air.md).</span></span>

> [!NOTE]
> <span data-ttu-id="34859-108">您必须是全局管理员、安全管理员、安全操作员或安全读者才能访问空中功能。</span><span class="sxs-lookup"><span data-stu-id="34859-108">You must be a global administrator, security administrator, security operator, or security reader to access AIR capabilities.</span></span> <span data-ttu-id="34859-109">若要了解有关这些权限的详细信息，请参阅[Microsoft 365 安全中心：角色和权限](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。</span><span class="sxs-lookup"><span data-stu-id="34859-109">To learn more about these permissions, see [Microsoft 365 security center: roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="34859-110">空气的整体流动</span><span class="sxs-lookup"><span data-stu-id="34859-110">The overall flow of AIR</span></span>

<span data-ttu-id="34859-111">从较高的层次来看，空气流的工作原理如下所示：</span><span class="sxs-lookup"><span data-stu-id="34859-111">At a high level, the AIR flow works like this:</span></span>

|<span data-ttu-id="34859-112">阶段</span><span class="sxs-lookup"><span data-stu-id="34859-112">Phase</span></span>  |<span data-ttu-id="34859-113">涉及的内容</span><span class="sxs-lookup"><span data-stu-id="34859-113">What's involved</span></span>  |
|---------|---------|
|<span data-ttu-id="34859-114">1</span><span class="sxs-lookup"><span data-stu-id="34859-114">1</span></span>     |<span data-ttu-id="34859-115">触发的[警报](#alerts)，以及[安全行动手册](#security-playbooks)启动。</span><span class="sxs-lookup"><span data-stu-id="34859-115">An [alert](#alerts) that is triggered, and a [security playbook](#security-playbooks) initiates.</span></span>         |
|<span data-ttu-id="34859-116">双面</span><span class="sxs-lookup"><span data-stu-id="34859-116">2</span></span>     |<span data-ttu-id="34859-117">根据特定的警报和安全行动手册，[自动调查立即开始](#example-a-user-reported-phish-message-launches-an-investigation-playbook)。</span><span class="sxs-lookup"><span data-stu-id="34859-117">Depending on the particular alert and security playbook, [automated investigation begins immediately](#example-a-user-reported-phish-message-launches-an-investigation-playbook).</span></span> <span data-ttu-id="34859-118">（或者，安全分析员可以[手动开始进行自动调查](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)，从报告中的值（如[Explorer](threat-explorer.md)）。</span><span class="sxs-lookup"><span data-stu-id="34859-118">(Alternately, a security analyst can [start an automated investigation manually](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer), from a value in a report such as [Explorer](threat-explorer.md).)</span></span>         |
|<span data-ttu-id="34859-119">第三章</span><span class="sxs-lookup"><span data-stu-id="34859-119">3</span></span>     |<span data-ttu-id="34859-120">自动调查运行时，其范围可能会随着新的相关警报的触发而增加。</span><span class="sxs-lookup"><span data-stu-id="34859-120">While an automated investigation runs, its scope can increase as new, related alerts are triggered.</span></span>         |
|<span data-ttu-id="34859-121">4</span><span class="sxs-lookup"><span data-stu-id="34859-121">4</span></span>     |<span data-ttu-id="34859-122">在自动调查期间和之后，可以查看[详细信息和结果](#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="34859-122">During and after an automated investigation, [details and results](#investigation-graph) are available to view.</span></span> <span data-ttu-id="34859-123">结果包括[建议的操作](#recommended-actions)，可采取这些操作来响应和修正发现的任何威胁。</span><span class="sxs-lookup"><span data-stu-id="34859-123">Results include [recommended actions](#recommended-actions) that can be taken to respond and remediate any threats that were found.</span></span> <span data-ttu-id="34859-124">此外，还可以使用[行动手册日志](#playbook-log)来跟踪所有调查活动。</span><span class="sxs-lookup"><span data-stu-id="34859-124">In addition, a [playbook log](#playbook-log) is available that tracks all investigation activity.</span></span><br/><span data-ttu-id="34859-125">如果您的组织使用的是自定义报告解决方案或第三方解决方案，则可以[使用 Office 365 管理活动 API](office-365-air.md#use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions)来查看有关自动调查和威胁的信息。</span><span class="sxs-lookup"><span data-stu-id="34859-125">If your organization is using a custom reporting solution or a third-party solution, you can [use the Office 365 Management Activity API](office-365-air.md#use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions) to view information about automated investigations and threats.</span></span>         |
|<span data-ttu-id="34859-126">5</span><span class="sxs-lookup"><span data-stu-id="34859-126">5</span></span>     |<span data-ttu-id="34859-127">您的安全操作团队将检查结果和建议，并批准修正操作。</span><span class="sxs-lookup"><span data-stu-id="34859-127">Your security operations team reviews the results and recommendations, and approves remediation actions.</span></span> <span data-ttu-id="34859-128">在 Office 365 中，仅在组织的安全团队批准时才采取更正措施。</span><span class="sxs-lookup"><span data-stu-id="34859-128">In Office 365, remediation actions are taken only upon approval by your organization's security team.</span></span>         |

<span data-ttu-id="34859-129">以下各节提供了有关空中的更多详细信息，包括有关警报、安全行动手册和调查详细信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="34859-129">The following sections provide more details about AIR, including details about alerts, security playbooks, and investigation details.</span></span> <span data-ttu-id="34859-130">此外，本文还介绍了如何提供空中工作的两个示例。</span><span class="sxs-lookup"><span data-stu-id="34859-130">In addition, two examples of how AIR works are included in this article.</span></span> <span data-ttu-id="34859-131">若要开始使用 AIR，请参阅[在 Office 365 中自动调查和响应威胁](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="34859-131">To get started using AIR, see [Automatically investigate and respond to threats in Office 365](office-365-air.md).</span></span>

## <a name="alerts"></a><span data-ttu-id="34859-132">警报</span><span class="sxs-lookup"><span data-stu-id="34859-132">Alerts</span></span>

<span data-ttu-id="34859-133">[警报](../../compliance/alert-policies.md#viewing-alerts)表示用于事件响应的安全操作团队工作流的触发器。</span><span class="sxs-lookup"><span data-stu-id="34859-133">[Alerts](../../compliance/alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="34859-134">确定要调查的正确通知集的优先级，同时确保没有威胁是 unaddressed 的挑战。</span><span class="sxs-lookup"><span data-stu-id="34859-134">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="34859-135">在手动对通知进行调查时，安全操作团队必须在威胁的风险下对实体（例如，内容、设备和用户）进行搜寻和关联。</span><span class="sxs-lookup"><span data-stu-id="34859-135">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="34859-136">此类任务和工作流非常耗时，并涉及多个工具和系统。</span><span class="sxs-lookup"><span data-stu-id="34859-136">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="34859-137">通过空气、调查和响应自动化到关键安全和威胁管理警报，可自动触发安全响应行动手册。</span><span class="sxs-lookup"><span data-stu-id="34859-137">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="34859-138">在空中的初始发行版（2019年4月开始），根据以下单个事件通知策略生成的警报将自动调查。</span><span class="sxs-lookup"><span data-stu-id="34859-138">In the initial release of AIR (beginning April 2019), alerts generated from following single events alert policies are auto-investigated.</span></span> 

- <span data-ttu-id="34859-139">检测到潜在的恶意 URL 单击</span><span class="sxs-lookup"><span data-stu-id="34859-139">A potentially malicious URL click was detected</span></span>

- <span data-ttu-id="34859-140">用户报告为网络钓鱼的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="34859-140">Email reported by user as phish\*</span></span>

- <span data-ttu-id="34859-141">包含在传递后删除的恶意软件的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="34859-141">Email messages containing malware removed after delivery\*</span></span>

- <span data-ttu-id="34859-142">包含在传递后删除的网络钓鱼 Url 的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="34859-142">Email messages containing phish URLs removed after delivery\*</span></span>

- <span data-ttu-id="34859-143">检测到可疑的电子邮件发送模式#</span><span class="sxs-lookup"><span data-stu-id="34859-143">Suspicious email sending patterns detected#</span></span>

- <span data-ttu-id="34859-144">限制用户发送电子邮件#</span><span class="sxs-lookup"><span data-stu-id="34859-144">User restricted from sending email#</span></span>

> [!NOTE]
> <span data-ttu-id="34859-145">以星号（*）标记的警报在安全 & 合规性中心（电子邮件通知已关闭）的相应警报策略中被分配了一个*信息性\*严重性。</span><span class="sxs-lookup"><span data-stu-id="34859-145">The alerts marked with an asterisk (\*) are assigned an *Informational* severity in the respective alert policies within the Security & Compliance Center, with email notifications turned off.</span></span> <span data-ttu-id="34859-146">可以通过[报警策略配置](../../compliance/alert-policies.md#alert-policy-settings)启用电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="34859-146">Email notifications can be turned on through [Alert policy configuration](../../compliance/alert-policies.md#alert-policy-settings).</span></span> <span data-ttu-id="34859-147">使用哈希（#）标记的警报通常是与公共预览版行动手册相关联的警报。</span><span class="sxs-lookup"><span data-stu-id="34859-147">Alerts marked with a hash (#) are generally available alerts associated with public preview playbooks.</span></span>

<span data-ttu-id="34859-148">若要查看警报，请在安全 & 合规性中心中，选择 "**通知** > " "**查看警报**"。</span><span class="sxs-lookup"><span data-stu-id="34859-148">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="34859-149">选择一个警报以查看其详细信息，然后在那里使用 "**查看调查**" 链接转到相应的[调查](#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="34859-149">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span> <span data-ttu-id="34859-150">请注意，默认情况下通知视图中隐藏了信息警报。</span><span class="sxs-lookup"><span data-stu-id="34859-150">Note that informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="34859-151">若要查看它们，您需要更改警报筛选以包含信息警报。</span><span class="sxs-lookup"><span data-stu-id="34859-151">To see them, you need to change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="34859-152">如果您的组织通过警报管理系统、服务管理系统或安全信息和事件管理（SIEM）系统管理安全警报，则可以通过电子邮件通知或通过[Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)将 Office 365 警报发送到该系统。</span><span class="sxs-lookup"><span data-stu-id="34859-152">If your organization manages your security alerts through a alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send Office 365 alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="34859-153">通过电子邮件或 API 的调查通知通知包括访问安全 & 合规性中心中的警报的链接，使分配的安全管理员能够快速导航到调查。</span><span class="sxs-lookup"><span data-stu-id="34859-153">The investigation alert notifications via email or API include links to access the alerts in the Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![链接到调查的警报](../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a><span data-ttu-id="34859-155">安全行动手册</span><span class="sxs-lookup"><span data-stu-id="34859-155">Security playbooks</span></span>

<span data-ttu-id="34859-156">安全行动手册是在 Microsoft 威胁防护中处于自动化的中心的后端策略。</span><span class="sxs-lookup"><span data-stu-id="34859-156">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="34859-157">AIR 中提供的安全行动手册基于常见的实际安全方案。</span><span class="sxs-lookup"><span data-stu-id="34859-157">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="34859-158">当您的组织中触发一个警报时，将自动启动安全行动手册。</span><span class="sxs-lookup"><span data-stu-id="34859-158">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="34859-159">通知触发后，关联的行动手册将自动运行。</span><span class="sxs-lookup"><span data-stu-id="34859-159">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="34859-160">行动手册将运行调查，查看所有关联的元数据（包括电子邮件、用户、主题、发件人等）。</span><span class="sxs-lookup"><span data-stu-id="34859-160">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="34859-161">根据行动手册的发现，AIR 推荐了您的组织的安全团队可采取的一组操作来控制和缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="34859-161">Based on the playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="34859-162">你将使用空中获取的安全行动手册旨在解决组织目前面临的最常见威胁。</span><span class="sxs-lookup"><span data-stu-id="34859-162">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="34859-163">它们基于安全操作和事件响应团队的输入，包括帮助保护 Microsoft 和客户资产的人员。</span><span class="sxs-lookup"><span data-stu-id="34859-163">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="34859-164">安全行动手册在几个阶段推出</span><span class="sxs-lookup"><span data-stu-id="34859-164">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="34859-165">作为空气的一部分，安全行动手册将分阶段推出。</span><span class="sxs-lookup"><span data-stu-id="34859-165">As part of AIR, security playbooks are rolling out in phases.</span></span> <span data-ttu-id="34859-166">第1阶段现已推出，其中包含多个行动手册，这些操作提供了安全管理员可以查看和批准的操作建议：</span><span class="sxs-lookup"><span data-stu-id="34859-166">Phase 1 is now generally available and includes several playbooks that provide recommendations for actions that security administrators can review and approve:</span></span>
- <span data-ttu-id="34859-167">用户报告的网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="34859-167">User-reported phish message</span></span>
- <span data-ttu-id="34859-168">URL 单击 "判定更改"</span><span class="sxs-lookup"><span data-stu-id="34859-168">URL click verdict change</span></span>
- <span data-ttu-id="34859-169">恶意软件检测到送达后（恶意软件 ZAP）</span><span class="sxs-lookup"><span data-stu-id="34859-169">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="34859-170">网络钓鱼检测到传递后的 ZAP （网络钓鱼 ZAP）</span><span class="sxs-lookup"><span data-stu-id="34859-170">Phish detected post-delivery ZAP (Phish ZAP)</span></span>

<span data-ttu-id="34859-171">第1阶段还包括对手动电子邮件调查的支持（使用[威胁资源管理器](threat-explorer.md)）。</span><span class="sxs-lookup"><span data-stu-id="34859-171">Phase 1 also includes support for manual e-mail investigations (using [Threat Explorer](threat-explorer.md)).</span></span>

<span data-ttu-id="34859-172">第2阶段现在与**公共预览版**中的以下行动手册结合在一起，为操作和 aiding 安全管理员提供调查问题的建议：</span><span class="sxs-lookup"><span data-stu-id="34859-172">Phase 2 is now progress with the following playbooks in **public preview**, providing recommendations for actions and aiding security administrators in investigating issues:</span></span>
- <span data-ttu-id="34859-173">用户报告为 "已损坏" （公用预览）</span><span class="sxs-lookup"><span data-stu-id="34859-173">User reported as compromised (public preview)</span></span>

<span data-ttu-id="34859-174">在完成后，将立即发布后续行动手册。</span><span class="sxs-lookup"><span data-stu-id="34859-174">Further playbooks will be released as they are completed.</span></span> <span data-ttu-id="34859-175">访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)以查看计划和即将推出的其他内容。</span><span class="sxs-lookup"><span data-stu-id="34859-175">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what else is planned and coming soon.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="34859-176">行动手册包括调查和建议</span><span class="sxs-lookup"><span data-stu-id="34859-176">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="34859-177">在空中，每个安全行动手册包括：</span><span class="sxs-lookup"><span data-stu-id="34859-177">In AIR, each security playbook includes:</span></span> 
- <span data-ttu-id="34859-178">根调查</span><span class="sxs-lookup"><span data-stu-id="34859-178">a root investigation,</span></span> 
- <span data-ttu-id="34859-179">确定并关联其他潜在威胁所需的步骤，以及</span><span class="sxs-lookup"><span data-stu-id="34859-179">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="34859-180">建议的威胁补救措施。</span><span class="sxs-lookup"><span data-stu-id="34859-180">recommended threat remediation actions.</span></span>

<span data-ttu-id="34859-181">每个高级别步骤都包含多个执行的子步骤，以提供对威胁的深入、详细和详尽的响应。</span><span class="sxs-lookup"><span data-stu-id="34859-181">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="automated-investigations"></a><span data-ttu-id="34859-182">自动调查</span><span class="sxs-lookup"><span data-stu-id="34859-182">Automated investigations</span></span>

<span data-ttu-id="34859-183">"自动调查" 页面显示您的组织的调查及其当前状态。</span><span class="sxs-lookup"><span data-stu-id="34859-183">The automated investigations page shows your organization's investigations and their current states.</span></span>

![空气的主要调查页面](../media/air-maininvestigationpage.png) 
  
<span data-ttu-id="34859-185">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="34859-185">You can:</span></span>
- <span data-ttu-id="34859-186">直接导航到调查（选择**调查 ID**）。</span><span class="sxs-lookup"><span data-stu-id="34859-186">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="34859-187">应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="34859-187">Apply filters.</span></span> <span data-ttu-id="34859-188">从**调查类型**、**时间范围**、**状态**或这些情况的组合中进行选择。</span><span class="sxs-lookup"><span data-stu-id="34859-188">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="34859-189">将数据导出到 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="34859-189">Export the data to a .csv file.</span></span>

<span data-ttu-id="34859-190">调查状态指示分析和操作的进度。</span><span class="sxs-lookup"><span data-stu-id="34859-190">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="34859-191">在调查运行时，状态更改以指示是否发现威胁，以及是否已批准操作。</span><span class="sxs-lookup"><span data-stu-id="34859-191">As the investigation runs, status changes to indicate whether threats were found, and whether actions have been approved.</span></span> 


|<span data-ttu-id="34859-192">状态</span><span class="sxs-lookup"><span data-stu-id="34859-192">Status</span></span>  |<span data-ttu-id="34859-193">含义</span><span class="sxs-lookup"><span data-stu-id="34859-193">What it means</span></span>  |
|---------|---------|
|<span data-ttu-id="34859-194">即将开始</span><span class="sxs-lookup"><span data-stu-id="34859-194">Starting</span></span> | <span data-ttu-id="34859-195">调查已排入队列，以便尽快开始</span><span class="sxs-lookup"><span data-stu-id="34859-195">The investigation is queued to begin soon</span></span> |
|<span data-ttu-id="34859-196">运行</span><span class="sxs-lookup"><span data-stu-id="34859-196">Running</span></span> | <span data-ttu-id="34859-197">调查已开始，正在进行分析</span><span class="sxs-lookup"><span data-stu-id="34859-197">The investigation has started and is conducting its analysis</span></span> |
|<span data-ttu-id="34859-198">找不到威胁</span><span class="sxs-lookup"><span data-stu-id="34859-198">No Threats Found</span></span> | <span data-ttu-id="34859-199">调查已完成其分析，未发现任何威胁</span><span class="sxs-lookup"><span data-stu-id="34859-199">The investigation has completed its analysis and no threats were found</span></span> |
|<span data-ttu-id="34859-200">已由系统终止</span><span class="sxs-lookup"><span data-stu-id="34859-200">Terminated By System</span></span> | <span data-ttu-id="34859-201">调查未关闭并在7天后过期</span><span class="sxs-lookup"><span data-stu-id="34859-201">The investigation was not closed and expired after 7 days</span></span> |
|<span data-ttu-id="34859-202">挂起的操作</span><span class="sxs-lookup"><span data-stu-id="34859-202">Pending Action</span></span> | <span data-ttu-id="34859-203">调查发现了与建议的操作有关的威胁</span><span class="sxs-lookup"><span data-stu-id="34859-203">The investigation found threats with actions recommended</span></span> |
|<span data-ttu-id="34859-204">发现威胁</span><span class="sxs-lookup"><span data-stu-id="34859-204">Threats Found</span></span> | <span data-ttu-id="34859-205">调查发现威胁，但威胁没有在空中可用的操作</span><span class="sxs-lookup"><span data-stu-id="34859-205">The investigation found threats, but the threats do not have actions available within AIR</span></span> |
|<span data-ttu-id="34859-206">已修正</span><span class="sxs-lookup"><span data-stu-id="34859-206">Remediated</span></span> | <span data-ttu-id="34859-207">调查已完成且已完全修正（已批准所有操作）</span><span class="sxs-lookup"><span data-stu-id="34859-207">The investigation finished and was fully remediated (all actions were approved)</span></span> |
|<span data-ttu-id="34859-208">部分修正</span><span class="sxs-lookup"><span data-stu-id="34859-208">Partially Remediated</span></span> | <span data-ttu-id="34859-209">调查已完成，某些建议的操作已获得批准</span><span class="sxs-lookup"><span data-stu-id="34859-209">The investigation finished and some of the recommended actions were approved</span></span> |
|<span data-ttu-id="34859-210">由用户终止</span><span class="sxs-lookup"><span data-stu-id="34859-210">Terminated By User</span></span> | <span data-ttu-id="34859-211">管理员终止了调查</span><span class="sxs-lookup"><span data-stu-id="34859-211">An admin terminated the investigation</span></span> |
|<span data-ttu-id="34859-212">Failed</span><span class="sxs-lookup"><span data-stu-id="34859-212">Failed</span></span> | <span data-ttu-id="34859-213">调查过程中发生错误，阻止它达到威胁的结论</span><span class="sxs-lookup"><span data-stu-id="34859-213">An error occurred during the investigation that prevented it from reaching a conclusion on threats</span></span> |
|<span data-ttu-id="34859-214">按限制排队</span><span class="sxs-lookup"><span data-stu-id="34859-214">Queued By Throttling</span></span> | <span data-ttu-id="34859-215">由于系统处理限制，调查正在等待分析（以保护服务性能）</span><span class="sxs-lookup"><span data-stu-id="34859-215">The investigation is waiting for analysis due to system processing limitations (to protect service performance)</span></span> |
|<span data-ttu-id="34859-216">已通过限制终止</span><span class="sxs-lookup"><span data-stu-id="34859-216">Terminated By Throttling</span></span> | <span data-ttu-id="34859-217">由于调查卷和系统处理限制，无法在足够的时间内完成调查。</span><span class="sxs-lookup"><span data-stu-id="34859-217">The investigation could not be completed in sufficient time due to investigation volume and system processing limitations.</span></span> <span data-ttu-id="34859-218">您可以通过在资源管理器中选择电子邮件并选择调查操作来重新触发调查。</span><span class="sxs-lookup"><span data-stu-id="34859-218">You can re-trigger the investigation by selecting the email in Explorer and selecting the Investigate action.</span></span> |

### <a name="investigation-graph"></a><span data-ttu-id="34859-219">调查图形</span><span class="sxs-lookup"><span data-stu-id="34859-219">Investigation graph</span></span>

<span data-ttu-id="34859-220">当您打开特定调查时，您将看到 "调查图形" 页。</span><span class="sxs-lookup"><span data-stu-id="34859-220">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="34859-221">此页面显示所有不同的实体：电子邮件、用户（及其活动）以及自动调查为触发的警报一部分的设备。</span><span class="sxs-lookup"><span data-stu-id="34859-221">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![空中调查图形页面](../media/air-investigationgraphpage.png)

<span data-ttu-id="34859-223">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="34859-223">You can:</span></span>
- <span data-ttu-id="34859-224">获取当前调查的直观概述。</span><span class="sxs-lookup"><span data-stu-id="34859-224">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="34859-225">查看调查持续时间的摘要。</span><span class="sxs-lookup"><span data-stu-id="34859-225">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="34859-226">在可视化中选择一个节点以查看该节点的详细信息。</span><span class="sxs-lookup"><span data-stu-id="34859-226">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="34859-227">在顶部选择一个选项卡以查看该选项卡的详细信息。</span><span class="sxs-lookup"><span data-stu-id="34859-227">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="34859-228">通知调查</span><span class="sxs-lookup"><span data-stu-id="34859-228">Alert investigation</span></span>

<span data-ttu-id="34859-229">在调查的 "**通知**" 选项卡上，您可以查看与调查相关的警报。</span><span class="sxs-lookup"><span data-stu-id="34859-229">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="34859-230">详细信息包括触发调查的警报以及与调查相关的其他警报（如有风险的登录、成批下载等）。</span><span class="sxs-lookup"><span data-stu-id="34859-230">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="34859-231">在此页面中，安全分析员还可以查看各个通知的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="34859-231">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![空气警报页面](../media/air-investigationalertspage.png)

<span data-ttu-id="34859-233">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="34859-233">You can:</span></span>
- <span data-ttu-id="34859-234">获取当前触发警报和任何关联警报的直观概述。</span><span class="sxs-lookup"><span data-stu-id="34859-234">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="34859-235">在列表中选择一个警报，打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="34859-235">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="34859-236">电子邮件调查</span><span class="sxs-lookup"><span data-stu-id="34859-236">Email investigation</span></span>

<span data-ttu-id="34859-237">在调查的 "**电子邮件**" 选项卡上，您可以查看标识为调查一部分的电子邮件的所有群集。</span><span class="sxs-lookup"><span data-stu-id="34859-237">On the **Email** tab for an investigation, you can see all the clusters of email identified as part of the investigation.</span></span> 

<span data-ttu-id="34859-238">由于组织中的用户发送和接收的电子邮件数量巨大，因此</span><span class="sxs-lookup"><span data-stu-id="34859-238">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="34859-239">根据邮件头、正文、URL 和附件中的类似属性对电子邮件进行群集化;</span><span class="sxs-lookup"><span data-stu-id="34859-239">clustering email messages based on similar attributes from a message header, body, URL and attachments;</span></span> 
- <span data-ttu-id="34859-240">将恶意电子邮件与优质电子邮件分开;并</span><span class="sxs-lookup"><span data-stu-id="34859-240">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="34859-241">对恶意电子邮件采取操作</span><span class="sxs-lookup"><span data-stu-id="34859-241">taking action on malicious email messages</span></span> 

<span data-ttu-id="34859-242">可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="34859-242">can take many hours.</span></span> <span data-ttu-id="34859-243">现在，AIR 可以自动执行此过程，从而节省了贵组织的安全团队的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="34859-243">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="34859-244">电子邮件分析步骤中可能会标识两种不同类型的电子邮件群集：相似性群集和指示器群集。</span><span class="sxs-lookup"><span data-stu-id="34859-244">Two different types of email clusters may be identified during the email analysis step: similarity clusters and indicator clusters.</span></span> 
- <span data-ttu-id="34859-245">相似性群集是包含相似的发件人和内容属性的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34859-245">Similarity clusters are email messages that contain similar sender and content attributes.</span></span> <span data-ttu-id="34859-246">根据原始检测结果评估这些群集中的恶意内容。</span><span class="sxs-lookup"><span data-stu-id="34859-246">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="34859-247">包含足够恶意检测的电子邮件群集被认为是恶意的。</span><span class="sxs-lookup"><span data-stu-id="34859-247">Email clusters that contain enough malicious detections are considered malicious.</span></span>
- <span data-ttu-id="34859-248">指示器群集是包含来自原始电子邮件的指示器实体（文件哈希或 URL）的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34859-248">Indicator clusters are email messages that contain the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="34859-249">将原始文件/URL 实体标识为恶意时，AIR 会将指示器判定为包含该实体的电子邮件的整个群集。</span><span class="sxs-lookup"><span data-stu-id="34859-249">When the original file/URL entity is identified as malicious, AIR applies the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="34859-250">作为恶意软件识别的文件意味着包含该文件的电子邮件群集被视为恶意软件电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34859-250">As a file identified as malware means that the cluster of email messages containing that file are treated as malware email messages.</span></span>

<span data-ttu-id="34859-251">群集的目标是查找与攻击或市场活动的一部分由同一发件人发送的其他相关电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34859-251">The goal of clustering is to find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>

<span data-ttu-id="34859-252">"**电子邮件**" 选项卡还显示与调查相关的电子邮件项目，例如用户报告的电子邮件详细信息、报告的原始电子邮件、电子邮件 zapped （由于恶意软件/网络钓鱼诈骗等）。</span><span class="sxs-lookup"><span data-stu-id="34859-252">The **Email** tab also shows email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

<span data-ttu-id="34859-253">"电子邮件" 选项卡上标识的电子邮件计数当前代表 "**电子邮件**" 选项卡上显示的所有电子邮件的总数。由于电子邮件存在于多个群集中，因此标识的电子邮件的实际总数（并受修正操作影响）是所有群集和原始收件人的电子邮件中显示的唯一电子邮件的计数。</span><span class="sxs-lookup"><span data-stu-id="34859-253">The email count identified on the email tab currently represents the sum total of all email messages shown on the **Email** tab. Because email messages are present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) is the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span> 

<span data-ttu-id="34859-254">由于每个收件人的安全 verdicts、操作和传递位置各不相同，因此每个收件人的资源管理器和空中计数电子邮件都会有所不同。</span><span class="sxs-lookup"><span data-stu-id="34859-254">Both Explorer and AIR count email messages on a per recipient basis, since the security verdicts, actions, and delivery locations vary on a per recipient basis.</span></span> <span data-ttu-id="34859-255">因此，发送给三个用户的原始电子邮件总共计为三封电子邮件，而不是一封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34859-255">Thus an original email sent to three users count as a total of three email messages instead of one email.</span></span> <span data-ttu-id="34859-256">注释可能会出现两次或多次计数电子邮件的情况，因为电子邮件可能会对其进行多个操作，并且在发生所有操作后，可能会有多个电子邮件副本。</span><span class="sxs-lookup"><span data-stu-id="34859-256">Note there may be cases where an email gets counted two or more times, since the email may have multiple actions on it and there may be multiple copies of the email once all actions occur.</span></span> <span data-ttu-id="34859-257">例如，在传递时检测到的恶意软件电子邮件可能会导致阻止（隔离）的电子邮件和替换的电子邮件（受警告文件替换的威胁文件，然后传递到用户的邮箱）。</span><span class="sxs-lookup"><span data-stu-id="34859-257">For example a malware email that is detected at delivery may result in both a blocked (quarantined) email and a replaced email (threat file replaced with an warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="34859-258">由于在系统中有电子邮件的两个副本，因此这两个副本可能会在群集计数中进行计数。</span><span class="sxs-lookup"><span data-stu-id="34859-258">Since there are literally two copies of the email in the system - these may both be counted in cluster counts.</span></span> 

<span data-ttu-id="34859-259">电子邮件计数是在调查时计算的，当您打开调查 flyouts 时，会重新计算一些计数（基于基础查询）。</span><span class="sxs-lookup"><span data-stu-id="34859-259">Email counts are calculated at the time of the investigation and some counts are re-calculated when you open investigation flyouts (based on an underlying query).</span></span> <span data-ttu-id="34859-260">"电子邮件" 选项卡上显示的电子邮件群集的电子邮件计数以及在调查时将计算在 "群集浮出控件" 上显示的电子邮件数量值。</span><span class="sxs-lookup"><span data-stu-id="34859-260">The email counts shown for the email clusters on the email tab and the email quantity value shown on cluster flyout are calculated at the time of investigation.</span></span> <span data-ttu-id="34859-261">在 "群集" 浮出控件的 "电子邮件" 选项卡底部显示的电子邮件计数，资源管理器中显示的电子邮件计数反映在调查的初始分析之后收到的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34859-261">The email count shown at the bottom of the email tab of the cluster flyout, and the count of email messages shown in Explorer reflect email messages received after the investigation's initial analysis.</span></span> <span data-ttu-id="34859-262">因此，显示原始数量10封电子邮件的电子邮件群集会在调查分析阶段和管理员审查调查时，显示总的电子邮件列表15个电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34859-262">Thus an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when 5 more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span> <span data-ttu-id="34859-263">在不同的视图中显示这两个计数将完成，以指示调查时的电子邮件影响和当前的影响，直到运行补救时间为止。</span><span class="sxs-lookup"><span data-stu-id="34859-263">Showing both counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

<span data-ttu-id="34859-264">例如，请考虑以下方案。</span><span class="sxs-lookup"><span data-stu-id="34859-264">As an example, consider the following scenario.</span></span> <span data-ttu-id="34859-265">三封电子邮件的第一个群集被认为是网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="34859-265">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="34859-266">找到具有相同 IP 和主题的类似邮件的另一个群集，并被视为恶意邮件，因为在初始检测过程中将其部分标识为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="34859-266">Another cluster of similar messages with the same IP and subject was found and considered malicious, as some of them were identified as phish during initial detection.</span></span> 

![空中电子邮件调查页面](../media/air-investigationemailpage.png)

<span data-ttu-id="34859-268">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="34859-268">You can:</span></span>
- <span data-ttu-id="34859-269">获取当前群集结果和发现的威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="34859-269">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="34859-270">单击 "群集" 实体或威胁列表打开显示完整警报详细信息的弹出页面。</span><span class="sxs-lookup"><span data-stu-id="34859-270">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="34859-271">单击 "电子邮件群集详细信息" 选项卡顶部的 "在资源管理器中打开" 链接进一步调查电子邮件群集</span><span class="sxs-lookup"><span data-stu-id="34859-271">Further investigate the email cluster by clicking the 'Open in Explorer' link at the top of the 'Email cluster details' tab</span></span>

![使用浮出控件详细信息的航空调查电子邮件](../media/air-investigationemailpageflyoutdetails.png)

> [!NOTE]
> <span data-ttu-id="34859-273">在电子邮件上下文中，您可能会在调查过程中看到一个卷异常威胁曲面。</span><span class="sxs-lookup"><span data-stu-id="34859-273">In the context of email, you may see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="34859-274">卷异常表明调查事件时间与之前的时间框架相比，与调查事件的类似电子邮件中的峰值。</span><span class="sxs-lookup"><span data-stu-id="34859-274">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="34859-275">这种具有类似特征（例如，subject 和发件人域、正文相似性和发件人 IP）的电子邮件通信的峰值是电子邮件宣传活动或攻击的典型启动。</span><span class="sxs-lookup"><span data-stu-id="34859-275">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span> <span data-ttu-id="34859-276">但是，批量、垃圾邮件和合法电子邮件活动通常共享这些特征。</span><span class="sxs-lookup"><span data-stu-id="34859-276">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span> <span data-ttu-id="34859-277">由于使用反病毒引擎、沙箱或恶意信誉识别的恶意软件或网络钓鱼威胁相比，大量异常会带来潜在的威胁，因此可能会降低严重程度。</span><span class="sxs-lookup"><span data-stu-id="34859-277">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="34859-278">用户调查</span><span class="sxs-lookup"><span data-stu-id="34859-278">User investigation</span></span>

<span data-ttu-id="34859-279">在 "**用户**" 选项卡上，您可以看到标识为调查的一部分的所有用户。</span><span class="sxs-lookup"><span data-stu-id="34859-279">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="34859-280">当存在事件或指示这些用户帐户可能受到影响或受到威胁时，用户帐户将出现在调查中。</span><span class="sxs-lookup"><span data-stu-id="34859-280">User accounts appear in the investigation when there is an event or indication that those user accounts might be affected or compromised.</span></span>

<span data-ttu-id="34859-281">例如，在下图中，空气根据创建的新收件箱规则确定了安全指标和异常情况。</span><span class="sxs-lookup"><span data-stu-id="34859-281">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="34859-282">可通过此选项卡中的详细视图查看调查的其他详细信息（证据）。损坏的迹象和异常也可能包含来自[Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)的异常检测。</span><span class="sxs-lookup"><span data-stu-id="34859-282">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies may also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![空中调查用户页](../media/air-investigationuserspage.png)

<span data-ttu-id="34859-284">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="34859-284">You can:</span></span>
- <span data-ttu-id="34859-285">获取已确定的用户结果和发现的风险的直观概述。</span><span class="sxs-lookup"><span data-stu-id="34859-285">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="34859-286">选择用户以打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="34859-286">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="34859-287">机器调查</span><span class="sxs-lookup"><span data-stu-id="34859-287">Machine investigation</span></span>

<span data-ttu-id="34859-288">在 "**计算机**" 选项卡上，您可以看到标识为调查的一部分的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="34859-288">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![空中调查计算机页面](../media/air-investigationmachinepage.png)

<span data-ttu-id="34859-290">作为调查的一部分，空中将电子邮件威胁与设备相关联。</span><span class="sxs-lookup"><span data-stu-id="34859-290">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="34859-291">例如，调查会将恶意文件哈希传递到[Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
)以进行调查。</span><span class="sxs-lookup"><span data-stu-id="34859-291">For example, an investigation passes a malicious file hash across to [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="34859-292">这样，就可以为您的用户自动调查相关的计算机，以帮助确保在云中和终结点上解决威胁。</span><span class="sxs-lookup"><span data-stu-id="34859-292">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span> 

<span data-ttu-id="34859-293">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="34859-293">You can:</span></span>
- <span data-ttu-id="34859-294">获取发现的当前计算机和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="34859-294">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="34859-295">选择一台计算机以打开在 Microsoft Defender 安全中心的相关[Microsoft DEFENDER ATP 调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)中的视图。</span><span class="sxs-lookup"><span data-stu-id="34859-295">Select a machine to open a view that into the related [Microsoft Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="34859-296">实体调查</span><span class="sxs-lookup"><span data-stu-id="34859-296">Entity investigation</span></span>

<span data-ttu-id="34859-297">在 "**实体**" 选项卡上，您可以看到标识为调查的一部分的所有实体。</span><span class="sxs-lookup"><span data-stu-id="34859-297">On the **Entities** tab, you can see all the entities identified as part of the investigation.</span></span> 

<span data-ttu-id="34859-298">在这里，您可以查看调查的实体和实体类型的详细信息，例如电子邮件、群集、IP 地址、用户等。</span><span class="sxs-lookup"><span data-stu-id="34859-298">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="34859-299">您还可以查看已分析的实体数以及与每个实体相关联的威胁。</span><span class="sxs-lookup"><span data-stu-id="34859-299">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

!["航空调查实体" 页](../media/air-investigationentitiespage.png)

<span data-ttu-id="34859-301">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="34859-301">You can:</span></span>
- <span data-ttu-id="34859-302">获取发现的调查实体和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="34859-302">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="34859-303">选择一个实体以打开显示相关实体详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="34859-303">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![空中调查实体详细信息](../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="34859-305">行动手册日志</span><span class="sxs-lookup"><span data-stu-id="34859-305">Playbook log</span></span>

<span data-ttu-id="34859-306">在 "**日志**" 选项卡上，您可以查看调查过程中的所有操作手册步骤。</span><span class="sxs-lookup"><span data-stu-id="34859-306">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="34859-307">该日志将捕获由 Office 365 自动调查功能作为空气的一部分完成的所有操作的完整清单。</span><span class="sxs-lookup"><span data-stu-id="34859-307">The log captures a complete inventory of all actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="34859-308">它提供了所执行的所有步骤的清晰视图，包括操作本身、说明以及实际 "开始到完成" 的持续时间。</span><span class="sxs-lookup"><span data-stu-id="34859-308">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span> 

![航空调查日志页](../media/air-investigationlogpage.png)

<span data-ttu-id="34859-310">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="34859-310">You can:</span></span>
- <span data-ttu-id="34859-311">获取有关执行操作手册步骤的直观概述。</span><span class="sxs-lookup"><span data-stu-id="34859-311">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="34859-312">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="34859-312">Export the results to a CSV file.</span></span>
- <span data-ttu-id="34859-313">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="34859-313">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="34859-314">建议的操作</span><span class="sxs-lookup"><span data-stu-id="34859-314">Recommended actions</span></span>

<span data-ttu-id="34859-315">在 "**操作**" 选项卡上，您可以查看在调查完成后建议用于修正的所有操作手册操作。</span><span class="sxs-lookup"><span data-stu-id="34859-315">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="34859-316">操作会捕获 Microsoft 建议在调查结束时执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="34859-316">Actions capture the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="34859-317">您可以通过选择一个或多个操作来采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="34859-317">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="34859-318">单击 "**批准**" 可开始进行修正。</span><span class="sxs-lookup"><span data-stu-id="34859-318">Clicking **Approve** allows remediation to begin.</span></span> <span data-ttu-id="34859-319">（需要适当的权限-需要 "搜索和清除" 角色才能从资源管理器和 AIR 运行操作）。</span><span class="sxs-lookup"><span data-stu-id="34859-319">(Appropriate permissions are needed - the 'Search And Purge' role is required to run actions from Explorer and AIR).</span></span> <span data-ttu-id="34859-320">例如，安全读者可以查看操作但不能批准。</span><span class="sxs-lookup"><span data-stu-id="34859-320">For example, a Security Reader can view actions but not approve them.</span></span> <span data-ttu-id="34859-321">注意-您无需批准每个操作。</span><span class="sxs-lookup"><span data-stu-id="34859-321">Note - you do not have to approve every action.</span></span> <span data-ttu-id="34859-322">如果您不同意建议的操作，或者您的组织不选择特定类型的操作，则可以选择**拒绝**这些操作，也可以仅忽略它们，不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="34859-322">If you do not agree with the recommended action or your organization does not choose certain types of actions - then you can either choose to **Reject** the actions or simply ignore them and take no action.</span></span> <span data-ttu-id="34859-323">通过批准和/或拒绝所有操作，可以完全关闭调查，同时保留某些操作不完整将导致调查状态更改为 "部分修正" 状态。</span><span class="sxs-lookup"><span data-stu-id="34859-323">Approving and/or rejecting all actions let the investigation fully close, while leaving some actions incomplete results in the investigation status changing to a partially remediated state.</span></span>

![航空调查操作页](../media/air-investigationactionspage.png)

<span data-ttu-id="34859-325">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="34859-325">You can:</span></span>
- <span data-ttu-id="34859-326">获取对操作手册建议的操作的直观概述。</span><span class="sxs-lookup"><span data-stu-id="34859-326">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="34859-327">选择一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="34859-327">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="34859-328">使用注释批准或拒绝建议的操作。</span><span class="sxs-lookup"><span data-stu-id="34859-328">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="34859-329">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="34859-329">Export the results to a CSV file.</span></span>
- <span data-ttu-id="34859-330">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="34859-330">Filter the view.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="34859-331">示例：用户报告的网络钓鱼邮件启动调查行动手册</span><span class="sxs-lookup"><span data-stu-id="34859-331">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="34859-332">当组织中的用户提交电子邮件并使用[outlook 或 Outlook Web Access 的报告邮件加载项](enable-the-report-message-add-in.md)将其报告给 Microsoft 时，该报告也会发送到您的系统，并在用户报告的视图中显示在资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="34859-332">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md), the report is also sent to your system and is visible in Explorer in the User-reported view.</span></span> <span data-ttu-id="34859-333">此用户报告的消息现在会触发基于系统的信息警报，这将自动启动调查行动手册。</span><span class="sxs-lookup"><span data-stu-id="34859-333">This user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="34859-334">在根调查阶段，会评估电子邮件的各个方面。</span><span class="sxs-lookup"><span data-stu-id="34859-334">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="34859-335">具体包括：</span><span class="sxs-lookup"><span data-stu-id="34859-335">These include:</span></span>
- <span data-ttu-id="34859-336">确定它可能属于哪种类型的威胁;</span><span class="sxs-lookup"><span data-stu-id="34859-336">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="34859-337">发件人数;</span><span class="sxs-lookup"><span data-stu-id="34859-337">Who sent it;</span></span>
- <span data-ttu-id="34859-338">发送电子邮件的位置（发送基础结构）;</span><span class="sxs-lookup"><span data-stu-id="34859-338">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="34859-339">是否已传递或阻止电子邮件的其他实例;</span><span class="sxs-lookup"><span data-stu-id="34859-339">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="34859-340">我们分析家中的一种评估;</span><span class="sxs-lookup"><span data-stu-id="34859-340">An assessment from our analysts;</span></span>
- <span data-ttu-id="34859-341">电子邮件是否与任何已知的市场活动相关联;</span><span class="sxs-lookup"><span data-stu-id="34859-341">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="34859-342">等等。</span><span class="sxs-lookup"><span data-stu-id="34859-342">and more.</span></span>

<span data-ttu-id="34859-343">根调查完成后，行动手册提供了要对其关联的原始电子邮件和实体执行的建议操作的列表。</span><span class="sxs-lookup"><span data-stu-id="34859-343">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="34859-344">接下来，执行以下几个威胁调查和搜寻步骤：</span><span class="sxs-lookup"><span data-stu-id="34859-344">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="34859-345">搜索其他电子邮件群集中的类似电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34859-345">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="34859-346">该信号与其他平台（如[Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共享。</span><span class="sxs-lookup"><span data-stu-id="34859-346">The signal is shared with other platforms, such as [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="34859-347">确定是否有用户通过可疑电子邮件中的任何恶意链接单击过。</span><span class="sxs-lookup"><span data-stu-id="34859-347">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="34859-348">跨 Office 365 Exchange Online Protection （[EOP](exchange-online-protection-eop.md)）和 Office 365 高级威胁防护（[ATP](office-365-atp.md)）执行检查以查看用户是否报告了任何其他类似的消息。</span><span class="sxs-lookup"><span data-stu-id="34859-348">A check is done across Office 365 Exchange Online Protection ([EOP](exchange-online-protection-eop.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="34859-349">将执行检查以查看是否已泄露用户。</span><span class="sxs-lookup"><span data-stu-id="34859-349">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="34859-350">此检查在[Microsoft 云应用安全](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)中利用信号，关联任何相关的用户活动异常。</span><span class="sxs-lookup"><span data-stu-id="34859-350">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span> 

<span data-ttu-id="34859-351">在搜寻阶段，会为各种搜寻步骤分配风险和威胁。</span><span class="sxs-lookup"><span data-stu-id="34859-351">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="34859-352">修正是行动手册的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="34859-352">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="34859-353">在此阶段中，将根据调查和搜寻阶段采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="34859-353">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="34859-354">示例：安全管理员触发来自威胁资源管理器的调查</span><span class="sxs-lookup"><span data-stu-id="34859-354">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="34859-355">除了由警报触发的自动调查之外，组织的安全操作团队可以通过[威胁资源管理器](threat-explorer.md)中的视图触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="34859-355">In addition to automatic investigations that are triggered by an alert, your organization's security operations team can trigger an automatic investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>

<span data-ttu-id="34859-356">例如，假设您正在查看资源管理器中有关用户报告的消息的数据。</span><span class="sxs-lookup"><span data-stu-id="34859-356">For example, suppose that you are viewing data in Explorer about user-reported messages.</span></span> <span data-ttu-id="34859-357">您可以在结果列表中选择一个项目，然后单击 "**调查**"。</span><span class="sxs-lookup"><span data-stu-id="34859-357">You can select an item in the list of results, and then click **Investigate**.</span></span>

![使用调查按钮的资源管理器中的用户报告的消息](../media/Explorer-UserReported-Investigate.png)

<span data-ttu-id="34859-359">作为另一个示例，假设您要查看检测为包含恶意软件的电子邮件的数据，并且有几封电子邮件被检测为包含恶意软件。</span><span class="sxs-lookup"><span data-stu-id="34859-359">As another example, suppose you are viewing data about email messages detected as containing malware, and there are several email messages detected as containing malware.</span></span> <span data-ttu-id="34859-360">您可以选择 "**电子邮件**" 选项卡，选择一个或多个电子邮件，然后在 "**操作**" 菜单上选择 "**调查**"。</span><span class="sxs-lookup"><span data-stu-id="34859-360">You can select the **Email** tab, select one or more email messages, and then, on the **Actions** menu, select **Investigate**.</span></span> 

![在资源管理器中开始调查恶意软件](../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="34859-362">与由警报触发的行动手册类似，通过资源管理器中的视图触发的自动调查包括根调查、标识和关联威胁的步骤以及缓解这些威胁的建议操作。</span><span class="sxs-lookup"><span data-stu-id="34859-362">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="34859-363">如何获取空中</span><span class="sxs-lookup"><span data-stu-id="34859-363">How to get AIR</span></span>

<span data-ttu-id="34859-364">Office 365 AIR 包含在以下订阅中：</span><span class="sxs-lookup"><span data-stu-id="34859-364">Office 365 AIR is included in the following subscriptions:</span></span>

- <span data-ttu-id="34859-365">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="34859-365">Microsoft 365 E5</span></span>
- <span data-ttu-id="34859-366">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="34859-366">Office 365 E5</span></span>
- <span data-ttu-id="34859-367">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="34859-367">Microsoft Threat Protection</span></span>
- <span data-ttu-id="34859-368">Office 365 高级威胁防护（计划 2）</span><span class="sxs-lookup"><span data-stu-id="34859-368">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="34859-369">如果你没有这些订阅，请[启动免费试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US)。</span><span class="sxs-lookup"><span data-stu-id="34859-369">If you don't have any of these subscriptions, [start a free trial](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US).</span></span>

<span data-ttu-id="34859-370">若要了解有关功能可用性的详细信息，请访问[跨高级威胁防护（ATP）计划的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="34859-370">To learn more about feature availability, visit the [Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="next-steps"></a><span data-ttu-id="34859-371">后续步骤</span><span class="sxs-lookup"><span data-stu-id="34859-371">Next steps</span></span>

[<span data-ttu-id="34859-372">开始使用 Office 365 中的 AIR</span><span class="sxs-lookup"><span data-stu-id="34859-372">Get started using AIR in Office 365</span></span>](office-365-air.md)

[<span data-ttu-id="34859-373">了解 Microsoft Defender ATP 中的空气</span><span class="sxs-lookup"><span data-stu-id="34859-373">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 

[<span data-ttu-id="34859-374">访问 Microsoft 365 路线图以了解即将推出和推出的内容</span><span class="sxs-lookup"><span data-stu-id="34859-374">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

