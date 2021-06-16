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
description: 了解如何使用威胁资源管理器和实时检测报告来调查和响应 Microsoft 365 Defender 门户中的威胁。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1c79cc717a2dbe345627f99830590c674fa02f09
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929610"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="5cf0b-103">威胁资源管理器中的视图和实时检测</span><span class="sxs-lookup"><span data-stu-id="5cf0b-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5cf0b-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="5cf0b-104">**Applies to**</span></span>
- [<span data-ttu-id="5cf0b-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="5cf0b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5cf0b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5cf0b-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


![威胁资源管理器](../../media/explorer.png)

<span data-ttu-id="5cf0b-108">[威胁](threat-explorer.md) (和实时检测报告) 是一款功能强大的近实时工具，可帮助安全运营团队调查和响应 Microsoft 365 Defender 门户中的威胁。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="5cf0b-109">Explorer (和实时检测报告) 显示有关 Office 365 中电子邮件和文件中可疑恶意软件和网络钓鱼的信息，以及组织面临的其他安全威胁和风险。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="5cf0b-110">如果你有[Microsoft Defender for Office 365](defender-for-office-365.md)计划 2，则你有资源管理器。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-110">If you have [Microsoft Defender for Office 365](defender-for-office-365.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="5cf0b-111">如果你有 Microsoft Defender for Office 365计划 1，则你有实时检测。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="5cf0b-112">首次打开浏览器 (或实时检测报告) ，默认视图会显示过去 7 天内的电子邮件恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="5cf0b-113">此报告还可以显示 Microsoft Defender 进行Office 365检测，例如由 保险箱[链接](safe-links.md)检测到的恶意 URL，以及由"附件"保险箱[恶意文件](safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](safe-links.md), and malicious files detected by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="5cf0b-114">此报告可修改为显示过去 30 天内使用 Microsoft Defender (P2 付费订阅Office 365的数据) 。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="5cf0b-115">试用版订阅仅包含过去七天的数据。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="5cf0b-116">订阅</span><span class="sxs-lookup"><span data-stu-id="5cf0b-116">Subscription</span></span>|<span data-ttu-id="5cf0b-117">实用工具</span><span class="sxs-lookup"><span data-stu-id="5cf0b-117">Utility</span></span>|<span data-ttu-id="5cf0b-118">数据天数</span><span class="sxs-lookup"><span data-stu-id="5cf0b-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="5cf0b-119">Microsoft Defender for Office 365 P1 试用版</span><span class="sxs-lookup"><span data-stu-id="5cf0b-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="5cf0b-120">实时检测</span><span class="sxs-lookup"><span data-stu-id="5cf0b-120">Real-time detections</span></span>|<span data-ttu-id="5cf0b-121">7 </span><span class="sxs-lookup"><span data-stu-id="5cf0b-121">7</span></span>|
|<span data-ttu-id="5cf0b-122">Microsoft Defender for Office 365 P1 付费</span><span class="sxs-lookup"><span data-stu-id="5cf0b-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="5cf0b-123">实时检测</span><span class="sxs-lookup"><span data-stu-id="5cf0b-123">Real-time detections</span></span>|<span data-ttu-id="5cf0b-124">30</span><span class="sxs-lookup"><span data-stu-id="5cf0b-124">30</span></span>|
|<span data-ttu-id="5cf0b-125">Microsoft Defender for Office 365 P1 付费测试 Defender Office 365 P2 试用版</span><span class="sxs-lookup"><span data-stu-id="5cf0b-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="5cf0b-126">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="5cf0b-126">Threat Explorer</span></span>|<span data-ttu-id="5cf0b-127">7 </span><span class="sxs-lookup"><span data-stu-id="5cf0b-127">7</span></span>|
|<span data-ttu-id="5cf0b-128">Microsoft Defender for Office 365 P2 试用版</span><span class="sxs-lookup"><span data-stu-id="5cf0b-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="5cf0b-129">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="5cf0b-129">Threat Explorer</span></span>|<span data-ttu-id="5cf0b-130">7 </span><span class="sxs-lookup"><span data-stu-id="5cf0b-130">7</span></span>|
|<span data-ttu-id="5cf0b-131">Microsoft Defender for Office 365 P2 付费</span><span class="sxs-lookup"><span data-stu-id="5cf0b-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="5cf0b-132">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="5cf0b-132">Threat Explorer</span></span>|<span data-ttu-id="5cf0b-133">30</span><span class="sxs-lookup"><span data-stu-id="5cf0b-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="5cf0b-134">我们即将扩展 Explorer (实时检测，) 试用租户的数据保留和搜索限制从 7 天扩展到 30 天。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="5cf0b-135">此更改作为第 70544 号路线图项的一部分进行跟踪，当前处于推出阶段。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="5cf0b-136">使用 **"视图** "菜单更改显示的信息。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="5cf0b-137">工具提示可帮助您确定要使用哪个视图。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-137">Tooltips help you determine which view to use.</span></span>

![威胁资源管理器视图菜单](../../media/all-email.png)

<span data-ttu-id="5cf0b-139">选择视图后，可以应用筛选器并设置查询以执行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="5cf0b-140">以下各节简要概述了资源管理器中提供的各种视图 (或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="5cf0b-141">电子邮件>恶意软件</span><span class="sxs-lookup"><span data-stu-id="5cf0b-141">Email > Malware</span></span>

<span data-ttu-id="5cf0b-142">若要查看此报告，在资源管理器 (或实时检测中，) **查看** \> **电子邮件** \> **恶意软件"。**</span><span class="sxs-lookup"><span data-stu-id="5cf0b-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="5cf0b-143">此视图显示有关被标识为包含恶意软件的电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-143">This view shows information about email messages that were identified as containing malware.</span></span>

![查看有关标识为恶意软件的电子邮件的数据](../../media/detection-technology.png)

<span data-ttu-id="5cf0b-145">单击 **"** 发件人"打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="5cf0b-146">使用此列表按发件人、收件人、发件人域、主题、检测技术、保护状态等查看数据。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="5cf0b-147">例如，若要了解对检测到的电子邮件采取的操作，请选择 **列表中的"保护** 状态"。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="5cf0b-148">选择一个选项，然后单击"刷新"按钮以将筛选器应用到报表。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![威胁资源管理器的威胁防护状态选项](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="5cf0b-150">在图表下方，查看有关特定消息的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="5cf0b-151">当您在列表中选择一个项目时，将打开一个飞出窗格，您可以在其中了解有关所选项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![已打开飞出的威胁资源管理器](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="5cf0b-153">电子邮件>钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="5cf0b-153">Email > Phish</span></span>

<span data-ttu-id="5cf0b-154">若要查看此报告，在 Explorer (或实时检测中，) **查看** \> **电子邮件** \> **钓鱼邮件**"。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="5cf0b-155">此视图显示标识为网络钓鱼尝试的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-155">This view shows email messages identified as phishing attempts.</span></span>

![查看有关标识为网络钓鱼尝试的电子邮件的数据](../../media/phish.png)

<span data-ttu-id="5cf0b-157">单击 **"** 发件人"打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="5cf0b-158">使用此列表按发件人、收件人、发件人域、发件人 IP、URL 域、单击裁定等查看数据。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="5cf0b-159">例如，若要了解用户单击标识为网络钓鱼尝试的 URL 时采取的操作，请选择列表中的"单击裁定"，选择一个或多个选项，然后单击"刷新"按钮。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![单击钓鱼报告裁定选项](../../media/click-verdict.png)

<span data-ttu-id="5cf0b-161">在图表下方，查看有关特定邮件、URL 单击、URL 和电子邮件来源的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![电子邮件中检测为网络钓鱼的 URL](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="5cf0b-163">当您在列表中选择一个项目（如检测到的 URL）时，将打开一个飞出窗格，您可以在其中了解有关所选项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![有关检测到的 URL 的详细信息](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="5cf0b-165">电子邮件>提交</span><span class="sxs-lookup"><span data-stu-id="5cf0b-165">Email > Submissions</span></span>

<span data-ttu-id="5cf0b-166">若要查看此报告，在资源管理器 (或实时检测中，) **查看** \> **电子邮件** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="5cf0b-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="5cf0b-167">此视图显示用户报告为垃圾邮件、非垃圾邮件或钓鱼电子邮件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![用户报告的电子邮件](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="5cf0b-169">单击 **"** 发件人"打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="5cf0b-170">使用此列表可查看发件人、收件人、报告类型 (用户确定电子邮件是垃圾邮件、垃圾邮件或网络钓鱼邮件) 等。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="5cf0b-171">例如，若要查看有关报告为网络钓鱼尝试的电子邮件的信息，请单击"发件人报告类型"，选择"网络钓鱼"， \> 然后单击"刷新"按钮。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![为"报告类型"筛选器选择的网络钓鱼](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="5cf0b-173">在图表下方，查看有关特定电子邮件（如主题行、发件人 IP 地址、将邮件报告为垃圾邮件、非垃圾邮件或网络钓鱼的用户等）的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![报告为网络钓鱼尝试的邮件](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="5cf0b-175">选择列表中的某个项以查看其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="5cf0b-176">电子邮件>所有电子邮件</span><span class="sxs-lookup"><span data-stu-id="5cf0b-176">Email > All email</span></span>

<span data-ttu-id="5cf0b-177">若要查看此报告，在资源管理器中，选择 **查看** \> **电子邮件** \> **所有邮件**。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="5cf0b-178">此视图显示电子邮件活动的全视图，包括由于网络钓鱼或恶意软件而标识为恶意的电子邮件，以及所有非恶意 (电子邮件、垃圾邮件和批量邮件) 。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="5cf0b-179">如果收到读取要显示 **的数据** 过多的错误，请添加筛选器，如有必要，缩小正在查看的日期范围。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="5cf0b-180">若要应用筛选器，请选择" **发件人**"，选择列表中的某个项目，然后单击"刷新"按钮。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="5cf0b-181">在我们的示例中，我们使用了 **检测** 技术作为筛选器 (提供了多个可用的) 。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="5cf0b-182">查看发件人、发件人的域、收件人、主题、附件文件名、恶意软件系列、 (威胁防护功能和策略在 Office 365) 中采取的保护状态 (操作、检测技术 (检测恶意软件) 等。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![通过检测技术查看有关检测到的电子邮件的数据](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="5cf0b-184">在图表下方，查看有关特定电子邮件的更多详细信息，如主题行、收件人、发件人、状态等。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="5cf0b-185">恶意软件>内容</span><span class="sxs-lookup"><span data-stu-id="5cf0b-185">Content > Malware</span></span>

<span data-ttu-id="5cf0b-186">若要查看此报告，在资源管理器 (或实时检测中，) **查看** \> **内容** \> **恶意软件"。**</span><span class="sxs-lookup"><span data-stu-id="5cf0b-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="5cf0b-187">此视图显示 Microsoft Defender 在 Office 365 Online、SharePoint 和 OneDrive for Business 中Microsoft Teams恶意[Microsoft Teams。](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="5cf0b-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="5cf0b-188">按恶意软件系列、检测技术 (检测恶意软件) ，以及工作负荷 (OneDrive、SharePoint或Teams) 。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![查看有关检测到的恶意软件的数据](../../media/malware-family.png)

<span data-ttu-id="5cf0b-190">在图表下方，查看有关特定文件的更多详细信息，例如附件文件名、工作负荷、文件大小、上次修改文件的人等。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="5cf0b-191">单击筛选功能</span><span class="sxs-lookup"><span data-stu-id="5cf0b-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="5cf0b-192">使用资源管理器 (和实时检测) ，只需单击一下即可应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="5cf0b-193">单击图例中的某个项目，该项目将成为报表的筛选器。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="5cf0b-194">例如，假设我们正在资源管理器中查看恶意软件视图：</span><span class="sxs-lookup"><span data-stu-id="5cf0b-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![转到威胁管理 \> 资源管理器](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="5cf0b-196">单击 **此图中的 ATP** 触发将产生如下所示的视图：</span><span class="sxs-lookup"><span data-stu-id="5cf0b-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![已筛选为仅显示触发Office 365 Defender 的资源管理器](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="5cf0b-198">在此视图中，我们现在查看由附件 触发保险箱[数据](safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="5cf0b-199">在图表下方，我们可以看到有关附件由"附件"检测到的特定保险箱的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![有关带检测到附件的电子邮件的特定详细信息](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="5cf0b-201">选择一个或多个项目将激活"操作"菜单，该菜单提供多个选项，供用户选择 (选择) 。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![选择项目将激活"操作"菜单](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="5cf0b-203">通过单击进行筛选并导航到特定详细信息，可以节省调查威胁的很多时间。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="5cf0b-204">查询和筛选器</span><span class="sxs-lookup"><span data-stu-id="5cf0b-204">Queries and filters</span></span>

<span data-ttu-id="5cf0b-205">Explorer (以及实时检测报告) 具有多个强大的筛选器和查询功能，可让你深入了解详细信息，例如首要目标用户、主要恶意软件系列、检测技术等。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="5cf0b-206">每类报告都提供查看和浏览数据的各种方法。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5cf0b-207">请勿在资源管理器查询栏中使用通配符（如星号或问号 (或实时) 。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="5cf0b-208">在"主题"字段中搜索电子邮件时，Explorer (或实时检测) 将执行部分匹配并产生类似于通配符搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="5cf0b-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
