---
title: 威胁资源管理器和实时检测
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用浏览器门户中的资源管理器和实时检测Microsoft 365 Defender调查和响应威胁。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb72c99ae0b80c4091e79801c5515190811324a7
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "53195029"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="9318c-103">威胁资源管理器和实时检测</span><span class="sxs-lookup"><span data-stu-id="9318c-103">Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="9318c-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="9318c-104">**Applies to**</span></span>
- [<span data-ttu-id="9318c-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="9318c-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9318c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9318c-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9318c-107">如果你的组织具有适用于 Office 365 的 [Microsoft Defender，](defender-for-office-365.md)并且你拥有必要的权限，则你拥有资源管理器或实时检测 (以前是实时报告 *—* 请参阅新增功能 ！) 。 [](#new-features-in-threat-explorer-and-real-time-detections) [](#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="9318c-107">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **Real-time detections** (formerly *Real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="9318c-108">在安全&合规中心，转到"**威胁** 管理"，然后选择"**资源管理器**"_或_**"实时检测"。**</span><span class="sxs-lookup"><span data-stu-id="9318c-108">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="9318c-109">借助 Microsoft Defender for Office 365计划 2，你将看到：</span><span class="sxs-lookup"><span data-stu-id="9318c-109">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="9318c-110">借助 Microsoft Defender for Office 365 计划 1，可以看到：</span><span class="sxs-lookup"><span data-stu-id="9318c-110">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![威胁资源管理器](../../media/threatmgmt-explorer.png)|![实时检测](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="9318c-113">资源管理器或实时检测可帮助安全运营团队高效地调查和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="9318c-113">Explorer or Real-time detections helps your security operations team investigate and respond to threats efficiently.</span></span> <span data-ttu-id="9318c-114">报告类似于下图：</span><span class="sxs-lookup"><span data-stu-id="9318c-114">The report resembles the following image:</span></span>

![转到威胁管理 \> 资源管理器](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="9318c-116">通过此报告，您可以：</span><span class="sxs-lookup"><span data-stu-id="9318c-116">With this report, you can:</span></span>

- [<span data-ttu-id="9318c-117">查看由安全Microsoft 365检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="9318c-117">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="9318c-118">查看网络钓鱼 URL 并单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="9318c-118">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- <span data-ttu-id="9318c-119">[仅从 Explorer (](#start-automated-investigation-and-response) Defender for Office 365 计划 2 中的视图启动自动调查和响应) </span><span class="sxs-lookup"><span data-stu-id="9318c-119">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- [<span data-ttu-id="9318c-120">调查恶意电子邮件等</span><span class="sxs-lookup"><span data-stu-id="9318c-120">Investigate malicious email, and more</span></span>](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="9318c-121">威胁搜寻体验改进</span><span class="sxs-lookup"><span data-stu-id="9318c-121">Improvements to Threat Hunting Experience</span></span>

### <a name="introduction-of-alert-id-for-defender-for-office-365-alerts-within-explorerreal-time-detections-preview"></a><span data-ttu-id="9318c-122">在预览版中引入适用于 Office 365 警报的 Defender 警报 ID/实时 (检测) </span><span class="sxs-lookup"><span data-stu-id="9318c-122">Introduction of Alert ID for Defender for Office 365 alerts within Explorer/Real-time detections (Preview)</span></span>

<span data-ttu-id="9318c-123">今天，如果你从警报导航到威胁资源管理器，它将在资源管理器中打开筛选的视图，其中按警报策略 ID (策略 ID 筛选的视图是警报策略设置的唯一标识符) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-123">Today, if you navigate from an alert to Threat Explorer, it opens a filtered view within the Explorer, with the view filtered by Alert policy ID (policy ID being a unique identifier for an Alert policy).</span></span>
<span data-ttu-id="9318c-124">我们正在通过引入警报 ID (在威胁资源管理器和实时检测中查看) 下方的警报 ID 示例，以便查看与特定警报相关的邮件以及电子邮件数量，从而使此集成更具相关性。</span><span class="sxs-lookup"><span data-stu-id="9318c-124">We are making this integration more relevant by introducing the alert ID (see an example of alert ID below) in Threat Explorer and Real-time detections so that you see messages which are relevant to the specific alert, as well as a count of emails.</span></span> <span data-ttu-id="9318c-125">您还可以查看邮件是否属于警报，以及从该邮件导航到特定警报。</span><span class="sxs-lookup"><span data-stu-id="9318c-125">You will also be able to see if a message was part of an alert, as well as navigate from that message to the specific alert.</span></span>

<span data-ttu-id="9318c-126">查看单个警报时，警报 ID 在 URL 中可用;示例为 `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1` 。</span><span class="sxs-lookup"><span data-stu-id="9318c-126">Alert ID is available within the URL when you are viewing an individual alert; an example being `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-127">![筛选警报 ID](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-127">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-128">![详细信息中的警报 ID 飞出](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-128">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-the-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants-from-7-to-30-days-preview"></a><span data-ttu-id="9318c-129">扩展 Explorer (和实时检测) 预览版中试用版租户的数据保留和搜索限制从 7 天 (30) </span><span class="sxs-lookup"><span data-stu-id="9318c-129">Extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days (Preview)</span></span>

<span data-ttu-id="9318c-130">作为此更改的一部分，你将能够在威胁资源管理器中搜索并筛选 30 天内的电子邮件数据 (这一点比针对 Office P1 和 P2 试用租户的 Defender 前 7 天) 增加了。</span><span class="sxs-lookup"><span data-stu-id="9318c-130">As part of this change, you will be able to search for, and filter email data across 30 days (an increase from the previous 7 days) in Threat Explorer/Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span>
<span data-ttu-id="9318c-131">这不会影响 P1 和 P2/E5 客户的任何生产租户，这已具有 30 天的数据保留和搜索功能。</span><span class="sxs-lookup"><span data-stu-id="9318c-131">This does not impact any production tenants for both P1 and P2/E5 customers, which already has the 30 day data retention and search capabilities.</span></span>

### <a name="updated-limits-for-export-of-records-for-threat-explorer-preview"></a><span data-ttu-id="9318c-132">更新了威胁资源管理器预览版中导出 (限制) </span><span class="sxs-lookup"><span data-stu-id="9318c-132">Updated limits for Export of records for Threat Explorer (Preview)</span></span>

<span data-ttu-id="9318c-133">作为此更新的一部分，可以从威胁资源管理器导出的电子邮件记录的行数从 9990 增加到 200，000 条记录。</span><span class="sxs-lookup"><span data-stu-id="9318c-133">As part of this update, the number of rows for Email records that can be exported from Threat Explorer is increased from 9990 to 200,000 records.</span></span> <span data-ttu-id="9318c-134">当前可以导出的列集将保持不变，但行数将自当前限制开始增加。</span><span class="sxs-lookup"><span data-stu-id="9318c-134">The set of columns that can be exported currently will remain the same, but the number of rows will increase from the current limit.</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="9318c-135">威胁资源管理器中的标记</span><span class="sxs-lookup"><span data-stu-id="9318c-135">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="9318c-136">用户标记功能在 *预览版* 中，并非对所有人都可用，并且可能会更改。</span><span class="sxs-lookup"><span data-stu-id="9318c-136">The user tags feature is in *Preview*, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="9318c-137">有关发布计划的信息，请查看Microsoft 365路线图。</span><span class="sxs-lookup"><span data-stu-id="9318c-137">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="9318c-138">用户标记标识 Microsoft Defender for Office 365 中的特定用户组。</span><span class="sxs-lookup"><span data-stu-id="9318c-138">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9318c-139">有关标记（包括许可和配置）的信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="9318c-139">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="9318c-140">在威胁资源管理器中，可以在以下体验中查看有关用户标记的信息。</span><span class="sxs-lookup"><span data-stu-id="9318c-140">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="9318c-141">电子邮件网格视图</span><span class="sxs-lookup"><span data-stu-id="9318c-141">Email grid view</span></span>

<span data-ttu-id="9318c-142">电子邮件 **网格** 中的"标记"列包含已应用于发件人或收件人邮箱的所有标记。</span><span class="sxs-lookup"><span data-stu-id="9318c-142">The **Tags** column in the email grid contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="9318c-143">默认情况下，优先显示优先帐户等系统标记。</span><span class="sxs-lookup"><span data-stu-id="9318c-143">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-144">![电子邮件网格视图中的筛选器标记](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-144">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="9318c-145">筛选</span><span class="sxs-lookup"><span data-stu-id="9318c-145">Filtering</span></span>

<span data-ttu-id="9318c-146">可以将标记用作筛选器。</span><span class="sxs-lookup"><span data-stu-id="9318c-146">You can use tags as a filter.</span></span> <span data-ttu-id="9318c-147">仅跨优先级帐户或特定用户标记方案进行智能寻线。</span><span class="sxs-lookup"><span data-stu-id="9318c-147">Hunt just across priority accounts or specific user tags scenarios.</span></span> <span data-ttu-id="9318c-148">还可以排除具有特定标记的结果。</span><span class="sxs-lookup"><span data-stu-id="9318c-148">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="9318c-149">将此功能与其他筛选器相结合，以缩小调查范围。</span><span class="sxs-lookup"><span data-stu-id="9318c-149">Combine this functionality with other filters to narrow your scope of investigation.</span></span>

<span data-ttu-id="9318c-150">[![筛选器标记](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9318c-150">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-151">![非筛选器标记](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-151">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="9318c-152">电子邮件详细信息飞出</span><span class="sxs-lookup"><span data-stu-id="9318c-152">Email detail flyout</span></span>

<span data-ttu-id="9318c-153">若要查看发件人和收件人的单个标记，请选择主题以打开邮件详细信息飞出。</span><span class="sxs-lookup"><span data-stu-id="9318c-153">To view the individual tags for sender and recipient, select the subject to open the message details flyout.</span></span> <span data-ttu-id="9318c-154">在 **"摘要"** 选项卡上，如果电子邮件存在发件人和收件人标记，则分别显示它们。</span><span class="sxs-lookup"><span data-stu-id="9318c-154">On the **Summary** tab, the sender and recipient tags are shown separately, if they're present for an email.</span></span>
<span data-ttu-id="9318c-155">有关发件人和收件人的单个标记的信息还扩展到导出的 CSV 数据，您可以在两个单独的列中查看这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="9318c-155">The information about individual tags for sender and recipient also extends to exported CSV data, where you can see these details in two separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-156">![电子邮件详细信息标记](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-156">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="9318c-157">URL 单击飞出也显示标记信息。</span><span class="sxs-lookup"><span data-stu-id="9318c-157">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="9318c-158">若要查看它，请转到网络钓鱼或所有电子邮件视图，然后转到 **URL** 或 **URL 单击** 选项卡。选择单个 URL 飞出视图有关该 URL 的单击的其他详细信息，包括与该单击关联的标记。</span><span class="sxs-lookup"><span data-stu-id="9318c-158">To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Select an individual URL flyout to view additional details about clicks for that URL, including tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="9318c-159">更新的时间线视图</span><span class="sxs-lookup"><span data-stu-id="9318c-159">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-160">![URL 标记](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-160">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="9318c-161">观看[此视频](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="9318c-161">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a><span data-ttu-id="9318c-162">威胁搜寻体验的改进 (即将推出的) </span><span class="sxs-lookup"><span data-stu-id="9318c-162">Improvements to the threat hunting experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="9318c-163">更新了电子邮件的威胁信息</span><span class="sxs-lookup"><span data-stu-id="9318c-163">Updated threat information for emails</span></span>

<span data-ttu-id="9318c-164">我们专注于改进平台和数据质量，以提高电子邮件记录的数据准确性和一致性。</span><span class="sxs-lookup"><span data-stu-id="9318c-164">We've focused on platform and data-quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="9318c-165">改进包括将传递前和传递后信息（如作为 ZAP 过程的一部分对电子邮件执行的操作）合并到单个记录中。</span><span class="sxs-lookup"><span data-stu-id="9318c-165">Improvements include consolidation of pre-delivery and post-delivery information, such as actions executed on an email as part of the ZAP process, into a single record.</span></span> <span data-ttu-id="9318c-166">还包括垃圾邮件裁定、实体级别威胁 (例如，哪个 URL 是恶意) ，以及最新的送达位置。</span><span class="sxs-lookup"><span data-stu-id="9318c-166">Additional details like spam verdict, entity-level threats (for example, which URL was malicious), and latest delivery locations are also included.</span></span>

<span data-ttu-id="9318c-167">这些更新后，将看到每封邮件的单个条目，而不管影响邮件的不同传递后事件如何。</span><span class="sxs-lookup"><span data-stu-id="9318c-167">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that affect the message.</span></span> <span data-ttu-id="9318c-168">操作可能包括 ZAP、手动修正 (这意味着管理员操作) 、动态传递等。</span><span class="sxs-lookup"><span data-stu-id="9318c-168">Actions can include ZAP, manual remediation (which means admin action), dynamic delivery, and so on.</span></span>

<span data-ttu-id="9318c-169">除了显示恶意软件和网络钓鱼威胁之外，您还可以看到与电子邮件关联的垃圾邮件裁定。</span><span class="sxs-lookup"><span data-stu-id="9318c-169">In addition to showing malware and phishing threats, you see the spam verdict associated with an email.</span></span> <span data-ttu-id="9318c-170">在电子邮件中，查看与电子邮件关联的所有威胁以及相应的检测技术。</span><span class="sxs-lookup"><span data-stu-id="9318c-170">Within the email, see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="9318c-171">电子邮件可以具有零个、一个或多个威胁。</span><span class="sxs-lookup"><span data-stu-id="9318c-171">An email can have zero, one, or multiple threats.</span></span> <span data-ttu-id="9318c-172">你将在电子邮件飞出 **的详细信息部分看到** 当前威胁。</span><span class="sxs-lookup"><span data-stu-id="9318c-172">You'll see the current threats in the **Details** section of the email flyout.</span></span> <span data-ttu-id="9318c-173">对于恶意软件 (网络钓鱼等多个威胁) ，检测技术字段显示威胁检测映射，这是识别威胁的检测技术。</span><span class="sxs-lookup"><span data-stu-id="9318c-173">For multiple threats (such as malware and phishing), the **Detection tech** field shows the threat-detection mapping, which is the detection technology that identified the threat.</span></span>

<span data-ttu-id="9318c-174">检测技术集现在包括新的检测方法以及垃圾邮件检测技术。</span><span class="sxs-lookup"><span data-stu-id="9318c-174">The set of detection technologies now includes new detection methods, as well as spam-detection technologies.</span></span> <span data-ttu-id="9318c-175">您可以使用同一组检测技术跨恶意软件、网络钓鱼、所有电子邮件 (不同的电子邮件视图筛选) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-175">You can use the same set of detection technologies to filter the results across the different email views (Malware, Phish, All Email).</span></span>

> [!NOTE]
> <span data-ttu-id="9318c-176">裁定分析不一定与实体关联。</span><span class="sxs-lookup"><span data-stu-id="9318c-176">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="9318c-177">例如，电子邮件可能分类为网络钓鱼或垃圾邮件，但没有标记有网络钓鱼/垃圾邮件裁定的 URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-177">As an example, an email might be classified as phish or spam, but there are no URLs that are stamped with a phish/spam verdict.</span></span> <span data-ttu-id="9318c-178">这是因为在分配裁定之前，筛选器还会评估电子邮件的内容和其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="9318c-178">This is because the filters also evaluate content and other details for an email before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="9318c-179">URL 中的威胁</span><span class="sxs-lookup"><span data-stu-id="9318c-179">Threats in URLs</span></span>

<span data-ttu-id="9318c-180">现在，可以在"电子邮件"飞出"详细信息"选项卡上看到 URL **的特定** 威胁。威胁可以是 *恶意软件*、*网络钓鱼、\*\*垃圾邮件* 或 *无*。) </span><span class="sxs-lookup"><span data-stu-id="9318c-180">You can now see the specific threat for a URL on the email flyout **Details** tab. The threat can be *malware*, *phish*, *spam*, or *none*.)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-181">![URL 威胁](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-181">![URL threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="9318c-182">更新了日程表 (即将推出的) </span><span class="sxs-lookup"><span data-stu-id="9318c-182">Updated timeline view (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-183">![更新的时间线视图](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-183">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="9318c-184">时间线视图标识所有传递和传递后事件。</span><span class="sxs-lookup"><span data-stu-id="9318c-184">Timeline view identifies all delivery and post-delivery events.</span></span> <span data-ttu-id="9318c-185">它包括有关在这些事件的子集时确定的威胁的信息。</span><span class="sxs-lookup"><span data-stu-id="9318c-185">It includes information about the threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="9318c-186">时间线视图还提供了有关使用 ZAP (手动修正) 执行任何其他操作的信息，以及该操作的结果。</span><span class="sxs-lookup"><span data-stu-id="9318c-186">Timeline view also provides information about any additional action taken (such as ZAP or manual remediation), along with the result of that action.</span></span> <span data-ttu-id="9318c-187">时间线视图信息包括：</span><span class="sxs-lookup"><span data-stu-id="9318c-187">Timeline view information includes:</span></span>

- <span data-ttu-id="9318c-188">**源：** 事件的源。</span><span class="sxs-lookup"><span data-stu-id="9318c-188">**Source:** Source of the event.</span></span> <span data-ttu-id="9318c-189">它可以是管理员/系统/用户。</span><span class="sxs-lookup"><span data-stu-id="9318c-189">It can be admin/system/user.</span></span>
- <span data-ttu-id="9318c-190">**事件：** 包括顶级事件，如原始传递、手动修正、ZAP、提交和动态传递。</span><span class="sxs-lookup"><span data-stu-id="9318c-190">**Event:** Includes top-level events like original delivery, manual remediation, ZAP, submissions, and dynamic delivery.</span></span>
- <span data-ttu-id="9318c-191">**操作：** 作为 ZAP 或管理员操作一部分执行的特定 (例如，软删除) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-191">**Action:** The specific action that was taken either as part of ZAP or admin action (for example, soft delete).</span></span>
- <span data-ttu-id="9318c-192">**威胁：** 涵盖 (识别的恶意软件、网络钓鱼) 垃圾邮件威胁。</span><span class="sxs-lookup"><span data-stu-id="9318c-192">**Threats:** Covers the threats (malware, phish, spam) identified at that point of time.</span></span>
- <span data-ttu-id="9318c-193">**结果/详细信息：** 有关操作结果详细信息，例如它是否作为 ZAP/admin 操作一部分执行。</span><span class="sxs-lookup"><span data-stu-id="9318c-193">**Result/Details:** More information about the result of the action, such as whether it was performed as part of ZAP/admin action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="9318c-194">原始和最新的送达位置</span><span class="sxs-lookup"><span data-stu-id="9318c-194">Original and latest delivery location</span></span>

<span data-ttu-id="9318c-195">目前，我们在电子邮件网格和电子邮件浮出控件中显示传递位置。</span><span class="sxs-lookup"><span data-stu-id="9318c-195">Currently, we surface delivery location in the email grid and email flyout.</span></span> <span data-ttu-id="9318c-196">The **Delivery location** field is getting renamed Original delivery **_location_*_.我们将引入另一个字段 _*_最新送达位置_**。</span><span class="sxs-lookup"><span data-stu-id="9318c-196">The **Delivery location** field is getting renamed **_Original delivery location_*_. And we're introducing another field, _*_Latest delivery location_**.</span></span>

<span data-ttu-id="9318c-197">**原始送达** 位置将提供有关电子邮件最初送达位置的更多信息。</span><span class="sxs-lookup"><span data-stu-id="9318c-197">**Original delivery location** will give more information about where an email was delivered initially.</span></span> <span data-ttu-id="9318c-198">**最新的送达位置** 将说明电子邮件在系统操作（如 *ZAP）* 或管理员操作（如 *移动到已删除项目）之后登录的位置*。</span><span class="sxs-lookup"><span data-stu-id="9318c-198">**Latest delivery location** will state where an email landed after system actions like *ZAP* or admin actions like *Move to deleted items*.</span></span> <span data-ttu-id="9318c-199">最新送达位置旨在告知管理员邮件的上次已知位置传递后或任何系统/管理员操作。</span><span class="sxs-lookup"><span data-stu-id="9318c-199">Latest delivery location is intended to tell admins the message's last-known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="9318c-200">它不包括对电子邮件的任何最终用户操作。</span><span class="sxs-lookup"><span data-stu-id="9318c-200">It doesn't include any end-user actions on the email.</span></span> <span data-ttu-id="9318c-201">例如，如果用户删除了邮件或将邮件移动到 archive/pst，则邮件"传递"位置将不会更新。</span><span class="sxs-lookup"><span data-stu-id="9318c-201">For example, if a user deleted a message or moved the message to archive/pst, the message "delivery" location won't be updated.</span></span> <span data-ttu-id="9318c-202">但是，如果系统操作更新了位置 (例如 ZAP 导致电子邮件移动到隔离邮箱) ，则最新送达位置将显示为"隔离"。</span><span class="sxs-lookup"><span data-stu-id="9318c-202">But if a system action updated the location (for example, ZAP resulting in an email moving to quarantine), **Latest delivery location** would show as "quarantine."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-203">![更新的传递位置](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-203">![Updated delivery locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="9318c-204">在某些情况下，传递位置 **和\*\*\*\*传递操作** 可能显示为"未知"：</span><span class="sxs-lookup"><span data-stu-id="9318c-204">There are a few cases where **Delivery location** and **Delivery action** may show as "unknown":</span></span>
>
> - <span data-ttu-id="9318c-205">如果邮件已送达，您可能会看到"送达位置"和"送达位置"为"未知"，但收件箱规则将邮件移动到默认文件夹 (如草稿或存档) 而不是"收件箱"或"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="9318c-205">You might see **Delivery location** as "delivered" and **Delivery location** as "unknown" if the message was delivered, but an Inbox rule moved the message to a default folder (such as Draft or Archive) instead of to the Inbox or Junk Email folder.</span></span>
>
> - <span data-ttu-id="9318c-206">**如果已尝试** 执行管理/系统操作（ (ZAP) ，但未找到邮件，则最新的传递位置可能未知。</span><span class="sxs-lookup"><span data-stu-id="9318c-206">**Latest delivery location** can be unknown if an admin/system action (such as ZAP) was attempted, but the message wasn't found.</span></span> <span data-ttu-id="9318c-207">通常，该操作发生在用户移动或删除邮件之后。</span><span class="sxs-lookup"><span data-stu-id="9318c-207">Typically, the action happens after the user  moved or deleted the message.</span></span> <span data-ttu-id="9318c-208">在这种情况下，请验证 **日程表视图中的"结果/** 详细信息"列。</span><span class="sxs-lookup"><span data-stu-id="9318c-208">In such cases, verify the **Result/Details** column in timeline view.</span></span> <span data-ttu-id="9318c-209">查找"用户移动或删除的邮件"语句。</span><span class="sxs-lookup"><span data-stu-id="9318c-209">Look for the statement "Message moved or deleted by the user."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-210">![时间线的传递位置](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-210">![Delivery locations for timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="9318c-211">其他操作</span><span class="sxs-lookup"><span data-stu-id="9318c-211">Additional actions</span></span>

<span data-ttu-id="9318c-212">*在电子邮件* 传递后应用了其他操作。</span><span class="sxs-lookup"><span data-stu-id="9318c-212">*Additional actions* were applied after delivery of the email.</span></span> <span data-ttu-id="9318c-213">它们可以包括 *ZAP、 (* 管理员采取的操作（如软删除) 、动态传递和重新处理 *(）* 针对被反向检测为) 。 </span><span class="sxs-lookup"><span data-stu-id="9318c-213">They can include *ZAP*, *manual remediation* (action taken by an Admin such as soft delete), *dynamic delivery*, and *reprocessed* (for an email that was retroactively detected as good).</span></span>

> [!NOTE]
> <span data-ttu-id="9318c-214">作为挂起更改的一部分，当前在"传递操作"筛选器中显示"由 ZAP 删除"值将消失。</span><span class="sxs-lookup"><span data-stu-id="9318c-214">As part of the pending changes, the "Removed by ZAP" value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="9318c-215">你将有一种方法通过"其他操作"通过 ZAP 尝试搜索 **所有电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="9318c-215">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-216">![资源管理器中的其他操作](../../media/Additional_Actions.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-216">![Additional Actions in Explorer](../../media/Additional_Actions.png)</span></span>

### <a name="system-overrides"></a><span data-ttu-id="9318c-217">系统覆盖</span><span class="sxs-lookup"><span data-stu-id="9318c-217">System overrides</span></span>

<span data-ttu-id="9318c-218">*系统覆盖* 使您能够对邮件的预定传递位置进行例外。</span><span class="sxs-lookup"><span data-stu-id="9318c-218">*System overrides* enable you to make exceptions to the intended delivery location of a message.</span></span> <span data-ttu-id="9318c-219">根据筛选堆栈确定的威胁和其他检测，你可以覆盖系统提供的传递位置。</span><span class="sxs-lookup"><span data-stu-id="9318c-219">You override the delivery location provided by the system, based on the threats and other detections identified by the filtering stack.</span></span> <span data-ttu-id="9318c-220">可以通过租户或用户策略设置系统覆盖，以根据策略的建议传递邮件。</span><span class="sxs-lookup"><span data-stu-id="9318c-220">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="9318c-221">替代可以标识由于配置差异（例如，用户设置的发件人策略范围过宽保险箱发送恶意邮件的意外传递。</span><span class="sxs-lookup"><span data-stu-id="9318c-221">Overrides can identify unintentional delivery of malicious messages due to configurations gaps, such as an overly broad Safe Sender policy set by a user.</span></span> <span data-ttu-id="9318c-222">这些替代值可以是：</span><span class="sxs-lookup"><span data-stu-id="9318c-222">These override values can be:</span></span>

- <span data-ttu-id="9318c-223">用户策略允许：用户在邮箱级别创建策略以允许域或发件人。</span><span class="sxs-lookup"><span data-stu-id="9318c-223">Allowed by user policy: A user creates policies at the mailbox level to allows domains or senders.</span></span>

- <span data-ttu-id="9318c-224">被用户策略阻止：用户在邮件框级别创建策略以阻止域或发件人。</span><span class="sxs-lookup"><span data-stu-id="9318c-224">Blocked by user policy: A user creates policies at the mail box level to block domains or senders.</span></span>

- <span data-ttu-id="9318c-225">组织策略允许：组织的安全团队设置策略或 Exchange 邮件流规则 (也称为传输规则) ，以允许组织中的用户使用发件人和域。</span><span class="sxs-lookup"><span data-stu-id="9318c-225">Allowed by org policy: The organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="9318c-226">这适用于一组用户或整个组织。</span><span class="sxs-lookup"><span data-stu-id="9318c-226">This can be for a set of users or the entire organization.</span></span>

- <span data-ttu-id="9318c-227">被组织策略阻止：组织的安全团队设置策略或邮件流规则，以阻止组织中用户的发件人、域、邮件语言或源 IP。</span><span class="sxs-lookup"><span data-stu-id="9318c-227">Blocked by org policy: The organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="9318c-228">这可应用于一组用户或整个组织。</span><span class="sxs-lookup"><span data-stu-id="9318c-228">This can be applied to a set of users or the entire organization.</span></span>

- <span data-ttu-id="9318c-229">组织策略阻止的文件扩展名：组织的安全团队通过反恶意软件策略设置阻止文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="9318c-229">File extension blocked by org policy: An organization's security team blocks a file name extension through the anti-malware policy settings.</span></span> <span data-ttu-id="9318c-230">这些值现在将显示在电子邮件详细信息中，以帮助进行调查。</span><span class="sxs-lookup"><span data-stu-id="9318c-230">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="9318c-231">Secops 团队还可使用丰富的筛选功能筛选阻止的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="9318c-231">Secops teams can also use the rich-filtering capability to filter on blocked file extensions.</span></span>

<span data-ttu-id="9318c-232">[![资源管理器中的系统覆盖](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9318c-232">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-233">![资源管理器中的系统替代网格](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-233">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-for-the-url-and-clicks-experience"></a><span data-ttu-id="9318c-234">URL 和单击体验的改进</span><span class="sxs-lookup"><span data-stu-id="9318c-234">Improvements for the URL and clicks experience</span></span>

<span data-ttu-id="9318c-235">这些改进包括：</span><span class="sxs-lookup"><span data-stu-id="9318c-235">The improvements include:</span></span>

- <span data-ttu-id="9318c-236">显示完整的单击 URL (包括作为 URL 链接的一) **单击部分的任何** 查询参数。</span><span class="sxs-lookup"><span data-stu-id="9318c-236">Show the full clicked URL (including any query parameters that are part of the URL) in the **Clicks** section of the URL flyout.</span></span> <span data-ttu-id="9318c-237">目前，URL 域和路径显示在标题栏中。</span><span class="sxs-lookup"><span data-stu-id="9318c-237">Currently, the URL domain and path appear in the title bar.</span></span> <span data-ttu-id="9318c-238">我们将扩展该信息以显示完整 URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-238">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="9318c-239">跨 URL 筛选器 (*URL* 域与 *URL* 域和路径的修复) ：更新会影响对包含 URL/单击裁定的邮件的搜索。</span><span class="sxs-lookup"><span data-stu-id="9318c-239">Fixes across URL filters (*URL* versus *URL domain* versus *URL domain and path*): The updates affect searching for messages that contain a URL/click verdict.</span></span> <span data-ttu-id="9318c-240">我们启用了协议不可知搜索支持，因此无需使用 ，即可搜索 `http` URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-240">We enabled support for protocol-agnostic searches, so you can search for a URL without using `http`.</span></span> <span data-ttu-id="9318c-241">默认情况下，除非明确指定了其他值，否则 URL 搜索将映射到 http。</span><span class="sxs-lookup"><span data-stu-id="9318c-241">By default, the URL search maps to http, unless another value is explicitly specified.</span></span> <span data-ttu-id="9318c-242">例如：</span><span class="sxs-lookup"><span data-stu-id="9318c-242">For example:</span></span>
  - <span data-ttu-id="9318c-243">在"URL"、"URL 域"和"URL 域"和"路径"筛选器字段中使用 和 `http://` **不带前缀进行** 搜索。  </span><span class="sxs-lookup"><span data-stu-id="9318c-243">Search with and without the `http://` prefix in the **URL**, **URL Domain**, and **URL Domain and Path** filter fields.</span></span> <span data-ttu-id="9318c-244">搜索应显示相同的结果。</span><span class="sxs-lookup"><span data-stu-id="9318c-244">The searches should show the same results.</span></span>
  - <span data-ttu-id="9318c-245">在 URL `https://` 中搜索 **前缀**。</span><span class="sxs-lookup"><span data-stu-id="9318c-245">Search for the `https://` prefix in **URL**.</span></span> <span data-ttu-id="9318c-246">未指定任何值时， `http://` 将假定前缀。</span><span class="sxs-lookup"><span data-stu-id="9318c-246">When no value is specified, the `http://` prefix is assumed.</span></span>
  - <span data-ttu-id="9318c-247">`/`在 URL 路径、URL 域 **、URL** 域和路径字段的开头和结尾 **忽略**。</span><span class="sxs-lookup"><span data-stu-id="9318c-247">`/` is ignored at the beginning and end of the **URL path**, **URL Domain**, **URL domain and path** fields.</span></span> <span data-ttu-id="9318c-248">`/` 将忽略 **URL** 字段的末尾。</span><span class="sxs-lookup"><span data-stu-id="9318c-248">`/` at the end of the **URL** field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="9318c-249">网络钓鱼可信度</span><span class="sxs-lookup"><span data-stu-id="9318c-249">Phish confidence level</span></span>

<span data-ttu-id="9318c-250">网络钓鱼可信度有助于确定电子邮件被分类为"网络钓鱼"的可信度。</span><span class="sxs-lookup"><span data-stu-id="9318c-250">Phish confidence level helps identify the degree of confidence with which an email was categorized as "phish."</span></span> <span data-ttu-id="9318c-251">两个可能的值是 *High* 和 *Normal*。</span><span class="sxs-lookup"><span data-stu-id="9318c-251">The two possible values are *High* and *Normal*.</span></span> <span data-ttu-id="9318c-252">在初始阶段，此筛选器将仅在威胁资源管理器的网络钓鱼视图中可用。</span><span class="sxs-lookup"><span data-stu-id="9318c-252">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="9318c-253">[![资源管理器中的网络钓鱼可信度](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9318c-253">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="9318c-254">ZAP URL 信号</span><span class="sxs-lookup"><span data-stu-id="9318c-254">ZAP URL signal</span></span>

<span data-ttu-id="9318c-255">ZAP URL 信号通常用于 ZAP 网络钓鱼警报方案，其中电子邮件被标识为钓鱼邮件，在传递后被删除。</span><span class="sxs-lookup"><span data-stu-id="9318c-255">The ZAP URL signal is typically used for ZAP Phish alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="9318c-256">此信号将警报与资源管理器中的相应结果连接在一起。</span><span class="sxs-lookup"><span data-stu-id="9318c-256">This signal connects the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="9318c-257">它是警报的 IIC 之一。</span><span class="sxs-lookup"><span data-stu-id="9318c-257">It's one of the IOCs for the alert.</span></span>

<span data-ttu-id="9318c-258">为了改进搜寻过程，我们更新了威胁资源管理器和实时检测，使搜寻体验更加一致。</span><span class="sxs-lookup"><span data-stu-id="9318c-258">To improve the hunting process, we've updated Threat Explorer and Real-time detections to make the hunting experience more consistent.</span></span> <span data-ttu-id="9318c-259">此处概述了这些更改：</span><span class="sxs-lookup"><span data-stu-id="9318c-259">The changes are outlined here:</span></span>

- [<span data-ttu-id="9318c-260">时区改进</span><span class="sxs-lookup"><span data-stu-id="9318c-260">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="9318c-261">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="9318c-261">Update in the refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="9318c-262">要添加到筛选器的图表深化</span><span class="sxs-lookup"><span data-stu-id="9318c-262">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="9318c-263">在产品信息更新中</span><span class="sxs-lookup"><span data-stu-id="9318c-263">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="9318c-264">按用户标记筛选</span><span class="sxs-lookup"><span data-stu-id="9318c-264">Filter by user tags</span></span>

<span data-ttu-id="9318c-265">现在，你可以对系统或自定义用户标记进行排序和筛选，以快速了解威胁的范围。</span><span class="sxs-lookup"><span data-stu-id="9318c-265">You can now sort and filter on system or custom user tags to quickly grasp the scope of threats.</span></span> <span data-ttu-id="9318c-266">若要了解更多信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="9318c-266">To learn more, see [User tags](user-tags.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9318c-267">按用户标记进行筛选和排序目前处于公共预览阶段。</span><span class="sxs-lookup"><span data-stu-id="9318c-267">Filtering and sorting by user tags is currently in public preview.</span></span> <span data-ttu-id="9318c-268">此功能在商业发行之前可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="9318c-268">This functionality may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9318c-269">Microsoft 对提供的信息不做出明示或暗示的担保。</span><span class="sxs-lookup"><span data-stu-id="9318c-269">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-270">![资源管理器中的标记列](../../media/threat-explorer-tags.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-270">![Tags column in Explorer](../../media/threat-explorer-tags.png)</span></span>

### <a name="timezone-improvements"></a><span data-ttu-id="9318c-271">时区改进</span><span class="sxs-lookup"><span data-stu-id="9318c-271">Timezone improvements</span></span>

<span data-ttu-id="9318c-272">你将在门户和导出的数据中查看电子邮件记录的时区。</span><span class="sxs-lookup"><span data-stu-id="9318c-272">You'll see the time zone for the email records in the Portal as well as for Exported data.</span></span> <span data-ttu-id="9318c-273">它将在电子邮件网格、详细信息飞出控件、电子邮件时间线和类似电子邮件等体验中可见，因此电子邮件结果集清晰。</span><span class="sxs-lookup"><span data-stu-id="9318c-273">It will be visible across experiences like Email Grid, Details flyout, Email Timeline, and Similar Emails, so the time zone for the result set is clear.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-274">![在资源管理器中查看时区](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-274">![View time zone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="9318c-275">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="9318c-275">Update in the refresh process</span></span>

<span data-ttu-id="9318c-276">一些用户已评论过与自动刷新 (混淆，例如，一旦更改日期，页面就会刷新) ，并手动刷新 (筛选器) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-276">Some users have commented about confusion with automatic refresh (for example, as soon as you change the date, the page refreshes) and manual refresh (for other filters).</span></span> <span data-ttu-id="9318c-277">同样，删除筛选器也会导致自动刷新。</span><span class="sxs-lookup"><span data-stu-id="9318c-277">Similarly, removing filters leads to automatic refresh.</span></span> <span data-ttu-id="9318c-278">在修改查询时更改筛选器可能会导致搜索体验不一致。</span><span class="sxs-lookup"><span data-stu-id="9318c-278">Changing filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="9318c-279">为了解决这些问题，我们将迁移到手动筛选机制。</span><span class="sxs-lookup"><span data-stu-id="9318c-279">To resolve these issues, we're moving to a manual-filtering mechanism.</span></span>

<span data-ttu-id="9318c-280">从体验的角度来看，用户可以从筛选器集和日期) 应用和删除不同的筛选器 (范围，并选择"刷新"按钮以在定义查询后筛选结果。</span><span class="sxs-lookup"><span data-stu-id="9318c-280">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set and date) and select the refresh button to filter the results after they've defined the query.</span></span> <span data-ttu-id="9318c-281">屏幕上现在也强调刷新按钮。</span><span class="sxs-lookup"><span data-stu-id="9318c-281">The refresh button is also now emphasized on the screen.</span></span> <span data-ttu-id="9318c-282">我们还更新了相关工具提示和产品内文档。</span><span class="sxs-lookup"><span data-stu-id="9318c-282">We've also updated the related tooltips and in-product documentation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-283">![选择"刷新"筛选结果](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-283">![Select Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="9318c-284">要添加到筛选器的图表深化</span><span class="sxs-lookup"><span data-stu-id="9318c-284">Chart drilldown to add to filters</span></span>

<span data-ttu-id="9318c-285">现在，你可以绘制图例值图表以将它们添加为筛选器。</span><span class="sxs-lookup"><span data-stu-id="9318c-285">You can now chart legend values to add them as filters.</span></span> <span data-ttu-id="9318c-286">选择" **刷新"** 按钮以筛选结果。</span><span class="sxs-lookup"><span data-stu-id="9318c-286">Select the **Refresh** button to filter the results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-287">![向下钻取图表以筛选](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-287">![Drill down through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="9318c-288">产品内信息更新</span><span class="sxs-lookup"><span data-stu-id="9318c-288">In-product information updates</span></span>

<span data-ttu-id="9318c-289">现在可在产品内获得其他详细信息，如网格中的搜索结果总数 (请参阅下面的) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-289">Additional details are now available within the product, such as the total number of search results within the grid (see below).</span></span> <span data-ttu-id="9318c-290">我们改进了标签、错误消息和工具提示，以提供有关筛选器、搜索体验和搜索结果集。</span><span class="sxs-lookup"><span data-stu-id="9318c-290">We've improved labels, error messages, and tooltips to provide more information about the filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-291">![查看产品内信息](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-291">![View in-product information](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="9318c-292">威胁资源管理器中的扩展功能</span><span class="sxs-lookup"><span data-stu-id="9318c-292">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="9318c-293">主要目标用户</span><span class="sxs-lookup"><span data-stu-id="9318c-293">Top targeted users</span></span>

<span data-ttu-id="9318c-294">今天，我们在电子邮件的"恶意软件"视图中的"主要恶意软件系列"部分公开 **了主要目标** 用户列表。</span><span class="sxs-lookup"><span data-stu-id="9318c-294">Today we expose the list of the top targeted users in the Malware view for emails, in the **Top Malware Families** section.</span></span> <span data-ttu-id="9318c-295">我们还将在"钓鱼邮件"和"所有电子邮件"视图中扩展此视图。</span><span class="sxs-lookup"><span data-stu-id="9318c-295">We'll be extending this view in the Phish and All Email views as well.</span></span> <span data-ttu-id="9318c-296">你将能够看到前五个目标用户，以及每个用户针对相应视图的尝试次数。</span><span class="sxs-lookup"><span data-stu-id="9318c-296">You'll be able to see the top-five targeted users, along with the number of attempts for each user for the corresponding view.</span></span> <span data-ttu-id="9318c-297">例如，对于网络钓鱼视图，你将看到网络钓鱼尝试次数。</span><span class="sxs-lookup"><span data-stu-id="9318c-297">For example, for Phish view, you'll see the number of Phish attempts.</span></span>

<span data-ttu-id="9318c-298">你将能够导出目标用户列表（最多 3，000 个）以及每个电子邮件视图的脱机分析尝试次数。</span><span class="sxs-lookup"><span data-stu-id="9318c-298">You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="9318c-299">此外，选择尝试次数 (例如，在) 下的图像中尝试 13 次将在威胁资源管理器中打开筛选视图，以便你可以查看有关该用户的电子邮件和威胁的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="9318c-299">In addition, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-300">![主要目标用户](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-300">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="9318c-301">Exchange传输规则</span><span class="sxs-lookup"><span data-stu-id="9318c-301">Exchange transport rules</span></span>

<span data-ttu-id="9318c-302">作为数据扩充的一部分，你将能够看到应用于邮件的所有Exchange ETR (ETR) 传输规则。</span><span class="sxs-lookup"><span data-stu-id="9318c-302">As part of data enrichment, you'll be able to see all the different Exchange transport rules (ETR) that were applied to a message.</span></span> <span data-ttu-id="9318c-303">此信息将在电子邮件网格视图中提供。</span><span class="sxs-lookup"><span data-stu-id="9318c-303">This information will be available in the Email grid view.</span></span> <span data-ttu-id="9318c-304">若要查看它，请选择网格 **中的列** 选项，然后从Exchange **添加** 传输规则。</span><span class="sxs-lookup"><span data-stu-id="9318c-304">To view it,  select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="9318c-305">它还将在电子邮件的" **详细信息** "飞出内容上可见。</span><span class="sxs-lookup"><span data-stu-id="9318c-305">It will also be visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="9318c-306">您将能够查看已应用于邮件的传输规则的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="9318c-306">You'll be able to see both the GUID and the name of the transport rules that were applied to the message.</span></span> <span data-ttu-id="9318c-307">您将能够使用传输规则的名称搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="9318c-307">You'll be able to search for the messages by using the name of the transport rule.</span></span> <span data-ttu-id="9318c-308">这是一个"包含"搜索，这意味着您也可以执行部分搜索。</span><span class="sxs-lookup"><span data-stu-id="9318c-308">This is a "Contains" search, which means you can do partial searches as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9318c-309">ETR 搜索和名称可用性取决于分配给您的特定角色。</span><span class="sxs-lookup"><span data-stu-id="9318c-309">ETR search and name availability depend on the specific role that's assigned to you.</span></span> <span data-ttu-id="9318c-310">您需要具有以下角色/权限之一才能查看 ETR 名称和搜索。</span><span class="sxs-lookup"><span data-stu-id="9318c-310">You need to have one of the following roles/permissions to view the ETR names and search.</span></span> <span data-ttu-id="9318c-311">如果没有分配任何这些角色，则看不到传输规则的名称，也看不到使用 ETR 名称搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="9318c-311">If you don't have any of these roles assigned to you, you can't see the names of the transport rules or search for messages by using ETR names.</span></span> <span data-ttu-id="9318c-312">但是，您可以在电子邮件详细信息中查看 ETR 标签和 GUID 信息。</span><span class="sxs-lookup"><span data-stu-id="9318c-312">However, you could see the ETR label and GUID information in the Email Details.</span></span> <span data-ttu-id="9318c-313">电子邮件网格、电子邮件飞出、筛选器和导出中的其他记录查看体验不受影响。</span><span class="sxs-lookup"><span data-stu-id="9318c-313">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="9318c-314">仅 EXO - 数据丢失防护：全部</span><span class="sxs-lookup"><span data-stu-id="9318c-314">EXO Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="9318c-315">仅 EXO - O365SupportViewConfig：全部</span><span class="sxs-lookup"><span data-stu-id="9318c-315">EXO Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="9318c-316">Microsoft Azure Active Directory或 EXO - 安全管理员：全部</span><span class="sxs-lookup"><span data-stu-id="9318c-316">Microsoft Azure Active Directory or EXO - Security Admin: All</span></span>
> - <span data-ttu-id="9318c-317">AAD 或 EXO - 安全读者：全部</span><span class="sxs-lookup"><span data-stu-id="9318c-317">AAD or EXO - Security Reader: All</span></span>
> - <span data-ttu-id="9318c-318">仅 EXO - 传输规则：全部</span><span class="sxs-lookup"><span data-stu-id="9318c-318">EXO Only - Transport Rules: All</span></span>
> - <span data-ttu-id="9318c-319">仅 EXO - View-Only配置：全部</span><span class="sxs-lookup"><span data-stu-id="9318c-319">EXO Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="9318c-320">在电子邮件网格、详细信息飞出控件和导出的 CSV 中，ETR 将显示一个名称/GUID，如下所示。</span><span class="sxs-lookup"><span data-stu-id="9318c-320">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="9318c-321">![Exchange传输规则](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-321">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="9318c-322">入站连接器</span><span class="sxs-lookup"><span data-stu-id="9318c-322">Inbound connectors</span></span>

<span data-ttu-id="9318c-323">连接器是一组说明，用于自定义电子邮件在组织或组织Microsoft 365 Office 365流。</span><span class="sxs-lookup"><span data-stu-id="9318c-323">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="9318c-324">它们使您能够应用任何安全限制或控件。</span><span class="sxs-lookup"><span data-stu-id="9318c-324">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="9318c-325">在威胁资源管理器中，你现在可以查看与电子邮件相关的连接器，然后使用连接器名称搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9318c-325">Within Threat Explorer, you can now view the connectors that are related to an email and search for emails by using connector names.</span></span>

<span data-ttu-id="9318c-326">连接器的搜索本质上是"包含"的，这意味着部分关键字搜索也应正常工作。</span><span class="sxs-lookup"><span data-stu-id="9318c-326">The search for connectors is "contains" in nature, which means partial keyword searches should work as well.</span></span> <span data-ttu-id="9318c-327">在主网格视图、"详细信息"飞出控件和导出的 CSV 中，连接器以名称/GUID 格式显示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9318c-327">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown here:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-328">![连接器详细信息](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-328">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="9318c-329">威胁资源管理器和实时检测中的新功能</span><span class="sxs-lookup"><span data-stu-id="9318c-329">New features in Threat Explorer and Real-time detections</span></span>

- [<span data-ttu-id="9318c-330">查看发送给模拟用户和域的网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="9318c-330">View phishing emails sent to impersonated users and domains</span></span>](#view-phishing-emails-sent-to-impersonated-users-and-domains)
- [<span data-ttu-id="9318c-331">预览电子邮件头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="9318c-331">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="9318c-332">电子邮件时间线</span><span class="sxs-lookup"><span data-stu-id="9318c-332">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="9318c-333">导出 URL 单击数据</span><span class="sxs-lookup"><span data-stu-id="9318c-333">Export URL click data</span></span>](#export-url-click-data)

### <a name="view-phishing-emails-sent-to-impersonated-users-and-domains"></a><span data-ttu-id="9318c-334">查看发送给模拟用户和域的网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="9318c-334">View phishing emails sent to impersonated users and domains</span></span>

<span data-ttu-id="9318c-335">若要识别针对被模拟用户的用户和域的网络钓鱼尝试，必须添加到用户 *列表中以保护*。</span><span class="sxs-lookup"><span data-stu-id="9318c-335">To identify phishing attempts against users and domains that are impersonated users must be added to the list of *Users to protect*.</span></span> <span data-ttu-id="9318c-336">对于域，管理员必须启用 *"组织* 域"，或向"域"添加域名 *才能保护*。</span><span class="sxs-lookup"><span data-stu-id="9318c-336">For domains, admins must either enable *Organization domains*, or add a domain name to *Domains to protect*.</span></span> <span data-ttu-id="9318c-337">要保护的域位于"模拟"部分中的" *防* 钓鱼 *策略"* 页面上。</span><span class="sxs-lookup"><span data-stu-id="9318c-337">The domains to protect are found on the *Anti-Phishing policy page* in the *Impersonation* section.</span></span>

<span data-ttu-id="9318c-338">若要查看网络钓鱼邮件并搜索模拟的用户或域，请使用资源管理器> [电子邮件和网络钓鱼](threat-explorer-views.md) "视图。</span><span class="sxs-lookup"><span data-stu-id="9318c-338">To review phish messages and search for impersonated users or domains, use the [Email > Phish view](threat-explorer-views.md) of Explorer.</span></span>

<span data-ttu-id="9318c-339">此示例使用威胁资源管理器。</span><span class="sxs-lookup"><span data-stu-id="9318c-339">This example uses Threat Explorer.</span></span>

1. <span data-ttu-id="9318c-340">在安全 [&合规 (](https://protection.office.com) 中，选择"威胁>资源管理器 (或实时 https://protection.office.com)) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-340">In the [Security & Compliance Center](https://protection.office.com) (https://protection.office.com), choose Threat management > Explorer (or Real-time detections).</span></span>

2. <span data-ttu-id="9318c-341">在"视图"菜单中，选择"电子邮件>钓鱼邮件"。</span><span class="sxs-lookup"><span data-stu-id="9318c-341">In the View menu, choose Email > Phish.</span></span>

   <span data-ttu-id="9318c-342">可以在此处选择 **模拟域或\*\*\*\*模拟用户**。</span><span class="sxs-lookup"><span data-stu-id="9318c-342">Here you can choose **impersonated domain** or **impersonated user**.</span></span>

3. <span data-ttu-id="9318c-343">**选择\*\*\*\*"模拟域"，** 然后在文本框中键入受保护的域。</span><span class="sxs-lookup"><span data-stu-id="9318c-343">**EITHER** select **Impersonated domain**, and then type a protected domain in the textbox.</span></span>

   <span data-ttu-id="9318c-344">例如，搜索 *contoso、contoso.com* 或 *contoso.com.au\*\*等受保护的域名*。</span><span class="sxs-lookup"><span data-stu-id="9318c-344">For example, search for protected domain names like *contoso*, *contoso.com*, or *contoso.com.au*.</span></span>

4. <span data-ttu-id="9318c-345">Select the Subject of any message under the Email tab > Details tab to see additional impersonation information like Impersonated Domain / Detected location.</span><span class="sxs-lookup"><span data-stu-id="9318c-345">Select the Subject of any message under the Email tab > Details tab to see additional impersonation information like Impersonated Domain / Detected location.</span></span>

    <span data-ttu-id="9318c-346">**OR**</span><span class="sxs-lookup"><span data-stu-id="9318c-346">**OR**</span></span>

    <span data-ttu-id="9318c-347">选择 **"模拟用户** "，在文本框中键入受保护的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9318c-347">Select **Impersonated user** and type a protected user's email address in the textbox.</span></span>

    > [!TIP]
    > <span data-ttu-id="9318c-348">**为了获得最佳结果**，请使用 *完整电子邮件地址* 来搜索受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="9318c-348">**For best results**, use *full email addresses* to search protected users.</span></span> <span data-ttu-id="9318c-349">例如，在调查用户模拟时，如果搜索 *firstname.lastname@contoso.com，您将* 更快、更成功地找到受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="9318c-349">You will find your protected user quicker and more successfully if you search for *firstname.lastname@contoso.com*, for example, when investigating user impersonation.</span></span> <span data-ttu-id="9318c-350">搜索受保护的域时，搜索将接受根域 (contoso.com，例如) ，域名 (*contoso*) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-350">When searching for a protected domain the search will take the root domain (contoso.com, for example), and the domain name (*contoso*).</span></span> <span data-ttu-id="9318c-351">搜索根域 contoso.com将同时返回 contoso.com 和域名 *contoso 的模拟*。 </span><span class="sxs-lookup"><span data-stu-id="9318c-351">Searching for the root domain *contoso.com* will return both impersonations of *contoso.com* and the domain name *contoso*.</span></span>

5. <span data-ttu-id="9318c-352">在"**电子邮件"\*\*\*\*选项卡"详细信息**"选项卡下选择任何邮件的主题，以查看有关用户或域的其他模拟信息和  >  检测到 *的位置*。</span><span class="sxs-lookup"><span data-stu-id="9318c-352">Select the **Subject** of any message under **Email tab** > **Details tab** to see additional impersonation information about the user or domain, and the *Detected location*.</span></span>

    :::image type="content" source="../../media/threat-ex-views-impersonated-user-image.png" alt-text="显示检测位置和检测到的威胁的受保护用户的&quot;威胁资源管理器&quot;详细信息窗格 (冒充用户或) 。":::

> [!NOTE]
> <span data-ttu-id="9318c-354">在步骤 3 或 5 中，如果分别选择"检测技术"并选择"模拟域"或"模拟用户"，则"电子邮件"选项卡"详细信息"选项卡中有关用户或域的信息以及"检测到的位置"将只显示在与"反网络钓鱼策略"页中列出的用户或域相关的邮件上。   >    </span><span class="sxs-lookup"><span data-stu-id="9318c-354">In step 3 or 5, if you choose **Detection Technology** and select **Impersonation domain** or **Impersonation user** respectively, the information in the **Email tab** > **Details tab** about the user or domain, and the *Detected location* will be shown only on the messages that are related to the user or domain listed on the *Anti-Phishing policy* page.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="9318c-355">预览电子邮件头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="9318c-355">Preview email header and download email body</span></span>

<span data-ttu-id="9318c-356">你现在可以在威胁资源管理器中预览电子邮件头并下载电子邮件正文。</span><span class="sxs-lookup"><span data-stu-id="9318c-356">You can now preview an email header and download the email body in Threat Explorer.</span></span> <span data-ttu-id="9318c-357">管理员可以分析下载的邮件头/电子邮件中的威胁。</span><span class="sxs-lookup"><span data-stu-id="9318c-357">Admins can analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="9318c-358">因为下载电子邮件可能会暴露信息的风险，所以此过程由基于角色的访问控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-358">Because downloading email messages can risk exposure of information, this process is controlled by role-based access control (RBAC).</span></span> <span data-ttu-id="9318c-359">必须将新角色 *Preview* 添加到另一个角色组 (如安全操作或安全管理员) ，以授予在全电子邮件视图中下载邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="9318c-359">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails in all-email messages view.</span></span> <span data-ttu-id="9318c-360">但是，查看电子邮件头不需要任何其他角色 (在威胁资源管理器中查看邮件所需的角色) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-360">However, viewing the email header does not require any additional role (other than what is required to view messages in Threat Explorer).</span></span>

<span data-ttu-id="9318c-361">资源管理器和实时检测还将获得新字段，这些字段提供电子邮件到达位置的更完整图片。</span><span class="sxs-lookup"><span data-stu-id="9318c-361">Explorer and Real-time detections will also get new fields that provide a more complete picture of where your email messages land.</span></span> <span data-ttu-id="9318c-362">这些更改使搜寻安全操作变得更加简单。</span><span class="sxs-lookup"><span data-stu-id="9318c-362">These changes  make hunting easier for Security Ops.</span></span> <span data-ttu-id="9318c-363">但主要结果是你可以一目了然地知道问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="9318c-363">But the main result is you can know the location of problem email messages at a glance.</span></span>

<span data-ttu-id="9318c-364">如何完成此操作？</span><span class="sxs-lookup"><span data-stu-id="9318c-364">How is this done?</span></span> <span data-ttu-id="9318c-365">传递状态现在分为两列：</span><span class="sxs-lookup"><span data-stu-id="9318c-365">Delivery status is now broken out into two columns:</span></span>

- <span data-ttu-id="9318c-366">**传递操作** - 电子邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="9318c-366">**Delivery action** - Status of the email.</span></span>
- <span data-ttu-id="9318c-367">**传递位置** - 电子邮件的路由位置。</span><span class="sxs-lookup"><span data-stu-id="9318c-367">**Delivery location** - Where the email was routed.</span></span>

<span data-ttu-id="9318c-368">*传递* 操作是对现有策略或检测对电子邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="9318c-368">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="9318c-369">以下是电子邮件的可能操作：</span><span class="sxs-lookup"><span data-stu-id="9318c-369">Here are the possible actions for an email:</span></span>

<br>

****

|<span data-ttu-id="9318c-370">已传递</span><span class="sxs-lookup"><span data-stu-id="9318c-370">Delivered</span></span>|<span data-ttu-id="9318c-371">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="9318c-371">Junked</span></span>|<span data-ttu-id="9318c-372">Blocked</span><span class="sxs-lookup"><span data-stu-id="9318c-372">Blocked</span></span>|<span data-ttu-id="9318c-373">已替换</span><span class="sxs-lookup"><span data-stu-id="9318c-373">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="9318c-374">电子邮件已传递到用户的收件箱或文件夹，用户可以访问它。</span><span class="sxs-lookup"><span data-stu-id="9318c-374">Email was delivered to the inbox or folder of a user, and the user can access it.</span></span>|<span data-ttu-id="9318c-375">电子邮件已发送到用户的"垃圾邮件"或"已删除"文件夹，用户可以访问它。</span><span class="sxs-lookup"><span data-stu-id="9318c-375">Email was sent to the user's Junk  or Deleted folder, and the user can access it.</span></span>|<span data-ttu-id="9318c-376">被隔离、失败或已丢弃的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9318c-376">Emails that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="9318c-377">用户无法访问这些邮件。</span><span class="sxs-lookup"><span data-stu-id="9318c-377">These mails are inaccessible to the user.</span></span>|<span data-ttu-id="9318c-378">电子邮件的恶意附件替换为.txt附件是恶意附件的附件。</span><span class="sxs-lookup"><span data-stu-id="9318c-378">Email had malicious attachments replaced by .txt files that state the attachment was malicious.</span></span>|
|

<span data-ttu-id="9318c-379">下面是用户可以看到和看不到的：</span><span class="sxs-lookup"><span data-stu-id="9318c-379">Here is what the user can and can't see:</span></span>

<br>

****

|<span data-ttu-id="9318c-380">最终用户可访问</span><span class="sxs-lookup"><span data-stu-id="9318c-380">Accessible to end users</span></span>|<span data-ttu-id="9318c-381">最终用户无法访问</span><span class="sxs-lookup"><span data-stu-id="9318c-381">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="9318c-382">已传递</span><span class="sxs-lookup"><span data-stu-id="9318c-382">Delivered</span></span>|<span data-ttu-id="9318c-383">Blocked</span><span class="sxs-lookup"><span data-stu-id="9318c-383">Blocked</span></span>|
|<span data-ttu-id="9318c-384">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="9318c-384">Junked</span></span>|<span data-ttu-id="9318c-385">已替换</span><span class="sxs-lookup"><span data-stu-id="9318c-385">Replaced</span></span>|
|

<span data-ttu-id="9318c-386">**传递** 位置显示运行传递后的策略和检测的结果。</span><span class="sxs-lookup"><span data-stu-id="9318c-386">**Delivery location** shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="9318c-387">它链接到传递 **_操作_**。</span><span class="sxs-lookup"><span data-stu-id="9318c-387">It's linked to **_Delivery action_**.</span></span> <span data-ttu-id="9318c-388">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="9318c-388">These are the possible values:</span></span>

- <span data-ttu-id="9318c-389">*收件箱或文件夹*：电子邮件位于收件箱或文件夹中 (电子邮件规则) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-389">*Inbox or folder*: The email is in the inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="9318c-390">*本地或外部*：邮箱在云中不存在，但位于本地。</span><span class="sxs-lookup"><span data-stu-id="9318c-390">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="9318c-391">*垃圾邮件* 文件夹：电子邮件位于用户的"垃圾邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9318c-391">*Junk folder*: The email is in a user's Junk folder.</span></span>
- <span data-ttu-id="9318c-392">*"已删除邮件"文件夹*：用户的"已删除邮件"文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9318c-392">*Deleted items folder*: The email in a user's Deleted items folder.</span></span>
- <span data-ttu-id="9318c-393">*隔离*：电子邮件被隔离，不在用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="9318c-393">*Quarantine*: The email is in quarantine and not in a user's mailbox.</span></span>
- <span data-ttu-id="9318c-394">*失败*：电子邮件无法到达邮箱。</span><span class="sxs-lookup"><span data-stu-id="9318c-394">*Failed*: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="9318c-395">*已* 丢弃：电子邮件在邮件流中的某处丢失。</span><span class="sxs-lookup"><span data-stu-id="9318c-395">*Dropped*: The email got lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="9318c-396">电子邮件时间线</span><span class="sxs-lookup"><span data-stu-id="9318c-396">Email timeline</span></span>

<span data-ttu-id="9318c-397">电子邮件 **时间线** 是一种新的资源管理器功能，可改善管理员的搜寻体验。</span><span class="sxs-lookup"><span data-stu-id="9318c-397">The **Email timeline** is a new Explorer feature that improves the hunting experience for admins.</span></span> <span data-ttu-id="9318c-398">它减少检查不同位置以尝试了解事件所花的时间。</span><span class="sxs-lookup"><span data-stu-id="9318c-398">It cuts the time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="9318c-399">当在电子邮件到达的同一时间或接近同一时间发生多个事件时，这些事件将显示在时间线视图中。</span><span class="sxs-lookup"><span data-stu-id="9318c-399">When multiple events happen at or close to the same time an email arrives, those events are displayed in a timeline view.</span></span> <span data-ttu-id="9318c-400">在"特殊操作"列中捕获在电子邮件传递后发生的一 **些** 事件。</span><span class="sxs-lookup"><span data-stu-id="9318c-400">Some events that happen to your email post-delivery are captured in the **Special action** column.</span></span> <span data-ttu-id="9318c-401">管理员可以将时间线的信息与对邮件传递后采取的特殊操作相结合，以深入了解其策略如何工作、邮件最终路由在何处，在某些情况下，最终评估是什么。</span><span class="sxs-lookup"><span data-stu-id="9318c-401">Admins can combine  information from the timeline with the special action taken on the mail post-delivery to get insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="9318c-402">有关详细信息，请参阅调查和修正在 Office 365[中传递的恶意Office 365。](investigate-malicious-email-that-was-delivered.md)</span><span class="sxs-lookup"><span data-stu-id="9318c-402">For more information, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="9318c-403">导出 URL 单击数据</span><span class="sxs-lookup"><span data-stu-id="9318c-403">Export URL click data</span></span>

<span data-ttu-id="9318c-404">现在，可以将 URL 单击报告导出到Microsoft Excel查看其网络消息 **ID** 并单击 **"** 裁定"，这有助于说明 URL 单击流量的来源。</span><span class="sxs-lookup"><span data-stu-id="9318c-404">You can now export reports for URL clicks to Microsoft Excel to view their **network message ID** and **click verdict**, which helps explain where your URL click traffic originated.</span></span> <span data-ttu-id="9318c-405">它的工作原理如下：在快速启动Office 365上的威胁管理中，按照此链操作：</span><span class="sxs-lookup"><span data-stu-id="9318c-405">Here's how it works: In Threat Management on the Office 365 quick-launch bar, follow this chain:</span></span>

<span data-ttu-id="9318c-406">**资源管理器** \>**查看钓鱼邮件** \>**单击** \>**顶部 URL 或** **URL 顶部单击** \> 选择任意记录以打开 URL 飞出。</span><span class="sxs-lookup"><span data-stu-id="9318c-406">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs** or **URL Top Clicks** \> select any record to open the URL flyout.</span></span>

<span data-ttu-id="9318c-407">在列表中选择 URL 时，你将在飞出面板上看到一个新的"导出"按钮。</span><span class="sxs-lookup"><span data-stu-id="9318c-407">When you select a URL in the list, you'll see a new **Export** button on the fly-out panel.</span></span> <span data-ttu-id="9318c-408">使用此按钮将数据移动到 Excel 电子表格，以便更轻松地报告。</span><span class="sxs-lookup"><span data-stu-id="9318c-408">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="9318c-409">按照此路径到达实时检测报告中的相同位置：</span><span class="sxs-lookup"><span data-stu-id="9318c-409">Follow this path to get to the same location in the Real-time detections report:</span></span>

<span data-ttu-id="9318c-410">**资源管理器** \>**实时检测** \>**查看钓鱼邮件** \>**URL** \>**顶部 URL** 或 **顶部单击** \> 选择任意记录以打开 URL 飞出控件 \> ，导航到"**单击"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9318c-410">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs** or **Top Clicks** \> Select any record to open the URL flyout \> navigate to the **Clicks** tab.</span></span>

> [!TIP]
> <span data-ttu-id="9318c-411">当您通过资源管理器或关联的第三方工具搜索 ID 时，网络消息 ID 将单击映射回特定邮件。</span><span class="sxs-lookup"><span data-stu-id="9318c-411">The Network Message ID maps the click back to specific mails when you search on the ID through Explorer or associated third-party tools.</span></span> <span data-ttu-id="9318c-412">此类搜索可标识与单击结果关联的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9318c-412">Such searches identify the email associated with a click result.</span></span> <span data-ttu-id="9318c-413">通过关联网络消息 ID，可以更快速、更强大的分析。</span><span class="sxs-lookup"><span data-stu-id="9318c-413">Having the correlated Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9318c-414">![资源管理器中的"单击"选项卡](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-414">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="9318c-415">查看通过电子邮件技术检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="9318c-415">See malware detected in email by technology</span></span>

<span data-ttu-id="9318c-416">假设您希望查看在按技术排序的电子邮件Microsoft 365恶意软件。</span><span class="sxs-lookup"><span data-stu-id="9318c-416">Suppose you want to see malware detected in email sorted by Microsoft 365 technology.</span></span> <span data-ttu-id="9318c-417">为此，请使用 Explorer > 或 [实时检测 (](threat-explorer-views.md#email--malware) 的"电子邮件和恶意软件") 。</span><span class="sxs-lookup"><span data-stu-id="9318c-417">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="9318c-418">在安全&中心 () ，选择"威胁管理资源管理器 (<https://protection.office.com> 或实时检测 \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="9318c-418">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="9318c-419"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="9318c-419">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="9318c-420">在"**视图"** 菜单中，选择"**电子邮件恶意软件** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="9318c-420">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9318c-421">![资源管理器的"视图"菜单](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-421">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="9318c-422">单击 **"发件人**"，然后选择"**基本** \> **检测技术"。**</span><span class="sxs-lookup"><span data-stu-id="9318c-422">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="9318c-423">你的检测技术现在用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="9318c-423">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9318c-424">![恶意软件检测技术](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-424">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="9318c-425">选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="9318c-425">Choose an option.</span></span> <span data-ttu-id="9318c-426">然后选择" **刷新"** 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="9318c-426">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9318c-427">![选定的检测技术](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-427">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="9318c-428">报告将刷新，以使用所选的技术选项显示电子邮件中检测到的恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="9318c-428">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="9318c-429">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="9318c-429">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="9318c-430">查看网络钓鱼 URL 并单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="9318c-430">View phishing URL and click verdict data</span></span>

<span data-ttu-id="9318c-431">假设你想要查看通过电子邮件中的 URL 的网络钓鱼尝试，包括允许、阻止和覆盖的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="9318c-431">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="9318c-432">若要标识单击的[URL，保险箱链接](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="9318c-432">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="9318c-433">请确保为单击保险箱和单击[](set-up-safe-links-policies.md)裁定的日志记录设置"链接"策略保险箱链接" 。</span><span class="sxs-lookup"><span data-stu-id="9318c-433">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="9318c-434">若要查看邮件中的网络钓鱼 URL 并单击网络钓鱼邮件中的 URL，请使用资源管理器的电子邮件[  >  ](threat-explorer-views.md#email--phish)网络钓鱼视图或实时检测。</span><span class="sxs-lookup"><span data-stu-id="9318c-434">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="9318c-435">在安全&中心 () ，选择"威胁管理资源管理器 (<https://protection.office.com> 或实时检测 \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="9318c-435">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="9318c-436"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="9318c-436">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="9318c-437">在"**视图"** 菜单中，选择"**电子邮件钓鱼** \> **邮件"。**</span><span class="sxs-lookup"><span data-stu-id="9318c-437">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9318c-438">![网络钓鱼上下文中资源管理器的"查看"菜单](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-438">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="9318c-439">单击 **"发件人**"，然后选择 **"URL""** \> **单击裁定"。**</span><span class="sxs-lookup"><span data-stu-id="9318c-439">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="9318c-440">选择一个或多个选项，如"阻止"和"阻止 **覆盖**"，然后选择与应用该筛选器的选项位于同一行上的"刷新"按钮。</span><span class="sxs-lookup"><span data-stu-id="9318c-440">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="9318c-441"> (请勿刷新浏览器窗口。) </span><span class="sxs-lookup"><span data-stu-id="9318c-441">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9318c-442">![URL 和单击裁定](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-442">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="9318c-443">报告将刷新，以在报告下的"URL"选项卡上显示两个不同的 URL 表：</span><span class="sxs-lookup"><span data-stu-id="9318c-443">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="9318c-444">**顶部 URL** 是筛选到的邮件中的 URL，每个 URL 的电子邮件传递操作计数。</span><span class="sxs-lookup"><span data-stu-id="9318c-444">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="9318c-445">在网络钓鱼电子邮件视图中，此列表通常包含合法 URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-445">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="9318c-446">攻击者在邮件中混合了好 URL 和坏 URL，以尝试传递这些 URL，但它们会使恶意链接看起来更有趣。</span><span class="sxs-lookup"><span data-stu-id="9318c-446">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="9318c-447">URL 表按总电子邮件计数排序，但隐藏此列以简化视图。</span><span class="sxs-lookup"><span data-stu-id="9318c-447">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="9318c-448">**点击量** 最高是保险箱链接包装的 URL，按总点击数排序。</span><span class="sxs-lookup"><span data-stu-id="9318c-448">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="9318c-449">此列也不显示，以简化视图。</span><span class="sxs-lookup"><span data-stu-id="9318c-449">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="9318c-450">按列的总计数指示每个保险箱 URL 的链接单击裁定计数。</span><span class="sxs-lookup"><span data-stu-id="9318c-450">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="9318c-451">在网络钓鱼电子邮件视图中，这些 URL 通常是可疑或恶意 URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-451">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="9318c-452">但是，该视图可能包含不是威胁但包含钓鱼邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-452">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="9318c-453">此处不会显示对未包链接的 URL 单击。</span><span class="sxs-lookup"><span data-stu-id="9318c-453">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="9318c-454">这两个 URL 表按传递操作和位置显示网络钓鱼电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-454">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="9318c-455">这些表显示了尽管出现警告仍被阻止或访问的 URL 单击，因此你可以看到向用户显示哪些潜在的错误链接以及用户点击了哪些链接。</span><span class="sxs-lookup"><span data-stu-id="9318c-455">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the user's clicked.</span></span> <span data-ttu-id="9318c-456">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="9318c-456">From here, you can conduct further analysis.</span></span> <span data-ttu-id="9318c-457">例如，在图表下方，可以看到在组织环境中被阻止的电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-457">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9318c-458">![阻止的浏览器 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-458">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="9318c-459">选择 URL 以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="9318c-459">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9318c-460">在"URL"弹出对话框中，将删除对电子邮件的筛选，以显示环境中 URL 曝光的完整视图。</span><span class="sxs-lookup"><span data-stu-id="9318c-460">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="9318c-461">这允许你在资源管理器中筛选你关注的电子邮件，查找潜在威胁的特定 URL，然后通过"URL 详细信息"对话框) 扩展你了解环境中 (中的 URL 曝光，而无需将 URL 筛选器添加到资源管理器视图本身。</span><span class="sxs-lookup"><span data-stu-id="9318c-461">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="9318c-462">单击裁定的解释</span><span class="sxs-lookup"><span data-stu-id="9318c-462">Interpretation of click verdicts</span></span>

<span data-ttu-id="9318c-463">在"电子邮件"或"URL"飞出、点击次数以及筛选体验内，你将看到不同的单击裁定值：</span><span class="sxs-lookup"><span data-stu-id="9318c-463">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="9318c-464">**无：** 无法捕获 URL 裁定。</span><span class="sxs-lookup"><span data-stu-id="9318c-464">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="9318c-465">用户可能通过 URL 单击过。</span><span class="sxs-lookup"><span data-stu-id="9318c-465">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="9318c-466">**允许：** 允许用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-466">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="9318c-467">**已阻止：** 阻止用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-467">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="9318c-468">**待定裁定：** 向用户显示等待触发的页面。</span><span class="sxs-lookup"><span data-stu-id="9318c-468">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="9318c-469">**被阻止覆盖：** 阻止用户直接导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-469">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="9318c-470">但用户过度控制块以导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="9318c-470">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="9318c-471">**已绕过待定裁定：** 向用户显示触发页面。</span><span class="sxs-lookup"><span data-stu-id="9318c-471">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="9318c-472">但是，用户为了访问 URL 而过度使用邮件。</span><span class="sxs-lookup"><span data-stu-id="9318c-472">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="9318c-473">**错误：** 向用户显示错误页面，或捕获裁定时出错。</span><span class="sxs-lookup"><span data-stu-id="9318c-473">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="9318c-474">**失败：** 捕获裁定时发生未知异常。</span><span class="sxs-lookup"><span data-stu-id="9318c-474">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="9318c-475">用户可能通过 URL 单击过。</span><span class="sxs-lookup"><span data-stu-id="9318c-475">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="9318c-476">查看用户报告的电子邮件</span><span class="sxs-lookup"><span data-stu-id="9318c-476">Review email messages reported by users</span></span>

<span data-ttu-id="9318c-477">假定您希望查看您组织中用户通过报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、非垃圾邮件或网络钓鱼[的电子邮件](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="9318c-477">Suppose that you want to see email messages that users in your organization reported as *Junk*, *Not Junk*, or *Phishing* through the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span> <span data-ttu-id="9318c-478">若要查看它们，请使用资源管理器的"电子邮件[  >  提交" (](threat-explorer-views.md#email--submissions)或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-478">To see them, use the [**Email** > **Submissions**](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="9318c-479">在安全&中心 () ，选择"威胁管理资源管理器 (<https://protection.office.com> 或实时检测 \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="9318c-479">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="9318c-480"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="9318c-480">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="9318c-481">在"**视图"** 菜单中，选择"**电子邮件** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="9318c-481">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9318c-482">![电子邮件资源管理器的"查看"菜单](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-482">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="9318c-483">单击 **"发件人**"，然后选择"**基本** \> **报告类型"。**</span><span class="sxs-lookup"><span data-stu-id="9318c-483">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="9318c-484">选择一个选项（如 **钓鱼邮件**）然后选择" **刷新"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="9318c-484">Select an option, such as **Phish**, and then select the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9318c-485">![用户报告的网络钓鱼](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="9318c-485">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="9318c-486">报告将刷新以显示有关组织中人员报告为网络钓鱼尝试的电子邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="9318c-486">The report refreshes to show data about email messages that people in your organization reported as a phishing attempt.</span></span> <span data-ttu-id="9318c-487">可以使用此信息进行进一步分析，如有必要，在 Microsoft Defender 中调整反网络钓鱼策略[，Office 365。](configure-mdo-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9318c-487">You can use this information to conduct further analysis, and, if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="9318c-488">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="9318c-488">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="9318c-489">Microsoft Defender for *Office 365 计划 2* 和 Office 365 E5 *中提供了自动调查和响应Office 365 E5。*</span><span class="sxs-lookup"><span data-stu-id="9318c-489">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="9318c-490">[自动调查和响应](automated-investigation-response-office.md) 可以节省安全运营团队在调查和缓解网络攻击上花费的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="9318c-490">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="9318c-491">除了配置可触发安全手册的警报之外，还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="9318c-491">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="9318c-492">有关详细信息，请参阅 [示例：安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="9318c-492">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a><span data-ttu-id="9318c-493">使用资源管理器和实时检测的更多方法</span><span class="sxs-lookup"><span data-stu-id="9318c-493">More ways to use Explorer and Real-time detections</span></span>

<span data-ttu-id="9318c-494">除了本文中概述的方案之外，资源管理器或实时检测功能中还 (更多报告) 。</span><span class="sxs-lookup"><span data-stu-id="9318c-494">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span> <span data-ttu-id="9318c-495">另请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="9318c-495">See the following articles:</span></span>

- [<span data-ttu-id="9318c-496">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="9318c-496">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="9318c-497">查看在 SharePoint Online、OneDrive 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9318c-497">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](./mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="9318c-498">大致了解威胁资源管理器中的 (和实时检测) </span><span class="sxs-lookup"><span data-stu-id="9318c-498">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="9318c-499">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="9318c-499">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="9318c-500">自动调查和响应Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9318c-500">Automated investigation and response in Microsoft 365 Defender</span></span>](../defender/m365d-autoir.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="9318c-501">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="9318c-501">Required licenses and permissions</span></span>

<span data-ttu-id="9318c-502">你必须拥有[Microsoft Defender Office 365](defender-for-office-365.md)使用资源管理器或实时检测。</span><span class="sxs-lookup"><span data-stu-id="9318c-502">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="9318c-503">资源管理器包含在计划 2 Office 365 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="9318c-503">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="9318c-504">实时检测报告包含在计划 1 的 Defender Office 365中。</span><span class="sxs-lookup"><span data-stu-id="9318c-504">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="9318c-505">计划为应受 Defender for Office 365 保护的所有用户分配Office 365。</span><span class="sxs-lookup"><span data-stu-id="9318c-505">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="9318c-506">资源管理器和实时检测显示许可用户的检测数据。</span><span class="sxs-lookup"><span data-stu-id="9318c-506">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="9318c-507">若要查看和使用资源管理器或实时检测，您必须具有适当的权限，例如授予安全管理员或安全读者的权限。</span><span class="sxs-lookup"><span data-stu-id="9318c-507">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="9318c-508">对于安全&合规中心，必须分配以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="9318c-508">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="9318c-509">组织管理</span><span class="sxs-lookup"><span data-stu-id="9318c-509">Organization Management</span></span>
  - <span data-ttu-id="9318c-510">安全 (可以在管理中心Azure Active Directory分配 <https://aad.portal.azure.com> () </span><span class="sxs-lookup"><span data-stu-id="9318c-510">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="9318c-511">安全读取者</span><span class="sxs-lookup"><span data-stu-id="9318c-511">Security Reader</span></span>

- <span data-ttu-id="9318c-512">For Exchange Online， you must have one of the following roles assigned in either the Exchange admin center <https://admin.protection.outlook.com/ecp/> () or Exchange Online [PowerShell：](/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="9318c-512">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="9318c-513">组织管理</span><span class="sxs-lookup"><span data-stu-id="9318c-513">Organization Management</span></span>
  - <span data-ttu-id="9318c-514">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="9318c-514">View-Only Organization Management</span></span>
  - <span data-ttu-id="9318c-515">仅查看收件人</span><span class="sxs-lookup"><span data-stu-id="9318c-515">View-Only Recipients</span></span>
  - <span data-ttu-id="9318c-516">合规性管理</span><span class="sxs-lookup"><span data-stu-id="9318c-516">Compliance Management</span></span>

<span data-ttu-id="9318c-517">若要详细了解角色和权限，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="9318c-517">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="9318c-518">Microsoft 365 Defender 门户中的权限</span><span class="sxs-lookup"><span data-stu-id="9318c-518">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="9318c-519">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="9318c-519">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="9318c-520">威胁资源管理器和实时检测之间的差异</span><span class="sxs-lookup"><span data-stu-id="9318c-520">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="9318c-521">*实时检测报告在* Defender for Office 365 计划 1 中提供。</span><span class="sxs-lookup"><span data-stu-id="9318c-521">The *Real-time detections* report is available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="9318c-522">*威胁资源管理器* 在 Defender for Office 365计划 2 中可用。</span><span class="sxs-lookup"><span data-stu-id="9318c-522">*Threat Explorer* is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="9318c-523">实时检测报告允许你实时查看检测。</span><span class="sxs-lookup"><span data-stu-id="9318c-523">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="9318c-524">威胁资源管理器也这样做，但它还提供了给定攻击的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="9318c-524">Threat Explorer does this as well, but it also provides additional details for a given attack.</span></span>
- <span data-ttu-id="9318c-525">" *所有电子邮件* "视图在威胁资源管理器中可用，但在实时检测报告中不可用。</span><span class="sxs-lookup"><span data-stu-id="9318c-525">An *All email* view is available in Threat Explorer but not in the Real-time detections report.</span></span>
- <span data-ttu-id="9318c-526">威胁资源管理器中包含更多筛选功能和可用操作。</span><span class="sxs-lookup"><span data-stu-id="9318c-526">More filtering capabilities and available actions are included in Threat Explorer.</span></span> <span data-ttu-id="9318c-527">有关详细信息，请参阅[Microsoft Defender for Office 365 服务说明：跨 Defender for Office 365 计划的功能可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="9318c-527">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="other-articles"></a><span data-ttu-id="9318c-528">其他文章</span><span class="sxs-lookup"><span data-stu-id="9318c-528">Other articles</span></span>

[<span data-ttu-id="9318c-529">使用"电子邮件实体"页调查电子邮件</span><span class="sxs-lookup"><span data-stu-id="9318c-529">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
