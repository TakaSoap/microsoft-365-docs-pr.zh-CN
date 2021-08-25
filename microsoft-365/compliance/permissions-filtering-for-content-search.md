---
title: 配置内容搜索的权限筛选
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: 使用内容搜索权限筛选，让电子数据展示管理员仅搜索组织中邮箱和网站的子集。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 82e5ce9be5e2f26c1863b0951d3476a6aa31458d
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2021
ms.locfileid: "58508126"
---
# <a name="configure-permissions-filtering-for-content-search"></a>配置内容搜索的权限筛选

您可以使用搜索权限筛选让电子数据展示管理员仅搜索组织中邮箱和网站的子集。 您还可以使用权限筛选功能让该电子数据展示管理员仅搜索满足特定搜索条件的邮箱或站点内容。 例如，您可能会让电子数据展示管理员仅搜索特定位置或部门的用户的邮箱。 为此，可创建一个筛选器，该筛选器使用受支持的收件人筛选器来限制特定用户或用户组可以搜索的邮箱。 您还可以创建一个筛选器，以指定用户可以搜索的邮箱内容。 这是通过创建使用可搜索邮件属性的筛选器来完成的。 同样，您可以让电子数据展示管理员仅搜索SharePoint特定网站。 通过创建限制可以搜索哪些站点的筛选器执行此操作。 您还可以创建指定可以搜索哪些站点内容的筛选器。 这是通过创建使用可搜索站点属性的筛选器来完成的。

您还可以使用搜索权限筛选在控制用户内容位置（如邮箱、SharePoint 网站和 *OneDrive* 帐户) 可搜索的组织中创建称为合规性边界) 的逻辑边界 (。 ( 有关详细信息，请参阅在 Office 365 中设置电子[数据展示调查的合规性Office 365。](tagging-and-assessment-in-advanced-ediscovery.md)
  
搜索权限筛选受网站内容搜索功能Microsoft 365 合规中心。 这四个 cmdlet 让你可以配置和管理搜索权限筛选器：
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>配置权限筛选的要求

- 若要运行合规性安全筛选器 cmdlet，您必须是组织中组织管理角色组Microsoft 365 合规中心。 有关详细信息，请参阅[安全与合规中心中的权限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。

- 您必须同时连接到安全Exchange Online安全&中心 PowerShell，以使用合规性安全筛选器 cmdlet。 这是必需的，因为这些 cmdlet 需要访问邮箱属性，这就是您必须连接到 PowerShell Exchange Online的原因。 请参阅下一节中的步骤。

- 请参阅[More information](#more-information)部分，了解有关搜索权限筛选器的其他信息。

- 搜索权限筛选适用于非活动邮箱，这意味着您可以使用邮箱和邮箱内容筛选来限制可以搜索非活动邮箱的用户。 有关 [权限筛选](#more-information) 和非活动邮箱的其他信息，请参阅详细信息部分。

- 搜索权限筛选不能用于限制哪些人可以搜索 Exchange。

- 对可以在组织中创建的搜索权限筛选器的数量没有限制。 但是，当搜索权限筛选器超过 100 个时，搜索性能将会受到影响。 若要尽可能减少组织中搜索权限筛选器的数量，请创建尽可能将 Exchange、SharePoint 和 OneDrive 规则组合在一个筛选器中的筛选器。

## <a name="connect-to-exchange-online-and-security--compliance-center-powershell-in-a-single-session"></a>连接单个会话中Exchange Online安全&安全与合规中心 PowerShell

在成功运行本节中的脚本之前，必须下载并安装 powerShell V2 Exchange Online脚本。 有关信息，请参阅[关于 Exchange Online PowerShell V2 模块](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。

1. 将以下文本保存到Windows PowerShell脚本文件中，使用文件名后缀 **.ps1。** 例如，你可以将其保存到名为ConnectEXO-SCC.ps1 **的文件**。

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. 在本地计算机上，打开Windows PowerShell，转到上一步中创建的脚本所在的文件夹，然后运行脚本;例如：

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

您如何知道这是否有效？ 运行脚本后，来自安全Exchange Online安全& PowerShell 的 cmdlet 将导入到本地 Windows PowerShell 会话。 如果未收到任何错误，说明连接成功。 快速测试是运行安全Exchange Online安全&中心 PowerShell cmdlet。 例如，可以运行 **Get-Mailbox** 和 **Get-ComplianceSearch**。

有关 PowerShell 连接错误的疑难解答，请参阅：

- [连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

**New-ComplianceSecurityFilter** 用于创建搜索权限筛选器。 下表介绍了此 cmdlet 的参数。 创建遵从性安全筛选器需要全部参数。
  
| 参数 | 说明 |
|:-----|:-----|
| _操作_ <br/> | _Action_ 参数指定应用筛选器的搜索操作类型。 可能的内容搜索操作包括：  <br/><br/> **导出：** 导出搜索结果时应用筛选器。  <br/> **预览：** 预览搜索结果时应用筛选器。  <br/> **清除：** 清除搜索结果时应用筛选器。  <br/> **搜索：** 运行搜索时应用筛选器。  <br/> **全部：** 筛选器将应用于所有搜索操作。  <br/> |
| _FilterName_ <br/> |_FilterName_ 参数指定权限筛选器的名称。 在使用 **Get-ComplianceSecurityFilter**、**Set-ComplianceSecurityFilter** 和 **Remove-ComplianceSecurityFilter** cmdlet 时，此名称可用于标识筛选器。  <br/> |
| _筛选器_ <br/> | _Filters_ 参数指定合规性安全筛选器的搜索条件。 您可以创建三种不同类型的筛选器：  <br/><br/> **邮箱或OneDrive筛选：** 此类型的筛选器指定邮箱OneDrive分配的用户 (_Users_ 参数) 搜索的帐户。 此类型的筛选器的语法为 _mailboxPropertyName_ **Mailbox_，** 其中 _MailboxPropertyName_ 指定用于将邮箱和 OneDrive 帐户的范围的邮箱属性。 例如，邮箱筛选器将允许分配了此筛选器的用户仅搜索 `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` CustomAttribute10 属性中值为"OttawaUsers"的邮箱和 OneDrive 帐户。  <br/>  任何受支持的可筛选收件人属性都可用于  _MailboxPropertyName_ 属性。 有关受支持的属性的列表，请参阅 [-RecipientFilter 参数的可筛选属性](/powershell/exchange/recipientfilter-properties)。  <br/><br/> **邮箱内容筛选：** 此类型的筛选器应用于可搜索的内容。 它指定分配的用户可以搜索的邮箱内容。 此类型的筛选器的语法为 MailboxContent_ _SearchablePropertyName： value_，**其中** _SearchablePropertyName_ 指定可以在内容搜索中指定的关键字查询语言 (KQL) 属性。 例如，邮箱内容筛选器将允许分配了此筛选器的用户仅搜索发送到域中收件人 contoso.com  `MailboxContent_recipients:contoso.com` 的邮件。  <br/>  有关可搜索邮件属性的列表，请参阅内容搜索的关键字查询 [和搜索条件](keyword-queries-and-search-conditions.md)。 <br/> <br/> **重要提示：**  单个搜索筛选器不能包含邮箱筛选器和邮箱内容筛选器。 若要在单个筛选器中组合这些筛选器，您必须使用筛选器 [列表](#using-a-filters-list-to-combine-filter-types)。  但筛选器可以包含同一类型的更复杂的查询。 例如，  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **网站和网站内容筛选：** 有两SharePoint和OneDrive for Business网站相关的筛选器，您可以使用它们来指定分配的用户可以搜索的网站或网站内容：  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  这两个筛选器可互换。 例如，  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` 和  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` 返回相同的结果。 但是，为了帮助您确定筛选器用途，您可以使用 指定与网站相关的属性 (如网站 URL) 以及指定与内容相关的属性 ( `Site_`  `SiteContent_` 如文档类型。 例如，筛选器将允许分配了此筛选器的用户  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` 仅搜索网站集中 https://contoso.sharepoint.com/sites/doctors 的内容。 该筛选器将允许分配了此筛选器的用户仅搜索  `"SiteContent_FileExtension -eq 'docx'"` Word 2007 (及更高版本中的 Word) 。  <br/><br/>  有关可搜索网站属性的列表，请参阅 Overview [of crawled and managed properties in SharePoint](/SharePoint/technical-reference/crawled-and-managed-properties-overview)。 "**可查询"** 列中标有"是"的属性可用于创建站点或网站内容筛选器。  <br/><br/> **重要提示：** <br/><br/> - 使用受支持的属性之一设置网站筛选器并不意味着筛选器中的网站属性将传播到该网站上的所有文件。 这意味着用户仍负责填充与该网站上文件关联的特定属性字段，以便网站筛选器能够运行并捕获正确的内容。 例如，如果用户应用了安全筛选器"Site_RefineableString00 -eq 'abc'"，然后用户使用关键字查询"xyz"运行搜索。 安全筛选器将追加到查询中，实际运行的查询为"xyz **AND RefineableString0：'abc'"。** 用户需要确保网站上的文件在 RefineableString00 字段中确实具有 abc 值。 如果没有，此搜索查询将不会返回任何结果。 <br/><br/>- 您必须创建搜索权限筛选器以明确阻止用户搜索特定服务 (例如阻止用户搜索任何 Exchange 邮箱或任何 SharePoint 网站) 。 换句话说，创建允许用户搜索组织中所有SharePoint的搜索权限筛选器不会阻止该用户搜索邮箱。 例如，若要SharePoint管理员仅搜索SharePoint，必须创建一个筛选器来阻止他们搜索邮箱。 同样，Exchange管理员只能搜索邮箱，必须创建阻止他们搜索网站的筛选器。           |
| _用户_ <br/> |_Users_ 参数指定将此筛选器应用于其内容搜索的用户。 按其别名或主要 SMTP 地址标识用户。 您可以指定用逗号分隔的多个值，也可以通过使用值 **All** 将筛选器分配给所有用户。  <br/> 您还可以使用 _Users_ 参数指定Microsoft 365 合规中心角色组。 这可让您创建一个自定义角色组，然后为该角色组分配搜索权限筛选器。 例如，假设您具有一家跨国公司美国子公司的电子数据展示管理员自定义角色组。 通过使用角色组) 的 Name 属性，可以使用  _Users_ 参数指定此角色组 (，然后使用  _Filter_ 参数仅允许搜索美国的邮箱。  <br/> 不能使用此参数指定通讯组。  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>使用筛选器列表组合筛选器类型

筛选器 *列表* 是包含邮箱筛选器和网站筛选器（用逗号分隔）的筛选器。 使用筛选器列表是组合不同类型的筛选器的唯一受支持方法。 在下面的示例中，请注意，使用逗号分隔邮箱 **筛选器和站点** 筛选器：

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

在内容搜索运行过程中处理包含筛选器列表的筛选器时，会从筛选器列表中创建两个搜索权限筛选器：一个筛选器用于用逗号分隔的每个筛选器。 因此，在上一示例中，将创建一个邮箱搜索权限筛选器和一个网站搜索权限筛选器。 

使用筛选器列表的替代方法是创建两个单独的搜索权限筛选器。 因此，在上一示例中，您将为邮箱属性创建一个筛选器，为 site 属性创建一个筛选器。 在任一情况下，结果都是相同的。 优先使用筛选器列表或创建单独的搜索权限筛选器。

对于使用筛选器列表，请牢记以下事项：

- 您必须使用筛选器列表来创建包含邮箱筛选器和 **MailboxContent** 筛选器的筛选器。

- 筛选器列表的每个组件都可以包含复杂的筛选器语法。 例如，邮箱和站点筛选器可以包含多个筛选器，这些筛选器由 **-or 运算符** 分隔：

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>创建搜索权限筛选器的示例

下面是使用 **New-ComplianceSecurityFilter** cmdlet 创建搜索权限筛选器的示例。 
  
此示例允许用户 annb@contoso.com 加拿大的邮箱执行所有内容搜索操作。 此筛选器包含 ISO 3166-1 标准的加拿大三位数字国家/地区代码。

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

此示例允许用户 donh 和 suzanf 仅搜索 CustomAttribute1 邮箱属性中具有值“Marketing”的邮箱。

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

本示例允许"美国发现管理员"角色组的成员仅对美国的邮箱执行所有内容搜索操作。 此筛选器包含 ISO 3166-1 标准的美国三位数字国家/地区代码。
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

此示例允许电子数据展示管理员角色组的成员仅搜索渥太华用户通讯组的成员的邮箱。 PowerShell Get-DistributionGroup cmdlet Exchange Online查找渥太华用户组的成员。
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

本示例可防止任何用户删除管理团队通讯组的成员邮箱中的内容。 PowerShell Get-DistributionGroup cmdlet Exchange Online用于查找执行团队组的成员。

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

此示例允许电子数据OneDrive管理员自定义角色组的成员仅搜索组织中OneDrive for Business位置的内容。

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> 若要限制用户搜索特定网站，请使用筛选器  `Site_Path` ，如上一示例所示。 使用  `Site_Site` 将不起作用。 
  
本示例将用户限制为仅对日历年 2015 期间发送的电子邮件执行所有内容搜索操作。

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

与上一示例类似，此示例限制用户对上次在日历年 2015 中的某个时间更改的文档执行所有内容搜索操作。

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

本示例阻止"发现管理员OneDrive组的成员对组织的任何邮箱执行内容搜索操作。 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

本示例阻止组织任何人搜索 janets 或 sarad 发送或接收的电子邮件。

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

此示例使用筛选器列表来组合邮箱和网站筛选器。

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter** 用于返回搜索权限筛选器的列表。 使用  _FilterName_ 参数可返回特定搜索筛选器的信息。 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter** 用于修改现有搜索权限筛选器。 唯一必需的参数是  _FilterName_。 
  
| 参数 | 说明 |
|:-----|:-----|
| _操作_| _Action_ 参数指定应用筛选器的搜索操作的类型。 可能的内容搜索操作包括： <br/><br/> **导出：** 导出搜索结果时应用筛选器。  <br/> **预览：** 预览搜索结果时应用筛选器。  <br/> **清除：** 清除搜索结果时应用筛选器。  <br/> **搜索：** 运行搜索时应用筛选器。  <br/> **全部：** 筛选器将应用于所有搜索操作。  <br/> |
| _FilterName_|_FilterName_ 参数指定权限筛选器的名称。 |
| _筛选器_| _Filters_ 参数指定合规性安全筛选器的搜索条件。 可以创建两种不同类型的筛选器： <br/><br/>**邮箱和OneDrive筛选：** 此类型的筛选器指定邮箱OneDrive分配 (_Users_ 参数指定的) 帐户。 此类型的筛选器的语法为 _mailboxPropertyName_ **Mailbox_，** 其中 _MailboxPropertyName_ 指定用于设置可以搜索的邮箱的作用域的邮箱属性。 例如，邮箱筛选器将允许分配了此筛选器的用户仅搜索  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` CustomAttribute10 属性中值为"OttawaUsers"的邮箱。  任何受支持的可筛选收件人属性都可用于  _MailboxPropertyName_ 属性。 有关受支持的属性的列表，请参阅 [-RecipientFilter 参数的可筛选属性](/powershell/exchange/recipientfilter-properties)。 <br/><br/>**邮箱内容筛选：** 此类型的筛选器应用于可搜索的内容。 它指定分配的用户可以搜索的邮箱内容。 此类型的筛选器的语法为 MailboxContent_ _SearchablePropertyName：value_，**其中** _SearchablePropertyName_ 指定可以在内容搜索中指定的关键字查询语言 (KQL) 属性。 例如，邮箱内容筛选器将允许分配了此筛选器的用户仅搜索发送到域中收件人 contoso.com  `MailboxContent_recipients:contoso.com` 的邮件。  有关可搜索邮件属性的列表，请参阅内容 [搜索的关键字查询](keyword-queries-and-search-conditions.md)。 <br/><br/>**网站和网站内容筛选：** 有两SharePoint和OneDrive for Business网站相关的筛选器，您可以使用它们来指定分配的用户可以搜索的网站或网站内容： <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent** _ *SearchableSiteProperty*<br/><br/>这两个筛选器可互换。 例如，  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` 和  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` 返回相同的结果。 但是，为了帮助您确定筛选器用途，您可以使用 指定与网站相关的属性 (如网站 URL) 并指定与内容相关的属性 ( `Site_`  `SiteContent_` 如文档类型。 例如，筛选器将允许分配了此筛选器的用户  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` 仅搜索网站集中 https://contoso.spoppe.com/sites/doctors 的内容。 该筛选器将允许分配了此筛选器的用户仅搜索  `"SiteContent_FileExtension -eq 'docx'"` Word 2007 (及更高版本中的 Word) 。  <br/><br/>有关可搜索网站属性的列表，请参阅 Overview [of crawled and managed properties in SharePoint](/SharePoint/technical-reference/crawled-and-managed-properties-overview)。 "**可查询"** 列中标有"是"的属性可用于创建站点或网站内容筛选器。 <br/><br/>          |
| _用户_|_Users_ 参数指定将此筛选器应用于其内容搜索的用户。 由于这是一个多值属性，因此指定具有此参数的用户或用户组将覆盖现有用户列表。 有关添加和删除选定用户的语法，请参阅以下示例。 <br/><br/>您还可以使用 _Users_ 参数指定Microsoft 365 合规中心角色组。 这可让您创建一个自定义角色组，然后为该角色组分配搜索权限筛选器。 例如，假设您具有一家跨国公司美国子公司的电子数据展示管理员自定义角色组。 通过使用角色组) 的 Name 属性，可以使用  _Users_ 参数指定此角色组 (，然后使用  _Filter_ 参数仅允许搜索美国的邮箱。 <br/><br/>不能使用此参数指定通讯组。 |

## <a name="examples-of-changing-search-permissions-filters"></a>更改搜索权限筛选器的示例

这些示例显示如何使用 **Get-ComplianceSecurityFilter** 和 **Set-ComplianceSecurityFilter** cmdlet 向分配了筛选器的现有用户列表中添加或删除用户。 当您在筛选器中添加或删除用户时，使用这些用户的 SMTP 地址指定用户。 
  
此示例是将用户添加到筛选器。

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.add("pilarp@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

此示例是从筛选器中删除用户。

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.remove("annb@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

**Remove-ComplianceSecurityFilter** 用于删除搜索筛选器。 使用  _FilterName_ 参数指定要删除的筛选器。 
  
## <a name="more-information"></a>详细信息

- **搜索权限筛选功能的工作原理是什么？** 运行内容搜索时，权限筛选器将追加到搜索查询中。 权限筛选器通过 **AND** 布尔运算符加入到搜索查询中。 搜索查询和权限筛选器的查询逻辑如下所示：

  ```text
  <SearchQuery> AND <PermissionsFilter>
  ```

  例如，您具有允许 Bob 对 Workers 通讯组的成员邮箱执行所有搜索操作的权限筛选器。 然后，Bob 使用搜索查询 对组织的所有邮箱运行内容搜索  `sender:jerry@adatum.com` 。 由于权限筛选器和搜索查询逻辑上由 **AND** 运算符组合在一起，因此搜索将返回由 jerry@adatum.com 发送给 Workers 通讯组的任何成员的任何邮件。 

- **如果您有多个搜索权限筛选器会怎么样？** 在内容搜索查询中，多个权限筛选器通过 **OR** 布尔运算符进行组合。 因此，如果满足任意筛选器，将会返回结果。 在内容搜索中，所有 (**OR** 运算符组合) AND 运算符与搜索 **查询组合在** 一起。 

  ```text
  <SearchQuery> AND  (<PermissionsFilter1> OR <PermissionsFilter2> OR <PermissionsFilter3>)
  ```

  让我们以上一个示例为例，其中搜索筛选器允许 Bob 仅搜索 Workers 通讯组的成员的邮箱。 然后，我们创建另一个筛选器来阻止 Bob 搜索 Phil 的邮箱（“Mailbox_Alias -ne 'Phil'”）。 并且，让我们假设 Phil 是工作人员组的成员。 当 Bob 对组织 (的所有邮箱运行上一示例) 的内容搜索时，会返回 Phil 的邮箱的搜索结果，即使应用了筛选器来阻止 Bob 搜索 Phil 的邮箱。 这是因为满足允许 Bob 搜索工作人员组的第一个筛选器的条件。 还因为 Phil 是工作人员组的成员，所以 Bob 可以搜索 Phil 的邮箱。 

- **搜索权限筛选是否适用于非活动邮箱？** 可以，可以使用邮箱和邮箱内容筛选器来限制哪些人可以搜索组织中非活动邮箱。 与常规邮箱一样，非活动邮箱必须配置有用于创建权限筛选器的收件人属性。 如有必要，可以使用 **Get-Mailbox -InactiveMailboxOnly** 命令显示非活动邮箱的属性。 有关详细信息，请参阅 Create [and manage inactive mailboxes in Office 365](create-and-manage-inactive-mailboxes.md)。
    
- **搜索权限筛选是否适用于公用文件夹？** 不正确。 如前所述，搜索权限筛选不能用于限制哪些人可以搜索 Exchange。 例如，权限筛选器无法从搜索结果中排除公用文件夹位置中的项目。 

- **允许用户搜索特定服务中所有内容位置是否也会阻止他们搜索其他服务中的内容位置？** 不正确。 如前所述，您必须创建搜索权限筛选器以明确阻止用户搜索特定服务 (例如阻止用户搜索任何 Exchange 邮箱或任何 SharePoint 网站) 。 换句话说，创建允许用户搜索组织中所有SharePoint的搜索权限筛选器不会阻止该用户搜索邮箱。 例如，若要SharePoint管理员仅搜索SharePoint，必须创建一个筛选器来阻止他们搜索邮箱。 同样，Exchange管理员只能搜索邮箱，必须创建阻止他们搜索网站的筛选器。

- **搜索权限筛选器是否计入搜索查询字符限制？** 是的。 搜索权限筛选器根据搜索查询的字符限制进行计数。 有关详细信息，请参阅 Advanced eDiscovery[中的限制](limits-ediscovery20.md)。
