---
title: 自动化调查和响应（空中）概述
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 概述 Office 365 高级威胁防护计划2中的自动化调查和响应功能。
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: d62d24a8f4cbd0541099ece91e46a23d3fbc786c
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208907"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-365"></a><span data-ttu-id="cd922-103">Microsoft 365 中的自动化调查和响应（空气）概述</span><span class="sxs-lookup"><span data-stu-id="cd922-103">An overview of Automated investigation and response (AIR) in Microsoft 365</span></span>

<span data-ttu-id="cd922-104">随着安全警报的触发，安全操作团队可查看这些警报并采取措施来保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="cd922-104">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="cd922-105">有时，安全操作团队可能会受到触发的警报量的感觉的不知所措。</span><span class="sxs-lookup"><span data-stu-id="cd922-105">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="cd922-106">自动化调查和响应（空中）功能可能有所帮助。</span><span class="sxs-lookup"><span data-stu-id="cd922-106">Automated investigation and response (AIR) capabilities can help.</span></span> <span data-ttu-id="cd922-107">通过 AIR，您的安全操作团队可以更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="cd922-107">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="cd922-108">空中功能包括自动调查过程，以响应目前存在的已知威胁。</span><span class="sxs-lookup"><span data-stu-id="cd922-108">AIR capabilities include automated investigation processes in response to well known threats that exist today.</span></span> <span data-ttu-id="cd922-109">适当的补救措施等待批准，使安全操作团队能够响应检测到的威胁。</span><span class="sxs-lookup"><span data-stu-id="cd922-109">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span> 

<span data-ttu-id="cd922-110">本文提供了空中的概述。</span><span class="sxs-lookup"><span data-stu-id="cd922-110">This article provides an overview of AIR.</span></span> <span data-ttu-id="cd922-111">当您准备好开始使用 AIR 时，请参阅[自动调查和响应威胁](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="cd922-111">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

## <a name="at-a-high-level"></a><span data-ttu-id="cd922-112">高级别</span><span class="sxs-lookup"><span data-stu-id="cd922-112">At a high level</span></span>

<span data-ttu-id="cd922-113">随着警报的触发，安全行动手册将生效。</span><span class="sxs-lookup"><span data-stu-id="cd922-113">As alerts are triggered, security playbooks go into effect.</span></span> <span data-ttu-id="cd922-114">根据具体情况，可以开始执行[自动调查过程](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。</span><span class="sxs-lookup"><span data-stu-id="cd922-114">Depending on the situation, an [automated investigation process](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) can begin.</span></span> <span data-ttu-id="cd922-115">在进行自动调查的过程中和之后，建议采取[补救措施](air-remediation-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="cd922-115">During and after an automated investigation, [remediation actions](air-remediation-actions.md) are recommended.</span></span> <span data-ttu-id="cd922-116">在 Office 365 高级威胁防护中不会自动执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="cd922-116">No actions are taken automatically in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="cd922-117">您的安全操作团队将进行审核，然后[批准或拒绝每个更正操作](air-review-approve-pending-completed-actions.md)，完成后，每个调查完成。</span><span class="sxs-lookup"><span data-stu-id="cd922-117">Your security operations team reviews, and then [approves or rejects each remediation action](air-review-approve-pending-completed-actions.md), and when this is done, each investigation completes.</span></span> <span data-ttu-id="cd922-118">所有这些活动都会在安全 & 合规性中心中进行跟踪和查看（请参阅[查看调查的详细信息](air-view-investigation-results.md#view-details-of-an-investigation)）。</span><span class="sxs-lookup"><span data-stu-id="cd922-118">All of these activities are tracked and viewable in the Security & Compliance Center (see [View details of an investigation](air-view-investigation-results.md#view-details-of-an-investigation)).</span></span>

<span data-ttu-id="cd922-119">以下各节提供了有关警报、安全行动手册和操作中的示例的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="cd922-119">The following sections provide more details about alerts, security playbooks, and examples of AIR in action.</span></span>

## <a name="alerts"></a><span data-ttu-id="cd922-120">警报</span><span class="sxs-lookup"><span data-stu-id="cd922-120">Alerts</span></span>

<span data-ttu-id="cd922-121">[警报](../../compliance/alert-policies.md#viewing-alerts)表示用于事件响应的安全操作团队工作流的触发器。</span><span class="sxs-lookup"><span data-stu-id="cd922-121">[Alerts](../../compliance/alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="cd922-122">确定要调查的正确通知集的优先级，同时确保没有威胁是 unaddressed 的挑战。</span><span class="sxs-lookup"><span data-stu-id="cd922-122">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="cd922-123">在手动对通知进行调查时，安全操作团队必须在威胁的风险下对实体（如内容、设备和用户）进行寻找和关联。</span><span class="sxs-lookup"><span data-stu-id="cd922-123">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (such as content, devices and users) at risk from threats.</span></span> <span data-ttu-id="cd922-124">此类任务和工作流可能非常耗时，并涉及多个工具和系统。</span><span class="sxs-lookup"><span data-stu-id="cd922-124">Such tasks and workflows can be very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="cd922-125">通过让关键安全和威胁管理警报自动触发安全响应行动手册，可以通过空气、调查和响应安全事件进行自动化。</span><span class="sxs-lookup"><span data-stu-id="cd922-125">With AIR, investigation and response for security events are automated by having key security and threat management alerts trigger security response playbooks automatically.</span></span> 

<span data-ttu-id="cd922-126">目前，对于气流，从下列类型的警报策略生成的警报将自动调查：</span><span class="sxs-lookup"><span data-stu-id="cd922-126">Currently for AIR, alerts generated from the following kinds of alert policies are auto-investigated:</span></span>  

- <span data-ttu-id="cd922-127">检测到潜在的恶意 URL 单击</span><span class="sxs-lookup"><span data-stu-id="cd922-127">A potentially malicious URL click was detected</span></span>
- <span data-ttu-id="cd922-128">用户报告为网络钓鱼的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="cd922-128">Email reported by user as phish\*</span></span>
- <span data-ttu-id="cd922-129">包含在传递后删除的恶意软件的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="cd922-129">Email messages containing malware removed after delivery\*</span></span>
- <span data-ttu-id="cd922-130">包含在传递后删除的网络钓鱼 Url 的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="cd922-130">Email messages containing phish URLs removed after delivery\*</span></span>
- <span data-ttu-id="cd922-131">检测到可疑的电子邮件发送模式#</span><span class="sxs-lookup"><span data-stu-id="cd922-131">Suspicious email sending patterns detected#</span></span>
- <span data-ttu-id="cd922-132">限制用户发送电子邮件#</span><span class="sxs-lookup"><span data-stu-id="cd922-132">User restricted from sending email#</span></span>

> [!NOTE]
> <span data-ttu-id="cd922-133">以星号（*）标记的警报在安全 & 合规性中心（电子邮件通知已关闭）的相应警报策略中被分配了一个*信息性\*严重性。</span><span class="sxs-lookup"><span data-stu-id="cd922-133">The alerts marked with an asterisk (\*) are assigned an *Informational* severity in the respective alert policies within the Security & Compliance Center, with email notifications turned off.</span></span> <span data-ttu-id="cd922-134">可以通过[报警策略配置](../../compliance/alert-policies.md#alert-policy-settings)启用电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="cd922-134">Email notifications can be turned on through [Alert policy configuration](../../compliance/alert-policies.md#alert-policy-settings).</span></span> <span data-ttu-id="cd922-135">使用哈希（#）标记的警报通常是与公共预览版行动手册相关联的警报。</span><span class="sxs-lookup"><span data-stu-id="cd922-135">Alerts marked with a hash (#) are generally available alerts associated with public preview playbooks.</span></span>

<span data-ttu-id="cd922-136">若要查看警报，请在安全 & 合规性中心中，选择 "**通知**" "  >  **查看警报**"。</span><span class="sxs-lookup"><span data-stu-id="cd922-136">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="cd922-137">选择一个警报以查看其详细信息，然后在那里使用 "**查看调查**" 链接转到相应的[调查](air-view-investigation-results.md#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="cd922-137">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](air-view-investigation-results.md#investigation-graph).</span></span>  

> [!NOTE]
> <span data-ttu-id="cd922-138">默认情况下，通知视图中隐藏信息警报。</span><span class="sxs-lookup"><span data-stu-id="cd922-138">Informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="cd922-139">若要查看它们，请更改警报筛选以包含信息警报。</span><span class="sxs-lookup"><span data-stu-id="cd922-139">To see them, change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="cd922-140">如果您的组织通过警报管理系统、服务管理系统或安全信息和事件管理（SIEM）系统管理安全警报，则可以通过电子邮件通知或通过[Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)向该系统发送通知。</span><span class="sxs-lookup"><span data-stu-id="cd922-140">If your organization manages your security alerts through an alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="cd922-141">通过电子邮件或 API 的调查通知通知包括访问安全 & 合规性中心中的警报的链接，使分配的安全管理员能够快速导航到调查。</span><span class="sxs-lookup"><span data-stu-id="cd922-141">The investigation alert notifications via email or API include links to access the alerts in the Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![链接到调查的警报](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a><span data-ttu-id="cd922-143">安全行动手册</span><span class="sxs-lookup"><span data-stu-id="cd922-143">Security playbooks</span></span>

<span data-ttu-id="cd922-144">安全行动手册是在 Office 高级威胁防护和 Microsoft 威胁防护中实现自动化的后端策略。</span><span class="sxs-lookup"><span data-stu-id="cd922-144">Security playbooks are back-end policies that are at the heart of automation in Office Advanced Threat Protection and Microsoft Threat Protection.</span></span> <span data-ttu-id="cd922-145">空中提供的安全行动手册基于常见的实际安全方案，并根据安全操作团队的反馈进行开发。</span><span class="sxs-lookup"><span data-stu-id="cd922-145">The security playbooks provided in AIR are based on common real-world security scenarios and developed based on feedback from Security Operations teams.</span></span> <span data-ttu-id="cd922-146">当您的组织中触发特定警报时，将自动启动安全行动手册。</span><span class="sxs-lookup"><span data-stu-id="cd922-146">A security playbook is launched automatically when specific alerts are triggered within your organization.</span></span> <span data-ttu-id="cd922-147">通知触发后，相关的行动手册将由自动调查和响应（航空）系统运行。</span><span class="sxs-lookup"><span data-stu-id="cd922-147">Once the alert triggers, the associated playbook is run by the Automated Investigation and Response (AIR) system.</span></span> <span data-ttu-id="cd922-148">调查根据特定警报的操作手册分析预警的步骤，查看所有关联的元数据（包括电子邮件、用户、主题、发件人等）。</span><span class="sxs-lookup"><span data-stu-id="cd922-148">The investigation steps through analysis of the alert based on that particular alert's playbook, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="cd922-149">根据调查行动手册的发现，AIR 推荐了组织的安全团队可采取的一组操作来控制和缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="cd922-149">Based on the investigation playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="cd922-150">你将使用空中获取的安全行动手册旨在解决组织在当今的电子邮件中遇到的最常见威胁。</span><span class="sxs-lookup"><span data-stu-id="cd922-150">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations encounter today with email.</span></span> <span data-ttu-id="cd922-151">它们基于安全操作和事件响应团队的输入，包括帮助保护 Microsoft 和客户资产的人员。</span><span class="sxs-lookup"><span data-stu-id="cd922-151">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers' assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="cd922-152">安全行动手册在几个阶段推出</span><span class="sxs-lookup"><span data-stu-id="cd922-152">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="cd922-153">作为空气的一部分，安全行动手册将分阶段推出。</span><span class="sxs-lookup"><span data-stu-id="cd922-153">As part of AIR, security playbooks are rolling out in phases.</span></span> <span data-ttu-id="cd922-154">第1阶段现已推出，其中包含多个行动手册，这些操作提供了安全管理员可以查看和批准的操作建议：</span><span class="sxs-lookup"><span data-stu-id="cd922-154">Phase 1 is now generally available and includes several playbooks that provide recommendations for actions that security administrators can review and approve:</span></span>

- <span data-ttu-id="cd922-155">用户报告的网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="cd922-155">User-reported phish message</span></span>
- <span data-ttu-id="cd922-156">URL 单击 "判定更改"</span><span class="sxs-lookup"><span data-stu-id="cd922-156">URL click verdict change</span></span>
- <span data-ttu-id="cd922-157">恶意软件检测到送达后（恶意软件 ZAP）</span><span class="sxs-lookup"><span data-stu-id="cd922-157">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="cd922-158">网络钓鱼检测到传递后的 ZAP （网络钓鱼 ZAP）</span><span class="sxs-lookup"><span data-stu-id="cd922-158">Phish detected post-delivery ZAP (Phish ZAP)</span></span>

<span data-ttu-id="cd922-159">第1阶段还包括对管理员触发的电子邮件调查（使用[威胁资源管理器](threat-explorer.md)）的支持。</span><span class="sxs-lookup"><span data-stu-id="cd922-159">Phase 1 also includes support for administrator triggered e-mail investigations (using [Threat Explorer](threat-explorer.md)).</span></span>

<span data-ttu-id="cd922-160">第2阶段现在与**公共预览版**中的以下行动手册结合在一起，为操作和 aiding 安全管理员提供调查问题的建议：</span><span class="sxs-lookup"><span data-stu-id="cd922-160">Phase 2 is now progress with the following playbooks in **public preview**, providing recommendations for actions and aiding security administrators in investigating issues:</span></span>

- <span data-ttu-id="cd922-161">用户报告为 "已损坏" （公用预览）</span><span class="sxs-lookup"><span data-stu-id="cd922-161">User reported as compromised (public preview)</span></span>

<span data-ttu-id="cd922-162">在完成后，将立即发布后续行动手册。</span><span class="sxs-lookup"><span data-stu-id="cd922-162">Further playbooks will be released as they are completed.</span></span> <span data-ttu-id="cd922-163">访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)以查看计划和即将推出的其他内容。</span><span class="sxs-lookup"><span data-stu-id="cd922-163">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what else is planned and coming soon.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="cd922-164">行动手册包括调查和建议</span><span class="sxs-lookup"><span data-stu-id="cd922-164">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="cd922-165">在空中，每个安全行动手册包括：</span><span class="sxs-lookup"><span data-stu-id="cd922-165">In AIR, each security playbook includes:</span></span> 

- <span data-ttu-id="cd922-166">对电子邮件实体（文件、Url、收件人、IP 地址等）的根调查</span><span class="sxs-lookup"><span data-stu-id="cd922-166">a root investigation of an email's entities (files, URLs, recipients, IP addresses, etc.),</span></span>
- <span data-ttu-id="cd922-167">对组织收到的类似电子邮件的进一步搜寻</span><span class="sxs-lookup"><span data-stu-id="cd922-167">further hunting for similar emails received by the organization</span></span> 
- <span data-ttu-id="cd922-168">确定并关联其他潜在威胁所需的步骤，以及</span><span class="sxs-lookup"><span data-stu-id="cd922-168">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="cd922-169">建议的威胁补救措施。</span><span class="sxs-lookup"><span data-stu-id="cd922-169">recommended threat remediation actions.</span></span>

<span data-ttu-id="cd922-170">每个高级步骤都包含多个执行的子步骤，以提供对威胁的深入、详细和详尽的响应。</span><span class="sxs-lookup"><span data-stu-id="cd922-170">Each high-level step includes a number of substeps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="cd922-171">示例：用户报告的网络钓鱼邮件启动调查行动手册</span><span class="sxs-lookup"><span data-stu-id="cd922-171">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="cd922-172">假定组织中的某个用户收到电子邮件，而他们认为是网络钓鱼尝试。</span><span class="sxs-lookup"><span data-stu-id="cd922-172">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="cd922-173">经过培训的用户报告此类邮件，使用[报告邮件加载项](enable-the-report-message-add-in.md)将其发送到 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="cd922-173">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="cd922-174">提交也会发送到您的系统，并在 "**提交**" 视图中显示在资源管理器中（以前称为**用户报告**的视图）。</span><span class="sxs-lookup"><span data-stu-id="cd922-174">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="cd922-175">此外，用户报告的消息现在会触发基于系统的信息警报，这将自动启动调查行动手册。</span><span class="sxs-lookup"><span data-stu-id="cd922-175">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="cd922-176">在根调查阶段，会评估电子邮件的各个方面。</span><span class="sxs-lookup"><span data-stu-id="cd922-176">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="cd922-177">具体包括：</span><span class="sxs-lookup"><span data-stu-id="cd922-177">These include:</span></span>

- <span data-ttu-id="cd922-178">确定它可能属于哪种类型的威胁;</span><span class="sxs-lookup"><span data-stu-id="cd922-178">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="cd922-179">发件人数;</span><span class="sxs-lookup"><span data-stu-id="cd922-179">Who sent it;</span></span>
- <span data-ttu-id="cd922-180">发送电子邮件的位置（发送基础结构）;</span><span class="sxs-lookup"><span data-stu-id="cd922-180">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="cd922-181">是否已传递或阻止电子邮件的其他实例;</span><span class="sxs-lookup"><span data-stu-id="cd922-181">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="cd922-182">我们分析家中的一种评估;</span><span class="sxs-lookup"><span data-stu-id="cd922-182">An assessment from our analysts;</span></span>
- <span data-ttu-id="cd922-183">电子邮件是否与任何已知的市场活动相关联;</span><span class="sxs-lookup"><span data-stu-id="cd922-183">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="cd922-184">等等。</span><span class="sxs-lookup"><span data-stu-id="cd922-184">and more.</span></span>

<span data-ttu-id="cd922-185">根调查完成后，行动手册提供了要对其关联的原始电子邮件和实体执行的建议操作的列表。</span><span class="sxs-lookup"><span data-stu-id="cd922-185">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="cd922-186">接下来，执行以下几个威胁调查和搜寻步骤：</span><span class="sxs-lookup"><span data-stu-id="cd922-186">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="cd922-187">类似的电子邮件通过电子邮件群集搜索进行标识。</span><span class="sxs-lookup"><span data-stu-id="cd922-187">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="cd922-188">该信号与其他平台（如[Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共享。</span><span class="sxs-lookup"><span data-stu-id="cd922-188">The signal is shared with other platforms, such as [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="cd922-189">确定是否有用户通过可疑电子邮件中的任何恶意链接单击过。</span><span class="sxs-lookup"><span data-stu-id="cd922-189">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="cd922-190">通过 Exchange Online Protection （[EOP](exchange-online-protection-overview.md)）和 Office 365 高级威胁防护（[ATP](office-365-atp.md)）进行检查，以查看用户是否报告了任何其他类似的消息。</span><span class="sxs-lookup"><span data-stu-id="cd922-190">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="cd922-191">将执行检查以查看是否已泄露用户。</span><span class="sxs-lookup"><span data-stu-id="cd922-191">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="cd922-192">此检查跨 Office 365、 [Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)之间的信号，关联任何相关的用户活动异常。</span><span class="sxs-lookup"><span data-stu-id="cd922-192">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="cd922-193">在搜寻阶段，会为各种搜寻步骤分配风险和威胁。</span><span class="sxs-lookup"><span data-stu-id="cd922-193">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="cd922-194">修正是行动手册的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="cd922-194">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="cd922-195">在此阶段中，将根据调查和搜寻阶段采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="cd922-195">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="cd922-196">示例：安全管理员触发来自威胁资源管理器的调查</span><span class="sxs-lookup"><span data-stu-id="cd922-196">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="cd922-197">除了由警报触发的自动调查之外，组织的安全操作团队可以通过[威胁资源管理器](threat-explorer.md)中的视图触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="cd922-197">In addition to automatic investigations that are triggered by an alert, your organization's security operations team can trigger an automatic investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>

<span data-ttu-id="cd922-198">例如，假设您使用威胁资源管理器中的**恶意软件**视图。</span><span class="sxs-lookup"><span data-stu-id="cd922-198">For example, suppose that you are using the **Malware** view in Threat Explorer.</span></span> <span data-ttu-id="cd922-199">使用图表下方的选项卡，选择 "**电子邮件**" 选项卡。如果选择列表中的一个或多个项目，则 " **+ 动作**" 按钮将激活。</span><span class="sxs-lookup"><span data-stu-id="cd922-199">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span> 

:::image type="content" source="../../media/Explorer-Malware-Email-ActionsInvestigate.png" alt-text="包含所选邮件的资源管理器":::

<span data-ttu-id="cd922-201">使用 "**操作**" 菜单，可以选择**触发调查**。</span><span class="sxs-lookup"><span data-stu-id="cd922-201">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

:::image type="content" source="../../media/explorer-malwareview-selectedemails-actions.jpg" alt-text="选定邮件的 "操作" 菜单":::

<span data-ttu-id="cd922-203">与由警报触发的行动手册类似，通过资源管理器中的视图触发的自动调查包括根调查、标识和关联威胁的步骤以及缓解这些威胁的建议操作。</span><span class="sxs-lookup"><span data-stu-id="cd922-203">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cd922-204">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd922-204">Next steps</span></span>

- [<span data-ttu-id="cd922-205">开始使用空中</span><span class="sxs-lookup"><span data-stu-id="cd922-205">Get started using AIR</span></span>](office-365-air.md)

- [<span data-ttu-id="cd922-206">访问 Microsoft 365 路线图以了解即将推出和推出的内容</span><span class="sxs-lookup"><span data-stu-id="cd922-206">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)
