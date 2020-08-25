---
title: AIR R 自动调查和 () 概述
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
ms.date: 08/21/2020
description: 简要了解 Office 365 高级威胁防护计划 2 中的自动调查和响应功能。
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: 27a2330d5f1ff339aabf6a0fccb94a15dec30852
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860717"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-365"></a><span data-ttu-id="94fb4-103">Microsoft 365 自动调查 (响应（在 Microsoft 365 (AIR) 概述</span><span class="sxs-lookup"><span data-stu-id="94fb4-103">An overview of Automated investigation and response (AIR) in Microsoft 365</span></span>

<span data-ttu-id="94fb4-104">触发安全警报后，安全运营团队将根据这些警报来查看这些警报并采取措一步来保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="94fb4-104">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="94fb4-105">有时，安全运营团队可能对触发的警报数量感到不一些。</span><span class="sxs-lookup"><span data-stu-id="94fb4-105">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="94fb4-106">Office 365 高级威胁防护 () Office 365 ATP) 中的自动调 (查和) 可能有所帮助。</span><span class="sxs-lookup"><span data-stu-id="94fb4-106">Automated investigation and response (AIR) capabilities in Office 365 Advanced Threat Protection (Office 365 ATP) can help.</span></span> 

<span data-ttu-id="94fb4-107">AIR 使你的安全运营团队可以更有效地运营。</span><span class="sxs-lookup"><span data-stu-id="94fb4-107">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="94fb4-108">AIR 功能包括自动调查流程以响应当今存在的已知威胁。</span><span class="sxs-lookup"><span data-stu-id="94fb4-108">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="94fb4-109">适当的修正操作等待审批，从而使安全操作团队能够响应检测到的威胁。</span><span class="sxs-lookup"><span data-stu-id="94fb4-109">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span> 

<span data-ttu-id="94fb4-110">本文概述 AIR。</span><span class="sxs-lookup"><span data-stu-id="94fb4-110">This article provides an overview of AIR.</span></span> <span data-ttu-id="94fb4-111">准备好开始使用 AIR 后，请参阅["自动调查并响应威胁"。](office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="94fb4-111">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

## <a name="at-a-high-level"></a><span data-ttu-id="94fb4-112">在高级别</span><span class="sxs-lookup"><span data-stu-id="94fb4-112">At a high level</span></span>

<span data-ttu-id="94fb4-113">触发警报后，安全手册将生效。</span><span class="sxs-lookup"><span data-stu-id="94fb4-113">As alerts are triggered, security playbooks go into effect.</span></span> <span data-ttu-id="94fb4-114">根据情况，可以 [开始自动调查流程](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) 。</span><span class="sxs-lookup"><span data-stu-id="94fb4-114">Depending on the situation, an [automated investigation process](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) can begin.</span></span> <span data-ttu-id="94fb4-115">在自动调查期间以及在执行自动调查之后， [建议采取修正](air-remediation-actions.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="94fb4-115">During and after an automated investigation, [remediation actions](air-remediation-actions.md) are recommended.</span></span> <span data-ttu-id="94fb4-116">Office 365 高级威胁防护中不自动执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="94fb4-116">No actions are taken automatically in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="94fb4-117">安全操作团队审阅，然后 [批准或拒绝每个修正操作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="94fb4-117">Your security operations team reviews, and then [approves or rejects each remediation action](air-review-approve-pending-completed-actions.md).</span></span> <span data-ttu-id="94fb4-118">在批准或拒绝后的所有操作后，调查即完成。</span><span class="sxs-lookup"><span data-stu-id="94fb4-118">When all of the actions following an investigation are approved or rejected, the investigation completes.</span></span> <span data-ttu-id="94fb4-119">所有这些活动都要在安全 & 合规中心内进行跟踪和 (请参阅" [查看调查服务监视监视](air-view-investigation-results.md#view-details-of-an-investigation)) "。</span><span class="sxs-lookup"><span data-stu-id="94fb4-119">All of these activities are tracked and viewable in the Security & Compliance Center (see [View details of an investigation](air-view-investigation-results.md#view-details-of-an-investigation)).</span></span>

<span data-ttu-id="94fb4-120">以下部分提供了关于警报、安全手册以及 AIR 的操作示例的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="94fb4-120">The following sections provide more details about alerts, security playbooks, and examples of AIR in action.</span></span>

## <a name="alerts"></a><span data-ttu-id="94fb4-121">警报</span><span class="sxs-lookup"><span data-stu-id="94fb4-121">Alerts</span></span>

<span data-ttu-id="94fb4-122">[警报](../../compliance/alert-policies.md#viewing-alerts) 表示针对事件响应的安全操作团队工作流的触发器。</span><span class="sxs-lookup"><span data-stu-id="94fb4-122">[Alerts](../../compliance/alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="94fb4-123">确定合适警报组的调查优先级，确保未提供任何未解决的威胁是一大挑战性。</span><span class="sxs-lookup"><span data-stu-id="94fb4-123">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="94fb4-124">手动调查警报时，安全操作团队必须对实体 (如内容、设备和用户在风险中受威胁胁，并区) 分相关。</span><span class="sxs-lookup"><span data-stu-id="94fb4-124">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (such as content, devices and users) at risk from threats.</span></span> <span data-ttu-id="94fb4-125">此类任务和工作流可能非常耗时，并且涉及多个工具和系统。</span><span class="sxs-lookup"><span data-stu-id="94fb4-125">Such tasks and workflows can be very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="94fb4-126">通过 AIR，通过使关键安全性和威胁管理警报可自动触发安全响应 Playbook 来自动调查和响应安全事件。</span><span class="sxs-lookup"><span data-stu-id="94fb4-126">With AIR, investigation and response for security events are automated by having key security and threat management alerts trigger security response playbooks automatically.</span></span> 

<span data-ttu-id="94fb4-127">目前对于 AIR，从以下类型的警报策略生成的警报是自动调查的：</span><span class="sxs-lookup"><span data-stu-id="94fb4-127">Currently for AIR, alerts generated from the following kinds of alert policies are auto-investigated:</span></span>  

- <span data-ttu-id="94fb4-128">检测到可能存在的恶意 URL 单击</span><span class="sxs-lookup"><span data-stu-id="94fb4-128">A potentially malicious URL click was detected</span></span>
- <span data-ttu-id="94fb4-129">用户报告为钓鱼邮件的电子邮件`*`</span><span class="sxs-lookup"><span data-stu-id="94fb4-129">Email reported by user as phish`*`</span></span>
- <span data-ttu-id="94fb4-130">送达后删除了恶意软件的电子邮件`*`</span><span class="sxs-lookup"><span data-stu-id="94fb4-130">Email messages containing malware removed after delivery`*`</span></span>
- <span data-ttu-id="94fb4-131">传递后删除了包含网络钓鱼 URL 的电子邮件`*`</span><span class="sxs-lookup"><span data-stu-id="94fb4-131">Email messages containing phish URLs removed after delivery`*`</span></span>
- <span data-ttu-id="94fb4-132">检测到可疑电子邮件发送模式`#`</span><span class="sxs-lookup"><span data-stu-id="94fb4-132">Suspicious email sending patterns detected`#`</span></span>
- <span data-ttu-id="94fb4-133">限制发送电子邮件的用户`#`</span><span class="sxs-lookup"><span data-stu-id="94fb4-133">User restricted from sending email`#`</span></span>

> [!NOTE]
> <span data-ttu-id="94fb4-134">标有星号 () 的警报会在安全 & 合规中心内各自警报策略 `*` 中为其分配信息严*Informational*重性，并关闭电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="94fb4-134">The alerts marked with an asterisk (`*`) are assigned an *Informational* severity in the respective alert policies within the Security & Compliance Center, with email notifications turned off.</span></span> <span data-ttu-id="94fb4-135">电子邮件通知可以通过"提醒策略" [进行打开](../../compliance/alert-policies.md#alert-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="94fb4-135">Email notifications can be turned on through [Alert policy configuration](../../compliance/alert-policies.md#alert-policy-settings).</span></span> <span data-ttu-id="94fb4-136">标有哈希事件 `#` () 发布与公共预览手册相关联的公用警报。</span><span class="sxs-lookup"><span data-stu-id="94fb4-136">Alerts marked with a hash (`#`) are generally available alerts associated with public preview playbooks.</span></span>

<span data-ttu-id="94fb4-137">若要查看警报，请在安全&合规中心中，选择 **"警报**  >  **查看警报"。**</span><span class="sxs-lookup"><span data-stu-id="94fb4-137">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="94fb4-138">选择一个警报以查看其详细信息，然后从 **此处使用"** 查看调查"链接 [转到相应的调查](air-view-investigation-results.md#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="94fb4-138">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](air-view-investigation-results.md#investigation-graph).</span></span>  

> [!NOTE]
> <span data-ttu-id="94fb4-139">默认情况下，信息通知在警报视图中是隐藏的。</span><span class="sxs-lookup"><span data-stu-id="94fb4-139">Informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="94fb4-140">若要查看它们，请更改警报筛选以包含信息性警报。</span><span class="sxs-lookup"><span data-stu-id="94fb4-140">To see them, change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="94fb4-141">如果你的组织通过警报管理系统、服务管理系统或安全信息和事件管理 (SIEM) 系统管理安全警报，则可以通过电子邮件通知或通过 Office 365 管理活动 API 向 [该系统发送警报](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="94fb4-141">If your organization manages your security alerts through an alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="94fb4-142">调查警报通知是通过电子邮件或 API 发送的警报通知，其中包括指向安全 & 合规中心内访问警报的链接，这使分配的安全管理员能够快速导航至调查。</span><span class="sxs-lookup"><span data-stu-id="94fb4-142">The investigation alert notifications via email or API include links to access the alerts in the Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![链接到调查的警报](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a><span data-ttu-id="94fb4-144">安全手册</span><span class="sxs-lookup"><span data-stu-id="94fb4-144">Security playbooks</span></span>

<span data-ttu-id="94fb4-145">安全手册是 Office 高级威胁防护和 Microsoft 威胁防护中的自动化的后端策略。</span><span class="sxs-lookup"><span data-stu-id="94fb4-145">Security playbooks are back-end policies that are at the heart of automation in Office Advanced Threat Protection and Microsoft Threat Protection.</span></span> <span data-ttu-id="94fb4-146">AIR 中提供的安全手册基于常见的实际安全方案，并根据安全运营团队反馈而制定。</span><span class="sxs-lookup"><span data-stu-id="94fb4-146">The security playbooks provided in AIR are based on common real-world security scenarios and developed based on feedback from Security Operations teams.</span></span> <span data-ttu-id="94fb4-147">在组织内触发特定警报时，会自动启动安全手册。</span><span class="sxs-lookup"><span data-stu-id="94fb4-147">A security playbook is launched automatically when specific alerts are triggered within your organization.</span></span> <span data-ttu-id="94fb4-148">警报触发器触发器后，关联的手册将由自动调查和响应系统 (答) 运行。</span><span class="sxs-lookup"><span data-stu-id="94fb4-148">Once the alert triggers, the associated playbook is run by the Automated Investigation and Response (AIR) system.</span></span> <span data-ttu-id="94fb4-149">调查根据该特定警报的手册分步分析警报，查看所有关联的元数据 (包括电子邮件、用户、主题、发件人等 ) 。</span><span class="sxs-lookup"><span data-stu-id="94fb4-149">The investigation steps through analysis of the alert based on that particular alert's playbook, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="94fb4-150">基于调查手册的查找，AIR 建议执行一组操作，组织安全团队可对这些操作控制和缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="94fb4-150">Based on the investigation playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="94fb4-151">通过 AIR 你将获取的安全手册旨在应对组织现在遇到电子邮件的最常见威胁。</span><span class="sxs-lookup"><span data-stu-id="94fb4-151">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations encounter today with email.</span></span> <span data-ttu-id="94fb4-152">它们基于来自安全运营和事件响应团队的输入，包括帮助推迟 Microsoft 的人员和我们的客户资产。</span><span class="sxs-lookup"><span data-stu-id="94fb4-152">They're based on input from Security Operations and Incident Response teams, including people who help defend Microsoft and our customers' assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="94fb4-153">安全手册分阶段推出</span><span class="sxs-lookup"><span data-stu-id="94fb4-153">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="94fb4-154">作为 AIR 的一部分，安全手册分阶段推出。</span><span class="sxs-lookup"><span data-stu-id="94fb4-154">As part of AIR, security playbooks are rolling out in phases.</span></span> <span data-ttu-id="94fb4-155">第 1 阶段现在正式发布，并包括几个对于安全管理员可查看和批准的操作建议的手册：</span><span class="sxs-lookup"><span data-stu-id="94fb4-155">Phase 1 is now generally available and includes several playbooks that provide recommendations for actions that security administrators can review and approve:</span></span>

- <span data-ttu-id="94fb4-156">用户报告的网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="94fb4-156">User-reported phish message</span></span>
- <span data-ttu-id="94fb4-157">URL 单击顶点更改</span><span class="sxs-lookup"><span data-stu-id="94fb4-157">URL-click verdict change</span></span>
- <span data-ttu-id="94fb4-158">在恶意软件 ZAP 服务器后 (检测到) </span><span class="sxs-lookup"><span data-stu-id="94fb4-158">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="94fb4-159">网络钓鱼检测到了钓鱼邮件 (的邮政) </span><span class="sxs-lookup"><span data-stu-id="94fb4-159">Phish detected post-delivery ZAP (Phish ZAP)</span></span>

<span data-ttu-id="94fb4-160">第 1 阶段还包括对使用威胁资源管理器管理控制台网站 (管理员触发 [的电子邮件](threat-explorer.md) 调查) 。</span><span class="sxs-lookup"><span data-stu-id="94fb4-160">Phase 1 also includes support for administrator triggered e-mail investigations (using [Threat Explorer](threat-explorer.md)).</span></span>

<span data-ttu-id="94fb4-161">第 2 阶段现在正在开发公共预览版中的**public preview**以下手册，提供操作建议，并帮助安全管理员调查问题：</span><span class="sxs-lookup"><span data-stu-id="94fb4-161">Phase 2 is now progress with the following playbooks in **public preview**, providing recommendations for actions, and aiding security administrators in investigating issues:</span></span>

- <span data-ttu-id="94fb4-162">用户报告为已在 (预览版) </span><span class="sxs-lookup"><span data-stu-id="94fb4-162">User reported as compromised (public preview)</span></span>

<span data-ttu-id="94fb4-163">完成后将发布更多的 Playbook。</span><span class="sxs-lookup"><span data-stu-id="94fb4-163">More playbooks will be released as they are completed.</span></span> <span data-ttu-id="94fb4-164">请访问 [Microsoft 365 产品指南](https://www.microsoft.com/microsoft-365/roadmap) ，了解还有其他内容的计划和即将推出。</span><span class="sxs-lookup"><span data-stu-id="94fb4-164">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what else is planned and coming soon.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="94fb4-165">Playbook 包括调查和建议</span><span class="sxs-lookup"><span data-stu-id="94fb4-165">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="94fb4-166">在 AIR 中，每个安全手册都包括：</span><span class="sxs-lookup"><span data-stu-id="94fb4-166">In AIR, each security playbook includes:</span></span> 

- <span data-ttu-id="94fb4-167">电子邮件实体的根调查 (，如文件、URL、收件人、IP 地址等) ，等等</span><span class="sxs-lookup"><span data-stu-id="94fb4-167">a root investigation of an email's entities (such as files, URLs, recipients, IP addresses, and more),</span></span>
- <span data-ttu-id="94fb4-168">进一步寻搜索组织收到的类似电子邮件</span><span class="sxs-lookup"><span data-stu-id="94fb4-168">further hunting for similar emails received by the organization</span></span> 
- <span data-ttu-id="94fb4-169">识别和链接其他潜在威胁并进行共享的步骤，并且</span><span class="sxs-lookup"><span data-stu-id="94fb4-169">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="94fb4-170">建议的威胁修正操作。</span><span class="sxs-lookup"><span data-stu-id="94fb4-170">recommended threat remediation actions.</span></span>

<span data-ttu-id="94fb4-171">每个高级步骤都包括多个子步骤，执行它们可以对威胁提供深入、详细且十分详细的响应。</span><span class="sxs-lookup"><span data-stu-id="94fb4-171">Each high-level step includes a number of substeps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="94fb4-172">示例：用户报告的网络钓鱼邮件启动调查手册</span><span class="sxs-lookup"><span data-stu-id="94fb4-172">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="94fb4-173">假设您组织的用户会收到他们认为是网络钓鱼尝试的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="94fb4-173">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="94fb4-174">用户有一些训适用于报告此类邮件的文档 [，使用"报告邮件"加载项](enable-the-report-message-add-in.md) 将邮件发送到 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="94fb4-174">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="94fb4-175">提交也会发送到你的系统，并且可在资源管理器 **的"提交"** 视图中 ("请求 **的视图** "中) 。</span><span class="sxs-lookup"><span data-stu-id="94fb4-175">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="94fb4-176">此外，用户报告的消息现在会触发基于系统的信息警报，这会自动启动调查手册。</span><span class="sxs-lookup"><span data-stu-id="94fb4-176">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="94fb4-177">在根调查阶段，会评估电子邮件的各个方面。</span><span class="sxs-lookup"><span data-stu-id="94fb4-177">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="94fb4-178">这些方面包括：</span><span class="sxs-lookup"><span data-stu-id="94fb4-178">These aspects include:</span></span>

- <span data-ttu-id="94fb4-179">关于它可能是哪种威胁类型的确定;</span><span class="sxs-lookup"><span data-stu-id="94fb4-179">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="94fb4-180">它的发送对象;</span><span class="sxs-lookup"><span data-stu-id="94fb4-180">Who sent it;</span></span>
- <span data-ttu-id="94fb4-181">电子邮件从应用程序发送 (时) ;</span><span class="sxs-lookup"><span data-stu-id="94fb4-181">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="94fb4-182">是否传递或阻止了电子邮件的其他实例;</span><span class="sxs-lookup"><span data-stu-id="94fb4-182">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="94fb4-183">我们的评估中的评估;</span><span class="sxs-lookup"><span data-stu-id="94fb4-183">An assessment from our analysts;</span></span>
- <span data-ttu-id="94fb4-184">电子邮件是否与任何已知活动相关联;</span><span class="sxs-lookup"><span data-stu-id="94fb4-184">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="94fb4-185">等等。</span><span class="sxs-lookup"><span data-stu-id="94fb4-185">and more.</span></span>

<span data-ttu-id="94fb4-186">根调查完成后，手册将提供对原始电子邮件及其关联实体执行的建议操作的列表。</span><span class="sxs-lookup"><span data-stu-id="94fb4-186">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="94fb4-187">接下来，执行几个威胁调查和搜索步骤：</span><span class="sxs-lookup"><span data-stu-id="94fb4-187">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="94fb4-188">通过电子邮件群集搜索标识类似的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="94fb4-188">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="94fb4-189">信号可与其他平台（如 [Microsoft Defender ATP）共享](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="94fb4-189">The signal is shared with other platforms, such as [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="94fb4-190">确定是否有任何用户通过可疑电子邮件中的任何恶意链接进行了单击。</span><span class="sxs-lookup"><span data-stu-id="94fb4-190">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="94fb4-191">检查通过 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 Office 365 高级威胁防护 ([ATP](office-365-atp.md)) ，以查看是否有其他类似邮件由用户报告。</span><span class="sxs-lookup"><span data-stu-id="94fb4-191">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="94fb4-192">检查时是为了查看用户是否已被入入入是否被入入入。</span><span class="sxs-lookup"><span data-stu-id="94fb4-192">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="94fb4-193">此检查利用 Office 365、Microsoft [Cloud App Security](https://docs.microsoft.com/cloud-app-security)和 Azure Active [Directory](https://docs.microsoft.com/azure/active-directory)中的信号来关联任何相关的用户活动异常。</span><span class="sxs-lookup"><span data-stu-id="94fb4-193">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="94fb4-194">在搜索阶段，将为各种智能寻线步骤分配风险和威胁。</span><span class="sxs-lookup"><span data-stu-id="94fb4-194">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="94fb4-195">修正是 Playbook 的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="94fb4-195">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="94fb4-196">在此阶段，将根据调查和搜索阶段采取修正步骤。</span><span class="sxs-lookup"><span data-stu-id="94fb4-196">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="94fb4-197">示例：安全管理员通过威胁资源管理器触发调查</span><span class="sxs-lookup"><span data-stu-id="94fb4-197">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="94fb4-198">除了警报触发的自动调查，组织的安全运营团队还可以从威胁资源管理器中的视图触发自动 [调查](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="94fb4-198">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>

<span data-ttu-id="94fb4-199">例如，假设你在威胁资源管理器 **中使用** 恶意软件视图。</span><span class="sxs-lookup"><span data-stu-id="94fb4-199">For example, suppose that you are using the **Malware** view in Threat Explorer.</span></span> <span data-ttu-id="94fb4-200">使用图表下方的选项卡，选择"电子邮件 **"** 选项卡。如果选择列表中的一个或多个项，将激活+ **操作** 按钮。</span><span class="sxs-lookup"><span data-stu-id="94fb4-200">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span> 

![包含选定邮件的资源管理器](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="94fb4-202">使用 **"操作**"菜单，**可以选择"触发器调查"。**</span><span class="sxs-lookup"><span data-stu-id="94fb4-202">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![选定邮件的操作菜单](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="94fb4-204">与警报触发的手册、从资源管理器的视图触发的自动调查包括根调查、标识并相关威胁的步骤以及建议采取的操作以缓解这些威胁。</span><span class="sxs-lookup"><span data-stu-id="94fb4-204">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="94fb4-205">示例：安全操作团队使用 Office 365 管理活动 API 将 AIR 与其 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="94fb4-205">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="94fb4-206">Office 365 ATP 中的 AIR 功能包括 [的报告&安全](air-view-investigation-results.md) 运营团队可以用其监视和解决威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="94fb4-206">AIR capabilities in Office 365 ATP include [reports & details](air-view-investigation-results.md) that security operations team can use to monitor and address threats.</span></span> <span data-ttu-id="94fb4-207">但是，你也可以将 AIR 功能与其他解决方案集成。</span><span class="sxs-lookup"><span data-stu-id="94fb4-207">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="94fb4-208">示例包括安全信息和事件管理 (SIEM) 、事例管理系统或自定义报告解决方案。</span><span class="sxs-lookup"><span data-stu-id="94fb4-208">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="94fb4-209">这些类型的集成可以通过使用 [Office 365 管理活动 API 来完成](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="94fb4-209">These kinds of integration can be done by using the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="94fb4-210">例如，组织为安全运营团队制定了一种查看已由 AIR 处理的用户报告的网络钓鱼警报的方式。</span><span class="sxs-lookup"><span data-stu-id="94fb4-210">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="94fb4-211">其解决方案将相关警报与组织的 SIEM 服务器及其案例管理系统集成。</span><span class="sxs-lookup"><span data-stu-id="94fb4-211">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="94fb4-212">该解决方案大大减少误报数，以便安全运营团队可以专注于真实威胁的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="94fb4-212">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="94fb4-213">若要了解有关此自定义解决方案的详细信息，请参阅 [技术社区博客：通过 Office 365 ATP 和 O365 管理 API 提高 SOC 的效力](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="94fb4-213">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-step"></a><span data-ttu-id="94fb4-214">后续步骤</span><span class="sxs-lookup"><span data-stu-id="94fb4-214">Next step</span></span>

- [<span data-ttu-id="94fb4-215">AIR 使用入门</span><span class="sxs-lookup"><span data-stu-id="94fb4-215">Get started using AIR</span></span>](office-365-air.md)

## <a name="see-also"></a><span data-ttu-id="94fb4-216">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94fb4-216">See also</span></span>

- [<span data-ttu-id="94fb4-217">Microsoft 365 路线图</span><span class="sxs-lookup"><span data-stu-id="94fb4-217">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [<span data-ttu-id="94fb4-218">Microsoft 威胁防护中的自动调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="94fb4-218">Automated investigation and response capabilities in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide)