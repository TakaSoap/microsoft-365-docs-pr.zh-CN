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
# <a name="retirement-of-legacy-ediscovery-tools"></a>旧版电子数据展示工具的停用

> [!IMPORTANT]
> Microsoft 一直在评估公众健康情况，并且我们了解这对我们的客户的影响。 我们希望成为强大的合作伙伴和负责的全球公民。 为了减轻您面临的众多负担之一，我们将将本文中所述的旧电子数据展示工具的计划停用延迟三个月。 **更新后的停用日期如下。**

多年来，Microsoft 提供了电子数据展示工具，可用于搜索、预览和导出 Exchange Online 中的电子邮件内容。 但是，这些工具不再提供在其他 Microsoft 365 服务（如 SharePoint Online 和 Microsoft 365 组）中搜索非 Exchange 内容的有效方法。 为解决这一问题，Microsoft 提供了其他电子数据展示工具，可帮助你搜索各种 Microsoft 365 内容。 我们一直在努力在 [Microsoft 365](https://compliance.microsoft.com)合规中心内整合最新且强大的电子数据展示功能。 这允许组织对跨许多 Microsoft 365 服务（包括 Exchange Online）的内容的法律、内部和其他文档请求做出响应。

作为 Microsoft 365 合规中心中这一全新和改进电子数据展示功能的结果，我们将停用以下与在 Exchange Online 和 Microsoft 365 中搜索电子邮件内容相关的电子数据展示相关特性和功能：

- [Exchange 管理中心中的](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) 就地电子数据展示 [和就地](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) 保留。

- 支持 In-Place 电子数据展示和 In-Place 保留的 Exchange Online PowerShell cmdlet (这些 cmdlet 统称为 **-MailboxSearch* cmdlet) 。 这包括以下 cmdlet：

  - [New-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > 在其他 ****-MailboxSearch**_ cmdlet 停用后 [，Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) 和 [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) cmdlet 将可用，以便您可以使用它们来帮助转换到其他电子数据展示和保留工具。 但是，在下面引用 (日期后) Microsoft 支持将不再支持这两个 cmdlet。

- Exchange Online PowerShell 中的 [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) cmdlet。

- Exchange Web 服务 API 中的以下操作：

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 高级电子数据展示 v1.0，](office-365-advanced-ediscovery.md)这是通过 Office 365 安全与合规中心的核心电子数据展示案例访问的高级电子数据展示 &的第一个版本。 停用高级电子数据展示 v1.0 不会影响创建和管理核心电子数据展示事例的能力。

> [!NOTE]
> 要停用的电子数据展示功能仅适用于基于云的 Microsoft 365 和 Office 365 版本。 在进一步通知之前，Exchange 和 SharePoint 本地版本中电子数据展示功能仍将受支持。

本文中的以下各节提供有关要停用的每个功能的指导。 此信息包括日程表和可使用的替代工具，而不是停用的工具。

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place Exchange 管理中心In-Place电子数据展示和保留 

根据 2017 年 7 月 1 日的原始通知，Exchange 管理中心 (In-Place EAC) 中的 In-Place 电子数据展示 & 保留功能即将停用。 EAC In-Place电子数据展示&保留"页允许从 Exchange Online 搜索、保留和导出内容。 In-Place电子数据展示还使你可以将搜索结果复制到发现邮箱，以便你或其他电子数据展示管理员可以审阅内容，使其可用于法律、法规和公共请求。

由于除将搜索结果复制到发现邮箱) 之外的所有功能) 现在都可用于 [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 合规中心 (中的内容搜索、电子数据展示和高级电子数据展示工具，并改进了功能、可靠性和对各种 Microsoft 365 服务) 的支持，因此我们建议您尽快开始使用这些工具。 ( 为了帮助你过渡到这些其他电子数据展示工具，下表列出了可以使用的工具，而不是In-Place电子数据展示和In-Place保留。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365 和 Microsoft 365 企业版组织

- Office 365 和 Microsoft 365 教育版组织

- Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline-for-retirement"></a>停用日程表

- 2020 年 7 月 1 日：无法创建新的搜索和保留，但仍可以自行承担运行、编辑和删除现有搜索的风险。 Microsoft 支持将不再在 EAC In-Place电子数据&保留。

- 2020 年 10 月 1 In-Place：EAC 中的&电子数据展示保留功能将处于只读模式。 这意味着你只能删除现有搜索和保留。

### <a name="alternative-tools"></a>备用工具

下表介绍了可用于替换即将停用的现有功能的其他工具。

<table>
<thead>
<tr class="header">
<th>功能</th>
<th>备用工具</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>出于法律目的搜索、导出和保留</td>
<td>Microsoft 365 合规中心中的核心电子数据展示事例 </td>
<td><p>使用核心电子数据展示事例的功能为电子数据展示和保留In-Place功能In-Place奇偶校验。 其中包括：</p>
<ul>
<li>
<p>搜索扩展到数百万个位置</p>
</li>
<li>
<p>搜索、导出和将内容置于保留状态的可靠性更高</p>
</li>
<li>
<p>搜索 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer 组、Microsoft 365 组和 Office 365 应用程序中存储的其他内容的内容</p></li></ul>
</td>
</tr>
<tr class="even">
<td>保留出于保留目的</td>
<td>Microsoft 365 合规中心中的保留策略</td>
<td><p>可以使用保留策略来保留内容，如果需要，可以在保留期到期后将其删除。 其他功能包括：</p>
<ul>
<li>
<p>将策略应用于整个组织 </p>
</li><li>
<p>将策略应用于特定内容位置，如 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams 和 Office 365 组</p></li>
<li>
<p>将策略应用于特定用户</p></li></ul>
<p>有关详细信息，请参阅 <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> 了解保留策略和保留标签</a>。</td>
</tr>
<tr class="odd">
<td>将电子邮件搜索结果复制到发现邮箱进行审阅</td><td>高级电子数据展示 v2.0 中的审阅集</td>
<td><p>查看 Microsoft 365 中的内容从未如此简单。 审阅集具有许多出色的功能，可帮助减少查看所需的时间和数据，包括：</p>
<ul>
<li><p>执行快速搜索查询并筛选审阅集内的内容</p></li>
<li><p>分析审阅集内的内容;这包括电子邮件线程、近重复检测、主题分析和预测编码</p></li>
<li><p>标记审阅集中的文档</p></li>
<li><p>可帮助识别律师客户特权内容的标记建议</p></li></ul>
<p>有关详细信息，请参阅 <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 中的高级电子数据展示解决方案概述</a>。</p>
<p>
<p>或者，可以将搜索结果导出到 PST 文件，然后使用 Microsoft 365 导入服务将 PST 导入发现邮箱。 有关分步说明，请参阅使用<a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">网络上载将 PST 文件导入到 Office 365。</a>
</tr>
<tr class=even>
  <td>将邮件从一个邮箱复制到另一个邮箱</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></td>
  <td>若要向某人授予访问其他用户的电子邮件的权限 (例如当员工离开您的组织，并且你需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。 因此，只需为用户分配访问源邮箱的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</td>
  
  </tr>
<tr class="odd">
<td>从"可恢复的项目"文件夹中还原项目</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>只要邮件的已删除项目保留期尚未 (，就可以在邮箱中还原<i></i>永久删除的项目（也称为) 软删除项目）。 有关详细信息，请参阅 <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online 中的"可恢复的项目"文件夹</a>。</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>有关电子数据展示In-Place保留In-Place常见问题

_ 我在 EAC 中In-Place电子数据展示&保留的复制搜索结果功能，将搜索结果复制到发现邮箱供 *律师审查。现在我有什么选项？**

目前，有两种方法可以复制此功能。 第一个是在高级 [电子数据展示 v2.0 中使用审阅集](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)。 审阅集具有许多在传统审阅工具中相同的功能，如快速搜索文档、标记、电子邮件线程、近重复分组、主题分析和预测编码。 如果仍要使用发现邮箱进行审阅，第二个选项是将搜索结果导出到 PST 文件，然后使用 Microsoft 合规中心中的 PST 导入功能将 [PST](use-network-upload-to-import-pst-files.md) 文件导入发现邮箱。

**如何控制电子数据展示 (可以使用新工具搜索) 邮箱或网站等内容位置？**

Microsoft 365 合规中心还[](set-up-compliance-boundaries.md)使用合规性边界来控制电子数据展示管理器可以搜索的内容位置。 合规性边界在需要位于机构边界内的政府实体或需要遵守地理标志的跨国公司中非常有用。

**如何将当前搜索和保留移动到 Microsoft 365 合规中心？**

通过使用 PowerShell，In-Place EAC 中迁移电子数据展示搜索和保留。 有关说明，请参阅 [将搜索和保留从 EAC 迁移到 Microsoft 365 合规中心](https://go.microsoft.com/fwlink/?linkid=2114224)。

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch cmdlet

根据 Exchange 管理中心 2017 年 7 月 1 日宣布的原始通知，In-Place 电子数据展示 & 保留功能和相应的 **\* -MailboxSearch** cmdlet 将停用。 这些 cmdlet 使用户能够针对法律、法规和公共请求搜索、保留和导出邮箱内容。

由于 Microsoft [<span class="underline">365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 合规中心和 Office 36 & 5 安全与合规中心 PowerShell 中现已提供这些功能，并且性能和可伸缩性已提高，因此您应该使用这些改进的 cmdlet。 这些 cmdlet 包括[<span class="underline">-ComplianceCase、-ComplianceSearch、-CaseHoldPolicy、-CaseHoldRule \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)和[<span class="underline"> \* -ComplianceSearchAction。</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction) [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365 和 Microsoft 365 企业版组织

- Office 365 和 Microsoft 365 教育版组织

- Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline"></a>日程表

- 2020 年 7 月 1 日：你将无法使用 **New-MailboxSearch** 创建新的 In-Place 电子数据展示搜索和 In-Place 保留，但你仍可以使用 cmdlet 运行、编辑和删除现有搜索和保留，但需要自行承担风险。 Microsoft 支持将不再为这些类型的搜索和保留提供帮助。

- 2020 年 10 月 1 日：如前所述，EAC 中的 In-Place 电子数据展示 & 保留功能将处于只读模式。 这也意味着你将无法使用 **New-MailboxSearch、Start-MailboxSearch** 或 **Set-MailboxSearch** cmdlet。 你只能获取和删除现有搜索和保留。

### <a name="alternative-tools"></a>备用工具

下表介绍了可用于替换即将停用的现有功能的其他工具。

<table>
<thead>
<tr class="header">
<th>功能</th>
<th>备用工具</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>搜索和导出</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和导出内容。 您可以使用<strong>New-、Get</strong>和<strong>Start-ComplianceSearch</strong> cmdlet 创建新的搜索并查看搜索估计值。 <strong></strong> 然后，您可以使用 <strong>New-ComplianceSearchAction</strong> cmdlet 导出搜索结果。 你仍必须使用 Microsoft 365 合规中心中的核心电子数据展示工具，将这些搜索结果下载到本地计算机。</p>
<p>
<p><strong>注意：</strong>如果您使用这些 cmdlet 创建与核心电子数据展示案例不关联的搜索，这些搜索将位于 Microsoft 365 合规中心的内容搜索<strong></strong>页面上。</p></td>
</tr>
<tr class="even">
<td>保留邮箱中的内容</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Microsoft 365 合规中心中的保留项必须与 ComplianceCase 相关联。 首先，创建合规性案例，然后创建 CaseHoldPolicy 和 CaseHoldRule。</p>
<p><strong>注意：</strong> 创建 CaseHoldPolicy 而不创建 CaseHoldRule 将使保留不可操作，直到创建 CaseHoldRule 并关联到 CaseHoldPolicy。 有关详细信息，请参阅 cmdlet 文档。</p></td>
</tr>
<tr class="odd">
<td>将搜索结果复制到发现邮箱</td>
<td>无</td>
<td>此功能没有直接替代，因为它无法提供对全部 Microsoft 365 服务的访问权限。 有关替代解决方案，请参阅下面的常见问题解答。</td>
</tr>
  <tr class=even>
  <td>将邮件从一个邮箱复制到另一个邮箱</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></td>
  <td>若要向某人授予访问其他用户的电子邮件的权限 (例如当员工离开您的组织，并且你需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。 因此，只需为用户分配访问源邮箱的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>关于 ***-MailboxSearch** cmdlet 的常见问题解答

**我们使用复制搜索导出电子邮件或即时消息，以用于其他电子数据展示和法律调查。这些 cmdlet 停用后，我们还有其他哪些选项？**

与使用 **\* -MailboxSearch** cmdlet 不同 [<span class="underline">，Microsoft Graph API</span>](https://developer.microsoft.com/en-us/graph)提供了多种用于提取数据的方法，以便用于分析和实现其他目的，这些方法的复原和可扩展性要高很多。

**如何将我的搜索和保留迁移到 Microsoft 365 合规中心？**

通过使用 PowerShell 脚本，In-Place Exchange 管理中心迁移电子数据展示搜索和保留项。 有关详细信息，请参阅将 [旧版电子数据展示搜索和保留迁移到 Microsoft 365 合规中心](migrate-legacy-eDiscovery-searches-and-holds.md)。

**停用 cmdlet 后，我是否仍能够删除或检索搜索？**

可以，尽管我们正在删除创建和修改搜索功能，但您仍可以使用 **Get-MailboxSearch** 和 **Remove-MailboxSearch，** 直到进一步通知为止。 但是，在停用日期后，使用这些 cmdlet 将自行承担风险，Microsoft 支持将不再能够提供帮助。

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

Exchange Online PowerShell 中的 **Search-Mailbox** cmdlet 将于 2018 年停用，正如最初在 cmdlet 输出的警告中宣布的一样。 **Search-Mailbox** cmdlet 最初用于搜索用户的邮箱并清除恶意内容。 我们建议您开始使用 Office 365 安全与合规中心 PowerShell 中的 **New-ComplianceSearch** 和 **New-ComplianceSearchAction** cmdlet &搜索和清除内容。 对于内置的安全体验 [<span class="underline">，Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/security/) 安全功能为电子邮件和许多其他 Microsoft 服务提供了强大的威胁防护。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365 和 Microsoft 365 企业版组织

- Office 365 和 Microsoft 365 教育版组织

- Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline"></a>日程表

-  2020 年 7 月 1 日： **搜索邮箱** cmdlet 将不再可用，Microsoft 支持将不再提供帮助。

### <a name="alternative-tools"></a>备用工具

下表介绍了可用于替换即将停用的现有功能的其他工具。

<table>
<thead>
<tr class="header">
<th>功能</th>
<th>备用工具</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>搜索邮箱</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和导出内容。 您可以使用<strong>New-、Get</strong>和<strong>Start-ComplianceSearch</strong> cmdlet 创建新的搜索并查看搜索估计值。 <strong></strong> 然后，可以使用 <strong>New-ComplianceSearchAction -Export</strong> 命令导出搜索结果。 你仍必须使用 Microsoft 365 合规中心中的核心电子数据展示工具，将这些搜索结果下载到本地计算机。</p></p>
</td>
</tr>
<tr class="even">
<td>从邮箱中删除批量电子邮件</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">设置邮箱的存档和删除策略</span></a></p>
<p></p></td>
<td><p>管理员可以创建存档和删除策略，该策略会自动将项目移动到用户的存档邮箱，并自动从邮箱中删除项目。</p>
</td>
</tr>
<tr class="even">
<td>将搜索结果复制到发现邮箱</td>
<td> </td>
<td>此功能没有直接替代，因为它无法提供对全部 Microsoft 365 服务的访问权限。 有关替代解决方案，请参阅 <strong>*-MailboxSearch cmdlets</strong> 部分中的常见问题解答。 </td>
</tr>
<tr class=odd>
  <td>将邮件从一个邮箱复制到另一个邮箱</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></td>
  <td>若要向某人授予访问其他用户的电子邮件的权限 (例如当员工离开您的组织，并且你需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。 因此，只需为用户分配访问源邮箱的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</td>
</tr>
<tr class=even>
  <td>清除邮箱中的邮件</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和清除内容。 可以使用 <strong>New-ComplianceSearch</strong> 和 <strong>New-ComplianceSearch</strong> cmdlet 创建和运行搜索，然后可以使用 <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> 命令清除内容。 有关详细信息，请参阅"<a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">搜索和删除邮件"。</span></a></p>
</td>
</tr>
<tr class="odd"> 
<td>清除邮箱中的邮件</td>
<td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></td>
<td>若要清除邮箱中的邮件，请分配管理员权限以访问员工的邮箱。 可以根据需要删除和回收邮件，以利用 Outlook 中的内置搜索和查看功能。</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Web 服务 API 操作

Exchange Web 服务 API 中的这些操作由 Exchange 管理中心的 In-Place 电子数据展示 & 保留功能以及 Exchange Online PowerShell 中的相应 **\* -MailboxSearch** cmdlet 使用。 作为停用其他旧版电子数据展示工具的一部分，这些工具也将停用。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365 和 Microsoft 365 企业版组织

- Office 365 和 Microsoft 365 教育版组织

- Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline"></a>日程表

- 2020 年 7 月 1 日：GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 操作将不再可用，并且 Microsoft 支持将不再提供帮助。

## <a name="advanced-ediscovery-v10"></a>高级电子数据展示 v1.0

高级电子数据展示 v1.0（通过单击"切换到高级电子数据展示"可在核心电子数据展示案例中使用的高级电子数据展示版本）即将停用。 它的功能已被 Microsoft 365 合规中心中新的高级电子数据展示解决方案所取代。 [](https://aka.ms/edisco)

若要确定组织是否使用高级电子数据展示 v1.0：

1. 转到 [Office 365 安全&合规中心](https://protection.office.com)。

2. 在安全与合规中心的&窗格中，单击电子数据展示> **电子** 数据展示，然后打开核心电子数据展示案例。

3. 如果看到" **切换到高级电子数据** 展示"按钮，则单击此按钮将进入 1.0 版高级电子数据展示（即将停用）。 在核心电子数据展示中创建和管理事例的能力不会受到影响。 仅通过单击"切换到高级电子数据展示" (在高级电子数据展示 v1.0) 中添加和分析案例数据的能力将停用。

Microsoft 365 (中新的高级电子数据展示解决方案也称为高级电子数据展示 *v2.0*) 提供了原始解决方案的所有功能，但现在包括一种基于保管人的方法，用于识别其他 Microsoft 365 服务中的内容、收集该内容，然后将它添加到审阅集，审阅者可以利用快速搜索查询、标记和分析功能来帮助剔除相关文档。 高级电子数据展示现在包括针对 Microsoft 和非 Microsoft 文件类型的改进处理和本机查看器，文件类型的完整列表在此处，支持的元数据[字段在此处](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)。 [](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) 此外，新的高级电子数据展示解决方案提供了功能强大的保管人保留管理功能，使你可以将保留应用于不同服务中的内容，通知用户保留，并跟踪保管人响应，所有这些都位于高级电子数据展示案例中。

若要访问高级电子数据展示 v2.0：

1. 转到 [Microsoft 365 合规中心](https://compliance.microsoft.com)。

2. 在 Microsoft 365 合规中心的左侧导航窗格中，单击"全部显示"，然后单击"电子数据展示>**高级"**。

此时，我们建议您开始将电子数据展示工作流转换为新的高级电子数据展示功能。 如果需要，可以通过导出内容并脱机存储内容来存档高级电子数据展示 1.0 事例。 尽管在 2020 年 12 月 31 日之前，你仍然能够访问高级电子数据展示 v1.0，但 Microsoft 支持在 2020 年 10 月 1 日之后不会提供支持。 有关详细信息，请参阅以下日程表。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365 和 Microsoft 365 企业版组织

- Office 365 和 Microsoft 365 教育版组织

- Office 365 和 Microsoft 365 政府组织;这包括 GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline"></a>日程表

- 2020 年 7 月 1 日：无法创建新的高级电子数据展示 v1.0 事例。

- 2020 年 10 月 1 日：无法添加新数据 (为高级电子数据展示) 搜索结果。 你将能够继续处理现有情况下的数据，风险由你自己承担。 Microsoft 支持将不再提供帮助。 

- 2020 年 12 月 31 日：无法访问高级电子数据展示 v1.0 事例。

### <a name="alternative-tools"></a>备用工具

Microsoft [](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) 365 合规中心中的高级电子数据展示解决方案。
