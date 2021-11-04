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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Place电子数据展示和 In-Place 保留 (和 Exchange Online 中的相应 PowerShell cmdlet) 将于 2020 年上半年停用。 同时Search-Mailbox v1.0 Advanced eDiscovery cmdlet 和 Advanced eDiscovery cmdlet 和 cmdlet。
ms.openlocfilehash: 2d5e058f5fab62249f578d7f138731233bde1091
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756475"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>旧版电子数据展示工具的停用

> [!IMPORTANT]
> 本文中介绍的旧电子数据展示工具的功能已从 Microsoft 365 服务中删除，或者仍可用，但不再受支持。 任何仍然可用的功能都可能会删除，无需另行通知。 如果仍在使用这些旧工具中的任一种，请考虑迁移到 Microsoft 365 合规中心 中的电子数据展示工具或本文中所述的替代方法之一。

多年来，Microsoft 提供了电子数据展示工具，让你可以搜索、预览和导出电子邮件Exchange Online。 但是，这些工具不再提供在其他 Microsoft 365 服务（如 SharePoint Online 和 Microsoft 365 组）中搜索非 Exchange 内容的有效方式。 为解决这一问题，Microsoft 提供了其他电子数据展示工具，可帮助你搜索各种Microsoft 365内容。 我们一直在努力将最新且强大的电子数据展示功能纳入<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心。</a> 这使组织能够响应跨多个服务（包括 Exchange Online）对内容的法律、内部和其他Microsoft 365请求。

由于 Microsoft 365 合规中心 中新增和改进了电子数据展示功能，我们将停用以下与搜索 Exchange Online 和 Microsoft 365 中的电子邮件内容相关的电子数据展示相关特性和功能：

- [就地电子数据展示](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)和就[地](/exchange/security-and-compliance/create-or-remove-in-place-holds)保留Exchange管理中心。

- 支持 In-Place 电子数据展示和 In-Place 保留的 Exchange Online PowerShell cmdlet (统称为 **-MailboxSearch* cmdlet) 。 这包括以下 cmdlet：

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch)和[Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) cmdlet 将在其他 ****-MailboxSearch*** cmdlet 停用后可用，以便您可以使用它们来帮助转换到其他电子数据展示和保留工具。 但是，在下面引用 (日期后) Microsoft 支持将不再支持这两个 cmdlet。

- PowerShell 中的[Search-Mailbox](/powershell/module/exchange/search-mailbox) cmdlet Exchange Online。

- Exchange Web 服务 API 中的以下操作：

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 高级电子数据展示 v1.0，](./overview-ediscovery-20.md)它是通过 Advanced eDiscovery 中的核心电子数据展示案例访问的第一个版本的 Microsoft 365 合规中心。 停用 Advanced eDiscovery v1.0 不会影响创建和管理核心电子数据展示事例的能力。

> [!NOTE]
> 要停用的电子数据展示功能仅适用于基于云的 Microsoft 365 和 Office 365。 本地版本的 Exchange 和 SharePoint 中的电子数据展示功能仍将受支持，直到进一步通知为止。

本文中的以下各节提供有关要停用的每个功能的指导。 此信息包括日程表和可使用的替代工具，而不是停用的工具。

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place管理中心In-Place电子数据展示Exchange保留 

根据 2017 年 7 月 1 日的原始通知，Exchange 管理中心 (EAC) 中的 In-Place 电子数据展示 & 保留功能即将停用。 EAC In-Place电子数据展示&保留"页面允许搜索、保留和导出来自 Exchange Online。 In-Place电子数据展示还让您将搜索结果复制到发现邮箱，以便您或其他电子数据展示管理员能够查看内容，使其可用于法律、法规和公共请求。

由于所有这些功能 (除了将搜索结果复制到发现邮箱) 之外，现在 Microsoft 365 合规中心 (中的内容搜索、电子数据展示和[Advanced eDiscovery](./microsoft-365-compliance-center.md)工具中都提供了改进的功能、可靠性和对各种 Microsoft 365 服务) 的支持，因此建议不要请尽快开始使用这些工具。 为了帮助你转换到这些其他电子数据展示工具，下表列出了可以使用的工具，而不是In-Place电子数据展示In-Place保留。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365和Microsoft 365 企业版组织

- Office 365 和 Microsoft 365 教育版 组织

- Office 365 Microsoft 365政府组织;这包括GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline-for-retirement"></a>停用时间线

- 2020 年 7 月 1 日：无法创建新的搜索和保留，但仍可以自行运行、编辑和删除现有搜索。 Microsoft 支持将不再In-Place EAC &电子数据展示保留。

- 2020 年 10 月 1 日：In-Place EAC 中的 & 电子数据展示保留功能将置于只读模式。 这意味着你只能删除现有搜索和保留。

### <a name="alternative-tools"></a>替代工具

下表介绍了可用于替换即将停用的现有功能的其他工具。

<table>
<thead>
<tr class="header">
<th>功能</th>
<th>替代工具</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>出于法律目的搜索、导出和保留</td>
<td>服务中的核心电子数据展示Microsoft 365 合规中心 </td>
<td><p>使用核心电子数据展示事例的功能为电子数据展示和保留In-Place奇偶校验In-Place奇偶校验。 其中包括：</p>
<ul>
<li>
<p>搜索扩展到数百万个位置</p>
</li>
<li>
<p>搜索、导出和将内容置于保留状态的可靠性更高</p>
</li>
<li>
<p>搜索 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer 组Microsoft 365应用程序应用程序存储的组Office 365内容</p></li></ul>
</td>
</tr>
<tr class="even">
<td>保留出于保留目的</td>
<td>策略中的保留Microsoft 365 合规中心</td>
<td><p>可以使用保留策略来保留内容，如果需要，可以在保留期到期后将其删除。 其他功能包括：</p>
<ul>
<li>
<p>将策略应用于整个组织 </p>
</li><li>
<p>将策略应用于特定内容位置，如 Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams 和 Office 365 组</p></li>
<li>
<p>将策略应用于特定用户</p></li></ul>
<p>有关详细信息，请参阅 <a href="/microsoft-365/compliance/retention-policies"> 了解保留策略和保留标签</a>。</td>
</tr>
<tr class="odd">
<td>将电子邮件搜索结果复制到发现邮箱进行审阅</td><td>v2.0 Advanced eDiscovery审阅集</td>
<td><p>查看网站Microsoft 365从未如此简单过。 审阅集有很多出色的功能，可帮助减少查看所需的时间和数据，包括：</p>
<ul>
<li><p>执行快速搜索查询并筛选审阅集内的内容</p></li>
<li><p>分析审阅集内的内容;这包括电子邮件线程、近重复检测、主题分析和预测编码</p></li>
<li><p>标记审阅集中的文档</p></li>
<li><p>用于帮助识别律师客户特权内容的标记建议</p></li></ul>
<p>有关详细信息，请参阅 <a href="/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 中的高级电子数据展示解决方案概述</a>。</p>
<p>
<p>或者，可以将搜索结果导出到 PST 文件，然后Microsoft 365导入服务将 PST 导入发现邮箱。 有关分步说明，请参阅使用网络上传将<a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">PST 文件导入Office 365。</a>
</tr>
<tr class=even>
  <td>将邮件从一个邮箱复制到另一个邮箱</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></td>
  <td>若要向某人授予对其他用户的电子邮件 (例如当员工离开您的组织，并且您需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。 因此，只需为用户分配访问源邮箱所需的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</td>
  
  </tr>
<tr class="odd">
<td>从"可恢复的项目"文件夹中还原项目</td>
  <td><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>只要项目的已删除项目保留期尚未 (，就可以还原永久删除的项目) <i></i>也称为邮箱中的软删除项目。 有关详细信息，请参阅"可<a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">恢复的项目"文件夹Exchange Online。</a></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>有关电子数据展示In-Place保留的常见问题In-Place常见问题

**我在 EAC 中In-Place电子数据展示&保留的复制搜索结果功能，将搜索结果复制到发现邮箱中供律师审查。我现具有哪些选项？**

目前，有两种方法可以复制此功能。 第一种是在[v2.0 Advanced eDiscovery审阅集](./view-documents-in-review-set.md)。 在传统审阅工具（如快速搜索文档、标记、电子邮件线程、近乎重复的分组、主题分析和预测编码）中，审阅集有许多相同的功能。 如果仍要使用发现邮箱进行审阅，则第二个选项是，将搜索结果导出到 PST 文件，然后使用 Microsoft 合规中心中的 PST 导入功能将 [PST](use-network-upload-to-import-pst-files.md) 文件导入发现邮箱。

**如何控制电子数据展示 (搜索哪些内容位置，) 电子数据展示管理员可以使用新工具搜索哪些内容位置？**

该[Microsoft 365 合规中心还使用](set-up-compliance-boundaries.md)合规性边界来控制电子数据展示管理员可搜索的内容位置。 合规性边界在政府实体中非常有用，这些实体需要位于机构边界内，或者需要遵守地理边界的跨国公司。

**如何移动当前搜索和保留到Microsoft 365 合规中心？**

通过使用 PowerShell，In-Place EAC 中迁移电子数据展示搜索和保留。 有关说明，请参阅[将搜索和保留从 EAC 迁移到Microsoft 365 合规中心。](./migrate-legacy-ediscovery-searches-and-holds.md)

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch cmdlet

根据 2017 年 7 月 1 日 Exchange 管理中心中宣布的原始通知，In-Place 电子数据展示 & 保留功能以及相应的 **\* -MailboxSearch** cmdlet 将停用。 这些 cmdlet 使用户能够针对法律、法规和公共请求搜索、保留和导出邮箱内容。

由于这些功能现已在 Microsoft 365 合规中心 和[<span class="underline">Office 365</span>](./microsoft-365-compliance-center.md)安全与&合规中心 PowerShell 中提供，并且具有改进的性能和可伸缩性，因此您应该使用这些改进的 cmdlet。 这些 cmdlet 包括[<span class="underline">-ComplianceCase、-ComplianceSearch、-CaseHoldPolicy、-CaseHoldRule \* </span>](/powershell/module/exchange/get-compliancecase)和[<span class="underline"> \* -ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction)。 [<span class="underline"> \* </span>](/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdrule)

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365和Microsoft 365 企业版组织

- Office 365 和 Microsoft 365 教育版 组织

- Office 365 Microsoft 365政府组织;这包括GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline"></a>日程表

- 2020 年 7 月 1 日：你将无法使用 **New-MailboxSearch** 创建新的 In-Place 电子数据展示搜索和 In-Place 保留，但仍可以使用 cmdlet 运行、编辑和删除现有搜索和保留，但由你自己承担风险。 Microsoft 支持将不再为这些类型的搜索和保留提供帮助。

- 2020 年 10 月 1 日：如前所述，EAC 中的 In-Place 电子数据展示 & 保留功能将置于只读模式。 这也意味着你将无法使用 **New-MailboxSearch、Start-MailboxSearch** 或 **Set-MailboxSearch** cmdlet。 你只能获取和删除现有搜索和保留。

### <a name="alternative-tools"></a>替代工具

下表介绍了可用于替换即将停用的现有功能的其他工具。

<table>
<thead>
<tr class="header">
<th>功能</th>
<th>替代工具</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>搜索和导出</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和导出内容。 可以使用<strong>New-、Get-</strong>和<strong>Start-ComplianceSearch</strong> <strong></strong>cmdlet 创建新的搜索并查看搜索估计值。 然后，您可以使用 <strong>New-ComplianceSearchAction</strong> cmdlet 导出搜索结果。 你仍必须使用此服务中的核心电子数据展示Microsoft 365 合规中心将搜索结果下载到本地计算机。</p>
<p>
<p><strong>注意：</strong>如果您使用这些 cmdlet 创建与核心电子数据展示案例不关联的搜索，这些搜索将位于"内容"搜索页面上的Microsoft 365 合规中心。 <strong></strong></p></td>
</tr>
<tr class="even">
<td>保留邮箱中的内容</td>
<td><p><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Microsoft 365 合规中心中的保留项必须与 ComplianceCase 相关联。 首先，创建合规性案例，然后创建 CaseHoldPolicy 和 CaseHoldRule。</p>
<p><strong>注意：</strong> 创建 CaseHoldPolicy 而不创建 CaseHoldRule 将使保留不可操作，直到创建 CaseHoldRule 并关联到 CaseHoldPolicy。 有关详细信息，请参阅 cmdlet 文档。</p></td>
</tr>
<tr class="odd">
<td>将搜索结果复制到发现邮箱</td>
<td>None</td>
<td>此功能没有直接替代，因为它无法提供对所有 Microsoft 365服务的访问权限。 有关替代解决方案，请参阅下面的常见问题解答。</td>
</tr>
  <tr class=even>
  <td>将邮件从一个邮箱复制到另一个邮箱</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></td>
  <td>若要向某人授予访问其他用户的电子邮件的权限 (例如当员工离开您的组织，并且您需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。 因此，只需为用户分配访问源邮箱的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>关于 ***-MailboxSearch** cmdlet 的常见问题解答

**我们使用复制搜索导出电子邮件或即时消息，以便进行其他电子数据展示和法律调查。这些 cmdlet 停用后，我们还有其他哪些选项？**

[<span class="underline">Microsoft Graph API</span>](https://developer.microsoft.com/en-us/graph)提供了多种用于提取数据的方法，以便用于分析和其他目的，这些方法比使用 **\* -MailboxSearch** cmdlet 更具弹性和可扩展性。

**如何迁移我的搜索和保留到Microsoft 365 合规中心？**

通过使用 PowerShell 脚本，In-Place电子数据展示搜索和保留Exchange从管理中心迁移。 有关详细信息，请参阅将[旧版电子数据展示搜索和保留迁移到Microsoft 365 合规中心。](migrate-legacy-eDiscovery-searches-and-holds.md)

**停用 cmdlet 后，我是否仍能够删除或检索搜索？**

可以，尽管我们正在删除创建和修改搜索功能，但您仍可以使用 **Get-MailboxSearch** 和 **Remove-MailboxSearch，** 直到进一步通知。 但是，停用日期后使用这些 cmdlet 将自行承担风险，并且 Microsoft 支持将不再能够提供帮助。

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

PowerShell 中的 **Search-Mailbox** cmdlet Exchange Online从 2018 年开始在 cmdlet 输出的警告中最初宣布停用。 **Search-Mailbox** cmdlet 最初用于搜索用户的邮箱并清除恶意内容。 我们建议您开始使用 Office 365 & 安全与合规中心 PowerShell 中的 **New-ComplianceSearch** 和 **New-ComplianceSearchAction** cmdlet 来搜索和清除内容。 对于内置安全体验，Microsoft 365[<span class="underline">安全功能</span>](../security/index.yml)为电子邮件和许多其他安全环境提供强大的威胁Microsoft 服务。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365和Microsoft 365 企业版组织

- Office 365 和 Microsoft 365 教育版 组织

- Office 365 Microsoft 365政府组织;这包括GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline"></a>日程表

-  2020 年 7 月 1 日 **：Search-Mailbox** cmdlet 将不再可用，Microsoft 支持将不再提供帮助。

### <a name="alternative-tools"></a>替代工具

下表介绍了可用于替换即将停用的现有功能的其他工具。

<table>
<thead>
<tr class="header">
<th>功能</th>
<th>替代工具</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>搜索邮箱</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和导出内容。 可以使用<strong>New-、Get-</strong>和<strong>Start-ComplianceSearch</strong> <strong></strong>cmdlet 创建新的搜索并查看搜索估计值。 然后，可以使用 <strong>New-ComplianceSearchAction -Export</strong> 命令导出搜索结果。 你仍必须使用此服务中的核心电子数据展示Microsoft 365 合规中心将搜索结果下载到本地计算机。</p></p>
</td>
</tr>
<tr class="even">
<td>从邮箱中删除批量电子邮件</td>
<td><p><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">设置邮箱的存档和删除策略</span></a></p>
<p></p></td>
<td><p>管理员可以创建存档和删除策略，该策略会自动将项目移动到用户的存档邮箱，并自动从邮箱中删除项目。</p>
</td>
</tr>
<tr class="even">
<td>将搜索结果复制到发现邮箱</td>
<td> </td>
<td>此功能没有直接替代，因为它无法提供对所有 Microsoft 365服务的访问权限。 有关替代解决方案，请参阅 <strong>*-MailboxSearch cmdlets</strong> 部分中的常见问题解答。 </td>
</tr>
<tr class=odd>
  <td>将邮件从一个邮箱复制到另一个邮箱</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></td>
  <td>若要向某人授予访问其他用户的电子邮件的权限 (例如当员工离开您的组织，并且您需要向其他人授予对前员工的电子邮件) 的访问权限时，我们建议您为此人分配访问前员工邮箱的权限。 因此，只需为用户分配访问源邮箱的权限，而不是将邮箱项目复制到其他用户邮箱或共享邮箱。</td>
</tr>
<tr class=even>
  <td>清除邮箱中的邮件</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>ComplianceSearch 和 ComplianceSearchAction cmdlet 协同工作，以帮助您搜索和清除内容。 可以使用 <strong>New-ComplianceSearch</strong> 和 <strong>New-ComplianceSearch</strong> cmdlet 创建并运行搜索，然后可以使用 <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> 命令清除内容。 有关详细信息，请参阅搜索 <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">和删除邮件</span></a>。</p>
</td>
</tr>
<tr class="odd"> 
<td>清除邮箱中的邮件</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">向邮箱分配权限</a></td>
<td>若要清除邮箱中的邮件，请分配管理员权限以访问员工的邮箱。 可根据需要删除和回收邮件，以利用邮件中内置的搜索和查看Outlook。</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>ExchangeWeb 服务 API 操作

Exchange Web 服务 API 中的这些操作由 Exchange 管理中心中的 In-Place 电子数据展示 & 保留功能以及 Exchange Online PowerShell 中的相应 **\* -MailboxSearch** cmdlet 使用。 作为停用其他旧版电子数据展示工具的一部分，这些工具也将停用。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365和Microsoft 365 企业版组织

- Office 365 和 Microsoft 365 教育版 组织

- Office 365 Microsoft 365政府组织;这包括GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline"></a>日程表

- 2020 年 7 月 1 日：GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes 和 GetHoldOnMailboxes 操作将不再可用，并且 Microsoft 支持将不再提供帮助。

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0 版本（即核心电子数据展示Advanced eDiscovery切换到 Advanced eDiscovery）中可用的版本）即将停用。  其功能已由 Advanced eDiscovery[中的新](./ediscovery.md)解决方案Microsoft 365 合规中心。

若要确定您的组织是否正在使用 Advanced eDiscovery v1.0：

1. 转到"Microsoft 365 合规中心"，选择 **"电子数据** 展示  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2174007" target="_blank">**核心**</a>"，然后打开核心电子数据展示案例。

1. 如果看到"切换到Advanced eDiscovery"按钮，则单击此按钮将进入即将停用的 1.0 Advanced eDiscovery版本。 在核心电子数据展示中创建和管理事例的能力不会受到影响。 只有在 v1.0 Advanced eDiscovery中通过单击"切换到" (来添加和分析Advanced eDiscovery) 停用。 

Microsoft 365 (中新的 Advanced eDiscovery 解决方案（也称为 *Advanced eDiscovery v2.0*) ）提供原始解决方案的所有功能，但现在包括一种基于保管人的方法，用于识别其他 Microsoft 365 服务中的内容，收集该内容。然后将它添加到审阅集，审阅者可以利用快速搜索查询、标记和分析功能来帮助剔除相关文档。 Advanced eDiscovery Microsoft 和非 Microsoft 文件类型的改进处理和本机查看器，文件类型的完整列表在此处，支持的元数据[字段在此处](./document-metadata-fields-in-advanced-ediscovery.md)。 [](./supported-filetypes-ediscovery20.md) 此外，新的 Advanced eDiscovery 解决方案提供了一个强大的保管人保留管理功能，使您可以将保留应用于不同服务中的内容、将保留通知用户以及跟踪保管人响应，所有这些都在 Advanced eDiscovery 案例中。

若要访问高级电子数据展示 v2.0：

转到"Microsoft 365 合规中心"，选择 **"电子数据** 展示高级"，然后  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2174006" target="_blank"></a>打开核心电子数据展示案例。

目前，我们建议您开始将电子数据展示工作流转换为新的Advanced eDiscovery功能。 如有必要，您可以通过导出内容Advanced eDiscovery存储内容来存档 1.0 案例。 尽管你仍然能够在 2020 年 12 月 31 Advanced eDiscovery访问 Advanced eDiscovery v1.0，但 Microsoft 支持在 2020 年 10 月 1 日之后不会提供支持。 有关详细信息，请参阅以下日程表。

### <a name="scope-of-affected-organizations"></a>受影响组织的范围

- Office 365和Microsoft 365 企业版组织

- Office 365 和 Microsoft 365 教育版 组织

- Office 365 Microsoft 365政府组织;这包括GCC、GCC High 和 DoD

- Office 365 德国

### <a name="timeline"></a>日程表

- 2020 年 7 月 1 日：无法创建新的 Advanced eDiscovery v1.0 案例。

- 2020 年 10 月 1 日：无法将新数据 (准备搜索结果以用于Advanced eDiscovery) 的情况。 你将能够继续处理现有情况下的数据，但由你自己承担风险。 Microsoft 支持将不再提供帮助。 

- 2020 年 12 月 31 日：你将无法访问 Advanced eDiscovery v1.0 的情况。

### <a name="alternative-tools"></a>替代工具

Advanced eDiscovery[中的](./overview-ediscovery-20.md)Microsoft 365 合规中心。