---
title: 调查电子邮件中传递的恶意Office 365，查找并调查恶意电子邮件
keywords: TIMailData-Inline， 安全事件， 事件， Microsoft Defender for Endpoint PowerShell， 电子邮件恶意软件， 遭到入侵的用户， 电子邮件钓鱼邮件， 电子邮件恶意软件， 阅读电子邮件头， 阅读邮件头， 打开电子邮件头， 特殊操作
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/16/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 了解如何使用威胁调查和响应功能查找和调查恶意电子邮件。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 02e396cac060f2b8431b2b70e89c18950596d9c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933369"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="ccd63-104">调查在邮件中传递的恶意Office 365</span><span class="sxs-lookup"><span data-stu-id="ccd63-104">Investigate malicious email that was delivered in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ccd63-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="ccd63-105">**Applies to**</span></span>

- [<span data-ttu-id="ccd63-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="ccd63-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ccd63-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ccd63-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ccd63-108">[Microsoft Defender for Office 365](defender-for-office-365.md)使你能够调查使组织成员面临风险的活动，并采取措施来保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="ccd63-108">[Microsoft Defender for Office 365](defender-for-office-365.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="ccd63-109">例如，如果你是组织安全团队的一员，你可以查找并调查传递的可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-109">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="ccd63-110">为此，可以使用威胁资源管理器 ([或实时检测) 。 ](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="ccd63-110">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ccd63-111">跳转到此处的修正 [文章](remediate-malicious-email-delivered-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="ccd63-111">Jump to the remediation article [here](remediate-malicious-email-delivered-office-365.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ccd63-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="ccd63-112">Before you begin</span></span>

<span data-ttu-id="ccd63-113">请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="ccd63-113">Make sure that the following requirements are met:</span></span>

- <span data-ttu-id="ccd63-114">你的组织具有[Microsoft Defender for](defender-for-office-365.md) Office 365[许可证已分配给用户](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="ccd63-114">Your organization has [Microsoft Defender for Office 365](defender-for-office-365.md) and [licenses are assigned to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

- <span data-ttu-id="ccd63-115">[为](../../compliance/turn-audit-log-search-on-or-off.md) 组织启用审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="ccd63-115">[audit logging](../../compliance/turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span>

- <span data-ttu-id="ccd63-116">您的组织为反垃圾邮件、反恶意软件、防钓鱼等定义了策略。</span><span class="sxs-lookup"><span data-stu-id="ccd63-116">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="ccd63-117">请参阅[防止威胁Office 365。](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="ccd63-117">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="ccd63-118">你是全局管理员，或者你在安全与合规中心分配了安全管理员或&清除角色。</span><span class="sxs-lookup"><span data-stu-id="ccd63-118">You are a global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security & Compliance Center.</span></span> <span data-ttu-id="ccd63-119">请参阅 [安全与合规&中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ccd63-119">See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="ccd63-120">对于一些操作，还必须分配有新的 Preview 角色。</span><span class="sxs-lookup"><span data-stu-id="ccd63-120">For some actions, you must also have a new Preview role assigned.</span></span>

### <a name="preview-role-permissions"></a><span data-ttu-id="ccd63-121">预览角色权限</span><span class="sxs-lookup"><span data-stu-id="ccd63-121">Preview role permissions</span></span>

<span data-ttu-id="ccd63-122">若要执行某些操作（如查看邮件头或下载电子邮件内容），必须将名为 *Preview* 的新角色添加到另一个相应的角色组。</span><span class="sxs-lookup"><span data-stu-id="ccd63-122">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate role group.</span></span> <span data-ttu-id="ccd63-123">下表阐明了所需的角色和权限。</span><span class="sxs-lookup"><span data-stu-id="ccd63-123">The following table clarifies required roles and permissions.</span></span>

****

|<span data-ttu-id="ccd63-124">活动</span><span class="sxs-lookup"><span data-stu-id="ccd63-124">Activity</span></span>|<span data-ttu-id="ccd63-125">角色组</span><span class="sxs-lookup"><span data-stu-id="ccd63-125">Role group</span></span>|<span data-ttu-id="ccd63-126">需要预览角色？</span><span class="sxs-lookup"><span data-stu-id="ccd63-126">Preview role needed?</span></span>|
|---|---|---|
|<span data-ttu-id="ccd63-127">使用威胁 (和实时检测功能) 分析威胁</span><span class="sxs-lookup"><span data-stu-id="ccd63-127">Use Threat Explorer (and real-time detections) to analyze threats</span></span> |<span data-ttu-id="ccd63-128">全局管理员</span><span class="sxs-lookup"><span data-stu-id="ccd63-128">Global Administrator</span></span> <p> <span data-ttu-id="ccd63-129">安全管理员</span><span class="sxs-lookup"><span data-stu-id="ccd63-129">Security Administrator</span></span> <p> <span data-ttu-id="ccd63-130">安全读取者</span><span class="sxs-lookup"><span data-stu-id="ccd63-130">Security Reader</span></span>|<span data-ttu-id="ccd63-131">否</span><span class="sxs-lookup"><span data-stu-id="ccd63-131">No</span></span>|
|<span data-ttu-id="ccd63-132">使用威胁 (和实时检测) 查看电子邮件的邮件头，以及预览和下载隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="ccd63-132">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>|<span data-ttu-id="ccd63-133">全局管理员</span><span class="sxs-lookup"><span data-stu-id="ccd63-133">Global Administrator</span></span> <p> <span data-ttu-id="ccd63-134">安全管理员</span><span class="sxs-lookup"><span data-stu-id="ccd63-134">Security Administrator</span></span> <p> <span data-ttu-id="ccd63-135">安全读取者</span><span class="sxs-lookup"><span data-stu-id="ccd63-135">Security Reader</span></span>|<span data-ttu-id="ccd63-136">否</span><span class="sxs-lookup"><span data-stu-id="ccd63-136">No</span></span>|
|<span data-ttu-id="ccd63-137">使用威胁资源管理器查看邮件头、仅在 (电子邮件实体页面中预览电子邮件) 并下载传递到邮箱的电子邮件</span><span class="sxs-lookup"><span data-stu-id="ccd63-137">Use Threat Explorer to view headers, preview email (only in the email entity page) and download email messages delivered to mailboxes</span></span>|<span data-ttu-id="ccd63-138">全局管理员</span><span class="sxs-lookup"><span data-stu-id="ccd63-138">Global Administrator</span></span> <p> <span data-ttu-id="ccd63-139">安全管理员</span><span class="sxs-lookup"><span data-stu-id="ccd63-139">Security Administrator</span></span> <p> <span data-ttu-id="ccd63-140">安全读取者</span><span class="sxs-lookup"><span data-stu-id="ccd63-140">Security Reader</span></span> <p> <span data-ttu-id="ccd63-141">预览</span><span class="sxs-lookup"><span data-stu-id="ccd63-141">Preview</span></span>|<span data-ttu-id="ccd63-142">是</span><span class="sxs-lookup"><span data-stu-id="ccd63-142">Yes</span></span>|
|

> [!NOTE]
> <span data-ttu-id="ccd63-143">*预览* 是一个角色，而不是角色组;必须将 Preview 角色添加到现有角色组中，Office 365 (角色 <https://protection.office.com>) 。</span><span class="sxs-lookup"><span data-stu-id="ccd63-143">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365 (at <https://protection.office.com>).</span></span> <span data-ttu-id="ccd63-144">转到 **"权限"，** 然后编辑现有角色组或添加分配了 **预览** 角色的新角色组。</span><span class="sxs-lookup"><span data-stu-id="ccd63-144">Go to **Permissions**, and then either edit an existing role group or add a new role group with the **Preview** role assigned.</span></span>
> <span data-ttu-id="ccd63-145">全局管理员角色分配有 Microsoft 365 管理中心 () ，安全管理员和安全读者角色在安全& <https://admin.microsoft.com> 合规中心 <https://protection.office.com> () 。</span><span class="sxs-lookup"><span data-stu-id="ccd63-145">The Global Administrator role is assigned the Microsoft 365 admin center (<https://admin.microsoft.com>), and the Security Administrator and Security Reader roles are assigned in the Security & Compliance Center (<https://protection.office.com>).</span></span> <span data-ttu-id="ccd63-146">若要详细了解角色和权限，请参阅 [安全与合规&中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ccd63-146">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="ccd63-147">我们知道预览和下载电子邮件是敏感活动，因此为这些活动启用了审核功能。</span><span class="sxs-lookup"><span data-stu-id="ccd63-147">We understand previewing and downloading email are sensitive activities, and so we auditing is enabled for these.</span></span> <span data-ttu-id="ccd63-148">管理员在电子邮件上执行这些活动后，会生成相同的审核日志，可在 Office 365 安全与合规中心 & <https://protection.office.com> () 。</span><span class="sxs-lookup"><span data-stu-id="ccd63-148">Once an admin performs these activities on emails, audit logs are generated for the same and can be seen in the Office 365 Security & Compliance Center (<https://protection.office.com>).</span></span> <span data-ttu-id="ccd63-149">转到"**搜索**  >  **审核日志搜索"，** 并筛选"搜索"部分中的管理员名称。</span><span class="sxs-lookup"><span data-stu-id="ccd63-149">Go to **Search** > **Audit log search** and filter on the admin name in Search section.</span></span> <span data-ttu-id="ccd63-150">筛选出的结果将显示活动 **AdminMailAccess**。</span><span class="sxs-lookup"><span data-stu-id="ccd63-150">The filtered results will show activity **AdminMailAccess**.</span></span> <span data-ttu-id="ccd63-151">选择一行以查看有关预览或下载的电子邮件的详细信息部分的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ccd63-151">Select a row to view details in the **More information** section about previewed or downloaded email.</span></span>

## <a name="find-suspicious-email-that-was-delivered"></a><span data-ttu-id="ccd63-152">查找已送达的可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="ccd63-152">Find suspicious email that was delivered</span></span>

<span data-ttu-id="ccd63-153">威胁资源管理器是一个功能强大的报告，可用于多种目的，例如查找和删除邮件、标识恶意电子邮件发件人的 IP 地址或启动事件以进一步调查。</span><span class="sxs-lookup"><span data-stu-id="ccd63-153">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="ccd63-154">以下过程重点介绍使用资源管理器查找和删除收件人邮箱中的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-154">The following procedure focuses on using Explorer to find and delete malicious email from recipient's mailboxes.</span></span>

> [!NOTE]
> <span data-ttu-id="ccd63-155">资源管理器中的默认搜索当前不包括"已删除"项目。</span><span class="sxs-lookup"><span data-stu-id="ccd63-155">Default searches in Explorer don't currently include Zapped items.</span></span>  <span data-ttu-id="ccd63-156">这适用于所有视图，例如恶意软件或网络钓鱼视图。</span><span class="sxs-lookup"><span data-stu-id="ccd63-156">This applies to all views, for example malware or phish views.</span></span> <span data-ttu-id="ccd63-157">若要包含 Zapped 项目，你需要添加 **一个"** 传递"操作集，以包含 **"由 ZAP 删除"。**</span><span class="sxs-lookup"><span data-stu-id="ccd63-157">To include Zapped items you need to add a **Delivery action** set to include **Removed by ZAP**.</span></span> <span data-ttu-id="ccd63-158">如果包括所有选项，你将看到所有传递操作结果，包括"已删除的项目"。</span><span class="sxs-lookup"><span data-stu-id="ccd63-158">If you include all options, you'll see all delivery action results, including Zapped items.</span></span>

1. <span data-ttu-id="ccd63-159">**导航到威胁资源管理器**：转到 ，然后使用工作 <https://protection.office.com> 或学校帐户登录Office 365。</span><span class="sxs-lookup"><span data-stu-id="ccd63-159">**Navigate to Threat Explorer**: Go to <https://protection.office.com> and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="ccd63-160">这会将你带去安全&中心。</span><span class="sxs-lookup"><span data-stu-id="ccd63-160">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="ccd63-161">在左侧导航快速启动中，选择"**威胁管理资源管理器** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="ccd63-161">In the left navigation quick-launch, choose **Threat management** \> **Explorer**.</span></span>

    ![具有"传递操作"和"传递位置"字段的资源管理器。](../../media/ThreatExFields.PNG)

    <span data-ttu-id="ccd63-163">你可能会注意到新的" **特殊操作"** 列。</span><span class="sxs-lookup"><span data-stu-id="ccd63-163">You may notice the new **Special actions** column.</span></span> <span data-ttu-id="ccd63-164">此功能旨在告知管理员处理电子邮件的结果。</span><span class="sxs-lookup"><span data-stu-id="ccd63-164">This feature is aimed at telling admins the outcome of processing an email.</span></span> <span data-ttu-id="ccd63-165">可以在 **与** 传递操作和传递位置相同的位置访问特殊 **操作列**。 </span><span class="sxs-lookup"><span data-stu-id="ccd63-165">The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**.</span></span> <span data-ttu-id="ccd63-166">特殊操作可能在威胁资源管理器的电子邮件时间线结束时更新，这是一项旨在为管理员提供更好的搜寻体验的新功能。</span><span class="sxs-lookup"><span data-stu-id="ccd63-166">Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.</span></span>

3. <span data-ttu-id="ccd63-167">**威胁资源管理器中的视图**：在"视图 **"** 菜单中，选择"**所有电子邮件"。**</span><span class="sxs-lookup"><span data-stu-id="ccd63-167">**Views in Threat Explorer**: In the **View** menu, choose **All email**.</span></span>

    ![威胁资源管理器视图菜单和电子邮件 - 恶意软件、网络钓鱼、提交和所有电子邮件选项，以及内容 - 恶意软件。](../../media/tp-InvestigateMalEmail-viewmenu.png)

    <span data-ttu-id="ccd63-169">恶意软件 *视图* 当前为默认视图，并捕获检测到恶意软件威胁的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-169">The *Malware* view is currently the default, and captures emails where a malware threat is detected.</span></span> <span data-ttu-id="ccd63-170">对于 *网络钓鱼* ，网络钓鱼视图的运行方式相同。</span><span class="sxs-lookup"><span data-stu-id="ccd63-170">The *Phish* view operates in the same way, for Phish.</span></span>

    <span data-ttu-id="ccd63-171">但是 *，所有电子邮件* 视图都会列出组织接收的每封邮件，无论是否已检测到威胁。</span><span class="sxs-lookup"><span data-stu-id="ccd63-171">However, *All email* view lists every mail received by the organization, whether threats were detected or not.</span></span> <span data-ttu-id="ccd63-172">正如您想象的那样，这有很多数据，这就是此视图显示要求应用筛选器的占位符的原因。</span><span class="sxs-lookup"><span data-stu-id="ccd63-172">As you can imagine, this is a lot of data, which is why this view shows a placeholder that asks a filter be applied.</span></span> <span data-ttu-id="ccd63-173"> (此视图仅适用于 P2 Office 365 Defender。) </span><span class="sxs-lookup"><span data-stu-id="ccd63-173">(This view is only available for Defender for Office 365 P2 customers.)</span></span>

    <span data-ttu-id="ccd63-174">*提交* 视图显示管理员或用户提交给 Microsoft 的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-174">*Submissions* view shows up all mails submitted by admin or user that were reported to Microsoft.</span></span>

4. <span data-ttu-id="ccd63-175">**威胁资源管理器中的** 搜索和筛选：筛选器显示在搜索栏中页面的顶部，以帮助管理员进行调查。</span><span class="sxs-lookup"><span data-stu-id="ccd63-175">**Search and filter in Threat Explorer**: Filters appear at the top of the page in the search bar to help admins in their investigations.</span></span> <span data-ttu-id="ccd63-176">请注意，可以同时应用多个筛选器，并且向筛选器中添加多个逗号分隔值来缩小搜索范围。</span><span class="sxs-lookup"><span data-stu-id="ccd63-176">Notice that multiple filters can be applied at the same time, and multiple comma-separated values added to a filter to narrow down the search.</span></span> <span data-ttu-id="ccd63-177">请注意:</span><span class="sxs-lookup"><span data-stu-id="ccd63-177">Remember:</span></span>

    - <span data-ttu-id="ccd63-178">筛选器在大多数筛选条件上执行完全匹配。</span><span class="sxs-lookup"><span data-stu-id="ccd63-178">Filters do exact matching on most filter conditions.</span></span>
    - <span data-ttu-id="ccd63-179">主题筛选器使用 CONTAINS 查询。</span><span class="sxs-lookup"><span data-stu-id="ccd63-179">Subject filter uses a CONTAINS query.</span></span>
    - <span data-ttu-id="ccd63-180">URL 筛选器是否与协议一 (一。</span><span class="sxs-lookup"><span data-stu-id="ccd63-180">URL filters work with or without protocols (ex.</span></span> <span data-ttu-id="ccd63-181">https) 。</span><span class="sxs-lookup"><span data-stu-id="ccd63-181">https).</span></span>
    - <span data-ttu-id="ccd63-182">URL 域、URL 路径和 URL 域和路径筛选器不需要协议进行筛选。</span><span class="sxs-lookup"><span data-stu-id="ccd63-182">URL domain, URL path, and URL domain and path filters don't require a protocol to filter.</span></span>
    - <span data-ttu-id="ccd63-183">每次更改筛选器值时，必须单击"刷新"图标才能获得相关结果。</span><span class="sxs-lookup"><span data-stu-id="ccd63-183">You must click the Refresh icon every time you change the filter values to get relevant results.</span></span>

5. <span data-ttu-id="ccd63-184">**高级筛选器**：使用这些筛选器，可以生成复杂的查询并筛选数据集。</span><span class="sxs-lookup"><span data-stu-id="ccd63-184">**Advanced filters**: With these filters, you can build complex queries and filter your data set.</span></span> <span data-ttu-id="ccd63-185">单击" *高级筛选器"* 将打开一个包含选项的飞出区。</span><span class="sxs-lookup"><span data-stu-id="ccd63-185">Clicking on *Advanced Filters* opens a flyout with options.</span></span>

   <span data-ttu-id="ccd63-186">高级筛选是搜索功能的一项补充。</span><span class="sxs-lookup"><span data-stu-id="ccd63-186">Advanced filtering is a great addition to search capabilities.</span></span> <span data-ttu-id="ccd63-187">收件人、发件人和发件人域上引入了布尔 **NOT** 筛选器，以允许管理员通过排除值进行调查。</span><span class="sxs-lookup"><span data-stu-id="ccd63-187">A boolean **NOT** filter has been introduced on *Recipient*, *Sender* and *Sender domain* to allow admins to investigate by excluding values.</span></span> <span data-ttu-id="ccd63-188">此选项显示在 selection 参数"不包含 *"下*。</span><span class="sxs-lookup"><span data-stu-id="ccd63-188">This option appears under selection parameter *Contains none of*.</span></span> <span data-ttu-id="ccd63-189">**NOT** 将允许管理员从调查排除警报邮箱、默认回复邮箱，并且对于管理员搜索特定主题 (subject="Attention") 其中收件人可以设置为无 *defaultMail \@ contoso.com* 的情况很有用。</span><span class="sxs-lookup"><span data-stu-id="ccd63-189">**NOT** will let admins exclude alert mailboxes, default reply mailboxes from their investigations, and is useful for cases where admins search for a specific subject (subject="Attention") where the Recipient can be set to *none of defaultMail\@contoso.com*.</span></span> <span data-ttu-id="ccd63-190">这是精确值搜索。</span><span class="sxs-lookup"><span data-stu-id="ccd63-190">This is an exact value search.</span></span>

   ![Recipients - "Contains none of" Advanced filter.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   <span data-ttu-id="ccd63-192">*按小时* 筛选将帮助组织的安全团队快速向下钻取。</span><span class="sxs-lookup"><span data-stu-id="ccd63-192">*Filtering by hours* will help your organization's security team drill down quickly.</span></span> <span data-ttu-id="ccd63-193">允许的最短持续时间为 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="ccd63-193">The shortest allowed time duration is 30 minutes.</span></span> <span data-ttu-id="ccd63-194">如果可以通过时间范围限制来缩小可疑操作 (例如，它发生在) 3 小时之前，这将限制上下文并帮助找到问题所在。</span><span class="sxs-lookup"><span data-stu-id="ccd63-194">If you can narrow the suspicious action by time-frame (e.g. it happened 3 hours ago), this will limit the context and help pinpoint the problem.</span></span>

   ![按小时筛选选项可缩小数据安全团队必须处理的数据量，最短期限为 30 分钟。](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. <span data-ttu-id="ccd63-196">**威胁资源管理器中的** 字段：威胁资源管理器公开了许多与安全相关的邮件信息，如传递操作、传递位置、特殊操作、*方向性*、替代和 URL *威胁*。 </span><span class="sxs-lookup"><span data-stu-id="ccd63-196">**Fields in Threat Explorer**: Threat Explorer exposes a lot more security-related mail information such as *Delivery action*, *Delivery location*, *Special action*, *Directionality*, *Overrides*, and *URL threat*.</span></span> <span data-ttu-id="ccd63-197">它还允许组织的安全团队以更高的确定性进行调查。</span><span class="sxs-lookup"><span data-stu-id="ccd63-197">It also allows your organization's security team to investigate with a higher certainty.</span></span>

    <span data-ttu-id="ccd63-198">*传递* 操作是对现有策略或检测对电子邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="ccd63-198">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="ccd63-199">以下是电子邮件可以采取的可能操作：</span><span class="sxs-lookup"><span data-stu-id="ccd63-199">Here are the possible actions an email can take:</span></span>

    - <span data-ttu-id="ccd63-200">**已** 送达 - 电子邮件已传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="ccd63-200">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
    - <span data-ttu-id="ccd63-201">**垃圾邮件** (传递到垃圾邮件) – 电子邮件已发送到用户的垃圾邮件文件夹或已删除文件夹，并且用户有权访问其"垃圾邮件"或"已删除"文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-201">**Junked** (Delivered to junk)– email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>
    - <span data-ttu-id="ccd63-202">**已阻止** – 隔离、失败或已丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-202">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="ccd63-203"> (user.) </span><span class="sxs-lookup"><span data-stu-id="ccd63-203">(This is completely inaccessible by the user.)</span></span>
    - <span data-ttu-id="ccd63-204">**已** 替换 – 任何恶意附件替换为.txt附件是恶意附件的文件的电子邮件</span><span class="sxs-lookup"><span data-stu-id="ccd63-204">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious</span></span>

    <span data-ttu-id="ccd63-205">**传递位置**：提供传递位置筛选器，以帮助管理员了解可疑恶意邮件的结束位置以及已对邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="ccd63-205">**Delivery location**: The Delivery location filter is available in order to help admins understand where suspected malicious mail ended-up and what actions were taken on it.</span></span> <span data-ttu-id="ccd63-206">生成的数据可以导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="ccd63-206">The resulting data can be exported to spreadsheet.</span></span> <span data-ttu-id="ccd63-207">可能的传递位置包括：</span><span class="sxs-lookup"><span data-stu-id="ccd63-207">Possible delivery locations are:</span></span>

    - <span data-ttu-id="ccd63-208">**收件箱或文件夹** - 电子邮件位于收件箱或特定文件夹中，根据您的电子邮件规则。</span><span class="sxs-lookup"><span data-stu-id="ccd63-208">**Inbox or folder** – The email is in the Inbox or a specific folder, according to your email rules.</span></span>
    - <span data-ttu-id="ccd63-209">**本地或外部** – 邮箱不存在于云中，但位于本地。</span><span class="sxs-lookup"><span data-stu-id="ccd63-209">**On-prem or external** – The mailbox doesn't exist in the Cloud but is on-premises.</span></span>
    - <span data-ttu-id="ccd63-210">**垃圾邮件** 文件夹 – 电子邮件位于用户的"垃圾邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ccd63-210">**Junk folder** – The email is in a user's Junk mail folder.</span></span>
    - <span data-ttu-id="ccd63-211">**"已删除邮件** "文件夹 – 电子邮件位于用户的"已删除邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ccd63-211">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>
    - <span data-ttu-id="ccd63-212">**隔离** – 隔离中的电子邮件，而不是用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-212">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>
    - <span data-ttu-id="ccd63-213">**失败** – 电子邮件无法到达邮箱。</span><span class="sxs-lookup"><span data-stu-id="ccd63-213">**Failed** – The email failed to reach the mailbox.</span></span>
    - <span data-ttu-id="ccd63-214">**已** 丢弃 - 电子邮件在邮件流中的某处丢失。</span><span class="sxs-lookup"><span data-stu-id="ccd63-214">**Dropped** – The email was lost somewhere in the mail flow.</span></span>

    <span data-ttu-id="ccd63-215">**方向** 性：此选项允许安全运营团队按邮件来自或正在发送的"方向"进行筛选。</span><span class="sxs-lookup"><span data-stu-id="ccd63-215">**Directionality**: This option allows your security operations team to filter by the 'direction' a mail comes from, or is going.</span></span> <span data-ttu-id="ccd63-216">方向性值为 *Inbound、Outbound* 和 *Intra-org* (分别对应于从外部进入组织、从组织发出或内部发送到组织) 。</span><span class="sxs-lookup"><span data-stu-id="ccd63-216">Directionality values are *Inbound*, *Outbound*, and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively).</span></span> <span data-ttu-id="ccd63-217">此信息可帮助安全运营团队发现欺骗和模拟，因为方向性值与 (不匹配。</span><span class="sxs-lookup"><span data-stu-id="ccd63-217">This information can help security operations teams spot spoofing and impersonation, because a mismatch between the Directionality value (ex.</span></span> <span data-ttu-id="ccd63-218">*入站*) 和发件人域 (可能是内部域的域) 显而易见！ </span><span class="sxs-lookup"><span data-stu-id="ccd63-218">*Inbound*), and the domain of the sender (which *appears* to be an internal domain) will be evident!</span></span> <span data-ttu-id="ccd63-219">方向性值是单独的，并且可能与邮件跟踪不同。</span><span class="sxs-lookup"><span data-stu-id="ccd63-219">The Directionality value is separate, and can differ from, the Message Trace.</span></span> <span data-ttu-id="ccd63-220">结果可以导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="ccd63-220">Results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="ccd63-221">**替代**：此筛选器接受出现在邮件详细信息选项卡上的信息，并使用它公开组织策略或用户策略，以允许和阻止邮件已被 *覆盖*。</span><span class="sxs-lookup"><span data-stu-id="ccd63-221">**Overrides**: This filter takes information that appears on the mail's details tab and uses it to expose where organizational, or user policies, for allowing and blocking mails have been *overridden*.</span></span> <span data-ttu-id="ccd63-222">此筛选器最重要的一点就是，它可帮助组织的安全团队查看由于配置而传递的可疑电子邮件数。</span><span class="sxs-lookup"><span data-stu-id="ccd63-222">The most important thing about this filter is that it helps your organization's security team see how many suspicious emails were delivered due to configuration.</span></span> <span data-ttu-id="ccd63-223">这样，他们有机会根据需要修改允许和阻止。</span><span class="sxs-lookup"><span data-stu-id="ccd63-223">This gives them an opportunity to modify allows and blocks as needed.</span></span> <span data-ttu-id="ccd63-224">可以将结果集的此筛选器模板导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="ccd63-224">This result set of this filter can be exported to spreadsheet.</span></span>

    ****

    |<span data-ttu-id="ccd63-225">威胁资源管理器替代</span><span class="sxs-lookup"><span data-stu-id="ccd63-225">Threat Explorer Overrides</span></span>|<span data-ttu-id="ccd63-226">它们的含义</span><span class="sxs-lookup"><span data-stu-id="ccd63-226">What they mean</span></span>|
    |---|---|
    |<span data-ttu-id="ccd63-227">由组织策略允许</span><span class="sxs-lookup"><span data-stu-id="ccd63-227">Allowed by Org Policy</span></span>|<span data-ttu-id="ccd63-228">根据组织策略指示，允许邮件进入邮箱。</span><span class="sxs-lookup"><span data-stu-id="ccd63-228">Mail was allowed into the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="ccd63-229">被组织策略阻止</span><span class="sxs-lookup"><span data-stu-id="ccd63-229">Blocked by Org policy</span></span>|<span data-ttu-id="ccd63-230">邮件被阻止按照组织策略指示发送到邮箱。</span><span class="sxs-lookup"><span data-stu-id="ccd63-230">Mail was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="ccd63-231">组织策略阻止的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="ccd63-231">File extension blocked by Org Policy</span></span>|<span data-ttu-id="ccd63-232">根据组织策略指示，阻止将文件传递至邮箱。</span><span class="sxs-lookup"><span data-stu-id="ccd63-232">File was blocked from delivery to the mailbox as directed by the organization policy.</span></span>|
    |<span data-ttu-id="ccd63-233">用户策略允许</span><span class="sxs-lookup"><span data-stu-id="ccd63-233">Allowed by User Policy</span></span>|<span data-ttu-id="ccd63-234">根据用户策略指示，允许邮件进入邮箱。</span><span class="sxs-lookup"><span data-stu-id="ccd63-234">Mail was allowed into the mailbox as directed by the user policy.</span></span>|
    |<span data-ttu-id="ccd63-235">被用户策略阻止</span><span class="sxs-lookup"><span data-stu-id="ccd63-235">Blocked by User Policy</span></span>|<span data-ttu-id="ccd63-236">邮件被阻止按照用户策略指示发送到邮箱。</span><span class="sxs-lookup"><span data-stu-id="ccd63-236">Mail was blocked from delivery to the mailbox as directed by the user policy.</span></span>|
    |

    <span data-ttu-id="ccd63-237">**URL 威胁**：URL 威胁字段已包含在电子邮件的详细信息选项卡中，用于指示 URL 显示的威胁。</span><span class="sxs-lookup"><span data-stu-id="ccd63-237">**URL threat**: The URL threat field has been included on the *details* tab of an email to indicate the threat presented by a URL.</span></span> <span data-ttu-id="ccd63-238">URL 呈现的威胁可能包括 *恶意软件*、*网络钓鱼* 或 *垃圾邮件*，没有威胁的 URL 在威胁部分中将显示 *"无*"。</span><span class="sxs-lookup"><span data-stu-id="ccd63-238">Threats presented by a URL can include *Malware*, *Phish*, or *Spam*, and a URL with *no threat* will say *None* in the threats section.</span></span>

7. <span data-ttu-id="ccd63-239">**电子邮件时间线视图**：安全运营团队可能需要深入了解电子邮件详细信息，以便进一步调查。</span><span class="sxs-lookup"><span data-stu-id="ccd63-239">**Email timeline view**: Your security operations team might need to deep-dive into email details to investigate further.</span></span> <span data-ttu-id="ccd63-240">电子邮件时间线允许管理员查看对从传递到传递后的电子邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="ccd63-240">The email timeline allows admins to view actions taken on an email from delivery to post-delivery.</span></span> <span data-ttu-id="ccd63-241">若要查看电子邮件时间线，请单击电子邮件的主题，然后单击"电子邮件时间线"。</span><span class="sxs-lookup"><span data-stu-id="ccd63-241">To view an email timeline, click on the subject of an email message, and then click Email timeline.</span></span> <span data-ttu-id="ccd63-242"> ("摘要"或"详细信息"等面板上的其他标题中显示) 可以将这些结果导出到电子表格。</span><span class="sxs-lookup"><span data-stu-id="ccd63-242">(It appears among other headings on the panel like Summary or Details.) These results can be exported to spreadsheet.</span></span>

    <span data-ttu-id="ccd63-243">电子邮件时间线将打开一个表，该表显示电子邮件的所有传递和传递后事件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-243">Email timeline will open to a table that shows all delivery and post-delivery events for the email.</span></span> <span data-ttu-id="ccd63-244">如果电子邮件上没有进一步的操作，应该会看到原始传递的单个事件，该事件指出结果，如"被阻止"，并做出类似 *钓鱼的裁定*。</span><span class="sxs-lookup"><span data-stu-id="ccd63-244">If there are no further actions on the email, you should see a single event for the original delivery that states a result, such as *Blocked*, with a verdict like *Phish*.</span></span> <span data-ttu-id="ccd63-245">管理员可以导出整个电子邮件时间线，包括选项卡上的所有详细信息和电子邮件 (如主题、发件人、收件人、网络和邮件 ID) 。</span><span class="sxs-lookup"><span data-stu-id="ccd63-245">Admins can export the entire email timeline, including all details on the tab and email (such as, Subject, Sender, Recipient, Network, and Message ID).</span></span> <span data-ttu-id="ccd63-246">电子邮件时间线会减少随机化，因为检查不同位置以尝试了解自电子邮件到达后所发生事件所花的时间较少。</span><span class="sxs-lookup"><span data-stu-id="ccd63-246">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="ccd63-247">当在电子邮件上同时发生或接近多个事件时，这些事件会显示在时间线视图中。</span><span class="sxs-lookup"><span data-stu-id="ccd63-247">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span>

8. <span data-ttu-id="ccd63-248">**预览/下载**：威胁资源管理器向安全运营团队提供他们调查可疑电子邮件所需的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ccd63-248">**Preview / download**: Threat Explorer gives your security operations team the details they need to investigate suspicious email.</span></span> <span data-ttu-id="ccd63-249">安全运营团队可以：</span><span class="sxs-lookup"><span data-stu-id="ccd63-249">Your security operations team can either:</span></span>

    - <span data-ttu-id="ccd63-250">[检查传递操作和位置](#check-the-delivery-action-and-location)。</span><span class="sxs-lookup"><span data-stu-id="ccd63-250">[Check the delivery action and location](#check-the-delivery-action-and-location).</span></span>

    - <span data-ttu-id="ccd63-251">[查看电子邮件的时间线](#view-the-timeline-of-your-email)。</span><span class="sxs-lookup"><span data-stu-id="ccd63-251">[View the timeline of your email](#view-the-timeline-of-your-email).</span></span>

### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="ccd63-252">检查传递操作和位置</span><span class="sxs-lookup"><span data-stu-id="ccd63-252">Check the delivery action and location</span></span>

<span data-ttu-id="ccd63-253">在 [威胁 (](threat-explorer.md)和实时检测) 中，现在具有"传递操作"和"传递位置"列，而不是以前的"传递 **状态"** 列。</span><span class="sxs-lookup"><span data-stu-id="ccd63-253">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="ccd63-254">这可更完整地了解电子邮件的陆地位置。</span><span class="sxs-lookup"><span data-stu-id="ccd63-254">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="ccd63-255">此更改的一部分是使调查更易于安全运营团队，但最终结果是一目了然地了解问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="ccd63-255">Part of the goal of this change is to make investigations easier for security operations teams, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="ccd63-256">传递状态现在分为两列：</span><span class="sxs-lookup"><span data-stu-id="ccd63-256">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="ccd63-257">**传递** 操作 - 此电子邮件的状态是什么？</span><span class="sxs-lookup"><span data-stu-id="ccd63-257">**Delivery action** - What is the status of this email?</span></span>

- <span data-ttu-id="ccd63-258">**送达位置** - 此电子邮件作为结果路由在何处？</span><span class="sxs-lookup"><span data-stu-id="ccd63-258">**Delivery location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="ccd63-259">传递操作是对现有策略或检测对电子邮件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="ccd63-259">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="ccd63-260">以下是电子邮件可以采取的可能操作：</span><span class="sxs-lookup"><span data-stu-id="ccd63-260">Here are the possible actions an email can take:</span></span>

- <span data-ttu-id="ccd63-261">**已** 送达 - 电子邮件已传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="ccd63-261">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

- <span data-ttu-id="ccd63-262">**垃圾邮件** – 电子邮件发送到用户的垃圾邮件文件夹或已删除文件夹，并且用户有权访问其"垃圾邮件"或"已删除"文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-262">**Junked** – email was sent to either user's junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

- <span data-ttu-id="ccd63-263">**已阻止** – 隔离、失败或已丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-263">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="ccd63-264"> (user.) </span><span class="sxs-lookup"><span data-stu-id="ccd63-264">(This is completely inaccessible by the user.)</span></span>

- <span data-ttu-id="ccd63-265">**已** 替换 – 任何恶意附件替换为.txt附件是恶意附件的文件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-265">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>

<span data-ttu-id="ccd63-266">传递位置显示运行传递后的策略和检测的结果。</span><span class="sxs-lookup"><span data-stu-id="ccd63-266">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="ccd63-267">它链接到传递操作。</span><span class="sxs-lookup"><span data-stu-id="ccd63-267">It's linked to a Delivery Action.</span></span> <span data-ttu-id="ccd63-268">添加了此字段，可深入了解在发现问题邮件时采取的操作。</span><span class="sxs-lookup"><span data-stu-id="ccd63-268">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="ccd63-269">以下是传递位置的可能值：</span><span class="sxs-lookup"><span data-stu-id="ccd63-269">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="ccd63-270">**收件箱或文件夹** – 电子邮件位于收件箱或文件夹中 (电子邮件规则) 。</span><span class="sxs-lookup"><span data-stu-id="ccd63-270">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

- <span data-ttu-id="ccd63-271">**本地或外部** – 邮箱在云中不存在，但位于本地。</span><span class="sxs-lookup"><span data-stu-id="ccd63-271">**On-prem or external** – The mailbox doesn't exist on cloud but is on-premises.</span></span>

- <span data-ttu-id="ccd63-272">**垃圾邮件** 文件夹 – 电子邮件位于用户的"垃圾邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ccd63-272">**Junk folder** – The email is in a user's Junk folder.</span></span>

- <span data-ttu-id="ccd63-273">**"已删除邮件** "文件夹 – 电子邮件位于用户的"已删除邮件"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ccd63-273">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

- <span data-ttu-id="ccd63-274">**隔离** – 隔离中的电子邮件，而不是用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-274">**Quarantine** – The email in quarantine, and not in a user's mailbox.</span></span>

- <span data-ttu-id="ccd63-275">**失败** – 电子邮件无法到达邮箱。</span><span class="sxs-lookup"><span data-stu-id="ccd63-275">**Failed** – The email failed to reach the mailbox.</span></span>

- <span data-ttu-id="ccd63-276">**已** 丢弃 – 电子邮件在邮件流中的某处丢失。</span><span class="sxs-lookup"><span data-stu-id="ccd63-276">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="ccd63-277">查看电子邮件时间线</span><span class="sxs-lookup"><span data-stu-id="ccd63-277">View the timeline of your email</span></span>

<span data-ttu-id="ccd63-278">**电子邮件时间线** 是威胁资源管理器中的一个字段，可便于安全操作团队进行搜寻。</span><span class="sxs-lookup"><span data-stu-id="ccd63-278">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="ccd63-279">当电子邮件上同时发生或接近同一时间发生多个事件时，这些事件会显示在时间线视图中。</span><span class="sxs-lookup"><span data-stu-id="ccd63-279">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="ccd63-280">"特殊操作"列中会捕获在电子邮件传递后发生的 **一些** 事件。</span><span class="sxs-lookup"><span data-stu-id="ccd63-280">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="ccd63-281">将电子邮件时间线的信息与传递后执行的任何特殊操作相结合，管理员可以深入了解策略和威胁处理 (例如邮件的路由位置，在某些情况下，还了解最终评估) 。</span><span class="sxs-lookup"><span data-stu-id="ccd63-281">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccd63-282">跳转到此处的修正 [主题](remediate-malicious-email-delivered-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="ccd63-282">Jump to a remediation topic [here](remediate-malicious-email-delivered-office-365.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ccd63-283">相关主题</span><span class="sxs-lookup"><span data-stu-id="ccd63-283">Related topics</span></span>

[<span data-ttu-id="ccd63-284">修正邮件中传递的恶意Office 365</span><span class="sxs-lookup"><span data-stu-id="ccd63-284">Remediate malicious email delivered in Office 365</span></span>](remediate-malicious-email-delivered-office-365.md)

[<span data-ttu-id="ccd63-285">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ccd63-285">Microsoft Defender for Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="ccd63-286">防范威胁Office 365</span><span class="sxs-lookup"><span data-stu-id="ccd63-286">Protect against threats in Office 365</span></span>](protect-against-threats.md)

[<span data-ttu-id="ccd63-287">查看 Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ccd63-287">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
