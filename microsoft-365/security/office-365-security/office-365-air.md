---
title: Microsoft Defender for Office 365 中的自动调查和响应
keywords: AIR， autoIR， ATP， 自动化， 调查， 响应， 修正， 威胁， 高级， 威胁， 保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/05/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 开始使用 Microsoft Defender for Office 365 中的自动调查和响应功能。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 6ccefb5c435f08fcef4dcc872af676fba70668ee
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794540"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0df54-104">Microsoft Defender for Office 365 (AIR) 自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="0df54-104">Automated investigation and response (AIR) in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0df54-105">[Microsoft Defender for Office 365](office-365-atp.md) 包括强大的自动调查和响应 (AIR) 功能，可节省安全运营团队的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="0df54-105">[Microsoft Defender for Office 365](office-365-atp.md) includes powerful automated investigation and response (AIR) capabilities that can save your security operations team time and effort.</span></span> <span data-ttu-id="0df54-106">触发警报后，由安全运营团队来审阅、确定优先级并响应这些警报。</span><span class="sxs-lookup"><span data-stu-id="0df54-106">As alerts are triggered, it's up to your security operations team to review, prioritize, and respond to those alerts.</span></span> <span data-ttu-id="0df54-107">与传入警报的量保持一起可能会很不知所措。</span><span class="sxs-lookup"><span data-stu-id="0df54-107">Keeping up with the volume of incoming alerts can be overwhelming.</span></span> <span data-ttu-id="0df54-108">自动执行其中一些任务可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="0df54-108">Automating some of those tasks can help.</span></span>

<span data-ttu-id="0df54-109">AIR 使安全运营团队可以更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="0df54-109">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="0df54-110">AIR 功能包括自动调查流程，以响应当今存在的已知威胁。</span><span class="sxs-lookup"><span data-stu-id="0df54-110">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="0df54-111">适当的修正操作等待审批，使安全运营团队能够有效响应检测到的威胁。</span><span class="sxs-lookup"><span data-stu-id="0df54-111">Appropriate remediation actions await approval, enabling your security operations team to respond effectively to detected threats.</span></span> <span data-ttu-id="0df54-112">使用 AIR，安全运营团队可以专注于优先级较高的任务，而不会忽略触发的重要警报。</span><span class="sxs-lookup"><span data-stu-id="0df54-112">With AIR, your security operations team can focus on higher-priority tasks without losing sight of important alerts that are triggered.</span></span>

<span data-ttu-id="0df54-113">本文内容：</span><span class="sxs-lookup"><span data-stu-id="0df54-113">This article describes:</span></span>

- <span data-ttu-id="0df54-114">AIR [的整体流](#the-overall-flow-of-air);</span><span class="sxs-lookup"><span data-stu-id="0df54-114">The [overall flow of AIR](#the-overall-flow-of-air);</span></span>
- <span data-ttu-id="0df54-115">[如何获取 AIR;](#how-to-get-air)and</span><span class="sxs-lookup"><span data-stu-id="0df54-115">[How to get AIR](#how-to-get-air); and</span></span>
- <span data-ttu-id="0df54-116">[配置或使用](#required-permissions-to-use-air-capabilities)AIR 功能所需的权限。</span><span class="sxs-lookup"><span data-stu-id="0df54-116">The [required permissions](#required-permissions-to-use-air-capabilities) to configure or use AIR capabilities.</span></span>

<span data-ttu-id="0df54-117">本文还包括下 [一步](#next-steps)，以及了解更多信息的资源。</span><span class="sxs-lookup"><span data-stu-id="0df54-117">This article also includes [next steps](#next-steps), and resources to learn more.</span></span>

## <a name="the-overall-flow-of-air"></a><span data-ttu-id="0df54-118">AIR 的整体流</span><span class="sxs-lookup"><span data-stu-id="0df54-118">The overall flow of AIR</span></span>

<span data-ttu-id="0df54-119">触发警报，安全手册启动自动调查，从而产生发现和推荐操作。</span><span class="sxs-lookup"><span data-stu-id="0df54-119">An alert is triggered, and a security playbook starts an automated investigation, which results in findings and recommended actions.</span></span> <span data-ttu-id="0df54-120">下面是 AIR 的整体流程，分步说明：</span><span class="sxs-lookup"><span data-stu-id="0df54-120">Here's the overall flow of AIR, step by step:</span></span>

1. <span data-ttu-id="0df54-121">自动调查以下列方式之一启动：</span><span class="sxs-lookup"><span data-stu-id="0df54-121">An automated investigation is initiated in one of the following ways:</span></span>

   - <span data-ttu-id="0df54-122">警报 [由](#which-alert-policies-trigger-automated-investigations) 电子邮件内容中的可疑内容 (例如邮件、附件、URL 或遭到入侵的用户帐户) 。</span><span class="sxs-lookup"><span data-stu-id="0df54-122">An [alert is triggered](#which-alert-policies-trigger-automated-investigations) by something suspicious in email (such as a message, attachment, URL, or compromised user account).</span></span> <span data-ttu-id="0df54-123">创建事件，并开始自动调查。</span><span class="sxs-lookup"><span data-stu-id="0df54-123">An incident is created, and an automated investigation begins.</span></span>

     <span data-ttu-id="0df54-124">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="0df54-124">--- or ---</span></span>

   - <span data-ttu-id="0df54-125">安全分析 [员在使用威胁资源管理器时](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 启动 [自动调查](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="0df54-125">A security analyst [starts an automated investigation](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) while using [Threat Explorer](threat-explorer.md).</span></span>

2. <span data-ttu-id="0df54-126">当自动调查运行时，它将收集有关相关电子邮件和与该电子邮件相关的实体的其他数据。</span><span class="sxs-lookup"><span data-stu-id="0df54-126">While an automated investigation runs, it gathers additional data about the email in question and entities related to that email.</span></span> <span data-ttu-id="0df54-127">此类实体可以包括文件、URL 和收件人。</span><span class="sxs-lookup"><span data-stu-id="0df54-127">Such entities can include files, URLs, and recipients.</span></span>  <span data-ttu-id="0df54-128">随着新警报和相关警报的触发，调查的范围可能会增加。</span><span class="sxs-lookup"><span data-stu-id="0df54-128">The investigation's scope can increase as new and related alerts are triggered.</span></span>

3. <span data-ttu-id="0df54-129">在自动调查期间和之后， [可以查看](air-view-investigation-results.md) 详细信息和结果。</span><span class="sxs-lookup"><span data-stu-id="0df54-129">During and after an automated investigation, [details and results](air-view-investigation-results.md) are available to view.</span></span> <span data-ttu-id="0df54-130">结果 [包括可](air-remediation-actions.md) 采取的建议操作，以响应和修正发现的任何威胁。</span><span class="sxs-lookup"><span data-stu-id="0df54-130">Results include [recommended actions](air-remediation-actions.md) that can be taken to respond to and remediate any threats that were found.</span></span> <span data-ttu-id="0df54-131">此外，还有 [一个可](air-view-investigation-results.md#playbook-log) 跟踪所有调查活动的手册日志。</span><span class="sxs-lookup"><span data-stu-id="0df54-131">In addition, a [playbook log](air-view-investigation-results.md#playbook-log) is available that tracks all investigation activity.</span></span>

4. <span data-ttu-id="0df54-132">安全运营团队会审阅 [测试结果和建议](air-view-investigation-results.md)，并 [批准或拒绝修正操作](air-review-approve-pending-completed-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="0df54-132">Your security operations team reviews the [investigation results and recommendations](air-view-investigation-results.md), and [approves or rejects remediation actions](air-review-approve-pending-completed-actions.md).</span></span>

5. <span data-ttu-id="0df54-133">随着挂起的修正操作得到批准 (或拒绝) ，自动调查将完成。</span><span class="sxs-lookup"><span data-stu-id="0df54-133">As pending remediation actions are approved (or rejected), the automated investigation completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0df54-134">在 Microsoft Defender for Office 365 中，不会自动执行任何修正操作。</span><span class="sxs-lookup"><span data-stu-id="0df54-134">In Microsoft Defender for Office 365, no remediation actions are taken automatically.</span></span> <span data-ttu-id="0df54-135">只有在组织的安全团队批准后，才会执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="0df54-135">Remediation actions are taken only upon approval by your organization's security team.</span></span>
>
> <span data-ttu-id="0df54-136">AIR 功能通过确定修正操作并提供做出明智决定所需的详细信息来节省安全运营团队的时间。</span><span class="sxs-lookup"><span data-stu-id="0df54-136">AIR capabilities save your security operations team time by identifying remediation actions and providing the details needed to make an informed decision.</span></span>

<span data-ttu-id="0df54-137">在每个自动调查期间和之后，安全运营团队可以：</span><span class="sxs-lookup"><span data-stu-id="0df54-137">During and after each automated investigation, your security operations team can:</span></span>

- [<span data-ttu-id="0df54-138">查看与调查相关的警报的详细信息</span><span class="sxs-lookup"><span data-stu-id="0df54-138">View details about an alert related to an investigation</span></span>](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [<span data-ttu-id="0df54-139">查看调查的结果详细信息</span><span class="sxs-lookup"><span data-stu-id="0df54-139">View the results details of an investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="0df54-140">查看和批准调查后的操作</span><span class="sxs-lookup"><span data-stu-id="0df54-140">Review and approve actions as a result of an investigation</span></span>](air-review-approve-pending-completed-actions.md)

> [!TIP]
> <span data-ttu-id="0df54-141">有关更详细的概述，请参阅 [AIR 的工作原理](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="0df54-141">For a more detailed overview, see [How AIR works](automated-investigation-response-office.md).</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="0df54-142">如何获取 AIR</span><span class="sxs-lookup"><span data-stu-id="0df54-142">How to get AIR</span></span>

<span data-ttu-id="0df54-143">AIR 功能包含在 [Microsoft Defender for Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)中，但已配置策略和警报。</span><span class="sxs-lookup"><span data-stu-id="0df54-143">AIR capabilities are included in [Microsoft Defender for Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2), provided your policies and alerts are configured.</span></span> <span data-ttu-id="0df54-144">若要获得一些帮助，请按照"防止威胁"中的指南[](protect-against-threats.md)设置或配置以下保护设置：</span><span class="sxs-lookup"><span data-stu-id="0df54-144">If you would like some help with this, follow the guidance in [Protect against threats](protect-against-threats.md) to set up or configure the following protection settings:</span></span>

1. <span data-ttu-id="0df54-145">[审核日志记录](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (应打开) </span><span class="sxs-lookup"><span data-stu-id="0df54-145">[Audit logging](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (should be turned on)</span></span>

2. [<span data-ttu-id="0df54-146">反恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="0df54-146">Antimalware policies</span></span>](protect-against-threats.md#part-1---anti-malware-protection)

3. [<span data-ttu-id="0df54-147">反Phishing protection</span><span class="sxs-lookup"><span data-stu-id="0df54-147">Antiphishing protection</span></span>](protect-against-threats.md#part-2---anti-phishing-protection)

4. <span data-ttu-id="0df54-148">[反垃圾邮件保护](protect-against-threats.md#part-3---anti-spam-protection)。</span><span class="sxs-lookup"><span data-stu-id="0df54-148">[Antispam protection](protect-against-threats.md#part-3---anti-spam-protection).</span></span>

5. <span data-ttu-id="0df54-149">[安全链接和安全附件](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="0df54-149">[Safe Links and Safe Attachments](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).</span></span>

6. <span data-ttu-id="0df54-150">[SharePoint、OneDrive](protect-against-threats.md#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)和 Microsoft Teams 的安全附件。</span><span class="sxs-lookup"><span data-stu-id="0df54-150">[Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](protect-against-threats.md#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).</span></span>

7. <span data-ttu-id="0df54-151">[零时差自动清除电子邮件](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)。</span><span class="sxs-lookup"><span data-stu-id="0df54-151">[Zero-hour auto purge for email](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop).</span></span>

<span data-ttu-id="0df54-152">此外，请确保 [查看组织的](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)警报策略，尤其是威胁管理 [类别中的默认策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)。</span><span class="sxs-lookup"><span data-stu-id="0df54-152">In addition, make sure to [review your organization's alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), especially the [default policies in the Threat management category](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies).</span></span>

## <a name="which-alert-policies-trigger-automated-investigations"></a><span data-ttu-id="0df54-153">哪些警报策略会触发自动调查？</span><span class="sxs-lookup"><span data-stu-id="0df54-153">Which alert policies trigger automated investigations?</span></span>

<span data-ttu-id="0df54-154">Microsoft 365 提供了许多内置警报策略，可帮助识别 Exchange 管理员权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。</span><span class="sxs-lookup"><span data-stu-id="0df54-154">Microsoft 365 provides many built-in alert policies that help identify Exchange admin permissions abuse, malware activity, potential external and internal threats, and information governance risks.</span></span> <span data-ttu-id="0df54-155">一些 [默认警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 可以触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="0df54-155">Several of the [default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) can trigger automated investigations.</span></span> <span data-ttu-id="0df54-156">下表介绍了触发自动调查的警报、Microsoft 365 安全中心中警报的严重性以及如何生成这些警报：</span><span class="sxs-lookup"><span data-stu-id="0df54-156">The following table describes the alerts that trigger automated investigations, their severity in the Microsoft 365 security center, and how they're generated:</span></span>

|<span data-ttu-id="0df54-157">警报</span><span class="sxs-lookup"><span data-stu-id="0df54-157">Alert</span></span>|<span data-ttu-id="0df54-158">Severity</span><span class="sxs-lookup"><span data-stu-id="0df54-158">Severity</span></span>|<span data-ttu-id="0df54-159">如何生成警报</span><span class="sxs-lookup"><span data-stu-id="0df54-159">How the alert is generated</span></span>|
|---|---|---|
|<span data-ttu-id="0df54-160">检测到潜在恶意 URL 单击</span><span class="sxs-lookup"><span data-stu-id="0df54-160">A potentially malicious URL click was detected</span></span>|<span data-ttu-id="0df54-161">**High**</span><span class="sxs-lookup"><span data-stu-id="0df54-161">**High**</span></span>|<span data-ttu-id="0df54-162">发生以下任一情况时，将生成此警报：</span><span class="sxs-lookup"><span data-stu-id="0df54-162">This alert is generated when any of the following occurs:</span></span> <ul><li><span data-ttu-id="0df54-163">组织中受安全 [链接](atp-safe-links.md) 保护的用户单击恶意链接</span><span class="sxs-lookup"><span data-stu-id="0df54-163">A user protected by [Safe Links](atp-safe-links.md) in your organization clicks a malicious link</span></span></li><li><span data-ttu-id="0df54-164">URL 裁定更改由 Microsoft Defender for Office 365 标识</span><span class="sxs-lookup"><span data-stu-id="0df54-164">Verdict changes for URLs are identified by Microsoft Defender for Office 365</span></span></li><li><span data-ttu-id="0df54-165">根据组织的安全链接策略 (，用户会覆盖安全链接[警告) 。](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0df54-165">Users override Safe Links warning pages (based on your organization's [Safe Links policy](set-up-atp-safe-links-policies.md)).</span></span></li></ul> <p> <span data-ttu-id="0df54-166">有关触发此警报的事件详细信息，请参阅["设置安全链接策略"。](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0df54-166">For more information on events that trigger this alert, see [Set up Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>|
|<span data-ttu-id="0df54-167">用户将电子邮件报告为恶意软件或网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="0df54-167">An email message is reported by a user as malware or phish</span></span>|<span data-ttu-id="0df54-168">**信息**</span><span class="sxs-lookup"><span data-stu-id="0df54-168">**Informational**</span></span>|<span data-ttu-id="0df54-169">当组织的用户使用报告邮件外接程序将邮件报告为网络钓鱼电子邮件时， [将生成此警报](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="0df54-169">This alert is generated when users in your organization report messages as phishing email using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>|
|<span data-ttu-id="0df54-170">包含恶意软件的电子邮件在传递后被删除</span><span class="sxs-lookup"><span data-stu-id="0df54-170">Email messages containing malware are removed after delivery</span></span>|<span data-ttu-id="0df54-171">**信息**</span><span class="sxs-lookup"><span data-stu-id="0df54-171">**Informational**</span></span>|<span data-ttu-id="0df54-172">当包含恶意软件的任何电子邮件传递到您组织的邮箱时，将生成此警报。</span><span class="sxs-lookup"><span data-stu-id="0df54-172">This alert is generated when any email messages containing malware are delivered to mailboxes in your organization.</span></span> <span data-ttu-id="0df54-173">如果发生此事件，Microsoft 使用零时差自动清除从 Exchange Online 邮箱中删除 [受感染的邮件](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="0df54-173">If this event occurs, Microsoft removes the infected messages from Exchange Online mailboxes using [Zero-hour auto purge](zero-hour-auto-purge.md).</span></span>|
|<span data-ttu-id="0df54-174">包含网络钓鱼 URL 的电子邮件在传递后被删除</span><span class="sxs-lookup"><span data-stu-id="0df54-174">Email messages containing phish URLs are removed after delivery</span></span>|<span data-ttu-id="0df54-175">**信息**</span><span class="sxs-lookup"><span data-stu-id="0df54-175">**Informational**</span></span>|<span data-ttu-id="0df54-176">当包含网络钓鱼的任何邮件传递到您组织的邮箱时，将生成此警报。</span><span class="sxs-lookup"><span data-stu-id="0df54-176">This alert is generated when any messages containing phish are delivered to mailboxes in your organization.</span></span> <span data-ttu-id="0df54-177">如果发生此事件，Microsoft 使用零时差自动清除从 Exchange Online 邮箱中删除 [受感染的邮件](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="0df54-177">If this event occurs, Microsoft removes the infected messages from Exchange Online mailboxes using [Zero-hour auto purge](zero-hour-auto-purge.md).</span></span>|
|<span data-ttu-id="0df54-178">检测到可疑的电子邮件发送模式</span><span class="sxs-lookup"><span data-stu-id="0df54-178">Suspicious email sending patterns are detected</span></span>|<span data-ttu-id="0df54-179">**Medium**</span><span class="sxs-lookup"><span data-stu-id="0df54-179">**Medium**</span></span>|<span data-ttu-id="0df54-180">当组织中有人已发送可疑电子邮件，并且存在被限制发送电子邮件的风险时，将生成此警报。</span><span class="sxs-lookup"><span data-stu-id="0df54-180">This alert is generated when someone in your organization has sent suspicious email and is at risk of being restricted from sending email.</span></span> <span data-ttu-id="0df54-181">这是一个行为的早期警告，可能指示帐户受到威胁，但不够严重，无法限制用户。</span><span class="sxs-lookup"><span data-stu-id="0df54-181">This is an early warning for behavior that might indicate that the account is compromised, but not severe enough to restrict the user.</span></span> <p> <span data-ttu-id="0df54-182">尽管这种情况很少见，但此策略生成的警报可能是异常情况。</span><span class="sxs-lookup"><span data-stu-id="0df54-182">Although it's rare, an alert generated by this policy may be an anomaly.</span></span> <span data-ttu-id="0df54-183">但是，检查用户帐户是否遭到入侵 [是一](responding-to-a-compromised-email-account.md)个好主意。</span><span class="sxs-lookup"><span data-stu-id="0df54-183">However, it's a good idea to [check whether the user account is compromised](responding-to-a-compromised-email-account.md).</span></span>|
|<span data-ttu-id="0df54-184">用户被限制发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="0df54-184">A user is restricted from sending email</span></span>|<span data-ttu-id="0df54-185">**High**</span><span class="sxs-lookup"><span data-stu-id="0df54-185">**High**</span></span>|<span data-ttu-id="0df54-186">当组织中有人被限制发送出站邮件时，将生成此警报。</span><span class="sxs-lookup"><span data-stu-id="0df54-186">This alert is generated when someone in your organization is restricted from sending outbound mail.</span></span> <span data-ttu-id="0df54-187">这通常会导致电子邮件帐户 [遭到入侵](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="0df54-187">This typically results when an [email account is compromised](responding-to-a-compromised-email-account.md).</span></span> <p> <span data-ttu-id="0df54-188">有关受限用户详细信息，请参阅 Microsoft [365](removing-user-from-restricted-users-portal-after-spam.md)中的"从受限用户"门户删除被阻止的用户。</span><span class="sxs-lookup"><span data-stu-id="0df54-188">For more information about restricted users, see [Remove blocked users from the Restricted Users portal in Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md).</span></span>|
|

> [!TIP]
> <span data-ttu-id="0df54-189">若要了解有关警报策略或编辑默认设置的信息，请参阅 Microsoft [365 合规中心](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)中的警报策略。</span><span class="sxs-lookup"><span data-stu-id="0df54-189">To learn more about alert policies or edit the default settings, see [Alert policies in the Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).</span></span>

## <a name="required-permissions-to-use-air-capabilities"></a><span data-ttu-id="0df54-190">使用 AIR 功能所需的权限</span><span class="sxs-lookup"><span data-stu-id="0df54-190">Required permissions to use AIR capabilities</span></span>

<span data-ttu-id="0df54-191">权限通过某些角色授予，如下表中所述的角色：</span><span class="sxs-lookup"><span data-stu-id="0df54-191">Permissions are granted through certain roles, such as those that are described in the following table:</span></span>

|<span data-ttu-id="0df54-192">任务</span><span class="sxs-lookup"><span data-stu-id="0df54-192">Task</span></span>|<span data-ttu-id="0df54-193">需要 (角色) 角色</span><span class="sxs-lookup"><span data-stu-id="0df54-193">Role(s) required</span></span>|
|---|---|
|<span data-ttu-id="0df54-194">设置 AIR 功能</span><span class="sxs-lookup"><span data-stu-id="0df54-194">Set up AIR features</span></span>|<span data-ttu-id="0df54-195">下列角色之一：</span><span class="sxs-lookup"><span data-stu-id="0df54-195">One of the following roles:</span></span> <ul><li><span data-ttu-id="0df54-196">全局管理员</span><span class="sxs-lookup"><span data-stu-id="0df54-196">Global Administrator</span></span></li><li><span data-ttu-id="0df54-197">安全管理员</span><span class="sxs-lookup"><span data-stu-id="0df54-197">Security Administrator</span></span></li></ul> <p> <span data-ttu-id="0df54-198">这些角色可以在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或安全与合规中心& [分配](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0df54-198">These roles can be assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>|
|<span data-ttu-id="0df54-199">启动自动调查</span><span class="sxs-lookup"><span data-stu-id="0df54-199">Start an automated investigation</span></span> <p> <span data-ttu-id="0df54-200">--- 或 ---</span><span class="sxs-lookup"><span data-stu-id="0df54-200">--- or ---</span></span> <p> <span data-ttu-id="0df54-201">批准或拒绝建议的操作</span><span class="sxs-lookup"><span data-stu-id="0df54-201">Approve or reject recommended actions</span></span>|<span data-ttu-id="0df54-202">在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 或安全与合规中心& [角色之一](permissions-in-the-security-and-compliance-center.md)：</span><span class="sxs-lookup"><span data-stu-id="0df54-202">One of the following roles, assigned in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) or in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md):</span></span> <ul><li><span data-ttu-id="0df54-203">全局管理员</span><span class="sxs-lookup"><span data-stu-id="0df54-203">Global Administrator</span></span></li><li><span data-ttu-id="0df54-204">安全管理员</span><span class="sxs-lookup"><span data-stu-id="0df54-204">Security Administrator</span></span></li><li><span data-ttu-id="0df54-205">安全读取者</span><span class="sxs-lookup"><span data-stu-id="0df54-205">Security Reader</span></span> <br> <span data-ttu-id="0df54-206">--- 和 ---</span><span class="sxs-lookup"><span data-stu-id="0df54-206">--- and ---</span></span> </li><li><span data-ttu-id="0df54-207">搜索和 (此角色仅在安全与合规中心& [分配](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0df54-207">Search and Purge (this role is assigned only in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="0df54-208">您可能必须在那里创建一个新角色组，然后向该新角色组添加搜索和清除角色。</span><span class="sxs-lookup"><span data-stu-id="0df54-208">You might have to create a new role group there and add the Search and Purge role to that new role group.</span></span></li></ul>|
|

## <a name="required-licenses"></a><span data-ttu-id="0df54-209">所需的许可证</span><span class="sxs-lookup"><span data-stu-id="0df54-209">Required licenses</span></span>

<span data-ttu-id="0df54-210">[Microsoft Defender for Office 365 计划 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 许可证应分配给：</span><span class="sxs-lookup"><span data-stu-id="0df54-210">[Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) licenses should be assigned to:</span></span>

- <span data-ttu-id="0df54-211">安全管理员 (全局管理员) </span><span class="sxs-lookup"><span data-stu-id="0df54-211">Security administrators (including global administrators)</span></span>
- <span data-ttu-id="0df54-212">组织的安全运营团队 (包括安全读者和具有"搜索和清除"角色) </span><span class="sxs-lookup"><span data-stu-id="0df54-212">Your organization's security operations team (including security readers and those with the **Search and Purge** role)</span></span>
- <span data-ttu-id="0df54-213">最终用户</span><span class="sxs-lookup"><span data-stu-id="0df54-213">End users</span></span>

## <a name="next-steps"></a><span data-ttu-id="0df54-214">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0df54-214">Next steps</span></span>

- [<span data-ttu-id="0df54-215">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="0df54-215">See details and results of an automated investigation</span></span>](air-view-investigation-results.md#view-details-of-an-investigation)

- [<span data-ttu-id="0df54-216">审阅和批准挂起的操作</span><span class="sxs-lookup"><span data-stu-id="0df54-216">Review and approve pending actions</span></span>](air-remediation-actions.md)

## <a name="see-also"></a><span data-ttu-id="0df54-217">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0df54-217">See also</span></span>

- [<span data-ttu-id="0df54-218">Microsoft Defender for Endpoint 中的自动调查和修正</span><span class="sxs-lookup"><span data-stu-id="0df54-218">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="0df54-219">Microsoft 365 Defender 中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="0df54-219">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
