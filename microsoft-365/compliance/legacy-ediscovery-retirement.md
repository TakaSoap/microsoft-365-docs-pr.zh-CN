---
title: 旧电子数据展示工具的退休
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
ms.openlocfilehash: 08f568a82096efb143ff5c9fd87011a3d3029e42
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210057"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>旧电子数据展示工具的退休

多年以来，Microsoft 提供了电子数据展示工具，可让你搜索、预览和导出来自 Exchange Online 的电子邮件内容。 但是，这些工具不再提供在其他 Office 365 服务（如 SharePoint Online 和 Office 365 组）中搜索非 Exchange 内容的有效方法。 为解决此类情况，Microsoft 提供了其他电子数据展示工具，可帮助您搜索各种各样的 Office 365 内容。 我们在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中努力将最新和强大的电子数据展示功能结合在一起。 这使组织能够对多个 Office 365 服务（包括 Exchange Online）中的内容进行法律、内部和其他文档请求的响应。

由于 Microsoft 365 合规性中心中新增和改进的电子数据展示功能，我们即将淘汰以下与搜索电子邮件内容相关的电子数据展示相关特性和功能：

- Exchange 管理中心内的[就地电子数据展示](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)和[就地保留](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)。

- 支持就地电子数据展示和就地保留的 Exchange Online PowerShell cmdlet （这些 cmdlet 共同标识为 **-new-mailboxsearch* cmdlet）。 这包括以下 cmdlet：

  - [新 New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-mailboxsearch)

  - [启动-New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-mailboxsearch)

  - [New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/stop-mailboxsearch)

  - [New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-mailboxsearch)

   > [!NOTE]
   > [New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)和[new-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch) cmdlet 将在其他 * * * *-new-mailboxsearch * * （cmdlet 已停用之后提供，以便您可以使用它们来帮助您过渡到其他电子数据展示和保留工具。 但是，在某个特定日期（如下所示）后，Microsoft 支持将不再支持这两个 cmdlet。

- Exchange Online PowerShell 中的[搜索邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps)cmdlet。

- Exchange Web Services API 中的以下操作：

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)v1.0，它是高级电子数据展示的第一个版本，可通过 Office 365 安全性 & 合规性中心中的电子数据展示事例进行访问。

> [!NOTE]
> 要废弃的电子数据展示功能仅适用于基于云的 Microsoft 365 和 Office 365 版本。 在 Exchange 和 SharePoint 的本地版本中，电子数据展示功能将仍受支持，直至进一步通知。

本文中的以下各节提供有关即将停用的每个功能的指导。 此信息包括可供您使用的时间线和替代工具，而不是退休工具。

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>Exchange 管理中心内的就地电子数据展示和就地保留 

根据2017年7月1日的原始通知，将停用 Exchange 管理中心（EAC）中的 "就地电子数据展示 & 保留功能"。 EAC 中的就地电子数据展示 & 保留页面允许您搜索、保留和导出 Exchange Online 中的内容。 就地电子数据展示还允许您将搜索结果复制到发现邮箱，以便您或其他电子数据展示管理者可以查看内容并使其可用于法律、法规和公共请求。

由于所有这些功能（除了将搜索结果复制到发现邮箱之外）现已在[microsoft 365 合规性中心](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)的内容搜索、电子数据展示和高级电子数据展示工具（改进了各种 Microsoft 365 服务的功能、可靠性和支持）中提供，我们建议您尽快开始使用这些工具。 为了帮助您转换到这些其他电子数据展示工具，下表列出了您可以使用的工具，而不是就地电子数据展示和就地保留。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365 和 Microsoft 365 企业组织

- Office 365 和 Microsoft 365 教育组织

- Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline-for-retirement"></a>停用的日程表

- 2020年4月1日：您将无法创建新的搜索和保留，但您仍可以自行承担运行、编辑和删除现有搜索。 Microsoft 支持将不再将 EAC 中的电子数据展示 & 保留。

- 2020年7月1日：就地电子数据展示 & 保留 EAC 中的功能将被置于只读模式下。 这意味着您将只能删除现有的搜索和保留。

### <a name="alternative-tools"></a>替代工具

下表介绍了可用于替换即将停用的现有功能的其他工具。

<table>
<thead>
<tr class="header">
<th><strong>功能</strong></th>
<th><strong>替代工具</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>出于法律目的进行搜索、导出和保留</td>
<td>Microsoft 365 合规性中心中的核心电子数据展示案例 </td>
<td><p>使用核心电子数据展示事例的功能，可为就地电子数据展示和就地保留提供功能性奇偶校验。 其中包括：</p>
<ul>
<li>
<p>搜索范围扩展到数百万个位置</p>
</li>
<li>
<p>更高的可靠性用于搜索、导出和放置保留内容</p>
</li>
<li>
<p>在 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft 团队、Yammer 组、Office 365 组以及存储在 Office 365 应用程序中的其他内容中搜索内容</p></li></ul>
<p>有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">在 Office 365 中管理法律调查</a>。</td>
</tr>
<tr class="even">
<td>保留以供保留之用</td>
<td>Microsoft 365 合规性中心中的保留策略</td>
<td><p>您可以使用保留策略保留内容，如果需要，请在保留期到期后将其删除。 其他功能包括：</p>
<ul>
<li>
<p>将策略应用于整个组织 </p>
</li><li>
<p>将策略应用于特定的内容位置，如 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft 团队和 Office 365 组</p></li>
<li>
<p>将策略应用于特定用户</p></li></ul>
<p>有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">保留策略概述</a>。</td>
</tr>
<tr class="odd">
<td>将电子邮件搜索结果复制到发现邮箱以供审阅</td><td>高级电子数据展示2.0 版中的审阅集</td>
<td><p>在 Microsoft 365 中查看内容从未像以前这样轻松。 查看集具有许多有用的功能，可帮助减少所需的查看时间和数据量，包括：</p>
<ul>
<li><p>在审阅集中执行 fast search 查询和筛选内容</p></li>
<li><p>分析审阅集中的内容;这包括电子邮件线索、临近重复检测、主题分析和预测编码</p></li>
<li><p>标记审阅集中的文档</p></li>
<li><p>帮助识别律师客户端权限内容的标记建议</p></li></ul>
<p>有关详细信息，请参阅 <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 中的高级电子数据展示解决方案概述</a>。</p>
<p>
<p>或者，可以将搜索结果导出到 PST 文件，然后使用 Microsoft 365 导入服务将 Pst 导入到发现邮箱。 有关分步说明，请参阅<a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">使用网络上载将 PST 文件导入到 Office 365</a>。
</tr>
<tr class="even">
<td>还原 "可恢复的项目" 文件夹中的项目</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>您可以还原邮箱中永久删除的项目（也称为<i>软删除</i>的项目），只要项目的已删除邮件保留期尚未过期。 有关详细信息，请参阅<a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online 中的 "可恢复的项目" 文件夹</a>。</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>有关就地电子数据展示和就地保留的常见问题解答

**我使用就地电子数据展示 & 保留在 EAC 中的 "复制搜索结果" 功能，将搜索结果复制到发现邮箱以供律师审阅。我现在有哪些选项？**

目前，有两种方法可以复制此功能。 第一种是[在高级电子数据展示 2.0 2.0 中使用审阅集](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)。 评审集具有许多与传统审阅工具（如快速搜索文档、标记、电子邮件线程、临近重复分组、主题分析和预测编码）有关的功能。 如果仍要使用发现邮箱进行审阅，第二个选项是将搜索结果导出到 PST 文件，然后使用 Microsoft 合规性中心中的[pst 导入功能](use-network-upload-to-import-pst-files.md)将 pst 文件导入到发现邮箱。

**如何控制电子数据展示管理器可以使用新工具搜索的内容位置（如邮箱或网站）？**

Microsoft 365 合规性中心还使用[合规性边界](set-up-compliance-boundaries.md)来控制电子数据展示管理器可搜索的内容位置。 合规性边界适用于需要在机构边界或需要遵守地理 boarders 的多国公司内部的政府实体。

**如何将当前的搜索和保留移动到 Microsoft 365 合规性中心？**

可以使用 PowerShell 从 EAC 迁移就地电子数据展示搜索和保留。 有关说明，请参阅将[搜索和保留从 EAC 迁移到 Microsoft 365 合规性中心](https://go.microsoft.com/fwlink/?linkid=2114224)。

## <a name="-mailboxsearch-cmdlets"></a>\*-New-mailboxsearch cmdlet

根据在 Exchange 管理中心中的2017年7月1日宣布的原始通知，就地电子数据展示 & 保留功能和相应** \*的 new-mailboxsearch** cmdlet 将被停用。 这些 cmdlet 使用户能够搜索、保留和导出适用于法律、法规和公共请求的邮箱内容。

由于这些功能现已在[<span class="underline">Microsoft 365 合规性中心</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)和 Office 365 安全性 & 合规性中心 PowerShell 中提供了改进的性能和可伸缩性，因此您应使用这些改进的 cmdlet。 这些 cmdlet 包括[<span class="underline"> \*-get-compliancecase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase)、 [<span class="underline"> \*-new-compliancesearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)、 [<span class="underline"> \*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)、 [<span class="underline"> \*-new-caseholdrule</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule)和[<span class="underline"> \*-new-compliancesearchaction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365 和 Microsoft 365 企业组织

- Office 365 和 Microsoft 365 教育组织

- Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline"></a>日程表

- 2020年4月1日：您将无法使用**new-mailboxsearch**创建新的就地电子数据展示搜索和就地保留，但您仍可以使用 cmdlet 来运行、编辑和删除现有搜索并保留自己的风险。 Microsoft 支持将不再为这些类型的搜索和保留提供帮助。

- 2020年7月1日：如前所述，就地电子数据展示 & 保留 EAC 中的功能将被置于只读模式下。 这也意味着您不能使用**new-mailboxsearch**、 **Start-new-mailboxsearch**或**new-mailboxsearch** cmdlet。 你将只能获取和删除现有搜索和保留。

### <a name="alternative-tools"></a>替代工具

下表介绍了可用于替换即将停用的现有功能的其他工具。

<table>
<thead>
<tr class="header">
<th><strong>功能</strong></th>
<th><strong>替代工具</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>搜索和导出</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">*-New-compliancesearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">*-Get-compliancecase</span></a></p>
<p> </p></td>
<td><p>New-compliancesearch 和 New-compliancesearchaction cmdlet 一起使用可帮助您搜索和导出内容。 您可以使用<strong>new-</strong>、 <strong>Get</strong>和<strong>new-compliancesearch</strong> cmdlet 来创建新搜索并查看搜索估计。 然后，您可以使用<strong>new-compliancesearchaction</strong> cmdlet 导出搜索结果。 您仍需使用 Microsoft 365 合规性中心中的核心电子数据展示工具将这些搜索结果下载到您的本地计算机上。</p>
<p>
<p><strong>注意：</strong>如果您使用这些 cmdlet 来创建不与核心电子数据展示事例关联的搜索，则这些搜索将位于 Microsoft 365 合规性中心的<strong>内容搜索</strong>页中。</p></td>
</tr>
<tr class="even">
<td>保留邮箱中的内容</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">*-New-caseholdrule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">*-Get-compliancecase</span></a></p>
<p> </p></td>
<td><p>Microsoft 365 合规性中心中的保留必须与 Get-compliancecase 相关联。 首先，创建合规性事例，然后创建 CaseHoldPolicy 和 New-caseholdrule。</p>
<p><strong>注意：</strong>创建没有创建 New-caseholdrule 的 CaseHoldPolicy 将使保留不可操作，直到创建 New-caseholdrule 并将其与 CaseHoldPolicy 关联。 有关详细信息，请参阅 cmdlet 文档。</p></td>
</tr>
<tr class="odd">
<td>将搜索结果复制到发现邮箱</td>
<td>无</td>
<td>此功能没有直接替代，因为它不提供对所有 Microsoft 365 服务的访问权限。 有关其他解决方案，请参阅下面的 FAQ。</td>
</tr>
</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>有关 ***-new-mailboxsearch cmdlet 的**常见问题解答

**我们使用复制搜索来导出电子邮件或即时消息，以供其他电子数据展示和法律调查使用。停用这些 cmdlet 后还有哪些其他选项？**

[<span class="underline">Microsoft Graph api</span>](https://developer.microsoft.com/en-us/graph)提供了多种方法，用于提取用于分析的数据，以及与使用** \*-new-mailboxsearch** cmdlet 相比更具弹性和可伸缩性的其他目的。

**如何将我的搜索和保留迁移到 Microsoft 365 合规性中心？**

可以使用 PowerShell 脚本从 Exchange 管理中心迁移就地电子数据展示搜索和保留。 有关详细信息，请参阅将[旧电子数据展示搜索和保留迁移到 Microsoft 365 合规性中心](migrate-legacy-eDiscovery-searches-and-holds.md)。

**Cmdlet 停用后，我是否仍可以删除或检索搜索？**

是的，尽管我们要删除创建和修改搜索的功能，但仍可以使用**new-mailboxsearch**和**new-mailboxsearch** ，直到再次通知。 但是，这些 cmdlet 在退休日期后将受到自己的威胁，Microsoft 支持将不再能够提供协助。

## <a name="search-mailbox-cmdlet"></a>搜索-邮箱 cmdlet

Exchange Online PowerShell 中的**搜索邮箱**cmdlet 将被停用，因为最初在2018的 cmdlet 输出中已宣布出现警告。 **搜索邮箱**cmdlet 最初用于搜索用户的邮箱并清除恶意内容。 我们建议您开始使用 Office 365 Security & 合规性中心 PowerShell 中的**new-compliancesearch**和**new-compliancesearchaction** cmdlet 来搜索和清除内容。 对于内置的安全体验， [<span class="underline">microsoft 365 安全功能</span>](https://docs.microsoft.com/microsoft-365/security/)为电子邮件和许多其他 Microsoft 服务提供了强健的威胁防护。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365 和 Microsoft 365 企业组织

- Office 365 和 Microsoft 365 教育组织

- Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline"></a>日程表

-  2020年4月1日：将不再提供**搜索邮箱**Cmdlet，Microsoft 支持将不再提供帮助。

### <a name="alternative-tools"></a>替代工具

下表介绍了可用于替换即将停用的现有功能的其他工具。

<table>
<thead>
<tr class="header">
<th><strong>功能</strong></th>
<th><strong>替代工具</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>搜索邮箱</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">*-New-compliancesearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p></a></p></td>
<td><p>New-compliancesearch 和 New-compliancesearchaction cmdlet 一起使用可帮助您搜索和导出内容。 您可以使用<strong>new-</strong>、 <strong>Get</strong>和<strong>new-compliancesearch</strong> cmdlet 来创建新搜索并查看搜索估计。 然后，可以使用<strong>new-compliancesearchaction-export</strong>命令导出搜索结果。 您仍需使用 Microsoft 365 合规性中心中的核心电子数据展示工具将这些搜索结果下载到您的本地计算机上。</p></p>
</td>
</tr>
<tr class="even">
<td>清除邮箱中的邮件</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">*-New-compliancesearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p></p></td>
<td><p>New-compliancesearch 和 New-compliancesearchaction cmdlet 一起使用可帮助您搜索和清除内容。 您可以使用<strong>new-compliancesearch</strong>和<strong>new-compliancesearch</strong> cmdlet 创建和运行搜索，然后您可以使用<strong>new-compliancesearchaction-PurgeType</strong>命令清除内容的内容。 有关详细信息，请参阅<a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">搜索和删除邮件</span></a>。</p>
</td>
</tr>
<tr class="odd">
<td>将搜索结果复制到发现邮箱</td>
<td> </td>
<td>此功能没有直接替代，因为它不提供对所有 Microsoft 365 服务的访问权限。 有关替代解决方案，请参阅 " <strong>*-new-mailboxsearch cmdlet</strong> " 部分中的 faq。 </td>
</tr>
</tbody>
</table>

## <a name="getsearchablemailboxes-setholdonmailboxes-and-getholdonmailboxes-operations-in-the-ews-api"></a>EWS API 中的 GetSearchableMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 操作

Exchange 管理中心中的 "就地电子数据展示 & 保留" 功能和 exchange Online PowerShell 中的相应** \*new-mailboxsearch** cmdlet 使用这三个 Exchange Web Services api。 在停用其他旧的电子数据展示工具时，它们也会被停用。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365 和 Microsoft 365 企业组织

- Office 365 和 Microsoft 365 教育组织

- Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline"></a>日程表

- 2020年4月1日： GetSearchableMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 操作将不再可用，Microsoft 支持将不再提供协助。

## <a name="advanced-ediscovery-v10"></a>高级电子数据展示1.0 版

高级电子数据展示 v1.0，即在电子数据展示事例中，通过单击 "**切换到高级电子数据展示**" 将停用的高级电子数据展示的版本。 其功能已在 Microsoft 365 合规性中心中的新[高级电子数据展示解决方案](https://aka.ms/edisco)中取代。

Microsoft 365 中新的高级电子数据展示解决方案（也称为*高级电子数据展示 2.0 2.0*）提供了原始解决方案的所有功能，但现在提供了一种基于保管人的方法，可识别其他 Microsoft 365 服务中的内容，收集该内容，然后将其添加到审阅集中，以便审阅者可以利用 fast search 查询、标记和分析功能来帮助挑选相关文档。 高级电子数据展示现在为 Microsoft 和非 Microsoft 文件类型提供了改进的处理和本机查看器[，此处提供](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20)了文件类型的完整列表以及支持[的元数据字段。](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery) 此外，新的高级电子数据展示解决方案提供了强大的保管人保留功能，允许您将保留应用于不同服务中的内容、通知用户保留和在高级电子数据展示事例中跟踪保管人响应。

此时，我们建议您开始将电子数据展示工作流转换为新的高级电子数据展示功能。 尽管您仍可以在现有情况下访问高级电子数据展示 v1.0，但 Microsoft 支持不会在2020年7月1日之后提供支持。 有关详细信息，请参阅以下日程表。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围
    
- Office 365 和 Microsoft 365 企业组织

- Office 365 和 Microsoft 365 教育组织

- Office 365 德国

### <a name="timeline"></a>日程表

- 2020年4月1日：你将无法创建新的高级电子数据展示 v1.0 事例。

- 2020年7月1日：无法将新数据（为高级电子数据展示准备搜索结果）添加到任何情况。 你将能够继续使用现有案例中的数据，风险自负。 Microsoft 支持将不再提供协助。 

### <a name="alternative-tools"></a>替代工具

Microsoft 365 合规性中心中的[高级电子数据展示解决方案](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。
