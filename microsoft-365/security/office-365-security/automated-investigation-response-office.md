---
title: Office 365 中的自动化调查和响应（空气）
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
ms.openlocfilehash: 436d70934e32f8609d35532188ac71cbd590c345
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228578"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a><span data-ttu-id="81558-103">Office 365 中的自动化调查和响应（空气）</span><span class="sxs-lookup"><span data-stu-id="81558-103">Automated investigation and response (AIR) in Office 365</span></span>

<span data-ttu-id="81558-104">随着安全警报的触发，安全操作团队可查看这些警报并采取措施来保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="81558-104">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="81558-105">有时，安全操作团队可能会受到触发的警报量的感觉的不知所措。</span><span class="sxs-lookup"><span data-stu-id="81558-105">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="81558-106">Office 365 中的自动化调查和响应（空中）功能可以帮助。</span><span class="sxs-lookup"><span data-stu-id="81558-106">Automated investigation and response (AIR) capabilities in Office 365 can help.</span></span> <span data-ttu-id="81558-107">通过 AIR，您的安全操作团队可以更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="81558-107">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="81558-108">空中功能包括自动调查过程，以响应目前存在的已知威胁。</span><span class="sxs-lookup"><span data-stu-id="81558-108">AIR capabilities include automated investigation processes in response to well known threats that exist today.</span></span> <span data-ttu-id="81558-109">适当的补救措施等待批准，使安全操作团队能够响应检测到的威胁。</span><span class="sxs-lookup"><span data-stu-id="81558-109">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span> 

<span data-ttu-id="81558-110">本文提供了空气及其组件的概述。</span><span class="sxs-lookup"><span data-stu-id="81558-110">This article provides an overview of AIR and its components.</span></span> <span data-ttu-id="81558-111">当您准备好开始使用 AIR 时，请参阅在[Office 365 中自动调查和响应威胁](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="81558-111">When you're ready to get started using AIR, see [Automatically investigate and respond to threats in Office 365](office-365-air.md).</span></span>

> [!TIP]
> <span data-ttu-id="81558-112">你的 Microsoft 365 E5 或 Microsoft 365 E3 是否具有身份和威胁防护？</span><span class="sxs-lookup"><span data-stu-id="81558-112">Do you have Microsoft 365 E5 or Microsoft 365 E3 together with Identity & Threat Protection?</span></span> <span data-ttu-id="81558-113">考虑尝试使用 [Microsoft 威胁防护](../mtp/microsoft-threat-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="81558-113">Consider trying [Microsoft Threat Protection](../mtp/microsoft-threat-protection.md).</span></span>

## <a name="at-a-high-level"></a><span data-ttu-id="81558-114">高级别</span><span class="sxs-lookup"><span data-stu-id="81558-114">At a high level</span></span>

<span data-ttu-id="81558-115">随着警报的触发，安全行动手册将生效。</span><span class="sxs-lookup"><span data-stu-id="81558-115">As alerts are triggered, security playbooks go into effect.</span></span> <span data-ttu-id="81558-116">根据具体情况，可以开始执行[自动调查过程](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。</span><span class="sxs-lookup"><span data-stu-id="81558-116">Depending on the situation, an [automated investigation process](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) can begin.</span></span> <span data-ttu-id="81558-117">在进行自动调查的过程中和之后，建议采取[补救措施](air-remediation-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="81558-117">During and after an automated investigation, [remediation actions](air-remediation-actions.md) are recommended.</span></span> <span data-ttu-id="81558-118">在 Office 365 高级威胁防护中不会自动执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="81558-118">No actions are taken automatically in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="81558-119">您的安全操作团队将进行审核，然后[批准或拒绝每个更正操作](air-remediation-actions.md#approve-or-reject-pending-actions)，完成后，每个调查完成。</span><span class="sxs-lookup"><span data-stu-id="81558-119">Your security operations team reviews, and then [approves or rejects each remediation action](air-remediation-actions.md#approve-or-reject-pending-actions), and when this is done, each investigation completes.</span></span> <span data-ttu-id="81558-120">所有这些活动都会在 Office 365 安全 & 合规性中心中进行跟踪和查看（请参阅[查看调查的详细信息](air-view-investigation-results.md#view-details-of-an-investigation)）。</span><span class="sxs-lookup"><span data-stu-id="81558-120">All of these activities are tracked and viewable in the Office 365 Security & Compliance Center (see [View details of an investigation](air-view-investigation-results.md#view-details-of-an-investigation)).</span></span>

<span data-ttu-id="81558-121">以下各节提供了有关警报、安全行动手册和操作中的示例的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="81558-121">The following sections provide more details about alerts, security playbooks, and examples of AIR in action.</span></span>

## <a name="alerts"></a><span data-ttu-id="81558-122">警报</span><span class="sxs-lookup"><span data-stu-id="81558-122">Alerts</span></span>

<span data-ttu-id="81558-123">[警报](../../compliance/alert-policies.md#viewing-alerts)表示用于事件响应的安全操作团队工作流的触发器。</span><span class="sxs-lookup"><span data-stu-id="81558-123">[Alerts](../../compliance/alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="81558-124">确定要调查的正确通知集的优先级，同时确保没有威胁是 unaddressed 的挑战。</span><span class="sxs-lookup"><span data-stu-id="81558-124">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="81558-125">在手动对通知进行调查时，安全操作团队必须在威胁的风险下对实体（如内容、设备和用户）进行寻找和关联。</span><span class="sxs-lookup"><span data-stu-id="81558-125">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (such as content, devices and users) at risk from threats.</span></span> <span data-ttu-id="81558-126">此类任务和工作流可能非常耗时，并涉及多个工具和系统。</span><span class="sxs-lookup"><span data-stu-id="81558-126">Such tasks and workflows can be very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="81558-127">通过让关键安全和威胁管理警报自动触发安全响应行动手册，Office 365 安全事件的空中、调查和响应是自动化的。</span><span class="sxs-lookup"><span data-stu-id="81558-127">With AIR, investigation and response for Office 365 security events are automated by having key security and threat management alerts trigger security response playbooks automatically.</span></span> 

<span data-ttu-id="81558-128">目前，对于气流，从下列类型的警报策略生成的警报将自动调查：</span><span class="sxs-lookup"><span data-stu-id="81558-128">Currently for AIR, alerts generated from the following kinds of alert policies are auto-investigated:</span></span>  

- <span data-ttu-id="81558-129">检测到潜在的恶意 URL 单击</span><span class="sxs-lookup"><span data-stu-id="81558-129">A potentially malicious URL click was detected</span></span>
- <span data-ttu-id="81558-130">用户报告为网络钓鱼的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="81558-130">Email reported by user as phish\*</span></span>
- <span data-ttu-id="81558-131">包含在传递后删除的恶意软件的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="81558-131">Email messages containing malware removed after delivery\*</span></span>
- <span data-ttu-id="81558-132">包含在传递后删除的网络钓鱼 Url 的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="81558-132">Email messages containing phish URLs removed after delivery\*</span></span>
- <span data-ttu-id="81558-133">检测到可疑的电子邮件发送模式#</span><span class="sxs-lookup"><span data-stu-id="81558-133">Suspicious email sending patterns detected#</span></span>
- <span data-ttu-id="81558-134">限制用户发送电子邮件#</span><span class="sxs-lookup"><span data-stu-id="81558-134">User restricted from sending email#</span></span>

> [!NOTE]
> <span data-ttu-id="81558-135">以星号（*）标记的警报在安全 & 合规性中心（电子邮件通知已关闭）的相应警报策略中被分配了一个*信息性\*严重性。</span><span class="sxs-lookup"><span data-stu-id="81558-135">The alerts marked with an asterisk (\*) are assigned an *Informational* severity in the respective alert policies within the Security & Compliance Center, with email notifications turned off.</span></span> <span data-ttu-id="81558-136">可以通过[报警策略配置](../../compliance/alert-policies.md#alert-policy-settings)启用电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="81558-136">Email notifications can be turned on through [Alert policy configuration](../../compliance/alert-policies.md#alert-policy-settings).</span></span> <span data-ttu-id="81558-137">使用哈希（#）标记的警报通常是与公共预览版行动手册相关联的警报。</span><span class="sxs-lookup"><span data-stu-id="81558-137">Alerts marked with a hash (#) are generally available alerts associated with public preview playbooks.</span></span>

<span data-ttu-id="81558-138">若要查看警报，请在安全 & 合规性中心中，选择 "**通知** > " "**查看警报**"。</span><span class="sxs-lookup"><span data-stu-id="81558-138">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="81558-139">选择一个警报以查看其详细信息，然后在那里使用 "**查看调查**" 链接转到相应的[调查](air-view-investigation-results.md#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="81558-139">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](air-view-investigation-results.md#investigation-graph).</span></span>  

> [!NOTE]
> <span data-ttu-id="81558-140">默认情况下，通知视图中隐藏信息警报。</span><span class="sxs-lookup"><span data-stu-id="81558-140">Informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="81558-141">若要查看它们，请更改警报筛选以包含信息警报。</span><span class="sxs-lookup"><span data-stu-id="81558-141">To see them, change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="81558-142">如果您的组织通过警报管理系统、服务管理系统或安全信息和事件管理（SIEM）系统管理安全警报，则可以通过电子邮件通知或通过[Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)将 Office 365 警报发送到该系统。</span><span class="sxs-lookup"><span data-stu-id="81558-142">If your organization manages your security alerts through an alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send Office 365 alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="81558-143">通过电子邮件或 API 的调查通知通知包括访问安全 & 合规性中心中的警报的链接，使分配的安全管理员能够快速导航到调查。</span><span class="sxs-lookup"><span data-stu-id="81558-143">The investigation alert notifications via email or API include links to access the alerts in the Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![链接到调查的警报](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a><span data-ttu-id="81558-145">安全行动手册</span><span class="sxs-lookup"><span data-stu-id="81558-145">Security playbooks</span></span>

<span data-ttu-id="81558-146">安全行动手册是在 Office 高级威胁防护和 Microsoft 威胁防护中实现自动化的后端策略。</span><span class="sxs-lookup"><span data-stu-id="81558-146">Security playbooks are back-end policies that are at the heart of automation in Office Advanced Threat Protection and Microsoft Threat Protection.</span></span> <span data-ttu-id="81558-147">空中提供的安全行动手册基于常见的实际安全方案，并根据安全操作团队的反馈进行开发。</span><span class="sxs-lookup"><span data-stu-id="81558-147">The security playbooks provided in AIR are based on common real-world security scenarios and developed based on feedback from Security Operations teams.</span></span> <span data-ttu-id="81558-148">当您的组织中触发特定警报时，将自动启动安全行动手册。</span><span class="sxs-lookup"><span data-stu-id="81558-148">A security playbook is launched automatically when specific alerts are triggered within your organization.</span></span> <span data-ttu-id="81558-149">通知触发后，相关的行动手册将由自动调查和响应（航空）系统运行。</span><span class="sxs-lookup"><span data-stu-id="81558-149">Once the alert triggers, the associated playbook is run by the Automated Investigation and Response (AIR) system.</span></span> <span data-ttu-id="81558-150">调查根据特定警报的操作手册分析预警的步骤，查看所有关联的元数据（包括电子邮件、用户、主题、发件人等）。</span><span class="sxs-lookup"><span data-stu-id="81558-150">The investigation steps through analysis of the alert based on that particular alert's playbook, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="81558-151">根据调查行动手册的发现，AIR 推荐了组织的安全团队可采取的一组操作来控制和缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="81558-151">Based on the investigation playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="81558-152">你将使用空中获取的安全行动手册旨在解决组织在当今的电子邮件中遇到的最常见威胁。</span><span class="sxs-lookup"><span data-stu-id="81558-152">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations encounter today with email.</span></span> <span data-ttu-id="81558-153">它们基于安全操作和事件响应团队的输入，包括帮助保护 Microsoft 和客户资产的人员。</span><span class="sxs-lookup"><span data-stu-id="81558-153">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers' assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="81558-154">安全行动手册在几个阶段推出</span><span class="sxs-lookup"><span data-stu-id="81558-154">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="81558-155">作为空气的一部分，安全行动手册将分阶段推出。</span><span class="sxs-lookup"><span data-stu-id="81558-155">As part of AIR, security playbooks are rolling out in phases.</span></span> <span data-ttu-id="81558-156">第1阶段现已推出，其中包含多个行动手册，这些操作提供了安全管理员可以查看和批准的操作建议：</span><span class="sxs-lookup"><span data-stu-id="81558-156">Phase 1 is now generally available and includes several playbooks that provide recommendations for actions that security administrators can review and approve:</span></span>
- <span data-ttu-id="81558-157">用户报告的网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="81558-157">User-reported phish message</span></span>
- <span data-ttu-id="81558-158">URL 单击 "判定更改"</span><span class="sxs-lookup"><span data-stu-id="81558-158">URL click verdict change</span></span>
- <span data-ttu-id="81558-159">恶意软件检测到送达后（恶意软件 ZAP）</span><span class="sxs-lookup"><span data-stu-id="81558-159">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="81558-160">网络钓鱼检测到传递后的 ZAP （网络钓鱼 ZAP）</span><span class="sxs-lookup"><span data-stu-id="81558-160">Phish detected post-delivery ZAP (Phish ZAP)</span></span>

<span data-ttu-id="81558-161">第1阶段还包括对管理员触发的电子邮件调查（使用[威胁资源管理器](threat-explorer.md)）的支持。</span><span class="sxs-lookup"><span data-stu-id="81558-161">Phase 1 also includes support for administrator triggered e-mail investigations (using [Threat Explorer](threat-explorer.md)).</span></span>

<span data-ttu-id="81558-162">第2阶段现在与**公共预览版**中的以下行动手册结合在一起，为操作和 aiding 安全管理员提供调查问题的建议：</span><span class="sxs-lookup"><span data-stu-id="81558-162">Phase 2 is now progress with the following playbooks in **public preview**, providing recommendations for actions and aiding security administrators in investigating issues:</span></span>
- <span data-ttu-id="81558-163">用户报告为 "已损坏" （公用预览）</span><span class="sxs-lookup"><span data-stu-id="81558-163">User reported as compromised (public preview)</span></span>

<span data-ttu-id="81558-164">在完成后，将立即发布后续行动手册。</span><span class="sxs-lookup"><span data-stu-id="81558-164">Further playbooks will be released as they are completed.</span></span> <span data-ttu-id="81558-165">访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)以查看计划和即将推出的其他内容。</span><span class="sxs-lookup"><span data-stu-id="81558-165">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what else is planned and coming soon.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="81558-166">行动手册包括调查和建议</span><span class="sxs-lookup"><span data-stu-id="81558-166">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="81558-167">在空中，每个安全行动手册包括：</span><span class="sxs-lookup"><span data-stu-id="81558-167">In AIR, each security playbook includes:</span></span> 
- <span data-ttu-id="81558-168">对电子邮件实体（文件、Url、收件人、IP 地址等）的根调查</span><span class="sxs-lookup"><span data-stu-id="81558-168">a root investigation of an email's entities (files, URLs, recipients, IP addresses, etc.),</span></span>
- <span data-ttu-id="81558-169">对组织收到的类似电子邮件的进一步搜寻</span><span class="sxs-lookup"><span data-stu-id="81558-169">further hunting for similar emails received by the organization</span></span> 
- <span data-ttu-id="81558-170">确定并关联其他潜在威胁所需的步骤，以及</span><span class="sxs-lookup"><span data-stu-id="81558-170">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="81558-171">建议的威胁补救措施。</span><span class="sxs-lookup"><span data-stu-id="81558-171">recommended threat remediation actions.</span></span>

<span data-ttu-id="81558-172">每个高级步骤都包含多个执行的子步骤，以提供对威胁的深入、详细和详尽的响应。</span><span class="sxs-lookup"><span data-stu-id="81558-172">Each high-level step includes a number of substeps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="81558-173">示例：用户报告的网络钓鱼邮件启动调查行动手册</span><span class="sxs-lookup"><span data-stu-id="81558-173">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="81558-174">当您的组织中的用户提交电子邮件并使用[outlook 或 Outlook Web App 的报告邮件加载项](enable-the-report-message-add-in.md)将其报告给 Microsoft 时，该报告也会发送到您的系统，并在用户报告的视图中显示在资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="81558-174">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web App](enable-the-report-message-add-in.md), the report is also sent to your system and is visible in Explorer in the User-reported view.</span></span> <span data-ttu-id="81558-175">此用户报告的消息现在会触发基于系统的信息警报，这将自动启动调查行动手册。</span><span class="sxs-lookup"><span data-stu-id="81558-175">This user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="81558-176">在根调查阶段，会评估电子邮件的各个方面。</span><span class="sxs-lookup"><span data-stu-id="81558-176">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="81558-177">具体包括：</span><span class="sxs-lookup"><span data-stu-id="81558-177">These include:</span></span>
- <span data-ttu-id="81558-178">确定它可能属于哪种类型的威胁;</span><span class="sxs-lookup"><span data-stu-id="81558-178">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="81558-179">发件人数;</span><span class="sxs-lookup"><span data-stu-id="81558-179">Who sent it;</span></span>
- <span data-ttu-id="81558-180">发送电子邮件的位置（发送基础结构）;</span><span class="sxs-lookup"><span data-stu-id="81558-180">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="81558-181">是否已传递或阻止电子邮件的其他实例;</span><span class="sxs-lookup"><span data-stu-id="81558-181">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="81558-182">我们分析家中的一种评估;</span><span class="sxs-lookup"><span data-stu-id="81558-182">An assessment from our analysts;</span></span>
- <span data-ttu-id="81558-183">电子邮件是否与任何已知的市场活动相关联;</span><span class="sxs-lookup"><span data-stu-id="81558-183">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="81558-184">等等。</span><span class="sxs-lookup"><span data-stu-id="81558-184">and more.</span></span>

<span data-ttu-id="81558-185">根调查完成后，行动手册提供了要对其关联的原始电子邮件和实体执行的建议操作的列表。</span><span class="sxs-lookup"><span data-stu-id="81558-185">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="81558-186">接下来，执行以下几个威胁调查和搜寻步骤：</span><span class="sxs-lookup"><span data-stu-id="81558-186">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="81558-187">类似的电子邮件通过电子邮件群集搜索进行标识。</span><span class="sxs-lookup"><span data-stu-id="81558-187">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="81558-188">该信号与其他平台（如[Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共享。</span><span class="sxs-lookup"><span data-stu-id="81558-188">The signal is shared with other platforms, such as [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="81558-189">确定是否有用户通过可疑电子邮件中的任何恶意链接单击过。</span><span class="sxs-lookup"><span data-stu-id="81558-189">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="81558-190">跨 Office 365 Exchange Online Protection （[EOP](exchange-online-protection-eop.md)）和 Office 365 高级威胁防护（[ATP](office-365-atp.md)）执行检查以查看用户是否报告了任何其他类似的消息。</span><span class="sxs-lookup"><span data-stu-id="81558-190">A check is done across Office 365 Exchange Online Protection ([EOP](exchange-online-protection-eop.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="81558-191">将执行检查以查看是否已泄露用户。</span><span class="sxs-lookup"><span data-stu-id="81558-191">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="81558-192">此检查跨 Office 365、 [Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)之间的信号，关联任何相关的用户活动异常。</span><span class="sxs-lookup"><span data-stu-id="81558-192">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span> 

<span data-ttu-id="81558-193">在搜寻阶段，会为各种搜寻步骤分配风险和威胁。</span><span class="sxs-lookup"><span data-stu-id="81558-193">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="81558-194">修正是行动手册的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="81558-194">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="81558-195">在此阶段中，将根据调查和搜寻阶段采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="81558-195">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="81558-196">示例：安全管理员触发来自威胁资源管理器的调查</span><span class="sxs-lookup"><span data-stu-id="81558-196">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="81558-197">除了由警报触发的自动调查之外，组织的安全操作团队可以通过[威胁资源管理器](threat-explorer.md)中的视图触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="81558-197">In addition to automatic investigations that are triggered by an alert, your organization's security operations team can trigger an automatic investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>

<span data-ttu-id="81558-198">例如，假设您正在查看资源管理器中有关用户报告的消息的数据。</span><span class="sxs-lookup"><span data-stu-id="81558-198">For example, suppose that you are viewing data in Explorer about user-reported messages.</span></span> <span data-ttu-id="81558-199">您可以在结果列表中选择一个项目，然后从 "操作" 菜单中单击 "**调查**" （假设您有相应的修正权限）。</span><span class="sxs-lookup"><span data-stu-id="81558-199">You can select an item in the list of results, and then click **Investigate** from the action menu (assuming you have appropriate remediation permissions).</span></span>

![使用调查按钮的资源管理器中的用户报告的消息](../../media/Explorer-UserReported-Investigate.png)

<span data-ttu-id="81558-201">作为另一个示例，假设您要查看检测为包含恶意软件的电子邮件的数据，并且有几封电子邮件被检测为包含恶意软件。</span><span class="sxs-lookup"><span data-stu-id="81558-201">As another example, suppose you are viewing data about email messages detected as containing malware, and there are several email messages detected as containing malware.</span></span> <span data-ttu-id="81558-202">您可以选择 "**电子邮件**" 选项卡，选择一个或多个电子邮件，然后在 "**操作**" 菜单上选择 "**调查**"。</span><span class="sxs-lookup"><span data-stu-id="81558-202">You can select the **Email** tab, select one or more email messages, and then, on the **Actions** menu, select **Investigate**.</span></span> 

![在资源管理器中开始调查恶意软件](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="81558-204">与由警报触发的行动手册类似，通过资源管理器中的视图触发的自动调查包括根调查、标识和关联威胁的步骤以及缓解这些威胁的建议操作。</span><span class="sxs-lookup"><span data-stu-id="81558-204">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="next-steps"></a><span data-ttu-id="81558-205">后续步骤</span><span class="sxs-lookup"><span data-stu-id="81558-205">Next steps</span></span>

- [<span data-ttu-id="81558-206">开始使用 Office 365 中的 AIR</span><span class="sxs-lookup"><span data-stu-id="81558-206">Get started using AIR in Office 365</span></span>](office-365-air.md)

- [<span data-ttu-id="81558-207">访问 Microsoft 365 路线图以了解即将推出和推出的内容</span><span class="sxs-lookup"><span data-stu-id="81558-207">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

