---
title: 调查在 Office 365 中传递的恶意电子邮件，查找并调查恶意电子邮件
keywords: TIMailData Inline， 安全事件， 事件， ATP PowerShell， 电子邮件恶意软件， 受到威胁的用户， 电子邮件网络钓鱼， 电子邮件恶意软件， 阅读电子邮件头， 阅读邮件头， 打开电子邮件头， 特殊操作
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 07/09/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 了解如何使用威胁调查和响应功能查找并调查恶意电子邮件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5026b69f356fad11a664900a3e316d9c1c976905
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845950"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="cbcb1-104">调查在 Office 365 中传递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="cbcb1-104">Investigate malicious email that was delivered in Office 365</span></span>

<span data-ttu-id="cbcb1-105">[Office 365 高级威胁](office-365-atp.md) 防护使你能够调查将组织中的人员置于风险中的活动，并采取措施来保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-105">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="cbcb1-106">例如，如果您是组织的安全团队的一部分，您可以查找并调查已传递的可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-106">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="cbcb1-107">可以通过使用威胁资源[管理器管理人员 (或实时检测功能或实时) 。 ](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="cbcb1-107">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cbcb1-108">在此处跳转到修正 [文章](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-21vianet&branch=pr-en-us-4258)。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-108">Jump to the remediation article [here](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-21vianet&branch=pr-en-us-4258).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cbcb1-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="cbcb1-109">Before you begin</span></span>

<span data-ttu-id="cbcb1-110">请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="cbcb1-110">Make sure that the following requirements are met:</span></span>

- <span data-ttu-id="cbcb1-111">你的组织已[将 Office 365 高级威胁](office-365-atp.md)[防护许可证分配给用户](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-111">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) and [licenses are assigned to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

- <span data-ttu-id="cbcb1-112">[审核](../../compliance/turn-audit-log-search-on-or-off.md) 记录已为组织打开。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-112">[audit logging](../../compliance/turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span>

- <span data-ttu-id="cbcb1-113">您的组织已为反垃圾邮件、反恶意软件、防网络钓鱼等定义了策略。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-113">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="cbcb1-114">请参阅["Office 365 中的威胁防护"。](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="cbcb1-114">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="cbcb1-115">你是全局管理员，或者你已在安全合规中心分配了安全管理员或搜索并 &amp; 清除角色。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-115">You are a global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="cbcb1-116">请参阅 [安全合规中心 &amp; 中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-116">See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="cbcb1-117">对于某些操作，你还必须分配有新的预览角色。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-117">For some actions, you must also have a new Preview role assigned.</span></span>

### <a name="preview-role-permissions"></a><span data-ttu-id="cbcb1-118">预览角色权限</span><span class="sxs-lookup"><span data-stu-id="cbcb1-118">Preview role permissions</span></span>

<span data-ttu-id="cbcb1-119">若要执行某些操作，如查看邮件头或下载电子邮件内容，您必须将名为"预览"的新角色添加到其他适当*Preview*的角色组中。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-119">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate role group.</span></span> <span data-ttu-id="cbcb1-120">下表说明了所需角色和权限。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-120">The following table clarifies required roles and permissions.</span></span>

****

|<span data-ttu-id="cbcb1-121">活动</span><span class="sxs-lookup"><span data-stu-id="cbcb1-121">Activity</span></span>|<span data-ttu-id="cbcb1-122">角色组</span><span class="sxs-lookup"><span data-stu-id="cbcb1-122">Role group</span></span>|<span data-ttu-id="cbcb1-123">预览角色是否需要？</span><span class="sxs-lookup"><span data-stu-id="cbcb1-123">Preview role needed?</span></span>|
|---|---|---|
|<span data-ttu-id="cbcb1-124">使用威胁 (和实时检测) 分析威胁</span><span class="sxs-lookup"><span data-stu-id="cbcb1-124">Use Threat Explorer (and real-time detections) to analyze threats</span></span> |<span data-ttu-id="cbcb1-125">全局管理员</span><span class="sxs-lookup"><span data-stu-id="cbcb1-125">Global Administrator</span></span> <br> <span data-ttu-id="cbcb1-126">安全管理员</span><span class="sxs-lookup"><span data-stu-id="cbcb1-126">Security Administrator</span></span> <br> <span data-ttu-id="cbcb1-127">安全读取者</span><span class="sxs-lookup"><span data-stu-id="cbcb1-127">Security Reader</span></span>|<span data-ttu-id="cbcb1-128">否</span><span class="sxs-lookup"><span data-stu-id="cbcb1-128">No</span></span>|
|<span data-ttu-id="cbcb1-129">使用威胁 (和实) 时检测来查看电子邮件的邮件头，以及预览和下载隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="cbcb1-129">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>|<span data-ttu-id="cbcb1-130">全局管理员</span><span class="sxs-lookup"><span data-stu-id="cbcb1-130">Global Administrator</span></span> <br> <span data-ttu-id="cbcb1-131">安全管理员</span><span class="sxs-lookup"><span data-stu-id="cbcb1-131">Security Administrator</span></span> <br><span data-ttu-id="cbcb1-132">安全读取者</span><span class="sxs-lookup"><span data-stu-id="cbcb1-132">Security Reader</span></span>|<span data-ttu-id="cbcb1-133">否</span><span class="sxs-lookup"><span data-stu-id="cbcb1-133">No</span></span>|
|<span data-ttu-id="cbcb1-134">使用威胁资源管理器查看邮件头和下载传递到邮箱的电子邮件</span><span class="sxs-lookup"><span data-stu-id="cbcb1-134">Use Threat Explorer to view headers and download email messages delivered to mailboxes</span></span>|<span data-ttu-id="cbcb1-135">全局管理员</span><span class="sxs-lookup"><span data-stu-id="cbcb1-135">Global Administrator</span></span> <br><span data-ttu-id="cbcb1-136">安全管理员</span><span class="sxs-lookup"><span data-stu-id="cbcb1-136">Security Administrator</span></span> <br> <span data-ttu-id="cbcb1-137">安全读取者</span><span class="sxs-lookup"><span data-stu-id="cbcb1-137">Security Reader</span></span> <br> <span data-ttu-id="cbcb1-138">预览</span><span class="sxs-lookup"><span data-stu-id="cbcb1-138">Preview</span></span>|<span data-ttu-id="cbcb1-139">是</span><span class="sxs-lookup"><span data-stu-id="cbcb1-139">Yes</span></span>|
|

> [!NOTE]
> <span data-ttu-id="cbcb1-140">*预览* 是一个角色，而不是角色组;必须将预览角色添加到 Office 365 的现有角色组中。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-140">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365.</span></span> <span data-ttu-id="cbcb1-141">将为全局管理员角色分配 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) ，并在安全 & 合规性中心网站中分配安全管理员和安全 [https://protection.office.com](https://protection.office.com) () 。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-141">The Global Administrator role is assigned the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)), and the Security Administrator and Security Reader roles are assigned in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="cbcb1-142">若要了解有关角色和权限的详细信息，请参阅 [安全与合规中心&权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-142">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="cbcb1-143">查找并删除传递的可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="cbcb1-143">Find and delete suspicious email that was delivered</span></span>

<span data-ttu-id="cbcb1-144">威胁资源管理器是一种功能强大的报告，可以用于多种用途，如查找和删除邮件、识别恶意电子邮件发件人的 IP 地址或启动事件以供进一步调查。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-144">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="cbcb1-145">以下步骤重点介绍使用资源管理器查找并删除收件人邮箱中的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-145">The following procedure focuses on using Explorer to find and delete malicious email from recipient's mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="cbcb1-146">浏览器中的默认搜索当前不包括 Zapped 项目。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-146">Default searches in Explorer don't currently include Zapped items.</span></span>  <span data-ttu-id="cbcb1-147">这适用于所有视图，如恶意软件或钓鱼视图。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-147">This applies to all views, for example malware or phish views.</span></span> <span data-ttu-id="cbcb1-148">若要包含"交付"项目，需要添加设置为包括"已通过 ZAP 删除"的"传递"操作。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-148">To include Zapped items you need to add a 'Delivery action' set to include 'Removed by ZAP'.</span></span> <span data-ttu-id="cbcb1-149">如果包含所有选项，则将看到所有送达操作结果，包括"已压缩项目"。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-149">If you include all options, you'll see all delivery action results, including Zapped items.</span></span>

1. <span data-ttu-id="cbcb1-150">**导航到威胁资源**管理器： [https://protection.office.com](https://protection.office.com) 转到并使用 Office 365 工作或学校帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-150">**Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="cbcb1-151">这会转到安全合 &amp; 规中心。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-151">This takes you to the Security &amp; Compliance Center.</span></span>

2. <span data-ttu-id="cbcb1-152">在左侧导航快速启动中，选择威胁 **管理资源** \> **管理器**。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-152">In the left navigation quick-launch, choose **Threat management** \> **Explorer**.</span></span>

    ![使用"传递操作和传递位置"字段的资源管理器。](../../media/ThreatExFields.PNG)

    <span data-ttu-id="cbcb1-154">您可能会注意到新的 **特殊操作** 列。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-154">You may notice the new **Special actions** column.</span></span> <span data-ttu-id="cbcb1-155">此功能适用于告诉管理员处理电子邮件的成就。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-155">This feature is aimed at telling admins the outcome of processing an email.</span></span> <span data-ttu-id="cbcb1-156">可以在**与**传递操作和传递位置相同的位置**访问特殊\*\*\*\*操作列**。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-156">The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**.</span></span> <span data-ttu-id="cbcb1-157">特殊操作可能会在威胁资源管理器电子邮件时间线结束时更新，这是一种专为管理员提供更好搜索体验的新功能。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-157">Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.</span></span>

3. <span data-ttu-id="cbcb1-158">**威胁资源管理器中的**视图：在"**视图"菜单**中，选择"**所有电子邮件"。**</span><span class="sxs-lookup"><span data-stu-id="cbcb1-158">**Views in Threat Explorer**: In the **View** menu, choose **All email**.</span></span>

    ![威胁资源管理器查看菜单，电子邮件 - 恶意软件、网络钓鱼、提交和所有电子邮件选项，也是"内容 - 恶意软件"。](../../media/tp-InvestigateMalEmail-viewmenu.png)

    <span data-ttu-id="cbcb1-160">" *恶意软件* "视图当前为默认视图，可捕获检测到恶意软件威胁的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-160">The *Malware* view is currently the default, and captures emails where a malware threat is detected.</span></span> <span data-ttu-id="cbcb1-161">*网络钓鱼*视图的操作方式与网络钓鱼相同。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-161">The *Phish* view operates in the same way, for Phish.</span></span>

    <span data-ttu-id="cbcb1-162">但是， *所有电子邮件* 视图都会列出组织收到的所有邮件，无论是否检测到威胁。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-162">However, *All email* view lists every mail received by the organization, whether threats were detected or not.</span></span> <span data-ttu-id="cbcb1-163">正如您所见，这是大量数据，这就是为什么此视图显示要求应用筛选器的占位符的显示。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-163">As you can imagine, this is a lot of data, which is why this view shows a placeholder that asks a filter be applied.</span></span> <span data-ttu-id="cbcb1-164"> (此视图仅适用于 ATP P2 客户。) </span><span class="sxs-lookup"><span data-stu-id="cbcb1-164">(This view is only available for ATP P2 customers.)</span></span>

    <span data-ttu-id="cbcb1-165">*"提交* "视图显示由管理员或用户提交的报告为 Microsoft 的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-165">*Submissions* view shows up all mails submitted by admin or user that were reported to Microsoft.</span></span>

4. <span data-ttu-id="cbcb1-166">**在威胁资源管理器中**搜索并筛选：筛选器显示在搜索栏中页面顶部，以帮助管理员进行调查。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-166">**Search and filter in Threat Explorer**: Filters appear at the top of the page in the search bar to help admins in their investigations.</span></span> <span data-ttu-id="cbcb1-167">请注意，可以同时应用多个筛选器，并且添加到筛选器中的多个以逗号分隔的值以缩小搜索范围。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-167">Notice that multiple filters can be applied at the same time, and multiple comma-separated values added to a filter to narrow down the search.</span></span> <span data-ttu-id="cbcb1-168">请注意：</span><span class="sxs-lookup"><span data-stu-id="cbcb1-168">Remember:</span></span>

    - <span data-ttu-id="cbcb1-169">筛选器将对大部分筛选条件执行完全匹配。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-169">Filters do exact matching on most filter conditions.</span></span>
    - <span data-ttu-id="cbcb1-170">主题筛选器使用 CONTAINS 查询。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-170">Subject filter uses a CONTAINS query.</span></span>
    - <span data-ttu-id="cbcb1-171">URL 筛选器使用或不带协议， (扩展。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-171">URL filters work with or without protocols (ex.</span></span> <span data-ttu-id="cbcb1-172">https) 。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-172">https).</span></span>
    - <span data-ttu-id="cbcb1-173">URL 域、URL 路径和 URL 域和路径筛选器不需要协议来筛选。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-173">URL domain, URL path, and URL domain and path filters don't require a protocol to filter.</span></span>
    - <span data-ttu-id="cbcb1-174">每次更改筛选器值以获取相关结果时都必须单击"刷新"图标。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-174">You must click the Refresh icon every time you change the filter values to get relevant results.</span></span>

5. <span data-ttu-id="cbcb1-175">**高级筛选器**：通过这些筛选器，可以生成复杂的查询并筛选数据集。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-175">**Advanced filters**: With these filters, you can build complex queries and filter your data set.</span></span> <span data-ttu-id="cbcb1-176">单击高级 *筛选器将打开* 一个包含选项的浮出控件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-176">Clicking on *Advanced Filters* opens a flyout with options.</span></span>

   <span data-ttu-id="cbcb1-177">高级筛选是对搜索功能的不仅功能。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-177">Advanced filtering is a great addition to search capabilities.</span></span> <span data-ttu-id="cbcb1-178">已在**收件人**、发件人和*发件人域上*引入了*Sender*布尔 NOT*筛选器*，以允许管理员通过排除值进行调查。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-178">A boolean **NOT** filter has been introduced on *Recipient*, *Sender* and *Sender domain* to allow admins to investigate by excluding values.</span></span> <span data-ttu-id="cbcb1-179">该选项出现在选择参数（ *不包含任何参数）下*。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-179">This option appears under selection parameter *Contains none of*.</span></span> <span data-ttu-id="cbcb1-180">**不**允许管理员排除警报邮箱、调查的默认答复邮箱，并对管理员搜索特定主题 (subject="注意") 其中收件人可以设置为*任何 defaultMail \@ contoso.com。*</span><span class="sxs-lookup"><span data-stu-id="cbcb1-180">**NOT** will let admins exclude alert mailboxes, default reply mailboxes from their investigations, and is useful for cases where admins search for a specific subject (subject="Attention") where the Recipient can be set to *none of defaultMail\@contoso.com*.</span></span> <span data-ttu-id="cbcb1-181">这是一个确切的值搜索。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-181">This is an exact value search.</span></span>

   ![Recipients -'Contains no of' Advanced filter.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   <span data-ttu-id="cbcb1-183">*按小时筛选* 将有助于组织的安全团队快速钻取。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-183">*Filtering by hours* will help your organization's security team drill down quickly.</span></span> <span data-ttu-id="cbcb1-184">最短的允许时段为 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-184">The shortest allowed time duration is 30 minutes.</span></span> <span data-ttu-id="cbcb1-185">如果你可以通过超时时间框架缩小 (操作的范围，例如 3 小时前) ，这将限制上下文并有助于引断问题。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-185">If you can narrow the suspicious action by time-frame (e.g. it happened 3 hours ago), this will limit the context and help pinpoint the problem.</span></span>

   ![按小时筛选选项可缩小数据安全团队必须处理的数据安全团队的范围，且最短的持续时间为 30 分钟。](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. <span data-ttu-id="cbcb1-187">**威胁资源管理器中的**字段：威胁资源管理器中显示更多安全性相关邮件，例如*传递*操作、送达*位置\*\*、特殊操作*、*方向性*、*重*写和*URL 威胁*。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-187">**Fields in threat explorer**: Threat Explorer exposes a lot more security-related mail information such as *Delivery action*, *Delivery location*, *Special action*, *Directionality*, *Overrides*, and *URL threat*.</span></span> <span data-ttu-id="cbcb1-188">此外，它还允许组织的安全团队调查更高的人员。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-188">It also allows your organization's security team to investigate with a higher certainty.</span></span>

    <span data-ttu-id="cbcb1-189">*由于存在* 现有策略或检测，导致对电子邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-189">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="cbcb1-190">以下是电子邮件可以采取的操作：</span><span class="sxs-lookup"><span data-stu-id="cbcb1-190">Here are the possible actions an email can take:</span></span>

    - <span data-ttu-id="cbcb1-191">**已送** 达 - 电子邮件被传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-191">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
    - <span data-ttu-id="cbcb1-192">**已 (** 送 (送至垃圾邮件) 的电子邮件被发送到用户的垃圾邮件文件夹或已删除文件夹，并且用户有权访问其"垃圾邮件"或"已删除"文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-192">**Junked** (Delivered to junk)– email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>
    - <span data-ttu-id="cbcb1-193">**已** 阻止 - 任何被隔离、失败或已删除的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-193">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="cbcb1-194"> (user.) 完全无法访问此功能) </span><span class="sxs-lookup"><span data-stu-id="cbcb1-194">(This is completely inaccessible by the user.)</span></span>
    - <span data-ttu-id="cbcb1-195">**已替换** - 恶意附件替换为声明是恶意附件的 .txt 文件的任何电子邮件</span><span class="sxs-lookup"><span data-stu-id="cbcb1-195">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious</span></span>

    <span data-ttu-id="cbcb1-196">**传递位置**：传递位置筛选器提供，以帮助管理员了解可疑邮件在哪里结束以及对其采取的操作。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-196">**Delivery location**: The Delivery location filter is available in order to help admins understand where suspected malicious mail ended-up and what actions were taken on it.</span></span> <span data-ttu-id="cbcb1-197">生成的数据可导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-197">The resulting data can be exported to spreadsheet.</span></span> <span data-ttu-id="cbcb1-198">可能的传递位置包括：</span><span class="sxs-lookup"><span data-stu-id="cbcb1-198">Possible delivery locations are:</span></span>

    - <span data-ttu-id="cbcb1-199">**收件箱** 或文件夹 - 电子邮件位于收件箱或特定文件夹中，具体取决于你的电子邮件规则。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-199">**Inbox or folder** – The email is in the Inbox or a specific folder, according to your email rules.</span></span>
    - <span data-ttu-id="cbcb1-200">**本地或外部** – 邮箱不存在于云中，但本地。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-200">**On-prem or external** – The mailbox doesn't exist in the Cloud but is on-premises.</span></span>
    - <span data-ttu-id="cbcb1-201">**"垃圾邮件** "文件夹 – 电子邮件在用户的"垃圾邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-201">**Junk folder** – The email is in a user's Junk mail folder.</span></span>
    - <span data-ttu-id="cbcb1-202">**"已删除邮件** "文件夹 – 电子邮件位于用户的"已删除邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-202">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>
    - <span data-ttu-id="cbcb1-203">**隔离 – 在隔离** 电子邮件，而不是在用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-203">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>
    - <span data-ttu-id="cbcb1-204">**失败** – 电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-204">**Failed** – The email failed to reach the mailbox.</span></span>
    - <span data-ttu-id="cbcb1-205">**Dropped** – 电子邮件在邮件流中的某个位置中丢失。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-205">**Dropped** – The email was lost somewhere in the mail flow.</span></span>

    <span data-ttu-id="cbcb1-206">**方向性**：此选项允许安全操作团队按邮件来源于或正在进行筛选的"方向"进行筛选。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-206">**Directionality**: This option allows your security operations team to filter by the 'direction' a mail comes from, or is going.</span></span> <span data-ttu-id="cbcb1-207">方向值为 *Inbound* *、Outbound*和 *Intra- (* 与将进入组织的外部、外出或内部发送给组织的邮件相对应的) 。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-207">Directionality values are *Inbound*, *Outbound*, and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively).</span></span> <span data-ttu-id="cbcb1-208">此信息有助于安全运营团队欺骗欺骗和模拟，因为方向性值之间 (难。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-208">This information can help security operations teams spot spoofing and impersonation, because a mismatch between the Directionality value (ex.</span></span> <span data-ttu-id="cbcb1-209">*入*) 站消息，以及用户 (*域* 显示为) 显示！</span><span class="sxs-lookup"><span data-stu-id="cbcb1-209">*Inbound*), and the domain of the sender (which *appears* to be an internal domain) will be evident!</span></span> <span data-ttu-id="cbcb1-210">方向性值是分隔的且可以不同于邮件跟踪。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-210">The Directionality value is separate, and can differ from, the Message Trace.</span></span> <span data-ttu-id="cbcb1-211">可将结果导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-211">Results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="cbcb1-212">**重**写：此筛选器获取邮件的详细信息选项卡上显示的信息，并用它来公开组织或用户策略，以允许和阻止 *邮件被覆盖*。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-212">**Overrides**: This filter takes information that appears on the mail's details tab and uses it to expose where organizational, or user policies, for allowing and blocking mails have been *overridden*.</span></span> <span data-ttu-id="cbcb1-213">此筛选器最重要的一点是，它可以帮助组织的安全团队查看根据配置而传递了多少封可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-213">The most important thing about this filter is that it helps your organization's security team see how many suspicious emails were delivered due to configuration.</span></span> <span data-ttu-id="cbcb1-214">这样他们就可以根据需要修改允许和阻止。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-214">This gives them an opportunity to modify allows and blocks as needed.</span></span> <span data-ttu-id="cbcb1-215">此结果集可导出到电子表格的此筛选器。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-215">This result set of this filter can be exported to spreadsheet.</span></span>

    ****

    |<span data-ttu-id="cbcb1-216">威胁资源管理器覆盖</span><span class="sxs-lookup"><span data-stu-id="cbcb1-216">Threat Explorer Overrides</span></span>|<span data-ttu-id="cbcb1-217">其含义</span><span class="sxs-lookup"><span data-stu-id="cbcb1-217">What they mean</span></span>|
    |---|---|
    |<span data-ttu-id="cbcb1-218">组织策略允许</span><span class="sxs-lookup"><span data-stu-id="cbcb1-218">Allowed by Org Policy</span></span>|<span data-ttu-id="cbcb1-219">通过组织策略的指示邮件可以进入邮箱。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-219">Mail was allowed into the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="cbcb1-220">因组织策略被阻止</span><span class="sxs-lookup"><span data-stu-id="cbcb1-220">Blocked by Org policy</span></span>|<span data-ttu-id="cbcb1-221">已阻止邮件按组织策略的指示传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-221">Mail was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="cbcb1-222">组织策略阻止的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="cbcb1-222">File extension blocked by Org Policy</span></span>|<span data-ttu-id="cbcb1-223">阻止文件按组织策略的指示传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-223">File was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="cbcb1-224">用户策略允许</span><span class="sxs-lookup"><span data-stu-id="cbcb1-224">Allowed by User Policy</span></span>|<span data-ttu-id="cbcb1-225">邮件被用户策略的定向允许进入邮箱。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-225">Mail was allowed into the mailbox as directed by the user policy.</span></span>|
    |<span data-ttu-id="cbcb1-226">被用户策略阻止</span><span class="sxs-lookup"><span data-stu-id="cbcb1-226">Blocked by User Policy</span></span>|<span data-ttu-id="cbcb1-227">已阻止邮件按用户策略的指示传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-227">Mail was blocked from delivery to the mailbox as directed by the user policy.</span></span>|
    |

    <span data-ttu-id="cbcb1-228">**URL 威**胁：URL 威胁字段包含在 *电子邮件* 的详细信息选项卡中，以指示 URL 显示的威胁。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-228">**URL threat**: The URL threat field has been included on the *details* tab of an email to indicate the threat presented by a URL.</span></span> <span data-ttu-id="cbcb1-229">URL 提供的威胁可能包括*恶意软件、\*\*网络钓鱼*或*垃圾邮件*，但"*威*胁"部分中的"无任何"的 URL*将说明为"* 无"。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-229">Threats presented by a URL can include *Malware*, *Phish*, or *Spam*, and a URL with *no threat* will say *None* in the threats section.</span></span>

7. <span data-ttu-id="cbcb1-230">**电子邮件日程表**视图：安全运营团队可能需要深入了解电子邮件详细信息才能进一步调查。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-230">**Email timeline view**: Your security operations team might need to deep-dive into email details to investigate further.</span></span> <span data-ttu-id="cbcb1-231">电子邮件时间线允许管理员查看对电子邮件所采取的送达投递的操作。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-231">The email timeline allows admins to view actions taken on an email from delivery to post-delivery.</span></span> <span data-ttu-id="cbcb1-232">要查看电子邮件时间线，请单击电子邮件主题，然后单击"电子邮件"时间线。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-232">To view an email timeline, click on the subject of an email message, and then click Email timeline.</span></span> <span data-ttu-id="cbcb1-233"> (它出现在面板上的其他标题中，如摘要或详细信息.) 这些结果可以导出到电子表格中。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-233">(It appears among other headings on the panel like Summary or Details.) These results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="cbcb1-234">电子邮件日程表将打开到表，该表显示电子邮件的所有送达和后期事件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-234">Email timeline will open to a table that shows all delivery and post-delivery events for the email.</span></span> <span data-ttu-id="cbcb1-235">如果对电子邮件没有进一步操作，则应该会看到原始传递的单个事件，其中声明了像钓鱼这样的*谓词的原始传递*。 *Blocked*</span><span class="sxs-lookup"><span data-stu-id="cbcb1-235">If there are no further actions on the email, you should see a single event for the original delivery that states a result, such as *Blocked*, with a verdict like *Phish*.</span></span> <span data-ttu-id="cbcb1-236">管理员可以导出整个电子邮件时间线，包括选项卡和电子邮件标题、 (如主题、发件人、收件人、网络和邮件 ID) 。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-236">Admins can export the entire email timeline, including all details on the tab and email (such as, Subject, Sender, Recipient, Network, and Message ID).</span></span> <span data-ttu-id="cbcb1-237">电子邮件时间线切断日程表，因为花费的时间较少，可以试图了解自从电子邮件到达以来发生的事件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-237">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="cbcb1-238">当多个事件发生在一封电子邮件或接近，在一封电子邮件中发生，这些事件会显示在时间线视图中。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-238">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span>

8. <span data-ttu-id="cbcb1-239">**预览/** 下载：威胁资源管理器为你的安全运营团队提供了调查可疑电子邮件所需的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-239">**Preview / download**: Threat Explorer gives your security operations team the details they need to investigate suspicious email.</span></span> <span data-ttu-id="cbcb1-240">安全运营团队可以：</span><span class="sxs-lookup"><span data-stu-id="cbcb1-240">Your security operations team can either:</span></span>

    - <span data-ttu-id="cbcb1-241">[检查传递操作和位置](#check-the-delivery-action-and-location)。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-241">[Check the delivery action and location](#check-the-delivery-action-and-location).</span></span>

    - <span data-ttu-id="cbcb1-242">[查看电子邮件的日程表](#view-the-timeline-of-your-email)。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-242">[View the timeline of your email](#view-the-timeline-of-your-email).</span></span>

### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="cbcb1-243">检查传递操作和位置</span><span class="sxs-lookup"><span data-stu-id="cbcb1-243">Check the delivery action and location</span></span>

<span data-ttu-id="cbcb1-244">在[威胁 (和实时) ](threat-explorer.md)中，现在具有 **"传递操作和\*\*\*\*传递位置"列**，而不是以前的"**传递状态"** 列。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-244">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="cbcb1-245">这将更加完整地了解电子邮件的地位置。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-245">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="cbcb1-246">这一更改的目标是使调查更易于安全操作团队，但最终结果是可以一目了然地了解有问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-246">Part of the goal of this change is to make investigations easier for security operations teams, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="cbcb1-247">现在，传递状态分成两列：</span><span class="sxs-lookup"><span data-stu-id="cbcb1-247">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="cbcb1-248">**传递操作** - 此电子邮件的状态是什么？</span><span class="sxs-lookup"><span data-stu-id="cbcb1-248">**Delivery action** - What is the status of this email?</span></span>

- <span data-ttu-id="cbcb1-249">**传递位置** - 该电子邮件的结果是什么结果？</span><span class="sxs-lookup"><span data-stu-id="cbcb1-249">**Delivery location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="cbcb1-250">由于存在现有策略或检测，导致对电子邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-250">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="cbcb1-251">以下是电子邮件可以采取的操作：</span><span class="sxs-lookup"><span data-stu-id="cbcb1-251">Here are the possible actions an email can take:</span></span>

- <span data-ttu-id="cbcb1-252">**已送** 达 - 电子邮件被传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-252">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

- <span data-ttu-id="cbcb1-253">**垃圾邮件** - 电子邮件被发送到用户的垃圾邮件文件夹或已删除文件夹，并且用户有权访问其"垃圾邮件"或"已删除"文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-253">**Junked** – email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

- <span data-ttu-id="cbcb1-254">**已** 阻止 - 任何被隔离、失败或已删除的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-254">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="cbcb1-255"> (user.) 完全无法访问此功能) </span><span class="sxs-lookup"><span data-stu-id="cbcb1-255">(This is completely inaccessible by the user.)</span></span>

- <span data-ttu-id="cbcb1-256">**已替换** - 恶意附件替换为声明该附件是恶意附件的 .txt 文件的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-256">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>

<span data-ttu-id="cbcb1-257">传递位置显示运行后邮件的策略和检测的结果。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-257">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="cbcb1-258">它链接到传递操作。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-258">It's linked to a Delivery Action.</span></span> <span data-ttu-id="cbcb1-259">添加此字段是为了让你了解发现问题邮件时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-259">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="cbcb1-260">以下是传递位置可能的值：</span><span class="sxs-lookup"><span data-stu-id="cbcb1-260">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="cbcb1-261">**收件箱或** 文件夹 - 电子邮件位于收件箱或文件夹中， (联系人中) 。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-261">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

- <span data-ttu-id="cbcb1-262">**本地或外部** – 邮箱不存在于云上，但在本地。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-262">**On-prem or external** – The mailbox doesn't exist on cloud but is on-premises.</span></span>

- <span data-ttu-id="cbcb1-263">**垃圾邮件** 文件夹 – 电子邮件位于用户的"垃圾邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-263">**Junk folder** – The email is in a user's Junk folder.</span></span>

- <span data-ttu-id="cbcb1-264">**"已删除邮件** "文件夹 – 电子邮件位于用户的"已删除邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-264">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

- <span data-ttu-id="cbcb1-265">**隔离 – 在隔离** 电子邮件，而不是在用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-265">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>

- <span data-ttu-id="cbcb1-266">**失败** – 电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-266">**Failed** – The email failed to reach the mailbox.</span></span>

- <span data-ttu-id="cbcb1-267">**Dropped** – 电子邮件丢失于邮件流中的某个地点。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-267">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="cbcb1-268">查看电子邮件的日程表</span><span class="sxs-lookup"><span data-stu-id="cbcb1-268">View the timeline of your email</span></span>

<span data-ttu-id="cbcb1-269">**"电子邮件日程** 表"是威胁资源管理器中的一个字段，可以帮助你更轻松地寻线安全运营团队。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-269">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="cbcb1-270">当在电子邮件上同时或接近同一时间发生多个事件时，这些事件会显示在时间线视图中。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-270">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="cbcb1-271">某些在送达电子邮件后的事件将捕获到"特殊 **操作"列** 中。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-271">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="cbcb1-272">将电子邮件的时间线信息与在送达后采取的任何特殊操作相组合，管理员将对策略和威胁处理 (（例如邮件的路由位置以及某些情况下的最终评估是) ）提供。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-272">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cbcb1-273">单击此处的修正 [主题](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="cbcb1-273">Jump to a remediation topic [here](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-worldwide).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cbcb1-274">相关主题</span><span class="sxs-lookup"><span data-stu-id="cbcb1-274">Related topics</span></span>

[<span data-ttu-id="cbcb1-275">修正 Office 365 中传递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="cbcb1-275">Remediate malicious email delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-worldwide)

[<span data-ttu-id="cbcb1-276">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="cbcb1-276">Office 365 Advanced Threat Protection</span></span>](office-365-ti.md)

[<span data-ttu-id="cbcb1-277">Office 365 中的威胁防护</span><span class="sxs-lookup"><span data-stu-id="cbcb1-277">Protect against threats in Office 365</span></span>](protect-against-threats.md)

[<span data-ttu-id="cbcb1-278">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="cbcb1-278">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
