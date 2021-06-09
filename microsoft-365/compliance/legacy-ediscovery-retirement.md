---
title: 旧版电子数据展示工具的停用
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Place电子数据展示和 In-Place 保留 (以及 Exchange Online 中的相应 PowerShell cmdlet) 将于 2020 年上半年停用。 v1.0 Search-Mailbox cmdlet 和 Advanced eDiscovery 1.0 也在同一时间内停用。
ms.openlocfilehash: c5f1ddb4c817ebc316c2e2efdba9a4bc605eb5a2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842658"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="6eb9a-104">旧版电子数据展示工具的停用</span><span class="sxs-lookup"><span data-stu-id="6eb9a-104">Retirement of legacy eDiscovery tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6eb9a-105">Microsoft 一直在评估公众健康情况，并且我们了解这对我们的客户的影响。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-105">Microsoft has been evaluating the public health situation, and we understand the impact this is having on our customers.</span></span> <span data-ttu-id="6eb9a-106">我们希望成为强大的合作伙伴和负责的全球公民。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-106">We want to be strong partners and responsible global citizens.</span></span> <span data-ttu-id="6eb9a-107">为了减轻你面临的众多负担之一，我们将将本文中所述的旧式电子数据展示工具的计划停用延迟三个月。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-107">To ease one of the many burdens you are facing, we are going to delay the scheduled retirement for the legacy eDiscovery tools described in this article by three months.</span></span> <span data-ttu-id="6eb9a-108">**更新后的停用日期将在下面反映出来。**</span><span class="sxs-lookup"><span data-stu-id="6eb9a-108">**The updated retirement dates are reflected below.**</span></span>

<span data-ttu-id="6eb9a-109">多年来，Microsoft 提供了电子数据展示工具，让你可以搜索、预览和导出电子邮件Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-109">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="6eb9a-110">但是，这些工具不再提供在其他 Microsoft 365 服务（如 SharePoint Online 和 Microsoft 365 组）中搜索非 Exchange 内容的有效方式。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-110">However, these tools no longer offer an effective way to search for non-Exchange content in other Microsoft 365 services, such as SharePoint Online and Microsoft 365 Groups.</span></span> <span data-ttu-id="6eb9a-111">为解决这一问题，Microsoft 提供了其他电子数据展示工具，可帮助你搜索各种Microsoft 365内容。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-111">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Microsoft 365 content.</span></span> <span data-ttu-id="6eb9a-112">我们一直在致力于将最新且强大的电子数据展示功能纳入Microsoft 365[中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-112">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="6eb9a-113">这使组织可以响应跨多个服务（包括 Exchange Online）对内容的法律、内部和其他Microsoft 365请求。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-113">This allows organizations to respond to legal, internal, and other document requests for content across many Microsoft 365 services, including Exchange Online.</span></span>

<span data-ttu-id="6eb9a-114">由于 Microsoft 365 合规中心中新增和改进了电子数据展示功能，我们将停用以下与搜索 Exchange Online 和 Microsoft 365 中的电子邮件内容相关的电子数据展示相关特性和功能：</span><span class="sxs-lookup"><span data-stu-id="6eb9a-114">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Microsoft 365:</span></span>

- <span data-ttu-id="6eb9a-115">[就地电子数据展示](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)管理[中心内](/exchange/security-and-compliance/create-or-remove-in-place-holds)设置Exchange就地保留。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-115">[In-Place eDiscovery](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="6eb9a-116">支持 In-Place 电子数据展示和 In-Place 保留的 Exchange Online PowerShell cmdlet (统称为 \**-MailboxSearch* cmdlet) 。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-116">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="6eb9a-117">这包括以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6eb9a-117">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="6eb9a-118">New-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="6eb9a-118">New-MailboxSearch</span></span>](/powershell/module/exchange/new-mailboxsearch)

  - [<span data-ttu-id="6eb9a-119">Start-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="6eb9a-119">Start-MailboxSearch</span></span>](/powershell/module/exchange/start-mailboxsearch)

  - [<span data-ttu-id="6eb9a-120">Stop-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="6eb9a-120">Stop-MailboxSearch</span></span>](/powershell/module/exchange/stop-mailboxsearch)

  - [<span data-ttu-id="6eb9a-121">Set-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="6eb9a-121">Set-MailboxSearch</span></span>](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="6eb9a-122">[Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch)和[Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) cmdlet 将在其他 \*\*\*\*-MailboxSearch\*\*\* cmdlet 停用后可用，以便您可以使用它们来帮助转换到其他电子数据展示和保留工具。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-122">The [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*\* cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="6eb9a-123">但是，在下面引用 (日期后) Microsoft 支持将不再支持这两个 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-123">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="6eb9a-124">PowerShell 中的[Search-Mailbox](/powershell/module/exchange/search-mailbox) cmdlet Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-124">The [Search-Mailbox](/powershell/module/exchange/search-mailbox) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="6eb9a-125">web 服务 API 中的Exchange操作：</span><span class="sxs-lookup"><span data-stu-id="6eb9a-125">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="6eb9a-126">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="6eb9a-126">GetSearchableMailboxes</span></span>](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="6eb9a-127">SearchMailboxes</span><span class="sxs-lookup"><span data-stu-id="6eb9a-127">SearchMailboxes</span></span>](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [<span data-ttu-id="6eb9a-128">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="6eb9a-128">SetHoldOnMailboxes</span></span>](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="6eb9a-129">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="6eb9a-129">GetHoldOnMailboxes</span></span>](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="6eb9a-130">[Office 365 高级电子数据展示 v1.0，](./overview-ediscovery-20.md)这是第一个版本的 Advanced eDiscovery，可以通过 Office 365 安全与合规中心中的核心电子数据展示&访问。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-130">[Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), which is the first version of Advanced eDiscovery that's accessed through a Core eDiscovery case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="6eb9a-131">停用 Advanced eDiscovery v1.0 不会影响创建和管理核心电子数据展示事例的能力。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-131">The retirement of Advanced eDiscovery v1.0 doesn't impact your ability to create and manage Core eDiscovery cases.</span></span>

> [!NOTE]
> <span data-ttu-id="6eb9a-132">要停用的电子数据展示功能仅适用于基于云的 Microsoft 365 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-132">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="6eb9a-133">本地版本的 Exchange 和 SharePoint 中的电子数据展示功能仍将受支持，直到进一步通知为止。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-133">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="6eb9a-134">本文中的以下各节提供有关要停用的每个功能的指导。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-134">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="6eb9a-135">此信息包括日程表和替代工具，您可以使用它们，而不是停用的工具。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-135">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="6eb9a-136">In-Place管理中心In-Place电子数据展示Exchange保留</span><span class="sxs-lookup"><span data-stu-id="6eb9a-136">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="6eb9a-137">根据 2017 年 7 月 1 日的原始通知，Exchange EAC () 中的 In-Place 电子数据展示 & 保留功能即将停用。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-137">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="6eb9a-138">EAC In-Place电子数据展示&保留"页面允许搜索、保留和导出来自 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-138">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="6eb9a-139">In-Place电子数据展示还让您将搜索结果复制到发现邮箱，以便您或其他电子数据展示管理员能够查看内容，使其可用于法律、法规和公共请求。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-139">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="6eb9a-140">由于除将搜索结果复制到发现邮箱) 之外，所有这些功能现在均可用于 Microsoft 365 合规中心 (中的内容搜索、电子数据展示和[Advanced eDiscovery](./microsoft-365-compliance-center.md)工具，这些功能、可靠性和对各种 Microsoft 365 服务) 的支持已改进，我们建议您尽快开始使用这些工具。 (</span><span class="sxs-lookup"><span data-stu-id="6eb9a-140">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](./microsoft-365-compliance-center.md) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="6eb9a-141">为了帮助你转换到这些其他电子数据展示工具，下表列出了可以使用的工具，而不是In-Place电子数据展示In-Place保留。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-141">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="6eb9a-142">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="6eb9a-142">Scope of affected organizations</span></span>

- <span data-ttu-id="6eb9a-143">Office 365 和 Microsoft 365 企业版 组织</span><span class="sxs-lookup"><span data-stu-id="6eb9a-143">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="6eb9a-144">Office 365和Microsoft 365 教育版组织</span><span class="sxs-lookup"><span data-stu-id="6eb9a-144">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="6eb9a-145">Office 365和Microsoft 365政府组织;这包括GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="6eb9a-145">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="6eb9a-146">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="6eb9a-146">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="6eb9a-147">停用时间线</span><span class="sxs-lookup"><span data-stu-id="6eb9a-147">Timeline for retirement</span></span>

- <span data-ttu-id="6eb9a-148">2020 年 7 月 1 日：无法创建新的搜索和保留，但仍可以自行运行、编辑和删除现有搜索。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-148">July 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="6eb9a-149">Microsoft 支持将不再In-Place EAC &电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-149">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="6eb9a-150">2020 年 10 月 1 日：In-Place EAC 中的 & 电子数据展示保留功能将置于只读模式。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-150">October 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="6eb9a-151">这意味着你只能删除现有搜索和保留。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-151">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="6eb9a-152">替代工具</span><span class="sxs-lookup"><span data-stu-id="6eb9a-152">Alternative tools</span></span>

<span data-ttu-id="6eb9a-153">下表介绍了可用于替换即将停用的现有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-153">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="6eb9a-154">功能</span><span class="sxs-lookup"><span data-stu-id="6eb9a-154">Functionality</span></span></th>
<th><span data-ttu-id="6eb9a-155">替代工具</span><span class="sxs-lookup"><span data-stu-id="6eb9a-155">Alternative tool</span></span></th>
<th><span data-ttu-id="6eb9a-156">备注</span><span class="sxs-lookup"><span data-stu-id="6eb9a-156">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6eb9a-157">出于法律目的搜索、导出和保留</span><span class="sxs-lookup"><span data-stu-id="6eb9a-157">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="6eb9a-158">Microsoft 365合规中心中的核心电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="6eb9a-158">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="6eb9a-159">使用核心电子数据展示事例的功能为电子数据展示和保留In-Place奇偶校验In-Place奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-159">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="6eb9a-160">其中包括：</span><span class="sxs-lookup"><span data-stu-id="6eb9a-160">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="6eb9a-161">搜索扩展到数百万个位置</span><span class="sxs-lookup"><span data-stu-id="6eb9a-161">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="6eb9a-162">搜索、导出和将内容置于保留状态的可靠性更高</span><span class="sxs-lookup"><span data-stu-id="6eb9a-162">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="6eb9a-163">搜索 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer 组、Microsoft 365 组和其他存储在 Office 365 应用程序中的内容</span><span class="sxs-lookup"><span data-stu-id="6eb9a-163">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Microsoft 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="6eb9a-164">保留出于保留目的</span><span class="sxs-lookup"><span data-stu-id="6eb9a-164">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="6eb9a-165">Microsoft 365合规中心中的保留策略</span><span class="sxs-lookup"><span data-stu-id="6eb9a-165">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="6eb9a-166">可以使用保留策略来保留内容，如果需要，可以在保留期到期后将其删除。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-166">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="6eb9a-167">其他功能包括：</span><span class="sxs-lookup"><span data-stu-id="6eb9a-167">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="6eb9a-168">将策略应用于整个组织</span><span class="sxs-lookup"><span data-stu-id="6eb9a-168">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="6eb9a-169">将策略应用于特定内容位置，如 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams 和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="6eb9a-169">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="6eb9a-170">将策略应用于特定用户</span><span class="sxs-lookup"><span data-stu-id="6eb9a-170">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="6eb9a-171">有关详细信息，请参阅 <a href="/microsoft-365/compliance/retention-policies"> 了解保留策略和保留标签</a>。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-171">For more information, see <a href="/microsoft-365/compliance/retention-policies"> Learn about retention policies and retention labels</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6eb9a-172">将电子邮件搜索结果复制到发现邮箱进行审阅</span><span class="sxs-lookup"><span data-stu-id="6eb9a-172">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="6eb9a-173">v2.0 Advanced eDiscovery审阅集</span><span class="sxs-lookup"><span data-stu-id="6eb9a-173">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="6eb9a-174">查看网站Microsoft 365从未如此简单过。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-174">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="6eb9a-175">审阅集有许多出色的功能，可帮助减少查看所需的时间和数据，包括：</span><span class="sxs-lookup"><span data-stu-id="6eb9a-175">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="6eb9a-176">执行快速搜索查询并筛选审阅集内的内容</span><span class="sxs-lookup"><span data-stu-id="6eb9a-176">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="6eb9a-177">分析审阅集内的内容;这包括电子邮件线程、近重复检测、主题分析和预测编码</span><span class="sxs-lookup"><span data-stu-id="6eb9a-177">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="6eb9a-178">标记审阅集中的文档</span><span class="sxs-lookup"><span data-stu-id="6eb9a-178">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="6eb9a-179">用于帮助识别律师客户特权内容的标记建议</span><span class="sxs-lookup"><span data-stu-id="6eb9a-179">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="6eb9a-180">有关详细信息，请参阅 <a href="/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 中的高级电子数据展示解决方案概述</a>。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-180">For more information, see <a href="/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="6eb9a-181">或者，可以将搜索结果导出到 PST 文件，然后使用 Microsoft 365 导入服务将 PST 导入发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-181">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="6eb9a-182">有关分步说明，请参阅使用网络上传将<a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">PST 文件导入Office 365。</a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-182">For step-by-step instruction, see <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class=even>
  <td><span data-ttu-id="6eb9a-183">将邮件从一个邮箱复制到另一个邮箱</span><span class="sxs-lookup"><span data-stu-id="6eb9a-183">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="6eb9a-184"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-184"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="6eb9a-185">若要向某人授予访问其他用户的电子邮件的权限 (例如当员工离开您的组织，并且您需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-185">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="6eb9a-186">因此，只需为用户分配访问源邮箱的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-186">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>
<tr class="odd">
<td><span data-ttu-id="6eb9a-187">从"可恢复的项目"文件夹中还原项目</span><span class="sxs-lookup"><span data-stu-id="6eb9a-187">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="6eb9a-188"><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="6eb9a-188"><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="6eb9a-189">只要项目的已删除项目保留期尚未 (，就可以还原永久删除的项目) <i></i>也称为邮箱中的软删除项目。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-189">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="6eb9a-190">有关详细信息，请参阅"可<a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">恢复的项目"文件夹Exchange Online。</a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-190">For more information, see <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="6eb9a-191">有关电子数据展示In-Place保留的常见问题In-Place常见问题</span><span class="sxs-lookup"><span data-stu-id="6eb9a-191">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="6eb9a-192">**我在 EAC 中In-Place电子数据展示&保留的复制搜索结果功能，将搜索结果复制到发现邮箱，供律师审查。我现具有哪些选项？**</span><span class="sxs-lookup"><span data-stu-id="6eb9a-192">**I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?**</span></span>

<span data-ttu-id="6eb9a-193">目前，有两种方法可以复制此功能。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-193">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="6eb9a-194">第一种是在[v2.0 Advanced eDiscovery审阅集](./view-documents-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-194">The first is to use [review sets in Advanced eDiscovery v2.0](./view-documents-in-review-set.md).</span></span> <span data-ttu-id="6eb9a-195">在传统审阅工具（如快速搜索文档、标记、电子邮件线程、近乎重复的分组、主题分析和预测编码）中，审阅集有许多相同的功能。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-195">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="6eb9a-196">如果仍要使用发现邮箱进行审阅，则第二个选项是，将搜索结果导出到 PST 文件，然后使用 Microsoft 合规中心中的 PST 导入功能将 [PST](use-network-upload-to-import-pst-files.md) 文件导入发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-196">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="6eb9a-197">**如何控制电子数据展示 (可以使用新工具) 搜索哪些内容位置，例如邮箱或网站？**</span><span class="sxs-lookup"><span data-stu-id="6eb9a-197">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="6eb9a-198">合规性Microsoft 365中心还使用合规性边界来控制电子[](set-up-compliance-boundaries.md)数据展示管理员可搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-198">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="6eb9a-199">合规性边界在政府实体中非常有用，这些实体需要位于机构边界内，或者需要遵守地理边界的跨国公司。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-199">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="6eb9a-200">**如何将当前搜索和保留移动到Microsoft 365中心？**</span><span class="sxs-lookup"><span data-stu-id="6eb9a-200">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="6eb9a-201">通过使用 PowerShell，In-Place EAC 迁移电子数据展示搜索和保留。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-201">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="6eb9a-202">有关说明，请参阅[将搜索和保留从 EAC 迁移到Microsoft 365中心](./migrate-legacy-ediscovery-searches-and-holds.md)。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-202">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](./migrate-legacy-ediscovery-searches-and-holds.md).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="6eb9a-203">\*-MailboxSearch cmdlet</span><span class="sxs-lookup"><span data-stu-id="6eb9a-203">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="6eb9a-204">根据 2017 年 7 月 1 日 Exchange 管理中心中宣布的原始通知，In-Place 电子数据展示 & 保留功能以及相应的 **\* -MailboxSearch** cmdlet 将停用。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-204">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="6eb9a-205">这些 cmdlet 使用户能够针对法律、法规和公共请求搜索、保留和导出邮箱内容。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-205">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="6eb9a-206">由于这些功能现在在 Microsoft 365 合规中心和[<span class="underline">Office 365</span>](./microsoft-365-compliance-center.md) & 安全与合规中心 PowerShell 中可用，具有改进的性能和可伸缩性，因此您应该使用这些改进的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-206">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](./microsoft-365-compliance-center.md) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="6eb9a-207">这些 cmdlet 包括[<span class="underline">-ComplianceCase、-ComplianceSearch、-CaseHoldPolicy、-CaseHoldRule \* </span>](/powershell/module/exchange/get-compliancecase)和[<span class="underline"> \* -ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction)。 [<span class="underline"> \* </span>](/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdrule)</span><span class="sxs-lookup"><span data-stu-id="6eb9a-207">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="6eb9a-208">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="6eb9a-208">Scope of affected organizations</span></span>

- <span data-ttu-id="6eb9a-209">Office 365 和 Microsoft 365 企业版 组织</span><span class="sxs-lookup"><span data-stu-id="6eb9a-209">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="6eb9a-210">Office 365和Microsoft 365 教育版组织</span><span class="sxs-lookup"><span data-stu-id="6eb9a-210">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="6eb9a-211">Office 365和Microsoft 365政府组织;这包括GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="6eb9a-211">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="6eb9a-212">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="6eb9a-212">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="6eb9a-213">日程表</span><span class="sxs-lookup"><span data-stu-id="6eb9a-213">Timeline</span></span>

- <span data-ttu-id="6eb9a-214">2020 年 7 月 1 日：你将无法使用 **New-MailboxSearch** 创建新的 In-Place 电子数据展示搜索和 In-Place 保留，但你仍可以使用 cmdlet 运行、编辑和删除现有搜索和保留，并自行承担风险。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-214">July 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="6eb9a-215">Microsoft 支持将不再为这些类型的搜索和保留提供帮助。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-215">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="6eb9a-216">2020 年 10 月 1 日：如前所述，EAC 中的 In-Place 电子数据展示 & 保留功能将置于只读模式。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-216">October 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="6eb9a-217">这也意味着你将无法使用 **New-MailboxSearch、Start-MailboxSearch** 或 **Set-MailboxSearch** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-217">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="6eb9a-218">你只能获取和删除现有搜索和保留。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-218">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="6eb9a-219">替代工具</span><span class="sxs-lookup"><span data-stu-id="6eb9a-219">Alternative tools</span></span>

<span data-ttu-id="6eb9a-220">下表介绍了可用于替换即将停用的现有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-220">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="6eb9a-221">功能</span><span class="sxs-lookup"><span data-stu-id="6eb9a-221">Functionality</span></span></th>
<th><span data-ttu-id="6eb9a-222">替代工具</span><span class="sxs-lookup"><span data-stu-id="6eb9a-222">Alternative tools</span></span></th>
<th><span data-ttu-id="6eb9a-223">备注</span><span class="sxs-lookup"><span data-stu-id="6eb9a-223">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6eb9a-224">搜索和导出</span><span class="sxs-lookup"><span data-stu-id="6eb9a-224">Search and export</span></span></td>
<td><p><span data-ttu-id="6eb9a-225"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-225"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="6eb9a-226"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-226"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="6eb9a-227"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-227"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="6eb9a-228">ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和导出内容。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-228">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="6eb9a-229">可以使用<strong>New-、Get-</strong>和<strong>Start-ComplianceSearch</strong> <strong></strong>cmdlet 创建新的搜索并查看搜索估计值。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-229">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="6eb9a-230">然后，您可以使用 <strong>New-ComplianceSearchAction</strong> cmdlet 导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-230">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="6eb9a-231">你仍必须使用此合规性中心中的核心电子数据展示Microsoft 365将搜索结果下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-231">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="6eb9a-232"><strong>注意：</strong>如果您使用这些 cmdlet 创建与核心电子数据展示案例不关联的搜索，这些搜索将位于 Microsoft 365 合规中心的内容搜索页面上。 <strong></strong></span><span class="sxs-lookup"><span data-stu-id="6eb9a-232"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6eb9a-233">保留邮箱中的内容</span><span class="sxs-lookup"><span data-stu-id="6eb9a-233">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="6eb9a-234"><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-234"><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="6eb9a-235"><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-235"><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="6eb9a-236"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-236"><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="6eb9a-237">合规性Microsoft 365中的保留项必须与 ComplianceCase 相关联。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-237">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="6eb9a-238">首先，创建合规性案例，然后创建 CaseHoldPolicy 和 CaseHoldRule。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-238">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="6eb9a-239"><strong>注意：</strong> 创建 CaseHoldPolicy 而不创建 CaseHoldRule 将使保留不可操作，直到创建 CaseHoldRule 并关联到 CaseHoldPolicy。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-239"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="6eb9a-240">有关详细信息，请参阅 cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-240">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6eb9a-241">将搜索结果复制到发现邮箱</span><span class="sxs-lookup"><span data-stu-id="6eb9a-241">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="6eb9a-242">无</span><span class="sxs-lookup"><span data-stu-id="6eb9a-242">None</span></span></td>
<td><span data-ttu-id="6eb9a-243">此功能没有直接替代，因为它不提供访问所有 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-243">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="6eb9a-244">有关替代解决方案，请参阅下面的常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-244">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
  <tr class=even>
  <td><span data-ttu-id="6eb9a-245">将邮件从一个邮箱复制到另一个邮箱</span><span class="sxs-lookup"><span data-stu-id="6eb9a-245">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="6eb9a-246"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-246"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="6eb9a-247">若要向某人授予访问其他用户的电子邮件的权限 (例如当员工离开您的组织，并且您需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-247">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="6eb9a-248">因此，只需为用户分配访问源邮箱的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-248">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="6eb9a-249">关于 \***-MailboxSearch** cmdlet 的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="6eb9a-249">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="6eb9a-250">**我们使用复制搜索导出电子邮件或即时消息，以便进行其他电子数据展示和法律调查。这些 cmdlet 停用后，我们还有其他哪些选项？**</span><span class="sxs-lookup"><span data-stu-id="6eb9a-250">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="6eb9a-251">[<span class="underline">Microsoft Graph API</span>](https://developer.microsoft.com/en-us/graph)提供了多种用于提取数据的方法，用于进行分析和其他用途，这些方法比使用 **\* -MailboxSearch** cmdlet 具有更多的弹性和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-251">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="6eb9a-252">**如何将我的搜索和保留迁移到Microsoft 365中心？**</span><span class="sxs-lookup"><span data-stu-id="6eb9a-252">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="6eb9a-253">通过使用 PowerShell 脚本，In-Place电子数据展示搜索和保留Exchange从管理中心迁移。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-253">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="6eb9a-254">有关详细信息，请参阅将[旧版电子数据展示搜索和保留](migrate-legacy-eDiscovery-searches-and-holds.md)迁移到Microsoft 365中心。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-254">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="6eb9a-255">**停用 cmdlet 后，我是否仍能够删除或检索搜索？**</span><span class="sxs-lookup"><span data-stu-id="6eb9a-255">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="6eb9a-256">可以，尽管我们正在删除创建和修改搜索功能，但您仍可以使用 **Get-MailboxSearch** 和 **Remove-MailboxSearch，** 直到进一步通知为止。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-256">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="6eb9a-257">但是，停用日期后使用这些 cmdlet 将自行承担风险，并且 Microsoft 支持将不再能够提供帮助。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-257">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="6eb9a-258">Search-Mailbox cmdlet</span><span class="sxs-lookup"><span data-stu-id="6eb9a-258">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="6eb9a-259">PowerShell 中的 **Search-Mailbox** cmdlet Exchange Online从 2018 年开始在 cmdlet 输出的警告中最初宣布停用。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-259">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="6eb9a-260">**Search-Mailbox** cmdlet 最初用于搜索用户的邮箱并清除恶意内容。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-260">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="6eb9a-261">我们建议您开始使用 Office 365 & 安全与合规中心 PowerShell 中的 **New-ComplianceSearch** 和 **New-ComplianceSearchAction** cmdlet 来搜索和清除内容。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-261">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="6eb9a-262">对于内置安全体验，Microsoft 365[<span class="underline">安全功能</span>](../security/index.yml)为电子邮件和许多其他安全环境提供强大的威胁Microsoft 服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-262">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](../security/index.yml) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="6eb9a-263">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="6eb9a-263">Scope of affected organizations</span></span>

- <span data-ttu-id="6eb9a-264">Office 365 和 Microsoft 365 企业版 组织</span><span class="sxs-lookup"><span data-stu-id="6eb9a-264">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="6eb9a-265">Office 365和Microsoft 365 教育版组织</span><span class="sxs-lookup"><span data-stu-id="6eb9a-265">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="6eb9a-266">Office 365和Microsoft 365政府组织;这包括GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="6eb9a-266">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="6eb9a-267">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="6eb9a-267">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="6eb9a-268">日程表</span><span class="sxs-lookup"><span data-stu-id="6eb9a-268">Timeline</span></span>

-  <span data-ttu-id="6eb9a-269">2020 年 7 月 1 日 **：Search-Mailbox** cmdlet 将不再可用，Microsoft 支持将不再提供帮助。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-269">July 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="6eb9a-270">替代工具</span><span class="sxs-lookup"><span data-stu-id="6eb9a-270">Alternative tools</span></span>

<span data-ttu-id="6eb9a-271">下表介绍了可用于替换即将停用的现有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-271">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="6eb9a-272">功能</span><span class="sxs-lookup"><span data-stu-id="6eb9a-272">Functionality</span></span></th>
<th><span data-ttu-id="6eb9a-273">替代工具</span><span class="sxs-lookup"><span data-stu-id="6eb9a-273">Alternative tools</span></span></th>
<th><span data-ttu-id="6eb9a-274">备注</span><span class="sxs-lookup"><span data-stu-id="6eb9a-274">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6eb9a-275">搜索邮箱</span><span class="sxs-lookup"><span data-stu-id="6eb9a-275">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="6eb9a-276"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-276"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="6eb9a-277"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-277"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="6eb9a-278">ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和导出内容。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-278">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="6eb9a-279">可以使用<strong>New-、Get-</strong>和<strong>Start-ComplianceSearch</strong> <strong></strong>cmdlet 创建新的搜索并查看搜索估计值。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-279">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="6eb9a-280">然后，可以使用 <strong>New-ComplianceSearchAction -Export</strong> 命令导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-280">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="6eb9a-281">你仍必须使用此合规性中心中的核心电子数据展示Microsoft 365将搜索结果下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-281">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="6eb9a-282">从邮箱中删除批量电子邮件</span><span class="sxs-lookup"><span data-stu-id="6eb9a-282">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="6eb9a-283"><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">设置邮箱的存档和删除策略</span></a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-283"><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="6eb9a-284">管理员可以创建存档和删除策略，该策略会自动将项目移动到用户的存档邮箱，并自动从邮箱中删除项目。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-284">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="6eb9a-285">将搜索结果复制到发现邮箱</span><span class="sxs-lookup"><span data-stu-id="6eb9a-285">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="6eb9a-286">此功能没有直接替代，因为它不提供访问所有 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-286">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="6eb9a-287">有关替代解决方案，请参阅 <strong>\*-MailboxSearch cmdlets</strong> 部分中的常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-287">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
<tr class=odd>
  <td><span data-ttu-id="6eb9a-288">将邮件从一个邮箱复制到另一个邮箱</span><span class="sxs-lookup"><span data-stu-id="6eb9a-288">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="6eb9a-289"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-289"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="6eb9a-290">若要向某人授予访问其他用户的电子邮件的权限 (例如当员工离开您的组织，并且您需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-290">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="6eb9a-291">因此，只需为用户分配访问源邮箱的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-291">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
</tr>
<tr class=even>
  <td><span data-ttu-id="6eb9a-292">清除邮箱中的邮件</span><span class="sxs-lookup"><span data-stu-id="6eb9a-292">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="6eb9a-293"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-293"><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="6eb9a-294"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-294"><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="6eb9a-295">ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和清除内容。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-295">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="6eb9a-296">可以使用 <strong>New-ComplianceSearch</strong> 和 <strong>New-ComplianceSearch</strong> cmdlet 创建并运行搜索，然后可以使用 <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> 命令清除内容。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-296">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="6eb9a-297">有关详细信息，请参阅搜索 <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">和删除邮件</span></a>。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-297">For more information, see <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd"> 
<td><span data-ttu-id="6eb9a-298">清除邮箱中的邮件</span><span class="sxs-lookup"><span data-stu-id="6eb9a-298">Purge messages from a mailbox</span></span></td>
<td><span data-ttu-id="6eb9a-299"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></span><span class="sxs-lookup"><span data-stu-id="6eb9a-299"><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
<td><span data-ttu-id="6eb9a-300">若要清除邮箱中的邮件，请分配管理员权限以访问员工的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-300">To purge messages from a mailbox, assign an administrator permissions to access the employee's mailbox.</span></span> <span data-ttu-id="6eb9a-301">可根据需要删除和回收邮件，以利用邮件中内置的搜索和查看Outlook。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-301">Messages can be deleted and recycled as needed taking advantage of the built in search and viewing capabilities in Outlook.</span></span></td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a><span data-ttu-id="6eb9a-302">ExchangeWeb 服务 API 操作</span><span class="sxs-lookup"><span data-stu-id="6eb9a-302">Exchange Web Services API operations</span></span>

<span data-ttu-id="6eb9a-303">Exchange Web 服务 API 中的这些操作由 Exchange 管理中心中的 In-Place 电子数据展示 & 保留功能以及 Exchange Online PowerShell 中的相应 **\* -MailboxSearch** cmdlet 使用。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-303">These operations in the Exchange Web Services API are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="6eb9a-304">作为停用其他旧版电子数据展示工具的一部分，它们也将停用。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-304">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="6eb9a-305">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="6eb9a-305">Scope of affected organizations</span></span>

- <span data-ttu-id="6eb9a-306">Office 365 和 Microsoft 365 企业版 组织</span><span class="sxs-lookup"><span data-stu-id="6eb9a-306">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="6eb9a-307">Office 365和Microsoft 365 教育版组织</span><span class="sxs-lookup"><span data-stu-id="6eb9a-307">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="6eb9a-308">Office 365和Microsoft 365政府组织;这包括GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="6eb9a-308">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="6eb9a-309">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="6eb9a-309">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="6eb9a-310">日程表</span><span class="sxs-lookup"><span data-stu-id="6eb9a-310">Timeline</span></span>

- <span data-ttu-id="6eb9a-311">2020 年 7 月 1 日：GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 操作将不再可用，并且 Microsoft 支持将不再提供帮助。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-311">July 1, 2020: The GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="6eb9a-312">Advanced eDiscovery v1.0</span><span class="sxs-lookup"><span data-stu-id="6eb9a-312">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="6eb9a-313">Advanced eDiscovery v1.0 版本（即核心电子数据展示Advanced eDiscovery切换到 Advanced eDiscovery）中可用的版本）即将停用。 </span><span class="sxs-lookup"><span data-stu-id="6eb9a-313">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in a core eDiscovery case by clicking **Switch to Advanced eDiscovery**, is being retired.</span></span> <span data-ttu-id="6eb9a-314">其功能已由 Advanced eDiscovery[合规](./ediscovery.md)中心中的Microsoft 365解决方案取代。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-314">Its functionality has been replaced by the new [Advanced eDiscovery solution](./ediscovery.md) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="6eb9a-315">若要确定您的组织是否正在使用 Advanced eDiscovery v1.0：</span><span class="sxs-lookup"><span data-stu-id="6eb9a-315">To determine if your organization is using Advanced eDiscovery v1.0:</span></span>

1. <span data-ttu-id="6eb9a-316">转到安全Office 365[合规&中心](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-316">Go to the [Office 365 Security & Compliance Center](https://protection.office.com).</span></span>

2. <span data-ttu-id="6eb9a-317">在安全与合规中心的左侧导航窗格中，&电子数据展示> **电子** 数据展示"，然后打开核心电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-317">In the left navigation pane of the Security & Compliance Center, click **eDiscovery > eDiscovery**, and open a Core eDiscovery case.</span></span>

3. <span data-ttu-id="6eb9a-318">如果看到"切换到Advanced eDiscovery"按钮，则单击此按钮将进入即将停用的 1.0 Advanced eDiscovery版本。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-318">If you see the **Switch to Advanced eDiscovery** button, then clicking it will take you to the 1.0 version of Advanced eDiscovery, which is being retired.</span></span> <span data-ttu-id="6eb9a-319">在核心电子数据展示中创建和管理事例的能力不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-319">The ability to create and manage cases in Core eDiscovery won't be affected.</span></span> <span data-ttu-id="6eb9a-320">只有在 v1.0 Advanced eDiscovery中通过单击"切换到 ("来添加和分析案例数据Advanced eDiscovery) 停用。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-320">Only the ability to add and analyze case data in Advanced eDiscovery v1.0 (by clicking **Switch to Advanced eDiscovery**) is being retired.</span></span>

<span data-ttu-id="6eb9a-321">Microsoft 365 (中新的 Advanced eDiscovery 解决方案（也称为 *Advanced eDiscovery v2.0*) ）提供了原始解决方案的所有功能，但现在包括一种基于保管人的方法，用于识别其他 Microsoft 365 服务中的内容、收集该内容，然后将它添加到审阅集，审阅者可以利用快速搜索查询、标记和分析功能来帮助剔除相关文档。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-321">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="6eb9a-322">Advanced eDiscovery包括针对 Microsoft 和非 Microsoft 文件类型的改进处理和本机查看器，文件类型的完整列表在此处，支持的元数据字段[在此处](./document-metadata-fields-in-advanced-ediscovery.md)。 [](./supported-filetypes-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="6eb9a-322">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](./supported-filetypes-ediscovery20.md) and supported metadata fields are [here](./document-metadata-fields-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="6eb9a-323">此外，新的 Advanced eDiscovery 解决方案提供了一个强大的保管人保留管理功能，使您可以将保留应用于不同服务中的内容、通知用户保留项并跟踪保管人响应，所有这些都在 Advanced eDiscovery 案例中。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-323">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="6eb9a-324">若要访问高级电子数据展示 v2.0：</span><span class="sxs-lookup"><span data-stu-id="6eb9a-324">To access Advanced eDiscovery v2.0:</span></span>

1. <span data-ttu-id="6eb9a-325">转到 [Microsoft 365 合规中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-325">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="6eb9a-326">在 Microsoft 365 合规中心的左侧导航窗格中，单击 **显示所有**，然后单击" **电子数据展示>高级**。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-326">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

<span data-ttu-id="6eb9a-327">目前，我们建议您开始将电子数据展示工作流转换为新的Advanced eDiscovery功能。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-327">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="6eb9a-328">如果需要，您可以通过导出内容Advanced eDiscovery存储内容来存档 1.0 事例。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-328">If required, you can archive your Advanced eDiscovery 1.0 cases by exporting the content and storing it offline.</span></span> <span data-ttu-id="6eb9a-329">尽管你仍然能够在 2020 年 12 月 31 Advanced eDiscovery访问 Advanced eDiscovery v1.0，但 Microsoft 支持不会在 2020 年 10 月 1 日之后提供支持。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-329">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases until December 31, 2020, Microsoft Support won't provide support after October 1, 2020.</span></span> <span data-ttu-id="6eb9a-330">有关详细信息，请参阅以下日程表。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-330">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="6eb9a-331">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="6eb9a-331">Scope of affected organizations</span></span>

- <span data-ttu-id="6eb9a-332">Office 365 和 Microsoft 365 企业版 组织</span><span class="sxs-lookup"><span data-stu-id="6eb9a-332">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="6eb9a-333">Office 365和Microsoft 365 教育版组织</span><span class="sxs-lookup"><span data-stu-id="6eb9a-333">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="6eb9a-334">Office 365和Microsoft 365政府组织;这包括GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="6eb9a-334">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="6eb9a-335">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="6eb9a-335">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="6eb9a-336">日程表</span><span class="sxs-lookup"><span data-stu-id="6eb9a-336">Timeline</span></span>

- <span data-ttu-id="6eb9a-337">2020 年 7 月 1 日：将无法创建新的 Advanced eDiscovery v1.0 用例。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-337">July 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="6eb9a-338">2020 年 10 月 1 日：无法将新数据 (准备搜索结果以Advanced eDiscovery) 任何情况。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-338">October 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="6eb9a-339">你将能够继续处理现有情况下的数据，但由你自己承担风险。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-339">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="6eb9a-340">Microsoft 支持将不再提供帮助。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-340">Microsoft Support will no longer provide assistance.</span></span> 

- <span data-ttu-id="6eb9a-341">2020 年 12 月 31 日：你将无法访问 Advanced eDiscovery v1.0 的情况。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-341">December 31, 2020: You won't be able to access Advanced eDiscovery v1.0 cases.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="6eb9a-342">替代工具</span><span class="sxs-lookup"><span data-stu-id="6eb9a-342">Alternative tools</span></span>

<span data-ttu-id="6eb9a-343">Advanced eDiscovery[合规中心](./overview-ediscovery-20.md)Microsoft 365解决方案。</span><span class="sxs-lookup"><span data-stu-id="6eb9a-343">The [Advanced eDiscovery solution](./overview-ediscovery-20.md) in the Microsoft 365 compliance center.</span></span>