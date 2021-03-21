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
description: 使用安全与合规中心中的资源管理器和实时检测有效 &amp; 调查和响应威胁。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3f8f8dfc5cf1066b4ebcf166487bfcdb0a8b2db7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922494"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="8011c-103">威胁资源管理器和实时检测</span><span class="sxs-lookup"><span data-stu-id="8011c-103">Threat Explorer and Real-time detections</span></span>


<span data-ttu-id="8011c-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="8011c-104">**Applies to**</span></span>
- [<span data-ttu-id="8011c-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="8011c-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="8011c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8011c-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="8011c-107">如果你的组织拥有 [适用于 Office 365](office-365-atp.md)的 Microsoft Defender，并且你拥有必要的权限，则你拥有资源管理器或实时检测 (以前是实时报告 *-查看* 新增功能 [！) 。](#new-features-in-threat-explorer-and-real-time-detections) [](#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="8011c-107">If your organization has [Microsoft Defender for Office 365](office-365-atp.md), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **Real-time detections** (formerly *Real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="8011c-108">在安全&合规中心，转到"**威胁** 管理"，然后选择"**资源管理器**"_或_**"实时检测"。**</span><span class="sxs-lookup"><span data-stu-id="8011c-108">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>


|<span data-ttu-id="8011c-109">借助 Microsoft Defender for Office 365 计划 2，可以看到：</span><span class="sxs-lookup"><span data-stu-id="8011c-109">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="8011c-110">借助 Microsoft Defender for Office 365 计划 1，可以看到：</span><span class="sxs-lookup"><span data-stu-id="8011c-110">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![威胁资源管理器](../../media/threatmgmt-explorer.png)|![实时检测](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="8011c-113">资源管理器或实时检测可帮助安全运营团队高效地调查和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="8011c-113">Explorer or Real-time detections helps your security operations team investigate and respond to threats efficiently.</span></span> <span data-ttu-id="8011c-114">报告类似于下图：</span><span class="sxs-lookup"><span data-stu-id="8011c-114">The report resembles the following image:</span></span>

![转到威胁管理 \> 资源管理器](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="8011c-116">通过此报告，您可以：</span><span class="sxs-lookup"><span data-stu-id="8011c-116">With this report, you can:</span></span>

- [<span data-ttu-id="8011c-117">查看 Microsoft 365 安全功能检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="8011c-117">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="8011c-118">查看网络钓鱼 URL 并单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="8011c-118">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- <span data-ttu-id="8011c-119">[仅从 Explorer (](#start-automated-investigation-and-response) Defender for Office 365 计划 2 中的视图启动自动调查和响应) </span><span class="sxs-lookup"><span data-stu-id="8011c-119">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- [<span data-ttu-id="8011c-120">调查恶意电子邮件等</span><span class="sxs-lookup"><span data-stu-id="8011c-120">Investigate malicious email, and more</span></span>](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="8011c-121">威胁搜寻体验改进</span><span class="sxs-lookup"><span data-stu-id="8011c-121">Improvements to Threat Hunting Experience</span></span>

### <a name="introduction-of-alert-id-for-mdo-alerts-within-explorerreal-time-detections-preview"></a><span data-ttu-id="8011c-122">在预览版资源管理器中引入 MDO 警报的警报 ID/ (实时) </span><span class="sxs-lookup"><span data-stu-id="8011c-122">Introduction of Alert ID for MDO alerts within Explorer/Real-time detections (Preview)</span></span>
<span data-ttu-id="8011c-123">今天，如果你从警报导航到威胁资源管理器，它将在资源管理器中打开筛选的视图，其中按警报策略 ID (策略 ID 筛选的视图是警报策略设置的唯一标识符) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-123">Today, if you navigate from an alert to Threat Explorer, it opens a filtered view within the Explorer, with the view filtered by Alert policy ID (policy ID being a unique identifier for an Alert policy).</span></span>
<span data-ttu-id="8011c-124">我们正在通过引入警报 ID (在威胁资源管理器和实时检测中查看) 下方的警报 ID 示例，以便查看与特定警报相关的邮件以及电子邮件数量，从而使此集成更具相关性。</span><span class="sxs-lookup"><span data-stu-id="8011c-124">We are making this integration more relevant by introducing the alert ID (see an example of alert ID below) in Threat Explorer and Real-time detections so that you see messages which are relevant to the specific alert, as well as a count of emails.</span></span> <span data-ttu-id="8011c-125">您还可以查看邮件是否属于警报，以及从该邮件导航到特定警报。</span><span class="sxs-lookup"><span data-stu-id="8011c-125">You will also be able to see if a message was part of an alert, as well as navigate from that message to the specific alert.</span></span>  

<span data-ttu-id="8011c-126">查看单个警报时，警报 ID 在 URL 中可用;示例为 `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span><span class="sxs-lookup"><span data-stu-id="8011c-126">Alert ID is available within the URL when you are viewing an individual alert; an example being `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-127">![筛选警报 ID](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-127">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-128">![详细信息中的警报 ID 飞出](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-128">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

 
### <a name="extending-the-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants-from-7-to-30-days-preview"></a><span data-ttu-id="8011c-129">扩展 Explorer (和实时检测) 预览版中试用版租户的数据保留和搜索限制从 7 天 (30) </span><span class="sxs-lookup"><span data-stu-id="8011c-129">Extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days (Preview)</span></span>  
<span data-ttu-id="8011c-130">作为此更改的一部分，你将能够在威胁资源管理器/实时检测（适用于 Office P1 和 P2 试用租户的 Defender）中搜索和筛选电子邮件数据 (这一点比前 7 天) 增加了。</span><span class="sxs-lookup"><span data-stu-id="8011c-130">As part of this change, you will be able to search for, and filter email data across 30 days (an increase from the previous 7 days) in Threat Explorer/Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="8011c-131">这不会影响 P1 和 P2/E5 客户的任何生产租户，这已具有 30 天的数据保留和搜索功能。</span><span class="sxs-lookup"><span data-stu-id="8011c-131">This does not impact any production tenants for both P1 and P2/E5 customers, which already has the 30 day data retention and search capabilities.</span></span> 

### <a name="updated-limits-for-export-of-records-for-threat-explorer-preview"></a><span data-ttu-id="8011c-132">更新了威胁资源管理器预览版中导出 (限制) </span><span class="sxs-lookup"><span data-stu-id="8011c-132">Updated limits for Export of records for Threat Explorer (Preview)</span></span> 
<span data-ttu-id="8011c-133">作为此更新的一部分，可以从威胁资源管理器导出的电子邮件记录的行数从 9990 增加到 200，000 条记录。</span><span class="sxs-lookup"><span data-stu-id="8011c-133">As part of this update, the number of rows for Email records that can be exported from Threat Explorer is increased from 9990 to 200,000 records.</span></span> <span data-ttu-id="8011c-134">当前可以导出的列集将保持不变，但行数将自当前限制开始增加。</span><span class="sxs-lookup"><span data-stu-id="8011c-134">The set of columns that can be exported currently will remain the same, but the number of rows will increase from the current limit.</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="8011c-135">威胁资源管理器中的标记</span><span class="sxs-lookup"><span data-stu-id="8011c-135">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="8011c-136">用户标记功能在 *预览版* 中，并非对所有人都可用，并且可能会更改。</span><span class="sxs-lookup"><span data-stu-id="8011c-136">The user tags feature is in *Preview*, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="8011c-137">有关发布计划的信息，请查看 Microsoft 365 路线图。</span><span class="sxs-lookup"><span data-stu-id="8011c-137">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="8011c-138">用户标记标识 Microsoft Defender for Office 365 中的特定用户组。</span><span class="sxs-lookup"><span data-stu-id="8011c-138">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8011c-139">有关标记（包括许可和配置）的信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="8011c-139">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="8011c-140">在威胁资源管理器中，可以在以下体验中查看有关用户标记的信息。</span><span class="sxs-lookup"><span data-stu-id="8011c-140">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="8011c-141">电子邮件网格视图</span><span class="sxs-lookup"><span data-stu-id="8011c-141">Email grid view</span></span>

<span data-ttu-id="8011c-142">电子邮件 **网格** 中的"标记"列包含已应用于发件人或收件人邮箱的所有标记。</span><span class="sxs-lookup"><span data-stu-id="8011c-142">The **Tags** column in the email grid contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="8011c-143">默认情况下，优先显示优先帐户等系统标记。</span><span class="sxs-lookup"><span data-stu-id="8011c-143">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-144">![电子邮件网格视图中的筛选器标记](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-144">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="8011c-145">筛选</span><span class="sxs-lookup"><span data-stu-id="8011c-145">Filtering</span></span>

<span data-ttu-id="8011c-146">可以将标记用作筛选器。</span><span class="sxs-lookup"><span data-stu-id="8011c-146">You can use tags as a filter.</span></span> <span data-ttu-id="8011c-147">仅跨优先级帐户或特定用户标记方案进行智能寻线。</span><span class="sxs-lookup"><span data-stu-id="8011c-147">Hunt just across priority accounts or specific user tags scenarios.</span></span> <span data-ttu-id="8011c-148">还可以排除具有特定标记的结果。</span><span class="sxs-lookup"><span data-stu-id="8011c-148">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="8011c-149">将此功能与其他筛选器相结合，以缩小调查范围。</span><span class="sxs-lookup"><span data-stu-id="8011c-149">Combine this functionality with other filters to narrow your scope of investigation.</span></span>

<span data-ttu-id="8011c-150">[![筛选器标记](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8011c-150">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-151">![非筛选器标记](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-151">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="8011c-152">电子邮件详细信息飞出</span><span class="sxs-lookup"><span data-stu-id="8011c-152">Email detail flyout</span></span>
<span data-ttu-id="8011c-153">若要查看发件人和收件人的单个标记，请选择主题以打开邮件详细信息飞出。</span><span class="sxs-lookup"><span data-stu-id="8011c-153">To view the individual tags for sender and recipient, select the subject to open the message details flyout.</span></span> <span data-ttu-id="8011c-154">在 **"摘要"** 选项卡上，如果电子邮件存在发件人和收件人标记，则分别显示它们。</span><span class="sxs-lookup"><span data-stu-id="8011c-154">On the **Summary** tab, the sender and recipient tags are shown separately, if they're present for an email.</span></span>
<span data-ttu-id="8011c-155">有关发件人和收件人的单个标记的信息还扩展到导出的 CSV 数据，您可以在两个单独的列中查看这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="8011c-155">The information about individual tags for sender and recipient also extends to exported CSV data, where you can see these details in two separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-156">![电子邮件详细信息标记](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-156">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="8011c-157">URL 单击飞出也显示标记信息。</span><span class="sxs-lookup"><span data-stu-id="8011c-157">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="8011c-158">若要查看它，请转到网络钓鱼或所有电子邮件视图，然后转到 **URL** 或 **URL 单击** 选项卡。选择单个 URL 飞出视图有关该 URL 的单击的其他详细信息，包括与该单击关联的标记。</span><span class="sxs-lookup"><span data-stu-id="8011c-158">To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Select an individual URL flyout to view additional details about clicks for that URL, including tags associated with that click.</span></span>


### <a name="updated-timeline-view"></a><span data-ttu-id="8011c-159">更新的时间线视图</span><span class="sxs-lookup"><span data-stu-id="8011c-159">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-160">![URL 标记](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-160">![URL tags](../../media/tags-urls.png)</span></span>

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a><span data-ttu-id="8011c-161">威胁搜寻体验的改进 (即将推出的) </span><span class="sxs-lookup"><span data-stu-id="8011c-161">Improvements to the threat hunting experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="8011c-162">更新了电子邮件的威胁信息</span><span class="sxs-lookup"><span data-stu-id="8011c-162">Updated threat information for emails</span></span>

<span data-ttu-id="8011c-163">我们专注于改进平台和数据质量，以提高电子邮件记录的数据准确性和一致性。</span><span class="sxs-lookup"><span data-stu-id="8011c-163">We've focused on platform and data-quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="8011c-164">改进包括将传递前和传递后信息（如作为 ZAP 过程的一部分对电子邮件执行的操作）合并到单个记录中。</span><span class="sxs-lookup"><span data-stu-id="8011c-164">Improvements include consolidation of pre-delivery and post-delivery information, such as actions executed on an email as part of the ZAP process, into a single record.</span></span> <span data-ttu-id="8011c-165">还包括垃圾邮件裁定、实体级别威胁 (例如，哪个 URL 是恶意) ，以及最新的送达位置。</span><span class="sxs-lookup"><span data-stu-id="8011c-165">Additional details like spam verdict, entity-level threats (for example, which URL was malicious), and latest delivery locations are also included.</span></span>

<span data-ttu-id="8011c-166">这些更新后，将看到每封邮件的单个条目，而不管影响邮件的不同传递后事件如何。</span><span class="sxs-lookup"><span data-stu-id="8011c-166">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that affect the message.</span></span> <span data-ttu-id="8011c-167">操作可能包括 ZAP、手动修正 (这意味着管理员操作) 、动态传递等。</span><span class="sxs-lookup"><span data-stu-id="8011c-167">Actions can include ZAP, manual remediation (which means admin action), dynamic delivery, and so on.</span></span>

<span data-ttu-id="8011c-168">除了显示恶意软件和网络钓鱼威胁之外，您还可以看到与电子邮件关联的垃圾邮件裁定。</span><span class="sxs-lookup"><span data-stu-id="8011c-168">In addition to showing malware and phishing threats, you see the spam verdict associated with an email.</span></span> <span data-ttu-id="8011c-169">在电子邮件中，查看与电子邮件关联的所有威胁以及相应的检测技术。</span><span class="sxs-lookup"><span data-stu-id="8011c-169">Within the email, see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="8011c-170">电子邮件可以具有零个、一个或多个威胁。</span><span class="sxs-lookup"><span data-stu-id="8011c-170">An email can have zero, one, or multiple threats.</span></span> <span data-ttu-id="8011c-171">你将在电子邮件飞出 **的详细信息部分看到** 当前威胁。</span><span class="sxs-lookup"><span data-stu-id="8011c-171">You'll see the current threats in the **Details** section of the email flyout.</span></span> <span data-ttu-id="8011c-172">对于恶意软件 (网络钓鱼等多个威胁) ，检测技术字段显示威胁检测映射，这是识别威胁的检测技术。</span><span class="sxs-lookup"><span data-stu-id="8011c-172">For multiple threats (such as malware and phishing), the **Detection tech** field shows the threat-detection mapping, which is the detection technology that identified the threat.</span></span>

<span data-ttu-id="8011c-173">检测技术集现在包括新的检测方法以及垃圾邮件检测技术。</span><span class="sxs-lookup"><span data-stu-id="8011c-173">The set of detection technologies now includes new detection methods, as well as spam-detection technologies.</span></span> <span data-ttu-id="8011c-174">您可以使用同一组检测技术跨恶意软件、网络钓鱼、所有电子邮件 (不同的电子邮件视图筛选) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-174">You can use the same set of detection technologies to filter the results across the different email views (Malware, Phish, All Email).</span></span>

> [!NOTE]
> <span data-ttu-id="8011c-175">裁定分析不一定与实体关联。</span><span class="sxs-lookup"><span data-stu-id="8011c-175">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="8011c-176">例如，电子邮件可能分类为网络钓鱼或垃圾邮件，但没有标记有网络钓鱼/垃圾邮件裁定的 URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-176">As an example, an email might be classified as phish or spam, but there are no URLs that are stamped with a phish/spam verdict.</span></span> <span data-ttu-id="8011c-177">这是因为在分配裁定之前，筛选器还会评估电子邮件的内容和其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="8011c-177">This is because the filters also evaluate content and other details for an email before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="8011c-178">URL 中的威胁</span><span class="sxs-lookup"><span data-stu-id="8011c-178">Threats in URLs</span></span>

<span data-ttu-id="8011c-179">现在，可以在"电子邮件"飞出"详细信息"选项卡上看到 URL **的特定** 威胁。威胁可以是 *恶意软件*、*网络钓鱼、\*\*垃圾邮件* 或 *无*。) </span><span class="sxs-lookup"><span data-stu-id="8011c-179">You can now see the specific threat for a URL on the email flyout **Details** tab. The threat can be *malware*, *phish*, *spam*, or *none*.)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-180">![URL 威胁](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-180">![URL threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="8011c-181">更新了日程表 (即将推出的) </span><span class="sxs-lookup"><span data-stu-id="8011c-181">Updated timeline view (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-182">![更新的时间线视图](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-182">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="8011c-183">时间线视图标识所有传递和传递后事件。</span><span class="sxs-lookup"><span data-stu-id="8011c-183">Timeline view identifies all delivery and post-delivery events.</span></span> <span data-ttu-id="8011c-184">它包括有关在这些事件的子集时确定的威胁的信息。</span><span class="sxs-lookup"><span data-stu-id="8011c-184">It includes information about the threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="8011c-185">时间线视图还提供了有关使用 ZAP (手动修正) 执行任何其他操作的信息，以及该操作的结果。</span><span class="sxs-lookup"><span data-stu-id="8011c-185">Timeline view also provides information about any additional action taken (such as ZAP or manual remediation), along with the result of that action.</span></span> <span data-ttu-id="8011c-186">时间线视图信息包括：</span><span class="sxs-lookup"><span data-stu-id="8011c-186">Timeline view information includes:</span></span>

- <span data-ttu-id="8011c-187">**源：** 事件的源。</span><span class="sxs-lookup"><span data-stu-id="8011c-187">**Source:** Source of the event.</span></span> <span data-ttu-id="8011c-188">它可以是管理员/系统/用户。</span><span class="sxs-lookup"><span data-stu-id="8011c-188">It can be admin/system/user.</span></span>
- <span data-ttu-id="8011c-189">**事件：** 包括顶级事件，如原始传递、手动修正、ZAP、提交和动态传递。</span><span class="sxs-lookup"><span data-stu-id="8011c-189">**Event:** Includes top-level events like original delivery, manual remediation, ZAP, submissions, and dynamic delivery.</span></span>
- <span data-ttu-id="8011c-190">**操作：** 作为 ZAP 或管理员操作一部分执行的特定 (例如，软删除) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-190">**Action:** The specific action that was taken either as part of ZAP or admin action (for example, soft delete).</span></span>
- <span data-ttu-id="8011c-191">**威胁：** 涵盖 (识别的恶意软件、网络钓鱼) 垃圾邮件威胁。</span><span class="sxs-lookup"><span data-stu-id="8011c-191">**Threats:** Covers the threats (malware, phish, spam) identified at that point of time.</span></span>
- <span data-ttu-id="8011c-192">**结果/详细信息：** 有关操作结果详细信息，例如它是否作为 ZAP/admin 操作一部分执行。</span><span class="sxs-lookup"><span data-stu-id="8011c-192">**Result/Details:** More information about the result of the action, such as whether it was performed as part of ZAP/admin action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="8011c-193">原始和最新的送达位置</span><span class="sxs-lookup"><span data-stu-id="8011c-193">Original and latest delivery location</span></span>

<span data-ttu-id="8011c-194">目前，我们在电子邮件网格和电子邮件浮出控件中显示传递位置。</span><span class="sxs-lookup"><span data-stu-id="8011c-194">Currently, we surface delivery location in the email grid and email flyout.</span></span> <span data-ttu-id="8011c-195">The **Delivery location** field is getting renamed Original delivery **_location_*_.我们将引入另一个字段 _*_最新送达位置_**。</span><span class="sxs-lookup"><span data-stu-id="8011c-195">The **Delivery location** field is getting renamed **_Original delivery location_*_. And we're introducing another field, _*_Latest delivery location_**.</span></span>

<span data-ttu-id="8011c-196">**原始送达** 位置将提供有关电子邮件最初送达位置的更多信息。</span><span class="sxs-lookup"><span data-stu-id="8011c-196">**Original delivery location** will give more information about where an email was delivered initially.</span></span> <span data-ttu-id="8011c-197">**最新的送达位置** 将说明电子邮件在系统操作（如 *ZAP）* 或管理员操作（如 *移动到已删除项目）之后登录的位置*。</span><span class="sxs-lookup"><span data-stu-id="8011c-197">**Latest delivery location** will state where an email landed after system actions like *ZAP* or admin actions like *Move to deleted items*.</span></span> <span data-ttu-id="8011c-198">最新送达位置旨在告知管理员邮件的上次已知位置传递后或任何系统/管理员操作。</span><span class="sxs-lookup"><span data-stu-id="8011c-198">Latest delivery location is intended to tell admins the message's last-known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="8011c-199">它不包括对电子邮件的任何最终用户操作。</span><span class="sxs-lookup"><span data-stu-id="8011c-199">It doesn't include any end-user actions on the email.</span></span> <span data-ttu-id="8011c-200">例如，如果用户删除了邮件或将邮件移动到 archive/pst，则邮件"传递"位置将不会更新。</span><span class="sxs-lookup"><span data-stu-id="8011c-200">For example, if a user deleted a message or moved the message to archive/pst, the message "delivery" location won't be updated.</span></span> <span data-ttu-id="8011c-201">但是，如果系统操作更新了位置 (例如 ZAP 导致电子邮件移动到隔离邮箱) ，则最新送达位置将显示为"隔离"。</span><span class="sxs-lookup"><span data-stu-id="8011c-201">But if a system action updated the location (for example, ZAP resulting in an email moving to quarantine), **Latest delivery location** would show as "quarantine."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-202">![更新的传递位置](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-202">![Updated delivery locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="8011c-203">在某些情况下，传递位置 **和\*\*\*\*传递操作** 可能显示为"未知"：</span><span class="sxs-lookup"><span data-stu-id="8011c-203">There are a few cases where **Delivery location** and **Delivery action** may show as "unknown":</span></span>
>
> - <span data-ttu-id="8011c-204">如果邮件已送达，您可能会看到"送达位置"和"送达位置"为"未知"，但收件箱规则将邮件移动到默认文件夹 (如草稿或存档) 而不是"收件箱"或"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="8011c-204">You might see **Delivery location** as "delivered" and **Delivery location** as "unknown" if the message was delivered, but an Inbox rule moved the message to a default folder (such as Draft or Archive) instead of to the Inbox or Junk Email folder.</span></span>
>
> - <span data-ttu-id="8011c-205">**如果已尝试** 执行管理/系统操作（ (ZAP) ，但未找到邮件，则最新的传递位置可能未知。</span><span class="sxs-lookup"><span data-stu-id="8011c-205">**Latest delivery location** can be unknown if an admin/system action (such as ZAP) was attempted, but the message wasn't found.</span></span> <span data-ttu-id="8011c-206">通常，该操作发生在用户移动或删除邮件之后。</span><span class="sxs-lookup"><span data-stu-id="8011c-206">Typically, the action happens after the user  moved or deleted the message.</span></span> <span data-ttu-id="8011c-207">在这种情况下，请验证 **日程表视图中的"结果/** 详细信息"列。</span><span class="sxs-lookup"><span data-stu-id="8011c-207">In such cases, verify the **Result/Details** column in timeline view.</span></span> <span data-ttu-id="8011c-208">查找"用户移动或删除的邮件"语句。</span><span class="sxs-lookup"><span data-stu-id="8011c-208">Look for the statement "Message moved or deleted by the user."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-209">![时间线的传递位置](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-209">![Delivery locations for timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="8011c-210">其他操作</span><span class="sxs-lookup"><span data-stu-id="8011c-210">Additional actions</span></span>

<span data-ttu-id="8011c-211">*在电子邮件* 传递后应用了其他操作。</span><span class="sxs-lookup"><span data-stu-id="8011c-211">*Additional actions* were applied after delivery of the email.</span></span> <span data-ttu-id="8011c-212">它们可以包括 *ZAP、 (* 管理员采取的操作（如软删除) 、动态传递和重新处理 *(）* 针对被反向检测为) 。 </span><span class="sxs-lookup"><span data-stu-id="8011c-212">They can include *ZAP*, *manual remediation* (action taken by an Admin such as soft delete), *dynamic delivery*, and *reprocessed* (for an email that was retroactively detected as good).</span></span>

> [!NOTE]
> - <span data-ttu-id="8011c-213">作为挂起更改的一部分，当前在"传递操作"筛选器中显示"由 ZAP 删除"值将消失。</span><span class="sxs-lookup"><span data-stu-id="8011c-213">As part of the pending changes, the "Removed by ZAP" value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="8011c-214">你将有一种方法通过"其他操作"通过 ZAP 尝试搜索 **所有电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="8011c-214">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span></span>
>
> - <span data-ttu-id="8011c-215">检测技术和其他操作将具有新的字段和值 **， (适用于** ZAP) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-215">There will be new fields and values for **Detection technologies** and **Additional actions** (especially for ZAP scenarios).</span></span> <span data-ttu-id="8011c-216">您需要评估现有的已保存查询和跟踪查询，以确保它们使用新值。</span><span class="sxs-lookup"><span data-stu-id="8011c-216">You'll need to evaluate your existing saved queries and tracked queries to make sure they work with the new values.</span></span>

> [!div class="mx-imgBorder"]

> ![资源管理器中的其他操作](../../media/Additional_Actions.png)

### <a name="system-overrides"></a><span data-ttu-id="8011c-218">系统覆盖</span><span class="sxs-lookup"><span data-stu-id="8011c-218">System overrides</span></span>

<span data-ttu-id="8011c-219">*系统覆盖* 使您能够对邮件的预定传递位置进行例外。</span><span class="sxs-lookup"><span data-stu-id="8011c-219">*System overrides* enable you to make exceptions to the intended delivery location of a message.</span></span> <span data-ttu-id="8011c-220">根据筛选堆栈确定的威胁和其他检测，你可以覆盖系统提供的传递位置。</span><span class="sxs-lookup"><span data-stu-id="8011c-220">You override the delivery location provided by the system, based on the threats and other detections identified by the filtering stack.</span></span> <span data-ttu-id="8011c-221">可以通过租户或用户策略设置系统覆盖，以根据策略的建议传递邮件。</span><span class="sxs-lookup"><span data-stu-id="8011c-221">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="8011c-222">替代可以标识由于配置差异（如用户设置过宽的安全发件人策略）而意外传递恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="8011c-222">Overrides can identify unintentional delivery of malicious messages due to configurations gaps, such as an overly broad Safe Sender policy set by a user.</span></span> <span data-ttu-id="8011c-223">这些替代值可以是：</span><span class="sxs-lookup"><span data-stu-id="8011c-223">These override values can be:</span></span>

- <span data-ttu-id="8011c-224">用户策略允许：用户在邮箱级别创建策略以允许域或发件人。</span><span class="sxs-lookup"><span data-stu-id="8011c-224">Allowed by user policy: A user creates policies at the mailbox level to allows domains or senders.</span></span>
- <span data-ttu-id="8011c-225">被用户策略阻止：用户在邮件框级别创建策略以阻止域或发件人。</span><span class="sxs-lookup"><span data-stu-id="8011c-225">Blocked by user policy: A user creates policies at the mail box level to block domains or senders.</span></span>
- <span data-ttu-id="8011c-226">组织策略允许：组织的安全团队设置策略或 Exchange 邮件流规则 (也称为传输规则) ，以允许组织中的用户使用发件人和域。</span><span class="sxs-lookup"><span data-stu-id="8011c-226">Allowed by org policy: The organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="8011c-227">这适用于一组用户或整个组织。</span><span class="sxs-lookup"><span data-stu-id="8011c-227">This can be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="8011c-228">被组织策略阻止：组织的安全团队设置策略或邮件流规则，以阻止组织中用户的发件人、域、邮件语言或源 IP。</span><span class="sxs-lookup"><span data-stu-id="8011c-228">Blocked by org policy: The organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="8011c-229">这可应用于一组用户或整个组织。</span><span class="sxs-lookup"><span data-stu-id="8011c-229">This can be applied to a set of users or the entire organization.</span></span>
- <span data-ttu-id="8011c-230">组织策略阻止的文件扩展名：组织的安全团队通过反恶意软件策略设置阻止文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="8011c-230">File extension blocked by org policy: An organization's security team blocks a file name extension through the anti-malware policy settings.</span></span> <span data-ttu-id="8011c-231">这些值现在将显示在电子邮件详细信息中，以帮助进行调查。</span><span class="sxs-lookup"><span data-stu-id="8011c-231">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="8011c-232">Secops 团队还可使用丰富的筛选功能筛选阻止的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="8011c-232">Secops teams can also use the rich-filtering capability to filter on blocked file extensions.</span></span>

<span data-ttu-id="8011c-233">[![资源管理器中的系统覆盖](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8011c-233">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-234">![资源管理器中的系统替代网格](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-234">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-for-the-url-and-clicks-experience"></a><span data-ttu-id="8011c-235">URL 和单击体验的改进</span><span class="sxs-lookup"><span data-stu-id="8011c-235">Improvements for the URL and clicks experience</span></span>

<span data-ttu-id="8011c-236">这些改进包括：</span><span class="sxs-lookup"><span data-stu-id="8011c-236">The improvements include:</span></span>

- <span data-ttu-id="8011c-237">显示完整的单击 URL (包括作为 URL 链接的一) **单击部分的任何** 查询参数。</span><span class="sxs-lookup"><span data-stu-id="8011c-237">Show the full clicked URL (including any query parameters that are part of the URL) in the **Clicks** section of the URL flyout.</span></span> <span data-ttu-id="8011c-238">目前，URL 域和路径显示在标题栏中。</span><span class="sxs-lookup"><span data-stu-id="8011c-238">Currently, the URL domain and path appear in the title bar.</span></span> <span data-ttu-id="8011c-239">我们将扩展该信息以显示完整 URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-239">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="8011c-240">跨 URL 筛选器 (*URL* 域与 *URL* 域和路径的修复) ：更新会影响对包含 URL/单击裁定的邮件的搜索。</span><span class="sxs-lookup"><span data-stu-id="8011c-240">Fixes across URL filters (*URL* versus *URL domain* versus *URL domain and path*): The updates affect searching for messages that contain a URL/click verdict.</span></span> <span data-ttu-id="8011c-241">我们启用了协议不可知搜索支持，因此无需使用 ，即可搜索 `http` URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-241">We enabled support for protocol-agnostic searches, so you can search for a URL without using `http`.</span></span> <span data-ttu-id="8011c-242">默认情况下，除非明确指定了其他值，否则 URL 搜索将映射到 http。</span><span class="sxs-lookup"><span data-stu-id="8011c-242">By default, the URL search maps to http, unless another value is explicitly specified.</span></span> <span data-ttu-id="8011c-243">例如：</span><span class="sxs-lookup"><span data-stu-id="8011c-243">For example:</span></span>

   -  <span data-ttu-id="8011c-244">在"URL"、"URL 域"和"URL 域"和"路径"筛选器字段中使用 和 `http://` **不带前缀进行** 搜索。  </span><span class="sxs-lookup"><span data-stu-id="8011c-244">Search with and without the `http://` prefix in the **URL**, **URL Domain**, and **URL Domain and Path** filter fields.</span></span> <span data-ttu-id="8011c-245">搜索应显示相同的结果。</span><span class="sxs-lookup"><span data-stu-id="8011c-245">The searches should show the same results.</span></span>

   -  <span data-ttu-id="8011c-246">在 URL `https://` 中搜索 **前缀**。</span><span class="sxs-lookup"><span data-stu-id="8011c-246">Search for the `https://` prefix in **URL**.</span></span> <span data-ttu-id="8011c-247">未指定任何值时， `http://` 将假定前缀。</span><span class="sxs-lookup"><span data-stu-id="8011c-247">When no value is specified, the `http://` prefix is assumed.</span></span>

   - <span data-ttu-id="8011c-248">`/`在 URL 路径、URL 域 **、URL** 域和路径字段的开头和结尾 **忽略**。</span><span class="sxs-lookup"><span data-stu-id="8011c-248">`/` is ignored at the beginning and end of the **URL path**, **URL Domain**, **URL domain and path** fields.</span></span> <span data-ttu-id="8011c-249">`/` 将忽略 **URL** 字段的末尾。</span><span class="sxs-lookup"><span data-stu-id="8011c-249">`/` at the end of the **URL** field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="8011c-250">网络钓鱼可信度</span><span class="sxs-lookup"><span data-stu-id="8011c-250">Phish confidence level</span></span>

<span data-ttu-id="8011c-251">网络钓鱼可信度有助于确定电子邮件被分类为"网络钓鱼"的可信度。</span><span class="sxs-lookup"><span data-stu-id="8011c-251">Phish confidence level helps identify the degree of confidence with which an email was categorized as "phish."</span></span> <span data-ttu-id="8011c-252">两个可能的值是 *High* 和 *Normal*。</span><span class="sxs-lookup"><span data-stu-id="8011c-252">The two possible values are *High* and *Normal*.</span></span> <span data-ttu-id="8011c-253">在初始阶段，此筛选器将仅在威胁资源管理器的网络钓鱼视图中可用。</span><span class="sxs-lookup"><span data-stu-id="8011c-253">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="8011c-254">[![资源管理器中的网络钓鱼可信度](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8011c-254">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="8011c-255">ZAP URL 信号</span><span class="sxs-lookup"><span data-stu-id="8011c-255">ZAP URL signal</span></span>

<span data-ttu-id="8011c-256">ZAP URL 信号通常用于 ZAP 网络钓鱼警报方案，其中电子邮件被标识为钓鱼邮件，在传递后被删除。</span><span class="sxs-lookup"><span data-stu-id="8011c-256">The ZAP URL signal is typically used for ZAP Phish alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="8011c-257">此信号将警报与资源管理器中的相应结果连接在一起。</span><span class="sxs-lookup"><span data-stu-id="8011c-257">This signal connects the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="8011c-258">它是警报的 IIC 之一。</span><span class="sxs-lookup"><span data-stu-id="8011c-258">It's one of the IOCs for the alert.</span></span>

<span data-ttu-id="8011c-259">为了改进搜寻过程，我们更新了威胁资源管理器和实时检测，使搜寻体验更加一致。</span><span class="sxs-lookup"><span data-stu-id="8011c-259">To improve the hunting process, we've updated Threat Explorer and Real-time detections to make the hunting experience more consistent.</span></span> <span data-ttu-id="8011c-260">此处概述了这些更改：</span><span class="sxs-lookup"><span data-stu-id="8011c-260">The changes are outlined here:</span></span>

- [<span data-ttu-id="8011c-261">时区改进</span><span class="sxs-lookup"><span data-stu-id="8011c-261">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="8011c-262">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="8011c-262">Update in the refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="8011c-263">要添加到筛选器的图表深化</span><span class="sxs-lookup"><span data-stu-id="8011c-263">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="8011c-264">在产品信息更新中</span><span class="sxs-lookup"><span data-stu-id="8011c-264">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="8011c-265">按用户标记筛选</span><span class="sxs-lookup"><span data-stu-id="8011c-265">Filter by user tags</span></span>

<span data-ttu-id="8011c-266">现在，你可以对系统或自定义用户标记进行排序和筛选，以快速了解威胁的范围。</span><span class="sxs-lookup"><span data-stu-id="8011c-266">You can now sort and filter on system or custom user tags to quickly grasp the scope of threats.</span></span> <span data-ttu-id="8011c-267">若要了解更多信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="8011c-267">To learn more, see [User tags](user-tags.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8011c-268">按用户标记进行筛选和排序目前处于公共预览阶段。</span><span class="sxs-lookup"><span data-stu-id="8011c-268">Filtering and sorting by user tags is currently in public preview.</span></span> <span data-ttu-id="8011c-269">此功能在商业发行之前可能会进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="8011c-269">This functionality may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8011c-270">Microsoft 对提供的信息不做出明示或暗示的担保。</span><span class="sxs-lookup"><span data-stu-id="8011c-270">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

![资源管理器中的标记列](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a><span data-ttu-id="8011c-272">时区改进</span><span class="sxs-lookup"><span data-stu-id="8011c-272">Timezone improvements</span></span>

<span data-ttu-id="8011c-273">你将在门户和导出的数据中查看电子邮件记录的时区。</span><span class="sxs-lookup"><span data-stu-id="8011c-273">You'll see the time zone for the email records in the Portal as well as for Exported data.</span></span> <span data-ttu-id="8011c-274">它将在电子邮件网格、详细信息飞出控件、电子邮件时间线和类似电子邮件等体验中可见，因此电子邮件结果集清晰。</span><span class="sxs-lookup"><span data-stu-id="8011c-274">It will be visible across experiences like Email Grid, Details flyout, Email Timeline, and Similar Emails, so the time zone for the result set is clear.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-275">![在资源管理器中查看时区](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-275">![View time zone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="8011c-276">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="8011c-276">Update in the refresh process</span></span>

<span data-ttu-id="8011c-277">一些用户已评论过与自动刷新 (混淆，例如，一旦更改日期，页面就会刷新) ，并手动刷新 (筛选器) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-277">Some users have commented about confusion with automatic refresh (for example, as soon as you change the date, the page refreshes) and manual refresh (for other filters).</span></span> <span data-ttu-id="8011c-278">同样，删除筛选器也会导致自动刷新。</span><span class="sxs-lookup"><span data-stu-id="8011c-278">Similarly, removing filters leads to automatic refresh.</span></span> <span data-ttu-id="8011c-279">在修改查询时更改筛选器可能会导致搜索体验不一致。</span><span class="sxs-lookup"><span data-stu-id="8011c-279">Changing filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="8011c-280">为了解决这些问题，我们将迁移到手动筛选机制。</span><span class="sxs-lookup"><span data-stu-id="8011c-280">To resolve these issues, we're moving to a manual-filtering mechanism.</span></span>

<span data-ttu-id="8011c-281">从体验的角度来看，用户可以从筛选器集和日期) 应用和删除不同的筛选器 (范围，并选择"刷新"按钮以在定义查询后筛选结果。</span><span class="sxs-lookup"><span data-stu-id="8011c-281">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set and date) and select the refresh button to filter the results after they've defined the query.</span></span> <span data-ttu-id="8011c-282">屏幕上现在也强调刷新按钮。</span><span class="sxs-lookup"><span data-stu-id="8011c-282">The refresh button is also now emphasized on the screen.</span></span> <span data-ttu-id="8011c-283">我们还更新了相关工具提示和产品内文档。</span><span class="sxs-lookup"><span data-stu-id="8011c-283">We've also updated the related tooltips and in-product documentation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-284">![选择"刷新"筛选结果](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-284">![Select Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="8011c-285">要添加到筛选器的图表深化</span><span class="sxs-lookup"><span data-stu-id="8011c-285">Chart drilldown to add to filters</span></span>

<span data-ttu-id="8011c-286">现在，你可以绘制图例值图表以将它们添加为筛选器。</span><span class="sxs-lookup"><span data-stu-id="8011c-286">You can now chart legend values to add them as filters.</span></span> <span data-ttu-id="8011c-287">选择" **刷新"** 按钮以筛选结果。</span><span class="sxs-lookup"><span data-stu-id="8011c-287">Select the **Refresh** button to filter the results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-288">![向下钻取图表以筛选](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-288">![Drill down through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="8011c-289">产品内信息更新</span><span class="sxs-lookup"><span data-stu-id="8011c-289">In-product information updates</span></span>

<span data-ttu-id="8011c-290">现在可在产品内获得其他详细信息，如网格中的搜索结果总数 (请参阅下面的) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-290">Additional details are now available within the product, such as the total number of search results within the grid (see below).</span></span> <span data-ttu-id="8011c-291">我们改进了标签、错误消息和工具提示，以提供有关筛选器、搜索体验和搜索结果集。</span><span class="sxs-lookup"><span data-stu-id="8011c-291">We've improved labels, error messages, and tooltips to provide more information about the filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-292">![查看产品内信息](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-292">![View in-product information](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="8011c-293">威胁资源管理器中的扩展功能</span><span class="sxs-lookup"><span data-stu-id="8011c-293">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="8011c-294">主要目标用户</span><span class="sxs-lookup"><span data-stu-id="8011c-294">Top targeted users</span></span>

<span data-ttu-id="8011c-295">今天，我们在电子邮件的"恶意软件"视图中的"主要恶意软件系列"部分公开 **了主要目标** 用户列表。</span><span class="sxs-lookup"><span data-stu-id="8011c-295">Today we expose the list of the top targeted users in the Malware view for emails, in the **Top Malware Families** section.</span></span> <span data-ttu-id="8011c-296">我们还将在"钓鱼邮件"和"所有电子邮件"视图中扩展此视图。</span><span class="sxs-lookup"><span data-stu-id="8011c-296">We'll be extending this view in the Phish and All Email views as well.</span></span> <span data-ttu-id="8011c-297">你将能够看到前五个目标用户，以及每个用户针对相应视图的尝试次数。</span><span class="sxs-lookup"><span data-stu-id="8011c-297">You'll be able to see the top-five targeted users, along with the number of attempts for each user for the corresponding view.</span></span> <span data-ttu-id="8011c-298">例如，对于网络钓鱼视图，你将看到网络钓鱼尝试次数。</span><span class="sxs-lookup"><span data-stu-id="8011c-298">For example, for Phish view, you'll see the number of Phish attempts.</span></span>

<span data-ttu-id="8011c-299">你将能够导出目标用户列表（最多 3，000 个）以及每个电子邮件视图的脱机分析尝试次数。</span><span class="sxs-lookup"><span data-stu-id="8011c-299">You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="8011c-300">此外，选择尝试次数 (例如，在) 下的图像中尝试 13 次将在威胁资源管理器中打开筛选视图，以便你可以查看有关该用户的电子邮件和威胁的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="8011c-300">In addition, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-301">![主要目标用户](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-301">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="8011c-302">Exchange 传输规则</span><span class="sxs-lookup"><span data-stu-id="8011c-302">Exchange transport rules</span></span>

<span data-ttu-id="8011c-303">作为数据扩充的一部分，你将能够看到应用于邮件的所有 (ETR) Exchange 传输规则。</span><span class="sxs-lookup"><span data-stu-id="8011c-303">As part of data enrichment, you'll be able to see all the different Exchange transport rules (ETR) that were applied to a message.</span></span> <span data-ttu-id="8011c-304">此信息将在电子邮件网格视图中提供。</span><span class="sxs-lookup"><span data-stu-id="8011c-304">This information will be available in the Email grid view.</span></span> <span data-ttu-id="8011c-305">若要查看它，请选择网格 **中的列** 选项，然后从列选项添加 **Exchange** 传输规则。</span><span class="sxs-lookup"><span data-stu-id="8011c-305">To view it,  select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="8011c-306">它还将在电子邮件的" **详细信息** "飞出内容上可见。</span><span class="sxs-lookup"><span data-stu-id="8011c-306">It will also be visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="8011c-307">您将能够查看已应用于邮件的传输规则的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="8011c-307">You'll be able to see both the GUID and the name of the transport rules that were applied to the message.</span></span> <span data-ttu-id="8011c-308">您将能够使用传输规则的名称搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="8011c-308">You'll be able to search for the messages by using the name of the transport rule.</span></span> <span data-ttu-id="8011c-309">这是一个"包含"搜索，这意味着您也可以执行部分搜索。</span><span class="sxs-lookup"><span data-stu-id="8011c-309">This is a "Contains" search, which means you can do partial searches as well.</span></span>

#### <a name="important-note"></a><span data-ttu-id="8011c-310">重要说明：</span><span class="sxs-lookup"><span data-stu-id="8011c-310">Important note:</span></span>

<span data-ttu-id="8011c-311">ETR 搜索和名称可用性取决于分配给您的特定角色。</span><span class="sxs-lookup"><span data-stu-id="8011c-311">ETR search and name availability depend on the specific role that's assigned to you.</span></span> <span data-ttu-id="8011c-312">您需要具有以下角色/权限之一才能查看 ETR 名称和搜索。</span><span class="sxs-lookup"><span data-stu-id="8011c-312">You need to have one of the following roles/permissions to view the ETR names and search.</span></span> <span data-ttu-id="8011c-313">如果没有分配任何这些角色，则看不到传输规则的名称，也看不到使用 ETR 名称搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="8011c-313">If you don't have any of these roles assigned to you, you can't see the names of the transport rules or search for messages by using ETR names.</span></span> <span data-ttu-id="8011c-314">但是，您可以在电子邮件详细信息中查看 ETR 标签和 GUID 信息。</span><span class="sxs-lookup"><span data-stu-id="8011c-314">However, you could see the ETR label and GUID information in the Email Details.</span></span> <span data-ttu-id="8011c-315">电子邮件网格、电子邮件飞出、筛选器和导出中的其他记录查看体验不受影响。</span><span class="sxs-lookup"><span data-stu-id="8011c-315">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>

- <span data-ttu-id="8011c-316">仅 EXO - 数据丢失防护：全部</span><span class="sxs-lookup"><span data-stu-id="8011c-316">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="8011c-317">仅 EXO - O365SupportViewConfig：全部</span><span class="sxs-lookup"><span data-stu-id="8011c-317">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="8011c-318">Microsoft Azure Active Directory 或 EXO - 安全管理员：全部</span><span class="sxs-lookup"><span data-stu-id="8011c-318">Microsoft Azure Active Directory or EXO - Security Admin: All</span></span>
- <span data-ttu-id="8011c-319">AAD 或 EXO - 安全读者：全部</span><span class="sxs-lookup"><span data-stu-id="8011c-319">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="8011c-320">仅 EXO - 传输规则：全部</span><span class="sxs-lookup"><span data-stu-id="8011c-320">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="8011c-321">仅 EXO - View-Only配置：全部</span><span class="sxs-lookup"><span data-stu-id="8011c-321">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="8011c-322">在电子邮件网格、详细信息飞出控件和导出的 CSV 中，ETR 将显示一个名称/GUID，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8011c-322">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-323">![Exchange 传输规则](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-323">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="8011c-324">入站连接器</span><span class="sxs-lookup"><span data-stu-id="8011c-324">Inbound connectors</span></span>

<span data-ttu-id="8011c-325">连接器是一组说明，用于自定义电子邮件在 Microsoft 365 或 Office 365 组织之间流动和流出。</span><span class="sxs-lookup"><span data-stu-id="8011c-325">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="8011c-326">它们使您能够应用任何安全限制或控件。</span><span class="sxs-lookup"><span data-stu-id="8011c-326">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="8011c-327">在威胁资源管理器中，你现在可以查看与电子邮件相关的连接器，然后使用连接器名称搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8011c-327">Within Threat Explorer, you can now view the connectors that are related to an email and search for emails by using connector names.</span></span>

<span data-ttu-id="8011c-328">连接器的搜索本质上是"包含"的，这意味着部分关键字搜索也应正常工作。</span><span class="sxs-lookup"><span data-stu-id="8011c-328">The search for connectors is "contains" in nature, which means partial keyword searches should work as well.</span></span> <span data-ttu-id="8011c-329">在主网格视图、"详细信息"飞出控件和导出的 CSV 中，连接器以名称/GUID 格式显示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8011c-329">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown here:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-330">![连接器详细信息](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-330">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="8011c-331">威胁资源管理器和实时检测中的新功能</span><span class="sxs-lookup"><span data-stu-id="8011c-331">New features in Threat Explorer and Real-time detections</span></span>

- [<span data-ttu-id="8011c-332">查看发送给模拟用户和域的网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="8011c-332">View phishing emails sent to impersonated users and domains</span></span>](#view-phishing-emails-sent-to-impersonated-users-and-domains)
-  [<span data-ttu-id="8011c-333">预览电子邮件头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="8011c-333">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="8011c-334">电子邮件时间线</span><span class="sxs-lookup"><span data-stu-id="8011c-334">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="8011c-335">导出 URL 单击数据</span><span class="sxs-lookup"><span data-stu-id="8011c-335">Export URL click data</span></span>](#export-url-click-data)

### <a name="view-phishing-emails-sent-to-impersonated-users-and-domains"></a><span data-ttu-id="8011c-336">查看发送给模拟用户和域的网络钓鱼电子邮件</span><span class="sxs-lookup"><span data-stu-id="8011c-336">View phishing emails sent to impersonated users and domains</span></span>

<span data-ttu-id="8011c-337">若要识别针对被模拟用户的用户和域的网络钓鱼尝试，必须添加到用户 *列表中以保护*。</span><span class="sxs-lookup"><span data-stu-id="8011c-337">To identify phishing attempts against users and domains that are impersonated users must be added to the list of *Users to protect*.</span></span> <span data-ttu-id="8011c-338">对于域，管理员必须启用 *"组织* 域"，或向"域"添加域名 *才能保护*。</span><span class="sxs-lookup"><span data-stu-id="8011c-338">For domains, admins must either enable *Organization domains*, or add a domain name to *Domains to protect*.</span></span> <span data-ttu-id="8011c-339">要保护的域位于"模拟"部分中的" *防* 钓鱼 *策略"* 页面上。</span><span class="sxs-lookup"><span data-stu-id="8011c-339">The domains to protect are found on the *Anti-Phishing policy page* in the *Impersonation* section.</span></span>

<span data-ttu-id="8011c-340">若要查看网络钓鱼邮件并搜索模拟的用户或域，请使用资源管理器> [电子邮件和网络钓鱼](threat-explorer-views.md) "视图。</span><span class="sxs-lookup"><span data-stu-id="8011c-340">To review phish messages and search for impersonated users or domains, use the [Email > Phish view](threat-explorer-views.md) of Explorer.</span></span>

<span data-ttu-id="8011c-341">此示例使用威胁资源管理器。</span><span class="sxs-lookup"><span data-stu-id="8011c-341">This example uses Threat Explorer.</span></span>

1. <span data-ttu-id="8011c-342">在安全 [&合规 (](https://protection.office.com) 中，选择"威胁>资源管理器 (或实时 https://protection.office.com)) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-342">In the [Security & Compliance Center](https://protection.office.com) (https://protection.office.com), choose Threat management > Explorer (or Real-time detections).</span></span>

2. <span data-ttu-id="8011c-343">在"视图"菜单中，选择"电子邮件>钓鱼邮件"。</span><span class="sxs-lookup"><span data-stu-id="8011c-343">In the View menu, choose Email > Phish.</span></span>

   <span data-ttu-id="8011c-344">可以在此处选择 **模拟域或\*\*\*\*模拟用户**。</span><span class="sxs-lookup"><span data-stu-id="8011c-344">Here you can choose **impersonated domain** or **impersonated user**.</span></span>

3. <span data-ttu-id="8011c-345">**选择\*\*\*\*"模拟域"，** 然后在文本框中键入受保护的域。</span><span class="sxs-lookup"><span data-stu-id="8011c-345">**EITHER** select **Impersonated domain**, and then type a protected domain in the textbox.</span></span>

   <span data-ttu-id="8011c-346">例如，搜索 *contoso、contoso.com* 或 *contoso.com.au\*\*等受保护的域名*。</span><span class="sxs-lookup"><span data-stu-id="8011c-346">For example, search for protected domain names like *contoso*, *contoso.com*, or *contoso.com.au*.</span></span>

4. <span data-ttu-id="8011c-347">Select the Subject of any message under the Email tab > Details tab to see additional impersonation information like Impersonated Domain / Detected location.</span><span class="sxs-lookup"><span data-stu-id="8011c-347">Select the Subject of any message under the Email tab > Details tab to see additional impersonation information like Impersonated Domain / Detected location.</span></span>

5. <span data-ttu-id="8011c-348">**OR** 选择 **"模拟用户** "，在文本框中键入受保护的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8011c-348">**OR** Select **Impersonated user** and type a protected user's email address in the textbox.</span></span>

6. <span data-ttu-id="8011c-349">在"**电子邮件"\*\*\*\*选项卡"详细信息**"选项卡下选择任何邮件的主题，以查看有关用户或域的其他模拟信息和  >  检测到 *的位置*。</span><span class="sxs-lookup"><span data-stu-id="8011c-349">Select the **Subject** of any message under **Email tab** > **Details tab** to see additional impersonation information about the user or domain, and the *Detected location*.</span></span>

:::image type="content" source="../../media/threat-ex-views-impersonated-user-image.png" alt-text="显示检测位置和检测到的威胁的受保护用户的&quot;威胁资源管理器&quot;详细信息窗格 (冒充用户或) 。":::

> [!TIP]
> <span data-ttu-id="8011c-351">**为了获得最佳结果**，请使用 *完整电子邮件地址* 来搜索受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="8011c-351">**For best results**, use *full email addresses* to search protected users.</span></span> <span data-ttu-id="8011c-352">例如，在调查用户模拟时，如果搜索 *firstname.lastname@contoso.com，您将* 更快、更成功地找到受保护的用户。</span><span class="sxs-lookup"><span data-stu-id="8011c-352">You will find your protected user quicker and more successfully if you search for *firstname.lastname@contoso.com*, for example, when investigating user impersonation.</span></span> <span data-ttu-id="8011c-353">搜索受保护的域时，搜索将接受根域 (contoso.com，例如) ，域名 (*contoso*) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-353">When searching for a protected domain the search will take the root domain (contoso.com, for example), and the domain name (*contoso*).</span></span> <span data-ttu-id="8011c-354">搜索根域 contoso.com将同时返回 contoso.com 和域名 *contoso 的模拟*。 </span><span class="sxs-lookup"><span data-stu-id="8011c-354">Searching for the root domain *contoso.com* will return both impersonations of *contoso.com* and the domain name *contoso*.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="8011c-355">预览电子邮件头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="8011c-355">Preview email header and download email body</span></span>

<span data-ttu-id="8011c-356">你现在可以在威胁资源管理器中预览电子邮件头并下载电子邮件正文。管理员可以分析下载的邮件头/电子邮件中的威胁。</span><span class="sxs-lookup"><span data-stu-id="8011c-356">You can now preview an email header and download the email body in Threat Explorer Admins can analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="8011c-357">因为下载电子邮件可能会暴露信息的风险，所以此过程由基于角色的访问控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-357">Because downloading email messages can risk exposure of information, this process is controlled by role-based access control (RBAC).</span></span> <span data-ttu-id="8011c-358">必须将新角色 *Preview* 添加到另一个角色组 (如安全操作或安全管理员) ，以授予在全电子邮件视图中下载邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="8011c-358">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails in all-email messages view.</span></span> <span data-ttu-id="8011c-359">但是，查看电子邮件头不需要任何其他角色 (在威胁资源管理器中查看邮件所需的角色) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-359">However, viewing email header does not require any additional role (other than what is required to view messages in Threat Explorer).</span></span>

<span data-ttu-id="8011c-360">资源管理器和实时检测还将获得新字段，这些字段提供电子邮件到达位置的更完整图片。</span><span class="sxs-lookup"><span data-stu-id="8011c-360">Explorer and Real-time detections will also get new fields that provide a more complete picture of where your email messages land.</span></span> <span data-ttu-id="8011c-361">这些更改使搜寻安全操作变得更加简单。</span><span class="sxs-lookup"><span data-stu-id="8011c-361">These changes  make hunting easier for Security Ops.</span></span> <span data-ttu-id="8011c-362">但主要结果是你可以一目了然地知道问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="8011c-362">But the main result is you can know the location of problem email messages at a glance.</span></span>

<span data-ttu-id="8011c-363">如何完成此操作？</span><span class="sxs-lookup"><span data-stu-id="8011c-363">How is this done?</span></span> <span data-ttu-id="8011c-364">传递状态现在分为两列：</span><span class="sxs-lookup"><span data-stu-id="8011c-364">Delivery status is now broken out into two columns:</span></span>

- <span data-ttu-id="8011c-365">**传递操作** - 电子邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="8011c-365">**Delivery action** - Status of the email.</span></span>
- <span data-ttu-id="8011c-366">**传递位置** - 电子邮件的路由位置。</span><span class="sxs-lookup"><span data-stu-id="8011c-366">**Delivery location** - Where the email was routed.</span></span>

<span data-ttu-id="8011c-367">*传递* 操作是对现有策略或检测对电子邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="8011c-367">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="8011c-368">以下是电子邮件的可能操作：</span><span class="sxs-lookup"><span data-stu-id="8011c-368">Here are the possible actions for an email:</span></span>

|<span data-ttu-id="8011c-369">已传递</span><span class="sxs-lookup"><span data-stu-id="8011c-369">Delivered</span></span>|<span data-ttu-id="8011c-370">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="8011c-370">Junked</span></span>|<span data-ttu-id="8011c-371">Blocked</span><span class="sxs-lookup"><span data-stu-id="8011c-371">Blocked</span></span>|<span data-ttu-id="8011c-372">已替换</span><span class="sxs-lookup"><span data-stu-id="8011c-372">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="8011c-373">电子邮件已传递到用户的收件箱或文件夹，用户可以访问它。</span><span class="sxs-lookup"><span data-stu-id="8011c-373">Email was delivered to the inbox or folder of a user, and the user can access it.</span></span>|<span data-ttu-id="8011c-374">电子邮件已发送到用户的"垃圾邮件"或"已删除"文件夹，用户可以访问它。</span><span class="sxs-lookup"><span data-stu-id="8011c-374">Email was sent to the user's Junk  or Deleted folder, and the user can access it.</span></span>|<span data-ttu-id="8011c-375">被隔离、失败或已丢弃的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8011c-375">Emails that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="8011c-376">用户无法访问这些邮件。</span><span class="sxs-lookup"><span data-stu-id="8011c-376">These mails are inaccessible to the user.</span></span>|<span data-ttu-id="8011c-377">电子邮件具有由 .txt 文件取代的恶意附件，这些文件指出附件是恶意附件。</span><span class="sxs-lookup"><span data-stu-id="8011c-377">Email had malicious attachments replaced by .txt files that state the attachment was malicious.</span></span>|

<span data-ttu-id="8011c-378">下面是用户可以看到和看不到的：</span><span class="sxs-lookup"><span data-stu-id="8011c-378">Here is what the user can and can't see:</span></span>

|<span data-ttu-id="8011c-379">最终用户可访问</span><span class="sxs-lookup"><span data-stu-id="8011c-379">Accessible to end users</span></span>|<span data-ttu-id="8011c-380">最终用户无法访问</span><span class="sxs-lookup"><span data-stu-id="8011c-380">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="8011c-381">已传递</span><span class="sxs-lookup"><span data-stu-id="8011c-381">Delivered</span></span>|<span data-ttu-id="8011c-382">Blocked</span><span class="sxs-lookup"><span data-stu-id="8011c-382">Blocked</span></span>|
|<span data-ttu-id="8011c-383">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="8011c-383">Junked</span></span>|<span data-ttu-id="8011c-384">已替换</span><span class="sxs-lookup"><span data-stu-id="8011c-384">Replaced</span></span>|

<span data-ttu-id="8011c-385">**传递** 位置显示运行传递后的策略和检测的结果。</span><span class="sxs-lookup"><span data-stu-id="8011c-385">**Delivery location** shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="8011c-386">它链接到传递 **_操作_**。</span><span class="sxs-lookup"><span data-stu-id="8011c-386">It's linked to **_Delivery action_**.</span></span> <span data-ttu-id="8011c-387">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="8011c-387">These are the possible values:</span></span>

- <span data-ttu-id="8011c-388">*收件箱或文件夹*：电子邮件位于收件箱或文件夹中 (电子邮件规则) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-388">*Inbox or folder*: The email is in the inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="8011c-389">*本地或外部*：邮箱在云中不存在，但位于本地。</span><span class="sxs-lookup"><span data-stu-id="8011c-389">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="8011c-390">*垃圾邮件* 文件夹：电子邮件位于用户的"垃圾邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8011c-390">*Junk folder*: The email is in a user's Junk folder.</span></span>
- <span data-ttu-id="8011c-391">*"已删除邮件"文件夹*：用户的"已删除邮件"文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8011c-391">*Deleted items folder*: The email in a user's Deleted items folder.</span></span>
- <span data-ttu-id="8011c-392">*隔离*：电子邮件被隔离，不在用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="8011c-392">*Quarantine*: The email is in quarantine and not in a user's mailbox.</span></span>
- <span data-ttu-id="8011c-393">*失败*：电子邮件无法到达邮箱。</span><span class="sxs-lookup"><span data-stu-id="8011c-393">*Failed*: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="8011c-394">*已* 丢弃：电子邮件在邮件流中的某处丢失。</span><span class="sxs-lookup"><span data-stu-id="8011c-394">*Dropped*: The email got lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="8011c-395">电子邮件时间线</span><span class="sxs-lookup"><span data-stu-id="8011c-395">Email timeline</span></span>

<span data-ttu-id="8011c-396">电子邮件 **时间线** 是一种新的资源管理器功能，可改善管理员的搜寻体验。</span><span class="sxs-lookup"><span data-stu-id="8011c-396">The **Email timeline** is a new Explorer feature that improves the hunting experience for admins.</span></span> <span data-ttu-id="8011c-397">它减少检查不同位置以尝试了解事件所花的时间。</span><span class="sxs-lookup"><span data-stu-id="8011c-397">It cuts the time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="8011c-398">当在电子邮件到达的同一时间或接近同一时间发生多个事件时，这些事件将显示在时间线视图中。</span><span class="sxs-lookup"><span data-stu-id="8011c-398">When multiple events happen at or close to the same time an email arrives, those events are displayed in a timeline view.</span></span> <span data-ttu-id="8011c-399">在"特殊操作"列中捕获在电子邮件传递后发生的一 **些** 事件。</span><span class="sxs-lookup"><span data-stu-id="8011c-399">Some events that happen to your email post-delivery are captured in the **Special action** column.</span></span> <span data-ttu-id="8011c-400">管理员可以将时间线的信息与对邮件传递后采取的特殊操作相结合，以深入了解其策略如何工作、邮件最终路由在何处，在某些情况下，最终评估是什么。</span><span class="sxs-lookup"><span data-stu-id="8011c-400">Admins can combine  information from the timeline with the special action taken on the mail post-delivery to get insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="8011c-401">有关详细信息，请参阅调查和修正在 [Office 365 中传递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)。</span><span class="sxs-lookup"><span data-stu-id="8011c-401">For more information, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="8011c-402">导出 URL 单击数据</span><span class="sxs-lookup"><span data-stu-id="8011c-402">Export URL click data</span></span>

<span data-ttu-id="8011c-403">现在可以将 URL 单击的报告导出到 Microsoft Excel 以查看其网络消息 **ID** 并单击 **裁定**，这有助于说明 URL 单击流量的来源。</span><span class="sxs-lookup"><span data-stu-id="8011c-403">You can now export reports for URL clicks to Microsoft Excel to view their **network message ID** and **click verdict**, which helps explain where your URL click traffic originated.</span></span> <span data-ttu-id="8011c-404">它的工作原理如下：在 Office 365 快速启动栏上的威胁管理中，按照此链操作：</span><span class="sxs-lookup"><span data-stu-id="8011c-404">Here's how it works: In Threat Management on the Office 365 quick-launch bar, follow this chain:</span></span>

<span data-ttu-id="8011c-405">**资源管理器** \>**查看钓鱼邮件** \>**单击** \>**顶部 URL 或** **URL 顶部单击** \> 选择任意记录以打开 URL 飞出。</span><span class="sxs-lookup"><span data-stu-id="8011c-405">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs** or **URL Top Clicks** \> select any record to open the URL flyout.</span></span>

<span data-ttu-id="8011c-406">在列表中选择 URL 时，你将在飞出面板上看到一个新的"导出"按钮。</span><span class="sxs-lookup"><span data-stu-id="8011c-406">When you select a URL in the list, you'll see a new **Export** button on the fly-out panel.</span></span> <span data-ttu-id="8011c-407">使用此按钮将数据移动到 Excel 电子表格，以便更轻松地报告。</span><span class="sxs-lookup"><span data-stu-id="8011c-407">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="8011c-408">按照此路径到达实时检测报告中的相同位置：</span><span class="sxs-lookup"><span data-stu-id="8011c-408">Follow this path to get to the same location in the Real-time detections report:</span></span>

<span data-ttu-id="8011c-409">**资源管理器** \>**实时检测** \>**查看钓鱼邮件** \>**URL** \>**顶部 URL** 或 **顶部单击** \> 选择任意记录以打开 URL 飞出控件 \> ，导航到"**单击"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8011c-409">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs** or **Top Clicks** \> Select any record to open the URL flyout \> navigate to the **Clicks** tab.</span></span>

> [!TIP]
> <span data-ttu-id="8011c-410">当您通过资源管理器或关联的第三方工具搜索 ID 时，网络消息 ID 将单击映射回特定邮件。</span><span class="sxs-lookup"><span data-stu-id="8011c-410">The Network Message ID maps the click back to specific mails when you search on the ID through Explorer or associated third-party tools.</span></span> <span data-ttu-id="8011c-411">此类搜索可标识与单击结果关联的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8011c-411">Such searches identify the email associated with a click result.</span></span> <span data-ttu-id="8011c-412">通过关联网络消息 ID，可以更快速、更强大的分析。</span><span class="sxs-lookup"><span data-stu-id="8011c-412">Having the correlated Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8011c-413">![资源管理器中的"单击"选项卡](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-413">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="8011c-414">查看通过电子邮件技术检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="8011c-414">See malware detected in email by technology</span></span>

<span data-ttu-id="8011c-415">假设你想要查看在按 Microsoft 365 技术排序的电子邮件中检测到的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="8011c-415">Suppose you want to see malware detected in email sorted by Microsoft 365 technology.</span></span> <span data-ttu-id="8011c-416">为此，请使用 Explorer > 或 [实时检测 (](threat-explorer-views.md#email--malware) 的"电子邮件和恶意软件") 。</span><span class="sxs-lookup"><span data-stu-id="8011c-416">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="8011c-417">在安全&中心 () ，选择"威胁管理资源管理器 (<https://protection.office.com> 或实时检测 \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="8011c-417">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="8011c-418"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="8011c-418">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="8011c-419">在"**视图"** 菜单中，选择"**电子邮件恶意软件** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="8011c-419">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8011c-420">![资源管理器的"视图"菜单](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-420">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="8011c-421">单击 **"发件人**"，然后选择"**基本** \> **检测技术"。**</span><span class="sxs-lookup"><span data-stu-id="8011c-421">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="8011c-422">你的检测技术现在用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="8011c-422">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8011c-423">![恶意软件检测技术](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-423">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="8011c-424">选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="8011c-424">Choose an option.</span></span> <span data-ttu-id="8011c-425">然后选择" **刷新"** 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="8011c-425">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8011c-426">![选定的检测技术](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-426">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="8011c-427">报告将刷新，以使用所选的技术选项显示电子邮件中检测到的恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="8011c-427">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="8011c-428">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="8011c-428">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="8011c-429">查看网络钓鱼 URL 并单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="8011c-429">View phishing URL and click verdict data</span></span>

<span data-ttu-id="8011c-430">假设你想要查看通过电子邮件中的 URL 的网络钓鱼尝试，包括允许、阻止和覆盖的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="8011c-430">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="8011c-431">若要标识单击的 URL， [必须配置](atp-safe-links.md) 安全链接。</span><span class="sxs-lookup"><span data-stu-id="8011c-431">To identify URLs that were clicked, [Safe Links](atp-safe-links.md) must be configured.</span></span> <span data-ttu-id="8011c-432">请确保为单击时保护 [和安全](set-up-atp-safe-links-policies.md) 链接记录单击裁定设置安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="8011c-432">Make sure that you set up [Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="8011c-433">若要查看邮件中的网络钓鱼 URL 并单击网络钓鱼邮件中的 URL，请使用资源管理器的电子邮件[  >  ](threat-explorer-views.md#email--phish)网络钓鱼视图或实时检测。</span><span class="sxs-lookup"><span data-stu-id="8011c-433">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="8011c-434">在安全&中心 () ，选择"威胁管理资源管理器 (<https://protection.office.com> 或实时检测 \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="8011c-434">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="8011c-435"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="8011c-435">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="8011c-436">在"**视图"** 菜单中，选择"**电子邮件钓鱼** \> **邮件"。**</span><span class="sxs-lookup"><span data-stu-id="8011c-436">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8011c-437">![网络钓鱼上下文中资源管理器的"查看"菜单](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-437">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="8011c-438">单击 **"发件人**"，然后选择 **"URL""** \> **单击裁定"。**</span><span class="sxs-lookup"><span data-stu-id="8011c-438">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="8011c-439">选择一个或多个选项，如"阻止"和"阻止 **覆盖**"，然后选择与应用该筛选器的选项位于同一行上的"刷新"按钮。</span><span class="sxs-lookup"><span data-stu-id="8011c-439">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="8011c-440"> (请勿刷新浏览器窗口。) </span><span class="sxs-lookup"><span data-stu-id="8011c-440">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8011c-441">![URL 和单击裁定](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-441">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="8011c-442">报告将刷新，以在报告下的"URL"选项卡上显示两个不同的 URL 表：</span><span class="sxs-lookup"><span data-stu-id="8011c-442">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="8011c-443">**顶部 URL** 是筛选到的邮件中的 URL，每个 URL 的电子邮件传递操作计数。</span><span class="sxs-lookup"><span data-stu-id="8011c-443">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="8011c-444">在网络钓鱼电子邮件视图中，此列表通常包含合法 URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-444">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="8011c-445">攻击者在邮件中混合了好 URL 和坏 URL，以尝试传递这些 URL，但它们会使恶意链接看起来更有趣。</span><span class="sxs-lookup"><span data-stu-id="8011c-445">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="8011c-446">URL 表按总电子邮件计数排序，但隐藏此列以简化视图。</span><span class="sxs-lookup"><span data-stu-id="8011c-446">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="8011c-447">**点击** 量最高是单击的安全链接包装 URL，按总点击数排序。</span><span class="sxs-lookup"><span data-stu-id="8011c-447">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="8011c-448">此列也不显示，以简化视图。</span><span class="sxs-lookup"><span data-stu-id="8011c-448">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="8011c-449">按列的总计数指示每个单击的 URL 的安全链接单击裁定计数。</span><span class="sxs-lookup"><span data-stu-id="8011c-449">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="8011c-450">在网络钓鱼电子邮件视图中，这些 URL 通常是可疑或恶意 URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-450">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="8011c-451">但是，该视图可能包含不是威胁但包含钓鱼邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-451">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="8011c-452">此处不会显示对未包链接的 URL 单击。</span><span class="sxs-lookup"><span data-stu-id="8011c-452">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="8011c-453">这两个 URL 表按传递操作和位置显示网络钓鱼电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-453">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="8011c-454">这些表显示了尽管出现警告仍被阻止或访问的 URL 单击，因此你可以看到向用户显示哪些潜在的错误链接以及用户点击了哪些链接。</span><span class="sxs-lookup"><span data-stu-id="8011c-454">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the user's clicked.</span></span> <span data-ttu-id="8011c-455">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="8011c-455">From here, you can conduct further analysis.</span></span> <span data-ttu-id="8011c-456">例如，在图表下方，可以看到在组织环境中被阻止的电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-456">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8011c-457">![阻止的浏览器 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-457">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="8011c-458">选择 URL 以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="8011c-458">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8011c-459">在"URL"弹出对话框中，将删除对电子邮件的筛选，以显示环境中 URL 曝光的完整视图。</span><span class="sxs-lookup"><span data-stu-id="8011c-459">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="8011c-460">这允许你在资源管理器中筛选你关注的电子邮件，查找潜在威胁的特定 URL，然后通过"URL 详细信息"对话框) 扩展你了解环境中 (中的 URL 曝光，而无需将 URL 筛选器添加到资源管理器视图本身。</span><span class="sxs-lookup"><span data-stu-id="8011c-460">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="8011c-461">单击裁定的解释</span><span class="sxs-lookup"><span data-stu-id="8011c-461">Interpretation of click verdicts</span></span>

<span data-ttu-id="8011c-462">在"电子邮件"或"URL"飞出、点击次数以及筛选体验内，你将看到不同的单击裁定值：</span><span class="sxs-lookup"><span data-stu-id="8011c-462">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="8011c-463">**无：** 无法捕获 URL 裁定。</span><span class="sxs-lookup"><span data-stu-id="8011c-463">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="8011c-464">用户可能通过 URL 单击过。</span><span class="sxs-lookup"><span data-stu-id="8011c-464">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="8011c-465">**允许：** 允许用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-465">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="8011c-466">**已阻止：** 阻止用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-466">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="8011c-467">**待定裁定：** 向用户显示等待触发的页面。</span><span class="sxs-lookup"><span data-stu-id="8011c-467">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="8011c-468">**被阻止覆盖：** 阻止用户直接导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-468">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="8011c-469">但用户过度控制块以导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="8011c-469">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="8011c-470">**已绕过待定裁定：** 向用户显示触发页面。</span><span class="sxs-lookup"><span data-stu-id="8011c-470">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="8011c-471">但是，用户为了访问 URL 而过度使用邮件。</span><span class="sxs-lookup"><span data-stu-id="8011c-471">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="8011c-472">**错误：** 向用户显示错误页面，或捕获裁定时出错。</span><span class="sxs-lookup"><span data-stu-id="8011c-472">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="8011c-473">**失败：** 捕获裁定时发生未知异常。</span><span class="sxs-lookup"><span data-stu-id="8011c-473">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="8011c-474">用户可能通过 URL 单击过。</span><span class="sxs-lookup"><span data-stu-id="8011c-474">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="8011c-475">查看用户报告的电子邮件</span><span class="sxs-lookup"><span data-stu-id="8011c-475">Review email messages reported by users</span></span>

<span data-ttu-id="8011c-476">假定您希望查看您组织中用户通过报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、非垃圾邮件或网络钓鱼[的电子邮件](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="8011c-476">Suppose that you want to see email messages that users in your organization reported as *Junk*, *Not Junk*, or *Phishing* through the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span> <span data-ttu-id="8011c-477">若要查看它们，请使用资源管理器的"电子邮件[  >  提交" (](threat-explorer-views.md#email--submissions)或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-477">To see them, use the [**Email** > **Submissions**](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="8011c-478">在安全&中心 () ，选择"威胁管理资源管理器 (<https://protection.office.com> 或实时检测 \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="8011c-478">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="8011c-479"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="8011c-479">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="8011c-480">在"**视图"** 菜单中，选择"**电子邮件** \> **提交"。**</span><span class="sxs-lookup"><span data-stu-id="8011c-480">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8011c-481">![电子邮件资源管理器的"查看"菜单](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-481">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="8011c-482">单击 **"发件人**"，然后选择"**基本** \> **报告类型"。**</span><span class="sxs-lookup"><span data-stu-id="8011c-482">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="8011c-483">选择一个选项（如 **钓鱼邮件**）然后选择" **刷新"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="8011c-483">Select an option, such as **Phish**, and then select the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8011c-484">![用户报告的网络钓鱼](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="8011c-484">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="8011c-485">报告将刷新以显示有关组织中人员报告为网络钓鱼尝试的电子邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="8011c-485">The report refreshes to show data about email messages that people in your organization reported as a phishing attempt.</span></span> <span data-ttu-id="8011c-486">可以使用此信息进行进一步分析，如有必要，还可以在 Microsoft Defender [for Office 365](configure-atp-anti-phishing-policies.md)中调整反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="8011c-486">You can use this information to conduct further analysis, and, if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="8011c-487">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="8011c-487">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="8011c-488">Microsoft Defender for *Office 365 计划 2* 和 Office *365 E5* 中提供了自动调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="8011c-488">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="8011c-489">[自动调查和响应](automated-investigation-response-office.md) 可以节省安全运营团队在调查和缓解网络攻击上花费的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="8011c-489">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="8011c-490">除了配置可触发安全手册的警报之外，还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="8011c-490">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="8011c-491">有关详细信息，请参阅 [示例：安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="8011c-491">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a><span data-ttu-id="8011c-492">使用资源管理器和实时检测的更多方法</span><span class="sxs-lookup"><span data-stu-id="8011c-492">More ways to use Explorer and Real-time detections</span></span>

<span data-ttu-id="8011c-493">除了本文中概述的方案之外，资源管理器或实时检测功能中还 (更多报告) 。</span><span class="sxs-lookup"><span data-stu-id="8011c-493">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span> <span data-ttu-id="8011c-494">另请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="8011c-494">See the following articles:</span></span>

- [<span data-ttu-id="8011c-495">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="8011c-495">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="8011c-496">查看在 SharePoint Online、OneDrive 和 Microsoft Teams 中检测到的恶意文件</span><span class="sxs-lookup"><span data-stu-id="8011c-496">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](./atp-for-spo-odb-and-teams.md)
- [<span data-ttu-id="8011c-497">大致了解威胁资源管理器中的 (和实时检测) </span><span class="sxs-lookup"><span data-stu-id="8011c-497">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="8011c-498">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="8011c-498">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="8011c-499">Microsoft 威胁防护中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="8011c-499">Automated investigation and response in Microsoft Threat Protection</span></span>](../mtp/mtp-autoir.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="8011c-500">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="8011c-500">Required licenses and permissions</span></span>

<span data-ttu-id="8011c-501">必须具有适用于 [Office 365](office-365-atp.md) 的 Microsoft Defender，以使用资源管理器或实时检测。</span><span class="sxs-lookup"><span data-stu-id="8011c-501">You must have [Microsoft Defender for Office 365](office-365-atp.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="8011c-502">资源管理器包含在 Defender for Office 365 计划 2 中。</span><span class="sxs-lookup"><span data-stu-id="8011c-502">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="8011c-503">实时检测报告包含在 Defender for Office 365 计划 1 中。</span><span class="sxs-lookup"><span data-stu-id="8011c-503">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="8011c-504">计划为应受 Office 365 Defender 保护的所有用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="8011c-504">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="8011c-505">资源管理器和实时检测显示许可用户的检测数据。</span><span class="sxs-lookup"><span data-stu-id="8011c-505">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="8011c-506">若要查看和使用资源管理器或实时检测，您必须具有适当的权限，例如授予安全管理员或安全读者的权限。</span><span class="sxs-lookup"><span data-stu-id="8011c-506">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="8011c-507">对于安全&合规中心，必须分配以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="8011c-507">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="8011c-508">组织管理</span><span class="sxs-lookup"><span data-stu-id="8011c-508">Organization Management</span></span>
  - <span data-ttu-id="8011c-509">安全 (可以在 Azure Active Directory 管理中心管理中心 <https://aad.portal.azure.com> () </span><span class="sxs-lookup"><span data-stu-id="8011c-509">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="8011c-510">安全读取者</span><span class="sxs-lookup"><span data-stu-id="8011c-510">Security Reader</span></span>

- <span data-ttu-id="8011c-511">对于 Exchange Online，必须在 Exchange 管理中心或 <https://admin.protection.outlook.com/ecp/> Exchange Online PowerShell () 分配以下 [角色之一](/powershell/exchange/exchange-online-powershell)：</span><span class="sxs-lookup"><span data-stu-id="8011c-511">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="8011c-512">组织管理</span><span class="sxs-lookup"><span data-stu-id="8011c-512">Organization Management</span></span>
  - <span data-ttu-id="8011c-513">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="8011c-513">View-Only Organization Management</span></span>
  - <span data-ttu-id="8011c-514">仅查看收件人</span><span class="sxs-lookup"><span data-stu-id="8011c-514">View-Only Recipients</span></span>
  - <span data-ttu-id="8011c-515">合规性管理</span><span class="sxs-lookup"><span data-stu-id="8011c-515">Compliance Management</span></span>

<span data-ttu-id="8011c-516">若要详细了解角色和权限，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="8011c-516">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="8011c-517">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="8011c-517">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="8011c-518">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="8011c-518">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="8011c-519">威胁资源管理器和实时检测之间的差异</span><span class="sxs-lookup"><span data-stu-id="8011c-519">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="8011c-520">*实时检测报告在* Defender for Office 365 计划 1 中提供。</span><span class="sxs-lookup"><span data-stu-id="8011c-520">The *Real-time detections* report is available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="8011c-521">*威胁资源管理器* 在 Office 365 计划 2 的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="8011c-521">*Threat Explorer* is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="8011c-522">实时检测报告允许你实时查看检测。</span><span class="sxs-lookup"><span data-stu-id="8011c-522">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="8011c-523">威胁资源管理器也这样做，但它还提供了给定攻击的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="8011c-523">Threat Explorer does this as well, but it also provides additional details for a given attack.</span></span>
- <span data-ttu-id="8011c-524">" *所有电子邮件* "视图在威胁资源管理器中可用，但在实时检测报告中不可用。</span><span class="sxs-lookup"><span data-stu-id="8011c-524">An *All email* view is available in Threat Explorer but not in the Real-time detections report.</span></span>
- <span data-ttu-id="8011c-525">威胁资源管理器中包含更多筛选功能和可用操作。</span><span class="sxs-lookup"><span data-stu-id="8011c-525">More filtering capabilities and available actions are included in Threat Explorer.</span></span> <span data-ttu-id="8011c-526">有关详细信息，请参阅 [Microsoft Defender for Office 365 服务说明：跨 Defender for Office 365 计划的功能可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="8011c-526">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="other-articles"></a><span data-ttu-id="8011c-527">其他文章</span><span class="sxs-lookup"><span data-stu-id="8011c-527">Other articles</span></span>

[<span data-ttu-id="8011c-528">使用"电子邮件实体"页调查电子邮件</span><span class="sxs-lookup"><span data-stu-id="8011c-528">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)