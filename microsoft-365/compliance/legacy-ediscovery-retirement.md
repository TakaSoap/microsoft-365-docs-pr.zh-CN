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
description: In-Place电子数据展示In-Place保留 (Exchange Online 中的相应 PowerShell cmdlet) 将于 2020 年上半年停用。 同时Search-Mailbox停用 Search-Mailbox cmdlet 和高级电子数据展示 v1.0。
ms.openlocfilehash: a40cc67b29e33d61d6750792f6a773622a73f678
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750875"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a><span data-ttu-id="8c4c2-104">旧版电子数据展示工具的停用</span><span class="sxs-lookup"><span data-stu-id="8c4c2-104">Retirement of legacy eDiscovery tools</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c4c2-105">Microsoft 一直在评估公众健康情况，并且我们了解这对我们的客户的影响。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-105">Microsoft has been evaluating the public health situation, and we understand the impact this is having on our customers.</span></span> <span data-ttu-id="8c4c2-106">我们希望成为强大的合作伙伴和负责的全球公民。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-106">We want to be strong partners and responsible global citizens.</span></span> <span data-ttu-id="8c4c2-107">为了减轻您面临的众多负担之一，我们将将本文中所述的旧电子数据展示工具的计划停用延迟三个月。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-107">To ease one of the many burdens you are facing, we are going to delay the scheduled retirement for the legacy eDiscovery tools described in this article by three months.</span></span> <span data-ttu-id="8c4c2-108">**更新后的停用日期如下。**</span><span class="sxs-lookup"><span data-stu-id="8c4c2-108">**The updated retirement dates are reflected below.**</span></span>

<span data-ttu-id="8c4c2-109">多年来，Microsoft 提供了电子数据展示工具，可用于搜索、预览和导出 Exchange Online 中的电子邮件内容。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-109">Over the years, Microsoft has provided eDiscovery tools that let you search, preview, and export email content from Exchange Online.</span></span> <span data-ttu-id="8c4c2-110">但是，这些工具不再提供在其他 Microsoft 365 服务（如 SharePoint Online 和 Microsoft 365 组）中搜索非 Exchange 内容的有效方法。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-110">However, these tools no longer offer an effective way to search for non-Exchange content in other Microsoft 365 services, such as SharePoint Online and Microsoft 365 Groups.</span></span> <span data-ttu-id="8c4c2-111">为解决这一问题，Microsoft 提供了其他电子数据展示工具，可帮助你搜索各种 Microsoft 365 内容。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-111">To address this, Microsoft offers other eDiscovery tools that help you search for a wide variety of Microsoft 365 content.</span></span> <span data-ttu-id="8c4c2-112">我们一直在努力在 [Microsoft 365](https://compliance.microsoft.com)合规中心内整合最新且强大的电子数据展示功能。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-112">And we've been working hard to incorporate the most current and powerful eDiscovery functionality in the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="8c4c2-113">这允许组织对跨许多 Microsoft 365 服务（包括 Exchange Online）的内容的法律、内部和其他文档请求做出响应。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-113">This allows organizations to respond to legal, internal, and other document requests for content across many Microsoft 365 services, including Exchange Online.</span></span>

<span data-ttu-id="8c4c2-114">作为 Microsoft 365 合规中心中这一全新和改进电子数据展示功能的结果，我们将停用以下与在 Exchange Online 和 Microsoft 365 中搜索电子邮件内容相关的电子数据展示相关特性和功能：</span><span class="sxs-lookup"><span data-stu-id="8c4c2-114">As a result of this new and improved eDiscovery functionality in the Microsoft 365 compliance center, we're retiring the following eDiscovery-related features and functionality related to searching for email content in Exchange Online and Microsoft 365:</span></span>

- <span data-ttu-id="8c4c2-115">[Exchange 管理中心中的](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) 就地电子数据展示 [和就地](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) 保留。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-115">[In-Place eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) and [In-Place Holds](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) in the Exchange admin center.</span></span>

- <span data-ttu-id="8c4c2-116">支持 In-Place 电子数据展示和 In-Place 保留的 Exchange Online PowerShell cmdlet (这些 cmdlet 统称为 \**-MailboxSearch* cmdlet) 。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-116">The Exchange Online PowerShell cmdlets that support In-Place eDiscovery and In-Place Holds (these cmdlets are collectively identified as \**-MailboxSearch* cmdlets).</span></span> <span data-ttu-id="8c4c2-117">这包括以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8c4c2-117">This includes the following cmdlets:</span></span>

  - [<span data-ttu-id="8c4c2-118">New-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="8c4c2-118">New-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [<span data-ttu-id="8c4c2-119">Start-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="8c4c2-119">Start-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [<span data-ttu-id="8c4c2-120">Stop-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="8c4c2-120">Stop-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [<span data-ttu-id="8c4c2-121">Set-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="8c4c2-121">Set-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > <span data-ttu-id="8c4c2-122">在其他 \*\*\*\*-MailboxSearch\*\*_ cmdlet 停用后 [，Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) 和 [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) cmdlet 将可用，以便您可以使用它们来帮助转换到其他电子数据展示和保留工具。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-122">The [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other \*\*\*\*-MailboxSearch\*\*_ cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools.</span></span> <span data-ttu-id="8c4c2-123">但是，在下面引用 (日期后) Microsoft 支持将不再支持这两个 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-123">However, after a certain date (cited below) Microsoft Support will no longer supports these two cmdlets.</span></span>

- <span data-ttu-id="8c4c2-124">Exchange Online PowerShell 中的 [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-124">The [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) cmdlet in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="8c4c2-125">Exchange Web 服务 API 中的以下操作：</span><span class="sxs-lookup"><span data-stu-id="8c4c2-125">The following operations in the Exchange Web Services API:</span></span>

   - [<span data-ttu-id="8c4c2-126">GetSearchableMailboxes</span><span class="sxs-lookup"><span data-stu-id="8c4c2-126">GetSearchableMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [<span data-ttu-id="8c4c2-127">SearchMailboxes</span><span class="sxs-lookup"><span data-stu-id="8c4c2-127">SearchMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [<span data-ttu-id="8c4c2-128">SetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="8c4c2-128">SetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [<span data-ttu-id="8c4c2-129">GetHoldOnMailboxes</span><span class="sxs-lookup"><span data-stu-id="8c4c2-129">GetHoldOnMailboxes</span></span>](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- <span data-ttu-id="8c4c2-130">[Office 365 高级电子数据展示 v1.0，](office-365-advanced-ediscovery.md)这是通过 Office 365 安全与合规中心的核心电子数据展示案例访问的高级电子数据展示 &的第一个版本。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-130">[Office 365 Advanced eDiscovery v1.0](office-365-advanced-ediscovery.md), which is the first version of Advanced eDiscovery that's accessed through a Core eDiscovery case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="8c4c2-131">停用高级电子数据展示 v1.0 不会影响创建和管理核心电子数据展示事例的能力。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-131">The retirement of Advanced eDiscovery v1.0 doesn't impact your ability to create and manage Core eDiscovery cases.</span></span>

> [!NOTE]
> <span data-ttu-id="8c4c2-132">要停用的电子数据展示功能仅适用于基于云的 Microsoft 365 和 Office 365 版本。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-132">The eDiscovery functionality being retired only applies to cloud-based versions of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="8c4c2-133">在进一步通知之前，Exchange 和 SharePoint 本地版本中电子数据展示功能仍将受支持。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-133">eDiscovery functionality in on-premises versions of Exchange and SharePoint will still be supported until further notice.</span></span>

<span data-ttu-id="8c4c2-134">本文中的以下各节提供有关要停用的每个功能的指导。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-134">The following sections in this article provide guidance about each feature being retired.</span></span> <span data-ttu-id="8c4c2-135">此信息包括日程表和可使用的替代工具，而不是停用的工具。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-135">This information including timelines and alternative tools that you can use instead of the retired tool.</span></span>

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a><span data-ttu-id="8c4c2-136">In-Place Exchange 管理中心In-Place电子数据展示和保留</span><span class="sxs-lookup"><span data-stu-id="8c4c2-136">In-Place eDiscovery and In-Place Holds in the Exchange admin center</span></span> 

<span data-ttu-id="8c4c2-137">根据 2017 年 7 月 1 日的原始通知，Exchange 管理中心 (In-Place EAC) 中的 In-Place 电子数据展示 & 保留功能即将停用。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-137">As per the original announcement on July 1, 2017, the In-Place eDiscovery & Hold functionality in the Exchange admin center (EAC) is being retired.</span></span> <span data-ttu-id="8c4c2-138">EAC In-Place电子数据展示&保留"页允许从 Exchange Online 搜索、保留和导出内容。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-138">The In-Place eDiscovery & Holds page in the EAC allowed you to search, hold, and export content from Exchange Online.</span></span> <span data-ttu-id="8c4c2-139">In-Place电子数据展示还使你可以将搜索结果复制到发现邮箱，以便你或其他电子数据展示管理员可以审阅内容，使其可用于法律、法规和公共请求。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-139">In-Place eDiscovery also let you copy search results to a discovery mailbox so that you or other eDiscovery managers could review content and make it available for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="8c4c2-140">由于除将搜索结果复制到发现邮箱) 之外的所有功能) 现在都可用于 [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 合规中心 (中的内容搜索、电子数据展示和高级电子数据展示工具，并改进了功能、可靠性和对各种 Microsoft 365 服务) 的支持，因此我们建议您尽快开始使用这些工具。 (</span><span class="sxs-lookup"><span data-stu-id="8c4c2-140">Because all of these capabilities (except for copying search results to a discovery mailbox) are now available in the content search, eDiscovery and Advanced eDiscovery tools in the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (with improved functionality, reliability, and support for a wide range of Microsoft 365 services), we recommend that you start using these tools as soon as possible.</span></span> <span data-ttu-id="8c4c2-141">为了帮助你过渡到这些其他电子数据展示工具，下表列出了可以使用的工具，而不是In-Place电子数据展示和In-Place保留。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-141">To help you in the transition to these other eDiscovery tools, the table below lists the tools you can use instead of In-Place eDiscovery and In-Place Hold.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="8c4c2-142">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="8c4c2-142">Scope of affected organizations</span></span>

- <span data-ttu-id="8c4c2-143">Office 365 和 Microsoft 365 企业版组织</span><span class="sxs-lookup"><span data-stu-id="8c4c2-143">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="8c4c2-144">Office 365 和 Microsoft 365 教育版组织</span><span class="sxs-lookup"><span data-stu-id="8c4c2-144">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="8c4c2-145">Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="8c4c2-145">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="8c4c2-146">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="8c4c2-146">Office 365 Germany</span></span>

### <a name="timeline-for-retirement"></a><span data-ttu-id="8c4c2-147">停用日程表</span><span class="sxs-lookup"><span data-stu-id="8c4c2-147">Timeline for retirement</span></span>

- <span data-ttu-id="8c4c2-148">2020 年 7 月 1 日：无法创建新的搜索和保留，但仍可以自行承担运行、编辑和删除现有搜索的风险。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-148">July 1, 2020: You won't be able to create new searches and holds, but you can still run, edit, and delete existing searches at your own risk.</span></span> <span data-ttu-id="8c4c2-149">Microsoft 支持将不再在 EAC In-Place电子数据&保留。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-149">Microsoft Support will no longer In-Place eDiscovery & Holds in the EAC.</span></span>

- <span data-ttu-id="8c4c2-150">2020 年 10 月 1 In-Place：EAC 中的&电子数据展示保留功能将处于只读模式。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-150">October 1, 2020: The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="8c4c2-151">这意味着你只能删除现有搜索和保留。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-151">This means you'll only be able to remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="8c4c2-152">备用工具</span><span class="sxs-lookup"><span data-stu-id="8c4c2-152">Alternative tools</span></span>

<span data-ttu-id="8c4c2-153">下表介绍了可用于替换即将停用的现有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-153">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="8c4c2-154">功能</span><span class="sxs-lookup"><span data-stu-id="8c4c2-154">Functionality</span></span></th>
<th><span data-ttu-id="8c4c2-155">备用工具</span><span class="sxs-lookup"><span data-stu-id="8c4c2-155">Alternative tool</span></span></th>
<th><span data-ttu-id="8c4c2-156">备注</span><span class="sxs-lookup"><span data-stu-id="8c4c2-156">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8c4c2-157">出于法律目的搜索、导出和保留</span><span class="sxs-lookup"><span data-stu-id="8c4c2-157">Search, export, and hold for legal purposes</span></span></td>
<td><span data-ttu-id="8c4c2-158">Microsoft 365 合规中心中的核心电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="8c4c2-158">Core eDiscovery cases in the Microsoft 365 compliance center</span></span> </td>
<td><p><span data-ttu-id="8c4c2-159">使用核心电子数据展示事例的功能为电子数据展示和保留In-Place功能In-Place奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-159">Using the capabilities of core eDiscovery cases provide the functional parity to In-Place eDiscovery and In-Place Holds.</span></span> <span data-ttu-id="8c4c2-160">其中包括：</span><span class="sxs-lookup"><span data-stu-id="8c4c2-160">This includes the following:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="8c4c2-161">搜索扩展到数百万个位置</span><span class="sxs-lookup"><span data-stu-id="8c4c2-161">Search scales to millions of locations</span></span></p>
</li>
<li>
<p><span data-ttu-id="8c4c2-162">搜索、导出和将内容置于保留状态的可靠性更高</span><span class="sxs-lookup"><span data-stu-id="8c4c2-162">Higher reliability for searching, exporting, and placing content on hold</span></span></p>
</li>
<li>
<p><span data-ttu-id="8c4c2-163">搜索 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer 组、Microsoft 365 组和 Office 365 应用程序中存储的其他内容的内容</span><span class="sxs-lookup"><span data-stu-id="8c4c2-163">Searching for content in for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Groups, Microsoft 365 Groups, and other content stored in Office 365 applications</span></span></p></li></ul>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="8c4c2-164">保留出于保留目的</span><span class="sxs-lookup"><span data-stu-id="8c4c2-164">Hold for retention purposes</span></span></td>
<td><span data-ttu-id="8c4c2-165">Microsoft 365 合规中心中的保留策略</span><span class="sxs-lookup"><span data-stu-id="8c4c2-165">Retention policies in the Microsoft 365 compliance center</span></span></td>
<td><p><span data-ttu-id="8c4c2-166">可以使用保留策略来保留内容，如果需要，可以在保留期到期后将其删除。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-166">You can use Retention policies to retain content and, if desired, delete it after the retention period expires.</span></span> <span data-ttu-id="8c4c2-167">其他功能包括：</span><span class="sxs-lookup"><span data-stu-id="8c4c2-167">Other capabilities include:</span></span></p>
<ul>
<li>
<p><span data-ttu-id="8c4c2-168">将策略应用于整个组织</span><span class="sxs-lookup"><span data-stu-id="8c4c2-168">Applying policies to your entire organization</span></span> </p>
</li><li>
<p><span data-ttu-id="8c4c2-169">将策略应用于特定内容位置，如 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams 和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="8c4c2-169">Applying policies to specific content locations such as Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, and Office 365 Groups</span></span></p></li>
<li>
<p><span data-ttu-id="8c4c2-170">将策略应用于特定用户</span><span class="sxs-lookup"><span data-stu-id="8c4c2-170">Applying policies to specific users</span></span></p></li></ul>
<p><span data-ttu-id="8c4c2-171">有关详细信息，请参阅 <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> 了解保留策略和保留标签</a>。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-171">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> Learn about retention policies and retention labels</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8c4c2-172">将电子邮件搜索结果复制到发现邮箱进行审阅</span><span class="sxs-lookup"><span data-stu-id="8c4c2-172">Copy email search results to a discovery mailbox for review</span></span></td><td><span data-ttu-id="8c4c2-173">高级电子数据展示 v2.0 中的审阅集</span><span class="sxs-lookup"><span data-stu-id="8c4c2-173">Review sets in Advanced eDiscovery v2.0</span></span></td>
<td><p><span data-ttu-id="8c4c2-174">查看 Microsoft 365 中的内容从未如此简单。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-174">Reviewing content in Microsoft 365 has never been easier.</span></span> <span data-ttu-id="8c4c2-175">审阅集具有许多出色的功能，可帮助减少查看所需的时间和数据，包括：</span><span class="sxs-lookup"><span data-stu-id="8c4c2-175">Review sets have many great capabilities to help reduce the amount of time and data needed to review, including:</span></span></p>
<ul>
<li><p><span data-ttu-id="8c4c2-176">执行快速搜索查询并筛选审阅集内的内容</span><span class="sxs-lookup"><span data-stu-id="8c4c2-176">Perform fast search queries and filter content in a review set</span></span></p></li>
<li><p><span data-ttu-id="8c4c2-177">分析审阅集内的内容;这包括电子邮件线程、近重复检测、主题分析和预测编码</span><span class="sxs-lookup"><span data-stu-id="8c4c2-177">Analyze content in a review set; this includes email threading, near-duplicate detection, Themes analysis, and Predictive coding</span></span></p></li>
<li><p><span data-ttu-id="8c4c2-178">标记审阅集中的文档</span><span class="sxs-lookup"><span data-stu-id="8c4c2-178">Tag documents in a review set</span></span></p></li>
<li><p><span data-ttu-id="8c4c2-179">可帮助识别律师客户特权内容的标记建议</span><span class="sxs-lookup"><span data-stu-id="8c4c2-179">Tagging suggestions to help identify attorney  client privilege content</span></span></p></li></ul>
<p><span data-ttu-id="8c4c2-180">有关详细信息，请参阅 <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 中的高级电子数据展示解决方案概述</a>。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-180">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Overview of the Advanced eDiscovery solution in Microsoft 365</a>.</span></span></p>
<p>
<p><span data-ttu-id="8c4c2-181">或者，可以将搜索结果导出到 PST 文件，然后使用 Microsoft 365 导入服务将 PST 导入发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-181">Alternatively, you can export search results to PST files and then use Microsoft 365 Import service to import the PSTs to a discovery mailbox.</span></span> <span data-ttu-id="8c4c2-182">有关分步说明，请参阅使用<a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">网络上载将 PST 文件导入到 Office 365。</a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-182">For step-by-step instruction, see <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.</span></span>
</tr>
<tr class=even>
  <td><span data-ttu-id="8c4c2-183">将邮件从一个邮箱复制到另一个邮箱</span><span class="sxs-lookup"><span data-stu-id="8c4c2-183">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="8c4c2-184"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-184"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="8c4c2-185">若要向某人授予访问其他用户的电子邮件的权限 (例如当员工离开您的组织，并且你需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-185">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="8c4c2-186">因此，只需为用户分配访问源邮箱的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-186">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>
<tr class="odd">
<td><span data-ttu-id="8c4c2-187">从"可恢复的项目"文件夹中还原项目</span><span class="sxs-lookup"><span data-stu-id="8c4c2-187">Restore items from the Recoverable Items folder</span></span></td>
  <td><span data-ttu-id="8c4c2-188"><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span><span class="sxs-lookup"><span data-stu-id="8c4c2-188"><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</span></span></td>
  <td><span data-ttu-id="8c4c2-189">只要邮件的已删除项目保留期尚未 (，就可以在邮箱中还原<i></i>永久删除的项目（也称为) 软删除项目）。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-189">You can restore permanently deleted items (also known as <i>soft-deleted</i> items) in mailboxes, as long as the deleted item retention period for an item hasn't expired.</span></span> <span data-ttu-id="8c4c2-190">有关详细信息，请参阅 <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online 中的"可恢复的项目"文件夹</a>。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-190">For more information, see <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Recoverable Items folder in Exchange Online</a>.</span></span></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a><span data-ttu-id="8c4c2-191">有关电子数据展示In-Place保留In-Place常见问题</span><span class="sxs-lookup"><span data-stu-id="8c4c2-191">FAQs about In-Place eDiscovery and In-Place Holds</span></span>

<span data-ttu-id="8c4c2-192">_ 我在 EAC 中In-Place电子数据展示&保留的复制搜索结果功能，将搜索结果复制到发现邮箱供 *律师审查。现在我有什么选项？*\*</span><span class="sxs-lookup"><span data-stu-id="8c4c2-192">_ *I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. What options do I have now?*\*</span></span>

<span data-ttu-id="8c4c2-193">目前，有两种方法可以复制此功能。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-193">There are two ways to replicate this functionality today.</span></span> <span data-ttu-id="8c4c2-194">第一个是在高级 [电子数据展示 v2.0 中使用审阅集](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-194">The first is to use [review sets in Advanced eDiscovery v2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set).</span></span> <span data-ttu-id="8c4c2-195">审阅集具有许多在传统审阅工具中相同的功能，如快速搜索文档、标记、电子邮件线程、近重复分组、主题分析和预测编码。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-195">Review sets have many of the same capabilities you see in a traditional review tool like fast search of documents, tagging, email threading, near duplicate grouping, themes analysis, and predictive coding.</span></span> <span data-ttu-id="8c4c2-196">如果仍要使用发现邮箱进行审阅，第二个选项是将搜索结果导出到 PST 文件，然后使用 Microsoft 合规中心中的 PST 导入功能将 [PST](use-network-upload-to-import-pst-files.md) 文件导入发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-196">If you still want to use discovery mailboxes for review, the second option is to export search results to PST files and then import the PST files to a discovery mailbox by using the [PST import feature](use-network-upload-to-import-pst-files.md) in the Microsoft compliance center.</span></span>

<span data-ttu-id="8c4c2-197">**如何控制电子数据展示 (可以使用新工具搜索) 邮箱或网站等内容位置？**</span><span class="sxs-lookup"><span data-stu-id="8c4c2-197">**How do I control which content locations (such as mailboxes or sites) that can an eDiscovery manager can search using the new tools?**</span></span>

<span data-ttu-id="8c4c2-198">Microsoft 365 合规中心还[](set-up-compliance-boundaries.md)使用合规性边界来控制电子数据展示管理器可以搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-198">The Microsoft 365 compliance center also uses [compliance boundaries](set-up-compliance-boundaries.md) to control which content locations an eDiscovery Manager can search.</span></span> <span data-ttu-id="8c4c2-199">合规性边界在需要位于机构边界内的政府实体或需要遵守地理标志的跨国公司中非常有用。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-199">Compliance boundaries are useful in government entities that need to stay within agency boundaries or multi-national corporations required to respect geographical boarders.</span></span>

<span data-ttu-id="8c4c2-200">**如何将当前搜索和保留移动到 Microsoft 365 合规中心？**</span><span class="sxs-lookup"><span data-stu-id="8c4c2-200">**How can I move my current searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="8c4c2-201">通过使用 PowerShell，In-Place EAC 中迁移电子数据展示搜索和保留。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-201">It's possible to migrate In-Place eDiscovery searches and holds from the EAC by using PowerShell.</span></span> <span data-ttu-id="8c4c2-202">有关说明，请参阅 [将搜索和保留从 EAC 迁移到 Microsoft 365 合规中心](https://go.microsoft.com/fwlink/?linkid=2114224)。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-202">For instructions, see [Migrate searches and holds from the EAC to the Microsoft 365 compliance center](https://go.microsoft.com/fwlink/?linkid=2114224).</span></span>

## <a name="-mailboxsearch-cmdlets"></a><span data-ttu-id="8c4c2-203">\*-MailboxSearch cmdlet</span><span class="sxs-lookup"><span data-stu-id="8c4c2-203">\*-MailboxSearch cmdlets</span></span>

<span data-ttu-id="8c4c2-204">根据 Exchange 管理中心 2017 年 7 月 1 日宣布的原始通知，In-Place 电子数据展示 & 保留功能和相应的 **\* -MailboxSearch** cmdlet 将停用。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-204">As per the original notice announced on July 1, 2017 in the Exchange admin center, the In-Place eDiscovery & Hold functionality and the corresponding **\*-MailboxSearch** cmdlets are being retired.</span></span> <span data-ttu-id="8c4c2-205">这些 cmdlet 使用户能够针对法律、法规和公共请求搜索、保留和导出邮箱内容。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-205">These cmdlets provide users the ability to search, hold, and export mailbox content for legal, regulatory, and public requests.</span></span>

<span data-ttu-id="8c4c2-206">由于 Microsoft [<span class="underline">365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 合规中心和 Office 36 & 5 安全与合规中心 PowerShell 中现已提供这些功能，并且性能和可伸缩性已提高，因此您应该使用这些改进的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-206">Because these capabilities are now available in the [<span class="underline">Microsoft 365 compliance center</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) and Office 365 Security & Compliance Center PowerShell with improved performance and scalability, you should using these improved cmdlets.</span></span> <span data-ttu-id="8c4c2-207">这些 cmdlet 包括[<span class="underline">-ComplianceCase、-ComplianceSearch、-CaseHoldPolicy、-CaseHoldRule \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)和[<span class="underline"> \* -ComplianceSearchAction。</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction) [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)</span><span class="sxs-lookup"><span data-stu-id="8c4c2-207">These cmdlets include [<span class="underline">\*-ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule), and [<span class="underline">\*-ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction).</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="8c4c2-208">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="8c4c2-208">Scope of affected organizations</span></span>

- <span data-ttu-id="8c4c2-209">Office 365 和 Microsoft 365 企业版组织</span><span class="sxs-lookup"><span data-stu-id="8c4c2-209">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="8c4c2-210">Office 365 和 Microsoft 365 教育版组织</span><span class="sxs-lookup"><span data-stu-id="8c4c2-210">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="8c4c2-211">Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="8c4c2-211">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="8c4c2-212">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="8c4c2-212">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="8c4c2-213">日程表</span><span class="sxs-lookup"><span data-stu-id="8c4c2-213">Timeline</span></span>

- <span data-ttu-id="8c4c2-214">2020 年 7 月 1 日：你将无法使用 **New-MailboxSearch** 创建新的 In-Place 电子数据展示搜索和 In-Place 保留，但你仍可以使用 cmdlet 运行、编辑和删除现有搜索和保留，但需要自行承担风险。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-214">July 1, 2020: You won't be able to use **New-MailboxSearch** to create new In-Place eDiscovery searches and In-Place Holds, but you can still use cmdlets to run, edit, and delete existing searches and holds at your own risk.</span></span> <span data-ttu-id="8c4c2-215">Microsoft 支持将不再为这些类型的搜索和保留提供帮助。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-215">Microsoft Support will no longer provide assistance for these types of searches and holds.</span></span>

- <span data-ttu-id="8c4c2-216">2020 年 10 月 1 日：如前所述，EAC 中的 In-Place 电子数据展示 & 保留功能将处于只读模式。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-216">October 1, 2020: As previously stated, The In-Place eDiscovery & Holds functionality in the EAC will be placed in a read-only mode.</span></span> <span data-ttu-id="8c4c2-217">这也意味着你将无法使用 **New-MailboxSearch、Start-MailboxSearch** 或 **Set-MailboxSearch** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-217">That also means that you won't be able to use the **New-MailboxSearch**, **Start-MailboxSearch**, or **Set-MailboxSearch** cmdlets.</span></span> <span data-ttu-id="8c4c2-218">你只能获取和删除现有搜索和保留。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-218">You'll only be able to get and remove existing searches and holds.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="8c4c2-219">备用工具</span><span class="sxs-lookup"><span data-stu-id="8c4c2-219">Alternative tools</span></span>

<span data-ttu-id="8c4c2-220">下表介绍了可用于替换即将停用的现有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-220">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="8c4c2-221">功能</span><span class="sxs-lookup"><span data-stu-id="8c4c2-221">Functionality</span></span></th>
<th><span data-ttu-id="8c4c2-222">备用工具</span><span class="sxs-lookup"><span data-stu-id="8c4c2-222">Alternative tools</span></span></th>
<th><span data-ttu-id="8c4c2-223">备注</span><span class="sxs-lookup"><span data-stu-id="8c4c2-223">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8c4c2-224">搜索和导出</span><span class="sxs-lookup"><span data-stu-id="8c4c2-224">Search and export</span></span></td>
<td><p><span data-ttu-id="8c4c2-225"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-225"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="8c4c2-226"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-226"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p><span data-ttu-id="8c4c2-227"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-227"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="8c4c2-228">ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和导出内容。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-228">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="8c4c2-229">您可以使用<strong>New-、Get</strong>和<strong>Start-ComplianceSearch</strong> cmdlet 创建新的搜索并查看搜索估计值。 <strong></strong></span><span class="sxs-lookup"><span data-stu-id="8c4c2-229">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="8c4c2-230">然后，您可以使用 <strong>New-ComplianceSearchAction</strong> cmdlet 导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-230">Then you can use the <strong>New-ComplianceSearchAction</strong> cmdlet to export the search results.</span></span> <span data-ttu-id="8c4c2-231">你仍必须使用 Microsoft 365 合规中心中的核心电子数据展示工具，将这些搜索结果下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-231">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p>
<p>
<p><span data-ttu-id="8c4c2-232"><strong>注意：</strong>如果您使用这些 cmdlet 创建与核心电子数据展示案例不关联的搜索，这些搜索将位于 Microsoft 365 合规中心的内容搜索<strong></strong>页面上。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-232"><strong>Note:</strong> If you use these cmdlets to create searches that aren't associated with a core eDiscovery case, these searches will be located on the <strong>Content search</strong> page in the Microsoft 365 compliance center.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="8c4c2-233">保留邮箱中的内容</span><span class="sxs-lookup"><span data-stu-id="8c4c2-233">Hold content in a mailbox</span></span></td>
<td><p><span data-ttu-id="8c4c2-234"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-234"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">\*-CaseHoldPolicy</span></a></span></span></p>
<p><span data-ttu-id="8c4c2-235"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-235"><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">\*-CaseHoldRule</span></a></span></span></p>
<p><span data-ttu-id="8c4c2-236"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-236"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">\*-ComplianceCase</span></a></span></span></p>
<p> </p></td>
<td><p><span data-ttu-id="8c4c2-237">Microsoft 365 合规中心中的保留项必须与 ComplianceCase 相关联。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-237">Holds in the Microsoft 365 compliance center must be associated with a ComplianceCase.</span></span> <span data-ttu-id="8c4c2-238">首先，创建合规性案例，然后创建 CaseHoldPolicy 和 CaseHoldRule。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-238">First, create the compliance case, and then create a CaseHoldPolicy and a CaseHoldRule.</span></span></p>
<p><span data-ttu-id="8c4c2-239"><strong>注意：</strong> 创建 CaseHoldPolicy 而不创建 CaseHoldRule 将使保留不可操作，直到创建 CaseHoldRule 并关联到 CaseHoldPolicy。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-239"><strong>Note:</strong> Creating a CaseHoldPolicy without a creating CaseHoldRule will render the hold inoperable until the CaseHoldRule is created and associated to the CaseHoldPolicy.</span></span> <span data-ttu-id="8c4c2-240">有关详细信息，请参阅 cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-240">See the cmdlet documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="8c4c2-241">将搜索结果复制到发现邮箱</span><span class="sxs-lookup"><span data-stu-id="8c4c2-241">Copy search results to a discovery mailbox</span></span></td>
<td><span data-ttu-id="8c4c2-242">无</span><span class="sxs-lookup"><span data-stu-id="8c4c2-242">None</span></span></td>
<td><span data-ttu-id="8c4c2-243">此功能没有直接替代，因为它无法提供对全部 Microsoft 365 服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-243">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="8c4c2-244">有关替代解决方案，请参阅下面的常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-244">See the following FAQ below for alternative solutions.</span></span></td>
</tr>
  <tr class=even>
  <td><span data-ttu-id="8c4c2-245">将邮件从一个邮箱复制到另一个邮箱</span><span class="sxs-lookup"><span data-stu-id="8c4c2-245">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="8c4c2-246"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-246"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="8c4c2-247">若要向某人授予访问其他用户的电子邮件的权限 (例如当员工离开您的组织，并且你需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-247">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="8c4c2-248">因此，只需为用户分配访问源邮箱的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-248">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a><span data-ttu-id="8c4c2-249">关于 \***-MailboxSearch** cmdlet 的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="8c4c2-249">FAQs about \***-MailboxSearch** cmdlets</span></span>

<span data-ttu-id="8c4c2-250">**我们使用复制搜索导出电子邮件或即时消息，以用于其他电子数据展示和法律调查。这些 cmdlet 停用后，我们还有其他哪些选项？**</span><span class="sxs-lookup"><span data-stu-id="8c4c2-250">**We use Copy Search to export email messages or instant Messages for purposes other eDiscovery and legal investigations. What other options do we have after these cmdlets are retired?**</span></span>

<span data-ttu-id="8c4c2-251">与使用 **\* -MailboxSearch** cmdlet 不同 [<span class="underline">，Microsoft Graph API</span>](https://developer.microsoft.com/en-us/graph)提供了多种用于提取数据的方法，以便用于分析和实现其他目的，这些方法的复原和可扩展性要高很多。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-251">The [<span class="underline">Microsoft Graph APIs</span>](https://developer.microsoft.com/en-us/graph) provide a number of methods for extracting data for analysis and other purposes that are far more resilient and scalable than the using the **\*-MailboxSearch** cmdlets.</span></span>

<span data-ttu-id="8c4c2-252">**如何将我的搜索和保留迁移到 Microsoft 365 合规中心？**</span><span class="sxs-lookup"><span data-stu-id="8c4c2-252">**How can I migrate my searches and holds to the Microsoft 365 compliance center?**</span></span>

<span data-ttu-id="8c4c2-253">通过使用 PowerShell 脚本，In-Place Exchange 管理中心迁移电子数据展示搜索和保留项。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-253">It's possible to migrate In-Place eDiscovery searches and holds from the Exchange admin center by using a PowerShell script.</span></span> <span data-ttu-id="8c4c2-254">有关详细信息，请参阅将 [旧版电子数据展示搜索和保留迁移到 Microsoft 365 合规中心](migrate-legacy-eDiscovery-searches-and-holds.md)。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-254">For more information, see [Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).</span></span>

<span data-ttu-id="8c4c2-255">**停用 cmdlet 后，我是否仍能够删除或检索搜索？**</span><span class="sxs-lookup"><span data-stu-id="8c4c2-255">**After the cmdlets are retired, will I still be able to remove or retrieve searches?**</span></span>

<span data-ttu-id="8c4c2-256">可以，尽管我们正在删除创建和修改搜索功能，但您仍可以使用 **Get-MailboxSearch** 和 **Remove-MailboxSearch，** 直到进一步通知为止。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-256">Yes, although we're removing the ability to create and modify searches, you'll still be able to use **Get-MailboxSearch** and **Remove-MailboxSearch** until further notice.</span></span> <span data-ttu-id="8c4c2-257">但是，在停用日期后，使用这些 cmdlet 将自行承担风险，Microsoft 支持将不再能够提供帮助。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-257">However, the use of these cmdlets will be at your own risk after the retirement dates and Microsoft Support will no longer be able to provide assistance.</span></span>

## <a name="search-mailbox-cmdlet"></a><span data-ttu-id="8c4c2-258">Search-Mailbox cmdlet</span><span class="sxs-lookup"><span data-stu-id="8c4c2-258">Search-Mailbox cmdlet</span></span>

<span data-ttu-id="8c4c2-259">Exchange Online PowerShell 中的 **Search-Mailbox** cmdlet 将于 2018 年停用，正如最初在 cmdlet 输出的警告中宣布的一样。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-259">The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018.</span></span> <span data-ttu-id="8c4c2-260">**Search-Mailbox** cmdlet 最初用于搜索用户的邮箱并清除恶意内容。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-260">The **Search-Mailbox** cmdlet was originally used to search a user's mailbox and purge malicious content.</span></span> <span data-ttu-id="8c4c2-261">我们建议您开始使用 Office 365 安全与合规中心 PowerShell 中的 **New-ComplianceSearch** 和 **New-ComplianceSearchAction** cmdlet &搜索和清除内容。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-261">We recommend that you start using the **New-ComplianceSearch** and **New-ComplianceSearchAction** cmdlets in Office 365 Security & Compliance Center PowerShell to search for and purge content.</span></span> <span data-ttu-id="8c4c2-262">对于内置的安全体验 [<span class="underline">，Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/security/) 安全功能为电子邮件和许多其他 Microsoft 服务提供了强大的威胁防护。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-262">For a built-in security experience, the [<span class="underline">Microsoft 365 security features</span>](https://docs.microsoft.com/microsoft-365/security/) provide robust threat protection for email and many other Microsoft services.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="8c4c2-263">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="8c4c2-263">Scope of affected organizations</span></span>

- <span data-ttu-id="8c4c2-264">Office 365 和 Microsoft 365 企业版组织</span><span class="sxs-lookup"><span data-stu-id="8c4c2-264">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="8c4c2-265">Office 365 和 Microsoft 365 教育版组织</span><span class="sxs-lookup"><span data-stu-id="8c4c2-265">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="8c4c2-266">Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="8c4c2-266">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="8c4c2-267">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="8c4c2-267">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="8c4c2-268">日程表</span><span class="sxs-lookup"><span data-stu-id="8c4c2-268">Timeline</span></span>

-  <span data-ttu-id="8c4c2-269">2020 年 7 月 1 日： **搜索邮箱** cmdlet 将不再可用，Microsoft 支持将不再提供帮助。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-269">July 1, 2020: The **Search-Mailbox** cmdlet will no longer be available and Microsoft Support will no longer provide assistance.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="8c4c2-270">备用工具</span><span class="sxs-lookup"><span data-stu-id="8c4c2-270">Alternative tools</span></span>

<span data-ttu-id="8c4c2-271">下表介绍了可用于替换即将停用的现有功能的其他工具。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-271">The following table describes other tools that you can use to replace the existing functionality that's being retired.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="8c4c2-272">功能</span><span class="sxs-lookup"><span data-stu-id="8c4c2-272">Functionality</span></span></th>
<th><span data-ttu-id="8c4c2-273">备用工具</span><span class="sxs-lookup"><span data-stu-id="8c4c2-273">Alternative tools</span></span></th>
<th><span data-ttu-id="8c4c2-274">备注</span><span class="sxs-lookup"><span data-stu-id="8c4c2-274">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="8c4c2-275">搜索邮箱</span><span class="sxs-lookup"><span data-stu-id="8c4c2-275">Search a mailbox</span></span></td>
<td><p><span data-ttu-id="8c4c2-276"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-276"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="8c4c2-277"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-277"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></a></p></td>
<td><p><span data-ttu-id="8c4c2-278">ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和导出内容。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-278">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and export content.</span></span> <span data-ttu-id="8c4c2-279">您可以使用<strong>New-、Get</strong>和<strong>Start-ComplianceSearch</strong> cmdlet 创建新的搜索并查看搜索估计值。 <strong></strong></span><span class="sxs-lookup"><span data-stu-id="8c4c2-279">You can create a new search and view the search estimate by using the <strong>New-</strong>, <strong>Get-</strong>, and <strong>Start-ComplianceSearch</strong> cmdlets.</span></span> <span data-ttu-id="8c4c2-280">然后，可以使用 <strong>New-ComplianceSearchAction -Export</strong> 命令导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-280">Then you can use the <strong>New-ComplianceSearchAction -Export</strong> command to export the search results.</span></span> <span data-ttu-id="8c4c2-281">你仍必须使用 Microsoft 365 合规中心中的核心电子数据展示工具，将这些搜索结果下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-281">You'll still have to use the core eDiscovery tool in the Microsoft 365 compliance center to download those search results to your local computer.</span></span></p></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="8c4c2-282">从邮箱中删除批量电子邮件</span><span class="sxs-lookup"><span data-stu-id="8c4c2-282">Delete bulk email from a mailbox</span></span></td>
<td><p><span data-ttu-id="8c4c2-283"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">设置邮箱的存档和删除策略</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-283"><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Set up an archive and deletion policy for mailboxes</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="8c4c2-284">管理员可以创建存档和删除策略，该策略会自动将项目移动到用户的存档邮箱，并自动从邮箱中删除项目。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-284">Admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="8c4c2-285">将搜索结果复制到发现邮箱</span><span class="sxs-lookup"><span data-stu-id="8c4c2-285">Copy search results to a discovery mailbox</span></span></td>
<td> </td>
<td><span data-ttu-id="8c4c2-286">此功能没有直接替代，因为它无法提供对全部 Microsoft 365 服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-286">There's no direct replacement for this functionality because it does not provide access to all Microsoft 365 services.</span></span> <span data-ttu-id="8c4c2-287">有关替代解决方案，请参阅 <strong>\*-MailboxSearch cmdlets</strong> 部分中的常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-287">See the FAQs in the <strong>\*-MailboxSearch cmdlets</strong> section for alternative solutions.</span></span> </td>
</tr>
<tr class=odd>
  <td><span data-ttu-id="8c4c2-288">将邮件从一个邮箱复制到另一个邮箱</span><span class="sxs-lookup"><span data-stu-id="8c4c2-288">Copy messages from one mailbox to a different mailbox</span></span></td>
  <td><span data-ttu-id="8c4c2-289"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-289"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
  <td><span data-ttu-id="8c4c2-290">若要向某人授予访问其他用户的电子邮件的权限 (例如当员工离开您的组织，并且你需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-290">To give a person access to another user's email (such as when an employee leaves your organization and you need to give another person access to the former employee's email), we recommended that you assign that person permissions to access the former employee's mailbox.</span></span> <span data-ttu-id="8c4c2-291">因此，只需为用户分配访问源邮箱的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-291">So instead of copying mailbox items to another user mailbox or a shared mailbox, just assign a user permissions to access the source mailbox.</span></span></td>
</tr>
<tr class=even>
  <td><span data-ttu-id="8c4c2-292">清除邮箱中的邮件</span><span class="sxs-lookup"><span data-stu-id="8c4c2-292">Purge messages from a mailbox</span></span></td>
<td><p><span data-ttu-id="8c4c2-293"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-293"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">\*-ComplianceSearch</span></a></span></span></p>
<p><span data-ttu-id="8c4c2-294"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-294"><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">\*-ComplianceSearchAction</span></a></span></span></p>
<p></p></td>
<td><p><span data-ttu-id="8c4c2-295">ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和清除内容。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-295">The ComplianceSearch and ComplianceSearchAction cmdlets work together to help you search and purge content.</span></span> <span data-ttu-id="8c4c2-296">可以使用 <strong>New-ComplianceSearch</strong> 和 <strong>New-ComplianceSearch</strong> cmdlet 创建和运行搜索，然后可以使用 <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> 命令清除内容。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-296">You can create and run a search with <strong>New-ComplianceSearch</strong> and <strong>New-ComplianceSearch</strong> cmdlets, and then you can purge the content by using <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> command.</span></span> <span data-ttu-id="8c4c2-297">有关详细信息，请参阅"<a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">搜索和删除邮件"。</span></a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-297">For more information, see <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Search for and delete messages</span></a>.</span></span></p>
</td>
</tr>
<tr class="odd"> 
<td><span data-ttu-id="8c4c2-298">清除邮箱中的邮件</span><span class="sxs-lookup"><span data-stu-id="8c4c2-298">Purge messages from a mailbox</span></span></td>
<td><span data-ttu-id="8c4c2-299"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></span><span class="sxs-lookup"><span data-stu-id="8c4c2-299"><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Assign permissions to a mailbox</a></span></span></td>
<td><span data-ttu-id="8c4c2-300">若要清除邮箱中的邮件，请分配管理员权限以访问员工的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-300">To purge messages from a mailbox, assign an administrator permissions to access the employee's mailbox.</span></span> <span data-ttu-id="8c4c2-301">可以根据需要删除和回收邮件，以利用 Outlook 中的内置搜索和查看功能。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-301">Messages can be deleted and recycled as needed taking advantage of the built in search and viewing capabilities in Outlook.</span></span></td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a><span data-ttu-id="8c4c2-302">Exchange Web 服务 API 操作</span><span class="sxs-lookup"><span data-stu-id="8c4c2-302">Exchange Web Services API operations</span></span>

<span data-ttu-id="8c4c2-303">Exchange Web 服务 API 中的这些操作由 Exchange 管理中心的 In-Place 电子数据展示 & 保留功能以及 Exchange Online PowerShell 中的相应 **\* -MailboxSearch** cmdlet 使用。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-303">These operations in the Exchange Web Services API are used by the In-Place eDiscovery & Holds feature in the Exchange admin center and the corresponding **\*-MailboxSearch** cmdlets in Exchange Online PowerShell.</span></span> <span data-ttu-id="8c4c2-304">作为停用其他旧版电子数据展示工具的一部分，这些工具也将停用。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-304">They will also be retired as part of retiring the other legacy eDiscovery tools.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="8c4c2-305">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="8c4c2-305">Scope of affected organizations</span></span>

- <span data-ttu-id="8c4c2-306">Office 365 和 Microsoft 365 企业版组织</span><span class="sxs-lookup"><span data-stu-id="8c4c2-306">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="8c4c2-307">Office 365 和 Microsoft 365 教育版组织</span><span class="sxs-lookup"><span data-stu-id="8c4c2-307">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="8c4c2-308">Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="8c4c2-308">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="8c4c2-309">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="8c4c2-309">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="8c4c2-310">日程表</span><span class="sxs-lookup"><span data-stu-id="8c4c2-310">Timeline</span></span>

- <span data-ttu-id="8c4c2-311">2020 年 7 月 1 日：GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 操作将不再可用，并且 Microsoft 支持将不再提供帮助。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-311">July 1, 2020: The GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes, and GetHoldOnMailboxes operations will no longer be available, and Microsoft Support will no longer provide assistance.</span></span>

## <a name="advanced-ediscovery-v10"></a><span data-ttu-id="8c4c2-312">高级电子数据展示 v1.0</span><span class="sxs-lookup"><span data-stu-id="8c4c2-312">Advanced eDiscovery v1.0</span></span>

<span data-ttu-id="8c4c2-313">高级电子数据展示 v1.0（通过单击"切换到高级电子数据展示"可在核心电子数据展示案例中使用的高级电子数据展示版本）即将停用。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-313">Advanced eDiscovery v1.0, which is the version of Advanced eDiscovery available in a core eDiscovery case by clicking **Switch to Advanced eDiscovery**, is being retired.</span></span> <span data-ttu-id="8c4c2-314">它的功能已被 Microsoft 365 合规中心中新的高级电子数据展示解决方案所取代。 [](https://aka.ms/edisco)</span><span class="sxs-lookup"><span data-stu-id="8c4c2-314">Its functionality has been replaced by the new [Advanced eDiscovery solution](https://aka.ms/edisco) in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="8c4c2-315">若要确定组织是否使用高级电子数据展示 v1.0：</span><span class="sxs-lookup"><span data-stu-id="8c4c2-315">To determine if your organization is using Advanced eDiscovery v1.0:</span></span>

1. <span data-ttu-id="8c4c2-316">转到 [Office 365 安全&合规中心](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-316">Go to the [Office 365 Security & Compliance Center](https://protection.office.com).</span></span>

2. <span data-ttu-id="8c4c2-317">在安全与合规中心的&窗格中，单击电子数据展示> **电子** 数据展示，然后打开核心电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-317">In the left navigation pane of the Security & Compliance Center, click **eDiscovery > eDiscovery**, and open a Core eDiscovery case.</span></span>

3. <span data-ttu-id="8c4c2-318">如果看到" **切换到高级电子数据** 展示"按钮，则单击此按钮将进入 1.0 版高级电子数据展示（即将停用）。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-318">If you see the **Switch to Advanced eDiscovery** button, then clicking it will take you to the 1.0 version of Advanced eDiscovery, which is being retired.</span></span> <span data-ttu-id="8c4c2-319">在核心电子数据展示中创建和管理事例的能力不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-319">The ability to create and manage cases in Core eDiscovery won't be affected.</span></span> <span data-ttu-id="8c4c2-320">仅通过单击"切换到高级电子数据展示" (在高级电子数据展示 v1.0) 中添加和分析案例数据的能力将停用。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-320">Only the ability to add and analyze case data in Advanced eDiscovery v1.0 (by clicking **Switch to Advanced eDiscovery**) is being retired.</span></span>

<span data-ttu-id="8c4c2-321">Microsoft 365 (中新的高级电子数据展示解决方案也称为高级电子数据展示 *v2.0*) 提供了原始解决方案的所有功能，但现在包括一种基于保管人的方法，用于识别其他 Microsoft 365 服务中的内容、收集该内容，然后将它添加到审阅集，审阅者可以利用快速搜索查询、标记和分析功能来帮助剔除相关文档。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-321">The new Advanced eDiscovery solution in Microsoft 365 (also known as *Advanced eDiscovery v2.0*) provides all of the capabilities of the original solution, but now includes a custodian-based approach of identifying content in other Microsoft 365 services, collecting that content, and then adding it to a review set where reviewers can take advantage of fast search queries, tagging, and analytics features to help cull relevant documents.</span></span> <span data-ttu-id="8c4c2-322">高级电子数据展示现在包括针对 Microsoft 和非 Microsoft 文件类型的改进处理和本机查看器，文件类型的完整列表在此处，支持的元数据[字段在此处](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)。 [](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20)</span><span class="sxs-lookup"><span data-stu-id="8c4c2-322">Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) and supported metadata fields are [here](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery).</span></span> <span data-ttu-id="8c4c2-323">此外，新的高级电子数据展示解决方案提供了功能强大的保管人保留管理功能，使你可以将保留应用于不同服务中的内容，通知用户保留，并跟踪保管人响应，所有这些都位于高级电子数据展示案例中。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-323">Also, the new Advanced eDiscovery solution provides a powerful custodian holds management feature that lets you apply holds to content in different services, notify users of the holds, and track custodian responses, all within an Advanced eDiscovery case.</span></span>

<span data-ttu-id="8c4c2-324">若要访问高级电子数据展示 v2.0：</span><span class="sxs-lookup"><span data-stu-id="8c4c2-324">To access Advanced eDiscovery v2.0:</span></span>

1. <span data-ttu-id="8c4c2-325">转到 [Microsoft 365 合规中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-325">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="8c4c2-326">在 Microsoft 365 合规中心的左侧导航窗格中，单击"全部显示"，然后单击"电子数据展示>**高级"**。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-326">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

<span data-ttu-id="8c4c2-327">此时，我们建议您开始将电子数据展示工作流转换为新的高级电子数据展示功能。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-327">At this time, we recommend that you begin to transition your eDiscovery workflow to the new Advanced eDiscovery functionality.</span></span> <span data-ttu-id="8c4c2-328">如果需要，可以通过导出内容并脱机存储内容来存档高级电子数据展示 1.0 事例。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-328">If required, you can archive your Advanced eDiscovery 1.0 cases by exporting the content and storing it offline.</span></span> <span data-ttu-id="8c4c2-329">尽管在 2020 年 12 月 31 日之前，你仍然能够访问高级电子数据展示 v1.0，但 Microsoft 支持在 2020 年 10 月 1 日之后不会提供支持。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-329">Although you'll still be able to access Advanced eDiscovery v1.0 in existing cases until December 31, 2020, Microsoft Support won't provide support after October 1, 2020.</span></span> <span data-ttu-id="8c4c2-330">有关详细信息，请参阅以下日程表。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-330">See the following timeline for more details.</span></span>

### <a name="scope-of-affected-organizations"></a><span data-ttu-id="8c4c2-331">受影响组织的范围</span><span class="sxs-lookup"><span data-stu-id="8c4c2-331">Scope of affected organizations</span></span>

- <span data-ttu-id="8c4c2-332">Office 365 和 Microsoft 365 企业版组织</span><span class="sxs-lookup"><span data-stu-id="8c4c2-332">Office 365 and Microsoft 365 Enterprise organizations</span></span>

- <span data-ttu-id="8c4c2-333">Office 365 和 Microsoft 365 教育版组织</span><span class="sxs-lookup"><span data-stu-id="8c4c2-333">Office 365 and Microsoft 365 Education organizations</span></span>

- <span data-ttu-id="8c4c2-334">Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD</span><span class="sxs-lookup"><span data-stu-id="8c4c2-334">Office 365 and Microsoft 365 Government organizations; this includes GCC, GCC High, and DoD</span></span>

- <span data-ttu-id="8c4c2-335">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="8c4c2-335">Office 365 Germany</span></span>

### <a name="timeline"></a><span data-ttu-id="8c4c2-336">日程表</span><span class="sxs-lookup"><span data-stu-id="8c4c2-336">Timeline</span></span>

- <span data-ttu-id="8c4c2-337">2020 年 7 月 1 日：无法创建新的高级电子数据展示 v1.0 事例。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-337">July 1, 2020: You won't be able to create new Advanced eDiscovery v1.0  cases.</span></span>

- <span data-ttu-id="8c4c2-338">2020 年 10 月 1 日：无法添加新数据 (为高级电子数据展示) 搜索结果。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-338">October 1, 2020: You won't be able to add new data (Prepare search results for Advanced eDiscovery) to any cases.</span></span> <span data-ttu-id="8c4c2-339">你将能够继续处理现有情况下的数据，风险由你自己承担。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-339">You'll be able to continue working with data in existing cases at your own risk.</span></span> <span data-ttu-id="8c4c2-340">Microsoft 支持将不再提供帮助。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-340">Microsoft Support will no longer provide assistance.</span></span> 

- <span data-ttu-id="8c4c2-341">2020 年 12 月 31 日：无法访问高级电子数据展示 v1.0 事例。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-341">December 31, 2020: You won't be able to access Advanced eDiscovery v1.0 cases.</span></span>

### <a name="alternative-tools"></a><span data-ttu-id="8c4c2-342">备用工具</span><span class="sxs-lookup"><span data-stu-id="8c4c2-342">Alternative tools</span></span>

<span data-ttu-id="8c4c2-343">Microsoft [](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) 365 合规中心中的高级电子数据展示解决方案。</span><span class="sxs-lookup"><span data-stu-id="8c4c2-343">The [Advanced eDiscovery solution](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) in the Microsoft 365 compliance center.</span></span>
