---
title: 威胁资源管理器和实时检测
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用安全合规中心中的资源管理器和实时 &amp; 检测来有效调查和响应威胁。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5ecc90602573de0de08336c3bca41aed701d8329
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865028"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="c4673-103">威胁资源管理器和实时检测</span><span class="sxs-lookup"><span data-stu-id="c4673-103">Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="c4673-104">如果你的组织拥有 [适用于 Office 365 的 Microsoft Defender，](office-365-atp.md)并且你拥有 [必要的](#required-licenses-and-permissions)权限，则你有权访问 *资源管理器* 或实时检测，这些检测以前是 *实时报告*。</span><span class="sxs-lookup"><span data-stu-id="c4673-104">If your organization has [Microsoft Defender for Office 365](office-365-atp.md) and you have the [necessary permissions](#required-licenses-and-permissions), you have access to *Explorer* or *Real-time detections*, which were formerly *Real-time reports*.</span></span> <span data-ttu-id="c4673-105"> ([了解](#new-features-in-threat-explorer-and-real-time-detections)新增功能。) 在安全与合规&中，转到"威胁管理"，然后选择"**资源管理器**"或"实时 **检测"。**</span><span class="sxs-lookup"><span data-stu-id="c4673-105">([See what's new.](#new-features-in-threat-explorer-and-real-time-detections)) In the Security & Compliance Center, go to **Threat management**, and then select **Explorer** _or_ **Real-time detections**.</span></span>

|<span data-ttu-id="c4673-106">借助 Microsoft Defender for Office 365 计划 2，可以看到：</span><span class="sxs-lookup"><span data-stu-id="c4673-106">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="c4673-107">借助 Microsoft Defender for Office 365 计划 1，可以看到：</span><span class="sxs-lookup"><span data-stu-id="c4673-107">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![威胁资源管理器](../../media/threatmgmt-explorer.png)|![实时检测](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="c4673-110">资源管理器或实时检测可帮助安全运营团队有效调查和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="c4673-110">Explorer or Real-time detections helps your security operations team investigate and respond to threats efficiently.</span></span> <span data-ttu-id="c4673-111">报表类似于下图：</span><span class="sxs-lookup"><span data-stu-id="c4673-111">The report resembles the following image:</span></span>

![转到威胁管理 \> 资源管理器](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="c4673-113">通过此报告，您可以：</span><span class="sxs-lookup"><span data-stu-id="c4673-113">With this report, you can:</span></span>

- [<span data-ttu-id="c4673-114">查看 Microsoft 365 安全功能检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="c4673-114">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="c4673-115">查看网络钓鱼 URL 和单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="c4673-115">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- <span data-ttu-id="c4673-116">[仅从资源管理器中的](#start-automated-investigation-and-response) 视图启动自动调查和响应 (Defender for Office 365 计划 2) </span><span class="sxs-lookup"><span data-stu-id="c4673-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- [<span data-ttu-id="c4673-117">调查恶意电子邮件等</span><span class="sxs-lookup"><span data-stu-id="c4673-117">Investigate malicious email, and more</span></span>](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="c4673-118">威胁资源管理器和实时检测的改进</span><span class="sxs-lookup"><span data-stu-id="c4673-118">Improvements to Threat Explorer and Real-time detections</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="c4673-119">威胁资源管理器中的标记</span><span class="sxs-lookup"><span data-stu-id="c4673-119">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="c4673-120">用户标记功能在 *预览版* 中，并非对所有人都可用，并且可能会更改。</span><span class="sxs-lookup"><span data-stu-id="c4673-120">The user tags feature is in *Preview*, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="c4673-121">有关发布计划的信息，请查看 Microsoft 365 路线图。</span><span class="sxs-lookup"><span data-stu-id="c4673-121">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="c4673-122">用户标记标识 Microsoft Defender for Office 365 中的特定用户组。</span><span class="sxs-lookup"><span data-stu-id="c4673-122">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="c4673-123">有关标记（包括许可和配置）详细信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="c4673-123">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="c4673-124">在威胁资源管理器中，可以在以下体验中查看有关用户标记的信息。</span><span class="sxs-lookup"><span data-stu-id="c4673-124">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="c4673-125">电子邮件网格视图</span><span class="sxs-lookup"><span data-stu-id="c4673-125">Email grid view</span></span>

<span data-ttu-id="c4673-126">电子邮件 **网格** 中的"标记"列包含已应用于发件人或收件人邮箱的所有标记。</span><span class="sxs-lookup"><span data-stu-id="c4673-126">The **Tags** column in the email grid contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="c4673-127">默认情况下，优先帐户等系统标记将首先显示。</span><span class="sxs-lookup"><span data-stu-id="c4673-127">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-128">![电子邮件网格视图中的筛选器标记](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-128">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="c4673-129">筛选</span><span class="sxs-lookup"><span data-stu-id="c4673-129">Filtering</span></span>

<span data-ttu-id="c4673-130">可以使用标记作为筛选器。</span><span class="sxs-lookup"><span data-stu-id="c4673-130">You can use tags as a filter.</span></span> <span data-ttu-id="c4673-131">仅跨优先级帐户或特定用户标记方案进行智能寻线。</span><span class="sxs-lookup"><span data-stu-id="c4673-131">Hunt just across priority accounts or specific user tags scenarios.</span></span> <span data-ttu-id="c4673-132">还可以排除具有特定标记的结果。</span><span class="sxs-lookup"><span data-stu-id="c4673-132">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="c4673-133">将此功能与其他筛选器相结合，以缩小调查范围。</span><span class="sxs-lookup"><span data-stu-id="c4673-133">Combine this functionality with other filters to narrow your scope of investigation.</span></span>

<span data-ttu-id="c4673-134">[![筛选器标记](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c4673-134">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-135">![非筛选器标记](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-135">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="c4673-136">电子邮件详细信息飞出</span><span class="sxs-lookup"><span data-stu-id="c4673-136">Email detail flyout</span></span>
<span data-ttu-id="c4673-137">若要查看发件人和收件人的单个标记，请选择主题以打开邮件详细信息飞出。</span><span class="sxs-lookup"><span data-stu-id="c4673-137">To view the individual tags for sender and recipient, select the subject to open the message details flyout.</span></span> <span data-ttu-id="c4673-138">在 **"摘要"** 选项卡上，如果电子邮件存在发件人和收件人标记，则分别显示它们。</span><span class="sxs-lookup"><span data-stu-id="c4673-138">On the **Summary** tab, the sender and recipient tags are shown separately, if they're present for an email.</span></span>
<span data-ttu-id="c4673-139">有关发件人和收件人的单个标记的信息还扩展到导出的 CSV 数据，您可以在两个单独的列中查看这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="c4673-139">The information about individual tags for sender and recipient also extends to exported CSV data, where you can see these details in two separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-140">![电子邮件详细信息标记](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-140">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="c4673-141">标记信息也显示在 URL 单击飞出中。</span><span class="sxs-lookup"><span data-stu-id="c4673-141">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="c4673-142">若要查看它，请转到"网络钓鱼"或"所有电子邮件"视图，然后转到 **"URL"或\*\*\*\*"URL** 单击"选项卡。选择单个 URL 飞出以查看有关该 URL 的单击的其他详细信息，包括与该单击关联的标记。</span><span class="sxs-lookup"><span data-stu-id="c4673-142">To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Select an individual URL flyout to view additional details about clicks for that URL, including tags associated with that click.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-143">![URL 标记](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-143">![URL tags](../../media/tags-urls.png)</span></span>

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a><span data-ttu-id="c4673-144">威胁搜寻体验的改进 (即将推出的) </span><span class="sxs-lookup"><span data-stu-id="c4673-144">Improvements to the threat hunting experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="c4673-145">更新了电子邮件的威胁信息</span><span class="sxs-lookup"><span data-stu-id="c4673-145">Updated threat information for emails</span></span>

<span data-ttu-id="c4673-146">我们专注于平台和数据质量改进，以提高电子邮件记录的数据准确性和一致性。</span><span class="sxs-lookup"><span data-stu-id="c4673-146">We've focused on platform and data-quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="c4673-147">改进包括将传递前和传递后信息（如作为 ZAP 过程的一部分对电子邮件执行的操作）合并到单个记录中。</span><span class="sxs-lookup"><span data-stu-id="c4673-147">Improvements include consolidation of pre-delivery and post-delivery information, such as actions executed on an email as part of the ZAP process, into a single record.</span></span> <span data-ttu-id="c4673-148">还包括垃圾邮件裁定、实体级威胁 (（例如，哪个 URL 是恶意) 和最新的传递位置）。</span><span class="sxs-lookup"><span data-stu-id="c4673-148">Additional details like spam verdict, entity-level threats (for example, which URL was malicious), and latest delivery locations are also included.</span></span>

<span data-ttu-id="c4673-149">这些更新后，你将看到每封邮件的单个条目，无论影响邮件的不同传递后事件如何。</span><span class="sxs-lookup"><span data-stu-id="c4673-149">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that affect the message.</span></span> <span data-ttu-id="c4673-150">操作可能包括 ZAP、手动修正 (这意味着管理员操作) 、动态传递等。</span><span class="sxs-lookup"><span data-stu-id="c4673-150">Actions can include ZAP, manual remediation (which means admin action), dynamic delivery, and so on.</span></span>

<span data-ttu-id="c4673-151">除了显示恶意软件和网络钓鱼威胁外，您还可以看到与电子邮件关联的垃圾邮件裁定。</span><span class="sxs-lookup"><span data-stu-id="c4673-151">In addition to showing malware and phishing threats, you see the spam verdict associated with an email.</span></span> <span data-ttu-id="c4673-152">在电子邮件中，查看与电子邮件关联的所有威胁以及相应的检测技术。</span><span class="sxs-lookup"><span data-stu-id="c4673-152">Within the email, see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="c4673-153">电子邮件可以具有零个威胁、一个威胁或多个威胁。</span><span class="sxs-lookup"><span data-stu-id="c4673-153">An email can have zero, one, or multiple threats.</span></span> <span data-ttu-id="c4673-154">你将在电子邮件飞出"详细信息"部分看到当前威胁。</span><span class="sxs-lookup"><span data-stu-id="c4673-154">You'll see the current threats in the **Details** section of the email flyout.</span></span> <span data-ttu-id="c4673-155">对于恶意软件 (网络钓鱼) ，检测技术字段显示威胁检测映射，这是识别威胁的检测技术。</span><span class="sxs-lookup"><span data-stu-id="c4673-155">For multiple threats (such as malware and phishing), the **Detection tech** field shows the threat-detection mapping, which is the detection technology that identified the threat.</span></span>

<span data-ttu-id="c4673-156">检测技术集现在包括新的检测方法以及垃圾邮件检测技术。</span><span class="sxs-lookup"><span data-stu-id="c4673-156">The set of detection technologies now includes new detection methods, as well as spam-detection technologies.</span></span> <span data-ttu-id="c4673-157">您可以使用同一组检测技术筛选恶意软件、网络钓鱼、所有电子邮件 (不同电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="c4673-157">You can use the same set of detection technologies to filter the results across the different email views (Malware, Phish, All Email).</span></span>

> [!NOTE]
> <span data-ttu-id="c4673-158">裁定分析不一定与实体关联。</span><span class="sxs-lookup"><span data-stu-id="c4673-158">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="c4673-159">例如，电子邮件可能分类为网络钓鱼或垃圾邮件，但没有标记有网络钓鱼/垃圾邮件裁定的 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-159">As an example, an email might be classified as phish or spam, but there are no URLs that are stamped with a phish/spam verdict.</span></span> <span data-ttu-id="c4673-160">这是因为筛选器还会在分配裁定之前评估电子邮件的内容和其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="c4673-160">This is because the filters also evaluate content and other details for an email before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="c4673-161">URL 中的威胁</span><span class="sxs-lookup"><span data-stu-id="c4673-161">Threats in URLs</span></span>

<span data-ttu-id="c4673-162">现在，可以在"电子邮件飞出详细信息"选项卡上看到 URL **的特定威胁**。威胁可以是 *恶意软件*、*网络钓鱼*、*垃圾邮件* 或无 *.)*</span><span class="sxs-lookup"><span data-stu-id="c4673-162">You can now see the specific threat for a URL on the email flyout **Details** tab. The threat can be *malware*, *phish*, *spam*, or *none*.)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-163">![URL 威胁](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-163">![URL threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="c4673-164">更新了 (视图) </span><span class="sxs-lookup"><span data-stu-id="c4673-164">Updated timeline view (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-165">![更新的日程表视图](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-165">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="c4673-166">时间线视图标识所有传递和传递后事件。</span><span class="sxs-lookup"><span data-stu-id="c4673-166">Timeline view identifies all delivery and post-delivery events.</span></span> <span data-ttu-id="c4673-167">它包括有关在这些事件的子集时标识的威胁的信息。</span><span class="sxs-lookup"><span data-stu-id="c4673-167">It includes information about the threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="c4673-168">时间线视图还提供有关对项目执行 (操作（如 ZAP 或手动修正) ）的信息，以及该操作的结果。</span><span class="sxs-lookup"><span data-stu-id="c4673-168">Timeline view also provides information about any additional action taken (such as ZAP or manual remediation), along with the result of that action.</span></span> <span data-ttu-id="c4673-169">日程表视图信息包括：</span><span class="sxs-lookup"><span data-stu-id="c4673-169">Timeline view information includes:</span></span>

- <span data-ttu-id="c4673-170">**源：** 事件的源。</span><span class="sxs-lookup"><span data-stu-id="c4673-170">**Source:** Source of the event.</span></span> <span data-ttu-id="c4673-171">它可以是管理员/系统/用户。</span><span class="sxs-lookup"><span data-stu-id="c4673-171">It can be admin/system/user.</span></span>
- <span data-ttu-id="c4673-172">**事件：** 包括顶级事件，如原始传递、手动修正、ZAP、提交和动态传递。</span><span class="sxs-lookup"><span data-stu-id="c4673-172">**Event:** Includes top-level events like original delivery, manual remediation, ZAP, submissions, and dynamic delivery.</span></span>
- <span data-ttu-id="c4673-173">**操作：** 作为 ZAP 或管理员操作一部分执行的特定 (例如，软删除) 。</span><span class="sxs-lookup"><span data-stu-id="c4673-173">**Action:** The specific action that was taken either as part of ZAP or admin action (for example, soft delete).</span></span>
- <span data-ttu-id="c4673-174">**威胁：** 涵盖 (时标识) 恶意软件、网络钓鱼、垃圾邮件等威胁。</span><span class="sxs-lookup"><span data-stu-id="c4673-174">**Threats:** Covers the threats (malware, phish, spam) identified at that point of time.</span></span>
- <span data-ttu-id="c4673-175">**结果/详细信息：** 有关操作结果（例如是否作为 ZAP/管理员操作一部分执行）详细信息。</span><span class="sxs-lookup"><span data-stu-id="c4673-175">**Result/Details:** More information about the result of the action, such as whether it was performed as part of ZAP/admin action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="c4673-176">原始和最新的送达位置</span><span class="sxs-lookup"><span data-stu-id="c4673-176">Original and latest delivery location</span></span>

<span data-ttu-id="c4673-177">目前，我们在电子邮件网格和电子邮件浮出控件中显示传递位置。</span><span class="sxs-lookup"><span data-stu-id="c4673-177">Currently, we surface delivery location in the email grid and email flyout.</span></span> <span data-ttu-id="c4673-178">传递 **位置字段** 被重命名 \**_原始传递位置_* _。</span><span class="sxs-lookup"><span data-stu-id="c4673-178">The **Delivery location** field is getting renamed \**_Original delivery location_* _.</span></span> <span data-ttu-id="c4673-179">我们正在引入另一个字段， _\*_即最新送达位置_\*_。</span><span class="sxs-lookup"><span data-stu-id="c4673-179">And we're introducing another field, _*_Latest delivery location_*_.</span></span>

<span data-ttu-id="c4673-180">_ *原始送达位置*\* 将提供有关电子邮件最初送达位置的更多信息。</span><span class="sxs-lookup"><span data-stu-id="c4673-180">_ *Original delivery location*\* will give more information about where an email was delivered initially.</span></span> <span data-ttu-id="c4673-181">**最新的送达位置** 将说明电子邮件在系统操作（如 *ZAP）* 或管理员操作（如 *移动到已删除项目）之后登录的位置*。</span><span class="sxs-lookup"><span data-stu-id="c4673-181">**Latest delivery location** will state where an email landed after system actions like *ZAP* or admin actions like *Move to deleted items*.</span></span> <span data-ttu-id="c4673-182">最新送达位置旨在告知管理员邮件传递后的最新已知位置或任何系统/管理员操作。</span><span class="sxs-lookup"><span data-stu-id="c4673-182">Latest delivery location is intended to tell admins the message's last-known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="c4673-183">它不包含对电子邮件的任何最终用户操作。</span><span class="sxs-lookup"><span data-stu-id="c4673-183">It doesn't include any end-user actions on the email.</span></span> <span data-ttu-id="c4673-184">例如，如果用户删除了邮件或将邮件移动到存档/pst，邮件"传递"位置将不会更新。</span><span class="sxs-lookup"><span data-stu-id="c4673-184">For example, if a user deleted a message or moved the message to archive/pst, the message "delivery" location won't be updated.</span></span> <span data-ttu-id="c4673-185">但是，如果系统操作更新了位置 (例如，ZAP 导致电子邮件移动到隔离邮箱) ，则最新送达位置将显示为"隔离"。</span><span class="sxs-lookup"><span data-stu-id="c4673-185">But if a system action updated the location (for example, ZAP resulting in an email moving to quarantine), **Latest delivery location** would show as "quarantine."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-186">![更新的传递位置](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-186">![Updated delivery locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="c4673-187">在某些情况下，传递位置 **和\*\*\*\*传递操作** 可能显示为"未知"：</span><span class="sxs-lookup"><span data-stu-id="c4673-187">There are a few cases where **Delivery location** and **Delivery action** may show as "unknown":</span></span>
>
> - <span data-ttu-id="c4673-188">如果邮件已送达，您可能会将传递位置视为"已送达"，而"传递位置"为"未知"，但收件箱规则将邮件移动到默认文件夹 (如草稿或存档) ，而不是"收件箱"或"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4673-188">You might see **Delivery location** as "delivered" and **Delivery location** as "unknown" if the message was delivered, but an Inbox rule moved the message to a default folder (such as Draft or Archive) instead of to the Inbox or Junk Email folder.</span></span>
>
> - <span data-ttu-id="c4673-189">**如果尝试执行** 管理/系统操作（如 ZAP (，但未找到邮件) ，则最新的传递位置可能未知。</span><span class="sxs-lookup"><span data-stu-id="c4673-189">**Latest delivery location** can be unknown if an admin/system action (such as ZAP) was attempted, but the message wasn't found.</span></span> <span data-ttu-id="c4673-190">通常，该操作发生在用户移动或删除邮件之后。</span><span class="sxs-lookup"><span data-stu-id="c4673-190">Typically, the action happens after the user  moved or deleted the message.</span></span> <span data-ttu-id="c4673-191">在这种情况下，请验证 **日程表视图中的结果/** 详细信息列。</span><span class="sxs-lookup"><span data-stu-id="c4673-191">In such cases, verify the **Result/Details** column in timeline view.</span></span> <span data-ttu-id="c4673-192">查找"用户移动或删除的邮件"语句。</span><span class="sxs-lookup"><span data-stu-id="c4673-192">Look for the statement "Message moved or deleted by the user."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-193">![时间线的传递位置](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-193">![Delivery locations for timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="c4673-194">其他操作</span><span class="sxs-lookup"><span data-stu-id="c4673-194">Additional actions</span></span>

<span data-ttu-id="c4673-195">*在电子邮件* 传递后应用了其他操作。</span><span class="sxs-lookup"><span data-stu-id="c4673-195">*Additional actions* were applied after delivery of the email.</span></span> <span data-ttu-id="c4673-196">它们可以包括 *ZAP、* 由管理员 (手动修正操作（如软删除 *) 、* 动态传递和重新处理 (）以用于被反向检测为良好的) 。  </span><span class="sxs-lookup"><span data-stu-id="c4673-196">They can include *ZAP*, *manual remediation* (action taken by an Admin such as soft delete), *dynamic delivery*, and *reprocessed* (for an email that was retroactively detected as good).</span></span>

> [!NOTE]
> - <span data-ttu-id="c4673-197">作为挂起更改的一部分，当前在传递操作筛选器中显示"ZAP 删除"值将消失。</span><span class="sxs-lookup"><span data-stu-id="c4673-197">As part of the pending changes, the "Removed by ZAP" value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="c4673-198">你将可以通过其他操作通过 ZAP 尝试搜索 **所有电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="c4673-198">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span></span>
>
> - <span data-ttu-id="c4673-199">检测技术和其他操作将具有新的字段 **和值**， (ZAP 方案) 。</span><span class="sxs-lookup"><span data-stu-id="c4673-199">There will be new fields and values for **Detection technologies** and **Additional actions** (especially for ZAP scenarios).</span></span> <span data-ttu-id="c4673-200">您需要评估现有保存的查询和跟踪的查询，以确保它们使用新值。</span><span class="sxs-lookup"><span data-stu-id="c4673-200">You'll need to evaluate your existing saved queries and tracked queries to make sure they work with the new values.</span></span>

> [!div class="mx-imgBorder"]

> ![资源管理器中的其他操作](../../media/Additional_Actions.png)

### <a name="system-overrides"></a><span data-ttu-id="c4673-202">系统替代</span><span class="sxs-lookup"><span data-stu-id="c4673-202">System overrides</span></span>

<span data-ttu-id="c4673-203">*系统覆盖* 使您能够对邮件的预定传递位置进行例外。</span><span class="sxs-lookup"><span data-stu-id="c4673-203">*System overrides* enable you to make exceptions to the intended delivery location of a message.</span></span> <span data-ttu-id="c4673-204">根据筛选堆栈标识的威胁和其他检测，覆盖系统提供的传递位置。</span><span class="sxs-lookup"><span data-stu-id="c4673-204">You override the delivery location provided by the system, based on the threats and other detections identified by the filtering stack.</span></span> <span data-ttu-id="c4673-205">可以通过租户或用户策略设置系统覆盖，以根据策略的建议传递邮件。</span><span class="sxs-lookup"><span data-stu-id="c4673-205">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="c4673-206">替代可以标识由于配置差异（如用户设置过宽的安全发件人策略）而无意传递恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="c4673-206">Overrides can identify unintentional delivery of malicious messages due to configurations gaps, such as an overly broad Safe Sender policy set by a user.</span></span> <span data-ttu-id="c4673-207">这些替代值可以是：</span><span class="sxs-lookup"><span data-stu-id="c4673-207">These override values can be:</span></span>

- <span data-ttu-id="c4673-208">用户策略允许：用户在邮箱级别创建策略以允许域或发件人。</span><span class="sxs-lookup"><span data-stu-id="c4673-208">Allowed by user policy: A user creates policies at the mailbox level to allows domains or senders.</span></span>
- <span data-ttu-id="c4673-209">被用户策略阻止：用户在邮件框级别创建策略以阻止域或发件人。</span><span class="sxs-lookup"><span data-stu-id="c4673-209">Blocked by user policy: A user creates policies at the mail box level to block domains or senders.</span></span>
- <span data-ttu-id="c4673-210">组织策略允许：组织的安全团队设置策略或 Exchange 邮件流规则 (也称为传输规则) ，以允许组织中的用户使用发件人和域。</span><span class="sxs-lookup"><span data-stu-id="c4673-210">Allowed by org policy: The organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="c4673-211">这适用于一组用户或整个组织。</span><span class="sxs-lookup"><span data-stu-id="c4673-211">This can be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="c4673-212">被组织策略阻止：组织的安全团队设置策略或邮件流规则，以阻止组织中的用户的发件人、域、邮件语言或源 IP。</span><span class="sxs-lookup"><span data-stu-id="c4673-212">Blocked by org policy: The organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="c4673-213">这可应用于一组用户或整个组织。</span><span class="sxs-lookup"><span data-stu-id="c4673-213">This can be applied to a set of users or the entire organization.</span></span>
- <span data-ttu-id="c4673-214">组织策略阻止的文件扩展名：组织的安全团队通过反恶意软件策略设置阻止文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="c4673-214">File extension blocked by org policy: An organization's security team blocks a file name extension through the anti-malware policy settings.</span></span> <span data-ttu-id="c4673-215">这些值现在将显示在电子邮件详细信息中，以帮助进行调查。</span><span class="sxs-lookup"><span data-stu-id="c4673-215">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="c4673-216">Secops 团队还可使用丰富的筛选功能筛选阻止的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="c4673-216">Secops teams can also use the rich-filtering capability to filter on blocked file extensions.</span></span>

<span data-ttu-id="c4673-217">[![资源管理器中的系统覆盖](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c4673-217">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-218">![资源管理器中的系统覆盖网格](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-218">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-for-the-url-and-clicks-experience"></a><span data-ttu-id="c4673-219">URL 和单击体验的改进</span><span class="sxs-lookup"><span data-stu-id="c4673-219">Improvements for the URL and clicks experience</span></span>

<span data-ttu-id="c4673-220">这些改进包括：</span><span class="sxs-lookup"><span data-stu-id="c4673-220">The improvements include:</span></span>

- <span data-ttu-id="c4673-221">显示完整单击的 URL (包括作为 URL 链接的一) **单击部分的任何** 查询参数。</span><span class="sxs-lookup"><span data-stu-id="c4673-221">Show the full clicked URL (including any query parameters that are part of the URL) in the **Clicks** section of the URL flyout.</span></span> <span data-ttu-id="c4673-222">目前，URL 域和路径显示在标题栏中。</span><span class="sxs-lookup"><span data-stu-id="c4673-222">Currently, the URL domain and path appear in the title bar.</span></span> <span data-ttu-id="c4673-223">我们将扩展该信息以显示完整 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-223">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="c4673-224">跨 URL 筛选器 (*URL* 域与 *URL* 域和路径的修复) ：更新会影响对包含 URL/单击裁定的邮件的搜索。</span><span class="sxs-lookup"><span data-stu-id="c4673-224">Fixes across URL filters (*URL* versus *URL domain* versus *URL domain and path*): The updates affect searching for messages that contain a URL/click verdict.</span></span> <span data-ttu-id="c4673-225">我们启用了协议不可知搜索支持，因此无需使用即可搜索 `http` URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-225">We enabled support for protocol-agnostic searches, so you can search for a URL without using `http`.</span></span> <span data-ttu-id="c4673-226">默认情况下，除非明确指定了其他值，否则 URL 搜索将映射到 http。</span><span class="sxs-lookup"><span data-stu-id="c4673-226">By default, the URL search maps to http, unless another value is explicitly specified.</span></span> <span data-ttu-id="c4673-227">例如：</span><span class="sxs-lookup"><span data-stu-id="c4673-227">For example:</span></span>

   -  <span data-ttu-id="c4673-228">在 URL、URL 域和 URL 域和路径筛选器字段中使用和 `http://` **不带前缀进行** 搜索。  </span><span class="sxs-lookup"><span data-stu-id="c4673-228">Search with and without the `http://` prefix in the **URL**, **URL Domain**, and **URL Domain and Path** filter fields.</span></span> <span data-ttu-id="c4673-229">搜索应显示相同的结果。</span><span class="sxs-lookup"><span data-stu-id="c4673-229">The searches should show the same results.</span></span>

   -  <span data-ttu-id="c4673-230">在 `https://` **URL** 中搜索前缀。</span><span class="sxs-lookup"><span data-stu-id="c4673-230">Search for the `https://` prefix in **URL**.</span></span> <span data-ttu-id="c4673-231">如果未指定任何值， `http://` 则假定前缀。</span><span class="sxs-lookup"><span data-stu-id="c4673-231">When no value is specified, the `http://` prefix is assumed.</span></span>

   - <span data-ttu-id="c4673-232">`/` 在 URL 路径 **、URL** 域 **、URL** 域和路径字段的开头和结尾 **被忽略** 。</span><span class="sxs-lookup"><span data-stu-id="c4673-232">`/` is ignored at the beginning and end of the **URL path**, **URL Domain**, **URL domain and path** fields.</span></span> <span data-ttu-id="c4673-233">`/` 将忽略 **URL** 字段的末尾。</span><span class="sxs-lookup"><span data-stu-id="c4673-233">`/` at the end of the **URL** field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="c4673-234">网络钓鱼可信度</span><span class="sxs-lookup"><span data-stu-id="c4673-234">Phish confidence level</span></span>

<span data-ttu-id="c4673-235">网络钓鱼可信度有助于确定电子邮件被分类为"网络钓鱼"的可信度。</span><span class="sxs-lookup"><span data-stu-id="c4673-235">Phish confidence level helps identify the degree of confidence with which an email was categorized as "phish."</span></span> <span data-ttu-id="c4673-236">两个可能的值是 *高和\*\*普通*。</span><span class="sxs-lookup"><span data-stu-id="c4673-236">The two possible values are *High* and *Normal*.</span></span> <span data-ttu-id="c4673-237">在初始阶段，此筛选器仅在威胁资源管理器的网络钓鱼视图中可用。</span><span class="sxs-lookup"><span data-stu-id="c4673-237">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="c4673-238">[![资源管理器中的网络钓鱼可信度](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c4673-238">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="c4673-239">ZAP URL 信号</span><span class="sxs-lookup"><span data-stu-id="c4673-239">ZAP URL signal</span></span>

<span data-ttu-id="c4673-240">ZAP URL 信号通常用于 ZAP 网络钓鱼警报方案，其中电子邮件被标识为网络钓鱼，且在传递后被删除。</span><span class="sxs-lookup"><span data-stu-id="c4673-240">The ZAP URL signal is typically used for ZAP Phish alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="c4673-241">此信号将警报与资源管理器中的相应结果连接在一起。</span><span class="sxs-lookup"><span data-stu-id="c4673-241">This signal connects the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="c4673-242">它是警报的 IIC 之一。</span><span class="sxs-lookup"><span data-stu-id="c4673-242">It's one of the IOCs for the alert.</span></span>

<span data-ttu-id="c4673-243">为了改进搜寻过程，我们更新了威胁资源管理器和实时检测，使搜寻体验更加一致。</span><span class="sxs-lookup"><span data-stu-id="c4673-243">To improve the hunting process, we've updated Threat Explorer and Real-time detections to make the hunting experience more consistent.</span></span> <span data-ttu-id="c4673-244">此处概述了这些更改：</span><span class="sxs-lookup"><span data-stu-id="c4673-244">The changes are outlined here:</span></span>

- [<span data-ttu-id="c4673-245">时区改进</span><span class="sxs-lookup"><span data-stu-id="c4673-245">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="c4673-246">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="c4673-246">Update in the refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="c4673-247">要添加到筛选器的图表向下钻取</span><span class="sxs-lookup"><span data-stu-id="c4673-247">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="c4673-248">在产品信息更新中</span><span class="sxs-lookup"><span data-stu-id="c4673-248">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="c4673-249">按用户标记筛选</span><span class="sxs-lookup"><span data-stu-id="c4673-249">Filter by user tags</span></span>

<span data-ttu-id="c4673-250">现在，你可以对系统或自定义用户标记进行排序和筛选，以快速了解威胁的范围。</span><span class="sxs-lookup"><span data-stu-id="c4673-250">You can now sort and filter on system or custom user tags to quickly grasp the scope of threats.</span></span> <span data-ttu-id="c4673-251">若要了解更多信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="c4673-251">To learn more, see [User tags](user-tags.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4673-252">按用户标记进行筛选和排序目前处于公共预览阶段。</span><span class="sxs-lookup"><span data-stu-id="c4673-252">Filtering and sorting by user tags is currently in public preview.</span></span> <span data-ttu-id="c4673-253">在商业发布之前，可能会对此功能进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="c4673-253">This functionality may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c4673-254">Microsoft 对提供的信息不做出明示或暗示的担保。</span><span class="sxs-lookup"><span data-stu-id="c4673-254">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

![资源管理器中的"标记"列](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a><span data-ttu-id="c4673-256">时区改进</span><span class="sxs-lookup"><span data-stu-id="c4673-256">Timezone improvements</span></span>

<span data-ttu-id="c4673-257">你将在门户中以及导出的数据中查看电子邮件记录的时区。</span><span class="sxs-lookup"><span data-stu-id="c4673-257">You'll see the time zone for the email records in the Portal as well as for Exported data.</span></span> <span data-ttu-id="c4673-258">它将在电子邮件网格、详细信息飞出控件、电子邮件时间线和类似电子邮件等体验中可见，因此邮件结果集清晰。</span><span class="sxs-lookup"><span data-stu-id="c4673-258">It will be visible across experiences like Email Grid, Details flyout, Email Timeline, and Similar Emails, so the time zone for the result set is clear.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-259">![在资源管理器中查看时区](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-259">![View time zone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="c4673-260">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="c4673-260">Update in the refresh process</span></span>

<span data-ttu-id="c4673-261">例如，一些用户评论了与自动刷新 (混淆，例如，一旦更改日期，页面就会) 其他筛选器 (刷新) 。</span><span class="sxs-lookup"><span data-stu-id="c4673-261">Some users have commented about confusion with automatic refresh (for example, as soon as you change the date, the page refreshes) and manual refresh (for other filters).</span></span> <span data-ttu-id="c4673-262">同样，删除筛选器会导致自动刷新。</span><span class="sxs-lookup"><span data-stu-id="c4673-262">Similarly, removing filters leads to automatic refresh.</span></span> <span data-ttu-id="c4673-263">修改查询时更改筛选器可能会导致搜索体验不一致。</span><span class="sxs-lookup"><span data-stu-id="c4673-263">Changing filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="c4673-264">为了解决这些问题，我们将迁移到手动筛选机制。</span><span class="sxs-lookup"><span data-stu-id="c4673-264">To resolve these issues, we're moving to a manual-filtering mechanism.</span></span>

<span data-ttu-id="c4673-265">从体验的角度来看，用户可以应用和删除筛选器集和日期 (的不同筛选器范围) 并选择刷新按钮，以在定义查询后筛选结果。</span><span class="sxs-lookup"><span data-stu-id="c4673-265">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set and date) and select the refresh button to filter the results after they've defined the query.</span></span> <span data-ttu-id="c4673-266">此时，屏幕上也强调刷新按钮。</span><span class="sxs-lookup"><span data-stu-id="c4673-266">The refresh button is also now emphasized on the screen.</span></span> <span data-ttu-id="c4673-267">我们还更新了相关工具提示和产品内文档。</span><span class="sxs-lookup"><span data-stu-id="c4673-267">We've also updated the related tooltips and in-product documentation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-268">![选择"刷新"筛选结果](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-268">![Select Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="c4673-269">要添加到筛选器的图表向下钻取</span><span class="sxs-lookup"><span data-stu-id="c4673-269">Chart drilldown to add to filters</span></span>

<span data-ttu-id="c4673-270">现在，你可以绘制图例值图表以将它们添加为筛选器。</span><span class="sxs-lookup"><span data-stu-id="c4673-270">You can now chart legend values to add them as filters.</span></span> <span data-ttu-id="c4673-271">选择 **"刷新** "按钮以筛选结果。</span><span class="sxs-lookup"><span data-stu-id="c4673-271">Select the **Refresh** button to filter the results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-272">![向下钻取图表以筛选](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-272">![Drill down through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="c4673-273">产品内信息更新</span><span class="sxs-lookup"><span data-stu-id="c4673-273">In-product information updates</span></span>

<span data-ttu-id="c4673-274">产品内现已提供其他详细信息，例如网格内搜索结果总数 (请参阅下面的) 。</span><span class="sxs-lookup"><span data-stu-id="c4673-274">Additional details are now available within the product, such as the total number of search results within the grid (see below).</span></span> <span data-ttu-id="c4673-275">我们改进了标签、错误消息和工具提示，以提供有关筛选器、搜索体验和搜索结果集。</span><span class="sxs-lookup"><span data-stu-id="c4673-275">We've improved labels, error messages, and tooltips to provide more information about the filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-276">![查看产品内信息](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-276">![View in-product information](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="c4673-277">威胁资源管理器中的扩展功能</span><span class="sxs-lookup"><span data-stu-id="c4673-277">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="c4673-278">主要目标用户</span><span class="sxs-lookup"><span data-stu-id="c4673-278">Top targeted users</span></span>

<span data-ttu-id="c4673-279">现在，我们在电子邮件的"恶意软件"视图中的"主要恶意软件系列"部分公开了主要目标 **用户** 的列表。</span><span class="sxs-lookup"><span data-stu-id="c4673-279">Today we expose the list of the top targeted users in the Malware view for emails, in the **Top Malware Families** section.</span></span> <span data-ttu-id="c4673-280">我们还将在"网络钓鱼"和"所有电子邮件"视图中扩展此视图。</span><span class="sxs-lookup"><span data-stu-id="c4673-280">We'll be extending this view in the Phish and All Email views as well.</span></span> <span data-ttu-id="c4673-281">你将能够看到前五个目标用户，以及每个用户针对相应视图的尝试次数。</span><span class="sxs-lookup"><span data-stu-id="c4673-281">You'll be able to see the top-five targeted users, along with the number of attempts for each user for the corresponding view.</span></span> <span data-ttu-id="c4673-282">例如，对于网络钓鱼视图，你将看到网络钓鱼尝试次数。</span><span class="sxs-lookup"><span data-stu-id="c4673-282">For example, for Phish view, you'll see the number of Phish attempts.</span></span>

<span data-ttu-id="c4673-283">你将能够导出目标用户的列表（最多为 3，000 个）以及每个电子邮件视图的脱机分析尝试次数。</span><span class="sxs-lookup"><span data-stu-id="c4673-283">You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="c4673-284">此外，选择尝试次数（例如 (，) 下面的图像中的 13 次尝试将在威胁资源管理器中打开筛选视图，以便你可以查看针对该用户的电子邮件和威胁的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="c4673-284">In addition, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-285">![主要目标用户](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-285">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="c4673-286">Exchange 传输规则</span><span class="sxs-lookup"><span data-stu-id="c4673-286">Exchange transport rules</span></span>

<span data-ttu-id="c4673-287">作为数据扩充的一部分，你将能够看到应用于邮件的所有不同 Exchange (ETR) 规则。</span><span class="sxs-lookup"><span data-stu-id="c4673-287">As part of data enrichment, you'll be able to see all the different Exchange transport rules (ETR) that were applied to a message.</span></span> <span data-ttu-id="c4673-288">此信息将在电子邮件网格视图中提供。</span><span class="sxs-lookup"><span data-stu-id="c4673-288">This information will be available in the Email grid view.</span></span> <span data-ttu-id="c4673-289">若要查看它，请选择网格 **中的** 列选项，然后 **从列** 选项中添加 Exchange 传输规则。</span><span class="sxs-lookup"><span data-stu-id="c4673-289">To view it,  select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="c4673-290">它还将在电子邮件 **的"详细信息** "飞出上可见。</span><span class="sxs-lookup"><span data-stu-id="c4673-290">It will also be visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="c4673-291">您将能够查看应用于邮件的传输规则的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="c4673-291">You'll be able to see both the GUID and the name of the transport rules that were applied to the message.</span></span> <span data-ttu-id="c4673-292">您可以使用传输规则的名称搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="c4673-292">You'll be able to search for the messages by using the name of the transport rule.</span></span> <span data-ttu-id="c4673-293">这是一个"包含"搜索，这意味着您也可以执行部分搜索。</span><span class="sxs-lookup"><span data-stu-id="c4673-293">This is a "Contains" search, which means you can do partial searches as well.</span></span>

#### <a name="important-note"></a><span data-ttu-id="c4673-294">重要说明：</span><span class="sxs-lookup"><span data-stu-id="c4673-294">Important note:</span></span>

<span data-ttu-id="c4673-295">ETR 搜索和名称可用性取决于分配给您的特定角色。</span><span class="sxs-lookup"><span data-stu-id="c4673-295">ETR search and name availability depend on the specific role that's assigned to you.</span></span> <span data-ttu-id="c4673-296">你需要具有以下角色/权限之一才能查看 ETR 名称和搜索。</span><span class="sxs-lookup"><span data-stu-id="c4673-296">You need to have one of the following roles/permissions to view the ETR names and search.</span></span> <span data-ttu-id="c4673-297">如果未分配任何这些角色，则看不到传输规则的名称，也看不到使用 ETR 名称搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="c4673-297">If you don't have any of these roles assigned to you, you can't see the names of the transport rules or search for messages by using ETR names.</span></span> <span data-ttu-id="c4673-298">但是，您可以在电子邮件详细信息中查看 ETR 标签和 GUID 信息。</span><span class="sxs-lookup"><span data-stu-id="c4673-298">However, you could see the ETR label and GUID information in the Email Details.</span></span> <span data-ttu-id="c4673-299">电子邮件网格、电子邮件飞出、筛选器和导出中的其他记录查看体验不受影响。</span><span class="sxs-lookup"><span data-stu-id="c4673-299">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>

- <span data-ttu-id="c4673-300">仅 EXO - 数据丢失防护：全部</span><span class="sxs-lookup"><span data-stu-id="c4673-300">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="c4673-301">仅 EXO - O365SupportViewConfig：全部</span><span class="sxs-lookup"><span data-stu-id="c4673-301">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="c4673-302">Microsoft Azure Active Directory 或 EXO - 安全管理员：全部</span><span class="sxs-lookup"><span data-stu-id="c4673-302">Microsoft Azure Active Directory or EXO - Security Admin: All</span></span>
- <span data-ttu-id="c4673-303">AAD 或 EXO - 安全读取器：全部</span><span class="sxs-lookup"><span data-stu-id="c4673-303">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="c4673-304">仅 EXO - 传输规则：全部</span><span class="sxs-lookup"><span data-stu-id="c4673-304">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="c4673-305">仅 EXO - View-Only配置：全部</span><span class="sxs-lookup"><span data-stu-id="c4673-305">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="c4673-306">在电子邮件网格、详细信息飞出和导出的 CSV 中，ETR 将显示一个名称/GUID，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c4673-306">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-307">![Exchange 传输规则](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-307">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="c4673-308">入站连接器</span><span class="sxs-lookup"><span data-stu-id="c4673-308">Inbound connectors</span></span>

<span data-ttu-id="c4673-309">连接器是一组说明，用于自定义电子邮件在 Microsoft 365 或 Office 365 组织之间流动和流出。</span><span class="sxs-lookup"><span data-stu-id="c4673-309">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="c4673-310">它们使您能够应用任何安全限制或控件。</span><span class="sxs-lookup"><span data-stu-id="c4673-310">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="c4673-311">在威胁资源管理器中，你现在可以查看与电子邮件相关的连接器，然后使用连接器名称搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c4673-311">Within Threat Explorer, you can now view the connectors that are related to an email and search for emails by using connector names.</span></span>

<span data-ttu-id="c4673-312">连接器搜索本质上是"包含"的，这意味着部分关键字搜索也应正常工作。</span><span class="sxs-lookup"><span data-stu-id="c4673-312">The search for connectors is "contains" in nature, which means partial keyword searches should work as well.</span></span> <span data-ttu-id="c4673-313">在主网格视图、"详细信息"飞出控件和导出的 CSV 中，连接器以名称/GUID 格式显示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c4673-313">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown here:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-314">![连接器详细信息](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-314">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="c4673-315">威胁资源管理器中的新功能和实时检测</span><span class="sxs-lookup"><span data-stu-id="c4673-315">New features in Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="c4673-316">威胁资源管理器和实时检测中提供了三项新功能：</span><span class="sxs-lookup"><span data-stu-id="c4673-316">Three new features are available in Threat Explorer and Real-time detections:</span></span>

- [<span data-ttu-id="c4673-317">预览电子邮件头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="c4673-317">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="c4673-318">电子邮件时间线</span><span class="sxs-lookup"><span data-stu-id="c4673-318">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="c4673-319">导出 URL 单击数据</span><span class="sxs-lookup"><span data-stu-id="c4673-319">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="c4673-320">下面概述了这些新功能。</span><span class="sxs-lookup"><span data-stu-id="c4673-320">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="c4673-321">预览电子邮件头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="c4673-321">Preview email header and download email body</span></span>

<span data-ttu-id="c4673-322">现在，你可以预览电子邮件头，并下载威胁资源管理器中的电子邮件正文。管理员可以分析下载的邮件头/电子邮件中的威胁。</span><span class="sxs-lookup"><span data-stu-id="c4673-322">You can now preview an email header and download the email body in Threat Explorer Admins can analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="c4673-323">因为下载电子邮件可能会暴露信息的风险，所以此过程由基于角色的访问控制控制， (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="c4673-323">Because downloading email messages can risk exposure of information, this process is controlled by role-based access control (RBAC).</span></span> <span data-ttu-id="c4673-324">必须将新角色 *Preview* 添加到另一个角色组 (如安全操作或安全管理员) ，以授予在全部电子邮件视图中下载邮件和预览邮件头的能力。</span><span class="sxs-lookup"><span data-stu-id="c4673-324">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="c4673-325">资源管理器和实时检测还将获取新字段，这些字段可提供电子邮件到达位置的更完整图片。</span><span class="sxs-lookup"><span data-stu-id="c4673-325">Explorer and Real-time detections will also get new fields that provide a more complete picture of where your email messages land.</span></span> <span data-ttu-id="c4673-326">这些更改使搜寻更便于安全操作。</span><span class="sxs-lookup"><span data-stu-id="c4673-326">These changes  make hunting easier for Security Ops.</span></span> <span data-ttu-id="c4673-327">但主要结果是，您可以一目了然地了解问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="c4673-327">But the main result is you can know the location of problem email messages at a glance.</span></span>

<span data-ttu-id="c4673-328">如何完成此操作？</span><span class="sxs-lookup"><span data-stu-id="c4673-328">How is this done?</span></span> <span data-ttu-id="c4673-329">传递状态现在分为两列：</span><span class="sxs-lookup"><span data-stu-id="c4673-329">Delivery status is now broken out into two columns:</span></span>

- <span data-ttu-id="c4673-330">**传递操作** - 电子邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="c4673-330">**Delivery action** - Status of the email.</span></span>
- <span data-ttu-id="c4673-331">**传递位置** - 电子邮件的路由位置。</span><span class="sxs-lookup"><span data-stu-id="c4673-331">**Delivery location** - Where the email was routed.</span></span>

<span data-ttu-id="c4673-332">*传递* 操作是对现有策略或检测对电子邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="c4673-332">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="c4673-333">以下是电子邮件的可能操作：</span><span class="sxs-lookup"><span data-stu-id="c4673-333">Here are the possible actions for an email:</span></span>

|<span data-ttu-id="c4673-334">已传递</span><span class="sxs-lookup"><span data-stu-id="c4673-334">Delivered</span></span>|<span data-ttu-id="c4673-335">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="c4673-335">Junked</span></span>|<span data-ttu-id="c4673-336">Blocked</span><span class="sxs-lookup"><span data-stu-id="c4673-336">Blocked</span></span>|<span data-ttu-id="c4673-337">已替换</span><span class="sxs-lookup"><span data-stu-id="c4673-337">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="c4673-338">电子邮件已传递到用户的收件箱或文件夹，用户可以访问它。</span><span class="sxs-lookup"><span data-stu-id="c4673-338">Email was delivered to the inbox or folder of a user, and the user can access it.</span></span>|<span data-ttu-id="c4673-339">电子邮件已发送到用户的"垃圾邮件"或"已删除邮件"文件夹，用户可以访问它。</span><span class="sxs-lookup"><span data-stu-id="c4673-339">Email was sent to the user's Junk  or Deleted folder, and the user can access it.</span></span>|<span data-ttu-id="c4673-340">隔离、失败或已丢弃的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c4673-340">Emails that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="c4673-341">用户无法访问这些邮件。</span><span class="sxs-lookup"><span data-stu-id="c4673-341">These mails are inaccessible to the user.</span></span>|<span data-ttu-id="c4673-342">电子邮件有恶意附件替换为 .txt 文件，指出附件是恶意附件。</span><span class="sxs-lookup"><span data-stu-id="c4673-342">Email had malicious attachments replaced by .txt files that state the attachment was malicious.</span></span>|

<span data-ttu-id="c4673-343">下面是用户可以看到和看不到的：</span><span class="sxs-lookup"><span data-stu-id="c4673-343">Here is what the user can and can't see:</span></span>

|<span data-ttu-id="c4673-344">最终用户可访问</span><span class="sxs-lookup"><span data-stu-id="c4673-344">Accessible to end users</span></span>|<span data-ttu-id="c4673-345">最终用户无法访问</span><span class="sxs-lookup"><span data-stu-id="c4673-345">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="c4673-346">已传递</span><span class="sxs-lookup"><span data-stu-id="c4673-346">Delivered</span></span>|<span data-ttu-id="c4673-347">Blocked</span><span class="sxs-lookup"><span data-stu-id="c4673-347">Blocked</span></span>|
|<span data-ttu-id="c4673-348">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="c4673-348">Junked</span></span>|<span data-ttu-id="c4673-349">已替换</span><span class="sxs-lookup"><span data-stu-id="c4673-349">Replaced</span></span>|

<span data-ttu-id="c4673-350">**传递** 位置显示运行传递后的策略和检测的结果。</span><span class="sxs-lookup"><span data-stu-id="c4673-350">**Delivery location** shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="c4673-351">它链接到 \**_传递操作_* _.</span><span class="sxs-lookup"><span data-stu-id="c4673-351">It's linked to \**_Delivery action_* _.</span></span> <span data-ttu-id="c4673-352">以下为可能的值：</span><span class="sxs-lookup"><span data-stu-id="c4673-352">These are the possible values:</span></span>

- <span data-ttu-id="c4673-353">_Inbox或文件夹\*：电子邮件位于收件箱或文件夹中 (根据您的电子邮件规则) 。</span><span class="sxs-lookup"><span data-stu-id="c4673-353">_Inbox or folder\*: The email is in the inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="c4673-354">*本地或外部*：邮箱在云中不存在，但位于本地。</span><span class="sxs-lookup"><span data-stu-id="c4673-354">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="c4673-355">*垃圾邮件* 文件夹：电子邮件位于用户的"垃圾邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c4673-355">*Junk folder*: The email is in a user's Junk folder.</span></span>
- <span data-ttu-id="c4673-356">*"已删除邮件"文件夹*：用户的"已删除邮件"文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c4673-356">*Deleted items folder*: The email in a user's Deleted items folder.</span></span>
- <span data-ttu-id="c4673-357">*隔离*：电子邮件被隔离，不在用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="c4673-357">*Quarantine*: The email is in quarantine and not in a user's mailbox.</span></span>
- <span data-ttu-id="c4673-358">*失败*：电子邮件无法到达邮箱。</span><span class="sxs-lookup"><span data-stu-id="c4673-358">*Failed*: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="c4673-359">*已* 丢弃：电子邮件在邮件流中的某位置丢失。</span><span class="sxs-lookup"><span data-stu-id="c4673-359">*Dropped*: The email got lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="c4673-360">电子邮件时间线</span><span class="sxs-lookup"><span data-stu-id="c4673-360">Email timeline</span></span>

<span data-ttu-id="c4673-361">电子邮件 **时间线** 是一种新的资源管理器功能，可改进管理员的搜寻体验。</span><span class="sxs-lookup"><span data-stu-id="c4673-361">The **Email timeline** is a new Explorer feature that improves the hunting experience for admins.</span></span> <span data-ttu-id="c4673-362">它减少检查不同位置以尝试了解事件所花的时间。</span><span class="sxs-lookup"><span data-stu-id="c4673-362">It cuts the time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="c4673-363">当在电子邮件到达的同一时间或接近同一时间发生多个事件时，这些事件将显示在日程表视图中。</span><span class="sxs-lookup"><span data-stu-id="c4673-363">When multiple events happen at or close to the same time an email arrives, those events are displayed in a timeline view.</span></span> <span data-ttu-id="c4673-364">在"特殊操作"列中捕获电子邮件传递后发生的一 **些** 事件。</span><span class="sxs-lookup"><span data-stu-id="c4673-364">Some events that happen to your email post-delivery are captured in the **Special action** column.</span></span> <span data-ttu-id="c4673-365">管理员可以将时间线的信息与对邮件传递后采取的特殊操作相结合，以深入了解其策略如何工作、邮件最终路由在何处，在某些情况下，了解最终评估内容。</span><span class="sxs-lookup"><span data-stu-id="c4673-365">Admins can combine  information from the timeline with the special action taken on the mail post-delivery to get insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="c4673-366">有关详细信息，请参阅 [调查和修正在 Office 365 中传递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)。</span><span class="sxs-lookup"><span data-stu-id="c4673-366">For more information, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="c4673-367">导出 URL 单击数据</span><span class="sxs-lookup"><span data-stu-id="c4673-367">Export URL click data</span></span>

<span data-ttu-id="c4673-368">现在可以将 URL 单击报告导出到 Microsoft Excel 以查看其网络消息 **ID** 和单击裁定，这有助于说明 URL 单击流量的来源。</span><span class="sxs-lookup"><span data-stu-id="c4673-368">You can now export reports for URL clicks to Microsoft Excel to view their **network message ID** and **click verdict**, which helps explain where your URL click traffic originated.</span></span> <span data-ttu-id="c4673-369">工作原理如下：在 Office 365 快速启动栏上的威胁管理中，按照以下链操作：</span><span class="sxs-lookup"><span data-stu-id="c4673-369">Here's how it works: In Threat Management on the Office 365 quick-launch bar, follow this chain:</span></span>

<span data-ttu-id="c4673-370">**资源管理器** \>**查看网络钓鱼** \>**单击** \>**顶部 URL 或** **URL 单击** \> 次数顶部选择任意记录以打开 URL 飞出。</span><span class="sxs-lookup"><span data-stu-id="c4673-370">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs** or **URL Top Clicks** \> select any record to open the URL flyout.</span></span>

<span data-ttu-id="c4673-371">When you select a URL in the list， you'll see a new **Export** button on the fly-out panel.</span><span class="sxs-lookup"><span data-stu-id="c4673-371">When you select a URL in the list, you'll see a new **Export** button on the fly-out panel.</span></span> <span data-ttu-id="c4673-372">使用此按钮将数据移动到 Excel 电子表格，以便于报告。</span><span class="sxs-lookup"><span data-stu-id="c4673-372">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="c4673-373">按照此路径到达实时检测报告中的相同位置：</span><span class="sxs-lookup"><span data-stu-id="c4673-373">Follow this path to get to the same location in the Real-time detections report:</span></span>

<span data-ttu-id="c4673-374">**资源管理器** \>**实时检测** \>**查看网络钓鱼** \>**URL** \>**顶部 URL** 或 **顶部单击** \> 选择任意记录以打开 URL 飞出控件 \> ，导航到 **"单击"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c4673-374">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs** or **Top Clicks** \> Select any record to open the URL flyout \> navigate to the **Clicks** tab.</span></span>

> [!TIP]
> <span data-ttu-id="c4673-375">当您通过资源管理器或关联的第三方工具搜索 ID 时，网络消息 ID 将单击映射回特定邮件。</span><span class="sxs-lookup"><span data-stu-id="c4673-375">The Network Message ID maps the click back to specific mails when you search on the ID through Explorer or associated third-party tools.</span></span> <span data-ttu-id="c4673-376">此类搜索可标识与单击结果关联的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c4673-376">Such searches identify the email associated with a click result.</span></span> <span data-ttu-id="c4673-377">通过关联网络消息 ID，可以更快、更强大的分析。</span><span class="sxs-lookup"><span data-stu-id="c4673-377">Having the correlated Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4673-378">![资源管理器中的"单击"选项卡](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-378">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="c4673-379">查看通过技术在电子邮件中检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="c4673-379">See malware detected in email by technology</span></span>

<span data-ttu-id="c4673-380">假设你想要查看在按 Microsoft 365 技术排序的电子邮件中检测到的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="c4673-380">Suppose you want to see malware detected in email sorted by Microsoft 365 technology.</span></span> <span data-ttu-id="c4673-381">为此，请使用资源管理器>或[](threat-explorer-views.md#email--malware)实时检测的"电子邮件 (恶意软件"视图) 。</span><span class="sxs-lookup"><span data-stu-id="c4673-381">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="c4673-382">在安全&中心 () ，选择威胁管理资源管理器 (或实时检测 <https://protection.office.com>  \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="c4673-382">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="c4673-383"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="c4673-383">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="c4673-384">在"**视图"** 菜单中，选择 **"电子邮件** \> **恶意软件"。**</span><span class="sxs-lookup"><span data-stu-id="c4673-384">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4673-385">![资源管理器的视图菜单](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-385">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="c4673-386">单击 **"** 发件人"，然后选择 **"基本** \> **检测技术"。**</span><span class="sxs-lookup"><span data-stu-id="c4673-386">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="c4673-387">你的检测技术现在用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="c4673-387">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4673-388">![恶意软件检测技术](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-388">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="c4673-389">选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="c4673-389">Choose an option.</span></span> <span data-ttu-id="c4673-390">然后选择" **刷新"** 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="c4673-390">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4673-391">![选定的检测技术](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-391">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="c4673-392">报告将刷新，以使用所选的技术选项显示电子邮件中检测到的恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="c4673-392">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="c4673-393">在这里，你可以执行进一步的分析。</span><span class="sxs-lookup"><span data-stu-id="c4673-393">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="c4673-394">查看网络钓鱼 URL 和单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="c4673-394">View phishing URL and click verdict data</span></span>

<span data-ttu-id="c4673-395">假设您希望查看通过电子邮件中的 URL（包括允许、阻止和覆盖的 URL 列表）的网络钓鱼尝试。</span><span class="sxs-lookup"><span data-stu-id="c4673-395">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="c4673-396">若要标识单击的 URL， [必须](atp-safe-links.md) 配置安全链接。</span><span class="sxs-lookup"><span data-stu-id="c4673-396">To identify URLs that were clicked, [Safe Links](atp-safe-links.md) must be configured.</span></span> <span data-ttu-id="c4673-397">确保为安全 [链接](set-up-atp-safe-links-policies.md) 的单击保护和单击裁定日志记录设置了安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="c4673-397">Make sure that you set up [Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="c4673-398">若要查看邮件中的网络钓鱼 URL 并单击网络钓鱼邮件中的 URL，请使用 Explorer[  >  ](threat-explorer-views.md#email--phish)的电子邮件网络钓鱼视图或实时检测。</span><span class="sxs-lookup"><span data-stu-id="c4673-398">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="c4673-399">在安全&中心 () ，选择威胁管理资源管理器 (或实时检测 <https://protection.office.com>  \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="c4673-399">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="c4673-400"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="c4673-400">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="c4673-401">在"**视图"** 菜单中，选择 **"电子邮件** \> **钓鱼"。**</span><span class="sxs-lookup"><span data-stu-id="c4673-401">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4673-402">![网络钓鱼上下文中资源管理器的"查看"菜单](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-402">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="c4673-403">单击 **"** 发件人"，然后选择 **"URL 单击** \> **"裁定**。</span><span class="sxs-lookup"><span data-stu-id="c4673-403">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="c4673-404">选择一个或多个选项，如"阻止"和"阻止覆盖"，然后选择与应用该筛选器的选项位于同一行上的"刷新"按钮。 </span><span class="sxs-lookup"><span data-stu-id="c4673-404">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="c4673-405"> (不刷新浏览器窗口。) </span><span class="sxs-lookup"><span data-stu-id="c4673-405">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4673-406">![URL 和单击裁定](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-406">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="c4673-407">报告刷新以显示报告下的"URL"选项卡上的两个不同的 URL 表：</span><span class="sxs-lookup"><span data-stu-id="c4673-407">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="c4673-408">**顶部 URL** 是筛选到的邮件中的 URL，以及每个 URL 的电子邮件传递操作计数。</span><span class="sxs-lookup"><span data-stu-id="c4673-408">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="c4673-409">在网络钓鱼电子邮件视图中，此列表通常包含合法 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-409">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="c4673-410">攻击者在邮件中混入好 URL 和坏 URL 以尝试传递这些 URL，但它们让恶意链接看起来更有趣。</span><span class="sxs-lookup"><span data-stu-id="c4673-410">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="c4673-411">URL 表按总电子邮件计数排序，但隐藏此列可简化视图。</span><span class="sxs-lookup"><span data-stu-id="c4673-411">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="c4673-412">**点击** 量居前的是单击的安全链接包装 URL，按总点击次数排序。</span><span class="sxs-lookup"><span data-stu-id="c4673-412">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="c4673-413">此列也不显示，以简化视图。</span><span class="sxs-lookup"><span data-stu-id="c4673-413">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="c4673-414">按列的总计数指示每个单击的 URL 的安全链接单击裁定计数。</span><span class="sxs-lookup"><span data-stu-id="c4673-414">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="c4673-415">在网络钓鱼电子邮件视图中，这些 URL 通常是可疑或恶意的 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-415">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="c4673-416">但视图可能包括不是威胁但包含钓鱼邮件的 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-416">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="c4673-417">此处不会显示单击未包链接的 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-417">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="c4673-418">这两个 URL 表按传递操作和位置显示网络钓鱼电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-418">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="c4673-419">这些表显示了在出现警告时被阻止或访问的 URL 单击，因此你可以看到向用户显示哪些潜在的错误链接以及用户点击了哪些链接。</span><span class="sxs-lookup"><span data-stu-id="c4673-419">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the user's clicked.</span></span> <span data-ttu-id="c4673-420">在这里，你可以执行进一步的分析。</span><span class="sxs-lookup"><span data-stu-id="c4673-420">From here, you can conduct further analysis.</span></span> <span data-ttu-id="c4673-421">例如，在图表下方，你可以看到在组织环境中被阻止的电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-421">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4673-422">![阻止的浏览器 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-422">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="c4673-423">选择 URL 以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="c4673-423">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c4673-424">在"URL"弹出对话框中，删除对电子邮件的筛选以显示环境中 URL 曝光的完整视图。</span><span class="sxs-lookup"><span data-stu-id="c4673-424">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="c4673-425">这允许你在资源管理器中筛选你关注的电子邮件，查找潜在威胁的特定 URL，然后通过 URL 详细信息对话框 (扩展你了解环境中 URL 的曝光) 而无需将 URL 筛选器添加到资源管理器视图本身。</span><span class="sxs-lookup"><span data-stu-id="c4673-425">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="c4673-426">单击裁定的解释</span><span class="sxs-lookup"><span data-stu-id="c4673-426">Interpretation of click verdicts</span></span>

<span data-ttu-id="c4673-427">在"电子邮件"或"URL"飞出、"点击量"以及筛选体验内，你将看到不同的单击裁定值：</span><span class="sxs-lookup"><span data-stu-id="c4673-427">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="c4673-428">**无：** 无法捕获 URL 裁定。</span><span class="sxs-lookup"><span data-stu-id="c4673-428">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="c4673-429">用户可能已经单击了 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-429">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="c4673-430">**允许：** 允许用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-430">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="c4673-431">**已阻止：** 阻止用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-431">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="c4673-432">**待定裁定：** 用户被呈现了等待触发的页面。</span><span class="sxs-lookup"><span data-stu-id="c4673-432">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="c4673-433">**阻止重写：** 阻止用户直接导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-433">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="c4673-434">但是，用户会超过此块以导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-434">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="c4673-435">**已绕过待定裁定：** 向用户显示触发页面。</span><span class="sxs-lookup"><span data-stu-id="c4673-435">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="c4673-436">但用户会过度更改邮件以访问 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-436">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="c4673-437">**错误：** 用户收到错误页，或捕获裁定时出错。</span><span class="sxs-lookup"><span data-stu-id="c4673-437">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="c4673-438">**失败：** 捕获裁定时发生未知异常。</span><span class="sxs-lookup"><span data-stu-id="c4673-438">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="c4673-439">用户可能已经单击了 URL。</span><span class="sxs-lookup"><span data-stu-id="c4673-439">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="c4673-440">查看用户报告的电子邮件</span><span class="sxs-lookup"><span data-stu-id="c4673-440">Review email messages reported by users</span></span>

<span data-ttu-id="c4673-441">假设您希望查看组织中用户通过报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、非垃圾邮件或网络钓鱼[的电子邮件](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="c4673-441">Suppose that you want to see email messages that users in your organization reported as *Junk*, *Not Junk*, or *Phishing* through the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span> <span data-ttu-id="c4673-442">若要查看它们，请使用资源管理器中的[  >  "电子邮件](threat-explorer-views.md#email--submissions)提交" (或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="c4673-442">To see them, use the [**Email** > **Submissions**](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="c4673-443">在安全&中心 () ，选择威胁管理资源管理器 (或实时检测 <https://protection.office.com>  \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="c4673-443">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="c4673-444"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="c4673-444">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="c4673-445">在"**视图"** 菜单中，选择 **"** \> **电子邮件提交"。**</span><span class="sxs-lookup"><span data-stu-id="c4673-445">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4673-446">![适用于电子邮件资源管理器的"查看"菜单](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-446">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="c4673-447">单击 **"** 发件人"，然后选择 **"基本** \> **报告类型"。**</span><span class="sxs-lookup"><span data-stu-id="c4673-447">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="c4673-448">选择一个选项，如 **钓鱼** 邮件，然后选择" **刷新"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="c4673-448">Select an option, such as **Phish**, and then select the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4673-449">![用户报告的网络钓鱼](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="c4673-449">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="c4673-450">报告将刷新以显示有关组织中人员报告为网络钓鱼尝试的电子邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="c4673-450">The report refreshes to show data about email messages that people in your organization reported as a phishing attempt.</span></span> <span data-ttu-id="c4673-451">可以使用此信息进行进一步分析，如有必要，在 [Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)中调整防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="c4673-451">You can use this information to conduct further analysis, and, if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="c4673-452">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="c4673-452">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="c4673-453">Microsoft Defender for *Office 365* 计划 2 和 *Office 365 E5* 中提供了自动调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="c4673-453">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="c4673-454">[自动调查和响应](automated-investigation-response-office.md) 可以节省安全运营团队在调查和缓解网络攻击上花费的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="c4673-454">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="c4673-455">除了配置可触发安全手册的警报外，还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="c4673-455">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="c4673-456">有关详细信息，请参阅 [示例：安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="c4673-456">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a><span data-ttu-id="c4673-457">更多使用资源管理器和实时检测的方法</span><span class="sxs-lookup"><span data-stu-id="c4673-457">More ways to use Explorer and Real-time detections</span></span>

<span data-ttu-id="c4673-458">除了本文中概述的方案之外，资源管理器或实时检测功能中 (更多报告) 。</span><span class="sxs-lookup"><span data-stu-id="c4673-458">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span> <span data-ttu-id="c4673-459">另请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="c4673-459">See the following articles:</span></span>

- [<span data-ttu-id="c4673-460">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="c4673-460">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="c4673-461">查看在 SharePoint Online、OneDrive 和 Microsoft Teams 中检测到的恶意文件</span><span class="sxs-lookup"><span data-stu-id="c4673-461">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="c4673-462">大致了解威胁资源管理器中的 (和实时检测) </span><span class="sxs-lookup"><span data-stu-id="c4673-462">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="c4673-463">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="c4673-463">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="c4673-464">Microsoft 威胁防护中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="c4673-464">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="c4673-465">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="c4673-465">Required licenses and permissions</span></span>

<span data-ttu-id="c4673-466">必须具有适用于 [Office 365 的 Microsoft Defender，](office-365-atp.md) 以使用资源管理器或实时检测。</span><span class="sxs-lookup"><span data-stu-id="c4673-466">You must have [Microsoft Defender for Office 365](office-365-atp.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="c4673-467">资源管理器包含在 Defender for Office 365 计划 2 中。</span><span class="sxs-lookup"><span data-stu-id="c4673-467">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="c4673-468">实时检测报告包含在 Defender for Office 365 计划 1 中。</span><span class="sxs-lookup"><span data-stu-id="c4673-468">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="c4673-469">计划为应受 Office 365 Defender 保护的所有用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c4673-469">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="c4673-470">资源管理器和实时检测显示许可用户的检测数据。</span><span class="sxs-lookup"><span data-stu-id="c4673-470">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="c4673-471">若要查看和使用资源管理器或实时检测，您必须具有适当的权限，例如授予安全管理员或安全读者的权限。</span><span class="sxs-lookup"><span data-stu-id="c4673-471">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="c4673-472">对于安全&合规中心，必须分配有以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="c4673-472">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="c4673-473">组织管理</span><span class="sxs-lookup"><span data-stu-id="c4673-473">Organization Management</span></span>
  - <span data-ttu-id="c4673-474">安全 (可以在 Azure Active Directory 管理中心 () <https://aad.portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="c4673-474">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="c4673-475">安全读取者</span><span class="sxs-lookup"><span data-stu-id="c4673-475">Security Reader</span></span>

- <span data-ttu-id="c4673-476">对于 Exchange Online，必须在 Exchange 管理中心或 Exchange Online PowerShell 中分配 <https://admin.protection.outlook.com/ecp/> () 角色 [之一](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)：</span><span class="sxs-lookup"><span data-stu-id="c4673-476">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="c4673-477">组织管理</span><span class="sxs-lookup"><span data-stu-id="c4673-477">Organization Management</span></span>
  - <span data-ttu-id="c4673-478">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="c4673-478">View-Only Organization Management</span></span>
  - <span data-ttu-id="c4673-479">仅查看收件人</span><span class="sxs-lookup"><span data-stu-id="c4673-479">View-Only Recipients</span></span>
  - <span data-ttu-id="c4673-480">合规性管理</span><span class="sxs-lookup"><span data-stu-id="c4673-480">Compliance Management</span></span>

<span data-ttu-id="c4673-481">若要详细了解角色和权限，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="c4673-481">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="c4673-482">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="c4673-482">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="c4673-483">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="c4673-483">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="c4673-484">威胁资源管理器和实时检测之间的差异</span><span class="sxs-lookup"><span data-stu-id="c4673-484">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="c4673-485">*实时检测报告在* Defender for Office 365 计划 1 中提供。</span><span class="sxs-lookup"><span data-stu-id="c4673-485">The *Real-time detections* report is available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="c4673-486">*威胁资源管理器* 在 Office 365 计划 2 的 Defender 中可用。</span><span class="sxs-lookup"><span data-stu-id="c4673-486">*Threat Explorer* is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="c4673-487">实时检测报告允许你实时查看检测。</span><span class="sxs-lookup"><span data-stu-id="c4673-487">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="c4673-488">威胁资源管理器也这样做，但它还提供给定攻击的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="c4673-488">Threat Explorer does this as well, but it also provides additional details for a given attack.</span></span>
- <span data-ttu-id="c4673-489">" *所有电子邮件* "视图在威胁资源管理器中可用，但在实时检测报告中不可用。</span><span class="sxs-lookup"><span data-stu-id="c4673-489">An *All email* view is available in Threat Explorer but not in the Real-time detections report.</span></span>
- <span data-ttu-id="c4673-490">威胁资源管理器中包含更多筛选功能和可用操作。</span><span class="sxs-lookup"><span data-stu-id="c4673-490">More filtering capabilities and available actions are included in Threat Explorer.</span></span> <span data-ttu-id="c4673-491">有关详细信息，请参阅 [Microsoft Defender for Office 365 服务说明：跨 Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)计划的 Defender 的功能可用性。</span><span class="sxs-lookup"><span data-stu-id="c4673-491">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
