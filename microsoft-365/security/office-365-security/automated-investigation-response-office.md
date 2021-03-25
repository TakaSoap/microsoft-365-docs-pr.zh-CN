---
title: Microsoft Defender for Office 365 中的自动调查和响应的工作原理
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自动事件响应， 调查， 修正， 威胁防护
ms.date: 01/29/2021
description: 了解 Microsoft Defender for Office 365 中的自动调查和响应功能如何工作
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e377927156e8c98d07f4527bca09e3764bed3f74
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203224"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9d1ee-104">Microsoft Defender for Office 365 中的自动调查和响应的工作原理</span><span class="sxs-lookup"><span data-stu-id="9d1ee-104">How automated investigation and response works in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9d1ee-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="9d1ee-105">**Applies to**</span></span>
- [<span data-ttu-id="9d1ee-106">适用于 Office 365 计划 2 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9d1ee-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9d1ee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d1ee-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9d1ee-108">触发安全警报时，由安全运营团队来调查这些警报，并采取措施来保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-108">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="9d1ee-109">有时，安全运营团队可能会因触发的警报数量而感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-109">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="9d1ee-110">Microsoft Defender for Office 365 (AIR) 功能的自动调查和响应可以提供帮助。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-110">Automated investigation and response (AIR) capabilities in Microsoft Defender for Office 365 can help.</span></span>

<span data-ttu-id="9d1ee-111">AIR 使安全运营团队可以更高效地操作。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-111">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="9d1ee-112">AIR 功能包括自动调查流程，以响应当今存在的已知威胁。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-112">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="9d1ee-113">适当的修正操作等待审批，使安全运营团队能够响应检测到的威胁。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-113">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span>

<span data-ttu-id="9d1ee-114">本文介绍 AIR 如何通过几个示例工作。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-114">This article describes how AIR works through several examples.</span></span> <span data-ttu-id="9d1ee-115">当你准备好开始使用 AIR 时，请参阅自动 [调查和响应威胁](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-115">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

- [<span data-ttu-id="9d1ee-116">示例 1：用户报告的网络钓鱼邮件启动调查手册</span><span class="sxs-lookup"><span data-stu-id="9d1ee-116">Example 1: A user-reported phish message launches an investigation playbook</span></span>](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [<span data-ttu-id="9d1ee-117">示例 2：安全管理员从威胁资源管理器触发调查</span><span class="sxs-lookup"><span data-stu-id="9d1ee-117">Example 2: A security administrator triggers an investigation from Threat Explorer</span></span>](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [<span data-ttu-id="9d1ee-118">示例 3：安全运营团队使用 Office 365 管理活动 API 将 AIR 与 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="9d1ee-118">Example 3: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="9d1ee-119">示例：用户报告的钓鱼邮件启动调查手册</span><span class="sxs-lookup"><span data-stu-id="9d1ee-119">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="9d1ee-120">假设你组织的用户收到一封电子邮件，他们会认为这是网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-120">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="9d1ee-121">经过培训可报告此类邮件的用户使用报告邮件外接程序或[](enable-the-report-message-add-in.md)报告网络钓鱼外接程序将其发送到 Microsoft[](enable-the-report-phish-add-in.md)进行分析。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-121">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="9d1ee-122">提交也会发送到你的系统，并且显示在"提交"视图中的资源管理器中 (以前称为用户 **报告的视图**) 。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-122">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="9d1ee-123">此外，用户报告的消息现在触发基于系统的信息警报，该警报将自动启动调查手册。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-123">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="9d1ee-124">在根调查阶段，将评估电子邮件的各个方面。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-124">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="9d1ee-125">这些方面包括：</span><span class="sxs-lookup"><span data-stu-id="9d1ee-125">These aspects include:</span></span>

- <span data-ttu-id="9d1ee-126">确定它可能是哪种类型的威胁;</span><span class="sxs-lookup"><span data-stu-id="9d1ee-126">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="9d1ee-127">发送者;</span><span class="sxs-lookup"><span data-stu-id="9d1ee-127">Who sent it;</span></span>
- <span data-ttu-id="9d1ee-128">电子邮件从发送基础结构 (发送) ;</span><span class="sxs-lookup"><span data-stu-id="9d1ee-128">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="9d1ee-129">电子邮件的其他实例是已送达还是被阻止;</span><span class="sxs-lookup"><span data-stu-id="9d1ee-129">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="9d1ee-130">来自分析员的评估;</span><span class="sxs-lookup"><span data-stu-id="9d1ee-130">An assessment from our analysts;</span></span>
- <span data-ttu-id="9d1ee-131">电子邮件是否与任何已知市场活动相关联;</span><span class="sxs-lookup"><span data-stu-id="9d1ee-131">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="9d1ee-132">等。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-132">and more.</span></span>

<span data-ttu-id="9d1ee-133">根调查完成后，该操作手册会提供对原始电子邮件及其关联实体执行的建议操作列表。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-133">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>

<span data-ttu-id="9d1ee-134">接下来，执行多个威胁调查和搜寻步骤：</span><span class="sxs-lookup"><span data-stu-id="9d1ee-134">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="9d1ee-135">类似的电子邮件通过电子邮件群集搜索进行标识。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-135">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="9d1ee-136">信号与其他平台（如 Microsoft Defender [for Endpoint）共享](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-136">The signal is shared with other platforms, such as [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="9d1ee-137">确定任何用户是否点击了可疑电子邮件中任何恶意链接。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-137">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="9d1ee-138">检查 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 (Microsoft Defender [for Office 365](defender-for-office-365.md)) 以查看用户是否报告了任何其他类似邮件。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-138">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and ([Microsoft Defender for Office 365](defender-for-office-365.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="9d1ee-139">检查用户是否遭到入侵。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-139">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="9d1ee-140">此检查利用 Office 365、Microsoft [Cloud App Security](/cloud-app-security)和 Azure Active [Directory](/azure/active-directory)中的信号，关联任何相关的用户活动异常。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-140">This check leverages signals across Office 365, [Microsoft Cloud App Security](/cloud-app-security), and [Azure Active Directory](/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="9d1ee-141">在搜寻阶段，将风险和威胁分配给各种搜寻步骤。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-141">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>

<span data-ttu-id="9d1ee-142">修正是 Playbook 的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-142">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="9d1ee-143">在此阶段中，将基于调查和搜寻阶段执行修正步骤。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-143">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span>

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="9d1ee-144">示例：安全管理员从威胁资源管理器触发调查</span><span class="sxs-lookup"><span data-stu-id="9d1ee-144">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="9d1ee-145">除了由警报触发的自动调查之外，组织的安全运营团队还可以从威胁资源管理器 中的视图触发 [自动调查](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-145">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>  <span data-ttu-id="9d1ee-146">此调查还会创建警报，以便 Microsoft Defender 事件和外部 SIEM 工具可以看到已触发此调查。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-146">This investigation also creates an alert, so that Microsoft Defender Incidents and external SIEM tools can see that this investigation was triggered.</span></span>

<span data-ttu-id="9d1ee-147">例如，假设您使用的是资源管理器 **中的"恶意软件** "视图。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-147">For example, suppose that you are using the **Malware** view in Explorer.</span></span> <span data-ttu-id="9d1ee-148">使用图表下方的选项卡，选择" **电子邮件"** 选项卡。如果在列表中选择一个或多个项目，则 **+ 操作** 按钮将激活。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-148">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span>

![包含选定邮件的资源管理器](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="9d1ee-150">使用"**操作"** 菜单，可以选择"触发 **调查"。**</span><span class="sxs-lookup"><span data-stu-id="9d1ee-150">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![所选邮件的操作菜单](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="9d1ee-152">与警报触发的手册类似，从资源管理器中的视图触发的自动调查包括根调查、识别和关联威胁的步骤，以及缓解这些威胁的建议操作。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-152">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="9d1ee-153">示例：安全运营团队使用 Office 365 管理活动 API 将 AIR 与 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="9d1ee-153">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="9d1ee-154">Microsoft Defender for Office 365[](air-view-investigation-results.md)中的 AIR 功能包括报告&安全运营团队可用于监视和解决威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-154">AIR capabilities in Microsoft Defender for Office 365 include [reports & details](air-view-investigation-results.md) that security operations teams can use to monitor and address threats.</span></span> <span data-ttu-id="9d1ee-155">但您也可以将 AIR 功能与其他解决方案集成。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-155">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="9d1ee-156">示例包括 SIEM (安全) 、案例管理系统或自定义报告解决方案。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-156">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="9d1ee-157">可以使用 [Office 365](/office/office-365-management-api/office-365-management-activity-api-reference)管理活动 API 完成这些类型的集成。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-157">These kinds of integrations can be done by using the [Office 365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="9d1ee-158">例如，最近，组织为安全运营团队设置了一种方法，用于查看 AIR 已处理的用户报告的网络钓鱼警报。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-158">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="9d1ee-159">他们的解决方案将相关警报与组织的 SIEM 服务器及其案例管理系统集成在一起。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-159">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="9d1ee-160">该解决方案大大减少了误报数量，以便其安全运营团队可以将时间和精力集中在实际威胁上。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-160">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="9d1ee-161">若要详细了解此自定义解决方案，请参阅技术社区 [博客：使用 Microsoft Defender for Office 365 和 O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)管理 API 提高 SOC 的有效性。</span><span class="sxs-lookup"><span data-stu-id="9d1ee-161">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Microsoft Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9d1ee-162">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9d1ee-162">Next steps</span></span>

- [<span data-ttu-id="9d1ee-163">使用 AIR 入门</span><span class="sxs-lookup"><span data-stu-id="9d1ee-163">Get started using AIR</span></span>](office-365-air.md)
- [<span data-ttu-id="9d1ee-164">查看挂起或已完成的修正操作</span><span class="sxs-lookup"><span data-stu-id="9d1ee-164">View pending or completed remediation actions</span></span>](air-review-approve-pending-completed-actions.md)