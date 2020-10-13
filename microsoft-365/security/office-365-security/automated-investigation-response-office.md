---
title: 自动调查和响应 (空中) 概述
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自动事件响应、调查、修正和威胁防护
ms.date: 09/29/2020
description: 在 Microsoft Defender for Office 365 中获取自动调查和响应功能的概述
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: d63ba8a6d3ffb653b30448a973e1cd862631d350
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447103"
---
# <a name="an-overview-of-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a><span data-ttu-id="5dbb7-104">Microsoft Defender for Office 365 中的自动调查和响应 (空中) 的概述</span><span class="sxs-lookup"><span data-stu-id="5dbb7-104">An overview of automated investigation and response (AIR) in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5dbb7-105">随着安全警报的触发，安全操作团队可查看这些警报并采取措施来保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-105">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="5dbb7-106">有时，安全操作团队可能会受到触发的警报量的感觉的不知所措。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-106">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="5dbb7-107">Microsoft Defender for Office 365 中的自动调查和响应 (空中) 功能可提供帮助。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-107">Automated investigation and response (AIR) capabilities in Microsoft Defender for Office 365 can help.</span></span> 

<span data-ttu-id="5dbb7-108">通过 AIR，您的安全操作团队可以更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-108">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="5dbb7-109">空中功能包括自动调查过程，以响应目前存在的已知威胁。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-109">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="5dbb7-110">适当的补救措施等待批准，使安全操作团队能够响应检测到的威胁。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-110">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span> 

<span data-ttu-id="5dbb7-111">本文提供了空中的概述。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-111">This article provides an overview of AIR.</span></span> <span data-ttu-id="5dbb7-112">当您准备好开始使用 AIR 时，请参阅 [自动调查和响应威胁](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-112">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

## <a name="at-a-high-level"></a><span data-ttu-id="5dbb7-113">高级别</span><span class="sxs-lookup"><span data-stu-id="5dbb7-113">At a high level</span></span>

<span data-ttu-id="5dbb7-114">随着警报的触发，安全行动手册将生效。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-114">As alerts are triggered, security playbooks go into effect.</span></span> <span data-ttu-id="5dbb7-115">根据具体情况，可以开始执行 [自动调查过程](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) 。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-115">Depending on the situation, an [automated investigation process](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) can begin.</span></span> <span data-ttu-id="5dbb7-116">在进行自动调查的过程中和之后，建议采取 [补救措施](air-remediation-actions.md) 。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-116">During and after an automated investigation, [remediation actions](air-remediation-actions.md) are recommended.</span></span> <span data-ttu-id="5dbb7-117">在 Microsoft Defender for Office 365 中不会自动执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-117">No actions are taken automatically in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="5dbb7-118">您的安全操作团队将进行审核，然后 [批准或拒绝每个修正操作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-118">Your security operations team reviews, and then [approves or rejects each remediation action](air-review-approve-pending-completed-actions.md).</span></span> <span data-ttu-id="5dbb7-119">当调查中的所有操作都被批准或拒绝时，调查完成。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-119">When all of the actions following an investigation are approved or rejected, the investigation completes.</span></span> <span data-ttu-id="5dbb7-120">所有这些活动都会在 Microsoft 365 安全中心 () 中进行跟踪和查看 [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-120">All of these activities are tracked and viewable in the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="5dbb7-121"> (若要了解详细信息，请参阅 [查看调查) 的详细信息](air-view-investigation-results.md#view-details-of-an-investigation) 。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-121">(To learn more, see [View details of an investigation](air-view-investigation-results.md#view-details-of-an-investigation)).</span></span>

<span data-ttu-id="5dbb7-122">以下各节提供了有关警报、安全行动手册和操作中的示例的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-122">The following sections provide more details about alerts, security playbooks, and examples of AIR in action.</span></span>

## <a name="alerts"></a><span data-ttu-id="5dbb7-123">警报</span><span class="sxs-lookup"><span data-stu-id="5dbb7-123">Alerts</span></span>

<span data-ttu-id="5dbb7-124">[警报](../../compliance/alert-policies.md#viewing-alerts) 表示用于事件响应的安全操作团队工作流的触发器。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-124">[Alerts](../../compliance/alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="5dbb7-125">确定要调查的正确通知集的优先级，同时确保没有威胁是 unaddressed 的挑战。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-125">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="5dbb7-126">在手动对通知进行调查时，安全操作团队必须对实体（如内容、设备和用户）进行 (（如内容、设备和用户）进行寻找和关联，) 威胁的风险。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-126">When investigations into alerts are performed manually, security operations teams must hunt and correlate entities (such as content, devices and users) at risk from threats.</span></span> <span data-ttu-id="5dbb7-127">此类任务和工作流可能非常耗时，并涉及多个工具和系统。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-127">Such tasks and workflows can be very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="5dbb7-128">通过让关键安全和威胁管理警报自动触发安全响应行动手册，可以通过空气、调查和响应安全事件进行自动化。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-128">With AIR, investigation and response for security events are automated by having key security and threat management alerts trigger security response playbooks automatically.</span></span> 

<span data-ttu-id="5dbb7-129">目前，对于气流，从下列类型的警报策略生成的警报将自动调查：</span><span class="sxs-lookup"><span data-stu-id="5dbb7-129">Currently for AIR, alerts generated from the following kinds of alert policies are auto-investigated:</span></span>  

- <span data-ttu-id="5dbb7-130">检测到潜在的恶意 URL 单击</span><span class="sxs-lookup"><span data-stu-id="5dbb7-130">A potentially malicious URL click was detected</span></span>
- <span data-ttu-id="5dbb7-131">用户报告为网络钓鱼的电子邮件`*`</span><span class="sxs-lookup"><span data-stu-id="5dbb7-131">Email reported by user as phish`*`</span></span>
- <span data-ttu-id="5dbb7-132">包含在传递后删除的恶意软件的电子邮件`*`</span><span class="sxs-lookup"><span data-stu-id="5dbb7-132">Email messages containing malware removed after delivery`*`</span></span>
- <span data-ttu-id="5dbb7-133">包含投递后删除的网络钓鱼 Url 的电子邮件`*`</span><span class="sxs-lookup"><span data-stu-id="5dbb7-133">Email messages containing phish URLs removed after delivery`*`</span></span>
- <span data-ttu-id="5dbb7-134">检测到可疑的电子邮件发送模式</span><span class="sxs-lookup"><span data-stu-id="5dbb7-134">Suspicious email sending patterns detected</span></span>
- <span data-ttu-id="5dbb7-135">限制用户发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="5dbb7-135">User restricted from sending email</span></span>
- <span data-ttu-id="5dbb7-136">管理员触发了电子邮件的手动调查`*`</span><span class="sxs-lookup"><span data-stu-id="5dbb7-136">Admin triggered manual investigation of email`*`</span></span>

> [!NOTE]
> <span data-ttu-id="5dbb7-137">标有星号 () 的警报在 `*` Microsoft 365 安全中心中的相应警报策略中被分配了一个 *信息性* 严重性，电子邮件通知处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-137">The alerts marked with an asterisk (`*`) are assigned an *Informational* severity in the respective alert policies within the Microsoft 365 security center, with email notifications turned off.</span></span> <span data-ttu-id="5dbb7-138">可以通过 [报警策略配置](../../compliance/alert-policies.md#alert-policy-settings)启用电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-138">Email notifications can be turned on through [Alert policy configuration](../../compliance/alert-policies.md#alert-policy-settings).</span></span> 

<span data-ttu-id="5dbb7-139">若要查看警报，请在安全 & 合规性中心中，选择 "**通知**" "  >  **查看警报**"。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-139">To view alerts, in the Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="5dbb7-140">选择一个警报以查看其详细信息，然后在那里使用 " **查看调查** " 链接转到相应的 [调查](air-view-investigation-results.md#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-140">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](air-view-investigation-results.md#investigation-graph).</span></span>  

> [!NOTE]
> <span data-ttu-id="5dbb7-141">默认情况下，通知视图中隐藏信息警报。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-141">Informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="5dbb7-142">若要查看它们，请更改警报筛选以包含信息警报。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-142">To see them, change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="5dbb7-143">如果您的组织通过警报管理系统、服务管理系统或安全信息和事件管理 (SIEM) 系统管理安全警报，则可以通过电子邮件通知或通过 [Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)向该系统发送通知。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-143">If your organization manages your security alerts through an alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="5dbb7-144">通过电子邮件或 API 的调查通知通知包含访问 Microsoft 365 安全中心中的警报的链接，使分配的安全管理员能够快速导航到调查。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-144">The investigation alert notifications via email or API include links to access the alerts in the Microsoft 365 security center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![链接到调查的警报](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a><span data-ttu-id="5dbb7-146">安全行动手册</span><span class="sxs-lookup"><span data-stu-id="5dbb7-146">Security playbooks</span></span>

<span data-ttu-id="5dbb7-147">安全行动手册是后端策略，是 Microsoft Defender for Office 365 和 Microsoft 威胁防护中的自动化的核心。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-147">Security playbooks are back-end policies that are at the heart of automation in Microsoft Defender for Office 365 and Microsoft Threat Protection.</span></span> <span data-ttu-id="5dbb7-148">空中提供的安全行动手册基于常见的实际安全方案，并根据安全操作团队的反馈进行开发。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-148">The security playbooks provided in AIR are based on common real-world security scenarios and developed based on feedback from security operations teams.</span></span> <span data-ttu-id="5dbb7-149">当您的组织中触发特定警报时，将自动启动安全行动手册。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-149">A security playbook is launched automatically when specific alerts are triggered within your organization.</span></span> <span data-ttu-id="5dbb7-150">通知触发后，相关的行动手册将由自动调查和响应系统运行。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-150">Once the alert triggers, the associated playbook is run by the automated investigation and response system.</span></span> <span data-ttu-id="5dbb7-151">调查根据特定警报的操作手册分析预警的步骤，查看所有关联的元数据 (包括电子邮件、用户、主题、发件人等 ) 。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-151">The investigation steps through analysis of the alert based on that particular alert's playbook, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="5dbb7-152">根据调查行动手册的发现，AIR 推荐了组织的安全团队可采取的一组操作来控制和缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-152">Based on the investigation playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="5dbb7-153">你将使用空中获取的安全行动手册旨在解决组织在当今的电子邮件中遇到的最常见威胁。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-153">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations encounter today with email.</span></span> <span data-ttu-id="5dbb7-154">它们基于安全操作和事件响应团队的输入，包括帮助保护 Microsoft 和客户资产的人员。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-154">They're based on input from security operations and incident response teams, including people who help defend Microsoft and our customers' assets.</span></span>

- <span data-ttu-id="5dbb7-155">用户报告的网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="5dbb7-155">User-reported phish message</span></span>
- <span data-ttu-id="5dbb7-156">URL-单击 "判定更改"</span><span class="sxs-lookup"><span data-stu-id="5dbb7-156">URL-click verdict change</span></span>
- <span data-ttu-id="5dbb7-157">检测到投递后 (恶意软件 ZAP) </span><span class="sxs-lookup"><span data-stu-id="5dbb7-157">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="5dbb7-158">网络钓鱼的检测到传送后的 ZAP (网络钓鱼 ZAP) </span><span class="sxs-lookup"><span data-stu-id="5dbb7-158">Phish detected post-delivery ZAP (Phish ZAP)</span></span>
- <span data-ttu-id="5dbb7-159">用户报告为已损坏</span><span class="sxs-lookup"><span data-stu-id="5dbb7-159">User reported as compromised</span></span> 
- <span data-ttu-id="5dbb7-160">管理员从资源管理器恶意软件、网络钓鱼或所有电子邮件视图触发的手动电子邮件调查 () </span><span class="sxs-lookup"><span data-stu-id="5dbb7-160">Manual email investigation (triggered by administrator from Explorer Malware, Phish, or All Email view)</span></span>

<span data-ttu-id="5dbb7-161">在完成后，将发布更多行动手册和行动手册更新。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-161">More playbooks and playbook updates will be released as they are completed.</span></span> <span data-ttu-id="5dbb7-162">访问 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap) 以查看计划和即将推出的其他内容。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-162">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what else is planned and coming soon.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="5dbb7-163">行动手册包括调查和建议</span><span class="sxs-lookup"><span data-stu-id="5dbb7-163">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="5dbb7-164">在空中，每个安全行动手册包括：</span><span class="sxs-lookup"><span data-stu-id="5dbb7-164">In AIR, each security playbook includes:</span></span> 

- <span data-ttu-id="5dbb7-165">对电子邮件的实体进行根调查 (如文件、Url、收件人、IP 地址等) </span><span class="sxs-lookup"><span data-stu-id="5dbb7-165">a root investigation of an email's entities (such as files, URLs, recipients, IP addresses, and more),</span></span>
- <span data-ttu-id="5dbb7-166">对组织收到的类似电子邮件的进一步搜寻</span><span class="sxs-lookup"><span data-stu-id="5dbb7-166">further hunting for similar emails received by the organization</span></span> 
- <span data-ttu-id="5dbb7-167">确定并关联其他潜在威胁所需的步骤，以及</span><span class="sxs-lookup"><span data-stu-id="5dbb7-167">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="5dbb7-168">建议的威胁补救措施。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-168">recommended threat remediation actions.</span></span>

<span data-ttu-id="5dbb7-169">每个高级步骤都包含多个执行的子步骤，以提供对威胁的深入、详细和详尽的响应。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-169">Each high-level step includes a number of substeps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="5dbb7-170">示例：用户报告的网络钓鱼邮件启动调查行动手册</span><span class="sxs-lookup"><span data-stu-id="5dbb7-170">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="5dbb7-171">假定组织中的某个用户收到电子邮件，而他们认为是网络钓鱼尝试。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-171">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="5dbb7-172">经过培训的用户报告此类邮件，使用 [报告邮件加载项](enable-the-report-message-add-in.md) 将其发送到 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-172">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="5dbb7-173">提交也会发送到您的系统，并在 " **提交** " 视图中显示 (以前称为 **用户报告** 的视图) 。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-173">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="5dbb7-174">此外，用户报告的消息现在会触发基于系统的信息警报，这将自动启动调查行动手册。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-174">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="5dbb7-175">在根调查阶段，会评估电子邮件的各个方面。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-175">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="5dbb7-176">这些方面包括：</span><span class="sxs-lookup"><span data-stu-id="5dbb7-176">These aspects include:</span></span>

- <span data-ttu-id="5dbb7-177">确定它可能属于哪种类型的威胁;</span><span class="sxs-lookup"><span data-stu-id="5dbb7-177">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="5dbb7-178">发件人数;</span><span class="sxs-lookup"><span data-stu-id="5dbb7-178">Who sent it;</span></span>
- <span data-ttu-id="5dbb7-179">电子邮件的发送位置 (发送基础结构) ;</span><span class="sxs-lookup"><span data-stu-id="5dbb7-179">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="5dbb7-180">是否已传递或阻止电子邮件的其他实例;</span><span class="sxs-lookup"><span data-stu-id="5dbb7-180">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="5dbb7-181">我们分析家中的一种评估;</span><span class="sxs-lookup"><span data-stu-id="5dbb7-181">An assessment from our analysts;</span></span>
- <span data-ttu-id="5dbb7-182">电子邮件是否与任何已知的市场活动相关联;</span><span class="sxs-lookup"><span data-stu-id="5dbb7-182">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="5dbb7-183">等等。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-183">and more.</span></span>

<span data-ttu-id="5dbb7-184">根调查完成后，行动手册提供了要对其关联的原始电子邮件和实体执行的建议操作的列表。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-184">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="5dbb7-185">接下来，执行以下几个威胁调查和搜寻步骤：</span><span class="sxs-lookup"><span data-stu-id="5dbb7-185">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="5dbb7-186">类似的电子邮件通过电子邮件群集搜索进行标识。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-186">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="5dbb7-187">该信号与其他平台（如 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共享。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-187">The signal is shared with other platforms, such as [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="5dbb7-188">确定是否有用户通过可疑电子邮件中的任何恶意链接单击过。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-188">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="5dbb7-189">在 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 Office 365 高级威胁防护 ([ATP](office-365-atp.md)) 中进行检查，以查看用户是否报告了任何其他类似的消息。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-189">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="5dbb7-190">将执行检查以查看是否已泄露用户。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-190">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="5dbb7-191">此检查跨 Office 365、 [Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)和 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)之间的信号，关联任何相关的用户活动异常。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-191">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="5dbb7-192">在搜寻阶段，会为各种搜寻步骤分配风险和威胁。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-192">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="5dbb7-193">修正是行动手册的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-193">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="5dbb7-194">在此阶段中，将根据调查和搜寻阶段采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-194">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="5dbb7-195">示例：安全管理员触发来自威胁资源管理器的调查</span><span class="sxs-lookup"><span data-stu-id="5dbb7-195">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="5dbb7-196">除了由警报触发的自动调查之外，组织的安全操作团队还可以通过 [威胁资源管理器](threat-explorer.md)中的视图触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-196">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>  <span data-ttu-id="5dbb7-197">此调查还会创建一个警报，以便 Microsoft Defender 事件和外部 SIEM 工具可以查看是否触发了此调查。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-197">This investigation also creates an alert, so that Microsoft Defender Incidents and external SIEM tools can see that this investigation was triggered.</span></span> 

<span data-ttu-id="5dbb7-198">例如，假设您正在使用资源管理器中的 **恶意软件** 视图。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-198">For example, suppose that you are using the **Malware** view in Explorer.</span></span> <span data-ttu-id="5dbb7-199">使用图表下方的选项卡，选择 " **电子邮件** " 选项卡。如果选择列表中的一个或多个项目，则 " **+ 动作** " 按钮将激活。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-199">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span> 

![包含所选邮件的资源管理器](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="5dbb7-201">使用 " **操作** " 菜单，可以选择 **触发调查**。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-201">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![选定邮件的 "操作" 菜单](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="5dbb7-203">与由警报触发的行动手册类似，通过资源管理器中的视图触发的自动调查包括根调查、标识和关联威胁的步骤以及缓解这些威胁的建议操作。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-203">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="5dbb7-204">示例：安全操作团队使用 Office 365 管理活动 API 将空中与其 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="5dbb7-204">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="5dbb7-205">Microsoft Defender for Office 365 中的空中功能包括 [报告 & 详细信息](air-view-investigation-results.md) ，安全操作团队可以使用这些信息来监视和解决威胁。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-205">AIR capabilities in Microsoft Defender for Office 365 include [reports & details](air-view-investigation-results.md) that security operations teams can use to monitor and address threats.</span></span> <span data-ttu-id="5dbb7-206">但您也可以将空中功能与其他解决方案集成。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-206">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="5dbb7-207">示例包括安全信息和事件管理 (SIEM) 系统、案例管理系统或自定义报告解决方案。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-207">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="5dbb7-208">这些类型的集成可以通过使用 [Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)来实现。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-208">These kinds of integrations can be done by using the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="5dbb7-209">例如，最近，一个组织为其安全操作团队设置了一种方法，以查看用户报告的已由 AIR 处理的网络钓鱼警报。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-209">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="5dbb7-210">其解决方案将相关警报与组织的 SIEM 服务器及其事例管理系统集成在一起。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-210">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="5dbb7-211">该解决方案大大减少了误报的数量，使其安全操作团队能够将他们的时间和精力集中在真正的威胁上。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-211">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="5dbb7-212">若要了解有关此自定义解决方案的详细信息，请参阅 [技术社区博客：使用 Office 365 ATP 和 O365 管理 API 提高 SOC 的有效性](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="5dbb7-212">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5dbb7-213">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5dbb7-213">Next steps</span></span>

- [<span data-ttu-id="5dbb7-214">开始使用空中</span><span class="sxs-lookup"><span data-stu-id="5dbb7-214">Get started using AIR</span></span>](office-365-air.md)

- [<span data-ttu-id="5dbb7-215">访问 Microsoft 365 路线图以查看已计划和即将发布的内容</span><span class="sxs-lookup"><span data-stu-id="5dbb7-215">Visit the Microsoft 365 Roadmap to see what's planned and releasing soon</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [<span data-ttu-id="5dbb7-216">了解 Microsoft 365 Defender 中的其他自动化调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="5dbb7-216">Learn about additional automated investigation and response capabilities in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
