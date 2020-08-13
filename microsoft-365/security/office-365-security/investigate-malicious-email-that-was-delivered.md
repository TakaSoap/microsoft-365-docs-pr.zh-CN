---
title: 调查 Office 365 中提供的恶意电子邮件，查找并调查恶意电子邮件
keywords: TIMailData-Inline，安全事件，事件，ATP PowerShell，电子邮件恶意软件，已损坏的用户，电子邮件网络钓鱼诈骗，电子邮件恶意软件，读取电子邮件头，读取邮件头，打开电子邮件头
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
description: 了解如何使用威胁调查和响应功能查找和调查恶意电子邮件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 193b637236957bd0543be847be97169600367ddf
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656917"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="7f597-104">调查在 Office 365 中提供的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="7f597-104">Investigate malicious email that was delivered in Office 365</span></span>

<span data-ttu-id="7f597-105">[Office 365 高级威胁防护](office-365-atp.md)使您能够调查将组织中的人员面临风险的活动，并采取措施保护组织。</span><span class="sxs-lookup"><span data-stu-id="7f597-105">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="7f597-106">例如，如果您是组织的安全团队的一部分，则可以查找并调查已传递的可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-106">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="7f597-107">您可以使用[威胁资源管理器 (或) 的实时检测](threat-explorer.md)来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7f597-107">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7f597-108">请在[此处](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-21vianet&branch=pr-en-us-4258)跳转到修补文章。</span><span class="sxs-lookup"><span data-stu-id="7f597-108">Jump to the remediation article [here](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-21vianet&branch=pr-en-us-4258).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7f597-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="7f597-109">Before you begin</span></span>

<span data-ttu-id="7f597-110">请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="7f597-110">Make sure that the following requirements are met:</span></span>

- <span data-ttu-id="7f597-111">您的组织具有[Office 365 高级威胁防护](office-365-atp.md)，并将[许可证分配给用户](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="7f597-111">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) and [licenses are assigned to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

- <span data-ttu-id="7f597-112">为你的组织启用[审核日志记录](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="7f597-112">[audit logging](../../compliance/turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span>

- <span data-ttu-id="7f597-113">您的组织具有为反垃圾邮件、反恶意软件、反网络钓鱼等定义的策略。</span><span class="sxs-lookup"><span data-stu-id="7f597-113">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="7f597-114">请参阅防御[Office 365 中的威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="7f597-114">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="7f597-115">您是全局管理员，或者您具有安全管理员或在安全合规中心中分配的搜索和清除角色 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="7f597-115">You are a global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="7f597-116">查看[安全 &amp; 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7f597-116">See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="7f597-117">对于某些操作，还必须分配新的预览角色。</span><span class="sxs-lookup"><span data-stu-id="7f597-117">For some actions, you must also have a new Preview role assigned.</span></span>

### <a name="preview-role-permissions"></a><span data-ttu-id="7f597-118">预览角色权限</span><span class="sxs-lookup"><span data-stu-id="7f597-118">Preview role permissions</span></span>

<span data-ttu-id="7f597-119">若要执行某些操作（如查看邮件头或下载电子邮件内容），您必须具有一个名为*Preview*的新角色，并将其添加到另一个相应的角色组。</span><span class="sxs-lookup"><span data-stu-id="7f597-119">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate role group.</span></span> <span data-ttu-id="7f597-120">下表阐明了所需的角色和权限。</span><span class="sxs-lookup"><span data-stu-id="7f597-120">The following table clarifies required roles and permissions.</span></span>

****

|<span data-ttu-id="7f597-121">活动</span><span class="sxs-lookup"><span data-stu-id="7f597-121">Activity</span></span>|<span data-ttu-id="7f597-122">角色组</span><span class="sxs-lookup"><span data-stu-id="7f597-122">Role group</span></span>|<span data-ttu-id="7f597-123">是否需要预览角色？</span><span class="sxs-lookup"><span data-stu-id="7f597-123">Preview role needed?</span></span>|
|---|---|---|
|<span data-ttu-id="7f597-124">使用威胁资源管理器 (和实时检测) 分析威胁</span><span class="sxs-lookup"><span data-stu-id="7f597-124">Use Threat Explorer (and real-time detections) to analyze threats</span></span> |<span data-ttu-id="7f597-125">全局管理员</span><span class="sxs-lookup"><span data-stu-id="7f597-125">Global Administrator</span></span> <br> <span data-ttu-id="7f597-126">安全管理员</span><span class="sxs-lookup"><span data-stu-id="7f597-126">Security Administrator</span></span> <br> <span data-ttu-id="7f597-127">安全读取者</span><span class="sxs-lookup"><span data-stu-id="7f597-127">Security Reader</span></span>|<span data-ttu-id="7f597-128">否</span><span class="sxs-lookup"><span data-stu-id="7f597-128">No</span></span>|
|<span data-ttu-id="7f597-129">使用威胁资源管理器 (和实时检测) 查看电子邮件的邮件头以及预览和下载隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="7f597-129">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>|<span data-ttu-id="7f597-130">全局管理员</span><span class="sxs-lookup"><span data-stu-id="7f597-130">Global Administrator</span></span> <br> <span data-ttu-id="7f597-131">安全管理员</span><span class="sxs-lookup"><span data-stu-id="7f597-131">Security Administrator</span></span> <br><span data-ttu-id="7f597-132">安全读取者</span><span class="sxs-lookup"><span data-stu-id="7f597-132">Security Reader</span></span>|<span data-ttu-id="7f597-133">否</span><span class="sxs-lookup"><span data-stu-id="7f597-133">No</span></span>|
|<span data-ttu-id="7f597-134">使用威胁浏览器查看邮件头并下载传递给邮箱的电子邮件</span><span class="sxs-lookup"><span data-stu-id="7f597-134">Use Threat Explorer to view headers and download email messages delivered to mailboxes</span></span>|<span data-ttu-id="7f597-135">全局管理员</span><span class="sxs-lookup"><span data-stu-id="7f597-135">Global Administrator</span></span> <br><span data-ttu-id="7f597-136">安全管理员</span><span class="sxs-lookup"><span data-stu-id="7f597-136">Security Administrator</span></span> <br> <span data-ttu-id="7f597-137">安全读取者</span><span class="sxs-lookup"><span data-stu-id="7f597-137">Security Reader</span></span> <br> <span data-ttu-id="7f597-138">预览</span><span class="sxs-lookup"><span data-stu-id="7f597-138">Preview</span></span>|<span data-ttu-id="7f597-139">是</span><span class="sxs-lookup"><span data-stu-id="7f597-139">Yes</span></span>|
|

> [!NOTE]
> <span data-ttu-id="7f597-140">*预览*是一个角色，而不是角色组;必须将预览角色添加到 Office 365 的现有角色组中。</span><span class="sxs-lookup"><span data-stu-id="7f597-140">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365.</span></span> <span data-ttu-id="7f597-141">全局管理员角色分配有 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) ，并且安全管理员和安全读者角色在安全 & 合规性中心 () 中分配 [https://protection.office.com](https://protection.office.com) 。</span><span class="sxs-lookup"><span data-stu-id="7f597-141">The Global Administrator role is assigned the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)), and the Security Administrator and Security Reader roles are assigned in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="7f597-142">若要了解有关角色和权限的详细信息，请参阅[Security & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7f597-142">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="7f597-143">查找并删除已传递的可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="7f597-143">Find and delete suspicious email that was delivered</span></span>

<span data-ttu-id="7f597-144">威胁资源管理器是一种功能强大的报告，可用于多种用途，如查找和删除邮件、标识恶意电子邮件发件人的 IP 地址或启动事件以进行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="7f597-144">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="7f597-145">下面的过程重点介绍如何使用资源管理器查找和删除收件人邮箱中的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-145">The following procedure focuses on using Explorer to find and delete malicious email from recipient's mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="7f597-146">资源管理器中的默认搜索当前不包含 Zapped 项目。</span><span class="sxs-lookup"><span data-stu-id="7f597-146">Default searches in Explorer don't currently include Zapped items.</span></span>  <span data-ttu-id="7f597-147">这适用于所有视图，例如恶意软件或网络钓鱼视图。</span><span class="sxs-lookup"><span data-stu-id="7f597-147">This applies to all views, for example malware or phish views.</span></span> <span data-ttu-id="7f597-148">若要包含 Zapped 项，需要将 "传递操作" 设置为 "已删除的由 ZAP 删除"。</span><span class="sxs-lookup"><span data-stu-id="7f597-148">To include Zapped items you need to add a 'Delivery action' set to include 'Removed by ZAP'.</span></span> <span data-ttu-id="7f597-149">如果包含所有选项，您将看到所有传递操作结果，包括 Zapped 项目。</span><span class="sxs-lookup"><span data-stu-id="7f597-149">If you include all options, you'll see all delivery action results, including Zapped items.</span></span>

1. <span data-ttu-id="7f597-150">**导航到 "威胁资源管理器**"：转到 [https://protection.office.com](https://protection.office.com) 并使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="7f597-150">**Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="7f597-151">这会将您带到安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="7f597-151">This takes you to the Security &amp; Compliance Center.</span></span>

2. <span data-ttu-id="7f597-152">在左侧导航快速启动栏中，选择 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="7f597-152">In the left navigation quick-launch, choose **Threat management** \> **Explorer**.</span></span>

    ![具有 "传递操作" 和 "送达位置" 字段的资源管理器。](../../media/ThreatExFields.PNG)

    <!-- You may notice the new **Special actions** column. This feature is aimed at telling admins the outcome of processing an email. The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**. Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.-->

3. <span data-ttu-id="7f597-154">**威胁资源管理器中的视图**：在 "**视图**" 菜单中选择 "**所有电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="7f597-154">**Views in Threat Explorer**: In the **View** menu, choose **All email**.</span></span>

    ![威胁资源管理器视图菜单和电子邮件-恶意软件、网络钓鱼诈骗、提交和所有电子邮件选项，也是内容恶意软件。](../../media/tp-InvestigateMalEmail-viewmenu.png)

    <span data-ttu-id="7f597-156">*恶意软件*视图当前是默认的，并捕获检测到恶意软件威胁的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-156">The *Malware* view is currently the default, and captures emails where a malware threat is detected.</span></span> <span data-ttu-id="7f597-157">*网络钓鱼*视图的工作方式与网络钓鱼的操作方式相同。</span><span class="sxs-lookup"><span data-stu-id="7f597-157">The *Phish* view operates in the same way, for Phish.</span></span>

    <span data-ttu-id="7f597-158">但是，*所有的电子邮件视图都会*列出组织收到的每封邮件，无论是否检测到威胁。</span><span class="sxs-lookup"><span data-stu-id="7f597-158">However, *All email* view lists every mail received by the organization, whether threats were detected or not.</span></span> <span data-ttu-id="7f597-159">正如您所想到的，这是大量数据，这就是为什么此视图显示一个要求应用筛选器的占位符。</span><span class="sxs-lookup"><span data-stu-id="7f597-159">As you can imagine, this is a lot of data, which is why this view shows a placeholder that asks a filter be applied.</span></span> <span data-ttu-id="7f597-160"> (此视图仅适用于 ATP P2 客户。 ) </span><span class="sxs-lookup"><span data-stu-id="7f597-160">(This view is only available for ATP P2 customers.)</span></span>

    <span data-ttu-id="7f597-161">"*提交*" 视图显示由管理员或用户提交的、报告给 Microsoft 的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-161">*Submissions* view shows up all mails submitted by admin or user that were reported to Microsoft.</span></span>

4. <span data-ttu-id="7f597-162">**威胁资源管理器中的搜索和筛选**器：筛选器显示在搜索栏中页面的顶部，以帮助管理员进行调查。</span><span class="sxs-lookup"><span data-stu-id="7f597-162">**Search and filter in Threat Explorer**: Filters appear at the top of the page in the search bar to help admins in their investigations.</span></span> <span data-ttu-id="7f597-163">请注意，可以同时应用多个筛选器，添加筛选器中的多个逗号分隔值，以缩小搜索范围。</span><span class="sxs-lookup"><span data-stu-id="7f597-163">Notice that multiple filters can be applied at the same time, and multiple comma-separated values added to a filter to narrow down the search.</span></span> <span data-ttu-id="7f597-164">请注意：</span><span class="sxs-lookup"><span data-stu-id="7f597-164">Remember:</span></span>

    - <span data-ttu-id="7f597-165">筛选器对大多数筛选条件执行完全匹配。</span><span class="sxs-lookup"><span data-stu-id="7f597-165">Filters do exact matching on most filter conditions.</span></span>
    - <span data-ttu-id="7f597-166">Subject 筛选器使用 CONTAINS 查询。</span><span class="sxs-lookup"><span data-stu-id="7f597-166">Subject filter uses a CONTAINS query.</span></span>
    - <span data-ttu-id="7f597-167">URL 筛选器使用或不使用协议 (ex。</span><span class="sxs-lookup"><span data-stu-id="7f597-167">URL filters work with or without protocols (ex.</span></span> <span data-ttu-id="7f597-168">https) 。</span><span class="sxs-lookup"><span data-stu-id="7f597-168">https).</span></span>
    - <span data-ttu-id="7f597-169">URL 域、URL 路径以及 URL 域和路径筛选器不需要使用协议进行筛选。</span><span class="sxs-lookup"><span data-stu-id="7f597-169">URL domain, URL path, and URL domain and path filters don't require a protocol to filter.</span></span>
    - <span data-ttu-id="7f597-170">每次更改筛选值时，必须单击 "刷新" 图标以获取相关结果。</span><span class="sxs-lookup"><span data-stu-id="7f597-170">You must click the Refresh icon every time you change the filter values to get relevant results.</span></span>

5. <span data-ttu-id="7f597-171">**高级筛选器**：使用这些筛选器，可以生成复杂的查询和筛选数据集。</span><span class="sxs-lookup"><span data-stu-id="7f597-171">**Advanced filters**: With these filters, you can build complex queries and filter your data set.</span></span> <span data-ttu-id="7f597-172">单击 "*高级" 筛选器*将打开带选项的浮出控件。</span><span class="sxs-lookup"><span data-stu-id="7f597-172">Clicking on *Advanced Filters* opens a flyout with options.</span></span>

   <span data-ttu-id="7f597-173">高级筛选是搜索功能的一个极好的补充。</span><span class="sxs-lookup"><span data-stu-id="7f597-173">Advanced filtering is a great addition to search capabilities.</span></span> <span data-ttu-id="7f597-174">*收件人*、*发件人*和*发件人域*中引入了 boolean **NOT** filter，以允许管理员通过排除值来进行调查。</span><span class="sxs-lookup"><span data-stu-id="7f597-174">A boolean **NOT** filter has been introduced on *Recipient*, *Sender* and *Sender domain* to allow admins to investigate by excluding values.</span></span> <span data-ttu-id="7f597-175">此选项显示在 "选择参数不*包含任何*"。</span><span class="sxs-lookup"><span data-stu-id="7f597-175">This option appears under selection parameter *Contains none of*.</span></span> <span data-ttu-id="7f597-176">[！注意]**不**允许管理员排除警报邮箱、默认的答复邮箱的调查，并在管理员搜索特定主题 (主题 = "注意" ) （可将收件人设置为*defaultMail \@ contoso.com）的*情况下很有用。</span><span class="sxs-lookup"><span data-stu-id="7f597-176">**NOT** will let admins exclude alert mailboxes, default reply mailboxes from their investigations, and is useful for cases where admins search for a specific subject (subject="Attention") where the Recipient can be set to *none of defaultMail\@contoso.com*.</span></span> <span data-ttu-id="7f597-177">这是精确的值搜索。</span><span class="sxs-lookup"><span data-stu-id="7f597-177">This is an exact value search.</span></span>

   ![收件人-"不包含任何" 高级筛选器。](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   <span data-ttu-id="7f597-179">*按小时筛选*可帮助贵组织的安全团队快速向下钻取。</span><span class="sxs-lookup"><span data-stu-id="7f597-179">*Filtering by hours* will help your organization's security team drill down quickly.</span></span> <span data-ttu-id="7f597-180">允许的最短持续时间为30分钟。</span><span class="sxs-lookup"><span data-stu-id="7f597-180">The shortest allowed time duration is 30 minutes.</span></span> <span data-ttu-id="7f597-181">如果可以根据时间帧缩小可疑操作 (例如，在3小时前) ，这将限制上下文并帮助查明问题。</span><span class="sxs-lookup"><span data-stu-id="7f597-181">If you can narrow the suspicious action by time-frame (e.g. it happened 3 hours ago), this will limit the context and help pinpoint the problem.</span></span>

   ![按小时筛选选项，以缩小数据安全团队的处理量，并且其最短持续时间为30分钟。](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. <span data-ttu-id="7f597-183">**威胁资源管理器中的字段**：威胁浏览器会公开更多与安全性相关的邮件信息，例如*传递操作*、*传递位置*、*特殊操作*、*方向*性、*覆盖*和*URL 威胁*。</span><span class="sxs-lookup"><span data-stu-id="7f597-183">**Fields in threat explorer**: Threat Explorer exposes a lot more security-related mail information such as *Delivery action*, *Delivery location*, *Special action*, *Directionality*, *Overrides*, and *URL threat*.</span></span> <span data-ttu-id="7f597-184">它还允许组织的安全团队以更高确定性进行调查。</span><span class="sxs-lookup"><span data-stu-id="7f597-184">It also allows your organization's security team to investigate with a higher certainty.</span></span>

    <span data-ttu-id="7f597-185">*传递操作*是由于现有策略或检测而导致对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7f597-185">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="7f597-186">以下是电子邮件可能执行的操作：</span><span class="sxs-lookup"><span data-stu-id="7f597-186">Here are the possible actions an email can take:</span></span>

    - <span data-ttu-id="7f597-187">**传递**–将电子邮件传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="7f597-187">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
    - <span data-ttu-id="7f597-188">**Junked** (传递到垃圾) –将电子邮件发送到用户的垃圾邮件文件夹或已删除的文件夹，并且用户可以访问其垃圾邮件或已删除文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-188">**Junked** (Delivered to junk)– email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>
    - <span data-ttu-id="7f597-189">已**阻止**–隔离、失败或丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-189">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="7f597-190"> (完全无法被用户访问。 ) </span><span class="sxs-lookup"><span data-stu-id="7f597-190">(This is completely inaccessible by the user.)</span></span>
    - <span data-ttu-id="7f597-191">**已替换**–所有恶意附件替换为 .txt 文件的电子邮件，这些文件的状态为 "恶意附件"。</span><span class="sxs-lookup"><span data-stu-id="7f597-191">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious</span></span>

    <span data-ttu-id="7f597-192">**送达位置**：提供了传递位置筛选器，以便帮助管理员了解可疑的恶意邮件结束的位置以及对它执行了哪些操作。</span><span class="sxs-lookup"><span data-stu-id="7f597-192">**Delivery location**: The Delivery location filter is available in order to help admins understand where suspected malicious mail ended-up and what actions were taken on it.</span></span> <span data-ttu-id="7f597-193">可将生成的数据导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="7f597-193">The resulting data can be exported to spreadsheet.</span></span> <span data-ttu-id="7f597-194">可能的送达位置为：</span><span class="sxs-lookup"><span data-stu-id="7f597-194">Possible delivery locations are:</span></span>

    - <span data-ttu-id="7f597-195">**收件箱或文件夹**–电子邮件位于收件箱中或特定文件夹中，具体取决于您的电子邮件规则。</span><span class="sxs-lookup"><span data-stu-id="7f597-195">**Inbox or folder** – The email is in the Inbox or a specific folder, according to your email rules.</span></span>
    - <span data-ttu-id="7f597-196">**本地或外部**–邮箱在云中不存在，但在本地。</span><span class="sxs-lookup"><span data-stu-id="7f597-196">**On-prem or external** – The mailbox doesn't exist in the Cloud but is on-premises.</span></span>
    - <span data-ttu-id="7f597-197">**垃圾邮件文件夹**–电子邮件位于用户的垃圾邮件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7f597-197">**Junk folder** – The email is in a user's Junk mail folder.</span></span>
    - <span data-ttu-id="7f597-198">"**已删除邮件" 文件夹**–电子邮件位于用户的 "已删除邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7f597-198">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>
    - <span data-ttu-id="7f597-199">**隔离**–隔离的电子邮件，而不是用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-199">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>
    - <span data-ttu-id="7f597-200">**失败**–电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="7f597-200">**Failed** – The email failed to reach the mailbox.</span></span>
    - <span data-ttu-id="7f597-201">**丢弃**–电子邮件在邮件流中的某处丢失。</span><span class="sxs-lookup"><span data-stu-id="7f597-201">**Dropped** – The email was lost somewhere in the mail flow.</span></span>

    <span data-ttu-id="7f597-202">**方向**性：此选项允许安全操作团队按邮件发件人的 "方向" 进行筛选或进行筛选。</span><span class="sxs-lookup"><span data-stu-id="7f597-202">**Directionality**: This option allows your security operations team to filter by the 'direction' a mail comes from, or is going.</span></span> <span data-ttu-id="7f597-203">方向性值为*入站*、*出站*和*组织内* (对应于从外部传入的邮件、从您的组织中发送或在内部发送到您的组织中的邮件，分别) 。</span><span class="sxs-lookup"><span data-stu-id="7f597-203">Directionality values are *Inbound*, *Outbound*, and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively).</span></span> <span data-ttu-id="7f597-204">此信息可帮助安全操作团队发现欺骗和模拟，因为方向性值之间不匹配 (ex。</span><span class="sxs-lookup"><span data-stu-id="7f597-204">This information can help security operations teams spot spoofing and impersonation, because a mismatch between the Directionality value (ex.</span></span> <span data-ttu-id="7f597-205">*入站*) 和发件人的域 (（*似乎*是内部域) 将很明显！</span><span class="sxs-lookup"><span data-stu-id="7f597-205">*Inbound*), and the domain of the sender (which *appears* to be an internal domain) will be evident!</span></span> <span data-ttu-id="7f597-206">方向性值是相互独立的，并且可以与邮件跟踪不同。</span><span class="sxs-lookup"><span data-stu-id="7f597-206">The Directionality value is separate, and can differ from, the Message Trace.</span></span> <span data-ttu-id="7f597-207">可将结果导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="7f597-207">Results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="7f597-208">**替代**：此筛选器获取邮件的 "详细信息" 选项卡上显示的信息，并使用它来公开允许和阻止邮件的组织或用户策略被*覆盖*的位置。</span><span class="sxs-lookup"><span data-stu-id="7f597-208">**Overrides**: This filter takes information that appears on the mail's details tab and uses it to expose where organizational, or user policies, for allowing and blocking mails have been *overridden*.</span></span> <span data-ttu-id="7f597-209">此筛选器最重要的一点是，它可以帮助组织的安全团队查看由于配置而传递了多少可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-209">The most important thing about this filter is that it helps your organization's security team see how many suspicious emails were delivered due to configuration.</span></span> <span data-ttu-id="7f597-210">这使他们有机会根据需要修改 "允许" 和 "阻止"。</span><span class="sxs-lookup"><span data-stu-id="7f597-210">This gives them an opportunity to modify allows and blocks as needed.</span></span> <span data-ttu-id="7f597-211">可以将此筛选器的结果集导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="7f597-211">This result set of this filter can be exported to spreadsheet.</span></span>

    ****

    |<span data-ttu-id="7f597-212">威胁资源管理器替代</span><span class="sxs-lookup"><span data-stu-id="7f597-212">Threat Explorer Overrides</span></span>|<span data-ttu-id="7f597-213">它们的含义</span><span class="sxs-lookup"><span data-stu-id="7f597-213">What they mean</span></span>|
    |---|---|
    |<span data-ttu-id="7f597-214">组织策略允许</span><span class="sxs-lookup"><span data-stu-id="7f597-214">Allowed by Org Policy</span></span>|<span data-ttu-id="7f597-215">按组织策略的指示，允许在邮箱中发送邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-215">Mail was allowed into the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="7f597-216">已被组织策略阻止</span><span class="sxs-lookup"><span data-stu-id="7f597-216">Blocked by Org policy</span></span>|<span data-ttu-id="7f597-217">邮件被阻止按照组织策略的指示将邮件传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="7f597-217">Mail was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="7f597-218">组织策略阻止的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="7f597-218">File extension blocked by Org Policy</span></span>|<span data-ttu-id="7f597-219">根据组织策略的指示，文件被阻止传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="7f597-219">File was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="7f597-220">用户策略允许</span><span class="sxs-lookup"><span data-stu-id="7f597-220">Allowed by User Policy</span></span>|<span data-ttu-id="7f597-221">用户策略允许在邮箱中发送邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-221">Mail was allowed into the mailbox as directed by the user policy.</span></span>|
    |<span data-ttu-id="7f597-222">被用户策略阻止</span><span class="sxs-lookup"><span data-stu-id="7f597-222">Blocked by User Policy</span></span>|<span data-ttu-id="7f597-223">阻止邮件按照用户策略的指导将邮件传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="7f597-223">Mail was blocked from delivery to the mailbox as directed by the user policy.</span></span>|
    |

    <span data-ttu-id="7f597-224">**Url 威胁**： "url 威胁" 字段已包含在电子邮件的 "*详细信息*" 选项卡上，用于指示 URL 所呈现的威胁。</span><span class="sxs-lookup"><span data-stu-id="7f597-224">**URL threat**: The URL threat field has been included on the *details* tab of an email to indicate the threat presented by a URL.</span></span> <span data-ttu-id="7f597-225">URL 表现的威胁可以包含*恶意软件*、*网络钓鱼*或*垃圾邮件*，而威胁部分中不会显示*任何\*\*威胁*的 url。</span><span class="sxs-lookup"><span data-stu-id="7f597-225">Threats presented by a URL can include *Malware*, *Phish*, or *Spam*, and a URL with *no threat* will say *None* in the threats section.</span></span>

7. <span data-ttu-id="7f597-226">**电子邮件日程表视图**：安全操作团队可能需要深入研究电子邮件详细信息，以便进一步调查。</span><span class="sxs-lookup"><span data-stu-id="7f597-226">**Email timeline view**: Your security operations team might need to deep-dive into email details to investigate further.</span></span> <span data-ttu-id="7f597-227">通过电子邮件时间线，管理员可以查看从传递到送达后对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7f597-227">The email timeline allows admins to view actions taken on an email from delivery to post-delivery.</span></span> <span data-ttu-id="7f597-228">若要查看电子邮件日程表，请单击电子邮件的主题，然后单击 "电子邮件日程表"。</span><span class="sxs-lookup"><span data-stu-id="7f597-228">To view an email timeline, click on the subject of an email message, and then click Email timeline.</span></span> <span data-ttu-id="7f597-229"> (它显示在面板上的其他标题中，如摘要或详细信息。 ) 可以将这些结果导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="7f597-229">(It appears among other headings on the panel like Summary or Details.) These results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="7f597-230">电子邮件日程表将打开，其中显示电子邮件的所有送达和传递后事件的表格。</span><span class="sxs-lookup"><span data-stu-id="7f597-230">Email timeline will open to a table that shows all delivery and post-delivery events for the email.</span></span> <span data-ttu-id="7f597-231">如果对电子邮件没有进一步的操作，您应该会看到原始传递的单个事件，其中指出了结果（如*网络钓鱼*）的结论，如 "已*阻止*"。</span><span class="sxs-lookup"><span data-stu-id="7f597-231">If there are no further actions on the email, you should see a single event for the original delivery that states a result, such as *Blocked*, with a verdict like *Phish*.</span></span> <span data-ttu-id="7f597-232">管理员可以导出整个电子邮件时间线，包括选项卡和电子邮件 (的所有详细信息，如 "主题"、"发件人"、"收件人"、"网络" 和 "邮件 ID") 。</span><span class="sxs-lookup"><span data-stu-id="7f597-232">Admins can export the entire email timeline, including all details on the tab and email (such as, Subject, Sender, Recipient, Network, and Message ID).</span></span> <span data-ttu-id="7f597-233">电子邮件日程表在随机时减少，因为检查不同位置的时间较少，以尝试了解自电子邮件到达后发生的事件。</span><span class="sxs-lookup"><span data-stu-id="7f597-233">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="7f597-234">当电子邮件上的多个事件发生时，或在同一时间结束时，这些事件将显示在 "日程表" 视图中。</span><span class="sxs-lookup"><span data-stu-id="7f597-234">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span>

8. <span data-ttu-id="7f597-235">**预览/下载**：威胁资源管理器为安全操作团队提供调查可疑电子邮件所需的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7f597-235">**Preview / download**: Threat Explorer gives your security operations team the details they need to investigate suspicious email.</span></span> <span data-ttu-id="7f597-236">您的安全操作团队可以执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="7f597-236">Your security operations team can either:</span></span>

    - <span data-ttu-id="7f597-237">[检查传递操作和位置](#check-the-delivery-action-and-location)。</span><span class="sxs-lookup"><span data-stu-id="7f597-237">[Check the delivery action and location](#check-the-delivery-action-and-location).</span></span>

    - <span data-ttu-id="7f597-238">[查看你的电子邮件的日程表](#view-the-timeline-of-your-email)。</span><span class="sxs-lookup"><span data-stu-id="7f597-238">[View the timeline of your email](#view-the-timeline-of-your-email).</span></span>

### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="7f597-239">检查传递操作和位置</span><span class="sxs-lookup"><span data-stu-id="7f597-239">Check the delivery action and location</span></span>

<span data-ttu-id="7f597-240">在[威胁资源管理器中 (和实时检测) ](threat-explorer.md)，现在您有 "**传递操作**" 和 "**传递位置**" 列，而不是以前的 "**传递状态**" 列。</span><span class="sxs-lookup"><span data-stu-id="7f597-240">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="7f597-241">这将导致您的电子邮件位于何处的更完整的图片。</span><span class="sxs-lookup"><span data-stu-id="7f597-241">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="7f597-242">此更改的目标部分是使调查更易于进行安全操作团队，但最终结果是了解问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="7f597-242">Part of the goal of this change is to make investigations easier for security operations teams, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="7f597-243">传递状态现已分为两列：</span><span class="sxs-lookup"><span data-stu-id="7f597-243">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="7f597-244">**传递操作**-此电子邮件的状态是什么？</span><span class="sxs-lookup"><span data-stu-id="7f597-244">**Delivery action** - What is the status of this email?</span></span>

- <span data-ttu-id="7f597-245">**送达位置**-此电子邮件的路由结果</span><span class="sxs-lookup"><span data-stu-id="7f597-245">**Delivery location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="7f597-246">传递操作是由于现有策略或检测而导致对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7f597-246">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="7f597-247">以下是电子邮件可能执行的操作：</span><span class="sxs-lookup"><span data-stu-id="7f597-247">Here are the possible actions an email can take:</span></span>

- <span data-ttu-id="7f597-248">**传递**–将电子邮件传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="7f597-248">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

- <span data-ttu-id="7f597-249">**Junked** –将电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹，并且用户可以访问其 "垃圾邮件" 或 "已删除" 文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-249">**Junked** – email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

- <span data-ttu-id="7f597-250">已**阻止**–隔离、失败或丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-250">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="7f597-251"> (完全无法被用户访问。 ) </span><span class="sxs-lookup"><span data-stu-id="7f597-251">(This is completely inaccessible by the user.)</span></span>

- <span data-ttu-id="7f597-252">**已替换**–所有恶意附件都被替换为 .txt 文件的电子邮件，这些文件的状态为 "恶意附件"。</span><span class="sxs-lookup"><span data-stu-id="7f597-252">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>

<span data-ttu-id="7f597-253">"送达位置" 显示运行送达后的策略和检测结果。</span><span class="sxs-lookup"><span data-stu-id="7f597-253">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="7f597-254">它已链接到传递操作。</span><span class="sxs-lookup"><span data-stu-id="7f597-254">It's linked to a Delivery Action.</span></span> <span data-ttu-id="7f597-255">添加此字段是为了深入了解在发现问题邮件时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="7f597-255">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="7f597-256">以下是送达位置的可能值：</span><span class="sxs-lookup"><span data-stu-id="7f597-256">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="7f597-257">**收件箱或文件夹**–电子邮件位于收件箱中或文件夹 (根据您的电子邮件规则) 。</span><span class="sxs-lookup"><span data-stu-id="7f597-257">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

- <span data-ttu-id="7f597-258">**本地或外部**–邮箱在云上不存在，但在本地。</span><span class="sxs-lookup"><span data-stu-id="7f597-258">**On-prem or external** – The mailbox doesn't exist on cloud but is on-premises.</span></span>

- <span data-ttu-id="7f597-259">**垃圾邮件文件夹**–电子邮件位于用户的垃圾邮件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7f597-259">**Junk folder** – The email is in a user's Junk folder.</span></span>

- <span data-ttu-id="7f597-260">"**已删除邮件" 文件夹**–电子邮件位于用户的 "已删除邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7f597-260">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

- <span data-ttu-id="7f597-261">**隔离**–隔离的电子邮件，而不是用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7f597-261">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>

- <span data-ttu-id="7f597-262">**失败**–电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="7f597-262">**Failed** – The email failed to reach the mailbox.</span></span>

- <span data-ttu-id="7f597-263">**丢弃**–电子邮件在邮件流中的某个位置丢失。</span><span class="sxs-lookup"><span data-stu-id="7f597-263">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="7f597-264">查看你的电子邮件的日程表</span><span class="sxs-lookup"><span data-stu-id="7f597-264">View the timeline of your email</span></span>

<span data-ttu-id="7f597-265">**电子邮件日程表**是威胁资源管理器中的一个字段，可使您的安全操作团队更轻松地使用查找。</span><span class="sxs-lookup"><span data-stu-id="7f597-265">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="7f597-266">当电子邮件上的多个事件同时发生或在同一时间结束时，这些事件将显示在 "日程表" 视图中。</span><span class="sxs-lookup"><span data-stu-id="7f597-266">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="7f597-267">在 "**特殊操作**" 列中捕获到电子邮件的传递后发生的一些事件。</span><span class="sxs-lookup"><span data-stu-id="7f597-267">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="7f597-268">将电子邮件的时间线中的信息与在传递后进行的任何特殊操作组合在一起，管理员可以深入了解策略和威胁处理 (例如邮件路由的位置，在某些情况下，) 最终评估。</span><span class="sxs-lookup"><span data-stu-id="7f597-268">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f597-269">请在[此处](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-worldwide)跳转到修正主题。</span><span class="sxs-lookup"><span data-stu-id="7f597-269">Jump to a remediation topic [here](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-worldwide).</span></span>

<!-- Reference material

1. **Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center.

2. In the left navigation quick-launch, choose **Threat management** \> **Explorer**.

3. Click on the subject of an email message, and then click **Email timeline**. (It appears among other headings on the panel like **Summary** or **Details**.)

    Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail. In the case of no further events for the email, you should see a single event for the original delivery that states a result like **Blocked** with a verdict like **Phish**. The tab also has the option to export the entire email timeline, and this exports all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).

    The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived. When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.

    Some events that happen post-delivery to your mail are captured in the **Special actions** column. Combining the information from the email timeline along with special actions taken on email post-delivery gives admins insight into how their policies work, where the email was finally routed, and, in some cases, what the final assessment was.

4. In the **View** menu, choose **All email**.

    ![Use the View menu to choose between Email and Content reports](../../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)

    Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.

    ![Threat Explorer showing data for all email](../../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)

    (Depending on the actions that were taken on email messages for your organization, you might see other labels, such as **Blocked** or **Replaced**.)

5. In the report, choose **Delivered** to view only email messages that ended up in users' inboxes.

    ![Clicking "Delivered to junk" removes that data from view](../../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)

6. Below the chart, review the **Email** list below the chart.

    ![Below the chart, view a list of email messages that were detected](../../media/dfb60590-1236-499d-97da-86c68621e2bc.png)

7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.

    ![You can view additional information about an item](../../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)

8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.

9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This deletes the selected messages from the recipients' mailboxes.

    ![When you select one or more email messages, you can choose from several available actions](../../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## Dealing with suspicious email messages

Malicious attackers might be sending mail to people in your organization in an attempt to phish their credentials and gain access to your corporate secrets. To help prevent this, you use the threat protection services in Office 365, including [Exchange Online Protection](exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md). However, it occasionally happens that an attacker sends email that contains a link (URL) that only later points to malicious content (such as malware). Or, you might realize too late that someone in your organization has been compromised, and while they were compromised, an attacker used their account to send email to other people in your organization. As part of dealing with either of these scenarios, you can remove suspicious email messages from user inboxes. To do that, you can use [Threat Explorer](threat-explorer.md).

## Finding re-routed email messages after actions are taken

Threat Explorer provides your security operations team with the details they need to investigate suspicious email. Your security operations team can:

- [View the email headers and download the email body](#view-the-email-headers-and-download-the-email-body)

- [Check the delivery action and location](#check-the-delivery-action-and-location)

- [View the timeline of your email](#view-the-timeline-of-your-email)

### View the email headers and download the email body

The ability to preview email headers and download the body of an email body are powerful capabilities in Threat Explorer. Appropriate [permissions](permissions-in-the-security-and-compliance-center.md) must be assigned. See [Preview role permissions](#preview-role-permissions).

To access your message header and email download options, follow these steps:

1. Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center.

2. In the left navigation, choose **Threat management** \> **Explorer**.

3. Click on a subject in the Threat Explorer table.

    This opens the flyout, where both header preview and email download links are positioned.

    ![Threat Explorer flyout with download and preview links on the page.](../../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> This capability doesn't show up for email messages that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed. In cases where email messages were deleted from users' mailboxes, admins see a "Mail not found" error message.
-->

## <a name="related-topics"></a><span data-ttu-id="7f597-270">相关主题</span><span class="sxs-lookup"><span data-stu-id="7f597-270">Related topics</span></span>

[<span data-ttu-id="7f597-271">修正在 Office 365 中传递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="7f597-271">Remediate malicious email delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-worldwide)

[<span data-ttu-id="7f597-272">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="7f597-272">Office 365 Advanced Threat Protection</span></span>](office-365-ti.md)

[<span data-ttu-id="7f597-273">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="7f597-273">Protect against threats in Office 365</span></span>](protect-against-threats.md)

[<span data-ttu-id="7f597-274">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="7f597-274">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
