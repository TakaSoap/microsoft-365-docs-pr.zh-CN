---
title: Microsoft Defender for Office 365 中的自动化调查和响应的工作原理
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
ms.date: 11/05/2020
description: 请参阅 Microsoft Defender for Office 365 中的自动化调查和响应功能的工作原理
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 039cca2f6f61d7c82f8c3e85f1fd147a68f84b68
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948429"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e2ae3-104">Microsoft Defender for Office 365 中的自动化调查和响应的工作原理</span><span class="sxs-lookup"><span data-stu-id="e2ae3-104">How automated investigation and response works in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e2ae3-105">随着安全警报的触发，安全操作团队可查看这些警报并采取措施来保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-105">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="e2ae3-106">有时，安全操作团队可能会受到触发的警报量的感觉的不知所措。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-106">Sometimes, security operations teams can feel overwhelmed by the volume of alerts that are triggered.</span></span> <span data-ttu-id="e2ae3-107">Microsoft Defender for Office 365 中的自动调查和响应 (空中) 功能可提供帮助。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-107">Automated investigation and response (AIR) capabilities in Microsoft Defender for Office 365 can help.</span></span>

<span data-ttu-id="e2ae3-108">通过 AIR，您的安全操作团队可以更高效地运行。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-108">AIR enables your security operations team to operate more efficiently and effectively.</span></span> <span data-ttu-id="e2ae3-109">空中功能包括自动调查过程，以响应目前存在的已知威胁。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-109">AIR capabilities include automated investigation processes in response to well-known threats that exist today.</span></span> <span data-ttu-id="e2ae3-110">适当的补救措施等待批准，使安全操作团队能够响应检测到的威胁。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-110">Appropriate remediation actions await approval, enabling your security operations team to respond to detected threats.</span></span>

<span data-ttu-id="e2ae3-111">本文介绍了 AIR 如何通过几个示例运行。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-111">This article describes how AIR works through several examples.</span></span> <span data-ttu-id="e2ae3-112">当您准备好开始使用 AIR 时，请参阅 [自动调查和响应威胁](office-365-air.md)。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-112">When you're ready to get started using AIR, see [Automatically investigate and respond to threats](office-365-air.md).</span></span>

- [<span data-ttu-id="e2ae3-113">示例1：用户报告的网络钓鱼邮件启动调查行动手册</span><span class="sxs-lookup"><span data-stu-id="e2ae3-113">Example 1: A user-reported phish message launches an investigation playbook</span></span>](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [<span data-ttu-id="e2ae3-114">示例2：安全管理员触发来自威胁资源管理器的调查</span><span class="sxs-lookup"><span data-stu-id="e2ae3-114">Example 2: A security administrator triggers an investigation from Threat Explorer</span></span>](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [<span data-ttu-id="e2ae3-115">示例3：安全操作团队使用 Office 365 管理活动 API 将空中与其 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="e2ae3-115">Example 3: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)


## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="e2ae3-116">示例：用户报告的网络钓鱼邮件启动调查行动手册</span><span class="sxs-lookup"><span data-stu-id="e2ae3-116">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="e2ae3-117">假定组织中的某个用户收到电子邮件，而他们认为是网络钓鱼尝试。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-117">Suppose that a user in your organization receives an email that they think is a phishing attempt.</span></span> <span data-ttu-id="e2ae3-118">经过培训的用户报告此类邮件，使用 [报告邮件加载项](enable-the-report-message-add-in.md) 将其发送到 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-118">The user, trained to report such messages, uses the [Report Message add-in](enable-the-report-message-add-in.md) to send it to Microsoft for analysis.</span></span> <span data-ttu-id="e2ae3-119">提交也会发送到您的系统，并在 " **提交** " 视图中显示 (以前称为 **用户报告** 的视图) 。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-119">The submission is also sent to your system and is visible in Explorer in the **Submissions** view (formerly referred to as the **User-reported** view).</span></span> <span data-ttu-id="e2ae3-120">此外，用户报告的消息现在会触发基于系统的信息警报，这将自动启动调查行动手册。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-120">In addition, the user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="e2ae3-121">在根调查阶段，会评估电子邮件的各个方面。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-121">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="e2ae3-122">这些方面包括：</span><span class="sxs-lookup"><span data-stu-id="e2ae3-122">These aspects include:</span></span>

- <span data-ttu-id="e2ae3-123">确定它可能属于哪种类型的威胁;</span><span class="sxs-lookup"><span data-stu-id="e2ae3-123">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="e2ae3-124">发件人数;</span><span class="sxs-lookup"><span data-stu-id="e2ae3-124">Who sent it;</span></span>
- <span data-ttu-id="e2ae3-125">电子邮件的发送位置 (发送基础结构) ;</span><span class="sxs-lookup"><span data-stu-id="e2ae3-125">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="e2ae3-126">是否已传递或阻止电子邮件的其他实例;</span><span class="sxs-lookup"><span data-stu-id="e2ae3-126">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="e2ae3-127">我们分析家中的一种评估;</span><span class="sxs-lookup"><span data-stu-id="e2ae3-127">An assessment from our analysts;</span></span>
- <span data-ttu-id="e2ae3-128">电子邮件是否与任何已知的市场活动相关联;</span><span class="sxs-lookup"><span data-stu-id="e2ae3-128">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="e2ae3-129">等等。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-129">and more.</span></span>

<span data-ttu-id="e2ae3-130">根调查完成后，行动手册提供了要对其关联的原始电子邮件和实体执行的建议操作的列表。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-130">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="e2ae3-131">接下来，执行以下几个威胁调查和搜寻步骤：</span><span class="sxs-lookup"><span data-stu-id="e2ae3-131">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="e2ae3-132">类似的电子邮件通过电子邮件群集搜索进行标识。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-132">Similar email messages are identified via email cluster searches.</span></span>
- <span data-ttu-id="e2ae3-133">该信号与其他平台（如 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)）共享。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-133">The signal is shared with other platforms, such as [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="e2ae3-134">确定是否有用户通过可疑电子邮件中的任何恶意链接单击过。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-134">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="e2ae3-135">在 Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) 和 ([Microsoft Defender for Office 365](office-365-atp.md)) 中进行检查，以查看用户是否报告了其他类似的邮件。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-135">A check is done across Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) and ([Microsoft Defender for Office 365](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="e2ae3-136">将执行检查以查看是否已泄露用户。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-136">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="e2ae3-137">此检查跨 Office 365、 [Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)和 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)之间的信号，关联任何相关的用户活动异常。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-137">This check leverages signals across Office 365, [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security), and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span>

<span data-ttu-id="e2ae3-138">在搜寻阶段，会为各种搜寻步骤分配风险和威胁。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-138">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="e2ae3-139">修正是行动手册的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-139">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="e2ae3-140">在此阶段中，将根据调查和搜寻阶段采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-140">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="e2ae3-141">示例：安全管理员触发来自威胁资源管理器的调查</span><span class="sxs-lookup"><span data-stu-id="e2ae3-141">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="e2ae3-142">除了由警报触发的自动调查之外，组织的安全操作团队还可以通过 [威胁资源管理器](threat-explorer.md)中的视图触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-142">In addition to automated investigations that are triggered by an alert, your organization's security operations team can trigger an automated investigation from a view in [Threat Explorer](threat-explorer.md).</span></span>  <span data-ttu-id="e2ae3-143">此调查还会创建一个警报，以便 Microsoft Defender 事件和外部 SIEM 工具可以查看是否触发了此调查。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-143">This investigation also creates an alert, so that Microsoft Defender Incidents and external SIEM tools can see that this investigation was triggered.</span></span> 

<span data-ttu-id="e2ae3-144">例如，假设您正在使用资源管理器中的 **恶意软件** 视图。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-144">For example, suppose that you are using the **Malware** view in Explorer.</span></span> <span data-ttu-id="e2ae3-145">使用图表下方的选项卡，选择 " **电子邮件** " 选项卡。如果选择列表中的一个或多个项目，则 " **+ 动作** " 按钮将激活。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-145">Using the tabs below the chart, you select the **Email** tab. If you select one or more items in the list, the **+ Actions** button activates.</span></span> 

![包含所选邮件的资源管理器](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="e2ae3-147">使用 " **操作** " 菜单，可以选择 **触发调查** 。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-147">Using the **Actions** menu, you can select **Trigger investigation**.</span></span>

![选定邮件的 "操作" 菜单](../../media/explorer-malwareview-selectedemails-actions.jpg)

<span data-ttu-id="e2ae3-149">与由警报触发的行动手册类似，通过资源管理器中的视图触发的自动调查包括根调查、标识和关联威胁的步骤以及缓解这些威胁的建议操作。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-149">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a><span data-ttu-id="e2ae3-150">示例：安全操作团队使用 Office 365 管理活动 API 将空中与其 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="e2ae3-150">Example: A security operations team integrates AIR with their SIEM using the Office 365 Management Activity API</span></span>

<span data-ttu-id="e2ae3-151">Microsoft Defender for Office 365 中的空中功能包括 [报告 & 详细信息](air-view-investigation-results.md) ，安全操作团队可以使用这些信息来监视和解决威胁。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-151">AIR capabilities in Microsoft Defender for Office 365 include [reports & details](air-view-investigation-results.md) that security operations teams can use to monitor and address threats.</span></span> <span data-ttu-id="e2ae3-152">但您也可以将空中功能与其他解决方案集成。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-152">But you can also integrate AIR capabilities with other solutions.</span></span> <span data-ttu-id="e2ae3-153">示例包括安全信息和事件管理 (SIEM) 系统、案例管理系统或自定义报告解决方案。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-153">Examples include a security information and event management (SIEM) system, a case management system, or a custom reporting solution.</span></span> <span data-ttu-id="e2ae3-154">这些类型的集成可以通过使用 [Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)来实现。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-154">These kinds of integrations can be done by using the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="e2ae3-155">例如，最近，一个组织为其安全操作团队设置了一种方法，以查看用户报告的已由 AIR 处理的网络钓鱼警报。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-155">For example, recently, an organization set up a way for their security operations team to view user-reported phish alerts that were already processed by AIR.</span></span> <span data-ttu-id="e2ae3-156">其解决方案将相关警报与组织的 SIEM 服务器及其事例管理系统集成在一起。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-156">Their solution integrates relevant alerts with the organization's SIEM server and their case-management system.</span></span> <span data-ttu-id="e2ae3-157">该解决方案大大减少了误报的数量，使其安全操作团队能够将他们的时间和精力集中在真正的威胁上。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-157">The solution greatly reduces the number of false positives so that their security operations team can focus their time and effort on real threats.</span></span> <span data-ttu-id="e2ae3-158">若要了解有关此自定义解决方案的详细信息，请参阅 [技术社区博客：使用 Microsoft Defender For Office 365 和 O365 管理 API 提高 SOC 的有效性](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="e2ae3-158">To learn more about this custom solution, see [Tech Community blog: Improve the Effectiveness of your SOC with Microsoft Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2ae3-159">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e2ae3-159">Next steps</span></span>

- [<span data-ttu-id="e2ae3-160">开始使用空中</span><span class="sxs-lookup"><span data-stu-id="e2ae3-160">Get started using AIR</span></span>](office-365-air.md)

- [<span data-ttu-id="e2ae3-161">访问 Microsoft 365 路线图以查看已计划和即将发布的内容</span><span class="sxs-lookup"><span data-stu-id="e2ae3-161">Visit the Microsoft 365 Roadmap to see what's planned and releasing soon</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [<span data-ttu-id="e2ae3-162">了解 Microsoft 365 Defender 中的自动化调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="e2ae3-162">Learn about automated investigation and response capabilities in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir?view=o365-worldwide&preserve-view=true)
