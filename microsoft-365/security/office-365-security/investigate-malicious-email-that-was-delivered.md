---
title: 调查 Office 365 中提供的恶意电子邮件，查找并调查恶意电子邮件
keywords: TIMailData-内联、安全事件、事件、ATP PowerShell、电子邮件恶意软件、受损用户、电子邮件网络钓鱼、电子邮件恶意软件、阅读电子邮件标头、阅读邮件头、打开电子邮件头、特殊操作
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
ms.openlocfilehash: 7677c1741a173c0528504f0fad67439608845f64
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842936"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="06781-104">调查在 Office 365 中提供的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="06781-104">Investigate malicious email that was delivered in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="06781-105">[Microsoft Defender For Office 365](office-365-atp.md) 使你能够调查将组织中的人员面临风险的活动，并采取措施保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="06781-105">[Microsoft Defender for Office 365](office-365-atp.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="06781-106">例如，如果您是组织的安全团队的一部分，则可以查找并调查已传递的可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-106">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="06781-107">您可以使用 [威胁资源管理器 (或) 的实时检测 ](threat-explorer.md)来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="06781-107">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>

> [!NOTE]
> <span data-ttu-id="06781-108">请在 [此处](remediate-malicious-email-delivered-office-365.md)跳转到修补文章。</span><span class="sxs-lookup"><span data-stu-id="06781-108">Jump to the remediation article [here](remediate-malicious-email-delivered-office-365.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="06781-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="06781-109">Before you begin</span></span>

<span data-ttu-id="06781-110">请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="06781-110">Make sure that the following requirements are met:</span></span>

- <span data-ttu-id="06781-111">您的组织具有 [Microsoft Defender For Office 365](office-365-atp.md) ，并且 [许可证已分配给用户](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="06781-111">Your organization has [Microsoft Defender for Office 365](office-365-atp.md) and [licenses are assigned to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

- <span data-ttu-id="06781-112">为你的组织启用[审核日志记录](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="06781-112">[audit logging](../../compliance/turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span>

- <span data-ttu-id="06781-113">您的组织具有为反垃圾邮件、反恶意软件、反网络钓鱼等定义的策略。</span><span class="sxs-lookup"><span data-stu-id="06781-113">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="06781-114">请参阅防御 [Office 365 中的威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="06781-114">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="06781-115">您是全局管理员，或者您具有安全管理员或在安全合规中心中分配的搜索和清除角色 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="06781-115">You are a global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="06781-116">查看 [安全 &amp; 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="06781-116">See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="06781-117">对于某些操作，还必须分配新的预览角色。</span><span class="sxs-lookup"><span data-stu-id="06781-117">For some actions, you must also have a new Preview role assigned.</span></span>

### <a name="preview-role-permissions"></a><span data-ttu-id="06781-118">预览角色权限</span><span class="sxs-lookup"><span data-stu-id="06781-118">Preview role permissions</span></span>

<span data-ttu-id="06781-119">若要执行某些操作（如查看邮件头或下载电子邮件内容），您必须具有一个名为 *Preview* 的新角色，并将其添加到另一个相应的角色组。</span><span class="sxs-lookup"><span data-stu-id="06781-119">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate role group.</span></span> <span data-ttu-id="06781-120">下表阐明了所需的角色和权限。</span><span class="sxs-lookup"><span data-stu-id="06781-120">The following table clarifies required roles and permissions.</span></span>

****

|<span data-ttu-id="06781-121">活动</span><span class="sxs-lookup"><span data-stu-id="06781-121">Activity</span></span>|<span data-ttu-id="06781-122">角色组</span><span class="sxs-lookup"><span data-stu-id="06781-122">Role group</span></span>|<span data-ttu-id="06781-123">是否需要预览角色？</span><span class="sxs-lookup"><span data-stu-id="06781-123">Preview role needed?</span></span>|
|---|---|---|
|<span data-ttu-id="06781-124">使用威胁资源管理器 (和实时检测) 分析威胁</span><span class="sxs-lookup"><span data-stu-id="06781-124">Use Threat Explorer (and real-time detections) to analyze threats</span></span> |<span data-ttu-id="06781-125">全局管理员</span><span class="sxs-lookup"><span data-stu-id="06781-125">Global Administrator</span></span> <br> <span data-ttu-id="06781-126">安全管理员</span><span class="sxs-lookup"><span data-stu-id="06781-126">Security Administrator</span></span> <br> <span data-ttu-id="06781-127">安全读取者</span><span class="sxs-lookup"><span data-stu-id="06781-127">Security Reader</span></span>|<span data-ttu-id="06781-128">否</span><span class="sxs-lookup"><span data-stu-id="06781-128">No</span></span>|
|<span data-ttu-id="06781-129">使用威胁资源管理器 (和实时检测) 查看电子邮件的邮件头以及预览和下载隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="06781-129">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>|<span data-ttu-id="06781-130">全局管理员</span><span class="sxs-lookup"><span data-stu-id="06781-130">Global Administrator</span></span> <br> <span data-ttu-id="06781-131">安全管理员</span><span class="sxs-lookup"><span data-stu-id="06781-131">Security Administrator</span></span> <br><span data-ttu-id="06781-132">安全读取者</span><span class="sxs-lookup"><span data-stu-id="06781-132">Security Reader</span></span>|<span data-ttu-id="06781-133">否</span><span class="sxs-lookup"><span data-stu-id="06781-133">No</span></span>|
|<span data-ttu-id="06781-134">使用威胁浏览器查看邮件头并下载传递给邮箱的电子邮件</span><span class="sxs-lookup"><span data-stu-id="06781-134">Use Threat Explorer to view headers and download email messages delivered to mailboxes</span></span>|<span data-ttu-id="06781-135">全局管理员</span><span class="sxs-lookup"><span data-stu-id="06781-135">Global Administrator</span></span> <br><span data-ttu-id="06781-136">安全管理员</span><span class="sxs-lookup"><span data-stu-id="06781-136">Security Administrator</span></span> <br> <span data-ttu-id="06781-137">安全读取者</span><span class="sxs-lookup"><span data-stu-id="06781-137">Security Reader</span></span> <br> <span data-ttu-id="06781-138">预览</span><span class="sxs-lookup"><span data-stu-id="06781-138">Preview</span></span>|<span data-ttu-id="06781-139">是</span><span class="sxs-lookup"><span data-stu-id="06781-139">Yes</span></span>|
|

> [!NOTE]
> <span data-ttu-id="06781-140">*预览* 是一个角色，而不是角色组;必须将预览角色添加到 Office 365 的现有角色组中。</span><span class="sxs-lookup"><span data-stu-id="06781-140">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365.</span></span> <span data-ttu-id="06781-141">全局管理员角色分配有 Microsoft 365 管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) ，并且安全管理员和安全读者角色在安全 & 合规性中心 () 中分配 [https://protection.office.com](https://protection.office.com) 。</span><span class="sxs-lookup"><span data-stu-id="06781-141">The Global Administrator role is assigned the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)), and the Security Administrator and Security Reader roles are assigned in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="06781-142">若要了解有关角色和权限的详细信息，请参阅 [Security & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="06781-142">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="find-suspicious-email-that-was-delivered"></a><span data-ttu-id="06781-143">查找已发送的可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="06781-143">Find suspicious email that was delivered</span></span>

<span data-ttu-id="06781-144">威胁资源管理器是一种功能强大的报告，可用于多种用途，如查找和删除邮件、标识恶意电子邮件发件人的 IP 地址或启动事件以进行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="06781-144">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="06781-145">下面的过程重点介绍如何使用资源管理器查找和删除收件人邮箱中的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-145">The following procedure focuses on using Explorer to find and delete malicious email from recipient's mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="06781-146">资源管理器中的默认搜索当前不包含 Zapped 项目。</span><span class="sxs-lookup"><span data-stu-id="06781-146">Default searches in Explorer don't currently include Zapped items.</span></span>  <span data-ttu-id="06781-147">这适用于所有视图，例如恶意软件或网络钓鱼视图。</span><span class="sxs-lookup"><span data-stu-id="06781-147">This applies to all views, for example malware or phish views.</span></span> <span data-ttu-id="06781-148">若要包含 Zapped 项，需要将 "传递操作" 设置为 "已删除的由 ZAP 删除"。</span><span class="sxs-lookup"><span data-stu-id="06781-148">To include Zapped items you need to add a 'Delivery action' set to include 'Removed by ZAP'.</span></span> <span data-ttu-id="06781-149">如果包含所有选项，您将看到所有传递操作结果，包括 Zapped 项目。</span><span class="sxs-lookup"><span data-stu-id="06781-149">If you include all options, you'll see all delivery action results, including Zapped items.</span></span>

1. <span data-ttu-id="06781-150">**导航到 "威胁资源管理器** "：转到 [https://protection.office.com](https://protection.office.com) 并使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="06781-150">**Navigate to Threat Explorer** : Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="06781-151">这会将您带到安全 &amp; 合规中心。</span><span class="sxs-lookup"><span data-stu-id="06781-151">This takes you to the Security &amp; Compliance Center.</span></span>

2. <span data-ttu-id="06781-152">在左侧导航快速启动栏中，选择 " **威胁管理** \> **资源管理器** "。</span><span class="sxs-lookup"><span data-stu-id="06781-152">In the left navigation quick-launch, choose **Threat management** \> **Explorer**.</span></span>

    ![具有 "传递操作" 和 "送达位置" 字段的资源管理器。](../../media/ThreatExFields.PNG)

    <span data-ttu-id="06781-154">您可能会注意到 "新建 **特殊操作** " 列。</span><span class="sxs-lookup"><span data-stu-id="06781-154">You may notice the new **Special actions** column.</span></span> <span data-ttu-id="06781-155">此功能旨在告诉管理员处理电子邮件的结果。</span><span class="sxs-lookup"><span data-stu-id="06781-155">This feature is aimed at telling admins the outcome of processing an email.</span></span> <span data-ttu-id="06781-156">可以在与 **传递操作** 和 **传递位置** 相同的位置访问 " **特殊操作** " 列。</span><span class="sxs-lookup"><span data-stu-id="06781-156">The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**.</span></span> <span data-ttu-id="06781-157">在威胁资源管理器的电子邮件日程表结束时，可能会更新特殊操作，这是旨在使求职体验更适合管理员的新功能。</span><span class="sxs-lookup"><span data-stu-id="06781-157">Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.</span></span>

3. <span data-ttu-id="06781-158">**威胁资源管理器中的视图** ：在 " **视图** " 菜单中选择 " **所有电子邮件** "。</span><span class="sxs-lookup"><span data-stu-id="06781-158">**Views in Threat Explorer** : In the **View** menu, choose **All email**.</span></span>

    ![威胁资源管理器视图菜单和电子邮件-恶意软件、网络钓鱼诈骗、提交和所有电子邮件选项，也是内容恶意软件。](../../media/tp-InvestigateMalEmail-viewmenu.png)

    <span data-ttu-id="06781-160">*恶意软件* 视图当前是默认的，并捕获检测到恶意软件威胁的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-160">The *Malware* view is currently the default, and captures emails where a malware threat is detected.</span></span> <span data-ttu-id="06781-161">*网络钓鱼* 视图的工作方式与网络钓鱼的操作方式相同。</span><span class="sxs-lookup"><span data-stu-id="06781-161">The *Phish* view operates in the same way, for Phish.</span></span>

    <span data-ttu-id="06781-162">但是， *所有的电子邮件视图都会* 列出组织收到的每封邮件，无论是否检测到威胁。</span><span class="sxs-lookup"><span data-stu-id="06781-162">However, *All email* view lists every mail received by the organization, whether threats were detected or not.</span></span> <span data-ttu-id="06781-163">正如您所想到的，这是大量数据，这就是为什么此视图显示一个要求应用筛选器的占位符。</span><span class="sxs-lookup"><span data-stu-id="06781-163">As you can imagine, this is a lot of data, which is why this view shows a placeholder that asks a filter be applied.</span></span> <span data-ttu-id="06781-164"> (此视图仅适用于 Office 365 P2 客户的 Defender。 ) </span><span class="sxs-lookup"><span data-stu-id="06781-164">(This view is only available for Defender for Office 365 P2 customers.)</span></span>

    <span data-ttu-id="06781-165">" *提交* " 视图显示由管理员或用户提交的、报告给 Microsoft 的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-165">*Submissions* view shows up all mails submitted by admin or user that were reported to Microsoft.</span></span>

4. <span data-ttu-id="06781-166">**威胁资源管理器中的搜索和筛选** 器：筛选器显示在搜索栏中页面的顶部，以帮助管理员进行调查。</span><span class="sxs-lookup"><span data-stu-id="06781-166">**Search and filter in Threat Explorer** : Filters appear at the top of the page in the search bar to help admins in their investigations.</span></span> <span data-ttu-id="06781-167">请注意，可以同时应用多个筛选器，添加筛选器中的多个逗号分隔值，以缩小搜索范围。</span><span class="sxs-lookup"><span data-stu-id="06781-167">Notice that multiple filters can be applied at the same time, and multiple comma-separated values added to a filter to narrow down the search.</span></span> <span data-ttu-id="06781-168">请注意：</span><span class="sxs-lookup"><span data-stu-id="06781-168">Remember:</span></span>

    - <span data-ttu-id="06781-169">筛选器对大多数筛选条件执行完全匹配。</span><span class="sxs-lookup"><span data-stu-id="06781-169">Filters do exact matching on most filter conditions.</span></span>
    - <span data-ttu-id="06781-170">Subject 筛选器使用 CONTAINS 查询。</span><span class="sxs-lookup"><span data-stu-id="06781-170">Subject filter uses a CONTAINS query.</span></span>
    - <span data-ttu-id="06781-171">URL 筛选器使用或不使用协议 (ex。</span><span class="sxs-lookup"><span data-stu-id="06781-171">URL filters work with or without protocols (ex.</span></span> <span data-ttu-id="06781-172">https) 。</span><span class="sxs-lookup"><span data-stu-id="06781-172">https).</span></span>
    - <span data-ttu-id="06781-173">URL 域、URL 路径以及 URL 域和路径筛选器不需要使用协议进行筛选。</span><span class="sxs-lookup"><span data-stu-id="06781-173">URL domain, URL path, and URL domain and path filters don't require a protocol to filter.</span></span>
    - <span data-ttu-id="06781-174">每次更改筛选值时，必须单击 "刷新" 图标以获取相关结果。</span><span class="sxs-lookup"><span data-stu-id="06781-174">You must click the Refresh icon every time you change the filter values to get relevant results.</span></span>

5. <span data-ttu-id="06781-175">**高级筛选器** ：使用这些筛选器，可以生成复杂的查询和筛选数据集。</span><span class="sxs-lookup"><span data-stu-id="06781-175">**Advanced filters** : With these filters, you can build complex queries and filter your data set.</span></span> <span data-ttu-id="06781-176">单击 " *高级" 筛选器* 将打开带选项的浮出控件。</span><span class="sxs-lookup"><span data-stu-id="06781-176">Clicking on *Advanced Filters* opens a flyout with options.</span></span>

   <span data-ttu-id="06781-177">高级筛选是搜索功能的一个极好的补充。</span><span class="sxs-lookup"><span data-stu-id="06781-177">Advanced filtering is a great addition to search capabilities.</span></span> <span data-ttu-id="06781-178">*收件人* 、 *发件人* 和 *发件人域* 中引入了 boolean **NOT** filter，以允许管理员通过排除值来进行调查。</span><span class="sxs-lookup"><span data-stu-id="06781-178">A boolean **NOT** filter has been introduced on *Recipient* , *Sender* and *Sender domain* to allow admins to investigate by excluding values.</span></span> <span data-ttu-id="06781-179">此选项显示在 "选择参数不 *包含任何* "。</span><span class="sxs-lookup"><span data-stu-id="06781-179">This option appears under selection parameter *Contains none of*.</span></span> <span data-ttu-id="06781-180">[！注意] **不** 允许管理员排除警报邮箱、默认的答复邮箱的调查，并在管理员搜索特定主题 (主题 = "注意" ) （可将收件人设置为 *defaultMail \@ contoso.com）的* 情况下很有用。</span><span class="sxs-lookup"><span data-stu-id="06781-180">**NOT** will let admins exclude alert mailboxes, default reply mailboxes from their investigations, and is useful for cases where admins search for a specific subject (subject="Attention") where the Recipient can be set to *none of defaultMail\@contoso.com*.</span></span> <span data-ttu-id="06781-181">这是精确的值搜索。</span><span class="sxs-lookup"><span data-stu-id="06781-181">This is an exact value search.</span></span>

   ![收件人-"不包含任何" 高级筛选器。](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   <span data-ttu-id="06781-183">*按小时筛选* 可帮助贵组织的安全团队快速向下钻取。</span><span class="sxs-lookup"><span data-stu-id="06781-183">*Filtering by hours* will help your organization's security team drill down quickly.</span></span> <span data-ttu-id="06781-184">允许的最短持续时间为30分钟。</span><span class="sxs-lookup"><span data-stu-id="06781-184">The shortest allowed time duration is 30 minutes.</span></span> <span data-ttu-id="06781-185">如果可以根据时间帧缩小可疑操作 (例如，在3小时前) ，这将限制上下文并帮助查明问题。</span><span class="sxs-lookup"><span data-stu-id="06781-185">If you can narrow the suspicious action by time-frame (e.g. it happened 3 hours ago), this will limit the context and help pinpoint the problem.</span></span>

   ![按小时筛选选项，以缩小数据安全团队的处理量，并且其最短持续时间为30分钟。](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. <span data-ttu-id="06781-187">**威胁资源管理器中的字段** ：威胁浏览器会公开更多与安全性相关的邮件信息，例如 *传递操作* 、 *传递位置* 、 *特殊操作* 、 *方向* 性、 *覆盖* 和 *URL 威胁* 。</span><span class="sxs-lookup"><span data-stu-id="06781-187">**Fields in threat explorer** : Threat Explorer exposes a lot more security-related mail information such as *Delivery action* , *Delivery location* , *Special action* , *Directionality* , *Overrides* , and *URL threat*.</span></span> <span data-ttu-id="06781-188">它还允许组织的安全团队以更高确定性进行调查。</span><span class="sxs-lookup"><span data-stu-id="06781-188">It also allows your organization's security team to investigate with a higher certainty.</span></span>

    <span data-ttu-id="06781-189">*传递操作* 是由于现有策略或检测而导致对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="06781-189">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="06781-190">以下是电子邮件可能执行的操作：</span><span class="sxs-lookup"><span data-stu-id="06781-190">Here are the possible actions an email can take:</span></span>

    - <span data-ttu-id="06781-191">**传递** –将电子邮件传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="06781-191">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
    - <span data-ttu-id="06781-192">**Junked** (传递到垃圾) –将电子邮件发送到用户的垃圾邮件文件夹或已删除的文件夹，并且用户可以访问其垃圾邮件或已删除文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-192">**Junked** (Delivered to junk)– email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>
    - <span data-ttu-id="06781-193">已 **阻止** –隔离、失败或丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-193">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="06781-194"> (完全无法被用户访问。 ) </span><span class="sxs-lookup"><span data-stu-id="06781-194">(This is completely inaccessible by the user.)</span></span>
    - <span data-ttu-id="06781-195">**已替换** –所有恶意附件替换为 .txt 文件的电子邮件，这些文件的状态为 "恶意附件"。</span><span class="sxs-lookup"><span data-stu-id="06781-195">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious</span></span>

    <span data-ttu-id="06781-196">**送达位置** ：提供了传递位置筛选器，以便帮助管理员了解可疑的恶意邮件结束的位置以及对它执行了哪些操作。</span><span class="sxs-lookup"><span data-stu-id="06781-196">**Delivery location** : The Delivery location filter is available in order to help admins understand where suspected malicious mail ended-up and what actions were taken on it.</span></span> <span data-ttu-id="06781-197">可将生成的数据导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="06781-197">The resulting data can be exported to spreadsheet.</span></span> <span data-ttu-id="06781-198">可能的送达位置为：</span><span class="sxs-lookup"><span data-stu-id="06781-198">Possible delivery locations are:</span></span>

    - <span data-ttu-id="06781-199">**收件箱或文件夹** –电子邮件位于收件箱中或特定文件夹中，具体取决于您的电子邮件规则。</span><span class="sxs-lookup"><span data-stu-id="06781-199">**Inbox or folder** – The email is in the Inbox or a specific folder, according to your email rules.</span></span>
    - <span data-ttu-id="06781-200">**本地或外部** –邮箱在云中不存在，但在本地。</span><span class="sxs-lookup"><span data-stu-id="06781-200">**On-prem or external** – The mailbox doesn't exist in the Cloud but is on-premises.</span></span>
    - <span data-ttu-id="06781-201">**垃圾邮件文件夹** –电子邮件位于用户的垃圾邮件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="06781-201">**Junk folder** – The email is in a user's Junk mail folder.</span></span>
    - <span data-ttu-id="06781-202">" **已删除邮件" 文件夹** –电子邮件位于用户的 "已删除邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="06781-202">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>
    - <span data-ttu-id="06781-203">**隔离** –隔离的电子邮件，而不是用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-203">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>
    - <span data-ttu-id="06781-204">**失败** –电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="06781-204">**Failed** – The email failed to reach the mailbox.</span></span>
    - <span data-ttu-id="06781-205">**丢弃** –电子邮件在邮件流中的某处丢失。</span><span class="sxs-lookup"><span data-stu-id="06781-205">**Dropped** – The email was lost somewhere in the mail flow.</span></span>

    <span data-ttu-id="06781-206">**方向** 性：此选项允许安全操作团队按邮件发件人的 "方向" 进行筛选或进行筛选。</span><span class="sxs-lookup"><span data-stu-id="06781-206">**Directionality** : This option allows your security operations team to filter by the 'direction' a mail comes from, or is going.</span></span> <span data-ttu-id="06781-207">方向性值为 *入站* 、 *出站* 和 *组织内* (对应于从外部传入的邮件、从您的组织中发送或在内部发送到您的组织中的邮件，分别) 。</span><span class="sxs-lookup"><span data-stu-id="06781-207">Directionality values are *Inbound* , *Outbound* , and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively).</span></span> <span data-ttu-id="06781-208">此信息可帮助安全操作团队发现欺骗和模拟，因为方向性值之间不匹配 (ex。</span><span class="sxs-lookup"><span data-stu-id="06781-208">This information can help security operations teams spot spoofing and impersonation, because a mismatch between the Directionality value (ex.</span></span> <span data-ttu-id="06781-209">*入站* ) 和发件人的域 (（ *似乎* 是内部域) 将很明显！</span><span class="sxs-lookup"><span data-stu-id="06781-209">*Inbound* ), and the domain of the sender (which *appears* to be an internal domain) will be evident!</span></span> <span data-ttu-id="06781-210">方向性值是相互独立的，并且可以与邮件跟踪不同。</span><span class="sxs-lookup"><span data-stu-id="06781-210">The Directionality value is separate, and can differ from, the Message Trace.</span></span> <span data-ttu-id="06781-211">可将结果导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="06781-211">Results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="06781-212">**替代** ：此筛选器获取邮件的 "详细信息" 选项卡上显示的信息，并使用它来公开允许和阻止邮件的组织或用户策略被 *覆盖* 的位置。</span><span class="sxs-lookup"><span data-stu-id="06781-212">**Overrides** : This filter takes information that appears on the mail's details tab and uses it to expose where organizational, or user policies, for allowing and blocking mails have been *overridden*.</span></span> <span data-ttu-id="06781-213">此筛选器最重要的一点是，它可以帮助组织的安全团队查看由于配置而传递了多少可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-213">The most important thing about this filter is that it helps your organization's security team see how many suspicious emails were delivered due to configuration.</span></span> <span data-ttu-id="06781-214">这使他们有机会根据需要修改 "允许" 和 "阻止"。</span><span class="sxs-lookup"><span data-stu-id="06781-214">This gives them an opportunity to modify allows and blocks as needed.</span></span> <span data-ttu-id="06781-215">可以将此筛选器的结果集导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="06781-215">This result set of this filter can be exported to spreadsheet.</span></span>

    ****

    |<span data-ttu-id="06781-216">威胁资源管理器替代</span><span class="sxs-lookup"><span data-stu-id="06781-216">Threat Explorer Overrides</span></span>|<span data-ttu-id="06781-217">它们的含义</span><span class="sxs-lookup"><span data-stu-id="06781-217">What they mean</span></span>|
    |---|---|
    |<span data-ttu-id="06781-218">组织策略允许</span><span class="sxs-lookup"><span data-stu-id="06781-218">Allowed by Org Policy</span></span>|<span data-ttu-id="06781-219">按组织策略的指示，允许在邮箱中发送邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-219">Mail was allowed into the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="06781-220">已被组织策略阻止</span><span class="sxs-lookup"><span data-stu-id="06781-220">Blocked by Org policy</span></span>|<span data-ttu-id="06781-221">邮件被阻止按照组织策略的指示将邮件传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="06781-221">Mail was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="06781-222">组织策略阻止的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="06781-222">File extension blocked by Org Policy</span></span>|<span data-ttu-id="06781-223">根据组织策略的指示，文件被阻止传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="06781-223">File was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="06781-224">用户策略允许</span><span class="sxs-lookup"><span data-stu-id="06781-224">Allowed by User Policy</span></span>|<span data-ttu-id="06781-225">用户策略允许在邮箱中发送邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-225">Mail was allowed into the mailbox as directed by the user policy.</span></span>|
    |<span data-ttu-id="06781-226">被用户策略阻止</span><span class="sxs-lookup"><span data-stu-id="06781-226">Blocked by User Policy</span></span>|<span data-ttu-id="06781-227">阻止邮件按照用户策略的指导将邮件传递到邮箱。</span><span class="sxs-lookup"><span data-stu-id="06781-227">Mail was blocked from delivery to the mailbox as directed by the user policy.</span></span>|
    |

    <span data-ttu-id="06781-228">**Url 威胁** ： "url 威胁" 字段已包含在电子邮件的 " *详细信息* " 选项卡上，用于指示 URL 所呈现的威胁。</span><span class="sxs-lookup"><span data-stu-id="06781-228">**URL threat** : The URL threat field has been included on the *details* tab of an email to indicate the threat presented by a URL.</span></span> <span data-ttu-id="06781-229">URL 表现的威胁可以包含 *恶意软件* 、 *网络钓鱼* 或 *垃圾邮件* ，而威胁部分中不会显示 *任何\*\*威胁* 的 url。</span><span class="sxs-lookup"><span data-stu-id="06781-229">Threats presented by a URL can include *Malware* , *Phish* , or *Spam* , and a URL with *no threat* will say *None* in the threats section.</span></span>

7. <span data-ttu-id="06781-230">**电子邮件日程表视图** ：安全操作团队可能需要深入研究电子邮件详细信息，以便进一步调查。</span><span class="sxs-lookup"><span data-stu-id="06781-230">**Email timeline view** : Your security operations team might need to deep-dive into email details to investigate further.</span></span> <span data-ttu-id="06781-231">通过电子邮件时间线，管理员可以查看从传递到送达后对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="06781-231">The email timeline allows admins to view actions taken on an email from delivery to post-delivery.</span></span> <span data-ttu-id="06781-232">若要查看电子邮件日程表，请单击电子邮件的主题，然后单击 "电子邮件日程表"。</span><span class="sxs-lookup"><span data-stu-id="06781-232">To view an email timeline, click on the subject of an email message, and then click Email timeline.</span></span> <span data-ttu-id="06781-233"> (它显示在面板上的其他标题中，如摘要或详细信息。 ) 可以将这些结果导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="06781-233">(It appears among other headings on the panel like Summary or Details.) These results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="06781-234">电子邮件日程表将打开，其中显示电子邮件的所有送达和传递后事件的表格。</span><span class="sxs-lookup"><span data-stu-id="06781-234">Email timeline will open to a table that shows all delivery and post-delivery events for the email.</span></span> <span data-ttu-id="06781-235">如果对电子邮件没有进一步的操作，您应该会看到原始传递的单个事件，其中指出了结果（如 *网络钓鱼* ）的结论，如 "已 *阻止* "。</span><span class="sxs-lookup"><span data-stu-id="06781-235">If there are no further actions on the email, you should see a single event for the original delivery that states a result, such as *Blocked* , with a verdict like *Phish*.</span></span> <span data-ttu-id="06781-236">管理员可以导出整个电子邮件时间线，包括选项卡和电子邮件 (的所有详细信息，如 "主题"、"发件人"、"收件人"、"网络" 和 "邮件 ID") 。</span><span class="sxs-lookup"><span data-stu-id="06781-236">Admins can export the entire email timeline, including all details on the tab and email (such as, Subject, Sender, Recipient, Network, and Message ID).</span></span> <span data-ttu-id="06781-237">电子邮件日程表在随机时减少，因为检查不同位置的时间较少，以尝试了解自电子邮件到达后发生的事件。</span><span class="sxs-lookup"><span data-stu-id="06781-237">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="06781-238">当电子邮件上的多个事件发生时，或在同一时间结束时，这些事件将显示在 "日程表" 视图中。</span><span class="sxs-lookup"><span data-stu-id="06781-238">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span>

8. <span data-ttu-id="06781-239">**预览/下载** ：威胁资源管理器为安全操作团队提供调查可疑电子邮件所需的详细信息。</span><span class="sxs-lookup"><span data-stu-id="06781-239">**Preview / download** : Threat Explorer gives your security operations team the details they need to investigate suspicious email.</span></span> <span data-ttu-id="06781-240">您的安全操作团队可以执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="06781-240">Your security operations team can either:</span></span>

    - <span data-ttu-id="06781-241">[检查传递操作和位置](#check-the-delivery-action-and-location)。</span><span class="sxs-lookup"><span data-stu-id="06781-241">[Check the delivery action and location](#check-the-delivery-action-and-location).</span></span>

    - <span data-ttu-id="06781-242">[查看你的电子邮件的日程表](#view-the-timeline-of-your-email)。</span><span class="sxs-lookup"><span data-stu-id="06781-242">[View the timeline of your email](#view-the-timeline-of-your-email).</span></span>

### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="06781-243">检查传递操作和位置</span><span class="sxs-lookup"><span data-stu-id="06781-243">Check the delivery action and location</span></span>

<span data-ttu-id="06781-244">在 [威胁资源管理器中 (和实时检测)](threat-explorer.md)，现在您有 " **传递操作** " 和 " **传递位置** " 列，而不是以前的 " **传递状态** " 列。</span><span class="sxs-lookup"><span data-stu-id="06781-244">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="06781-245">这将导致您的电子邮件位于何处的更完整的图片。</span><span class="sxs-lookup"><span data-stu-id="06781-245">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="06781-246">此更改的目标部分是使调查更易于进行安全操作团队，但最终结果是了解问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="06781-246">Part of the goal of this change is to make investigations easier for security operations teams, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="06781-247">传递状态现已分为两列：</span><span class="sxs-lookup"><span data-stu-id="06781-247">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="06781-248">**传递操作** -此电子邮件的状态是什么？</span><span class="sxs-lookup"><span data-stu-id="06781-248">**Delivery action** - What is the status of this email?</span></span>

- <span data-ttu-id="06781-249">**送达位置** -此电子邮件的路由结果</span><span class="sxs-lookup"><span data-stu-id="06781-249">**Delivery location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="06781-250">传递操作是由于现有策略或检测而导致对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="06781-250">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="06781-251">以下是电子邮件可能执行的操作：</span><span class="sxs-lookup"><span data-stu-id="06781-251">Here are the possible actions an email can take:</span></span>

- <span data-ttu-id="06781-252">**传递** –将电子邮件传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="06781-252">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

- <span data-ttu-id="06781-253">**Junked** –将电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹，并且用户可以访问其 "垃圾邮件" 或 "已删除" 文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-253">**Junked** – email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

- <span data-ttu-id="06781-254">已 **阻止** –隔离、失败或丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-254">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="06781-255"> (完全无法被用户访问。 ) </span><span class="sxs-lookup"><span data-stu-id="06781-255">(This is completely inaccessible by the user.)</span></span>

- <span data-ttu-id="06781-256">**已替换** –所有恶意附件都被替换为 .txt 文件的电子邮件，这些文件的状态为 "恶意附件"。</span><span class="sxs-lookup"><span data-stu-id="06781-256">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>

<span data-ttu-id="06781-257">"送达位置" 显示运行送达后的策略和检测结果。</span><span class="sxs-lookup"><span data-stu-id="06781-257">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="06781-258">它已链接到传递操作。</span><span class="sxs-lookup"><span data-stu-id="06781-258">It's linked to a Delivery Action.</span></span> <span data-ttu-id="06781-259">添加此字段是为了深入了解在发现问题邮件时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="06781-259">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="06781-260">以下是送达位置的可能值：</span><span class="sxs-lookup"><span data-stu-id="06781-260">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="06781-261">**收件箱或文件夹** –电子邮件位于收件箱中或文件夹 (根据您的电子邮件规则) 。</span><span class="sxs-lookup"><span data-stu-id="06781-261">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

- <span data-ttu-id="06781-262">**本地或外部** –邮箱在云上不存在，但在本地。</span><span class="sxs-lookup"><span data-stu-id="06781-262">**On-prem or external** – The mailbox doesn't exist on cloud but is on-premises.</span></span>

- <span data-ttu-id="06781-263">**垃圾邮件文件夹** –电子邮件位于用户的垃圾邮件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="06781-263">**Junk folder** – The email is in a user's Junk folder.</span></span>

- <span data-ttu-id="06781-264">" **已删除邮件" 文件夹** –电子邮件位于用户的 "已删除邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="06781-264">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

- <span data-ttu-id="06781-265">**隔离** –隔离的电子邮件，而不是用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="06781-265">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>

- <span data-ttu-id="06781-266">**失败** –电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="06781-266">**Failed** – The email failed to reach the mailbox.</span></span>

- <span data-ttu-id="06781-267">**丢弃** –电子邮件在邮件流中的某个位置丢失。</span><span class="sxs-lookup"><span data-stu-id="06781-267">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="06781-268">查看你的电子邮件的日程表</span><span class="sxs-lookup"><span data-stu-id="06781-268">View the timeline of your email</span></span>

<span data-ttu-id="06781-269">**电子邮件日程表** 是威胁资源管理器中的一个字段，可使您的安全操作团队更轻松地使用查找。</span><span class="sxs-lookup"><span data-stu-id="06781-269">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="06781-270">当电子邮件上的多个事件同时发生或在同一时间结束时，这些事件将显示在 "日程表" 视图中。</span><span class="sxs-lookup"><span data-stu-id="06781-270">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="06781-271">在 " **特殊操作** " 列中捕获到电子邮件的传递后发生的一些事件。</span><span class="sxs-lookup"><span data-stu-id="06781-271">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="06781-272">将电子邮件的时间线中的信息与在传递后进行的任何特殊操作组合在一起，管理员可以深入了解策略和威胁处理 (例如邮件路由的位置，在某些情况下，) 最终评估。</span><span class="sxs-lookup"><span data-stu-id="06781-272">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06781-273">请在 [此处](remediate-malicious-email-delivered-office-365.md)跳转到修正主题。</span><span class="sxs-lookup"><span data-stu-id="06781-273">Jump to a remediation topic [here](remediate-malicious-email-delivered-office-365.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="06781-274">相关主题</span><span class="sxs-lookup"><span data-stu-id="06781-274">Related topics</span></span>

[<span data-ttu-id="06781-275">修正在 Office 365 中传递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="06781-275">Remediate malicious email delivered in Office 365</span></span>](remediate-malicious-email-delivered-office-365.md)

[<span data-ttu-id="06781-276">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="06781-276">Microsoft Defender for Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="06781-277">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="06781-277">Protect against threats in Office 365</span></span>](protect-against-threats.md)

[<span data-ttu-id="06781-278">查看适用于 Office 365 的 Defender 报告</span><span class="sxs-lookup"><span data-stu-id="06781-278">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
