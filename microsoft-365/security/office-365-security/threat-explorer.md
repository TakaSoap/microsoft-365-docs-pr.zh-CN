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
- m365-initiative-defender-office365
description: 了解如何在安全合规中心中使用 Explorer 和实时检测， &amp; 以有效且高效地对威胁进行调查和响应。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab691e88c8450e4f1ab898fe6a9d75d6682370a5
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417374"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="1bf1c-103">威胁资源管理器和实时检测</span><span class="sxs-lookup"><span data-stu-id="1bf1c-103">Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1bf1c-104">如果您的组织具有 [office 365 高级威胁防护](office-365-atp.md) (OFFICE 365 ATP) ，并且您拥有 [必要的权限](#required-licenses-and-permissions)，则您可以使用 **资源管理器** 或 **实时检测** (以前的 *实时报告* — [请参阅最近更新](#new-features-in-threat-explorer-and-real-time-detections)！ ) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="1bf1c-105">在安全 & 合规性中心中，转到 " **威胁管理**"，然后选择 " **浏览器**" _或_" **实时检测**"。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

|<span data-ttu-id="1bf1c-106">在 ATP 计划2中，您将看到：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-106">With ATP Plan 2, you see:</span></span>|<span data-ttu-id="1bf1c-107">在 ATP 计划1中，您将看到：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-107">With ATP Plan 1, you see:</span></span>|
|---|---|
|![威胁资源管理器](../../media/threatmgmt-explorer.png)|![实时检测](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="1bf1c-110">通过资源管理器 (或) 的实时检测功能，您有一个功能强大的报告，使安全操作团队能够有效且高效地调查威胁并对其做出响应。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently.</span></span> <span data-ttu-id="1bf1c-111">该报告类似于以下图像：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-111">The report resembles the following image:</span></span>

![转到 "威胁管理 \> 资源管理器"](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="1bf1c-113">使用此报告，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-113">With this report, you can:</span></span>

- [<span data-ttu-id="1bf1c-114">查看 Microsoft 365 安全功能检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="1bf1c-114">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="1bf1c-115">查看有关仿冒 Url 的数据，然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="1bf1c-115">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- <span data-ttu-id="1bf1c-116">[从资源管理器中的视图启动自动调查和响应过程](#start-automated-investigation-and-response) (ATP 计划2仅) </span><span class="sxs-lookup"><span data-stu-id="1bf1c-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="1bf1c-117">... [调查恶意电子邮件，](#more-ways-to-use-explorer-or-real-time-detections)等等！</span><span class="sxs-lookup"><span data-stu-id="1bf1c-117">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="improvements-to-threat-hunting-experience-upcoming"></a><span data-ttu-id="1bf1c-118"> (即将到来的) 的威胁搜寻体验的改进</span><span class="sxs-lookup"><span data-stu-id="1bf1c-118">Improvements to Threat Hunting Experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="1bf1c-119">更新了电子邮件的威胁信息</span><span class="sxs-lookup"><span data-stu-id="1bf1c-119">Updated Threat Information for Emails</span></span>

<span data-ttu-id="1bf1c-120">我们重点介绍了平台和数据质量改进，以提高电子邮件记录的数据准确性和一致性。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-120">We have focused on platform and data quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="1bf1c-121">这些更新集包括将对电子邮件执行的预送达和送达后信息 (示例操作作为作为 ZAP 过程的一部分执行) 到单个记录中，同时增加了垃圾邮件结论、实体级威胁 (例如，哪些 URL 是恶意的) 和最新的传递位置。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-121">These set of updates includes consolidation of pre-delivery and post-delivery information (example action executed on an email as part of ZAP process) into a single record  along with added richness like Spam verdict, Entity level threats (e.g. which URL was malicious) and latest delivery locations.</span></span> 

<span data-ttu-id="1bf1c-122">在这些更新之后，您将看到每个邮件对应一个条目，而不考虑邮件上发生的不同送达事件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-122">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that have taken place on the message.</span></span> <span data-ttu-id="1bf1c-123">操作可以包括 ZAP、手动修正 (这意味着管理操作) 、动态传递等。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-123">Actions can include ZAP, Manual Remediation (which means admin action), Dynamic Delivery etc.</span></span> 

<span data-ttu-id="1bf1c-124">除了显示恶意软件和网络钓鱼威胁之外，您现在还可以查看与电子邮件相关联的垃圾邮件结论。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-124">In addition to showing malware and phish threats, you'll now be able to see spam verdict associated with an email.</span></span> <span data-ttu-id="1bf1c-125">在电子邮件中，你将能够查看与电子邮件相关的所有威胁以及相应的检测技术。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-125">Within the email, you will be able to see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="1bf1c-126">每封电子邮件可以有0个、1个或多个威胁。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-126">Each email can have 0, 1, or multiple threats.</span></span> <span data-ttu-id="1bf1c-127">您将在 "电子邮件" 浮出控件的 "详细信息" 部分看到当前威胁。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-127">You'll see the current Threats in the Details section of the Email flyout.</span></span> <span data-ttu-id="1bf1c-128">此外，对于多个威胁 (例如，同时包含恶意软件和网络钓鱼) 的电子邮件，检测技术字段将提供 Threat-Detection 的映射，这意味着哪些检测技术会导致威胁的识别。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-128">Additionally, for multiple threats (e.g., an email having both Malware and Phish), Detection tech field would give the Threat-Detection mapping, meaning which detection tech led to the identification of the Threat.</span></span>

<span data-ttu-id="1bf1c-129">已对一系列检测技术进行了更新，以包括新的检测方法以及垃圾邮件检测技术，并 aross 所有不同的电子邮件视图 (恶意软件、网络钓鱼诈骗、所有电子邮件) 中，您将拥有相同的一致的检测技术集来筛选结果。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-129">The set of detection technologies has been updated to include new detection methods, as well as spam detection technologies, and aross all the different email views (Malware, Phish, All Email), you'll have the same, consistent set of Detection technologies to filter the results.</span></span> 

<span data-ttu-id="1bf1c-130">**注意**：可能不一定要将 "可判定" 分析绑定到实体。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-130">**Note**: Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="1bf1c-131">例如，电子邮件可能会归类为网络钓鱼或垃圾邮件，但没有任何 Url 在其上标记任何网络钓鱼/垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-131">As an example, an email might be classified as Phish or Spam, but there are no URLs which have any Phish/Spam verdict stamped on them.</span></span> <span data-ttu-id="1bf1c-132">这是因为，在分配一个判定之前，我们的筛选器还会评估电子邮件的内容和其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-132">This is because our filters also evaluate content and other details for an email, before assigning a verdict.</span></span> 
 
#### <a name="threats-in-urls"></a><span data-ttu-id="1bf1c-133">Url 中的威胁</span><span class="sxs-lookup"><span data-stu-id="1bf1c-133">Threats in URLs</span></span>

<span data-ttu-id="1bf1c-134">在 "电子邮件飞出" > 详细信息 "选项卡中，您现在可以看到 url 的特定威胁 (URL 可以是恶意软件、网络钓鱼诈骗、垃圾邮件或无) </span><span class="sxs-lookup"><span data-stu-id="1bf1c-134">Within email flyout-> Details tab, you would now be able to see the specific threat for a URL (Threat for a URL can be Malware, Phish, Spam or None)</span></span>

![URL 威胁](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="1bf1c-136"> (即将开始的日程表视图更新) </span><span class="sxs-lookup"><span data-stu-id="1bf1c-136">Updated Timeline View (upcoming)</span></span>

![更新的日程表视图](../../media/Email_Timeline.png)

<span data-ttu-id="1bf1c-138">除了标识所有传递和传递后事件之外，"日程表" 视图还提供有关在该时间点为这些事件的子集确定的威胁的信息。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-138">In addition to identifying all delivery and post-delivery events, timeline view also gives information about the Threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="1bf1c-139">此外，它还提供了有关其他操作的详细信息 (例如，ZAP、手动修正) 以及该操作的结果。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-139">It also gives you more information about Additional Actions (e.g. ZAP, Manual Remediation) along with the Result of that action.</span></span> <span data-ttu-id="1bf1c-140">"日程表" 视图包含有关原始传递以及随后在电子邮件上执行的任何送达事件的信息。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-140">Timeline view contains information about the Original delivery and subsequently any post-delivery events performed on an email.</span></span>

-   <span data-ttu-id="1bf1c-141">来源：这可以是管理员/系统/用户，具体取决于事件的来源。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-141">Source: This can be Admin/System/user based on what was the source of the event.</span></span>
-   <span data-ttu-id="1bf1c-142">事件：其中包括原始传递、手动修正、ZAP、报送和动态传递等顶级事件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-142">Event: This includes top level events like Original Delivery, Manual Remediation, ZAP, Submissions, and Dynamic Delivery .</span></span>
-   <span data-ttu-id="1bf1c-143">操作：这涵盖作为 ZAP 或 Admin 操作的一部分执行的特定操作 (例如软删除) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-143">Action: This covers the specific action that was taken either as part of ZAP or Admin Action (e.g., Soft Delete).</span></span>
-   <span data-ttu-id="1bf1c-144">威胁：涵盖该时间点 (恶意软件、网络钓鱼诈骗、垃圾邮件) 的威胁。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-144">Threats: Covers the threats (Malware, Phish, Spam) identified at that point of time.</span></span>
-   <span data-ttu-id="1bf1c-145">Result/Details：涵盖有关操作结果的详细信息，即是否作为 ZAP/管理操作的一部分执行。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-145">Result/Details: Covers more information about the Result of the Action, whether it was performed as part of ZAP/Admin Action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="1bf1c-146">原始和最新送达位置</span><span class="sxs-lookup"><span data-stu-id="1bf1c-146">Original and Latest Delivery location</span></span>

<span data-ttu-id="1bf1c-147">目前，我们在电子邮件网格和电子邮件浮出控件中呈现了交付位置。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-147">Today, we surface delivery Location within email grid and email flyout.</span></span> <span data-ttu-id="1bf1c-148">今后，"送达位置" 字段将被重命名为原始送达位置。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-148">Going forward, the Delivery Location field will be renamed to Original Delivery Location.</span></span> <span data-ttu-id="1bf1c-149">此外，还引入了另一个名为 "最新传递位置" 的字段。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-149">Additionally, we're also introducing another field called Latest delivery location.</span></span> 

<span data-ttu-id="1bf1c-150">原始送达位置将提供有关最初传递电子邮件的位置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-150">The original delivery location would give more information about where an email was delivered initially.</span></span> <span data-ttu-id="1bf1c-151">最新的送达位置将包括在系统操作（如 " **移动到已删除邮件**"）的系统操作之后，电子邮件可能会进入到的位置。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-151">The latest delivery location would include location where an email may have landed after system actions like ZAP or admin actions like **Move to Deleted Items**.</span></span> <span data-ttu-id="1bf1c-152">最新送达位置旨在通知管理员邮件的最近已知位置投递或任何系统/管理员操作。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-152">Latest delivery location is intended to inform admins of the message's last known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="1bf1c-153">根据设计，它不包括任何与最终用户相关的电子邮件操作。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-153">By design, it doesn't include any end user related actions on the email.</span></span> <span data-ttu-id="1bf1c-154">例如：如果用户删除邮件或将邮件移动到存档/pst，则不会更新邮件 "送达" 位置。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-154">For example: if a user deletes a message or moves the message to archive/pst, the message "delivery" location will not be updated.</span></span> <span data-ttu-id="1bf1c-155">但是，如果系统操作更新了位置 (例如，通过将邮件移到隔离) ，则会看到最新的送达位置作为隔离。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-155">However, if a system action updated the location (e.g., ZAP resulting in an email moving to Quarantine), you would see the Latest delivery location as Quarantine.</span></span> 

![更新的送达位置](../../media/Updated_Delivery_Location.png)

<span data-ttu-id="1bf1c-157">**注意**：在少数情况下，送达位置和传递操作可能会将 "Unknown" 显示为值：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-157">**Note**: There are few cases where Delivery Location and Delivery Action may show 'Unknown' as the value:</span></span>

- <span data-ttu-id="1bf1c-158">您可能会看到送达位置为 "已传递"，并且传递位置为 "未知"。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-158">You might see Delivery location as Delivered, and Delivery Location as Unknown.</span></span> <span data-ttu-id="1bf1c-159">邮件传递过程中出现这种情况，但收件箱规则将邮件移动到默认文件夹 (草稿、存档等 ) 而不是 "收件箱" 或 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-159">This happens when the message was delivered, but an Inbox rule moved the message to a default folder (Draft, Archive, etc.) instead of the Inbox or Junk Email folders.</span></span> 

- <span data-ttu-id="1bf1c-160">如果管理员/系统操作 (（例如，ZAP、管理操作) ，但找不到该邮件），则无法识别最新的传递位置。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-160">Latest Delivery Location can be unknown if an admin/system action (e.g., ZAP, Admin Action) is attempted, but the message isn't found.</span></span> <span data-ttu-id="1bf1c-161">通常情况下，操作在用户移动或删除邮件之后发生。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-161">Typically, the action happens after the user has moved or deleted the Message.</span></span> <span data-ttu-id="1bf1c-162">在这种情况下，请验证 "日程表" 视图中的 "结果/详细信息" 列。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-162">In such cases, verify the Result/Details Column in timeline view.</span></span> <span data-ttu-id="1bf1c-163">查找邮件：用户移动或删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-163">Look for the message: Message moved or deleted by the user.</span></span>

![日程表的送达位置](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a><span data-ttu-id="1bf1c-165">其他操作</span><span class="sxs-lookup"><span data-stu-id="1bf1c-165">Additional Actions</span></span> 

<span data-ttu-id="1bf1c-166">其他操作包括已应用的操作在发送电子邮件时发布的操作，并且可以包括由 Admi 执行的 ZAP、手动修正 (操作; 例如，软删除) 、动态传递和重新处理 (追溯电子邮件被检测为正确的) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-166">Additional Actions consist of the actions that were applied post the delivery of the Email, and can include ZAP, Manual Remediation (action taken by an Admi;n e.g., Soft Delete), Dynamic Delivery, and Reprocessed (an email was retroactively detected as good).</span></span> 

> [!NOTE]
>
> - <span data-ttu-id="1bf1c-167">作为此更改的一部分，当前在传递操作筛选器中的已删除的 ZAP 值将离开。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-167">As part of this change, the Removed by ZAP value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="1bf1c-168">你可以通过其他操作搜索通过 ZAP 尝试的所有电子邮件的方法。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-168">You'll have a way to search for all email with the ZAP attempt through the Additional Actions.</span></span>
>
> <span data-ttu-id="1bf1c-169">-将提供检测技术和其他操作的新字段和值，尤其是) 的 ZAP 方案中 (。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-169">-There will be new fields and values for Detection technologies and Additional actions (especially for ZAP scenarios).</span></span> <span data-ttu-id="1bf1c-170">评估现有的已保存的查询和跟踪的查询，以确保它们能够处理新值。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-170">Evaluate your existing Saved Queries and Tracked queries to make sure they work with the new values.</span></span> 

![Additional_Actions](../../media/Additional_Actions.png)

### <a name="system-overrides"></a><span data-ttu-id="1bf1c-172">系统覆盖</span><span class="sxs-lookup"><span data-stu-id="1bf1c-172">System overrides</span></span> 

<span data-ttu-id="1bf1c-173">系统覆盖是一种通过覆盖由系统 (提供的传递位置（基于由我们的筛选堆栈) 标识的威胁和其他检测）来对邮件的预期送达位置进行例外的方法。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-173">System overrides are a method of making exceptions to the intended delivery location of a message by overriding the delivery location provided by system (based on the threats and other detections identified by our filtering stack).</span></span> <span data-ttu-id="1bf1c-174">可以通过租户或用户策略设置系统替代，以根据策略建议传递邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-174">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="1bf1c-175">重写可用于标识任何由于配置缺口而无意中传递的恶意邮件 (例如，由) 用户设置的一种非常广泛的安全发件人策略。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-175">Overrides are useful in identifying any unintentional delivery of malicious messages due to configurations gaps (for example, a very broad Safe Sender policy set by a user).</span></span> <span data-ttu-id="1bf1c-176">这些替代值可以是：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-176">These override values can be:</span></span>

- <span data-ttu-id="1bf1c-177">用户策略允许：这是用户通过在邮箱级别创建策略来允许域或发件人。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-177">Allowed by user policy: This is when a user allows domains or senders by creating policies at the mailbox level.</span></span>
- <span data-ttu-id="1bf1c-178">被用户策略阻止：当用户通过在邮箱级别创建策略来阻止域或发件人时，将会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-178">Blocked by user policy: This is when a user blocks domains or senders by creating policies at the mailbox level.</span></span>
- <span data-ttu-id="1bf1c-179">组织策略允许：这是组织的安全团队设置策略或 Exchange 邮件流规则时 (也称为传输规则) 为其组织中的用户允许发件人和域。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-179">Allowed by org policy: This is when the organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="1bf1c-180">这可用于一组用户或整个组织。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-180">This can be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="1bf1c-181">被组织策略阻止：这是组织的安全团队设置策略或邮件流规则，以阻止其组织中用户的发件人、域、邮件语言或源 Ip。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-181">Blocked by org policy: This is when the organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="1bf1c-182">这也可用于一组用户或整个组织。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-182">This can also be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="1bf1c-183">组织策略阻止的文件扩展名：这是组织的安全团队通过反恶意软件策略设置阻止的文件类型扩展名。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-183">File extension blocked by org policy: This is when a file type extension is blocked by the security teams of an organization through the anti-malware policy settings.</span></span> <span data-ttu-id="1bf1c-184">这些值现在将显示在电子邮件详细信息中，以帮助进行调查。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-184">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="1bf1c-185">Secops 团队还可以使用富筛选功能筛选阻止的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-185">Secops teams can also filter on blocked file extensions using the rich filtering capability.</span></span>

![System_Overrides](../../media/System_Overrides.png)

![System_Overrides_Grid](../../media/System_Overrides_Grid.png)

### <a name="improvements-around-url-and-clicks-experience"></a><span data-ttu-id="1bf1c-188">有关 URL 和点击体验的改进</span><span class="sxs-lookup"><span data-stu-id="1bf1c-188">Improvements around URL and Clicks Experience</span></span>

<span data-ttu-id="1bf1c-189">Focussed 对 URL 和 URL 的改进的集合单击数据包括：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-189">The set of improvements focussed towards URL and URL clicks data include:</span></span>

-   <span data-ttu-id="1bf1c-190">显示已完全单击的 URL (包括 URL 浮出控件的单击部分中的 URL) 的一部分查询参数。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-190">Showing full Clicked URL (including any query Parameters which are part of URL) within the Clicks Section in URL Flyout.</span></span> <span data-ttu-id="1bf1c-191">目前，我们在标题栏中显示 URL 域和路径。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-191">Currently we show the URL domain and path in title bar.</span></span> <span data-ttu-id="1bf1c-192">我们正在扩展该信息以显示完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-192">We're extending that information to show the full URL.</span></span>
-   <span data-ttu-id="1bf1c-193">通过 URL 筛选器 (URL vs URL 域与 URL 域和路径) 的修正：我们已在搜索包含 URL/单击判定的邮件时进行了更新。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-193">Fixes across URL filters (URL vs URL domain vs URL Domain and path): We've made updates around searching for messages that contain a URL/Click verdict.</span></span> <span data-ttu-id="1bf1c-194">作为此过程的一部分，我们启用了对协议不可知搜索的支持 (意义上，您可以直接搜索不带 http) 的 URL。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-194">As part of that, we've enabled support for protocol agnostic searches (meaning, you can directly search for a URL without http).</span></span> <span data-ttu-id="1bf1c-195">默认情况下，除非显式指定，否则 URL 搜索将映射到 http。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-195">By default, the URL search maps to http, unless explicitly specified.</span></span> <span data-ttu-id="1bf1c-196">例如：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-196">For example:</span></span>

  <span data-ttu-id="1bf1c-197">a.</span><span class="sxs-lookup"><span data-stu-id="1bf1c-197">a.</span></span>    <span data-ttu-id="1bf1c-198">`http://`在 "url"、"Url 域" 和 "Url 域和路径" 筛选器字段中使用和不带前缀进行搜索。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-198">Search with and without the `http://` prefix in "URL", "URL Domain", and "URL Domain and Path" filter fields.</span></span> <span data-ttu-id="1bf1c-199">此行为是一致的，并应显示相同的结果。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-199">This behavior is consistent, and should show the same result.</span></span>
  <span data-ttu-id="1bf1c-200">b.</span><span class="sxs-lookup"><span data-stu-id="1bf1c-200">b.</span></span>    <span data-ttu-id="1bf1c-201">`https://`在 "URL" 中搜索前缀。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-201">Search for the `https://` prefix in "URL".</span></span> <span data-ttu-id="1bf1c-202">如果不存在，则 `http://` 假定前缀。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-202">When not present, the `http://` prefix is assumed.</span></span>
  <span data-ttu-id="1bf1c-203">c.</span><span class="sxs-lookup"><span data-stu-id="1bf1c-203">c.</span></span>     <span data-ttu-id="1bf1c-204">`/` "URL 路径"、"URL 域"、"URL 域和路径" 字段的开头和结尾将被忽略。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-204">`/` in beginning and end of the "URL path", "URL Domain", "URL domain and path" fields is ignored.</span></span> <span data-ttu-id="1bf1c-205">`/` 在 "URL" 字段的末尾忽略。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-205">`/` at the end of the "URL" field is ignored.</span></span> 

### <a name="phish-confidence-level"></a><span data-ttu-id="1bf1c-206">网络钓鱼信任级别</span><span class="sxs-lookup"><span data-stu-id="1bf1c-206">Phish Confidence Level</span></span>

<span data-ttu-id="1bf1c-207">网络钓鱼可信度有助于确定置信度，其中电子邮件被分类为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-207">Phish confidence level helps to identify the degree of confidence, with which an email was categorized as Phish.</span></span> <span data-ttu-id="1bf1c-208">这两个可能的值为 "高" 和 "普通"。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-208">The two possible values are High and Normal.</span></span> <span data-ttu-id="1bf1c-209">在初始阶段，此筛选器仅适用于威胁资源管理器的 "网络钓鱼视图"。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-209">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

![Phish_Confidence_Level](../../media/Phish_Confidence_Level.png)

### <a name="zap-url-signal"></a><span data-ttu-id="1bf1c-211">ZAP URL 信号</span><span class="sxs-lookup"><span data-stu-id="1bf1c-211">ZAP URL Signal</span></span> 

<span data-ttu-id="1bf1c-212">通常用于将电子邮件标识为网络钓鱼并在送达后删除的 ZAP 网络钓鱼警报方案。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-212">Typically used for ZAP Phish Alert scenarios where an was email identified as Phish and removed after delivery.</span></span> <span data-ttu-id="1bf1c-213">此项用于在资源管理器中将通知与相应的结果连接。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-213">This is used to connect the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="1bf1c-214">它是警报的 IOCs 之一。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-214">It is one of the IOCs for the alert.</span></span> 

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="1bf1c-215">体验资源管理器和 Real-Time 检测的改进</span><span class="sxs-lookup"><span data-stu-id="1bf1c-215">Experience Improvements to Threat Explorer and Real-Time Detections</span></span>

<span data-ttu-id="1bf1c-216">在改进搜寻过程的过程中，我们已对威胁资源管理器和 Real-Time 检测进行了一些更新。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-216">As part of improving the hunting process, we have made a few updates to Threat Explorer and Real-Time Detections.</span></span> <span data-ttu-id="1bf1c-217">这些是 "体验" 改进，重点是让求职体验更一致。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-217">These are ‘experience’ improvements, with the focus on making the hunting experience more consistent.</span></span> <span data-ttu-id="1bf1c-218">下面概述了这些更改：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-218">These changes are outlined below:</span></span>

- [<span data-ttu-id="1bf1c-219">时区改进</span><span class="sxs-lookup"><span data-stu-id="1bf1c-219">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="1bf1c-220">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="1bf1c-220">Update in the Refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="1bf1c-221">要添加到筛选器的图表深入分析</span><span class="sxs-lookup"><span data-stu-id="1bf1c-221">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="1bf1c-222">在产品信息更新中</span><span class="sxs-lookup"><span data-stu-id="1bf1c-222">In product information updates</span></span>](#in-product-information-updates)

### <a name="timezone-improvements"></a><span data-ttu-id="1bf1c-223">时区改进</span><span class="sxs-lookup"><span data-stu-id="1bf1c-223">Timezone improvements</span></span>

<span data-ttu-id="1bf1c-224">你将看到门户中的电子邮件记录的时区以及导出的数据的时区。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-224">You will see the timezone for the email records within the Portal, as well as for Exported data.</span></span> <span data-ttu-id="1bf1c-225">在电子邮件网格、详细信息浮出控件、电子邮件日程表和类似的电子邮件等体验中，时区将可见，从而使用户可以清楚地了解结果集的时区。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-225">The timezone will be visible across experiences like Email Grid, Details Flyout, Email Timeline, and Similar Emails, so that the timezone for the result set is clear to the user.</span></span>

![在资源管理器中查看时区](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="1bf1c-227">刷新过程中的更新</span><span class="sxs-lookup"><span data-stu-id="1bf1c-227">Update in the Refresh process</span></span>

<span data-ttu-id="1bf1c-228">我们已经听说过与自动刷新 (混淆的反馈，例如日期，一旦您更改日期，页面将刷新) 并手动刷新 (其他筛选器) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-228">We have heard feedback around confusion with automatic refresh (e.g. for date, as soon as you change the date, the page would refresh) and manual refresh (for other filters).</span></span> <span data-ttu-id="1bf1c-229">同样，删除筛选器会导致自动刷新，这会导致在修改查询时更改不同的筛选器会导致不一致的搜索体验的情况。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-229">Similarly, removing filters leads to automatic refresh, this causes situations where changing the different filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="1bf1c-230">若要解决此情况，我们将迁移到手动筛选机制。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-230">To solve this, we are moving to a manual filtering mechanism.</span></span>

<span data-ttu-id="1bf1c-231">从经验的角度来看，用户可以应用和删除筛选器集 (的不同范围的筛选器，并在日期) ，然后按 "刷新" 按钮，在完成定义查询的情况下筛选结果。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-231">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set, and date), and press the refresh button to filter the results once they are done with defining the query.</span></span> <span data-ttu-id="1bf1c-232">"刷新" 按钮也已更新，可在屏幕上清楚地调用它。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-232">The refresh button has also been updated to call it out clearly on the screen.</span></span> <span data-ttu-id="1bf1c-233">我们还提供了有关此更改的更新工具提示和产品内文档。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-233">We have also updated tooltips and in-product documentation around this change.</span></span>

![单击 "刷新" 以筛选结果](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="1bf1c-235">要添加到筛选器的图表深入分析</span><span class="sxs-lookup"><span data-stu-id="1bf1c-235">Chart drilldown to add to filters</span></span>

<span data-ttu-id="1bf1c-236">现在，您可以单击 "图表图例" 值，将该值作为筛选器添加。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-236">You will now be able to click on the chart legend values to add that value as a filter.</span></span> <span data-ttu-id="1bf1c-237">请注意，您仍必须单击 "刷新" 按钮，才能将结果作为上述更改的一部分进行筛选。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-237">Note that you will still have to click on the refresh button to filter the results as part of the change described above.</span></span>

![通过要筛选的图表深入分析](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a><span data-ttu-id="1bf1c-239">在产品信息更新中</span><span class="sxs-lookup"><span data-stu-id="1bf1c-239">In product information updates</span></span>

<span data-ttu-id="1bf1c-240">您还应查看产品中的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-240">You should also see additional details within the product.</span></span> <span data-ttu-id="1bf1c-241">例如，网格中的搜索结果总数) ，以及有关标签、错误消息和工具提示的改进，以提供有关筛选器、搜索体验和结果集的详细信息，请参阅下图所示的 (。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-241">For example, the total number of search results within grid (see below), as well as improvements around labels, error messages and tooltips, to give more information around filters, search experience, and result set.</span></span>

![查看产品信息](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="1bf1c-243">威胁资源管理器中的扩展功能</span><span class="sxs-lookup"><span data-stu-id="1bf1c-243">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="1bf1c-244">主要目标用户</span><span class="sxs-lookup"><span data-stu-id="1bf1c-244">Top targeted users</span></span>

<span data-ttu-id="1bf1c-245">今天，我们在恶意软件的主要部分中公开主要目标用户的列表， (主要恶意软件系列中的电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-245">Today we expose the list of the top targeted users in the Malware View for Emails (within the Top Malware Families section).</span></span> <span data-ttu-id="1bf1c-246">我们将在网络钓鱼和所有电子邮件视图中扩展此视图，在该视图中，您将能够查看前五个目标用户以及每个用户对相应 (视图的尝试次数。例如，对于 "网络钓鱼" 视图，您将能够查看) 的网络钓鱼尝试次数。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-246">We will be extending this view within Phish and All Email views as well, where you will be able to see the top five targeted users along with the number of attempts for each user for the corresponding view (for example, for Phish view you will be able to see the number of Phish attempts).</span></span>
<span data-ttu-id="1bf1c-247">您还可以将目标用户列表导出为3000，并将每个电子邮件视图的脱机分析尝试次数导出到最大值为。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-247">You will also be able to export the list of targeted users up to a limit of 3000 along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="1bf1c-248">此外，选择 "否"。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-248">In addition to that, selecting No.</span></span> <span data-ttu-id="1bf1c-249"> (例如，下面的13次) 将在威胁 Explorer 中打开筛选视图，以便您可以在电子邮件和威胁中查看该用户的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-249">of attempts (for example, 13 attempts below) would open a filtered view in Threat Explorer, so that you can look at more details across emails and threats for that user.</span></span>

![主要目标用户](../../media/Top_Targeted_Users.png)


### <a name="exchange-transport-rules"></a><span data-ttu-id="1bf1c-251">Exchange 传输规则</span><span class="sxs-lookup"><span data-stu-id="1bf1c-251">Exchange transport rules</span></span>
<span data-ttu-id="1bf1c-252">作为数据扩充的一部分，您还应该能够查看应用于邮件的所有不同传输规则。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-252">As part of data enrichment, you should also be able to see all the different transport rules which were applied to a message.</span></span> <span data-ttu-id="1bf1c-253">此信息将显示在电子邮件网格视图中 (查看此内容，请在网格中选择 "列选项"，并在 "网格中的列选项" 中添加 Exchange 传输规则) 以及电子邮件中的 "详细信息" 浮出控件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-253">This information will be present within the Email grid view (to view this, select Column options in the grid and add Exchange Transport Rule from the Column options in the grid) as well as Details flyout in the email.</span></span>
<span data-ttu-id="1bf1c-254">你将能够同时查看 GUID 以及应用于邮件的传输规则的名称。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-254">You would be able to see both the GUID as well as the name of the transport rules which were applied to the message.</span></span> <span data-ttu-id="1bf1c-255">此外，您还可以使用传输规则的名称搜索邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-255">Additionally, you would be able to search for the messages using the name of the transport rule.</span></span> <span data-ttu-id="1bf1c-256">这是一个 "包含" 搜索，这意味着您也可以使用部分搜索进行搜索。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-256">This would be a ‘Contains’ search which means you will be able to search using partial searches as well.</span></span>

#### <a name="important-note"></a><span data-ttu-id="1bf1c-257">重要说明：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-257">Important Note:</span></span>
<span data-ttu-id="1bf1c-258">ETR 搜索和名称可用性取决于已分配给你的特定角色。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-258">ETR search and name availability would depend on the specific role that has been assigned to you.</span></span> <span data-ttu-id="1bf1c-259">您需要具有以下角色/权限之一才能查看 ETR 名称和搜索。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-259">You will need to have one of the following roles/permissions in order to view the ETR names and search.</span></span>  <span data-ttu-id="1bf1c-260">如果没有为您分配以下任何角色，您将无法看到传输规则的名称，并使用 ETR 名称搜索邮件的名称。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-260">If you do not have any of the following roles assigned to you, you will not be able to see the names of the transport rules, and search for the messages using the ETR names.</span></span> <span data-ttu-id="1bf1c-261">不过，你将能够在电子邮件详细信息中看到 ETR 标签和 GUID 信息。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-261">However, you will be able to see the ETR label and GUID information within the Email Details.</span></span> <span data-ttu-id="1bf1c-262">有关在电子邮件网格、电子邮件 flyouts、筛选器和导出中查看记录的其他体验不受影响。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-262">Your other experiences around viewing records in Email Grids, Email flyouts, Filters, and Export are not impacted.</span></span>

- <span data-ttu-id="1bf1c-263">仅限 EXO-数据丢失防护：全部</span><span class="sxs-lookup"><span data-stu-id="1bf1c-263">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="1bf1c-264">仅 EXO-O365SupportViewConfig： All</span><span class="sxs-lookup"><span data-stu-id="1bf1c-264">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="1bf1c-265">AAD 或 EXO-安全管理员： All</span><span class="sxs-lookup"><span data-stu-id="1bf1c-265">AAD or EXO - Security Admin: All</span></span>
- <span data-ttu-id="1bf1c-266">AAD 或 EXO-安全读者： All</span><span class="sxs-lookup"><span data-stu-id="1bf1c-266">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="1bf1c-267">仅限 EXO-传输规则： All</span><span class="sxs-lookup"><span data-stu-id="1bf1c-267">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="1bf1c-268">仅限 EXO-View-Only 配置： All</span><span class="sxs-lookup"><span data-stu-id="1bf1c-268">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="1bf1c-269">在电子邮件网格、详细信息浮出控件和导出的 CSV 中，Etr 显示如下所示的名称/GUID。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-269">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>

![Exchange 传输规则](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a><span data-ttu-id="1bf1c-271">入站连接器</span><span class="sxs-lookup"><span data-stu-id="1bf1c-271">Inbound connectors</span></span>

<span data-ttu-id="1bf1c-272">连接器是一组说明，可用于自定义电子邮件流动到 Microsoft 365 或 Office 365 组织的方式，并能够应用任何安全限制或控件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-272">Connectors are a collection of instructions that customize the way your email flows to and from your Microsoft 365 or Office 365 organization, with the ability to apply any security restriction or controls.</span></span> <span data-ttu-id="1bf1c-273">在威胁资源管理器中，您现在可以查看与电子邮件相关的连接器，也可以使用连接器名称搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-273">Within Threat Explorer, you will now have the ability to view the connectors which are related to an email as well as search for emails using the connector names.</span></span>
<span data-ttu-id="1bf1c-274">对连接器的搜索是 ' 包含 ' 性质的，这意味着分部关键字搜索也应正常工作。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-274">The search for connectors is ‘Contains’ in nature which means partial keyword searches should work as well.</span></span>
<span data-ttu-id="1bf1c-275">在主网格视图中，"详细信息" 浮出控件和导出的 CSV，连接器以如下所示的名称/GUID 格式显示：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-275">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown below:</span></span>

![连接器详细信息](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="1bf1c-277">威胁资源管理器中的新功能和实时检测</span><span class="sxs-lookup"><span data-stu-id="1bf1c-277">New features in Threat Explorer and real-time detections</span></span>

<span data-ttu-id="1bf1c-278">威胁资源管理器和实时检测添加了三个新功能：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-278">Three new features added into Threat Explorer and real-time detections:</span></span>

- [<span data-ttu-id="1bf1c-279">预览电子邮件标头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="1bf1c-279">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="1bf1c-280">电子邮件日程表</span><span class="sxs-lookup"><span data-stu-id="1bf1c-280">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="1bf1c-281">导出 URL 单击 "数据"</span><span class="sxs-lookup"><span data-stu-id="1bf1c-281">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="1bf1c-282">下面概述了这些新功能。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-282">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="1bf1c-283">预览电子邮件标头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="1bf1c-283">Preview email header and download email body</span></span>

<span data-ttu-id="1bf1c-284">在威胁资源管理器中，预览电子邮件标头和下载电子邮件正文的功能是可用的新功能。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-284">The ability to preview an email header and download the email body are new features available in Threat Explorer.</span></span> <span data-ttu-id="1bf1c-285">管理员将能够分析下载的邮件头/电子邮件是否有威胁。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-285">Admins will be able to analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="1bf1c-286">由于下载电子邮件可能会降低信息的暴露风险，因此此过程由基于角色的访问控制 (RBAC) 控制。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-286">Because downloading email messages can risk the exposure of information, this process is controlled by roles-based access control (RBAC).</span></span> <span data-ttu-id="1bf1c-287">必须向另一个角色 (组中添加一个新的角色、 *预览*，如安全操作或安全管理员) ，以授予在所有电子邮件视图中下载邮件和预览邮件头的能力。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-287">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="1bf1c-288">但是，资源管理器 (和实时检测) 也会添加新的新字段，旨在为您提供有关电子邮件土地的更完整的信息。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-288">But Explorer (and real-time detections) also adds fresh new fields designed to give you a more complete picture of where your email messages land.</span></span> <span data-ttu-id="1bf1c-289">此更改的目标部分是使搜索更易于进行安全操作人员，但最终结果是了解问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-289">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="1bf1c-290">这是如何完成的？</span><span class="sxs-lookup"><span data-stu-id="1bf1c-290">How is this done?</span></span> <span data-ttu-id="1bf1c-291">传递状态现已分为两列：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-291">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="1bf1c-292">**传递操作** -此电子邮件的状态是什么？</span><span class="sxs-lookup"><span data-stu-id="1bf1c-292">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="1bf1c-293">**送达位置** -此电子邮件的路由结果</span><span class="sxs-lookup"><span data-stu-id="1bf1c-293">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="1bf1c-294">传递操作是由于现有策略或检测而导致对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-294">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="1bf1c-295">以下是电子邮件可能执行的操作：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-295">Here are the possible actions an email can take:</span></span>

|<span data-ttu-id="1bf1c-296">附带</span><span class="sxs-lookup"><span data-stu-id="1bf1c-296">Delivered</span></span>|<span data-ttu-id="1bf1c-297">Junked</span><span class="sxs-lookup"><span data-stu-id="1bf1c-297">Junked</span></span>|<span data-ttu-id="1bf1c-298">Blocked</span><span class="sxs-lookup"><span data-stu-id="1bf1c-298">Blocked</span></span>|<span data-ttu-id="1bf1c-299">代替</span><span class="sxs-lookup"><span data-stu-id="1bf1c-299">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="1bf1c-300">电子邮件已传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-300">Email was delivered to Inbox or folder of a user and the user can directly access it.</span></span>|<span data-ttu-id="1bf1c-301">电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹，并且用户有权访问这些文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-301">Email was sent to either user’s Junk folder or Deleted folder, and the user has access to emails in those folders.</span></span>|<span data-ttu-id="1bf1c-302">隔离的、失败的或已丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-302">Any emails that are quarantined, that  failed, or were dropped.</span></span> <span data-ttu-id="1bf1c-303">用户完全无法访问它！</span><span class="sxs-lookup"><span data-stu-id="1bf1c-303">This is completely inaccessible by the user!</span></span>|<span data-ttu-id="1bf1c-304">所有恶意附件都被替换为 .txt 文件的电子邮件，以表明附件是恶意的。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-304">Any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>|

|<span data-ttu-id="1bf1c-305">附带</span><span class="sxs-lookup"><span data-stu-id="1bf1c-305">Delivered</span></span>|<span data-ttu-id="1bf1c-306">Junked</span><span class="sxs-lookup"><span data-stu-id="1bf1c-306">Junked</span></span>|<span data-ttu-id="1bf1c-307">Blocked</span><span class="sxs-lookup"><span data-stu-id="1bf1c-307">Blocked</span></span>|<span data-ttu-id="1bf1c-308">代替</span><span class="sxs-lookup"><span data-stu-id="1bf1c-308">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="1bf1c-309">电子邮件已传递到用户的收件箱或其他文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-309">Email was delivered to the user's inbox or another folder, and the user can directly access it.</span></span>|<span data-ttu-id="1bf1c-310">电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹，并且用户有权访问这些文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-310">Email was sent to either user's Junk folder or Deleted folder, and the user has access to email messages in those folders.</span></span>|<span data-ttu-id="1bf1c-311">隔离的、失败的或已删除的任何电子邮件、以及用户无法访问的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-311">Any email messages that are quarantined, that failed, or were dropped, and are not accessible by the user.</span></span>|<span data-ttu-id="1bf1c-312">任何电子邮件，其中恶意附件被替换为 .txt 文件，以表明这些附件是恶意的。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-312">Any email messages where malicious attachments were replaced by .txt files that state the attachments were malicious.</span></span>|
|

<span data-ttu-id="1bf1c-313">用户可以看到的内容及其不能执行的操作：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-313">And here is what the user can see, and what they can't:</span></span>

|<span data-ttu-id="1bf1c-314">最终用户可以访问</span><span class="sxs-lookup"><span data-stu-id="1bf1c-314">Accessible to end users</span></span>|<span data-ttu-id="1bf1c-315">最终用户无法访问</span><span class="sxs-lookup"><span data-stu-id="1bf1c-315">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="1bf1c-316">附带</span><span class="sxs-lookup"><span data-stu-id="1bf1c-316">Delivered</span></span>|<span data-ttu-id="1bf1c-317">Blocked</span><span class="sxs-lookup"><span data-stu-id="1bf1c-317">Blocked</span></span>|
|<span data-ttu-id="1bf1c-318">Junked</span><span class="sxs-lookup"><span data-stu-id="1bf1c-318">Junked</span></span>|<span data-ttu-id="1bf1c-319">代替</span><span class="sxs-lookup"><span data-stu-id="1bf1c-319">Replaced</span></span>|

<span data-ttu-id="1bf1c-320">"送达位置" 显示运行送达后的策略和检测结果。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-320">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="1bf1c-321">它已链接到传递操作。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-321">It's linked to a Delivery Action.</span></span> <span data-ttu-id="1bf1c-322">添加此字段是为了深入了解在发现问题邮件时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-322">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="1bf1c-323">以下是送达位置的可能值：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-323">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="1bf1c-324">**收件箱或文件夹**：电子邮件位于收件箱中或文件夹 (根据您的电子邮件规则) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-324">**Inbox or folder**: The email is in inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="1bf1c-325">**本地或 external**：邮箱在云上不存在，但在本地。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-325">**On-prem or external**: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="1bf1c-326">**垃圾邮件文件夹**：电子邮件位于用户的 "垃圾邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-326">**Junk folder**: The email is in the Junk folder of a user.</span></span>
- <span data-ttu-id="1bf1c-327">"**已删除**邮件" 文件夹：用户的 "已删除邮件" 文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-327">**Deleted items folder**: The email in the Deleted items folder of a user.</span></span>
- <span data-ttu-id="1bf1c-328">**隔离**：隔离中的电子邮件，并且不在用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-328">**Quarantine**: The email in quarantine, and is not in a user's mailbox.</span></span>
- <span data-ttu-id="1bf1c-329">**失败**：电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-329">**Failed**: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="1bf1c-330">已**删除**：电子邮件在邮件流中的某处丢失。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-330">**Dropped**: The email gets lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="1bf1c-331">电子邮件日程表</span><span class="sxs-lookup"><span data-stu-id="1bf1c-331">Email timeline</span></span>

<span data-ttu-id="1bf1c-332">**电子邮件日程表**是另一个新的浏览器功能，旨在提高管理员的求职体验。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-332">The **Email Timeline** is another new Explorer feature aimed at making the hunting experience better for admins.</span></span> <span data-ttu-id="1bf1c-333">它会在随机时减少，因为检查不同位置以尝试了解事件的时间较少。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-333">It cuts down on randomization because there is less time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="1bf1c-334">当电子邮件上的多个事件发生时，或在同一时间结束时，这些事件将显示在 "日程表" 视图中。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-334">When multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="1bf1c-335">事实上，在传递给邮件的某些事件将在 "特殊操作" 列中捕获。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-335">In fact, some events that happen post-delivery to your mail will be captured in the 'Special action' column.</span></span> <span data-ttu-id="1bf1c-336">将该邮件的时间线中的信息与邮件投递后执行的特殊操作组合在一起，管理员可以了解其策略的工作方式，即最后路由邮件的位置，在某些情况下，最终评估是什么。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-336">Combining the information from the timeline of that mail with the special action taken on the mail post-delivery will give admins insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="1bf1c-337">有关调查恶意电子邮件的详细讨论，请参阅 [调查和修正 Office 365 中提供的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-337">For more discussion about investigating malicious email messages, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="1bf1c-338">导出 URL 单击 "数据"</span><span class="sxs-lookup"><span data-stu-id="1bf1c-338">Export URL click data</span></span>

<span data-ttu-id="1bf1c-339">此外，您现在可以将 URL 单击的报告导出到 Microsoft Excel 中，以查看其网络消息 ID 和单击结论，从而使了解您的 URL 单击流量更容易的任务。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-339">Also, you will now be able to export reports for URL clicks to Microsoft Excel in order to view both their Network Message ID, and their Click Verdict, making the task of understanding where your URL click traffic originated easier.</span></span> <span data-ttu-id="1bf1c-340">下面介绍了它的工作原理。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-340">Here's how it works.</span></span> <span data-ttu-id="1bf1c-341">从 "Office 365 快速启动" 上的 "威胁管理" 开始，依次单击 "通过此链"：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-341">Starting in Threat Management on the Office 365 quick-launch, click through this chain:</span></span>

<span data-ttu-id="1bf1c-342">**浏览器** \>**查看网络钓鱼** \>**单击** \>**顶部 url 或 URL 顶部单击** \>**单击任意记录以打开 "URL 飞出**"</span><span class="sxs-lookup"><span data-stu-id="1bf1c-342">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs or URL Top Clicks** \> **Click on any record to open URL flyout**</span></span>

<span data-ttu-id="1bf1c-343">当您单击列表中的某个 URL 时，将会在弹出面板上看到一个新的 "导出" 按钮。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-343">When you click on a URL in the list, you'll see a new Export button on the fly-out panel.</span></span> <span data-ttu-id="1bf1c-344">使用此按钮可以将数据移动到 Excel 电子表格，以便更轻松地进行报告。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-344">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="1bf1c-345">您可以在实时检测报告中获取相同的位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-345">You can get to the same location in the real-time detections report as follows:</span></span>

<span data-ttu-id="1bf1c-346">**浏览器** \>**实时检测** \>**查看网络钓鱼** \>**Url** \>**顶部的 url 或顶部的单击** \>**单击任意记录以打开 "URL 飞出** \> "**导航到 "单击" 选项卡。**</span><span class="sxs-lookup"><span data-stu-id="1bf1c-346">**Explorer** \> **Real-time Detections** \> **View Phish** \> **URLs** \> **Top URLs or Top Clicks** \> **Click on any record to open URL flyout** \> **Navigate to the Clicks Tab.**</span></span>

> [!TIP]
> <span data-ttu-id="1bf1c-347">当您通过网络邮件 ID 搜索浏览器或关联的第三方工具时，网络邮件 ID 会将单击映射回特定邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-347">Network Message ID maps the click back to specific mails when you search through Explorer or associated 3rd party tools via Network Message ID.</span></span> <span data-ttu-id="1bf1c-348">在网络邮件 ID 中搜索将为管理员提供与单击结果关联的特定电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-348">Searching through the Network Message ID will give admins the specific email associated with a click result.</span></span> <span data-ttu-id="1bf1c-349">在有导出功能的情况下，网络邮件 ID 的关联标识将使分析速度更快、更强大。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-349">On export having, the correlating identification of Network Message ID makes for quicker and more powerful analysis.</span></span>

![在资源管理器中单击选项卡](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="1bf1c-351">查看电子邮件中的技术检测到恶意软件</span><span class="sxs-lookup"><span data-stu-id="1bf1c-351">See malware detected in email by technology</span></span>

<span data-ttu-id="1bf1c-352">假设您想要查看 Microsoft 365 技术在电子邮件中检测到的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-352">Suppose you want to see malware detected in email, by Microsoft 365 technology.</span></span> <span data-ttu-id="1bf1c-353">若要执行此操作，请使用资源管理器 (的 [电子邮件 > 恶意软件](threat-explorer-views.md#email--malware) 视图或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-353">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="1bf1c-354">在 "安全性 & 合规性中心 ([https://protection.office.com](https://protection.office.com) ") 中，选择 "**威胁管理**  >  **资源管理器** (" 或 "**实时检测**") 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-354">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="1bf1c-355"> (本示例使用 Explorer。 ) </span><span class="sxs-lookup"><span data-stu-id="1bf1c-355">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="1bf1c-356">在 "**视图**" 菜单中，选择 "**电子邮件**  >  **恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-356">In the **View** menu, choose **Email** > **Malware**.</span></span>

   ![浏览器的视图菜单](../../media/ExplorerViewEmailMalwareMenu.png)

3. <span data-ttu-id="1bf1c-358">单击 "**发件人**"，然后选择 "**基本**  >  **检测技术**"。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-358">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span>

   <span data-ttu-id="1bf1c-359">您的检测技术现在可用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-359">Your detection technologies are now available as filters for the report.</span></span>

   ![恶意软件检测技术](../../media/ExplorerEmailMalwareDetectionTech.png)

4. <span data-ttu-id="1bf1c-361">选择一个选项，然后单击 " **刷新** " 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-361">Select an option, and then click the **Refresh** button to apply that filter.</span></span>

   ![选定的检测技术](../../media/ExplorerEmailMalwareDetectionTechATP.png)

<span data-ttu-id="1bf1c-363">报告将刷新，以显示使用您选择的技术选项在电子邮件中检测到恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-363">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="1bf1c-364">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-364">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="1bf1c-365">查看有关仿冒 Url 的数据，然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="1bf1c-365">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="1bf1c-366">假定您要查看通过电子邮件中的 Url 进行的网络钓鱼尝试，包括允许、阻止和重写的 Url 的列表。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-366">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="1bf1c-367">若要标识所单击的 Url，则需要配置 [安全链接](atp-safe-links.md) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-367">Identifying URLs that were clicked requires [Safe Links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="1bf1c-368">确保已为单击时的保护设置了 [安全链接策略](set-up-atp-safe-links-policies.md) ，然后单击 "安全链接" 中的 "verdicts" 进行日志记录。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-368">Make sure that you have set up [Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="1bf1c-369">若要查看邮件中的网络钓鱼 Url 并单击网络钓鱼邮件中的 Url，请使用资源管理器 (的 [电子邮件 > 网络钓鱼](threat-explorer-views.md#email--phish) 视图或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-369">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="1bf1c-370">在 "安全性 & 合规性中心 ([https://protection.office.com](https://protection.office.com) ") 中，选择 "**威胁管理**  >  **资源管理器** (" 或 "**实时检测**") 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-370">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="1bf1c-371"> (本示例使用 Explorer。 ) </span><span class="sxs-lookup"><span data-stu-id="1bf1c-371">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="1bf1c-372">在 "**视图**" 菜单中，选择 "**电子邮件**  >  **网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-372">In the **View** menu, choose **Email** > **Phish**.</span></span>

   ![浏览器的视图菜单](../../media/ExplorerViewEmailPhishMenu.png)

3. <span data-ttu-id="1bf1c-374">单击 "**发件人**"，然后选择 " **url**  >  **" 单击 "判定"**。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-374">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="1bf1c-375">选择一个或多个选项（如 "已 **阻止** " 和 " **阻止被覆盖**"），然后单击与应用该筛选器的选项位于同一行中的 " **刷新** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-375">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="1bf1c-376"> (不刷新浏览器窗口。 ) </span><span class="sxs-lookup"><span data-stu-id="1bf1c-376">(Don't refresh your browser window.)</span></span>

   ![Url 并单击 "verdicts"](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    <span data-ttu-id="1bf1c-378">报告将刷新，以在报告下的 "URL" 选项卡上显示两个不同的 URL 表：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-378">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="1bf1c-379">**上面的 url** 是您已筛选出的邮件中包含的 url，并且每个 URL 的电子邮件传递操作都会计数。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-379">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="1bf1c-380">在网络钓鱼电子邮件视图中，此列表通常包含合法的 Url。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-380">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="1bf1c-381">攻击者在其邮件中加入了好和坏的 Url，以尝试传递它们，但它们会使用户更有趣地单击恶意链接。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-381">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="1bf1c-382">Url 表按总电子邮件计数进行排序 (但请注意，此列处于隐藏状态，以简化视图) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-382">The table of URLs is sorted by total email count (but note that this column is hidden to simplify the view).</span></span>

   - <span data-ttu-id="1bf1c-383">单击**鼠标顶部**的安全链接包装的 url 已被单击，按总单击次数排序 (此列也不会显示以简化视图) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-383">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="1bf1c-384">"总计计数依据" 列指示安全链接单击每个单击的 URL 的 "已判定计数"。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-384">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="1bf1c-385">在网络钓鱼电子邮件视图中，这些 Url 更常见或恶意 Url，但可能包括不是威胁但位于网络钓鱼邮件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-385">In the phish email view, these are more often suspicious or malicious URLs, but could include URLs that are not threats but are in phish messages.</span></span> <span data-ttu-id="1bf1c-386">URL 单击未打开的链接将不会显示在此处。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-386">URL clicks on unwrapped links will not show up here.</span></span>

   <span data-ttu-id="1bf1c-387">这两个 URL 表通过传递操作和位置显示网络钓鱼电子邮件中的前几个 url，并且它们显示的 URL 单击已被阻止 (或访问被阻止) 的情况，以便您可以了解用户收到的潜在坏链接和用户的交互情况。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-387">The two URL tables show top URLs in phishing email messages by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="1bf1c-388">在这里，你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-388">From here, you can conduct further analysis.</span></span> <span data-ttu-id="1bf1c-389">例如，在图表下方，您可以看到在组织的环境中被阻止的电子邮件中的最高 Url。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-389">For example, below the chart, you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   ![阻止的资源管理器 Url](../../media/ExplorerPhishClickVerdictURLs.png)

   <span data-ttu-id="1bf1c-391">选择一个 URL 以查看更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-391">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1bf1c-392">在 "URL 浮出控件" 对话框中，将删除对电子邮件的筛选，以显示您的环境中 URL 公开的完整视图。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-392">In the URL flyout dialog, the filtering on email messages is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="1bf1c-393">这样，您就可以在资源管理器中筛选出您关注的电子邮件，找出潜在威胁的特定 Url，然后通过 "URL 详细信息") 对话框 (了解您的环境中的 URL 公开情况，而无需向资源管理器视图本身添加 URL 筛选器。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-393">This lets you filter down email messages in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-different-click-verdicts"></a><span data-ttu-id="1bf1c-394">不同的单击 verdicts 的解释</span><span class="sxs-lookup"><span data-stu-id="1bf1c-394">Interpretation of different click verdicts</span></span>

<span data-ttu-id="1bf1c-395">在电子邮件或 URL flyouts 中，点击率和在筛选体验中，你将看到不同的 click 值作为你的求职体验的一部分。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-395">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you will see different click values as part of your hunting experience.</span></span> <span data-ttu-id="1bf1c-396">下面是单击 Verdicts 及其解释的可能值：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-396">Below are the possible values of Click Verdicts and their interpretation:</span></span>

- <span data-ttu-id="1bf1c-397">**无**：我们无法捕获 URL 的结论。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-397">**None**: We were unable to capture the verdict for the URL.</span></span> <span data-ttu-id="1bf1c-398">用户可能已通过 URL 单击。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-398">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="1bf1c-399">**允许**：允许用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-399">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="1bf1c-400">已**阻止**：阻止用户导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-400">**Blocked**: The User was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="1bf1c-401">**挂起的判定**：用户显示沙箱挂起页面。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-401">**Pending verdict**: The user was presented with the detonation pending page.</span></span>
- <span data-ttu-id="1bf1c-402">**被阻止的被覆盖**：阻止用户导航到 URL;但是，用户 overrode 阻止导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-402">**Blocked overridden**: The user was blocked from navigating to the URL; however, the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="1bf1c-403">**挂起的判定被绕过**：向用户显示沙箱页面;但是，用户 overrode 页面以导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-403">**Pending verdict bypassed**: The user was presented with the detonation page; however, the user overrode the page to navigate to the URL.</span></span>
- <span data-ttu-id="1bf1c-404">**错误**：用户显示错误页。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-404">**Error**: The user was presented with the error page.</span></span> <span data-ttu-id="1bf1c-405">这也意味着捕获判定的错误。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-405">This can also mean there was an error in capturing the verdict.</span></span>
- <span data-ttu-id="1bf1c-406">**失败**：捕获判定时出现未知异常。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-406">**Failure**: There was unknown exception while capturing the verdict.</span></span> <span data-ttu-id="1bf1c-407">用户可能已通过 URL 单击。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-407">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="1bf1c-408">查看用户报告的电子邮件</span><span class="sxs-lookup"><span data-stu-id="1bf1c-408">Review email messages reported by users</span></span>

<span data-ttu-id="1bf1c-409">假设您想要查看您的组织中的用户使用 [Outlook 和 web 上的 outlook 的报告邮件外接程序](enable-the-report-message-add-in.md)报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-409">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="1bf1c-410">为此，请使用浏览器 (的 [电子邮件 > 提交](threat-explorer-views.md#email--submissions) 视图或实时检测) 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-410">To do this, use the [Email > Submissions](threat-explorer-views.md#email--submissions) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="1bf1c-411">在 "安全性 & 合规性中心 ([https://protection.office.com](https://protection.office.com) ") 中，选择 "**威胁管理**  >  **资源管理器** (" 或 "**实时检测**") 。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-411">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="1bf1c-412"> (本示例使用 Explorer。 ) </span><span class="sxs-lookup"><span data-stu-id="1bf1c-412">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="1bf1c-413">在 "**视图**" 菜单中，选择 "**电子邮件**  >  **提交**"。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-413">In the **View** menu, choose **Email** > **Submissions**.</span></span>

   ![浏览器的视图菜单](../../media/explorer-view-menu-email-user-reported.png)

3. <span data-ttu-id="1bf1c-415">单击 "**发件人**"，然后选择 "**基本**  >  **报告类型**"。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-415">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="1bf1c-416">选择一个选项，如 " **网络钓鱼**"，然后单击 " **刷新** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-416">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span>

   ![用户报告的网络钓鱼](../../media/EmailUserReportedReportType.png)

<span data-ttu-id="1bf1c-418">报告将刷新，以显示组织中的人员已报告为网络钓鱼尝试的电子邮件的相关数据。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-418">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="1bf1c-419">您可以使用此信息进行进一步分析，如有必要，调整您的 [ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-419">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="1bf1c-420">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="1bf1c-420">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="1bf1c-421">**Office 365 ATP 计划 2**和**Office 365 E5**中提供了自动调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-421">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="1bf1c-422"> (NEW！ ) [自动调查和响应](automated-investigation-response-office.md) 可在调查和缓解 cyberattacks 的过程中节省您的安全操作团队时间和精力。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-422">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="1bf1c-423">除了配置可触发安全行动手册的警报外，还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-423">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span>

<span data-ttu-id="1bf1c-424">有关此操作的详细信息，请参阅 [示例：安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-424">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="1bf1c-425">使用资源管理器 (或实时检测) 的更多方法</span><span class="sxs-lookup"><span data-stu-id="1bf1c-425">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="1bf1c-426">除了本文中介绍的方案，您还可以使用浏览器 (或实时检测) 更多的报告选项。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-426">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span>

- [<span data-ttu-id="1bf1c-427">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="1bf1c-427">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="1bf1c-428">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="1bf1c-428">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="1bf1c-429">获取有关威胁资源管理器中的视图的概述 (和实时检测) </span><span class="sxs-lookup"><span data-stu-id="1bf1c-429">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="1bf1c-430">Microsoft 威胁防护中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="1bf1c-430">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="1bf1c-431">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="1bf1c-431">Required licenses and permissions</span></span>

<span data-ttu-id="1bf1c-432">您必须具有 [Office 365 ATP](office-365-atp.md) 才能获取资源管理器或实时检测。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-432">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>

- <span data-ttu-id="1bf1c-433">资源管理器包含在 Office 365 ATP 计划2中。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-433">Explorer is included in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="1bf1c-434">实时检测报告包含在 Office 365 ATP 计划1中。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-434">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>
- <span data-ttu-id="1bf1c-435">计划为应受 Office 365 ATP 保护的所有用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-435">Plan to assign licenses for all users who should be protected by Office 365 ATP.</span></span> <span data-ttu-id="1bf1c-436"> (资源管理器或实时检测显示许可用户的检测数据。 ) </span><span class="sxs-lookup"><span data-stu-id="1bf1c-436">(Explorer or real-time detections shows detection data for licensed users.)</span></span>

<span data-ttu-id="1bf1c-437">若要查看和使用资源管理器或实时检测，您必须具有适当的权限，例如，授予安全管理员或安全阅读者的权限。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-437">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="1bf1c-438">对于安全 &amp; 合规中心，您必须具有以下分配的角色之一：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-438">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="1bf1c-439">组织管理</span><span class="sxs-lookup"><span data-stu-id="1bf1c-439">Organization Management</span></span>
  - <span data-ttu-id="1bf1c-440">安全管理员 (可以在 Azure Active Directory 管理中心 (中分配此项 [https://aad.portal.azure.com](https://aad.portal.azure.com)) # A3</span><span class="sxs-lookup"><span data-stu-id="1bf1c-440">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="1bf1c-441">安全读取者</span><span class="sxs-lookup"><span data-stu-id="1bf1c-441">Security Reader</span></span>

- <span data-ttu-id="1bf1c-442">对于 Exchange Online，必须在 Exchange 管理中心 () 或 PowerShell cmdlet 中分配以下角色之一 [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) (请参阅 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) ：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-442">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="1bf1c-443">组织管理</span><span class="sxs-lookup"><span data-stu-id="1bf1c-443">Organization Management</span></span>
  - <span data-ttu-id="1bf1c-444">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="1bf1c-444">View-only Organization Management</span></span>
  - <span data-ttu-id="1bf1c-445">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="1bf1c-445">View-Only Recipients role</span></span>
  - <span data-ttu-id="1bf1c-446">合规性管理</span><span class="sxs-lookup"><span data-stu-id="1bf1c-446">Compliance Management</span></span>

<span data-ttu-id="1bf1c-447">若要了解有关角色和权限的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="1bf1c-447">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="1bf1c-448">安全 &amp; 合规性中心中的权限</span><span class="sxs-lookup"><span data-stu-id="1bf1c-448">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="1bf1c-449">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="1bf1c-449">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="1bf1c-450">威胁资源管理器和实时检测的区别</span><span class="sxs-lookup"><span data-stu-id="1bf1c-450">Some differences between Threat Explorer and real-time detections</span></span>

- <span data-ttu-id="1bf1c-451">Office 365 ATP 计划1中提供了 **实时检测** 报告，而 **威胁浏览器** 在 office 365 atp 计划2中可用。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-451">The **real-time detections** report is available in Office 365 ATP Plan 1, whereas **Threat Explorer** is available in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="1bf1c-452">**实时检测**报告允许你实时查看检测。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-452">The **real-time detections** report allows you to view detections in real-time.</span></span> <span data-ttu-id="1bf1c-453">**威胁资源管理器** 也会执行此功能，但也允许您查看给定攻击的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-453">**Threat Explorer** does this as well, but also allows you to view additional details for a given attack.</span></span>
- <span data-ttu-id="1bf1c-454">" **所有电子邮件** " 视图在 **威胁资源管理器** 中可用 (并且不在 **实时检测** 报告) 中。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-454">An **All email** view is available in **Threat Explorer** (and is not in the **real-time detections** report).</span></span>
- <span data-ttu-id="1bf1c-455">**威胁资源管理器**中包含更多筛选功能和可用操作。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-455">More filtering capabilities and available actions are included in **Threat Explorer**.</span></span>

<span data-ttu-id="1bf1c-456">有关更多详细信息，请参阅 [Office 365 ATP 服务说明：功能在高级威胁防护中的功能可用性 (ATP) 计划](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="1bf1c-456">For more details, see [Office 365 ATP Service Description: Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
