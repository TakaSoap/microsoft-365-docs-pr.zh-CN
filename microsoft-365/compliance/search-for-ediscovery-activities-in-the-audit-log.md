---
title: 在审核日志中搜索电子数据展示活动
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: 了解在用户分配了电子数据展示权限的用户执行内容搜索、核心电子数据展示和任务Advanced eDiscovery记录哪些Microsoft 365 合规中心。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e033864b15032e66995be439e1de750da06e988b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151010"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>在审核日志中搜索电子数据展示活动

Microsoft 365 合规中心 中通过运行相应的 PowerShell cmdlet (核心电子数据展示和 Advanced eDiscovery) 执行的内容搜索和与电子数据展示相关的活动记录在 审核日志 中。 当管理员或电子数据展示管理员 (或分配有电子数据展示权限的任何用户) 在) 中执行以下内容搜索和核心电子数据展示任务时，将记录Microsoft 365 合规中心：
  
- 创建和管理核心Advanced eDiscovery案例

- 创建、启动和编辑内容搜索

- 执行搜索操作，例如预览、导出和删除搜索结果

- 管理托管人和管理审核Advanced eDiscovery

- 配置内容搜索的权限筛选

- 管理电子数据展示管理员角色
  
有关搜索搜索列表审核日志所需的权限以及导出搜索结果的信息，请参阅在搜索审核日志[搜索](search-the-audit-log-in-security-and-compliance.md)Microsoft 365 合规中心。
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>如何搜索和查看电子数据展示活动

目前，您必须执行一些特定操作来查看电子数据展示审核日志。 方法如下：
  
1. 转到 <https://compliance.microsoft.com>，使用工作或学校帐户登录。

2. 在页面的左侧导航窗格中，Microsoft 365 合规中心审核 **"。**

3. 在"**活动**"下拉列表中的"**电子数据** 展示活动Advanced eDiscovery **活动"下**，单击要搜索的一个或多个活动。

    > [!NOTE]
    > " **活动** "下拉列表还包括一组名为 **"电子数据展示 cmdlet** 活动"的活动，这些活动将返回 cmdlet 审核日志。
  
4. 选择日期和时间范围以显示该时段内发生的电子数据展示事件。

5. 在" **用户** "框中，选择要显示其搜索结果的一个或多个用户。 将此框留空可返回所有用户的条目。

6. 单击“**搜索**”以使用搜索条件运行搜索。

7. 显示搜索结果后，可以单击"筛选 **结果** "来筛选或排序生成的活动记录。 遗憾的是，你无法使用筛选明确排除某些活动。 

8. 若要查看有关活动的详细信息，请单击搜索结果列表中的活动记录。 

    将显示 **"** 详细信息"飞出页面，其中包含事件记录的详细属性。 若要显示其他详细信息，请单击 **"详细信息"。** 有关这些属性的说明，请参阅电子数据 [展示活动的详细属性部分](#detailed-properties-for-ediscovery-activities) 。

9. 如果需要，可以将搜索审核日志导出到 CSV 文件，然后使用 power Query Excel格式化和筛选这些记录。 有关详细信息，请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md)。

## <a name="ediscovery-activities"></a>电子数据展示活动

下表介绍了管理员或电子数据展示管理员使用电子数据展示管理员执行与电子数据展示相关的活动时记录的内容搜索和核心电子数据Microsoft 365 合规中心。 搜索此列表中的Advanced eDiscovery，可能会返回在活动列表中执行的一些活动。
  
> [!NOTE]
> 本节中介绍的电子数据展示活动提供的信息与下一节中描述的电子数据展示 cmdlet 活动相似。 建议您使用本节中描述的电子数据展示活动，因为它们将在 30 分钟内审核日志搜索结果中显示。 电子数据展示 cmdlet 活动可能需要 24 小时才能显示在审核日志搜索结果中。
  
|**友好名称**|**操作**|**相应的 cmdlet**|**说明**|
|:-----|:-----|:-----|:-----|
|向电子数据展示案例添加了成员  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |用户已添加为电子数据展示案例的成员。 作为案例的成员，用户可以执行各种与案例相关的任务，具体取决于是否已为其分配必要的权限。  <br/> |
|已更改内容搜索  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |已更改现有内容搜索。 更改可能包括添加或删除内容位置或编辑搜索查询。  <br/> |
|更改了电子数据展示管理员成员身份  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |您组织中电子数据展示管理员的列表已更改。 当电子数据展示管理员列表替换为一组新用户时，将记录此活动。 如果添加或删除单个用户，将记录 CaseAdminAdded 操作。  <br/> |
|更改了电子数据展示案例  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |电子数据展示案例已更改。 更改包括关闭打开的案例或重新打开已关闭的案例。  <br/> |
|更改了电子数据展示案例成员身份  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |更改了电子数据展示案例的成员身份列表。 当所有成员替换为一组新用户时，将记录此活动。 如果添加或删除单个成员，将记录 CaseMemberAdded 或 CaseMemberRemoved 操作。  <br/> |
|已更改搜索权限筛选器  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |已更改搜索权限筛选器。  <br/> |
|更改了电子数据展示案例保留的搜索查询  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |已更改与电子数据展示案例关联的基于查询的保留。 可能的更改包括编辑基于查询的保留的查询或日期范围。  <br/> |
|下载的内容搜索预览项  <br/> |PreviewItemDownloaded  <br/> |不适用  <br/> |用户通过单击预览搜索结果时 (下载原始项目"链接) 下载项目到其本地计算机。  <br/> |
|列出的内容搜索预览项  <br/> |PreviewItemListed  <br/> |不适用  <br/> |用户单击" **预览搜索结果** "可显示预览搜索结果页面，其中最多列出搜索结果中的 1，000 个项目。  <br/> |
|查看的内容搜索预览项  <br/> |PreviewItemRendered  <br/> |不适用  <br/> |电子数据展示管理员在预览搜索结果时通过单击某个项目来查看该项目。  <br/> |
|已创建内容搜索  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |已创建一个新的内容搜索。  <br/> |
|已创建电子数据展示管理员  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |用户已添加为组织中电子数据展示管理员。  <br/> |
|已创建电子数据展示案例  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |已创建电子数据展示案例。 创建案例时，只需为案例命名。 其他与案例相关的任务（如添加成员、创建保留和创建与案例关联的内容搜索）将导致记录其他事件。  <br/> |
|已创建的搜索权限筛选器  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |已创建搜索权限筛选器。  <br/> |
|为电子数据展示案例保留创建了搜索查询  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |已创建与电子数据展示案例关联的基于查询的保留。  <br/> |
|已删除的内容搜索  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |已删除现有内容搜索。  <br/> |
|已删除电子数据展示管理员  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |从组织中删除了电子数据展示管理员。  <br/> |
|已删除电子数据展示案例  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |已删除电子数据展示案例。 必须删除与案例关联的任何保留，然后才能删除该案例。  <br/> |
|已删除搜索权限筛选器  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |已删除搜索权限筛选器。  <br/> |
|已删除电子数据展示案例保留的搜索查询  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |已删除与电子数据展示案例关联的基于查询的保留。 从保留中删除查询通常是删除保留的结果。 删除保留或保留查询时，将释放保留的内容位置。  <br/> |
|下载的内容搜索导出  <br/> |SearchExportDownloaded  <br/> |不适用  <br/> |用户将内容搜索的结果下载到其本地计算机。 内容 **搜索活动的** "开始"导出必须启动，然后才能下载搜索结果。  <br/> |
|内容搜索的预览结果  <br/> |SearchPreviewed  <br/> |不适用  <br/> |用户预览了内容搜索的结果。  <br/> |
|内容搜索的清除结果  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |用户通过运行 **New-ComplianceSearchAction -Purge** 命令清除内容搜索结果。  <br/> |
|删除了内容搜索分析  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |内容搜索准备操作 (为已删除的内容Advanced eDiscovery) 搜索结果。 如果准备操作不到两周，则为准备的Advanced eDiscovery将从存储区域Microsoft Azure搜索结果。 如果准备操作超过 2 周，则此事件指示仅删除了相应的准备操作。  <br/> |
|删除了内容搜索的导出  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |已删除内容搜索导出操作。 如果导出操作少于两周，则上载到存储区域Microsoft Azure搜索结果已删除。 如果导出操作超过 2 周，则此事件指示仅删除了相应的导出操作。  <br/> |
|从电子数据展示案例中删除成员  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |已删除用户作为电子数据展示案例的成员。  <br/> |
|删除了内容搜索的预览结果  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |已删除内容搜索预览操作。  <br/> |
|删除了对内容搜索执行的清除操作  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |已删除内容搜索清除操作。  <br/> |
|已删除搜索报告  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |已删除内容搜索导出报告操作。  <br/> |
|内容搜索的开始分析  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |内容搜索结果已准备用于Advanced eDiscovery。  <br/> |
|已启动内容搜索  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |内容搜索已启动。 当您使用搜索工具创建或更改内容Microsoft 365 合规中心，搜索将自动启动。<br/> |
|开始导出内容搜索  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |用户导出了内容搜索的结果。  <br/> |
|已启动导出报告  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |用户导出了内容搜索报告。  <br/> |
|已停止内容搜索  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |用户已停止内容搜索。  <br/> |
|(无)|CaseViewed|Get-ComplianceCase|用户在合规中心查看了核心电子数据展示案例。 此事件的审核记录包括已查看案例的名称。 |
|(无)|SearchViewed|Get-ComplianceSearch|用户通过访问核心电子数据展示案例的"搜索"选项卡上的搜索或在"内容搜索"页上访问该搜索来查看合规性 **中心的内容** 搜索。 此事件的审核记录包括已查看的搜索的标识。|
|(无)|ViewedSearchExported|Get-ComplianceSearchAction -Export|用户通过访问"内容"搜索页上"导出"选项卡上的导出来查看合规性 **中心中的内容搜索** 导出。  当用户查看与核心电子数据展示案例关联的导出时，也会记录此活动。|
|(无)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|用户在合规中心预览了内容搜索结果。 当用户预览与核心电子数据展示案例关联的搜索结果时，也会记录此活动。|
|||||
  
## <a name="advanced-ediscovery-activities"></a>高级电子数据展示活动

下表介绍了Advanced eDiscovery记录的活动审核日志。 这些活动可用于帮助你跟踪活动在一个Advanced eDiscovery进度。

|**友好名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|已将数据添加到另一审阅集|AddWorkingSetQueryToWorkingSet|用户已将文档从一个审阅集添加到另一审阅集。|
|已将数据添加到审阅集|AddQueryToWorkingSet|用户已将与高级电子数据展示案例相关联的内容搜索的搜索结果添加到审阅集。|
|已将非 Microsoft 365 数据添加到审阅集|AddNonOffice365DataToWorkingSet|用户已将非 Microsoft 365 数据添加到审阅集。|
|已将修正的文档添加到审阅集|AddRemediatedData|用户上传了文档，这些文档具有已在审阅集中修复的索引错误。|
|已分析审阅集中的数据|RunAlgo|用户已对审阅集中的文档运行分析。|
|已批注审阅集中的文档|AnnotateDocument|用户已批注审阅集中的文档。 批注包含文档中的编修内容。|
|已比较加载集|LoadComparisonJob|用户已对审阅集中的两个不同加载集进行比较。 将与案例关联的内容搜索中的数据添加到审阅集时需要使用加载集。|
|已将编修文档转换为 PDF|BurnJob|用户已将审阅集中的所有编修文档转换为 PDF 文件。|
|已创建审阅集|CreateWorkingSet|用户已创建审阅集。|
|已创建审阅集搜索|CreateWorkingSetSearch|用户已创建用于在审阅集中搜索文档的搜索查询。|
|已创建标记|CreateTag|用户已在审阅集中创建标记组。 标记组可以包含一个或多个子标记。 这些标记随后用于标记审阅集中的文档。|
|已删除审阅集搜索|DeleteWorkingSetSearch|用户已删除审阅集中的搜索查询。|
|已删除标记|DeleteTag|用户已删除审阅集中的标记或标记组。|
|已下载文档|DownloadDocument|用户从审阅集下载了文档。|
|已编辑标记|UpdateTag|用户已更改审阅集中的标记。|
|已从审阅集导出文档|ExportJob|用户已从审阅集导出文档。|
|已修改案例设置|UpdateCaseSettings|用户已修改案例设置。 案例设置包括控制搜索和分析行为的案例信息、访问权限和设置。|
|已修改审阅集搜索|UpdateWorkingSetSearch|用户已编辑审阅集中的搜索查询。|
|已预览审阅集搜索|PreviewWorkingSetSearch|用户已预览审阅集中的搜索查询结果。|
|已修正错误文档|ErrorRemediationJob|用户修复了包含索引错误的文件。|
|已标记文档|TagFiles|用户标记审阅集中的文档。|
|已标记查询结果|TagJob|用户标记与审阅集中的搜索查询条件相匹配的所有文档。|
|已查看审阅集中的文档|ViewDocument|用户已查看审阅集中的文档。|
|||

## <a name="ediscovery-cmdlet-activities"></a>电子数据展示 cmdlet 活动

下表列出了管理员或审核日志使用合规中心或在安全与合规中心 PowerShell 中运行相应 cmdlet 执行电子数据展示相关活动时记录的 cmd & let 记录。 对于此表中列出的 cmdlet 活动和上一节中所述的电子数据展示活动，审核日志记录中的详细信息有所不同。
  
如前所述，电子数据展示 cmdlet 活动最多可能需要 24 小时才能显示在审核日志搜索结果中。
  
> [!TIP]
> 下表中"操作"列中的cmdlet 链接到 TechNet 上的相应 cmdlet 帮助主题。 转到 cmdlet 帮助主题，了解每个 cmdlet 的可用参数的说明。 与 cmdlet 一起使用的参数和参数值包含在记录的每个审核日志电子数据展示 cmdlet 活动的 审核日志 条目中。 
  
|**友好名称**|**操作 (cmdlet)**|**说明**|
|:-----|:-----|:-----|
|在电子数据展示案例中创建的保留  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |为电子数据展示案例创建了保留。 可以使用或不指定内容源创建保留。 如果指定了内容源，将在"内容源"条目审核日志标识。  <br/> |
|从电子数据展示案例中删除的保留  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |已删除与电子数据展示案例关联的保留。 删除保留将解除保留中所有内容位置。 删除保留还会导致删除与保留关联的案例保留规则 (请参阅下面的 **Remove-CaseHoldRule**) 。  <br/> |
|更改了电子数据展示案例中的保留  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |与电子数据展示关联的保留已更改。 可能的更改包括添加或删除内容位置，或者关闭 (保留) 功能。  <br/> |
|为电子数据展示案例保留创建了搜索查询  <br/> |[New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule) <br/> |已创建与电子数据展示案例关联的基于查询的保留。  <br/> |
|已删除电子数据展示案例保留的搜索查询  <br/> |[Remove-CaseHoldRule](/powershell/module/exchange/remove-caseholdrule) <br/> |已删除与电子数据展示案例关联的基于查询的保留。 从保留中删除查询通常是删除保留的结果。 删除保留或保留查询时，将释放保留的内容位置。  <br/> |
|更改了电子数据展示案例保留的搜索查询  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |已更改与电子数据展示案例关联的基于查询的保留。 可能的更改包括编辑基于查询的保留的查询或日期范围。  <br/> |
|已创建电子数据展示案例  <br/> |[New-ComplianceCase](/powershell/module/exchange/new-compliancecase) <br/> |已创建电子数据展示案例。 创建案例时，只需为案例命名。 其他与案例相关的任务（如添加成员、创建保留和创建与案例关联的内容搜索）将导致记录其他事件。  <br/> |
|已删除电子数据展示案例  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |已删除电子数据展示案例。 必须删除与案例关联的任何保留，然后才能删除该案例。  <br/> |
|更改了电子数据展示案例  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |电子数据展示案例已更改。 更改包括关闭打开的案例或重新打开已关闭的案例。  <br/> |
|向电子数据展示案例添加了成员  <br/> |[Add-ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |用户已添加为电子数据展示案例的成员。 作为案例的成员，用户可以执行各种与案例相关的任务，具体取决于是否已为其分配必要的权限。  <br/> |
|从电子数据展示案例中删除成员  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |已删除用户作为电子数据展示案例的成员。  <br/> |
|更改了电子数据展示案例成员身份  <br/> |[Update-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |更改了电子数据展示案例的成员身份列表。 当所有成员替换为一组新用户时，将记录此活动。 如果添加或删除单个成员，将记录 **Add-ComplianceCaseMember** 或 **Remove-ComplianceCaseMember** 操作。  <br/> |
|已创建内容搜索  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |已创建一个新的内容搜索。  <br/> |
|已删除的内容搜索  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |已删除现有内容搜索。  <br/> |
|已更改内容搜索  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |已更改现有内容搜索。 更改可能包括添加或删除要搜索的内容位置以及编辑搜索查询。  <br/> |
|已启动内容搜索  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |内容搜索已启动。 使用合规中心 GUI 创建或更改内容搜索时，将自动启动搜索。 如果使用 **New-ComplianceSearch** 或 **Set-ComplianceSearch** cmdlet 创建或更改搜索，您必须运行 **Start-ComplianceSearch** cmdlet 以启动搜索。  <br/> |
|已停止内容搜索  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |正在运行的内容搜索已停止。  <br/> |
|创建的内容搜索操作  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |已创建内容搜索操作。 内容搜索操作包括预览搜索结果、导出搜索结果、准备搜索结果以在 Advanced eDiscovery 中进行分析以及永久删除与内容搜索的搜索条件匹配的项目。  <br/> |
|已删除的内容搜索操作  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |已删除内容搜索操作。  <br/> |
|已创建的搜索权限筛选器  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |已创建搜索权限筛选器。  <br/> |
|已删除搜索权限筛选器  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |已删除搜索权限筛选器。  <br/> |
|已更改搜索权限筛选器  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |已更改搜索权限筛选器。  <br/> |
|已创建电子数据展示管理员  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |用户已添加为组织中电子数据展示管理员。  <br/> |
|已删除电子数据展示管理员  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |从组织中删除了电子数据展示管理员。  <br/> |
|更改了电子数据展示管理员成员身份  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |您组织中电子数据展示管理员的列表已更改。 当电子数据展示管理员列表替换为一组新用户时，将记录此活动。 如果添加或删除单个用户，将记录 **Add-eDiscoveryCaseAdmin** 或 **Remove-eDiscoveryCaseAdmin** 操作。  <br/> |
|(无)|[Get-ComplianceCase](/powershell/module/exchange/get-compliancecase) <br/>|当用户查看核心电子数据展示或电子数据展示事例列表时，Advanced eDiscovery活动。 当用户在核心电子数据展示中查看特定案例时，也会记录此活动。 当用户查看特定案例时，审核记录将包含已查看案例的标识。 如果用户仅查看事例列表，则审核记录不包含事例标识。|
|(无)|[Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)|当用户查看了与核心电子数据展示案例关联的内容搜索或搜索列表时，将记录此活动。 当用户查看特定内容搜索或查看与核心电子数据展示案例关联的特定搜索时，也会记录此活动。 当用户查看特定搜索时，审核记录包括已查看的搜索的标识。 如果用户仅查看了搜索列表，则审核记录不包含搜索标识。
|(无)|[Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)|当用户查看合规性搜索操作列表时记录此活动 (如导出、预览或清除) 核心电子数据展示案例相关的操作）。 当用户查看特定合规性搜索操作（如 (导出) 或查看与核心电子数据展示案例关联的特定操作时，也会记录此活动。 当用户查看搜索操作时，审核记录包括已查看的搜索操作的身份。 如果用户仅查看了操作列表，则审核记录不包含操作标识。|
||||

## <a name="detailed-properties-for-ediscovery-activities"></a>电子数据展示活动的详细属性

下表介绍了搜索结果中列出的电子数据展示活动的飞出页面上包含的属性。 导出搜索结果时，CSV 文件中也会包含审核日志属性。 电子审核日志活动的详细记录不包括下面列出的每个详细属性。
  
> [!TIP]
> 导出搜索结果时，CSV 文件包含一个名为 **AudtiData** 的列，其中包含下表中多值属性中描述的详细属性。 可以使用 Power Query 功能将Excel拆分为多个列，以便每个属性都有其自己的列。 这将允许对其中一个或多个属性进行排序和筛选。 有关详细信息，请参阅 Search the search the 审核日志 中的"将搜索结果导出到 [文件"部分](search-the-audit-log-in-security-and-compliance.md#step-3-export-the-search-results-to-a-file)。 
  
|**属性**|**说明**|
|:-----|:-----|
|情况  <br/> |标识 (、) 或删除电子数据展示案例的 GUID。  <br/> |
|ClientApplication  <br/> |电子数据展示 cmdlet 活动具有此属性 **的 EMC** 值。 这表示使用合规中心 GUI 或在 PowerShell 中运行 cmdlet 执行了活动。  <br/> |
|ClientIP  <br/> |记录活动时使用的设备的 IP 地址。 IP 地址显示为 IPv4 或 IPv6 地址格式。  <br/> |
|ClientRequestId  <br/> | 对于电子数据展示活动，此属性通常为空。  <br/> |
|CmdletVersion  <br/> |组织中运行的合规中心版本的内部版本号。  <br/> |
|CreationTime  <br/> |电子数据展示活动完成后，协调世界时 (UTC) 表示。  <br/> |
|EffectiveOrganization  <br/> |Microsoft 365 组织的名称。  <br/> |
|ExchangeLocations  <br/> |The Exchange Online mailboxes that are included in a content search or placed on hold in an eDiscovery case.  <br/> |
|排除  <br/> |从内容搜索或电子数据展示案例中的保留中排除的邮箱或网站位置。  <br/> |
|ExtendedProperties  <br/> |来自内容搜索、内容搜索操作或电子数据展示案例保留的其他属性，例如对象 GUID 以及执行活动时所使用的相应 cmdlet 和 cmdlet 参数。  <br/> |
|Id  <br/> |报告条目的 ID。 ID 唯一标识审核日志条目。  <br/> |
|NonPIIParameters  <br/> |参数列表，其中 (Operation 属性) cmdlet 使用的任何值。 此属性中列出的参数与 Parameters 属性中列出的参数相同。  <br/> |
|ObjectId  <br/> |对象的 GUID 或名称 (例如内容搜索或核心电子数据展示) 由 Operation 属性中列出的活动创建、访问、更改或删除。 此对象还标识在搜索结果的"审核日志列中。  <br/> |
|ObjectType  <br/> |用户创建、删除或修改的 eDiscovery 对象的类型;例如，内容搜索操作 (预览、导出或清除) 、电子数据展示案例或内容搜索。  <br/> |
|操作  <br/> |与所执行电子数据展示活动对应的操作的名称。  <br/> |
|OrganizationId  <br/> |您的组织的 GUID Microsoft 365 GUID。  <br/> |
|参数  <br/> |用于相应 cmdlet 的参数的名称和值。  <br/> |
|PublicFolderLocations  <br/> |内容搜索中包含的Exchange Online电子数据展示案例中置于保留状态的文件中的公用文件夹位置。  <br/> |
|查询  <br/> |与活动关联的搜索查询，如内容搜索或基于查询的保留。  <br/> |
|RecordType  <br/> |记录指示的操作类型。 值 **18** 指示与"电子数据展示 [cmdlet](#ediscovery-cmdlet-activities) 活动"部分中列出的活动相关的事件。 值 **24** 指示与如何搜索和查看电子数据展示活动部分中列出的活动 [相关的](#how-to-search-for-and-view-ediscovery-activities) 事件。  <br/> |
|ResultStatus  <br/> |指示操作（在 Operation 属性中指定）成功还是失败。  <br/> |
|SecurityComplianceCenterEventType  <br/> |指示活动是合规中心事件。 对于此属性，所有电子数据展示活动的值为 **0。**  <br/> |
|SharepointLocations  <br/> |The SharePoint Online sites that are included in a content search or placed on hold in an eDiscovery case.  <br/> |
|StartTime  <br/> |启动电子数据展示活动时 (协调世界时) UTC 时间。  <br/> |
|UserID  <br/> |执行活动的用户 (Operation 属性) 导致记录记录。 系统帐户执行电子数据展示活动的记录 (如 NT AUTHORITY\SYSTEM) 也包含在审核日志。  <br/> |
|UserKey  <br/> |UserID 属性中标识的用户的备选 ID。 对于电子数据展示活动，此属性的值通常与 UserId 属性相同。  <br/> |
|UserServicePlan  <br/> |组织使用的订阅。 对于电子数据展示活动，此属性通常为空。  <br/> |
|UserType  <br/> |执行操作的用户类型。 以下值指示用户类型。  <br/> 0 常规用户。 2 您的组织中的管理员。 3 Microsoft 数据中心管理员或数据中心系统帐户。 4 系统帐户。 5 应用程序。 6 服务主体。 |
|版本  <br/> |指示由记录的 Operation (标识的活动) 版本号。  <br/> |
|工作负载  <br/> |发生活动的服务。 对于电子数据展示活动，值为 **SecurityComplianceCenter**。  <br/> |
