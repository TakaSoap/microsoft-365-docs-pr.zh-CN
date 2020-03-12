---
title: 旧电子数据展示工具的退休
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Exchange Online 中的就地电子数据展示和就地保留（以及相应的 PowerShell cmdlet）将在2020的上半年中停用。 搜索邮箱 cmdlet 和 Office 365 高级电子数据展示 v1.0 也会在同一时间段内被停用。
ms.openlocfilehash: 92b6648b603286871956db64631d334df2384112
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2020
ms.locfileid: "42605361"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="48297-104">旧电子数据展示工具的退休</span><span class="sxs-lookup"><span data-stu-id="48297-104">Retirement of legacy eDiscovery tools</span></span>

<span data-ttu-id="48297-105">多年以来，Microsoft 提供了电子数据展示工具，可让你搜索、预览和导出来自 Exchange Online 的电子邮件内容。</span><span class="sxs-lookup"><span data-stu-id="48297-105">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="48297-106">但是，这些工具不再提供在其他 Office 365 服务（如 SharePoint Online 和 Office 365 组）中搜索非 Exchange 内容的有效方法。</span><span class="sxs-lookup"><span data-stu-id="48297-106">However, these tools no longer offer an effective way to search for non-Exchange content in other Office 365 services, such as SharePoint Online and Office 365 Groups.</span></span> <span data-ttu-id="48297-107">为解决此类情况，Microsoft 提供了其他电子数据展示工具，可帮助您搜索各种各样的 Office 365 内容。</span><span class="sxs-lookup"><span data-stu-id="48297-107">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Office 365 content.</span></span> <span data-ttu-id="48297-108">我们在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中努力将最新和强大的电子数据展示功能结合在一起。</span><span class="sxs-lookup"><span data-stu-id="48297-108">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="48297-109">这使组织能够对多个 Office 365 服务（包括 Exchange Online）中的内容进行法律、内部和其他文档请求的响应。</span><span class="sxs-lookup"><span data-stu-id="48297-109">This allows organizations to respond to legal, internal, and other document requests for content across many Office 365 services, including Exchange Online.</span></span>

<span data-ttu-id="48297-110">由于 Microsoft 365 合规性中心中的这一新的和改进的电子数据展示功能，我们正在淘汰以下与在 Exchange Online 和 Office 365 中搜索电子邮件内容相关的电子数据展示相关功能和功能：</span><span class="sxs-lookup"><span data-stu-id="48297-110">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Office 365:</span></span>

- <span data-ttu-id="48297-111">Exchange 管理中心内的[就地电子数据展示](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)和[就地保留](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="48297-111">[In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="48297-112">支持就地电子数据展示和就地保留的 Exchange Online PowerShell cmdlet （这些 cmdlet 共同标识为 \**-new-mailboxsearch* cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="48297-112">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="48297-113">这包括以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="48297-113">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="48297-114">新 New-mailboxsearch</span><span class="sxs-lookup"><span data-stu-id="48297-114">New-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-mailboxsearch)

  - [<span data-ttu-id="48297-115">启动-New-mailboxsearch</span><span class="sxs-lookup"><span data-stu-id="48297-115">Start-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-mailboxsearch)

  - [<span data-ttu-id="48297-116">New-mailboxsearch</span><span class="sxs-lookup"><span data-stu-id="48297-116">Stop-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/stop-mailboxsearch)

  - [<span data-ttu-id="48297-117">New-mailboxsearch</span><span class="sxs-lookup"><span data-stu-id="48297-117">Set-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="48297-118">[New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)和[new-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch) cmdlet 将在其他 \* \* \* \*-new-mailboxsearch \* \* （cmdlet 已停用之后提供，以便您可以使用它们来帮助您过渡到其他电子数据展示和保留工具。</span><span class="sxs-lookup"><span data-stu-id="48297-118">The [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch) and [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*\* cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="48297-119">但是，在某个特定日期（如下所示）后，Microsoft 支持将不再支持这两个 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48297-119">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="48297-120">Exchange Online PowerShell 中的[搜索邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps)cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48297-120">The [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="48297-121">Exchange Web Services API 中的以下操作：</span><span class="sxs-lookup"><span data-stu-id="48297-121">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="48297-122">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="48297-122">GetSearchableMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="48297-123">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="48297-123">SetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="48297-124">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="48297-124">GetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="48297-125">[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)v1.0，它是高级电子数据展示的第一个版本，可通过 Office 365 安全性 & 合规性中心中的电子数据展示事例进行访问。</span><span class="sxs-lookup"><span data-stu-id="48297-125">[Office 365 Advanced eDiscovery v1.0](office-365-advanced-ediscovery.md), which is the first version of Advanced eDiscovery that's accessed through an eDiscovery case in the Office 365 Security & Compliance Center.</span></span>

> [!NOTE]
> <span data-ttu-id="48297-126">要废弃的电子数据展示功能仅适用于基于云的 Microsoft 365 和 Office 365 版本。</span><span class="sxs-lookup"><span data-stu-id="48297-126">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="48297-127">在 Exchange 和 SharePoint 的本地版本中，电子数据展示功能将仍受支持，直至进一步通知。</span><span class="sxs-lookup"><span data-stu-id="48297-127">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="48297-128">本文中的以下各节提供有关即将停用的每个功能的指导。</span><span class="sxs-lookup"><span data-stu-id="48297-128">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="48297-129">此信息包括可供您使用的时间线和替代工具，而不是退休工具。</span><span class="sxs-lookup"><span data-stu-id="48297-129">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="48297-130">Exchange 管理中心内的就地电子数据展示和就地保留</span><span class="sxs-lookup"><span data-stu-id="48297-130">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="48297-131">根据2017年7月1日的原始通知，将停用 Exchange 管理中心（EAC）中的 "就地电子数据展示 & 保留功能"。</span><span class="sxs-lookup"><span data-stu-id="48297-131">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="48297-132">EAC 中的就地电子数据展示 & 保留页面允许您搜索、保留和导出 Exchange Online 中的内容。</span><span class="sxs-lookup"><span data-stu-id="48297-132">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="48297-133">就地电子数据展示还允许您将搜索结果复制到发现邮箱，以便您或其他电子数据展示管理者可以查看内容并使其可用于法律、法规和公共请求。</span><span class="sxs-lookup"><span data-stu-id="48297-133">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="48297-134">由于所有这些功能（除了将搜索结果复制到发现邮箱之外）现已在[microsoft 365 合规性中心](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)的内容搜索、电子数据展示和高级电子数据展示工具（改进了各种 Microsoft 365 服务的功能、可靠性和支持）中提供，我们建议您尽快开始使用这些工具。</span><span class="sxs-lookup"><span data-stu-id="48297-134">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="48297-135">为了帮助您转换到这些其他电子数据展示工具，下表列出了您可以使用的工具，而不是就地电子数据展示和就地保留。</span><span class="sxs-lookup"><span data-stu-id="48297-135">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="48297-136">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="48297-136">Scope of affected organizations</span></span>

- <span data-ttu-id="48297-137">Office 365 和 Microsoft 365 企业组织</span><span class="sxs-lookup"><span data-stu-id="48297-137">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="48297-138">Office 365 和 Microsoft 365 教育组织</span><span class="sxs-lookup"><span data-stu-id="48297-138">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="48297-139">Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="48297-139">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="48297-140">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="48297-140">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="48297-141">停用的日程表</span><span class="sxs-lookup"><span data-stu-id="48297-141">Timeline for retirement</span></span>

- <span data-ttu-id="48297-142">2020年4月1日：您将无法创建新的搜索和保留，但您仍可以自行承担运行、编辑和删除现有搜索。</span><span class="sxs-lookup"><span data-stu-id="48297-142">April 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="48297-143">Microsoft 支持将不再将 EAC 中的电子数据展示 & 保留。</span><span class="sxs-lookup"><span data-stu-id="48297-143">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="48297-144">2020年7月1日：就地电子数据展示 & 保留 EAC 中的功能将被置于只读模式下。</span><span class="sxs-lookup"><span data-stu-id="48297-144">July 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="48297-145">这意味着您将只能删除现有的搜索和保留。</span><span class="sxs-lookup"><span data-stu-id="48297-145">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="48297-146">替代工具</span><span class="sxs-lookup"><span data-stu-id="48297-146">Alternative tools</span></span>

<span data-ttu-id="48297-147">下表介绍了可用于替换即将停用的现有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="48297-147">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="48297-148"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="48297-148"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="48297-149"><strong>替代工具</strong></span><span class="sxs-lookup"><span data-stu-id="48297-149"><strong>Alternative tool</strong></span></span></th>
<th><span data-ttu-id="48297-150"><strong>Comments</strong></span><span class="sxs-lookup"><span data-stu-id="48297-150"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="48297-151">出于法律目的进行搜索、导出和保留</span><span class="sxs-lookup"><span data-stu-id="48297-151">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="48297-152">Microsoft 365 合规性中心中的核心电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="48297-152">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="48297-153">使用核心电子数据展示事例的功能，可为就地电子数据展示和就地保留提供功能性奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="48297-153">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="48297-154">其中包括：</span><span class="sxs-lookup"><span data-stu-id="48297-154">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="48297-155">搜索范围扩展到数百万个位置</span><span class="sxs-lookup"><span data-stu-id="48297-155">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="48297-156">更高的可靠性用于搜索、导出和放置保留内容</span><span class="sxs-lookup"><span data-stu-id="48297-156">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="48297-157">在 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft 团队、Yammer 组、Office 365 组以及存储在 Office 365 应用程序中的其他内容中搜索内容</span><span class="sxs-lookup"><span data-stu-id="48297-157">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Office 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
<p><span data-ttu-id="48297-158">有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">在 Office 365 中管理法律调查</a>。</span><span class="sxs-lookup"><span data-stu-id="48297-158">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations"> Manage legal investigations in Office 365</a>.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="48297-159">保留以供保留之用</span><span class="sxs-lookup"><span data-stu-id="48297-159">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="48297-160">Microsoft 365 合规性中心中的保留策略</span><span class="sxs-lookup"><span data-stu-id="48297-160">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="48297-161">您可以使用保留策略保留内容，如果需要，请在保留期到期后将其删除。</span><span class="sxs-lookup"><span data-stu-id="48297-161">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="48297-162">其他功能包括：</span><span class="sxs-lookup"><span data-stu-id="48297-162">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="48297-163">将策略应用于整个组织</span><span class="sxs-lookup"><span data-stu-id="48297-163">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="48297-164">将策略应用于特定的内容位置，如 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft 团队和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="48297-164">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="48297-165">将策略应用于特定用户</span><span class="sxs-lookup"><span data-stu-id="48297-165">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="48297-166">有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">保留策略概述</a>。</span><span class="sxs-lookup"><span data-stu-id="48297-166">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> Overview of retention policies</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="48297-167">将电子邮件搜索结果复制到发现邮箱以供审阅</span><span class="sxs-lookup"><span data-stu-id="48297-167">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="48297-168">高级电子数据展示2.0 版中的审阅集</span><span class="sxs-lookup"><span data-stu-id="48297-168">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="48297-169">在 Microsoft 365 中查看内容从未像以前这样轻松。</span><span class="sxs-lookup"><span data-stu-id="48297-169">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="48297-170">查看集具有许多有用的功能，可帮助减少所需的查看时间和数据量，包括：</span><span class="sxs-lookup"><span data-stu-id="48297-170">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="48297-171">在审阅集中执行 fast search 查询和筛选内容</span><span class="sxs-lookup"><span data-stu-id="48297-171">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="48297-172">分析审阅集中的内容;这包括电子邮件线索、临近重复检测、主题分析和预测编码</span><span class="sxs-lookup"><span data-stu-id="48297-172">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="48297-173">标记审阅集中的文档</span><span class="sxs-lookup"><span data-stu-id="48297-173">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="48297-174">帮助识别律师客户端权限内容的标记建议</span><span class="sxs-lookup"><span data-stu-id="48297-174">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="48297-175">有关详细信息，请参阅 <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 中的高级电子数据展示解决方案概述</a>。</span><span class="sxs-lookup"><span data-stu-id="48297-175">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="48297-176">或者，可以将搜索结果导出到 PST 文件，然后使用 Microsoft 365 导入服务将 Pst 导入到发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="48297-176">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="48297-177">有关分步说明，请参阅<a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">使用网络上载将 PST 文件导入到 Office 365</a>。</span><span class="sxs-lookup"><span data-stu-id="48297-177">For step-by-step instruction, see <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class="even">
<td><span data-ttu-id="48297-178">还原 "可恢复的项目" 文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="48297-178">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="48297-179"><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">Restore-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="48297-179"><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="48297-180">您可以还原邮箱中永久删除的项目（也称为<i>软删除</i>的项目），只要项目的已删除邮件保留期尚未过期。</span><span class="sxs-lookup"><span data-stu-id="48297-180">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="48297-181">有关详细信息，请参阅<a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online 中的 "可恢复的项目" 文件夹</a>。</span><span class="sxs-lookup"><span data-stu-id="48297-181">For more information, see <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="48297-182">有关就地电子数据展示和就地保留的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="48297-182">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="48297-183">**我使用就地电子数据展示 & 保留在 EAC 中的 "复制搜索结果" 功能，将搜索结果复制到发现邮箱以供律师审阅。我现在有哪些选项？**</span><span class="sxs-lookup"><span data-stu-id="48297-183">**I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?**</span></span>

<span data-ttu-id="48297-184">目前，有两种方法可以复制此功能。</span><span class="sxs-lookup"><span data-stu-id="48297-184">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="48297-185">第一种是[在高级电子数据展示 2.0 2.0 中使用审阅集](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)。</span><span class="sxs-lookup"><span data-stu-id="48297-185">The first is to use [review sets in Advanced eDiscovery v2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set).</span></span> <span data-ttu-id="48297-186">评审集具有许多与传统审阅工具（如快速搜索文档、标记、电子邮件线程、临近重复分组、主题分析和预测编码）有关的功能。</span><span class="sxs-lookup"><span data-stu-id="48297-186">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="48297-187">如果仍要使用发现邮箱进行审阅，第二个选项是将搜索结果导出到 PST 文件，然后使用 Microsoft 合规性中心中的[pst 导入功能](use-network-upload-to-import-pst-files.md)将 pst 文件导入到发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="48297-187">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="48297-188">**如何控制电子数据展示管理器可以使用新工具搜索的内容位置（如邮箱或网站）？**</span><span class="sxs-lookup"><span data-stu-id="48297-188">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="48297-189">Microsoft 365 合规性中心还使用[合规性边界](set-up-compliance-boundaries.md)来控制电子数据展示管理器可搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="48297-189">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="48297-190">合规性边界适用于需要在机构边界或需要遵守地理 boarders 的多国公司内部的政府实体。</span><span class="sxs-lookup"><span data-stu-id="48297-190">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="48297-191">**如何将当前的搜索和保留移动到 Microsoft 365 合规性中心？**</span><span class="sxs-lookup"><span data-stu-id="48297-191">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="48297-192">可以使用 PowerShell 从 EAC 迁移就地电子数据展示搜索和保留。</span><span class="sxs-lookup"><span data-stu-id="48297-192">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="48297-193">有关说明，请参阅将[搜索和保留从 EAC 迁移到 Microsoft 365 合规性中心](https://go.microsoft.com/fwlink/?linkid=2114224)。</span><span class="sxs-lookup"><span data-stu-id="48297-193">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](https://go.microsoft.com/fwlink/?linkid=2114224).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="48297-194">\*-New-mailboxsearch cmdlet</span><span class="sxs-lookup"><span data-stu-id="48297-194">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="48297-195">根据在 Exchange 管理中心中的2017年7月1日宣布的原始通知，就地电子数据展示 & 保留功能和相应\*\* \*的 new-mailboxsearch\*\* cmdlet 将被停用。</span><span class="sxs-lookup"><span data-stu-id="48297-195">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="48297-196">这些 cmdlet 使用户能够搜索、保留和导出适用于法律、法规和公共请求的邮箱内容。</span><span class="sxs-lookup"><span data-stu-id="48297-196">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="48297-197">由于这些功能现已在[<span class="underline">Microsoft 365 合规性中心</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)和 Office 365 安全性 & 合规性中心 PowerShell 中提供了改进的性能和可伸缩性，因此您应使用这些改进的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48297-197">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="48297-198">这些 cmdlet 包括[<span class="underline"> \*-get-compliancecase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase)、 [<span class="underline"> \*-new-compliancesearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)、 [<span class="underline"> \*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)、 [<span class="underline"> \*-new-caseholdrule</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule)和[<span class="underline"> \*-new-compliancesearchaction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)。</span><span class="sxs-lookup"><span data-stu-id="48297-198">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="48297-199">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="48297-199">Scope of affected organizations</span></span>

- <span data-ttu-id="48297-200">Office 365 和 Microsoft 365 企业组织</span><span class="sxs-lookup"><span data-stu-id="48297-200">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="48297-201">Office 365 和 Microsoft 365 教育组织</span><span class="sxs-lookup"><span data-stu-id="48297-201">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="48297-202">Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="48297-202">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="48297-203">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="48297-203">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="48297-204">日程表</span><span class="sxs-lookup"><span data-stu-id="48297-204">Timeline</span></span>

- <span data-ttu-id="48297-205">2020年4月1日：您将无法使用**new-mailboxsearch**创建新的就地电子数据展示搜索和就地保留，但您仍可以使用 cmdlet 来运行、编辑和删除现有搜索并保留自己的风险。</span><span class="sxs-lookup"><span data-stu-id="48297-205">April 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="48297-206">Microsoft 支持将不再为这些类型的搜索和保留提供帮助。</span><span class="sxs-lookup"><span data-stu-id="48297-206">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="48297-207">2020年7月1日：如前所述，就地电子数据展示 & 保留 EAC 中的功能将被置于只读模式下。</span><span class="sxs-lookup"><span data-stu-id="48297-207">July 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="48297-208">这也意味着您不能使用**new-mailboxsearch**、 **Start-new-mailboxsearch**或**new-mailboxsearch** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48297-208">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="48297-209">你将只能获取和删除现有搜索和保留。</span><span class="sxs-lookup"><span data-stu-id="48297-209">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="48297-210">替代工具</span><span class="sxs-lookup"><span data-stu-id="48297-210">Alternative tools</span></span>

<span data-ttu-id="48297-211">下表介绍了可用于替换即将停用的现有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="48297-211">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="48297-212"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="48297-212"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="48297-213"><strong>替代工具</strong></span><span class="sxs-lookup"><span data-stu-id="48297-213"><strong>Alternative tools</strong></span></span></th>
<th><span data-ttu-id="48297-214"><strong>Comments</strong></span><span class="sxs-lookup"><span data-stu-id="48297-214"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="48297-215">搜索和导出</span><span class="sxs-lookup"><span data-stu-id="48297-215">Search and export</span></span></td>
<td><p><span data-ttu-id="48297-216"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">\*-New-compliancesearch</span></a></span><span class="sxs-lookup"><span data-stu-id="48297-216"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="48297-217"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="48297-217"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="48297-218"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-Get-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="48297-218"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="48297-219">New-compliancesearch 和 New-compliancesearchaction cmdlet 一起使用可帮助您搜索和导出内容。</span><span class="sxs-lookup"><span data-stu-id="48297-219">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="48297-220">您可以使用<strong>new-</strong>、 <strong>Get</strong>和<strong>new-compliancesearch</strong> cmdlet 来创建新搜索并查看搜索估计。</span><span class="sxs-lookup"><span data-stu-id="48297-220">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="48297-221">然后，您可以使用<strong>new-compliancesearchaction</strong> cmdlet 导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="48297-221">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="48297-222">您仍需使用 Microsoft 365 合规性中心中的核心电子数据展示工具将这些搜索结果下载到您的本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="48297-222">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="48297-223"><strong>注意：</strong>如果您使用这些 cmdlet 来创建不与核心电子数据展示事例关联的搜索，则这些搜索将位于 Microsoft 365 合规性中心的<strong>内容搜索</strong>页中。</span><span class="sxs-lookup"><span data-stu-id="48297-223"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="48297-224">保留邮箱中的内容</span><span class="sxs-lookup"><span data-stu-id="48297-224">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="48297-225"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="48297-225"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="48297-226"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">\*-New-caseholdrule</span></a></span><span class="sxs-lookup"><span data-stu-id="48297-226"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="48297-227"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-Get-compliancecase</span></a></span><span class="sxs-lookup"><span data-stu-id="48297-227"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="48297-228">Microsoft 365 合规性中心中的保留必须与 Get-compliancecase 相关联。</span><span class="sxs-lookup"><span data-stu-id="48297-228">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="48297-229">首先，创建合规性事例，然后创建 CaseHoldPolicy 和 New-caseholdrule。</span><span class="sxs-lookup"><span data-stu-id="48297-229">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="48297-230"><strong>注意：</strong>创建没有创建 New-caseholdrule 的 CaseHoldPolicy 将使保留不可操作，直到创建 New-caseholdrule 并将其与 CaseHoldPolicy 关联。</span><span class="sxs-lookup"><span data-stu-id="48297-230"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="48297-231">有关详细信息，请参阅 cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="48297-231">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="48297-232">将搜索结果复制到发现邮箱</span><span class="sxs-lookup"><span data-stu-id="48297-232">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="48297-233">无</span><span class="sxs-lookup"><span data-stu-id="48297-233">None</span></span></td>
<td><span data-ttu-id="48297-234">此功能没有直接替代，因为它不提供对所有 Microsoft 365 服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="48297-234">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="48297-235">有关其他解决方案，请参阅下面的 FAQ。</span><span class="sxs-lookup"><span data-stu-id="48297-235">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="48297-236">有关 \***-new-mailboxsearch cmdlet 的**常见问题解答</span><span class="sxs-lookup"><span data-stu-id="48297-236">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="48297-237">**我们使用复制搜索来导出电子邮件或即时消息，以供其他电子数据展示和法律调查使用。停用这些 cmdlet 后还有哪些其他选项？**</span><span class="sxs-lookup"><span data-stu-id="48297-237">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="48297-238">[<span class="underline">Microsoft Graph api</span>](https://developer.microsoft.com/en-us/graph)提供了多种方法，用于提取用于分析的数据，以及与使用\*\* \*-new-mailboxsearch\*\* cmdlet 相比更具弹性和可伸缩性的其他目的。</span><span class="sxs-lookup"><span data-stu-id="48297-238">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="48297-239">**如何将我的搜索和保留迁移到 Microsoft 365 合规性中心？**</span><span class="sxs-lookup"><span data-stu-id="48297-239">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="48297-240">可以使用 PowerShell 脚本从 Exchange 管理中心迁移就地电子数据展示搜索和保留。</span><span class="sxs-lookup"><span data-stu-id="48297-240">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="48297-241">有关详细信息，请参阅将[旧电子数据展示搜索和保留迁移到 Microsoft 365 合规性中心](migrate-legacy-eDiscovery-searches-and-holds.md)。</span><span class="sxs-lookup"><span data-stu-id="48297-241">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="48297-242">**Cmdlet 停用后，我是否仍可以删除或检索搜索？**</span><span class="sxs-lookup"><span data-stu-id="48297-242">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="48297-243">是的，尽管我们要删除创建和修改搜索的功能，但仍可以使用**new-mailboxsearch**和**new-mailboxsearch** ，直到再次通知。</span><span class="sxs-lookup"><span data-stu-id="48297-243">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="48297-244">但是，这些 cmdlet 在退休日期后将受到自己的威胁，Microsoft 支持将不再能够提供协助。</span><span class="sxs-lookup"><span data-stu-id="48297-244">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="48297-245">搜索-邮箱 cmdlet</span><span class="sxs-lookup"><span data-stu-id="48297-245">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="48297-246">Exchange Online PowerShell 中的**搜索邮箱**cmdlet 将被停用，因为最初在2018的 cmdlet 输出中已宣布出现警告。</span><span class="sxs-lookup"><span data-stu-id="48297-246">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="48297-247">**搜索邮箱**cmdlet 最初用于搜索用户的邮箱并清除恶意内容。</span><span class="sxs-lookup"><span data-stu-id="48297-247">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="48297-248">我们建议您开始使用 Office 365 Security & 合规性中心 PowerShell 中的**new-compliancesearch**和**new-compliancesearchaction** cmdlet 来搜索和清除内容。</span><span class="sxs-lookup"><span data-stu-id="48297-248">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="48297-249">对于内置的安全体验， [<span class="underline">microsoft 365 安全功能</span>](https://docs.microsoft.com/microsoft-365/security/)为电子邮件和许多其他 Microsoft 服务提供了强健的威胁防护。</span><span class="sxs-lookup"><span data-stu-id="48297-249">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](https://docs.microsoft.com/microsoft-365/security/) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="48297-250">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="48297-250">Scope of affected organizations</span></span>

- <span data-ttu-id="48297-251">Office 365 和 Microsoft 365 企业组织</span><span class="sxs-lookup"><span data-stu-id="48297-251">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="48297-252">Office 365 和 Microsoft 365 教育组织</span><span class="sxs-lookup"><span data-stu-id="48297-252">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="48297-253">Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="48297-253">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="48297-254">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="48297-254">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="48297-255">日程表</span><span class="sxs-lookup"><span data-stu-id="48297-255">Timeline</span></span>

-  <span data-ttu-id="48297-256">2020年4月1日：将不再提供**搜索邮箱**Cmdlet，Microsoft 支持将不再提供帮助。</span><span class="sxs-lookup"><span data-stu-id="48297-256">April 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="48297-257">替代工具</span><span class="sxs-lookup"><span data-stu-id="48297-257">Alternative tools</span></span>

<span data-ttu-id="48297-258">下表介绍了可用于替换即将停用的现有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="48297-258">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="48297-259"><strong>功能</strong></span><span class="sxs-lookup"><span data-stu-id="48297-259"><strong>Functionality</strong></span></span></th>
<th><span data-ttu-id="48297-260"><strong>替代工具</strong></span><span class="sxs-lookup"><span data-stu-id="48297-260"><strong>Alternative tools</strong></span></span></th>
<th><span data-ttu-id="48297-261"><strong>Comments</strong></span><span class="sxs-lookup"><span data-stu-id="48297-261"><strong>Comments</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="48297-262">搜索邮箱</span><span class="sxs-lookup"><span data-stu-id="48297-262">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="48297-263"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-New-compliancesearch</span></a></span><span class="sxs-lookup"><span data-stu-id="48297-263"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="48297-264"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="48297-264"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="48297-265">New-compliancesearch 和 New-compliancesearchaction cmdlet 一起使用可帮助您搜索和导出内容。</span><span class="sxs-lookup"><span data-stu-id="48297-265">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="48297-266">您可以使用<strong>new-</strong>、 <strong>Get</strong>和<strong>new-compliancesearch</strong> cmdlet 来创建新搜索并查看搜索估计。</span><span class="sxs-lookup"><span data-stu-id="48297-266">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="48297-267">然后，可以使用<strong>new-compliancesearchaction-export</strong>命令导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="48297-267">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="48297-268">您仍需使用 Microsoft 365 合规性中心中的核心电子数据展示工具将这些搜索结果下载到您的本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="48297-268">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="48297-269">清除邮箱中的邮件</span><span class="sxs-lookup"><span data-stu-id="48297-269">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="48297-270"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-New-compliancesearch</span></a></span><span class="sxs-lookup"><span data-stu-id="48297-270"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="48297-271"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-New-compliancesearchaction</span></a></span><span class="sxs-lookup"><span data-stu-id="48297-271"><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="48297-272">New-compliancesearch 和 New-compliancesearchaction cmdlet 一起使用可帮助您搜索和清除内容。</span><span class="sxs-lookup"><span data-stu-id="48297-272">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="48297-273">您可以使用<strong>new-compliancesearch</strong>和<strong>new-compliancesearch</strong> cmdlet 创建和运行搜索，然后您可以使用<strong>new-compliancesearchaction-PurgeType</strong>命令清除内容的内容。</span><span class="sxs-lookup"><span data-stu-id="48297-273">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="48297-274">有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">搜索和删除邮件</span></a>。</span><span class="sxs-lookup"><span data-stu-id="48297-274">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd">
<td><span data-ttu-id="48297-275">从邮箱中删除批量电子邮件</span><span class="sxs-lookup"><span data-stu-id="48297-275">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="48297-276"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">设置邮箱的存档和删除策略</span></a></span><span class="sxs-lookup"><span data-stu-id="48297-276"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="48297-277">管理员可以创建存档和删除策略，以自动将项目移动到用户的存档邮箱，并自动删除邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="48297-277">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="48297-278">将搜索结果复制到发现邮箱</span><span class="sxs-lookup"><span data-stu-id="48297-278">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="48297-279">此功能没有直接替代，因为它不提供对所有 Microsoft 365 服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="48297-279">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="48297-280">有关替代解决方案，请参阅 " <strong>\*-new-mailboxsearch cmdlet</strong> " 部分中的 faq。</span><span class="sxs-lookup"><span data-stu-id="48297-280">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
</tbody>
</table>

## <a name="getsearchablemailboxes-setholdonmailboxes-and-getholdonmailboxes-operations-in-the-ews-api"></a><span data-ttu-id="48297-281">EWS API 中的 GetSearchableMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 操作</span><span class="sxs-lookup"><span data-stu-id="48297-281">GetSearchableMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations in the EWS API</span></span>

<span data-ttu-id="48297-282">Exchange 管理中心中的 "就地电子数据展示 & 保留" 功能和 exchange Online PowerShell 中的相应\*\* \*new-mailboxsearch\*\* cmdlet 使用这三个 Exchange Web Services api。</span><span class="sxs-lookup"><span data-stu-id="48297-282">These three Exchange Web Services APIs are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="48297-283">在停用其他旧的电子数据展示工具时，它们也会被停用。</span><span class="sxs-lookup"><span data-stu-id="48297-283">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="48297-284">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="48297-284">Scope of affected organizations</span></span>

- <span data-ttu-id="48297-285">Office 365 和 Microsoft 365 企业组织</span><span class="sxs-lookup"><span data-stu-id="48297-285">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="48297-286">Office 365 和 Microsoft 365 教育组织</span><span class="sxs-lookup"><span data-stu-id="48297-286">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="48297-287">Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="48297-287">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="48297-288">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="48297-288">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="48297-289">日程表</span><span class="sxs-lookup"><span data-stu-id="48297-289">Timeline</span></span>

- <span data-ttu-id="48297-290">2020年4月1日： GetSearchableMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 操作将不再可用，Microsoft 支持将不再提供协助。</span><span class="sxs-lookup"><span data-stu-id="48297-290">April 1, 2020: The GetSearchableMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="48297-291">高级电子数据展示1.0 版</span><span class="sxs-lookup"><span data-stu-id="48297-291">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="48297-292">高级电子数据展示 v1.0，即在电子数据展示事例中，通过单击 "**切换到高级电子数据展示**" 将停用的高级电子数据展示的版本。</span><span class="sxs-lookup"><span data-stu-id="48297-292">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in an eDiscovery case by clicking **Switch to Advanced eDiscovery** is being retired.</span></span> <span data-ttu-id="48297-293">其功能已在 Microsoft 365 合规性中心中的新[高级电子数据展示解决方案](https://aka.ms/edisco)中取代。</span><span class="sxs-lookup"><span data-stu-id="48297-293">Its functionality has been replaced by the new [Advanced eDiscovery solution](https://aka.ms/edisco) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="48297-294">Microsoft 365 中新的高级电子数据展示解决方案（也称为*高级电子数据展示 2.0 2.0*）提供了原始解决方案的所有功能，但现在提供了一种基于保管人的方法，可识别其他 Microsoft 365 服务中的内容，收集该内容，然后将其添加到审阅集中，以便审阅者可以利用 fast search 查询、标记和分析功能来帮助挑选相关文档。</span><span class="sxs-lookup"><span data-stu-id="48297-294">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="48297-295">高级电子数据展示现在为 Microsoft 和非 Microsoft 文件类型提供了改进的处理和本机查看器[，此处提供](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20)了文件类型的完整列表以及支持[的元数据字段。](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)</span><span class="sxs-lookup"><span data-stu-id="48297-295">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) and supported metadata fields are [here](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery).</span></span> <span data-ttu-id="48297-296">此外，新的高级电子数据展示解决方案提供了强大的保管人保留功能，允许您将保留应用于不同服务中的内容、通知用户保留和在高级电子数据展示事例中跟踪保管人响应。</span><span class="sxs-lookup"><span data-stu-id="48297-296">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="48297-297">此时，我们建议您开始将电子数据展示工作流转换为新的高级电子数据展示功能。</span><span class="sxs-lookup"><span data-stu-id="48297-297">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="48297-298">尽管您仍可以在现有情况下访问高级电子数据展示 v1.0，但 Microsoft 支持不会在2020年7月1日之后提供支持。</span><span class="sxs-lookup"><span data-stu-id="48297-298">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases, Microsoft Support won’t provide support after July 1, 2020.</span></span> <span data-ttu-id="48297-299">有关详细信息，请参阅以下日程表。</span><span class="sxs-lookup"><span data-stu-id="48297-299">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="48297-300">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="48297-300">Scope of affected organizations</span></span>
    
- <span data-ttu-id="48297-301">Office 365 和 Microsoft 365 企业组织</span><span class="sxs-lookup"><span data-stu-id="48297-301">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="48297-302">Office 365 和 Microsoft 365 教育组织</span><span class="sxs-lookup"><span data-stu-id="48297-302">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="48297-303">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="48297-303">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="48297-304">日程表</span><span class="sxs-lookup"><span data-stu-id="48297-304">Timeline</span></span>

- <span data-ttu-id="48297-305">2020年4月1日：你将无法创建新的高级电子数据展示 v1.0 事例。</span><span class="sxs-lookup"><span data-stu-id="48297-305">April 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="48297-306">2020年7月1日：无法将新数据（为高级电子数据展示准备搜索结果）添加到任何情况。</span><span class="sxs-lookup"><span data-stu-id="48297-306">July 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="48297-307">你将能够继续使用现有案例中的数据，风险自负。</span><span class="sxs-lookup"><span data-stu-id="48297-307">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="48297-308">Microsoft 支持将不再提供协助。</span><span class="sxs-lookup"><span data-stu-id="48297-308">Microsoft Support will no longer provide assistance.</span></span> 

### <a name="alternative-tools"></a><span data-ttu-id="48297-309">替代工具</span><span class="sxs-lookup"><span data-stu-id="48297-309">Alternative tools</span></span>

<span data-ttu-id="48297-310">Microsoft 365 合规性中心中的[高级电子数据展示解决方案](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。</span><span class="sxs-lookup"><span data-stu-id="48297-310">The [Advanced eDiscovery solution](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) in the Microsoft 365 compliance center.</span></span>
