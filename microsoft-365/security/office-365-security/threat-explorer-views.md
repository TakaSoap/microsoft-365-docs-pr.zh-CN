---
title: 威胁资源管理器中的视图和实时检测
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 了解如何使用威胁资源管理器和实时检测报告调查和响应安全与合规中心&威胁。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b00b78432a34ec982208586f2fe19c1588354293
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406476"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="646b7-103">威胁资源管理器中的视图和实时检测</span><span class="sxs-lookup"><span data-stu-id="646b7-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="646b7-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="646b7-104">**Applies to**</span></span>
- [<span data-ttu-id="646b7-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="646b7-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="646b7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="646b7-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


![威胁资源管理器](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="646b7-108">[威胁](threat-explorer.md) 资源管理器 (实时检测报告) 是一个功能强大的近实时工具，可帮助安全运营团队调查和响应安全与合规中心&威胁。</span><span class="sxs-lookup"><span data-stu-id="646b7-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="646b7-109">Explorer (和实时检测报告) 显示有关 Office 365 电子邮件和文件中可疑恶意软件和网络钓鱼的信息，以及组织面临的其他安全威胁和风险。</span><span class="sxs-lookup"><span data-stu-id="646b7-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="646b7-110">如果你有 [Microsoft Defender for Office 365](office-365-atp.md) 计划 2，则你有资源管理器。</span><span class="sxs-lookup"><span data-stu-id="646b7-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="646b7-111">如果你有适用于 Office 365 计划 1 的 Microsoft Defender，则具有实时检测。</span><span class="sxs-lookup"><span data-stu-id="646b7-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="646b7-112">首次打开资源管理器 (或实时检测报告) ，默认视图显示过去 7 天内的电子邮件恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="646b7-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="646b7-113">此报告还可以显示 Microsoft Defender for Office 365 检测，如安全链接[](atp-safe-links.md)检测到的恶意 URL 和安全附件检测到的[恶意文件](atp-safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="646b7-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="646b7-114">此报告可修改为显示过去 30 天的数据 (Microsoft Defender for Office 365 P2 付费订阅) 。</span><span class="sxs-lookup"><span data-stu-id="646b7-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="646b7-115">试用版订阅将仅包含过去七天的数据。</span><span class="sxs-lookup"><span data-stu-id="646b7-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="646b7-116">订阅</span><span class="sxs-lookup"><span data-stu-id="646b7-116">Subscription</span></span>|<span data-ttu-id="646b7-117">实用工具</span><span class="sxs-lookup"><span data-stu-id="646b7-117">Utility</span></span>|<span data-ttu-id="646b7-118">数据天数</span><span class="sxs-lookup"><span data-stu-id="646b7-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="646b7-119">Microsoft Defender for Office 365 P1 试用版</span><span class="sxs-lookup"><span data-stu-id="646b7-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="646b7-120">实时检测</span><span class="sxs-lookup"><span data-stu-id="646b7-120">Real-time detections</span></span>|<span data-ttu-id="646b7-121">7 </span><span class="sxs-lookup"><span data-stu-id="646b7-121">7</span></span>|
|<span data-ttu-id="646b7-122">Microsoft Defender for Office 365 P1 付费</span><span class="sxs-lookup"><span data-stu-id="646b7-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="646b7-123">实时检测</span><span class="sxs-lookup"><span data-stu-id="646b7-123">Real-time detections</span></span>|<span data-ttu-id="646b7-124">30</span><span class="sxs-lookup"><span data-stu-id="646b7-124">30</span></span>|
|<span data-ttu-id="646b7-125">Microsoft Defender for Office 365 P1 付费测试 Defender for Office 365 P2 试用版</span><span class="sxs-lookup"><span data-stu-id="646b7-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="646b7-126">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="646b7-126">Threat Explorer</span></span>|<span data-ttu-id="646b7-127">7 </span><span class="sxs-lookup"><span data-stu-id="646b7-127">7</span></span>|
|<span data-ttu-id="646b7-128">Microsoft Defender for Office 365 P2 试用版</span><span class="sxs-lookup"><span data-stu-id="646b7-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="646b7-129">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="646b7-129">Threat Explorer</span></span>|<span data-ttu-id="646b7-130">7 </span><span class="sxs-lookup"><span data-stu-id="646b7-130">7</span></span>|
|<span data-ttu-id="646b7-131">Microsoft Defender for Office 365 P2 付费</span><span class="sxs-lookup"><span data-stu-id="646b7-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="646b7-132">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="646b7-132">Threat Explorer</span></span>|<span data-ttu-id="646b7-133">30</span><span class="sxs-lookup"><span data-stu-id="646b7-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="646b7-134">我们很快就会将 Explorer (和实时检测) 试用租户的数据保留和搜索限制从 7 天扩展到 30 天。</span><span class="sxs-lookup"><span data-stu-id="646b7-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="646b7-135">此更改作为路线图项 no. 70544 的一部分进行跟踪，当前处于推出阶段。</span><span class="sxs-lookup"><span data-stu-id="646b7-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="646b7-136">使用 **"视图** "菜单更改显示的信息。</span><span class="sxs-lookup"><span data-stu-id="646b7-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="646b7-137">工具提示可帮助你确定要使用哪个视图。</span><span class="sxs-lookup"><span data-stu-id="646b7-137">Tooltips help you determine which view to use.</span></span>

![威胁资源管理器视图菜单](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="646b7-139">选择视图后，可以应用筛选器并设置查询以执行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="646b7-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="646b7-140">以下各节简要概述了资源管理器中提供的各种 (或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="646b7-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="646b7-141">电子邮件>恶意软件</span><span class="sxs-lookup"><span data-stu-id="646b7-141">Email > Malware</span></span>

<span data-ttu-id="646b7-142">若要查看此报告，在资源管理器 (或实时检测中，) **查看** \> **电子邮件** \> **恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="646b7-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="646b7-143">此视图显示有关标识为包含恶意软件的电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="646b7-143">This view shows information about email messages that were identified as containing malware.</span></span>

![查看有关标识为恶意软件的电子邮件的数据](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="646b7-145">单击 **"** 发件人"打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="646b7-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="646b7-146">使用此列表按发件人、收件人、发件人域、主题、检测技术、保护状态等查看数据。</span><span class="sxs-lookup"><span data-stu-id="646b7-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="646b7-147">例如，若要了解对检测到的电子邮件采取的操作，请选择 **列表中的"保护** 状态"。</span><span class="sxs-lookup"><span data-stu-id="646b7-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="646b7-148">选择一个选项，然后单击"刷新"按钮以将筛选器应用到报表。</span><span class="sxs-lookup"><span data-stu-id="646b7-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![威胁资源管理器的威胁防护状态选项](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="646b7-150">在图表下方，查看有关特定消息的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="646b7-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="646b7-151">在列表中选择某个项目时，将打开一个飞出窗格，您可以在其中了解有关所选项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="646b7-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![已打开飞出的威胁资源管理器](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="646b7-153">电子邮件>钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="646b7-153">Email > Phish</span></span>

<span data-ttu-id="646b7-154">若要查看此报告，在资源管理器 (或实时检测中，) **查看** \> **电子邮件** \> **钓鱼邮件**。</span><span class="sxs-lookup"><span data-stu-id="646b7-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="646b7-155">此视图显示标识为网络钓鱼尝试的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="646b7-155">This view shows email messages identified as phishing attempts.</span></span>

![查看有关标识为网络钓鱼尝试的电子邮件的数据](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="646b7-157">单击 **"** 发件人"打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="646b7-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="646b7-158">使用此列表按发件人、收件人、发件人域、发件人 IP、URL 域、单击裁定等查看数据。</span><span class="sxs-lookup"><span data-stu-id="646b7-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="646b7-159">例如，若要了解用户单击标识为网络钓鱼尝试的 URL 时采取的操作，请选择列表中的"单击裁定"，选择一个或多个选项，然后单击"刷新"按钮。</span><span class="sxs-lookup"><span data-stu-id="646b7-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![单击网络钓鱼报告裁定选项](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="646b7-161">在图表下方，查看有关特定邮件、URL 单击、URL 和电子邮件源的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="646b7-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![电子邮件中检测为网络钓鱼的 URL](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="646b7-163">在列表中选择某个项目（如检测到的 URL）时，将打开一个飞出窗格，您可以在其中了解有关所选项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="646b7-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![有关检测到的 URL 的详细信息](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="646b7-165">电子邮件>提交</span><span class="sxs-lookup"><span data-stu-id="646b7-165">Email > Submissions</span></span>

<span data-ttu-id="646b7-166">若要查看此报告，在资源管理器 (或实时检测中，) **查看** \> **电子邮件** \> **提交**。</span><span class="sxs-lookup"><span data-stu-id="646b7-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="646b7-167">此视图显示用户报告为垃圾邮件、非垃圾邮件或网络钓鱼电子邮件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="646b7-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![用户报告的电子邮件](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="646b7-169">单击 **"** 发件人"打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="646b7-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="646b7-170">使用此列表可以查看发件人、收件人、报告类型 (用户确定电子邮件是垃圾邮件、非垃圾邮件或钓鱼邮件) 等。</span><span class="sxs-lookup"><span data-stu-id="646b7-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="646b7-171">例如，若要查看有关报告为网络钓鱼尝试的电子邮件的信息，请单击"发件人报告类型"，选择"网络钓鱼"，然后单击"刷新 \> "按钮。 </span><span class="sxs-lookup"><span data-stu-id="646b7-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![为"报告类型"筛选器选择的网络钓鱼](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="646b7-173">在图表下方，查看有关特定电子邮件的更多详细信息，例如主题行、发件人的 IP 地址、将邮件报告为垃圾邮件的用户、非垃圾邮件或网络钓鱼邮件等。</span><span class="sxs-lookup"><span data-stu-id="646b7-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![报告为网络钓鱼尝试的邮件](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="646b7-175">选择列表中的某个项以查看其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="646b7-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="646b7-176">电子邮件>所有电子邮件</span><span class="sxs-lookup"><span data-stu-id="646b7-176">Email > All email</span></span>

<span data-ttu-id="646b7-177">若要查看此报告，在资源管理器中，选择 **查看** \> **电子邮件** \> **全部邮件**。</span><span class="sxs-lookup"><span data-stu-id="646b7-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="646b7-178">此视图显示电子邮件活动的全视图，包括由于网络钓鱼或恶意软件而标识为恶意的电子邮件，以及所有非恶意邮件 (普通电子邮件、垃圾邮件和批量邮件) 。</span><span class="sxs-lookup"><span data-stu-id="646b7-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="646b7-179">如果出现错误，显示的数据过多，请添加筛选器，如有必要，缩小正在查看的日期范围。</span><span class="sxs-lookup"><span data-stu-id="646b7-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="646b7-180">若要应用筛选器，请选择 **"发件人**"，选择列表中的项目，然后单击"刷新"按钮。</span><span class="sxs-lookup"><span data-stu-id="646b7-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="646b7-181">在我们的示例中，我们使用检测 **技术** 作为筛选器 (提供了多个) 。</span><span class="sxs-lookup"><span data-stu-id="646b7-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="646b7-182">按发件人、发件人的域、收件人、主题、附件文件名、恶意软件系列、Office 365) 中的威胁防护功能和策略执行的保护状态 (操作、检测技术 (如何检测) 等查看信息。</span><span class="sxs-lookup"><span data-stu-id="646b7-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![通过检测技术查看有关检测到的电子邮件的数据](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="646b7-184">在图表下方，查看有关特定电子邮件（如主题行、收件人、发件人、状态等）的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="646b7-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="646b7-185">恶意软件>内容</span><span class="sxs-lookup"><span data-stu-id="646b7-185">Content > Malware</span></span>

<span data-ttu-id="646b7-186">若要查看此报告，在资源管理器 (或实时检测中，) **查看** \> **内容** \> **恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="646b7-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="646b7-187">此视图显示 [SharePoint Online、OneDrive for Business](atp-for-spo-odb-and-teams.md)和 Microsoft Teams 中的 Microsoft Defender for Office 365 标识为恶意文件。</span><span class="sxs-lookup"><span data-stu-id="646b7-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="646b7-188">按恶意软件系列、检测技术 (恶意软件检测方法、) 和工作负载 (OneDrive、SharePoint 或 Teams) 。</span><span class="sxs-lookup"><span data-stu-id="646b7-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![查看有关检测到的恶意软件的数据](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="646b7-190">在图表下方，查看有关特定文件的更多详细信息，例如附件文件名、工作负载、文件大小、上次修改文件的人等。</span><span class="sxs-lookup"><span data-stu-id="646b7-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="646b7-191">点击筛选功能</span><span class="sxs-lookup"><span data-stu-id="646b7-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="646b7-192">使用资源管理器 (和实时检测) ，单击即可应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="646b7-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="646b7-193">单击图例中的项目，该项目将成为报表的筛选器。</span><span class="sxs-lookup"><span data-stu-id="646b7-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="646b7-194">例如，假设我们正在资源管理器中查看恶意软件视图：</span><span class="sxs-lookup"><span data-stu-id="646b7-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![转到威胁管理 \> 资源管理器](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="646b7-196">单击 **此图表中的 ATP** 触发将产生如下所示的视图：</span><span class="sxs-lookup"><span data-stu-id="646b7-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![已筛选为仅显示 Defender for Office 365 触发结果的资源管理器](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="646b7-198">在此视图中，我们现在查看由安全附件触发 [的文件的数据](atp-safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="646b7-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="646b7-199">在图表下方，我们可以看到有关具有安全附件检测到的附件的特定电子邮件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="646b7-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![有关包含检测到附件的电子邮件的具体详细信息](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="646b7-201">选择一个或多个项目将激活"操作"菜单，该菜单提供了多个选项，可以从中选择所选项目 () 。</span><span class="sxs-lookup"><span data-stu-id="646b7-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![选择项目将激活"操作"菜单](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="646b7-203">通过单击进行筛选并导航到特定详细信息，可以节省调查威胁的很多时间。</span><span class="sxs-lookup"><span data-stu-id="646b7-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="646b7-204">查询和筛选器</span><span class="sxs-lookup"><span data-stu-id="646b7-204">Queries and filters</span></span>

<span data-ttu-id="646b7-205">资源管理器 (以及实时检测报告) 具有多个功能强大的筛选器和查询功能，可让你深入了解详细信息，例如首要目标用户、主要恶意软件系列、检测技术等。</span><span class="sxs-lookup"><span data-stu-id="646b7-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="646b7-206">每类报告都提供查看和浏览数据的各种方法。</span><span class="sxs-lookup"><span data-stu-id="646b7-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="646b7-207">请勿在 Explorer (查询栏中使用通配符（如星号或问号）或) 。</span><span class="sxs-lookup"><span data-stu-id="646b7-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="646b7-208">在"主题"字段中搜索电子邮件时，Explorer (或实时检测) 将执行部分匹配并生成类似于通配符搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="646b7-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
