---
title: 查找并调查 Office 365 中提供的恶意电子邮件、补救措施、补救措施、修正、威胁防护、威胁浏览器、保护
keywords: TIMailData-Inline，安全事件，事件，ATP PowerShell，电子邮件恶意软件，已损坏的用户，电子邮件网络钓鱼诈骗，电子邮件恶意软件，读取电子邮件头，读取邮件头，打开电子邮件头
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
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 了解如何使用威胁调查和响应功能查找和调查恶意电子邮件。
ms.openlocfilehash: 1b7cef7f079023dd88fe3f04eb1b7d159c4157ef
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955611"
---
# <a name="investigate-and-remediate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="7d0f2-104">调查并修正在 Office 365 中提供的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="7d0f2-104">Investigate and remediate malicious email that was delivered in Office 365</span></span>

<span data-ttu-id="7d0f2-105">[Office 365 高级威胁防护](office-365-atp.md)使您能够调查将组织中的人员面临风险的活动，并采取措施保护组织。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-105">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="7d0f2-106">例如，如果您是组织的安全团队的一部分，则可以查找并调查已传递的可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-106">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="7d0f2-107">可以使用[威胁资源管理器（或实时检测）](threat-explorer.md)执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-107">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="7d0f2-108">开始之前...</span><span class="sxs-lookup"><span data-stu-id="7d0f2-108">Before you begin...</span></span>

<span data-ttu-id="7d0f2-109">请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="7d0f2-109">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="7d0f2-110">您的组织具有[Office 365 高级威胁防护](office-365-atp.md)，并将[许可证分配给用户](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-110">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) and [licenses are assigned to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
    
- <span data-ttu-id="7d0f2-111">为你的组织启用了[Office 365 审核日志记录](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-111">[Office 365 audit logging](../../compliance/turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="7d0f2-112">您的组织具有为反垃圾邮件、反恶意软件、反网络钓鱼等定义的策略。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-112">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="7d0f2-113">请参阅防御[Office 365 中的威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-113">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="7d0f2-114">您是 Office 365 全局管理员，或者您具有安全管理员或在安全&amp;合规中心中分配的搜索和清除角色。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-114">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="7d0f2-115">请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-115">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="7d0f2-116">对于某些操作，还必须分配新的预览角色。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-116">For some actions, you must also have a new Preview role assigned.</span></span> 

#### <a name="preview-role-permissions"></a><span data-ttu-id="7d0f2-117">预览角色权限</span><span class="sxs-lookup"><span data-stu-id="7d0f2-117">Preview role permissions</span></span>

<span data-ttu-id="7d0f2-118">若要执行某些操作（如查看邮件头或下载电子邮件内容），您必须具有一个名为*Preview*的新角色，并将其添加到另一个相应的 Office 365 角色组。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-118">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate Office 365 role group.</span></span> <span data-ttu-id="7d0f2-119">下表阐明了所需的角色和权限。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-119">The following table clarifies required roles and permissions.</span></span>

|<span data-ttu-id="7d0f2-120">活动</span><span class="sxs-lookup"><span data-stu-id="7d0f2-120">Activity</span></span>  |<span data-ttu-id="7d0f2-121">角色组</span><span class="sxs-lookup"><span data-stu-id="7d0f2-121">Role group</span></span> |<span data-ttu-id="7d0f2-122">是否需要预览角色？</span><span class="sxs-lookup"><span data-stu-id="7d0f2-122">Preview role needed?</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7d0f2-123">使用威胁浏览器（和实时检测）分析威胁</span><span class="sxs-lookup"><span data-stu-id="7d0f2-123">Use Threat Explorer (and real-time detections) to analyze threats</span></span>     |<span data-ttu-id="7d0f2-124">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="7d0f2-124">Office 365 Global Administrator</span></span> <br> <span data-ttu-id="7d0f2-125">安全管理员</span><span class="sxs-lookup"><span data-stu-id="7d0f2-125">Security Administrator</span></span> <br> <span data-ttu-id="7d0f2-126">安全读取者</span><span class="sxs-lookup"><span data-stu-id="7d0f2-126">Security Reader</span></span>     | <span data-ttu-id="7d0f2-127">否</span><span class="sxs-lookup"><span data-stu-id="7d0f2-127">No</span></span>   |
|<span data-ttu-id="7d0f2-128">使用威胁资源管理器（和实时检测）查看电子邮件的邮件头，以及预览和下载隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="7d0f2-128">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>    |<span data-ttu-id="7d0f2-129">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="7d0f2-129">Office 365 Global Administrator</span></span> <br> <span data-ttu-id="7d0f2-130">安全管理员</span><span class="sxs-lookup"><span data-stu-id="7d0f2-130">Security Administrator</span></span> <br><span data-ttu-id="7d0f2-131">安全读取者</span><span class="sxs-lookup"><span data-stu-id="7d0f2-131">Security Reader</span></span>   |       <span data-ttu-id="7d0f2-132">否</span><span class="sxs-lookup"><span data-stu-id="7d0f2-132">No</span></span>  |
|<span data-ttu-id="7d0f2-133">使用威胁浏览器查看邮件头并下载传递给邮箱的电子邮件</span><span class="sxs-lookup"><span data-stu-id="7d0f2-133">Use Threat Explorer to view headers and download email messages delivered to mailboxes</span></span>     |<span data-ttu-id="7d0f2-134">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="7d0f2-134">Office 365 Global Administrator</span></span> <br><span data-ttu-id="7d0f2-135">安全管理员</span><span class="sxs-lookup"><span data-stu-id="7d0f2-135">Security Administrator</span></span> <br> <span data-ttu-id="7d0f2-136">安全读取者</span><span class="sxs-lookup"><span data-stu-id="7d0f2-136">Security Reader</span></span> <br> <span data-ttu-id="7d0f2-137">预览</span><span class="sxs-lookup"><span data-stu-id="7d0f2-137">Preview</span></span>   |   <span data-ttu-id="7d0f2-138">是</span><span class="sxs-lookup"><span data-stu-id="7d0f2-138">Yes</span></span>      |

> [!NOTE]
> <span data-ttu-id="7d0f2-139">*预览*是一个角色，而不是角色组;必须将预览角色添加到 Office 365 的现有角色组中。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-139">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365.</span></span> <span data-ttu-id="7d0f2-140">Office 365 全局管理员角色分配有 Microsoft 365 管理中心（[https://admin.microsoft.com](https://admin.microsoft.com)），安全管理员和安全读者角色是在 Office 365 安全 & 合规中心（[https://protection.office.com](https://protection.office.com)）中分配的。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-140">The Office 365 Global Administrator role is assigned the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)), and the Security Administrator and Security Reader roles are assigned in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="7d0f2-141">若要了解有关角色和权限的详细信息，请参阅[Office 365 Security & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-141">To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="7d0f2-142">查找并删除已传递的可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="7d0f2-142">Find and delete suspicious email that was delivered</span></span>

<span data-ttu-id="7d0f2-143">威胁资源管理器是一种功能强大的报告，可用于多种用途，如查找和删除邮件、标识恶意电子邮件发件人的 IP 地址或启动事件以进行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-143">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="7d0f2-144">下面的过程重点介绍如何使用资源管理器查找和删除收件人邮箱中的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-144">The following procedure focuses on using Explorer to find and delete malicious email from recipient's mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="7d0f2-145">资源管理器中的默认搜索当前不包含 Zapped 项目。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-145">Default searches in Explorer don't currently include Zapped items.</span></span>  <span data-ttu-id="7d0f2-146">这适用于所有视图，例如恶意软件或网络钓鱼视图。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-146">This applies to all views, for example malware or phish views.</span></span> <span data-ttu-id="7d0f2-147">若要包含 Zapped 项，需要将 "传递操作" 设置为 "已删除的由 ZAP 删除"。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-147">To include Zapped items you need to add a 'Delivery action' set to include 'Removed by ZAP'.</span></span> <span data-ttu-id="7d0f2-148">如果包含所有选项，您将看到所有传递操作结果，包括 Zapped 项目。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-148">If you include all options, you'll see all delivery action results, including Zapped items.</span></span>

1. <span data-ttu-id="7d0f2-149">**导航到 "威胁资源管理器**"：转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-149">**Navigate to Threat Explorer**: Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="7d0f2-150">这会将您带到&amp;安全合规中心。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-150">This takes you to the Security &amp; Compliance Center.</span></span>

2. <span data-ttu-id="7d0f2-151">在左侧导航快速启动栏中，选择 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-151">In the left navigation quick-launch, choose **Threat management** \> **Explorer**.</span></span>

    ![具有 "传递操作" 和 "送达位置" 字段的资源管理器。](../../media/ThreatExFields.PNG)

    <!-- You may notice the new **Special actions** column. This feature is aimed at telling admins the outcome of processing an email. The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**. Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.-->

3. <span data-ttu-id="7d0f2-153">**威胁资源管理器中的视图**：在 "**视图**" 菜单中选择 "**所有电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-153">**Views in Threat Explorer**: In the **View** menu, choose **All email**.</span></span>

    ![威胁资源管理器视图菜单和电子邮件-恶意软件、网络钓鱼诈骗、提交和所有电子邮件选项，也是内容恶意软件。](../../media/tp-InvestigateMalEmail-viewmenu.png)

    <span data-ttu-id="7d0f2-155">*恶意软件*视图当前是默认的，并捕获检测到恶意软件威胁的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-155">The *Malware* view is currently the default, and captures emails where a malware threat is detected.</span></span> <span data-ttu-id="7d0f2-156">*网络钓鱼*视图的工作方式与网络钓鱼的操作方式相同。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-156">The *Phish* view operates in the same way, for Phish.</span></span>

    <span data-ttu-id="7d0f2-157">但是，*所有的电子邮件视图都会*列出组织收到的每封邮件，无论是否检测到威胁。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-157">However, *All email* view lists every mail received by the organization, whether threats were detected or not.</span></span> <span data-ttu-id="7d0f2-158">正如您所想到的，这是大量数据，这就是为什么此视图显示一个要求应用筛选器的占位符。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-158">As you can imagine, this is a lot of data, which is why this view shows a placeholder that asks a filter be applied.</span></span> <span data-ttu-id="7d0f2-159">（此视图仅适用于 ATP P2 客户。）</span><span class="sxs-lookup"><span data-stu-id="7d0f2-159">(This view is only available for ATP P2 customers.)</span></span>

    <span data-ttu-id="7d0f2-160">"*提交*" 视图显示由管理员或用户提交的、报告给 Microsoft 的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-160">*Submissions* view shows up all mails submitted by admin or user that were reported to Microsoft.</span></span>

4. <span data-ttu-id="7d0f2-161">**威胁资源管理器中的搜索和筛选**器：筛选器显示在搜索栏中页面的顶部，以帮助管理员进行调查。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-161">**Search and filter in Threat Explorer**: Filters appear at the top of the page in the search bar to help admins in their investigations.</span></span> <span data-ttu-id="7d0f2-162">请注意，可以同时应用多个筛选器，添加筛选器中的多个逗号分隔值，以缩小搜索范围。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-162">Notice that multiple filters can be applied at the same time, and multiple comma-separated values added to a filter to narrow down the search.</span></span> <span data-ttu-id="7d0f2-163">请注意：</span><span class="sxs-lookup"><span data-stu-id="7d0f2-163">Remember:</span></span>
    - <span data-ttu-id="7d0f2-164">筛选器对大多数筛选条件执行完全匹配。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-164">Filters do exact matching on most filter conditions.</span></span>
    - <span data-ttu-id="7d0f2-165">Subject 筛选器使用 CONTAINS 查询。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-165">Subject filter uses a CONTAINS query.</span></span>
    - <span data-ttu-id="7d0f2-166">URL 筛选器使用或不使用协议（ex）。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-166">URL filters work with or without protocols (ex.</span></span> <span data-ttu-id="7d0f2-167">https）。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-167">https).</span></span>
    - <span data-ttu-id="7d0f2-168">URL 域、URL 路径以及 URL 域和路径筛选器不需要使用协议进行筛选。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-168">URL domain, URL path, and URL domain and path filters don't require a protocol to filter.</span></span>
    - <span data-ttu-id="7d0f2-169">每次更改筛选值时，必须单击 "刷新" 图标以获取相关结果。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-169">You must click the Refresh icon every time you change the filter values to get relevant results.</span></span>

5. <span data-ttu-id="7d0f2-170">**高级筛选器**：使用这些筛选器，可以生成复杂的查询和筛选数据集。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-170">**Advanced filters**: With these filters, you can build complex queries and filter your data set.</span></span> <span data-ttu-id="7d0f2-171">单击 "*高级" 筛选器*将打开带选项的浮出控件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-171">Clicking on *Advanced Filters* opens a flyout with options.</span></span>

   <span data-ttu-id="7d0f2-172">高级筛选是搜索功能的一个极好的补充。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-172">Advanced filtering is a great addition to search capabilities.</span></span> <span data-ttu-id="7d0f2-173">*收件人*、*发件人*和*发件人域*中引入了 boolean **NOT** filter，以允许管理员通过排除值来进行调查。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-173">A boolean **NOT** filter has been introduced on *Recipient*, *Sender* and *Sender domain* to allow admins to investigate by excluding values.</span></span> <span data-ttu-id="7d0f2-174">此选项显示在 "选择参数不*包含任何*"。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-174">This option appears under selection parameter *Contains none of*.</span></span> <span data-ttu-id="7d0f2-175">**不**允许管理员排除警报邮箱、默认的答复邮箱不会受到调查，并且在管理员搜索特定主题（主题 = "注意"）的情况下，可以将收件人设置为 "无" *defaultMail@contoso.com 的*情况很有用。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-175">**NOT** will let admins exclude alert mailboxes, default reply mailboxes from their investigations, and is useful for cases where admins search for a specific subject (subject="Attention") where the Recipient can be set to *none of defaultMail@contoso.com*.</span></span> <span data-ttu-id="7d0f2-176">这是精确的值搜索。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-176">This is an exact value search.</span></span>

   ![收件人-"不包含任何" 高级筛选器。](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   <span data-ttu-id="7d0f2-178">*按小时筛选*可帮助贵组织的安全团队快速向下钻取。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-178">*Filtering by hours* will help your organization's security team drill down quickly.</span></span> <span data-ttu-id="7d0f2-179">允许的最短持续时间为30分钟。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-179">The shortest allowed time duration is 30 minutes.</span></span> <span data-ttu-id="7d0f2-180">如果可以根据时间帧（例如，在3小时前发生）缩小可疑操作，这将限制上下文并帮助查明问题。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-180">If you can narrow the suspicious action by time-frame (e.g. it happened 3 hours ago), this will limit the context and help pinpoint the problem.</span></span>

  ![按小时筛选选项，以缩小数据安全团队的处理量，并且其最短持续时间为30分钟。](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. <span data-ttu-id="7d0f2-182">**威胁资源管理器中的字段**：威胁浏览器会公开更多与安全性相关的邮件信息，例如*传递操作*、*传递位置*、*特殊操作*、*方向*性、*覆盖*和*URL 威胁*。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-182">**Fields in threat explorer**: Threat Explorer exposes a lot more security-related mail information such as *Delivery action*, *Delivery location*, *Special action*, *Directionality*, *Overrides*, and *URL threat*.</span></span> <span data-ttu-id="7d0f2-183">它还允许组织的安全团队以更高确定性进行调查。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-183">It also allows your organization's security team to investigate with a higher certainty.</span></span> 

    <span data-ttu-id="7d0f2-184">*传递操作*是由于现有策略或检测而导致对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-184">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="7d0f2-185">以下是电子邮件可能执行的操作：</span><span class="sxs-lookup"><span data-stu-id="7d0f2-185">Here are the possible actions an email can take:</span></span>
    - <span data-ttu-id="7d0f2-186">**传递**–将电子邮件传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-186">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
    - <span data-ttu-id="7d0f2-187">**Junked** （传递给垃圾邮件）–将电子邮件发送到用户的垃圾邮件文件夹或已删除的文件夹，并且用户可以访问其垃圾邮件或已删除文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-187">**Junked** (Delivered to junk)– email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>
    - <span data-ttu-id="7d0f2-188">已**阻止**–隔离、失败或丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-188">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="7d0f2-189">（这是用户完全无法访问的。）</span><span class="sxs-lookup"><span data-stu-id="7d0f2-189">(This is completely inaccessible by the user.)</span></span>
    - <span data-ttu-id="7d0f2-190">**已替换**–所有恶意附件替换为 .txt 文件的电子邮件，这些文件的状态为 "恶意附件"。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-190">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious</span></span>

    <span data-ttu-id="7d0f2-191">**送达位置**：提供了传递位置筛选器，以便帮助管理员了解可疑的恶意邮件结束的位置以及对它执行了哪些操作。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-191">**Delivery location**: The Delivery location filter is available in order to help admins understand where suspected malicious mail ended-up and what actions were taken on it.</span></span> <span data-ttu-id="7d0f2-192">可将生成的数据导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-192">The resulting data can be exported to spreadsheet.</span></span> <span data-ttu-id="7d0f2-193">可能的送达位置为：</span><span class="sxs-lookup"><span data-stu-id="7d0f2-193">Possible delivery locations are:</span></span>
    - <span data-ttu-id="7d0f2-194">**收件箱或文件夹**–电子邮件位于收件箱中或特定文件夹中，具体取决于您的电子邮件规则。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-194">**Inbox or folder** – The email is in the Inbox or a specific folder, according to your email rules.</span></span>
    - <span data-ttu-id="7d0f2-195">**本地或外部**–邮箱在云中不存在，但在本地。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-195">**On-prem or external** – The mailbox doesn't exist in the Cloud but is on-premises.</span></span>
    - <span data-ttu-id="7d0f2-196">**垃圾邮件文件夹**–电子邮件位于用户的垃圾邮件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-196">**Junk folder** – The email is in a user's Junk mail folder.</span></span>
    - <span data-ttu-id="7d0f2-197">"**已删除邮件" 文件夹**–电子邮件位于用户的 "已删除邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-197">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>
    - <span data-ttu-id="7d0f2-198">**隔离**–隔离的电子邮件，而不是用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-198">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>
    - <span data-ttu-id="7d0f2-199">**失败**–电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-199">**Failed** – The email failed to reach the mailbox.</span></span>
    - <span data-ttu-id="7d0f2-200">**丢弃**–电子邮件在邮件流中的某处丢失。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-200">**Dropped** – The email was lost somewhere in the mail flow.</span></span>

    <span data-ttu-id="7d0f2-201">**方向**性：此选项允许安全操作团队按邮件发件人的 "方向" 进行筛选或进行筛选。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-201">**Directionality**: This option allows your security operations team to filter by the 'direction' a mail comes from, or is going.</span></span> <span data-ttu-id="7d0f2-202">方向性值为*入站*、*出站*和*组织内部*（对应于从外部进入您的组织的邮件、从您的组织发送出去或内部发送到您的组织）。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-202">Directionality values are *Inbound*, *Outbound*, and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively).</span></span> <span data-ttu-id="7d0f2-203">此信息可帮助安全操作团队发现欺骗和模拟，因为方向性值之间不匹配（例如，</span><span class="sxs-lookup"><span data-stu-id="7d0f2-203">This information can help security operations teams spot spoofing and impersonation, because a mismatch between the Directionality value (ex.</span></span> <span data-ttu-id="7d0f2-204">*入站*），发件人的域（*看起来*是内部域）将是明显的！</span><span class="sxs-lookup"><span data-stu-id="7d0f2-204">*Inbound*), and the domain of the sender (which *appears* to be an internal domain) will be evident!</span></span> <span data-ttu-id="7d0f2-205">方向性值是相互独立的，并且可以与邮件跟踪不同。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-205">The Directionality value is separate, and can differ from, the Message Trace.</span></span> <span data-ttu-id="7d0f2-206">可将结果导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-206">Results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="7d0f2-207">**替代**：此筛选器获取邮件的 "详细信息" 选项卡上显示的信息，并使用它来公开允许和阻止邮件的组织或用户策略被*覆盖*的位置。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-207">**Overrides**: This filter takes information that appears on the mail's details tab and uses it to expose where organizational, or user policies, for allowing and blocking mails have been *overridden*.</span></span> <span data-ttu-id="7d0f2-208">此筛选器最重要的一点是，它可以帮助组织的安全团队查看由于配置而传递了多少可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-208">The most important thing about this filter is that it helps your organization's security team see how many suspicious emails were delivered due to configuration.</span></span> <span data-ttu-id="7d0f2-209">这使他们有机会根据需要修改 "允许" 和 "阻止"。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-209">This gives them an opportunity to modify allows and blocks as needed.</span></span> <span data-ttu-id="7d0f2-210">可以将此筛选器的结果集导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-210">This result set of this filter can be exported to spreadsheet.</span></span>

|<span data-ttu-id="7d0f2-211">威胁资源管理器替代</span><span class="sxs-lookup"><span data-stu-id="7d0f2-211">Threat Explorer Overrides</span></span>  | <span data-ttu-id="7d0f2-212">它们的含义</span><span class="sxs-lookup"><span data-stu-id="7d0f2-212">What they mean</span></span>  |
|---------|---------|
|<span data-ttu-id="7d0f2-213">组织策略允许</span><span class="sxs-lookup"><span data-stu-id="7d0f2-213">Allowed by Org Policy</span></span>     |   <span data-ttu-id="7d0f2-214">按组织策略的指示，允许在邮箱中发送邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-214">Mail was allowed into the mailbox as directed by the organization policy.</span></span>       |
|<span data-ttu-id="7d0f2-215">已被组织策略阻止</span><span class="sxs-lookup"><span data-stu-id="7d0f2-215">Blocked by Org policy</span></span>      |  <span data-ttu-id="7d0f2-216">邮件被阻止按照组织策略的指示将邮件传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-216">Mail was blocked from delivery to the mailbox as directed by the organization policy.</span></span>    |
|<span data-ttu-id="7d0f2-217">组织策略阻止的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="7d0f2-217">File extension blocked by Org Policy</span></span>     | <span data-ttu-id="7d0f2-218">根据组织策略的指示，文件被阻止传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-218">File was blocked from delivery to the mailbox as directed by the organization policy.</span></span>        |
|<span data-ttu-id="7d0f2-219">用户策略允许</span><span class="sxs-lookup"><span data-stu-id="7d0f2-219">Allowed by User Policy</span></span>     | <span data-ttu-id="7d0f2-220">用户策略允许在邮箱中发送邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-220">Mail was allowed into the mailbox as directed by the user policy.</span></span>        |
|<span data-ttu-id="7d0f2-221">被用户策略阻止</span><span class="sxs-lookup"><span data-stu-id="7d0f2-221">Blocked by User Policy</span></span>     | <span data-ttu-id="7d0f2-222">阻止邮件按照用户策略的指导将邮件传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-222">Mail was blocked from delivery to the mailbox as directed by the user policy.</span></span>        |

<span data-ttu-id="7d0f2-223">**Url 威胁**： "url 威胁" 字段已包含在电子邮件的 "*详细信息*" 选项卡上，用于指示 URL 所呈现的威胁。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-223">**URL threat**: The URL threat field has been included on the *details* tab of an email to indicate the threat presented by a URL.</span></span> <span data-ttu-id="7d0f2-224">URL 表现的威胁可以包含*恶意软件*、*网络钓鱼*或*垃圾邮件*，而威胁部分中不会显示*任何\*\*威胁*的 url。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-224">Threats presented by a URL can include *Malware*, *Phish*, or *Spam*, and a URL with *no threat* will say *None* in the threats section.</span></span>

7. <span data-ttu-id="7d0f2-225">**电子邮件日程表视图**：安全操作团队可能需要深入研究电子邮件详细信息，以便进一步调查。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-225">**Email timeline view**: Your security operations team might need to deep-dive into email details to investigate further.</span></span> <span data-ttu-id="7d0f2-226">通过电子邮件时间线，管理员可以查看从传递到送达后对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-226">The email timeline allows admins to view actions taken on an email from delivery to post-delivery.</span></span> <span data-ttu-id="7d0f2-227">若要查看电子邮件日程表，请单击电子邮件的主题，然后单击 "电子邮件日程表"。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-227">To view an email timeline, click on the subject of an email message, and then click Email timeline.</span></span> <span data-ttu-id="7d0f2-228">（它显示在面板上的其他标题中，如摘要或详细信息。）可以将这些结果导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-228">(It appears among other headings on the panel like Summary or Details.) These results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="7d0f2-229">电子邮件日程表将打开，其中显示电子邮件的所有送达和传递后事件的表格。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-229">Email timeline will open to a table that shows all delivery and post-delivery events for the email.</span></span> <span data-ttu-id="7d0f2-230">如果对电子邮件没有进一步的操作，您应该会看到原始传递的单个事件，其中指出了结果（如*网络钓鱼*）的结论，如 "已*阻止*"。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-230">If there are no further actions on the email, you should see a single event for the original delivery that states a result, such as *Blocked*, with a verdict like *Phish*.</span></span> <span data-ttu-id="7d0f2-231">管理员可以导出整个电子邮件时间线，包括选项卡和电子邮件（如主题、发件人、收件人、网络和邮件 ID）上的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-231">Admins can export the entire email timeline, including all details on the tab and email (such as, Subject, Sender, Recipient, Network, and Message ID).</span></span> <span data-ttu-id="7d0f2-232">电子邮件日程表在随机时减少，因为检查不同位置的时间较少，以尝试了解自电子邮件到达后发生的事件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-232">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="7d0f2-233">当电子邮件上的多个事件发生时，或在同一时间结束时，这些事件将显示在 "日程表" 视图中。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-233">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span>

8. <span data-ttu-id="7d0f2-234">**预览/下载**：威胁资源管理器为安全操作团队提供调查可疑电子邮件所需的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-234">**Preview / download**: Threat Explorer gives your security operations team the details they need to investigate suspicious email.</span></span> <span data-ttu-id="7d0f2-235">您的安全操作团队可以执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="7d0f2-235">Your security operations team can either:</span></span>

    - <span data-ttu-id="7d0f2-236">[检查传递操作和位置](#check-the-delivery-action-and-location)。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-236">[Check the delivery action and location](#check-the-delivery-action-and-location).</span></span>

    - <span data-ttu-id="7d0f2-237">[查看你的电子邮件的日程表](#view-the-timeline-of-your-email)。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-237">[View the timeline of your email](#view-the-timeline-of-your-email).</span></span>

    ##### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="7d0f2-238">检查传递操作和位置</span><span class="sxs-lookup"><span data-stu-id="7d0f2-238">Check the delivery action and location</span></span>

    <span data-ttu-id="7d0f2-239">在[威胁资源管理器（和实时检测）](threat-explorer.md)中，您现在具有**传递操作**列和 "**传递位置**" 列，而不是以前的 "**传递状态**" 列。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-239">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="7d0f2-240">这将导致您的电子邮件位于何处的更完整的图片。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-240">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="7d0f2-241">此更改的目标部分是使调查更易于进行安全操作团队，但最终结果是了解问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-241">Part of the goal of this change is to make investigations easier for security operations teams, but the net result is knowing the location of problem email messages at a glance.</span></span>

    <span data-ttu-id="7d0f2-242">传递状态现已分为两列：</span><span class="sxs-lookup"><span data-stu-id="7d0f2-242">Delivery Status is now broken out into two columns:</span></span>

    - <span data-ttu-id="7d0f2-243">**传递操作**-此电子邮件的状态是什么？</span><span class="sxs-lookup"><span data-stu-id="7d0f2-243">**Delivery action** - What is the status of this email?</span></span>

    - <span data-ttu-id="7d0f2-244">**送达位置**-此电子邮件的路由结果</span><span class="sxs-lookup"><span data-stu-id="7d0f2-244">**Delivery location** - Where was this email routed as a result?</span></span>

    <span data-ttu-id="7d0f2-245">传递操作是由于现有策略或检测而导致对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-245">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="7d0f2-246">以下是电子邮件可能执行的操作：</span><span class="sxs-lookup"><span data-stu-id="7d0f2-246">Here are the possible actions an email can take:</span></span>

    - <span data-ttu-id="7d0f2-247">**传递**–将电子邮件传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-247">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

    - <span data-ttu-id="7d0f2-248">**Junked** –将电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹，并且用户可以访问其 "垃圾邮件" 或 "已删除" 文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-248">**Junked** – email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

    - <span data-ttu-id="7d0f2-249">已**阻止**–隔离、失败或丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-249">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="7d0f2-250">（这是用户完全无法访问的。）</span><span class="sxs-lookup"><span data-stu-id="7d0f2-250">(This is completely inaccessible by the user.)</span></span>

    - <span data-ttu-id="7d0f2-251">**已替换**–所有恶意附件都被替换为 .txt 文件的电子邮件，这些文件的状态为 "恶意附件"。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-251">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
    <span data-ttu-id="7d0f2-252">"送达位置" 显示运行送达后的策略和检测结果。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-252">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="7d0f2-253">它已链接到传递操作。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-253">It's linked to a Delivery Action.</span></span> <span data-ttu-id="7d0f2-254">添加此字段是为了深入了解在发现问题邮件时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-254">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="7d0f2-255">以下是送达位置的可能值：</span><span class="sxs-lookup"><span data-stu-id="7d0f2-255">Here are the possible values of delivery location:</span></span>

    - <span data-ttu-id="7d0f2-256">**收件箱或文件夹**–电子邮件位于收件箱或文件夹中（根据您的电子邮件规则）。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-256">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

    - <span data-ttu-id="7d0f2-257">**本地或外部**–邮箱在云上不存在，但在本地。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-257">**On-prem or external** – The mailbox doesn't exist on cloud but is on-premises.</span></span>

    - <span data-ttu-id="7d0f2-258">**垃圾邮件文件夹**–电子邮件位于用户的垃圾邮件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-258">**Junk folder** – The email is in a user's Junk folder.</span></span>

    - <span data-ttu-id="7d0f2-259">"**已删除邮件" 文件夹**–电子邮件位于用户的 "已删除邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-259">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

    - <span data-ttu-id="7d0f2-260">**隔离**–隔离的电子邮件，而不是用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-260">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>

    - <span data-ttu-id="7d0f2-261">**失败**–电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-261">**Failed** – The email failed to reach the mailbox.</span></span>

    - <span data-ttu-id="7d0f2-262">**丢弃**–电子邮件在邮件流中的某个位置丢失。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-262">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

     ##### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="7d0f2-263">查看你的电子邮件的日程表</span><span class="sxs-lookup"><span data-stu-id="7d0f2-263">View the timeline of your email</span></span>
  
     <span data-ttu-id="7d0f2-264">**电子邮件日程表**是威胁资源管理器中的一个字段，可使您的安全操作团队更轻松地使用查找。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-264">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="7d0f2-265">当电子邮件上的多个事件同时发生或在同一时间结束时，这些事件将显示在 "日程表" 视图中。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-265">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="7d0f2-266">在 "**特殊操作**" 列中捕获到电子邮件的传递后发生的一些事件。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-266">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="7d0f2-267">将电子邮件的时间线中的信息与所执行的任何特殊操作组合在一起，可使管理员深入了解策略和威胁处理（例如邮件路由的位置，在某些情况下，在某些情况下，最终评估是什么）。</span><span class="sxs-lookup"><span data-stu-id="7d0f2-267">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="7d0f2-268">相关主题</span><span class="sxs-lookup"><span data-stu-id="7d0f2-268">Related topics</span></span>

[<span data-ttu-id="7d0f2-269">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="7d0f2-269">Office 365 Advanced Threat Protection</span></span>](office-365-ti.md)
  
[<span data-ttu-id="7d0f2-270">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="7d0f2-270">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="7d0f2-271">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="7d0f2-271">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
