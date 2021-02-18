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
description: 使用安全合规中心中的资源管理器和实时检测 &amp; 来高效地调查和响应威胁。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: daa7b4014d1302743578d79c2e1e0e1d2d5ac61f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288893"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="dca18-103">威胁资源管理器和实时检测</span><span class="sxs-lookup"><span data-stu-id="dca18-103">Threat Explorer and Real-time detections</span></span>


<span data-ttu-id="dca18-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="dca18-104">**Applies to**</span></span>
- [<span data-ttu-id="dca18-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="dca18-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="dca18-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dca18-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="dca18-107">如果你的组织拥有适用于[Office 365](office-365-atp.md)的 Microsoft Defender，并且你拥有[必要的](#required-licenses-and-permissions)权限，你拥有资源管理器或实时检测 (以前的实时报告 -查看新增功能[！) 。](#new-features-in-threat-explorer-and-real-time-detections)</span><span class="sxs-lookup"><span data-stu-id="dca18-107">If your organization has [Microsoft Defender for Office 365](office-365-atp.md), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **Real-time detections** (formerly *Real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="dca18-108">在安全&合规中心，转到 **"威胁** 管理"，然后选择"**资源管理器**"_或_**"实时检测"。**</span><span class="sxs-lookup"><span data-stu-id="dca18-108">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>


|<span data-ttu-id="dca18-109">使用 Microsoft Defender for Office 365 计划 2，可以看到：</span><span class="sxs-lookup"><span data-stu-id="dca18-109">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="dca18-110">使用 Microsoft Defender for Office 365 计划 1，可以看到：</span><span class="sxs-lookup"><span data-stu-id="dca18-110">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![威胁资源管理器](../../media/threatmgmt-explorer.png)|![实时检测](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="dca18-113">资源管理器或实时检测可帮助安全运营团队高效地调查和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="dca18-113">Explorer or Real-time detections helps your security operations team investigate and respond to threats efficiently.</span></span> <span data-ttu-id="dca18-114">报表类似于下图：</span><span class="sxs-lookup"><span data-stu-id="dca18-114">The report resembles the following image:</span></span>

![转到威胁管理 \> 资源管理器](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="dca18-116">通过此报告，您可以：</span><span class="sxs-lookup"><span data-stu-id="dca18-116">With this report, you can:</span></span>

- [<span data-ttu-id="dca18-117">查看 Microsoft 365 安全功能检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="dca18-117">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="dca18-118">查看网络钓鱼 URL 并单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="dca18-118">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- <span data-ttu-id="dca18-119">[仅从 Explorer (](#start-automated-investigation-and-response) Defender for Office 365 计划 2 中的视图启动自动调查和响应) </span><span class="sxs-lookup"><span data-stu-id="dca18-119">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- [<span data-ttu-id="dca18-120">调查恶意电子邮件等</span><span class="sxs-lookup"><span data-stu-id="dca18-120">Investigate malicious email, and more</span></span>](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="dca18-121">威胁资源管理器和实时检测的改进</span><span class="sxs-lookup"><span data-stu-id="dca18-121">Improvements to Threat Explorer and Real-time detections</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="dca18-122">威胁资源管理器中的标记</span><span class="sxs-lookup"><span data-stu-id="dca18-122">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="dca18-123">用户标记功能在 *预览版* 中，不向所有人提供，并且可能会更改。</span><span class="sxs-lookup"><span data-stu-id="dca18-123">The user tags feature is in *Preview*, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="dca18-124">有关发布计划的信息，请查看 Microsoft 365 路线图。</span><span class="sxs-lookup"><span data-stu-id="dca18-124">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="dca18-125">用户标记标识 Microsoft Defender for Office 365 中的特定用户组。</span><span class="sxs-lookup"><span data-stu-id="dca18-125">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="dca18-126">有关标记（包括许可和配置）详细信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="dca18-126">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="dca18-127">在威胁资源管理器中，可以在以下体验中查看有关用户标记的信息。</span><span class="sxs-lookup"><span data-stu-id="dca18-127">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="dca18-128">电子邮件网格视图</span><span class="sxs-lookup"><span data-stu-id="dca18-128">Email grid view</span></span>

<span data-ttu-id="dca18-129">电子邮件 **网格** 中的"标签"列包含已应用于发件人或收件人邮箱的所有标记。</span><span class="sxs-lookup"><span data-stu-id="dca18-129">The **Tags** column in the email grid contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="dca18-130">默认情况下，优先显示系统标记（如优先级帐户）。</span><span class="sxs-lookup"><span data-stu-id="dca18-130">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-131">![电子邮件网格视图中的筛选器标记](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-131">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="dca18-132">筛选</span><span class="sxs-lookup"><span data-stu-id="dca18-132">Filtering</span></span>

<span data-ttu-id="dca18-133">可以使用标记作为筛选器。</span><span class="sxs-lookup"><span data-stu-id="dca18-133">You can use tags as a filter.</span></span> <span data-ttu-id="dca18-134">仅跨优先级帐户或特定用户标记方案进行智能寻线。</span><span class="sxs-lookup"><span data-stu-id="dca18-134">Hunt just across priority accounts or specific user tags scenarios.</span></span> <span data-ttu-id="dca18-135">还可以排除具有特定标记的结果。</span><span class="sxs-lookup"><span data-stu-id="dca18-135">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="dca18-136">将此功能与其他筛选器相结合，以缩小调查范围。</span><span class="sxs-lookup"><span data-stu-id="dca18-136">Combine this functionality with other filters to narrow your scope of investigation.</span></span>

<span data-ttu-id="dca18-137">[![筛选器标记](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="dca18-137">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-138">![非筛选器标记](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-138">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="dca18-139">电子邮件详细信息飞出</span><span class="sxs-lookup"><span data-stu-id="dca18-139">Email detail flyout</span></span>
<span data-ttu-id="dca18-140">若要查看发件人和收件人的单个标记，请选择主题以打开邮件详细信息飞出。</span><span class="sxs-lookup"><span data-stu-id="dca18-140">To view the individual tags for sender and recipient, select the subject to open the message details flyout.</span></span> <span data-ttu-id="dca18-141">在 **"摘要"** 选项卡上，如果发件人和收件人标记存在电子邮件，则分别显示它们。</span><span class="sxs-lookup"><span data-stu-id="dca18-141">On the **Summary** tab, the sender and recipient tags are shown separately, if they're present for an email.</span></span>
<span data-ttu-id="dca18-142">有关发件人和收件人的单个标记的信息还扩展到导出的 CSV 数据，您可以在两个单独的列中查看这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="dca18-142">The information about individual tags for sender and recipient also extends to exported CSV data, where you can see these details in two separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-143">![电子邮件详细信息标记](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-143">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="dca18-144">标记信息也显示在 URL 单击飞出中。</span><span class="sxs-lookup"><span data-stu-id="dca18-144">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="dca18-145">若要查看它，请转到"网络钓鱼"或"所有电子邮件"视图，然后转到 **"URL"** 或 **"URL** 单击"选项卡。选择单个 URL 飞出以查看有关该 URL 的单击的其他详细信息，包括与该单击关联的标记。</span><span class="sxs-lookup"><span data-stu-id="dca18-145">To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Select an individual URL flyout to view additional details about clicks for that URL, including tags associated with that click.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-146">![URL 标记](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-146">![URL tags](../../media/tags-urls.png)</span></span>

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a><span data-ttu-id="dca18-147">威胁搜寻体验的改进 (即将推出的) </span><span class="sxs-lookup"><span data-stu-id="dca18-147">Improvements to the threat hunting experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="dca18-148">更新了电子邮件的威胁信息</span><span class="sxs-lookup"><span data-stu-id="dca18-148">Updated threat information for emails</span></span>

<span data-ttu-id="dca18-149">我们专注于平台和数据质量改进，以提高电子邮件记录的数据准确性和一致性。</span><span class="sxs-lookup"><span data-stu-id="dca18-149">We've focused on platform and data-quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="dca18-150">改进包括将传递前和传递后信息（例如，在 ZAP 过程中对电子邮件执行的操作）合并到单个记录中。</span><span class="sxs-lookup"><span data-stu-id="dca18-150">Improvements include consolidation of pre-delivery and post-delivery information, such as actions executed on an email as part of the ZAP process, into a single record.</span></span> <span data-ttu-id="dca18-151">其他详细信息（如垃圾邮件裁定、实体级威胁 (例如，哪个 URL 是恶意) ，以及最新的传递位置也包括在内。</span><span class="sxs-lookup"><span data-stu-id="dca18-151">Additional details like spam verdict, entity-level threats (for example, which URL was malicious), and latest delivery locations are also included.</span></span>

<span data-ttu-id="dca18-152">这些更新后，你将看到每封邮件的单个条目，无论影响邮件的不同传递后事件如何。</span><span class="sxs-lookup"><span data-stu-id="dca18-152">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that affect the message.</span></span> <span data-ttu-id="dca18-153">操作可以包括 ZAP、手动修正 (这意味着管理员) 操作、动态传递等。</span><span class="sxs-lookup"><span data-stu-id="dca18-153">Actions can include ZAP, manual remediation (which means admin action), dynamic delivery, and so on.</span></span>

<span data-ttu-id="dca18-154">除了显示恶意软件和网络钓鱼威胁之外，还可以看到与电子邮件关联的垃圾邮件裁定。</span><span class="sxs-lookup"><span data-stu-id="dca18-154">In addition to showing malware and phishing threats, you see the spam verdict associated with an email.</span></span> <span data-ttu-id="dca18-155">在电子邮件中，查看与电子邮件关联的所有威胁以及相应的检测技术。</span><span class="sxs-lookup"><span data-stu-id="dca18-155">Within the email, see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="dca18-156">电子邮件可以具有零、一或多个威胁。</span><span class="sxs-lookup"><span data-stu-id="dca18-156">An email can have zero, one, or multiple threats.</span></span> <span data-ttu-id="dca18-157">你将在电子邮件飞出的" **详细信息"部分** 看到当前威胁。</span><span class="sxs-lookup"><span data-stu-id="dca18-157">You'll see the current threats in the **Details** section of the email flyout.</span></span> <span data-ttu-id="dca18-158">对于恶意软件 (网络钓鱼) ，检测技术字段显示威胁检测映射，这是标识威胁的检测技术。</span><span class="sxs-lookup"><span data-stu-id="dca18-158">For multiple threats (such as malware and phishing), the **Detection tech** field shows the threat-detection mapping, which is the detection technology that identified the threat.</span></span>

<span data-ttu-id="dca18-159">检测技术集现在包括新的检测方法以及垃圾邮件检测技术。</span><span class="sxs-lookup"><span data-stu-id="dca18-159">The set of detection technologies now includes new detection methods, as well as spam-detection technologies.</span></span> <span data-ttu-id="dca18-160">您可以使用同一组检测技术筛选恶意软件、网络钓鱼、所有电子邮件 (不同电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="dca18-160">You can use the same set of detection technologies to filter the results across the different email views (Malware, Phish, All Email).</span></span>

> [!NOTE]
> <span data-ttu-id="dca18-161">裁定分析不一定与实体关联。</span><span class="sxs-lookup"><span data-stu-id="dca18-161">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="dca18-162">例如，电子邮件可能分类为网络钓鱼或垃圾邮件，但没有标记有钓鱼/垃圾邮件裁定的 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-162">As an example, an email might be classified as phish or spam, but there are no URLs that are stamped with a phish/spam verdict.</span></span> <span data-ttu-id="dca18-163">这是因为筛选器还会在分配裁定之前评估电子邮件的内容和其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="dca18-163">This is because the filters also evaluate content and other details for an email before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="dca18-164">URL 中的威胁</span><span class="sxs-lookup"><span data-stu-id="dca18-164">Threats in URLs</span></span>

<span data-ttu-id="dca18-165">现在，您可以在电子邮件飞出详细信息选项卡上看到 URL **的特定威胁**。威胁可以是 *恶意软件、**网络钓鱼、**垃圾邮件* 或 *无*.) </span><span class="sxs-lookup"><span data-stu-id="dca18-165">You can now see the specific threat for a URL on the email flyout **Details** tab. The threat can be *malware*, *phish*, *spam*, or *none*.)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-166">![URL 威胁](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-166">![URL threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="dca18-167">更新了 (视图) </span><span class="sxs-lookup"><span data-stu-id="dca18-167">Updated timeline view (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-168">![更新的时间线视图](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-168">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="dca18-169">时间线视图标识所有传递和传递后事件。</span><span class="sxs-lookup"><span data-stu-id="dca18-169">Timeline view identifies all delivery and post-delivery events.</span></span> <span data-ttu-id="dca18-170">它包括有关在这些事件子集时标识的威胁的信息。</span><span class="sxs-lookup"><span data-stu-id="dca18-170">It includes information about the threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="dca18-171">时间线视图还提供了有关执行任何其他操作的信息 (如 ZAP 或手动修正) 操作的结果。</span><span class="sxs-lookup"><span data-stu-id="dca18-171">Timeline view also provides information about any additional action taken (such as ZAP or manual remediation), along with the result of that action.</span></span> <span data-ttu-id="dca18-172">时间线视图信息包括：</span><span class="sxs-lookup"><span data-stu-id="dca18-172">Timeline view information includes:</span></span>

- <span data-ttu-id="dca18-173">**源：** 事件的源。</span><span class="sxs-lookup"><span data-stu-id="dca18-173">**Source:** Source of the event.</span></span> <span data-ttu-id="dca18-174">它可以是管理员/系统/用户。</span><span class="sxs-lookup"><span data-stu-id="dca18-174">It can be admin/system/user.</span></span>
- <span data-ttu-id="dca18-175">**事件：** 包括顶级事件，如原始传递、手动修正、ZAP、提交和动态传递。</span><span class="sxs-lookup"><span data-stu-id="dca18-175">**Event:** Includes top-level events like original delivery, manual remediation, ZAP, submissions, and dynamic delivery.</span></span>
- <span data-ttu-id="dca18-176">**操作：** 作为 ZAP 或管理员操作一部分执行的特定操作 (例如，软删除) 。</span><span class="sxs-lookup"><span data-stu-id="dca18-176">**Action:** The specific action that was taken either as part of ZAP or admin action (for example, soft delete).</span></span>
- <span data-ttu-id="dca18-177">**威胁：** 涵盖 (时标识) 恶意软件、网络钓鱼、垃圾邮件的威胁。</span><span class="sxs-lookup"><span data-stu-id="dca18-177">**Threats:** Covers the threats (malware, phish, spam) identified at that point of time.</span></span>
- <span data-ttu-id="dca18-178">**结果/详细信息：** 有关操作结果的更多信息，例如它是否作为 ZAP/admin 操作一部分执行。</span><span class="sxs-lookup"><span data-stu-id="dca18-178">**Result/Details:** More information about the result of the action, such as whether it was performed as part of ZAP/admin action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="dca18-179">原始和最新的送达位置</span><span class="sxs-lookup"><span data-stu-id="dca18-179">Original and latest delivery location</span></span>

<span data-ttu-id="dca18-180">目前，我们在电子邮件网格和电子邮件浮出控件中显示传递位置。</span><span class="sxs-lookup"><span data-stu-id="dca18-180">Currently, we surface delivery location in the email grid and email flyout.</span></span> <span data-ttu-id="dca18-181">传递 **位置字段** 被重命名为 **_原始传递位置_*_。我们还介绍了另一个字段_*_最新送达位置_**。</span><span class="sxs-lookup"><span data-stu-id="dca18-181">The **Delivery location** field is getting renamed **_Original delivery location_*_. And we're introducing another field, _*_Latest delivery location_**.</span></span>

<span data-ttu-id="dca18-182">**原始送达** 位置将提供有关电子邮件最初送达位置的更多信息。</span><span class="sxs-lookup"><span data-stu-id="dca18-182">**Original delivery location** will give more information about where an email was delivered initially.</span></span> <span data-ttu-id="dca18-183">**最新的送达位置** 将说明电子邮件在系统操作（如 *ZAP）* 或管理员操作（如移动到已删除项目） *之后登录的位置*。</span><span class="sxs-lookup"><span data-stu-id="dca18-183">**Latest delivery location** will state where an email landed after system actions like *ZAP* or admin actions like *Move to deleted items*.</span></span> <span data-ttu-id="dca18-184">最新传递位置旨在告知管理员邮件的传递后最近已知位置或任何系统/管理员操作。</span><span class="sxs-lookup"><span data-stu-id="dca18-184">Latest delivery location is intended to tell admins the message's last-known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="dca18-185">它不包括对电子邮件的任何最终用户操作。</span><span class="sxs-lookup"><span data-stu-id="dca18-185">It doesn't include any end-user actions on the email.</span></span> <span data-ttu-id="dca18-186">例如，如果用户删除邮件或将邮件移动到存档/pst，邮件"传递"位置将不会更新。</span><span class="sxs-lookup"><span data-stu-id="dca18-186">For example, if a user deleted a message or moved the message to archive/pst, the message "delivery" location won't be updated.</span></span> <span data-ttu-id="dca18-187">但是，如果系统操作更新了位置 (例如，ZAP 导致电子邮件移动到隔离邮箱) ，最新送达位置将显示为"隔离"。</span><span class="sxs-lookup"><span data-stu-id="dca18-187">But if a system action updated the location (for example, ZAP resulting in an email moving to quarantine), **Latest delivery location** would show as "quarantine."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-188">![更新的送达位置](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-188">![Updated delivery locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="dca18-189">在某些情况下，传递位置 **和\*\*\*\*传递** 操作可能显示为"未知"：</span><span class="sxs-lookup"><span data-stu-id="dca18-189">There are a few cases where **Delivery location** and **Delivery action** may show as "unknown":</span></span>
>
> - <span data-ttu-id="dca18-190">如果邮件已送达，您可能会将传递位置视为"已送达"，并且传递位置为"未知"，但收件箱规则将邮件移动到默认文件夹 (例如"草稿"或"存档") ，而不是"收件箱"或"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="dca18-190">You might see **Delivery location** as "delivered" and **Delivery location** as "unknown" if the message was delivered, but an Inbox rule moved the message to a default folder (such as Draft or Archive) instead of to the Inbox or Junk Email folder.</span></span>
>
> - <span data-ttu-id="dca18-191">**如果管理员** /系统操作（如 ZAP (尝试了 ZAP) ，但未找到邮件，则最新传递位置可能未知。</span><span class="sxs-lookup"><span data-stu-id="dca18-191">**Latest delivery location** can be unknown if an admin/system action (such as ZAP) was attempted, but the message wasn't found.</span></span> <span data-ttu-id="dca18-192">通常，该操作发生在用户移动或删除邮件之后。</span><span class="sxs-lookup"><span data-stu-id="dca18-192">Typically, the action happens after the user  moved or deleted the message.</span></span> <span data-ttu-id="dca18-193">在这种情况下，请验证 **日程表视图中的结果/** 详细信息列。</span><span class="sxs-lookup"><span data-stu-id="dca18-193">In such cases, verify the **Result/Details** column in timeline view.</span></span> <span data-ttu-id="dca18-194">查找"用户移动或删除的邮件"语句。</span><span class="sxs-lookup"><span data-stu-id="dca18-194">Look for the statement "Message moved or deleted by the user."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-195">![时间线的传递位置](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-195">![Delivery locations for timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="dca18-196">其他操作</span><span class="sxs-lookup"><span data-stu-id="dca18-196">Additional actions</span></span>

<span data-ttu-id="dca18-197">*在电子邮件* 传递后应用了其他操作。</span><span class="sxs-lookup"><span data-stu-id="dca18-197">*Additional actions* were applied after delivery of the email.</span></span> <span data-ttu-id="dca18-198">它们可以包括 *ZAP、* 管理员 (手动修正操作（如软删除) 、动态传递和重新处理 (，这些操作被反向检测为良好) 。 </span><span class="sxs-lookup"><span data-stu-id="dca18-198">They can include *ZAP*, *manual remediation* (action taken by an Admin such as soft delete), *dynamic delivery*, and *reprocessed* (for an email that was retroactively detected as good).</span></span>

> [!NOTE]
> - <span data-ttu-id="dca18-199">作为挂起更改的一部分，"由 ZAP 删除"值当前在传递操作筛选器中显示将消失。</span><span class="sxs-lookup"><span data-stu-id="dca18-199">As part of the pending changes, the "Removed by ZAP" value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="dca18-200">你将具有通过其他操作搜索 ZAP 尝试的所有 **电子邮件的方法**。</span><span class="sxs-lookup"><span data-stu-id="dca18-200">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span></span>
>
> - <span data-ttu-id="dca18-201">检测技术和其他操作将具有新的字段 **和值**， (ZAP 方案) 。</span><span class="sxs-lookup"><span data-stu-id="dca18-201">There will be new fields and values for **Detection technologies** and **Additional actions** (especially for ZAP scenarios).</span></span> <span data-ttu-id="dca18-202">您需要评估现有已保存的查询和跟踪的查询，以确保它们使用新值。</span><span class="sxs-lookup"><span data-stu-id="dca18-202">You'll need to evaluate your existing saved queries and tracked queries to make sure they work with the new values.</span></span>

> [!div class="mx-imgBorder"]

> ![资源管理器中的其他操作](../../media/Additional_Actions.png)

### <a name="system-overrides"></a><span data-ttu-id="dca18-204">系统覆盖</span><span class="sxs-lookup"><span data-stu-id="dca18-204">System overrides</span></span>

<span data-ttu-id="dca18-205">*系统覆盖* 使您能够对邮件的预定传递位置进行例外。</span><span class="sxs-lookup"><span data-stu-id="dca18-205">*System overrides* enable you to make exceptions to the intended delivery location of a message.</span></span> <span data-ttu-id="dca18-206">根据筛选堆栈标识的威胁和其他检测，覆盖系统提供的传递位置。</span><span class="sxs-lookup"><span data-stu-id="dca18-206">You override the delivery location provided by the system, based on the threats and other detections identified by the filtering stack.</span></span> <span data-ttu-id="dca18-207">可以通过租户或用户策略设置系统覆盖，以根据策略的建议传递邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-207">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="dca18-208">替代可以标识由于配置差异（如用户设置过宽的安全发件人策略）而意外传递恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-208">Overrides can identify unintentional delivery of malicious messages due to configurations gaps, such as an overly broad Safe Sender policy set by a user.</span></span> <span data-ttu-id="dca18-209">这些替代值可以是：</span><span class="sxs-lookup"><span data-stu-id="dca18-209">These override values can be:</span></span>

- <span data-ttu-id="dca18-210">用户策略允许：用户在邮箱级别创建策略以允许域或发件人。</span><span class="sxs-lookup"><span data-stu-id="dca18-210">Allowed by user policy: A user creates policies at the mailbox level to allows domains or senders.</span></span>
- <span data-ttu-id="dca18-211">被用户策略阻止：用户在邮件框级别创建策略以阻止域或发件人。</span><span class="sxs-lookup"><span data-stu-id="dca18-211">Blocked by user policy: A user creates policies at the mail box level to block domains or senders.</span></span>
- <span data-ttu-id="dca18-212">组织策略允许：组织的安全团队设置策略或 Exchange 邮件流规则 (也称为传输规则) ，以允许组织中的用户使用发件人和域。</span><span class="sxs-lookup"><span data-stu-id="dca18-212">Allowed by org policy: The organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="dca18-213">这适用于一组用户或整个组织。</span><span class="sxs-lookup"><span data-stu-id="dca18-213">This can be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="dca18-214">受组织策略阻止：组织的安全团队设置策略或邮件流规则，以阻止组织中的用户的发件人、域、邮件语言或源 IP。</span><span class="sxs-lookup"><span data-stu-id="dca18-214">Blocked by org policy: The organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="dca18-215">这可应用于一组用户或整个组织。</span><span class="sxs-lookup"><span data-stu-id="dca18-215">This can be applied to a set of users or the entire organization.</span></span>
- <span data-ttu-id="dca18-216">组织策略阻止的文件扩展名：组织的安全团队通过反恶意软件策略设置阻止文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="dca18-216">File extension blocked by org policy: An organization's security team blocks a file name extension through the anti-malware policy settings.</span></span> <span data-ttu-id="dca18-217">这些值现在将显示在电子邮件详细信息中，以帮助进行调查。</span><span class="sxs-lookup"><span data-stu-id="dca18-217">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="dca18-218">Secops 团队还可使用丰富的筛选功能筛选阻止的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="dca18-218">Secops teams can also use the rich-filtering capability to filter on blocked file extensions.</span></span>

<span data-ttu-id="dca18-219">[![资源管理器中的系统覆盖](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="dca18-219">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-220">![资源管理器中的系统覆盖网格](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-220">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-for-the-url-and-clicks-experience"></a><span data-ttu-id="dca18-221">URL 和单击体验的改进</span><span class="sxs-lookup"><span data-stu-id="dca18-221">Improvements for the URL and clicks experience</span></span>

<span data-ttu-id="dca18-222">改进包括：</span><span class="sxs-lookup"><span data-stu-id="dca18-222">The improvements include:</span></span>

- <span data-ttu-id="dca18-223">显示完整单击的 URL (URL，包括 URL) 的"单击"部分包含的任何查询参数。</span><span class="sxs-lookup"><span data-stu-id="dca18-223">Show the full clicked URL (including any query parameters that are part of the URL) in the **Clicks** section of the URL flyout.</span></span> <span data-ttu-id="dca18-224">目前，URL 域和路径显示在标题栏中。</span><span class="sxs-lookup"><span data-stu-id="dca18-224">Currently, the URL domain and path appear in the title bar.</span></span> <span data-ttu-id="dca18-225">我们正在扩展该信息以显示完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-225">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="dca18-226">跨 URL 筛选器 (*URL* 域与 *URL* 域和路径) ：更新会影响搜索包含 URL/单击裁定的邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-226">Fixes across URL filters (*URL* versus *URL domain* versus *URL domain and path*): The updates affect searching for messages that contain a URL/click verdict.</span></span> <span data-ttu-id="dca18-227">我们启用了与协议无关的搜索支持，因此无需使用即可搜索 `http` URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-227">We enabled support for protocol-agnostic searches, so you can search for a URL without using `http`.</span></span> <span data-ttu-id="dca18-228">默认情况下，除非明确指定了其他值，否则 URL 搜索将映射到 http。</span><span class="sxs-lookup"><span data-stu-id="dca18-228">By default, the URL search maps to http, unless another value is explicitly specified.</span></span> <span data-ttu-id="dca18-229">例如：</span><span class="sxs-lookup"><span data-stu-id="dca18-229">For example:</span></span>

   -  <span data-ttu-id="dca18-230">在 URL、URL 域和 URL 域和路径筛选器字段中使用和不带 `http://` 前缀进行搜索。   </span><span class="sxs-lookup"><span data-stu-id="dca18-230">Search with and without the `http://` prefix in the **URL**, **URL Domain**, and **URL Domain and Path** filter fields.</span></span> <span data-ttu-id="dca18-231">搜索应显示相同的结果。</span><span class="sxs-lookup"><span data-stu-id="dca18-231">The searches should show the same results.</span></span>

   -  <span data-ttu-id="dca18-232">在 `https://` **URL** 中搜索前缀。</span><span class="sxs-lookup"><span data-stu-id="dca18-232">Search for the `https://` prefix in **URL**.</span></span> <span data-ttu-id="dca18-233">如果未指定值，则 `http://` 假定前缀。</span><span class="sxs-lookup"><span data-stu-id="dca18-233">When no value is specified, the `http://` prefix is assumed.</span></span>

   - <span data-ttu-id="dca18-234">`/`在 URL 路径 **、URL 域\*\*\*\*、URL** 域和路径字段的开头和 **结尾忽略**。</span><span class="sxs-lookup"><span data-stu-id="dca18-234">`/` is ignored at the beginning and end of the **URL path**, **URL Domain**, **URL domain and path** fields.</span></span> <span data-ttu-id="dca18-235">`/` 将忽略 **URL** 字段的末尾。</span><span class="sxs-lookup"><span data-stu-id="dca18-235">`/` at the end of the **URL** field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="dca18-236">网络钓鱼可信度</span><span class="sxs-lookup"><span data-stu-id="dca18-236">Phish confidence level</span></span>

<span data-ttu-id="dca18-237">网络钓鱼可信度有助于确定电子邮件被分类为"网络钓鱼"的可信度。</span><span class="sxs-lookup"><span data-stu-id="dca18-237">Phish confidence level helps identify the degree of confidence with which an email was categorized as "phish."</span></span> <span data-ttu-id="dca18-238">两个可能的值是 *高和\*\*普通*。</span><span class="sxs-lookup"><span data-stu-id="dca18-238">The two possible values are *High* and *Normal*.</span></span> <span data-ttu-id="dca18-239">在初始阶段，此筛选器仅在威胁资源管理器的网络钓鱼视图中可用。</span><span class="sxs-lookup"><span data-stu-id="dca18-239">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="dca18-240">[![资源管理器中的网络钓鱼可信度](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="dca18-240">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="dca18-241">ZAP URL 信号</span><span class="sxs-lookup"><span data-stu-id="dca18-241">ZAP URL signal</span></span>

<span data-ttu-id="dca18-242">ZAP URL 信号通常用于 ZAP 网络钓鱼警报方案，其中电子邮件被标识为网络钓鱼，且在传递后被删除。</span><span class="sxs-lookup"><span data-stu-id="dca18-242">The ZAP URL signal is typically used for ZAP Phish alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="dca18-243">此信号将警报与资源管理器中的相应结果连接。</span><span class="sxs-lookup"><span data-stu-id="dca18-243">This signal connects the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="dca18-244">它是警报的 IIC 之一。</span><span class="sxs-lookup"><span data-stu-id="dca18-244">It's one of the IOCs for the alert.</span></span>

<span data-ttu-id="dca18-245">为了改进搜寻过程，我们更新了威胁资源管理器和实时检测，使搜寻体验更加一致。</span><span class="sxs-lookup"><span data-stu-id="dca18-245">To improve the hunting process, we've updated Threat Explorer and Real-time detections to make the hunting experience more consistent.</span></span> <span data-ttu-id="dca18-246">此处概述了这些更改：</span><span class="sxs-lookup"><span data-stu-id="dca18-246">The changes are outlined here:</span></span>

- [<span data-ttu-id="dca18-247">时区改进</span><span class="sxs-lookup"><span data-stu-id="dca18-247">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="dca18-248">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="dca18-248">Update in the refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="dca18-249">要添加到筛选器的图表深化</span><span class="sxs-lookup"><span data-stu-id="dca18-249">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="dca18-250">在产品信息更新中</span><span class="sxs-lookup"><span data-stu-id="dca18-250">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="dca18-251">按用户标记筛选</span><span class="sxs-lookup"><span data-stu-id="dca18-251">Filter by user tags</span></span>

<span data-ttu-id="dca18-252">现在，你可以对系统或自定义用户标记进行排序和筛选，以快速了解威胁的范围。</span><span class="sxs-lookup"><span data-stu-id="dca18-252">You can now sort and filter on system or custom user tags to quickly grasp the scope of threats.</span></span> <span data-ttu-id="dca18-253">若要了解更多信息，请参阅 [用户标记](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="dca18-253">To learn more, see [User tags](user-tags.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dca18-254">按用户标记进行筛选和排序当前处于公共预览阶段。</span><span class="sxs-lookup"><span data-stu-id="dca18-254">Filtering and sorting by user tags is currently in public preview.</span></span> <span data-ttu-id="dca18-255">在商业发布之前，可能会对此功能进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="dca18-255">This functionality may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dca18-256">Microsoft 对提供的信息不做出明示或暗示的担保。</span><span class="sxs-lookup"><span data-stu-id="dca18-256">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

![资源管理器中的"标记"列](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a><span data-ttu-id="dca18-258">时区改进</span><span class="sxs-lookup"><span data-stu-id="dca18-258">Timezone improvements</span></span>

<span data-ttu-id="dca18-259">你将在门户中以及导出的数据中查看电子邮件记录的时区。</span><span class="sxs-lookup"><span data-stu-id="dca18-259">You'll see the time zone for the email records in the Portal as well as for Exported data.</span></span> <span data-ttu-id="dca18-260">它将在电子邮件网格、详细信息飞出、电子邮件时间线和类似电子邮件等体验中可见，因此邮件结果集清晰。</span><span class="sxs-lookup"><span data-stu-id="dca18-260">It will be visible across experiences like Email Grid, Details flyout, Email Timeline, and Similar Emails, so the time zone for the result set is clear.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-261">![在资源管理器中查看时区](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-261">![View time zone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="dca18-262">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="dca18-262">Update in the refresh process</span></span>

<span data-ttu-id="dca18-263">例如，一些用户评论了与自动刷新 (混淆，例如，一旦更改日期，页面就会刷新) ，并手动刷新 (其他筛选器) 。</span><span class="sxs-lookup"><span data-stu-id="dca18-263">Some users have commented about confusion with automatic refresh (for example, as soon as you change the date, the page refreshes) and manual refresh (for other filters).</span></span> <span data-ttu-id="dca18-264">同样，删除筛选器会导致自动刷新。</span><span class="sxs-lookup"><span data-stu-id="dca18-264">Similarly, removing filters leads to automatic refresh.</span></span> <span data-ttu-id="dca18-265">在修改查询时更改筛选器可能会导致搜索体验不一致。</span><span class="sxs-lookup"><span data-stu-id="dca18-265">Changing filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="dca18-266">为了解决这些问题，我们将迁移到手动筛选机制。</span><span class="sxs-lookup"><span data-stu-id="dca18-266">To resolve these issues, we're moving to a manual-filtering mechanism.</span></span>

<span data-ttu-id="dca18-267">从体验的角度来看，用户可以从筛选器集和日期) 应用和删除不同的筛选器 (范围，并选择刷新按钮以在定义查询后筛选结果。</span><span class="sxs-lookup"><span data-stu-id="dca18-267">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set and date) and select the refresh button to filter the results after they've defined the query.</span></span> <span data-ttu-id="dca18-268">屏幕上现在也强调刷新按钮。</span><span class="sxs-lookup"><span data-stu-id="dca18-268">The refresh button is also now emphasized on the screen.</span></span> <span data-ttu-id="dca18-269">我们还更新了相关工具提示和产品内文档。</span><span class="sxs-lookup"><span data-stu-id="dca18-269">We've also updated the related tooltips and in-product documentation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-270">![选择"刷新"筛选结果](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-270">![Select Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="dca18-271">要添加到筛选器的图表深化</span><span class="sxs-lookup"><span data-stu-id="dca18-271">Chart drilldown to add to filters</span></span>

<span data-ttu-id="dca18-272">现在，你可以绘制图例值图表以将它们添加为筛选器。</span><span class="sxs-lookup"><span data-stu-id="dca18-272">You can now chart legend values to add them as filters.</span></span> <span data-ttu-id="dca18-273">选择 **"刷新** "按钮以筛选结果。</span><span class="sxs-lookup"><span data-stu-id="dca18-273">Select the **Refresh** button to filter the results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-274">![向下钻取图表以筛选](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-274">![Drill down through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="dca18-275">产品内信息更新</span><span class="sxs-lookup"><span data-stu-id="dca18-275">In-product information updates</span></span>

<span data-ttu-id="dca18-276">产品内现已提供其他详细信息，如网格内搜索结果总数 (请参阅) 。</span><span class="sxs-lookup"><span data-stu-id="dca18-276">Additional details are now available within the product, such as the total number of search results within the grid (see below).</span></span> <span data-ttu-id="dca18-277">我们改进了标签、错误消息和工具提示，以提供有关筛选器、搜索体验和搜索结果集。</span><span class="sxs-lookup"><span data-stu-id="dca18-277">We've improved labels, error messages, and tooltips to provide more information about the filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-278">![查看产品内信息](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-278">![View in-product information](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="dca18-279">威胁资源管理器中的扩展功能</span><span class="sxs-lookup"><span data-stu-id="dca18-279">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="dca18-280">主要目标用户</span><span class="sxs-lookup"><span data-stu-id="dca18-280">Top targeted users</span></span>

<span data-ttu-id="dca18-281">现在，我们在电子邮件的"恶意软件"视图中的"主要恶意软件系列"部分公开了主要目标 **用户** 的列表。</span><span class="sxs-lookup"><span data-stu-id="dca18-281">Today we expose the list of the top targeted users in the Malware view for emails, in the **Top Malware Families** section.</span></span> <span data-ttu-id="dca18-282">我们还将在"网络钓鱼"和"所有电子邮件"视图中扩展此视图。</span><span class="sxs-lookup"><span data-stu-id="dca18-282">We'll be extending this view in the Phish and All Email views as well.</span></span> <span data-ttu-id="dca18-283">你将能够看到前五个目标用户，以及每个用户针对相应视图的尝试次数。</span><span class="sxs-lookup"><span data-stu-id="dca18-283">You'll be able to see the top-five targeted users, along with the number of attempts for each user for the corresponding view.</span></span> <span data-ttu-id="dca18-284">例如，对于网络钓鱼视图，你将看到网络钓鱼尝试次数。</span><span class="sxs-lookup"><span data-stu-id="dca18-284">For example, for Phish view, you'll see the number of Phish attempts.</span></span>

<span data-ttu-id="dca18-285">你将能够导出目标用户列表（最多 3，000 个）以及每个电子邮件视图的脱机分析尝试次数。</span><span class="sxs-lookup"><span data-stu-id="dca18-285">You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="dca18-286">此外，选择尝试次数（例如 (，) 下图中的 13 次尝试将在威胁资源管理器中打开筛选视图，因此可以查看该用户的电子邮件和威胁的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="dca18-286">In addition, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-287">![主要目标用户](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-287">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="dca18-288">Exchange 传输规则</span><span class="sxs-lookup"><span data-stu-id="dca18-288">Exchange transport rules</span></span>

<span data-ttu-id="dca18-289">作为数据扩充的一部分，你将能够看到应用于邮件的所有不同 Exchange 传输规则 (ETR) ETR 规则。</span><span class="sxs-lookup"><span data-stu-id="dca18-289">As part of data enrichment, you'll be able to see all the different Exchange transport rules (ETR) that were applied to a message.</span></span> <span data-ttu-id="dca18-290">此信息将在电子邮件网格视图中提供。</span><span class="sxs-lookup"><span data-stu-id="dca18-290">This information will be available in the Email grid view.</span></span> <span data-ttu-id="dca18-291">若要查看它，请选择网格 **中的** 列选项，然后从列选项中添加 **Exchange** 传输规则。</span><span class="sxs-lookup"><span data-stu-id="dca18-291">To view it,  select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="dca18-292">它还将在电子邮件中的"详细信息"飞出显示。</span><span class="sxs-lookup"><span data-stu-id="dca18-292">It will also be visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="dca18-293">您将能够查看已应用于邮件的传输规则的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="dca18-293">You'll be able to see both the GUID and the name of the transport rules that were applied to the message.</span></span> <span data-ttu-id="dca18-294">可以使用传输规则的名称搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-294">You'll be able to search for the messages by using the name of the transport rule.</span></span> <span data-ttu-id="dca18-295">这是一个"包含"搜索，这意味着您也可以执行部分搜索。</span><span class="sxs-lookup"><span data-stu-id="dca18-295">This is a "Contains" search, which means you can do partial searches as well.</span></span>

#### <a name="important-note"></a><span data-ttu-id="dca18-296">重要说明：</span><span class="sxs-lookup"><span data-stu-id="dca18-296">Important note:</span></span>

<span data-ttu-id="dca18-297">ETR 搜索和名称可用性取决于分配给您的特定角色。</span><span class="sxs-lookup"><span data-stu-id="dca18-297">ETR search and name availability depend on the specific role that's assigned to you.</span></span> <span data-ttu-id="dca18-298">您需要具有以下角色/权限之一才能查看 ETR 名称和搜索。</span><span class="sxs-lookup"><span data-stu-id="dca18-298">You need to have one of the following roles/permissions to view the ETR names and search.</span></span> <span data-ttu-id="dca18-299">如果未分配任何这些角色，则看不到传输规则的名称或使用 ETR 名称搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-299">If you don't have any of these roles assigned to you, you can't see the names of the transport rules or search for messages by using ETR names.</span></span> <span data-ttu-id="dca18-300">但是，您可以在"电子邮件详细信息"中查看 ETR 标签和 GUID 信息。</span><span class="sxs-lookup"><span data-stu-id="dca18-300">However, you could see the ETR label and GUID information in the Email Details.</span></span> <span data-ttu-id="dca18-301">电子邮件网格、电子邮件飞出、筛选器和导出中的其他记录查看体验不受影响。</span><span class="sxs-lookup"><span data-stu-id="dca18-301">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>

- <span data-ttu-id="dca18-302">仅 EXO - 数据丢失防护：全部</span><span class="sxs-lookup"><span data-stu-id="dca18-302">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="dca18-303">仅 EXO - O365SupportViewConfig：全部</span><span class="sxs-lookup"><span data-stu-id="dca18-303">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="dca18-304">Microsoft Azure Active Directory 或 EXO - 安全管理员：全部</span><span class="sxs-lookup"><span data-stu-id="dca18-304">Microsoft Azure Active Directory or EXO - Security Admin: All</span></span>
- <span data-ttu-id="dca18-305">AAD 或 EXO - 安全读取器：全部</span><span class="sxs-lookup"><span data-stu-id="dca18-305">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="dca18-306">仅 EXO - 传输规则：全部</span><span class="sxs-lookup"><span data-stu-id="dca18-306">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="dca18-307">仅 EXO - View-Only配置：全部</span><span class="sxs-lookup"><span data-stu-id="dca18-307">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="dca18-308">在电子邮件网格、详细信息飞出和导出的 CSV 中，ETR 将显示一个名称/GUID，如下所示。</span><span class="sxs-lookup"><span data-stu-id="dca18-308">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-309">![Exchange 传输规则](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-309">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="dca18-310">入站连接器</span><span class="sxs-lookup"><span data-stu-id="dca18-310">Inbound connectors</span></span>

<span data-ttu-id="dca18-311">连接器是一组说明，用于自定义电子邮件在 Microsoft 365 或 Office 365 组织之间流动的流式。</span><span class="sxs-lookup"><span data-stu-id="dca18-311">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="dca18-312">它们使您能够应用任何安全限制或控件。</span><span class="sxs-lookup"><span data-stu-id="dca18-312">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="dca18-313">在威胁资源管理器中，你现在可以查看与电子邮件相关的连接器，然后使用连接器名称搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-313">Within Threat Explorer, you can now view the connectors that are related to an email and search for emails by using connector names.</span></span>

<span data-ttu-id="dca18-314">连接器的搜索本质上是"包含"的，这意味着部分关键字搜索也应正常工作。</span><span class="sxs-lookup"><span data-stu-id="dca18-314">The search for connectors is "contains" in nature, which means partial keyword searches should work as well.</span></span> <span data-ttu-id="dca18-315">在主网格视图、"详细信息"飞出控件和导出的 CSV 中，连接器以名称/GUID 格式显示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dca18-315">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown here:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-316">![连接器详细信息](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-316">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="dca18-317">威胁资源管理器中的新功能和实时检测</span><span class="sxs-lookup"><span data-stu-id="dca18-317">New features in Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="dca18-318">威胁资源管理器和实时检测中提供了三项新功能：</span><span class="sxs-lookup"><span data-stu-id="dca18-318">Three new features are available in Threat Explorer and Real-time detections:</span></span>

- [<span data-ttu-id="dca18-319">预览电子邮件头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="dca18-319">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="dca18-320">电子邮件时间线</span><span class="sxs-lookup"><span data-stu-id="dca18-320">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="dca18-321">导出 URL 单击数据</span><span class="sxs-lookup"><span data-stu-id="dca18-321">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="dca18-322">下面概述了这些新功能。</span><span class="sxs-lookup"><span data-stu-id="dca18-322">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="dca18-323">预览电子邮件头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="dca18-323">Preview email header and download email body</span></span>

<span data-ttu-id="dca18-324">现在，你可以预览电子邮件头，在威胁资源管理器中下载电子邮件正文，管理员可以分析下载的邮件头/电子邮件中的威胁。</span><span class="sxs-lookup"><span data-stu-id="dca18-324">You can now preview an email header and download the email body in Threat Explorer Admins can analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="dca18-325">由于下载电子邮件可能会暴露信息的风险，因此此过程由基于角色的访问控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="dca18-325">Because downloading email messages can risk exposure of information, this process is controlled by role-based access control (RBAC).</span></span> <span data-ttu-id="dca18-326">必须将新角色 *"预览*"添加到另一个角色组 (如安全操作或安全管理员) ，以授予在"所有电子邮件"视图中下载邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="dca18-326">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails in all-email messages view.</span></span> <span data-ttu-id="dca18-327">但是，查看电子邮件头不需要任何其他角色 (在威胁资源管理器中查看邮件) 。</span><span class="sxs-lookup"><span data-stu-id="dca18-327">However, viewing email header does not require any additional role (other than what is required to view messages in Threat Explorer).</span></span>

<span data-ttu-id="dca18-328">资源管理器和实时检测还将获取新字段，这些字段可提供电子邮件到达位置的更完整图片。</span><span class="sxs-lookup"><span data-stu-id="dca18-328">Explorer and Real-time detections will also get new fields that provide a more complete picture of where your email messages land.</span></span> <span data-ttu-id="dca18-329">这些更改使安全操作更易于搜寻。</span><span class="sxs-lookup"><span data-stu-id="dca18-329">These changes  make hunting easier for Security Ops.</span></span> <span data-ttu-id="dca18-330">但主要结果是，您可以一目了然地了解问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="dca18-330">But the main result is you can know the location of problem email messages at a glance.</span></span>

<span data-ttu-id="dca18-331">如何完成此操作？</span><span class="sxs-lookup"><span data-stu-id="dca18-331">How is this done?</span></span> <span data-ttu-id="dca18-332">传递状态现在分为两列：</span><span class="sxs-lookup"><span data-stu-id="dca18-332">Delivery status is now broken out into two columns:</span></span>

- <span data-ttu-id="dca18-333">**传递操作** - 电子邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="dca18-333">**Delivery action** - Status of the email.</span></span>
- <span data-ttu-id="dca18-334">**传递位置** - 电子邮件的路由位置。</span><span class="sxs-lookup"><span data-stu-id="dca18-334">**Delivery location** - Where the email was routed.</span></span>

<span data-ttu-id="dca18-335">*传递* 操作是对现有策略或检测对电子邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="dca18-335">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="dca18-336">以下是电子邮件的可能操作：</span><span class="sxs-lookup"><span data-stu-id="dca18-336">Here are the possible actions for an email:</span></span>

|<span data-ttu-id="dca18-337">已送达</span><span class="sxs-lookup"><span data-stu-id="dca18-337">Delivered</span></span>|<span data-ttu-id="dca18-338">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="dca18-338">Junked</span></span>|<span data-ttu-id="dca18-339">Blocked</span><span class="sxs-lookup"><span data-stu-id="dca18-339">Blocked</span></span>|<span data-ttu-id="dca18-340">已替换</span><span class="sxs-lookup"><span data-stu-id="dca18-340">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="dca18-341">电子邮件已传递到用户的收件箱或文件夹，用户可以访问它。</span><span class="sxs-lookup"><span data-stu-id="dca18-341">Email was delivered to the inbox or folder of a user, and the user can access it.</span></span>|<span data-ttu-id="dca18-342">电子邮件已发送到用户的"垃圾邮件"或"已删除"文件夹，用户可以访问它。</span><span class="sxs-lookup"><span data-stu-id="dca18-342">Email was sent to the user's Junk  or Deleted folder, and the user can access it.</span></span>|<span data-ttu-id="dca18-343">已隔离、失败或已丢弃的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-343">Emails that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="dca18-344">用户无法访问这些邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-344">These mails are inaccessible to the user.</span></span>|<span data-ttu-id="dca18-345">电子邮件的恶意附件替换为 .txt 文件，这些文件指出附件是恶意附件。</span><span class="sxs-lookup"><span data-stu-id="dca18-345">Email had malicious attachments replaced by .txt files that state the attachment was malicious.</span></span>|

<span data-ttu-id="dca18-346">下面是用户可以看到和看不到的：</span><span class="sxs-lookup"><span data-stu-id="dca18-346">Here is what the user can and can't see:</span></span>

|<span data-ttu-id="dca18-347">最终用户可访问</span><span class="sxs-lookup"><span data-stu-id="dca18-347">Accessible to end users</span></span>|<span data-ttu-id="dca18-348">最终用户无法访问</span><span class="sxs-lookup"><span data-stu-id="dca18-348">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="dca18-349">已送达</span><span class="sxs-lookup"><span data-stu-id="dca18-349">Delivered</span></span>|<span data-ttu-id="dca18-350">Blocked</span><span class="sxs-lookup"><span data-stu-id="dca18-350">Blocked</span></span>|
|<span data-ttu-id="dca18-351">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="dca18-351">Junked</span></span>|<span data-ttu-id="dca18-352">已替换</span><span class="sxs-lookup"><span data-stu-id="dca18-352">Replaced</span></span>|

<span data-ttu-id="dca18-353">**传递** 位置显示运行传递后的策略和检测的结果。</span><span class="sxs-lookup"><span data-stu-id="dca18-353">**Delivery location** shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="dca18-354">它链接到传递 **_操作_**。</span><span class="sxs-lookup"><span data-stu-id="dca18-354">It's linked to **_Delivery action_**.</span></span> <span data-ttu-id="dca18-355">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="dca18-355">These are the possible values:</span></span>

- <span data-ttu-id="dca18-356">*收件箱或文件夹*：电子邮件位于收件箱或文件夹 (根据电子邮件规则) 。</span><span class="sxs-lookup"><span data-stu-id="dca18-356">*Inbox or folder*: The email is in the inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="dca18-357">*本地或外部*：邮箱在云中不存在，但位于本地。</span><span class="sxs-lookup"><span data-stu-id="dca18-357">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="dca18-358">*垃圾邮件* 文件夹：电子邮件位于用户的"垃圾邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dca18-358">*Junk folder*: The email is in a user's Junk folder.</span></span>
- <span data-ttu-id="dca18-359">*"已删除邮件"文件夹*：用户的"已删除邮件"文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-359">*Deleted items folder*: The email in a user's Deleted items folder.</span></span>
- <span data-ttu-id="dca18-360">*隔离*：电子邮件位于隔离邮箱中，不在用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="dca18-360">*Quarantine*: The email is in quarantine and not in a user's mailbox.</span></span>
- <span data-ttu-id="dca18-361">*失败*：电子邮件无法到达邮箱。</span><span class="sxs-lookup"><span data-stu-id="dca18-361">*Failed*: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="dca18-362">*已* 丢弃：电子邮件在邮件流中的某处丢失。</span><span class="sxs-lookup"><span data-stu-id="dca18-362">*Dropped*: The email got lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="dca18-363">电子邮件时间线</span><span class="sxs-lookup"><span data-stu-id="dca18-363">Email timeline</span></span>

<span data-ttu-id="dca18-364">电子邮件 **时间线** 是一种新的资源管理器功能，可改善管理员的搜寻体验。</span><span class="sxs-lookup"><span data-stu-id="dca18-364">The **Email timeline** is a new Explorer feature that improves the hunting experience for admins.</span></span> <span data-ttu-id="dca18-365">它减少检查不同位置以尝试了解事件所花的时间。</span><span class="sxs-lookup"><span data-stu-id="dca18-365">It cuts the time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="dca18-366">当多个事件在电子邮件到达的同一时间或接近同一时间发生时，这些事件将显示在时间线视图中。</span><span class="sxs-lookup"><span data-stu-id="dca18-366">When multiple events happen at or close to the same time an email arrives, those events are displayed in a timeline view.</span></span> <span data-ttu-id="dca18-367">在"特殊操作"列中捕获在电子邮件传递后发生的一 **些** 事件。</span><span class="sxs-lookup"><span data-stu-id="dca18-367">Some events that happen to your email post-delivery are captured in the **Special action** column.</span></span> <span data-ttu-id="dca18-368">管理员可以将时间线信息与对邮件传递后采取的特殊操作相结合，以深入了解其策略如何工作、邮件最终路由在何处，在某些情况下，最终评估是什么。</span><span class="sxs-lookup"><span data-stu-id="dca18-368">Admins can combine  information from the timeline with the special action taken on the mail post-delivery to get insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="dca18-369">有关详细信息，请参阅 [调查和修正在 Office 365](investigate-malicious-email-that-was-delivered.md)中传递的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-369">For more information, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="dca18-370">导出 URL 单击数据</span><span class="sxs-lookup"><span data-stu-id="dca18-370">Export URL click data</span></span>

<span data-ttu-id="dca18-371">现在可以将 URL 单击报告导出到 Microsoft Excel 以查看其网络消息 **ID** 和单击裁定，这有助于说明 URL 单击流量的来源。</span><span class="sxs-lookup"><span data-stu-id="dca18-371">You can now export reports for URL clicks to Microsoft Excel to view their **network message ID** and **click verdict**, which helps explain where your URL click traffic originated.</span></span> <span data-ttu-id="dca18-372">操作方法如下：在 Office 365 快速启动栏上的威胁管理中，按照以下链操作：</span><span class="sxs-lookup"><span data-stu-id="dca18-372">Here's how it works: In Threat Management on the Office 365 quick-launch bar, follow this chain:</span></span>

<span data-ttu-id="dca18-373">**资源管理器** \>**查看网络钓鱼** \>**单击次数** \>**顶部 URL 或** **URL"顶部** \> 单击"选择任意记录以打开 URL 飞出。</span><span class="sxs-lookup"><span data-stu-id="dca18-373">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs** or **URL Top Clicks** \> select any record to open the URL flyout.</span></span>

<span data-ttu-id="dca18-374">在列表中选择 URL 时，你将在飞出面板上看到新的"导出"按钮。</span><span class="sxs-lookup"><span data-stu-id="dca18-374">When you select a URL in the list, you'll see a new **Export** button on the fly-out panel.</span></span> <span data-ttu-id="dca18-375">使用此按钮将数据移动到 Excel 电子表格，以便更轻松地报告。</span><span class="sxs-lookup"><span data-stu-id="dca18-375">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="dca18-376">按照此路径到达实时检测报告中的相同位置：</span><span class="sxs-lookup"><span data-stu-id="dca18-376">Follow this path to get to the same location in the Real-time detections report:</span></span>

<span data-ttu-id="dca18-377">**资源管理器** \>**实时检测** \>**查看网络钓鱼** \>**URL** \>**顶部 URL** 或 **顶部单击** \> 选择任意记录以打开 URL 飞出控件 \> ，导航到 **"单击"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="dca18-377">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs** or **Top Clicks** \> Select any record to open the URL flyout \> navigate to the **Clicks** tab.</span></span>

> [!TIP]
> <span data-ttu-id="dca18-378">通过资源管理器或关联的第三方工具搜索 ID 时，网络消息 ID 将单击映射回特定邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-378">The Network Message ID maps the click back to specific mails when you search on the ID through Explorer or associated third-party tools.</span></span> <span data-ttu-id="dca18-379">此类搜索可标识与单击结果关联的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dca18-379">Such searches identify the email associated with a click result.</span></span> <span data-ttu-id="dca18-380">具有关联的网络消息 ID 可以更快速、更强大的分析。</span><span class="sxs-lookup"><span data-stu-id="dca18-380">Having the correlated Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dca18-381">![资源管理器中的"单击"选项卡](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-381">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="dca18-382">查看通过电子邮件技术检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="dca18-382">See malware detected in email by technology</span></span>

<span data-ttu-id="dca18-383">假设你想要查看在按 Microsoft 365 技术排序的电子邮件中检测到的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="dca18-383">Suppose you want to see malware detected in email sorted by Microsoft 365 technology.</span></span> <span data-ttu-id="dca18-384">为此，请使用资源管理器>或[](threat-explorer-views.md#email--malware)实时检测的"电子邮件 (恶意软件"视图) 。</span><span class="sxs-lookup"><span data-stu-id="dca18-384">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="dca18-385">在安全&中心 () ，选择威胁管理资源管理器 (或实时检测 <https://protection.office.com>  \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="dca18-385">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="dca18-386"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="dca18-386">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="dca18-387">在"**查看"** 菜单中，选择 **"电子邮件** \> **恶意软件"。**</span><span class="sxs-lookup"><span data-stu-id="dca18-387">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dca18-388">![资源管理器的"查看"菜单](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-388">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="dca18-389">单击 **"** 发件人"，然后选择 **"基本** \> **检测技术"。**</span><span class="sxs-lookup"><span data-stu-id="dca18-389">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="dca18-390">你的检测技术现在用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="dca18-390">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dca18-391">![恶意软件检测技术](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-391">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="dca18-392">选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="dca18-392">Choose an option.</span></span> <span data-ttu-id="dca18-393">然后选择" **刷新"** 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="dca18-393">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dca18-394">![选定的检测技术](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-394">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="dca18-395">报告将刷新以显示恶意软件使用所选的技术选项在电子邮件中检测到的结果。</span><span class="sxs-lookup"><span data-stu-id="dca18-395">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="dca18-396">在这里，你可以执行进一步的分析。</span><span class="sxs-lookup"><span data-stu-id="dca18-396">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="dca18-397">查看网络钓鱼 URL 并单击裁定数据</span><span class="sxs-lookup"><span data-stu-id="dca18-397">View phishing URL and click verdict data</span></span>

<span data-ttu-id="dca18-398">假设您希望查看通过电子邮件中的 URL（包括允许、阻止和重写的 URL 列表）的网络钓鱼尝试。</span><span class="sxs-lookup"><span data-stu-id="dca18-398">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="dca18-399">若要标识单击的 URL， [必须](atp-safe-links.md) 配置安全链接。</span><span class="sxs-lookup"><span data-stu-id="dca18-399">To identify URLs that were clicked, [Safe Links](atp-safe-links.md) must be configured.</span></span> <span data-ttu-id="dca18-400">请确保为安全 [链接](set-up-atp-safe-links-policies.md) 的单击时间和单击裁定日志记录设置安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="dca18-400">Make sure that you set up [Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="dca18-401">若要查看邮件中的网络钓鱼 URL 并单击网络钓鱼邮件中的 URL，请使用资源管理器的电子邮件[  >  ](threat-explorer-views.md#email--phish)网络钓鱼视图或实时检测。</span><span class="sxs-lookup"><span data-stu-id="dca18-401">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="dca18-402">在安全&中心 () ，选择威胁管理资源管理器 (或实时检测 <https://protection.office.com>  \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="dca18-402">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="dca18-403"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="dca18-403">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="dca18-404">在"**查看"** 菜单中，选择 **"电子邮件** \> **钓鱼邮件"。**</span><span class="sxs-lookup"><span data-stu-id="dca18-404">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dca18-405">![网络钓鱼上下文中资源管理器的视图菜单](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-405">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="dca18-406">单击 **"** 发件人"，然后选择 **"URL 单击** \> **"裁定**。</span><span class="sxs-lookup"><span data-stu-id="dca18-406">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="dca18-407">选择一个或多个选项，如"阻止"和"阻止 **覆盖**"，然后选择与应用该筛选器的选项位于同一行上的"刷新"按钮。</span><span class="sxs-lookup"><span data-stu-id="dca18-407">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="dca18-408"> (不刷新浏览器窗口。) </span><span class="sxs-lookup"><span data-stu-id="dca18-408">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dca18-409">![URL 和单击裁定](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-409">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="dca18-410">报告将刷新以显示报告下的"URL"选项卡上的两个不同的 URL 表：</span><span class="sxs-lookup"><span data-stu-id="dca18-410">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="dca18-411">**顶部 URL** 是筛选到的邮件中的 URL，每个 URL 的电子邮件传递操作计数。</span><span class="sxs-lookup"><span data-stu-id="dca18-411">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="dca18-412">在网络钓鱼电子邮件视图中，此列表通常包含合法 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-412">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="dca18-413">攻击者在邮件中混有好 URL 和坏 URL，以尝试传递这些 URL，但它们会使恶意链接看起来更有趣。</span><span class="sxs-lookup"><span data-stu-id="dca18-413">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="dca18-414">URL 表按总电子邮件计数排序，但隐藏此列可简化视图。</span><span class="sxs-lookup"><span data-stu-id="dca18-414">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="dca18-415">**顶部单击** 是单击的安全链接包装 URL，按总点击计数排序。</span><span class="sxs-lookup"><span data-stu-id="dca18-415">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="dca18-416">为了简化视图，也不显示此列。</span><span class="sxs-lookup"><span data-stu-id="dca18-416">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="dca18-417">按列的总计数指示每个单击 URL 的安全链接单击裁定计数。</span><span class="sxs-lookup"><span data-stu-id="dca18-417">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="dca18-418">在网络钓鱼电子邮件视图中，这些 URL 通常是可疑或恶意的 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-418">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="dca18-419">但是，该视图可能包含不是威胁但包含钓鱼邮件的 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-419">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="dca18-420">此处不会显示对未包装链接的 URL 单击。</span><span class="sxs-lookup"><span data-stu-id="dca18-420">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="dca18-421">这两个 URL 表按传递操作和位置显示网络钓鱼电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-421">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="dca18-422">这些表显示了在出现警告时被阻止或访问的 URL 单击，因此你可以看到向用户显示哪些潜在的错误链接，以及用户单击的内容。</span><span class="sxs-lookup"><span data-stu-id="dca18-422">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the user's clicked.</span></span> <span data-ttu-id="dca18-423">在这里，你可以执行进一步的分析。</span><span class="sxs-lookup"><span data-stu-id="dca18-423">From here, you can conduct further analysis.</span></span> <span data-ttu-id="dca18-424">例如，在图表下方，你可以看到在组织环境中被阻止的电子邮件中的顶部 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-424">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dca18-425">![被阻止的浏览器 URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-425">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="dca18-426">选择 URL 以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="dca18-426">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dca18-427">在"URL"弹出对话框中，删除对电子邮件的筛选以显示环境中 URL 公开的完整视图。</span><span class="sxs-lookup"><span data-stu-id="dca18-427">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="dca18-428">这允许你在资源管理器中筛选你关注的电子邮件，查找潜在威胁的特定 URL，然后通过 URL 详细信息对话框 () 扩展你了解环境中 URL 的曝光) 而无需将 URL 筛选器添加到资源管理器视图本身。</span><span class="sxs-lookup"><span data-stu-id="dca18-428">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="dca18-429">单击裁定的解释</span><span class="sxs-lookup"><span data-stu-id="dca18-429">Interpretation of click verdicts</span></span>

<span data-ttu-id="dca18-430">在"电子邮件"或"URL"飞出、点击量最高以及筛选体验内，你将看到不同的单击裁定值：</span><span class="sxs-lookup"><span data-stu-id="dca18-430">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="dca18-431">**无：** 无法捕获 URL 裁定。</span><span class="sxs-lookup"><span data-stu-id="dca18-431">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="dca18-432">用户可能已经单击了 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-432">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="dca18-433">**允许：** 允许用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-433">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="dca18-434">**已阻止：** 阻止用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-434">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="dca18-435">**待定裁定：** 用户已显示等待触发的页面。</span><span class="sxs-lookup"><span data-stu-id="dca18-435">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="dca18-436">**被阻止重写：** 阻止用户直接导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-436">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="dca18-437">但是，用户会过度设置此块以导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-437">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="dca18-438">**未通过待定裁定：** 用户已显示触发页面。</span><span class="sxs-lookup"><span data-stu-id="dca18-438">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="dca18-439">但是，用户会过度显示消息以访问 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-439">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="dca18-440">**错误：** 用户收到错误页面，或捕获裁定时出错。</span><span class="sxs-lookup"><span data-stu-id="dca18-440">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="dca18-441">**失败：** 捕获裁定时发生未知异常。</span><span class="sxs-lookup"><span data-stu-id="dca18-441">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="dca18-442">用户可能已经单击了 URL。</span><span class="sxs-lookup"><span data-stu-id="dca18-442">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="dca18-443">查看用户报告的电子邮件</span><span class="sxs-lookup"><span data-stu-id="dca18-443">Review email messages reported by users</span></span>

<span data-ttu-id="dca18-444">假设您希望查看组织中用户通过报告邮件外接程序或报告网络钓鱼外接程序报告为垃圾邮件、非垃圾邮件或网络钓鱼[的电子邮件](enable-the-report-phish-add-in.md)。 [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="dca18-444">Suppose that you want to see email messages that users in your organization reported as *Junk*, *Not Junk*, or *Phishing* through the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span> <span data-ttu-id="dca18-445">若要查看它们，请使用资源管理器中的[  >  ](threat-explorer-views.md#email--submissions)"电子邮件提交" (或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="dca18-445">To see them, use the [**Email** > **Submissions**](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="dca18-446">在安全&中心 () ，选择威胁管理资源管理器 (或实时检测 <https://protection.office.com>  \> ) 。 </span><span class="sxs-lookup"><span data-stu-id="dca18-446">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="dca18-447"> (此示例使用 Explorer.) </span><span class="sxs-lookup"><span data-stu-id="dca18-447">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="dca18-448">在"**查看"** 菜单中，选择 **"** \> **电子邮件提交"。**</span><span class="sxs-lookup"><span data-stu-id="dca18-448">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dca18-449">![电子邮件资源管理器的"查看"菜单](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-449">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="dca18-450">单击 **"** 发件人"，然后选择 **"基本** \> **报告类型"。**</span><span class="sxs-lookup"><span data-stu-id="dca18-450">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="dca18-451">选择一个选项，如 **钓鱼** 邮件，然后选择" **刷新"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="dca18-451">Select an option, such as **Phish**, and then select the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dca18-452">![用户报告的网络钓鱼](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="dca18-452">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="dca18-453">报告将刷新以显示有关组织中人员报告为网络钓鱼尝试的电子邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="dca18-453">The report refreshes to show data about email messages that people in your organization reported as a phishing attempt.</span></span> <span data-ttu-id="dca18-454">可以使用此信息进行进一步分析，如有必要，在 [Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)中调整防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="dca18-454">You can use this information to conduct further analysis, and, if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="dca18-455">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="dca18-455">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="dca18-456">Microsoft Defender for *Office 365 计划 2* 和 Office *365 E5* 中提供了自动调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="dca18-456">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="dca18-457">[自动调查和响应](automated-investigation-response-office.md) 可以节省安全运营团队调查和缓解网络攻击所花费的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="dca18-457">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="dca18-458">除了配置可触发安全手册的警报之外，还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="dca18-458">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="dca18-459">有关详细信息，请参阅 [示例：安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="dca18-459">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a><span data-ttu-id="dca18-460">使用资源管理器和实时检测的更多方法</span><span class="sxs-lookup"><span data-stu-id="dca18-460">More ways to use Explorer and Real-time detections</span></span>

<span data-ttu-id="dca18-461">除了本文中概述的方案之外，资源管理器或实时检测功能中还 (更多报告) 。</span><span class="sxs-lookup"><span data-stu-id="dca18-461">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span> <span data-ttu-id="dca18-462">另请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="dca18-462">See the following articles:</span></span>

- [<span data-ttu-id="dca18-463">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="dca18-463">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="dca18-464">查看在 SharePoint Online、OneDrive 和 Microsoft Teams 中检测到的恶意文件</span><span class="sxs-lookup"><span data-stu-id="dca18-464">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="dca18-465">大致了解威胁资源管理器中的 (和实时检测) </span><span class="sxs-lookup"><span data-stu-id="dca18-465">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="dca18-466">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="dca18-466">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="dca18-467">Microsoft 威胁防护中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="dca18-467">Automated investigation and response in Microsoft Threat Protection</span></span>](../mtp/mtp-autoir.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="dca18-468">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="dca18-468">Required licenses and permissions</span></span>

<span data-ttu-id="dca18-469">必须具有 [Microsoft Defender for Office 365，](office-365-atp.md) 以使用资源管理器或实时检测。</span><span class="sxs-lookup"><span data-stu-id="dca18-469">You must have [Microsoft Defender for Office 365](office-365-atp.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="dca18-470">资源管理器包含在 Defender for Office 365 计划 2 中。</span><span class="sxs-lookup"><span data-stu-id="dca18-470">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="dca18-471">实时检测报告包含在 Defender for Office 365 计划 1 中。</span><span class="sxs-lookup"><span data-stu-id="dca18-471">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="dca18-472">计划为应受 Office 365 Defender 保护的所有用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="dca18-472">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="dca18-473">资源管理器和实时检测显示许可用户的检测数据。</span><span class="sxs-lookup"><span data-stu-id="dca18-473">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="dca18-474">若要查看和使用资源管理器或实时检测，您必须具有适当的权限，例如授予安全管理员或安全读者的权限。</span><span class="sxs-lookup"><span data-stu-id="dca18-474">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="dca18-475">对于安全&合规中心，您必须分配以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="dca18-475">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="dca18-476">组织管理</span><span class="sxs-lookup"><span data-stu-id="dca18-476">Organization Management</span></span>
  - <span data-ttu-id="dca18-477">安全 (可以在 Azure Active Directory 管理中心 <https://aad.portal.azure.com> () </span><span class="sxs-lookup"><span data-stu-id="dca18-477">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="dca18-478">安全读取者</span><span class="sxs-lookup"><span data-stu-id="dca18-478">Security Reader</span></span>

- <span data-ttu-id="dca18-479">对于 Exchange Online，必须在 Exchange 管理中心或 Exchange Online <https://admin.protection.outlook.com/ecp/> PowerShell () 分配以下角色 [之一](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)：</span><span class="sxs-lookup"><span data-stu-id="dca18-479">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="dca18-480">组织管理</span><span class="sxs-lookup"><span data-stu-id="dca18-480">Organization Management</span></span>
  - <span data-ttu-id="dca18-481">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="dca18-481">View-Only Organization Management</span></span>
  - <span data-ttu-id="dca18-482">仅查看收件人</span><span class="sxs-lookup"><span data-stu-id="dca18-482">View-Only Recipients</span></span>
  - <span data-ttu-id="dca18-483">合规性管理</span><span class="sxs-lookup"><span data-stu-id="dca18-483">Compliance Management</span></span>

<span data-ttu-id="dca18-484">若要详细了解角色和权限，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="dca18-484">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="dca18-485">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="dca18-485">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="dca18-486">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="dca18-486">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="dca18-487">威胁资源管理器和实时检测之间的差异</span><span class="sxs-lookup"><span data-stu-id="dca18-487">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="dca18-488">*实时检测报告在* Defender for Office 365 计划 1 中可用。</span><span class="sxs-lookup"><span data-stu-id="dca18-488">The *Real-time detections* report is available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="dca18-489">*威胁资源管理器* 在 Defender for Office 365 计划 2 中可用。</span><span class="sxs-lookup"><span data-stu-id="dca18-489">*Threat Explorer* is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="dca18-490">实时检测报告允许你实时查看检测。</span><span class="sxs-lookup"><span data-stu-id="dca18-490">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="dca18-491">威胁资源管理器也会这样做，但它还提供给定攻击的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="dca18-491">Threat Explorer does this as well, but it also provides additional details for a given attack.</span></span>
- <span data-ttu-id="dca18-492">" *所有电子邮件* "视图在威胁资源管理器中可用，但在实时检测报告中不可用。</span><span class="sxs-lookup"><span data-stu-id="dca18-492">An *All email* view is available in Threat Explorer but not in the Real-time detections report.</span></span>
- <span data-ttu-id="dca18-493">威胁资源管理器中包含更多筛选功能和可用操作。</span><span class="sxs-lookup"><span data-stu-id="dca18-493">More filtering capabilities and available actions are included in Threat Explorer.</span></span> <span data-ttu-id="dca18-494">有关详细信息，请参阅 [Microsoft Defender for Office 365 服务说明：跨 Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)计划的功能可用性。</span><span class="sxs-lookup"><span data-stu-id="dca18-494">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
