---
title: 在审核日志中搜索电子数据展示活动
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: 了解在合规性管理员在安全 & 合规中心中执行内容搜索和电子数据展示案例任务时，如何在审核日志中搜索所记录的事件。
ms.openlocfilehash: e7ed3ddf16d22750449d3211d96800334676e519
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726524"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>在审核日志中搜索电子数据展示活动

在安全 & 合规性中心或通过运行相应的 PowerShell cmdlet 在审核日志中执行的内容搜索和电子数据展示相关活动（针对核心电子数据展示和高级电子数据展示）。 当管理员或电子数据展示管理者（或任何用户分配的电子数据展示权限）在安全 & 合规性中心中执行以下内容搜索和核心电子数据展示任务时，将记录事件：
  
- 创建和管理核心和高级电子数据展示事例

- 创建、启动和编辑“内容搜索”

- 执行“内容搜索”操作，如预览、导出和删除搜索结果

- 在高级电子数据展示中管理保管人和审查集

- 为“内容搜索”配置权限筛选

- 管理电子数据展示管理员角色

> [!IMPORTANT]
> 本文中所述的活动只是使用安全 & 合规中心执行的电子数据展示任务的结果。 不包括使用 Exchange Online 中的就地电子数据展示工具或 SharePoint Online 中的电子数据展示中心执行的电子数据展示任务。 
  
有关搜索审核日志、所需权限以及导出搜索结果的详细信息，请参阅[在安全 & 合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>如何搜索和查看电子数据展示活动

目前，您必须执行几个特定的操作才能在审核日志中查看电子数据展示活动。 方法如下：
  
1. 转到 [https://protection.office.com](https://protection.office.com)。

2. 使用工作或学校帐户进行登录。

3. 在左窗格中，单击 "**搜索**"，然后单击 "**审核日志搜索**"。

4. 在 "**活动**" 下拉列表中，在 "**电子数据展示活动**" 或 "**高级电子数据展示活动**" 下，单击要搜索的一个或多个活动。

    > [!NOTE]
    > "**活动**" 下拉列表还包含一组名为 "**电子数据展示 cmdlet** " 的活动，这些活动将从 cmdlet 审核日志中返回记录。
  
5. 选择日期和时间范围以显示在该时间段内发生的电子数据展示事件。 

6. 在 "**用户**" 框中，选择要为其显示搜索结果的一个或多个用户。 将此框保留为空将返回所有用户的条目。

7. 单击“**搜索**”以使用搜索条件运行搜索。

8. 在搜索结果显示之后，可以单击 "**筛选结果**" 以筛选或排序生成的活动记录。 遗憾的是，不能使用筛选来显式排除某些活动。 

9. 若要查看活动的详细信息，请单击搜索结果列表中的活动记录。 

    将显示 "弹出**详细信息**" 页，其中包含事件记录中的详细属性。 若要显示其他详细信息，请单击 "**详细信息**"。 有关这些属性的说明，请参阅 "[电子数据展示活动的详细属性](#detailed-properties-for-ediscovery-activities)" 部分。

10. 如果需要，可以将审核日志搜索结果导出到 CSV 文件，然后使用 Excel Power Query 功能设置这些记录的格式并对其进行筛选。 有关详细信息，请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md)。

## <a name="ediscovery-activities"></a>电子数据展示活动

下表介绍了在管理员或电子数据展示管理器使用安全 & 合规中心或在安全 & 合规中心 PowerShell 中运行相应的 cmdlet 时记录的内容搜索和核心电子数据展示活动。 另请注意，当您在此列表中搜索活动时，将返回在 "高级" 中执行的一些活动。
  
> [!NOTE]
> 本节中介绍的电子数据展示活动提供了与下一节中所述的电子数据展示 cmdlet 活动类似的信息。 我们建议您使用本节中介绍的电子数据展示活动，因为这些活动将在30分钟内显示在审核日志搜索结果中。 在审核日志搜索结果中显示电子数据展示 cmdlet 活动需要长达24小时。 
  
|**友好名称**|**操作**|**相应的 cmdlet**|**说明**|
|:-----|:-----|:-----|:-----|
|向电子数据展示事例添加了成员  <br/> |CaseMemberAdded  <br/> |外接 ComplianceCaseMember  <br/> |将用户添加为电子数据展示事例的成员。 作为案例的成员，用户可以执行各种与事例相关的任务，具体取决于是否已为其分配了必要的权限。  <br/> |
|更改内容搜索  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |已更改现有内容搜索。 更改可以包括添加或删除内容位置或编辑搜索查询。  <br/> |
|更改了电子数据展示管理员成员身份  <br/> |CaseAdminUpdated  <br/> |更新-eDiscoveryCaseAdmin  <br/> |组织中的电子数据展示管理员的列表已更改。 当电子数据展示管理员的列表被替换为一组新用户时，将记录此活动。 如果添加或删除了单个用户，则会记录 CaseAdminAdded 操作。  <br/> |
|更改后的电子数据展示案例  <br/> |CaseUpdated  <br/> |Get-compliancecase  <br/> |更改了电子数据展示事例。 更改包括关闭打开的事例或重新打开已关闭的案例。  <br/> |
|更改的电子数据展示事例成员资格  <br/> |CaseMemberUpdated  <br/> |更新-ComplianceCaseMember  <br/> |电子数据展示事例的成员资格列表已更改。 当所有成员都替换为一组新用户时，将记录此活动。 如果添加或删除了单个成员，则会记录 CaseMemberAdded 或 CaseMemberRemoved 操作。  <br/> |
|已更改的搜索权限筛选器  <br/> |SearchPermissionUpdated  <br/> |New-compliancesecurityfilter  <br/> |已更改搜索权限筛选器。  <br/> |
|更改了电子数据展示事例保留的搜索查询  <br/> |HoldUpdated  <br/> |New-caseholdrule  <br/> |与电子数据展示事例关联的基于查询的保留已更改。 可能的更改包括编辑基于查询的保留的查询或日期范围。  <br/> |
|已下载内容搜索预览项  <br/> |PreviewItemDownloaded  <br/> |不适用  <br/> |用户在预览搜索结果时，将项目下载到本地计算机（通过单击 "**下载原始项目**" 链接）。  <br/> |
|列出的内容搜索预览项  <br/> |PreviewItemListed  <br/> |不适用  <br/> |用户单击 "**预览搜索结果**" 以显示 "预览搜索结果" 页，其中列出了从内容搜索结果中最长可达1000个项目。  <br/> |
|已查看内容搜索预览项  <br/> |PreviewItemRendered  <br/> |不适用  <br/> |在预览搜索结果时，电子数据展示管理器通过单击它查看项目。  <br/> |
|已创建内容搜索  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |已创建新的内容搜索。  <br/> |
|创建的电子数据展示管理员  <br/> |CaseAdminAdded  <br/> |外接 eDiscoveryCaseAdmin  <br/> |将用户添加为组织中的电子数据展示管理员。  <br/> |
|创建的电子数据展示事例  <br/> |CaseAdded  <br/> |新 Get-compliancecase  <br/> |创建了电子数据展示事例。 创建事例时，只需为其指定一个名称。 其他与案例相关的任务，如添加成员、创建保留和创建与事例关联的内容搜索将导致其他事件被记录。  <br/> |
|已创建搜索权限筛选器  <br/> |SearchPermissionCreated  <br/> |新 New-compliancesecurityfilter  <br/> |已创建搜索权限筛选器。  <br/> |
|为电子数据展示事例保留创建搜索查询  <br/> |HoldCreated  <br/> |新 New-caseholdrule  <br/> |已创建与电子数据展示事例相关联的基于查询的保留。  <br/> |
|已删除内容搜索  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |已删除现有内容搜索。  <br/> |
|删除的电子数据展示管理员  <br/> |CaseAdminRemoved  <br/> |EDiscoveryCaseAdmin  <br/> |从你的组织中删除了电子数据展示管理员。  <br/> |
|删除的电子数据展示事例  <br/> |CaseRemoved  <br/> |Get-compliancecase  <br/> |已删除电子数据展示事例。 必须删除与事例关联的所有保留，然后才能删除案例。  <br/> |
|已删除搜索权限筛选器  <br/> |SearchPermissionRemoved  <br/> |New-compliancesecurityfilter  <br/> |已删除搜索权限筛选器。  <br/> |
|已删除的针对电子数据展示事例保留的搜索查询  <br/> |HoldRemoved  <br/> |New-caseholdrule  <br/> |删除了与电子数据展示事例相关联的基于查询的保留。 删除保留中的查询通常是删除保留的结果。 当删除保留或保留查询时，将释放保留的内容位置。  <br/> |
|已下载内容搜索的导出  <br/> |SearchExportDownloaded  <br/> |不适用  <br/> |用户将内容搜索的结果下载到本地计算机。 必须先启动 "**内容搜索**" 活动的 "导出"，然后才能下载搜索结果。  <br/> |
|预览内容搜索的结果  <br/> |SearchPreviewed  <br/> |不适用  <br/> |用户预览内容搜索的结果。  <br/> |
|内容搜索的已清除结果  <br/> |SearchResultsPurged  <br/> |新 New-compliancesearchaction  <br/> |用户通过运行 New-compliancesearchaction 清除的 "**清除**" 命令清除了内容搜索的结果。  <br/> |
|删除了内容搜索的分析  <br/> |RemovedSearchResultsSentToZoom  <br/> |New-compliancesearchaction  <br/> |已删除内容搜索准备操作（为高级电子数据展示准备搜索结果）。 如果准备操作的时间不是两周，则为高级电子数据展示准备的搜索结果将从 Microsoft Azure 存储区域中删除。 如果准备操作的时间已超过2周，则此事件指示仅删除了相应的准备操作。  <br/> |
|删除了内容搜索的导出  <br/> |RemovedSearchExported  <br/> |New-compliancesearchaction  <br/> |删除了内容搜索导出操作。 如果导出操作的时间不是两周，则已删除上载到 Microsoft Azure 存储区域的搜索结果。 如果导出操作的时间已超过2周，则此事件指示仅删除了相应的导出操作。  <br/> |
|从电子数据展示案例中删除了成员  <br/> |CaseMemberRemoved  <br/> |ComplianceCaseMember  <br/> |以电子数据展示事例的成员身份删除了用户。  <br/> |
|删除了内容搜索的预览结果  <br/> |RemovedSearchPreviewed  <br/> |New-compliancesearchaction  <br/> |已删除内容搜索预览操作。  <br/> |
|已删除对内容搜索执行的清除操作  <br/> |RemovedSearchResultsPurged  <br/> |New-compliancesearchaction  <br/> |删除了内容搜索清除操作。  <br/> |
|已删除搜索报告  <br/> |SearchReportRemoved  <br/> |New-compliancesearchaction  <br/> |删除了内容搜索导出报告操作。  <br/> |
|已开始对内容搜索进行分析  <br/> |SearchResultsSentToZoom  <br/> |新 New-compliancesearchaction  <br/> |内容搜索的结果已为高级电子数据展示中的分析做好了准备。  <br/> |
|已开始内容搜索  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |已启动内容搜索。 使用安全性 & 合规性中心 GUI 创建或更改内容搜索时，将自动启动搜索。 如果使用**new-compliancesearch** Cmdlet 或**new-compliancesearch** cmdlet 创建或更改搜索，则必须运行**new-compliancesearch** cmdlet 以启动搜索的。  <br/> |
|已开始导出内容搜索  <br/> |SearchExported  <br/> |新 New-compliancesearchaction  <br/> |用户导出内容搜索的结果。  <br/> |
|已启动导出报告  <br/> |SearchReport  <br/> |新 New-compliancesearchaction  <br/> |用户导出了内容搜索报告。  <br/> |
|已停止内容搜索  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |用户停止了内容搜索。  <br/> |
|(无)|CaseViewed|Get-compliancecase|用户在 "安全与合规中心" 中或通过运行 cmdlet 查看了**电子数据展示**页面上的案例列表。|
|(无)|SearchViewed|Get-ComplianceSearch|用户在 "安全与合规中心" 中或通过运行 cmdlet 查看了内容搜索（在 "**搜索**" 选项卡上列出）上的列表。 当用户查看与电子数据展示事例关联的内容搜索列表时（通过单击事例中的 "**搜索**" 选项卡）或运行**new-compliancesearch-case**命令时，也会记录此活动。|
|(无)|ViewedSearchExported|New-compliancesearchaction-导出|用户查看了 "安全和合规中心" 中的内容搜索导出作业列表（在 "**导出**" 选项卡上列出）或通过运行 cmdlet。 当用户在电子数据展示事例中查看导出作业列表时（在事例的 "**导出**" 选项卡上列出）或通过运行**New-compliancesearchaction-case 导出**命令，也会记录此活动。|
|(无)|ViewedSearchPreviewed|New-compliancesearchaction 预览|用户在 "安全与合规中心" 中或通过运行 cmdlet 预览内容搜索的结果。|
|||||
  
## <a name="advanced-ediscovery-activities"></a>高级电子数据展示活动

下表介绍了审核日志中记录的高级电子数据展示活动。 这些活动（以及相关的电子数据展示活动）可用于帮助您跟踪高级电子数据展示事例中活动的进展情况。

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

下表列出了管理员或用户使用安全 & 合规性中心或通过在与组织的安全 & 合规中心连接的远程 PowerShell 中运行相应的 cmdlet 来执行的与电子数据展示相关的活动时记录的 cmdlet 审核日志记录。 对于此表中列出的 cmdlet 活动以及上一节中介绍的电子数据展示活动，审核日志记录中的详细信息是不同的。
  
如前所述，电子数据展示 cmdlet 活动最长需要24小时才会显示在审核日志搜索结果中。
  
> [!TIP]
> 下表的 "**操作**" 列中的 cmdlet 链接到 TechNet 上相应的 cmdlet 帮助主题。 有关每个 cmdlet 的可用参数的说明，请参阅 cmdlet 帮助主题。 与 cmdlet 一起使用的参数和参数值包含在已记录的每个电子数据展示 cmdlet 活动的审核日志条目中。 
  
|**友好名称**|**Operation （cmdlet）**|**说明**|
|:-----|:-----|:-----|
|在电子数据展示事例中创建保留  <br/> |[新 CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |为电子数据展示事例创建了保留。 可以使用或不指定内容源来创建保留。 如果指定了内容源，则会在审核日志条目中对其进行标识。  <br/> |
|从电子数据展示案例中删除了保留  <br/> |[CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |删除了与电子数据展示事例相关联的保留。 删除保留将释放保留中的所有内容位置。 删除保留也会导致删除与保留相关的事例保留规则（请参阅下面的**new-caseholdrule** ）。  <br/> |
|在电子数据展示事例中更改了保留  <br/> |[CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |已更改与电子数据展示相关联的保留。 可能的更改包括添加或删除内容位置或关闭（禁用）保留。  <br/> |
|为电子数据展示事例保留创建搜索查询  <br/> |[新 New-caseholdrule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |已创建与电子数据展示事例相关联的基于查询的保留。  <br/> |
|已删除的针对电子数据展示事例保留的搜索查询  <br/> |[New-caseholdrule](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |删除了与电子数据展示事例相关联的基于查询的保留。 删除保留中的查询通常是删除保留的结果。 当删除保留或保留查询时，将释放保留的内容位置。  <br/> |
|更改了电子数据展示事例保留的搜索查询  <br/> |[New-caseholdrule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |与电子数据展示事例关联的基于查询的保留已更改。 可能的更改包括编辑基于查询的保留的查询或日期范围。  <br/> |
|创建的电子数据展示事例  <br/> |[新 Get-compliancecase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |创建了电子数据展示事例。 创建事例时，只需为其指定一个名称。 其他与案例相关的任务，如添加成员、创建保留和创建与事例关联的内容搜索将导致其他事件被记录。  <br/> |
|删除的电子数据展示事例  <br/> |[Get-compliancecase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |已删除电子数据展示事例。 必须删除与事例关联的所有保留，然后才能删除案例。  <br/> |
|更改后的电子数据展示案例  <br/> |[Get-compliancecase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |更改了电子数据展示事例。 更改包括关闭打开的事例或重新打开已关闭的案例。  <br/> |
|向电子数据展示事例添加了成员  <br/> |[外接 ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |将用户添加为电子数据展示事例的成员。 作为案例的成员，用户可以执行各种与事例相关的任务，具体取决于是否已为其分配了必要的权限。  <br/> |
|从电子数据展示案例中删除了成员  <br/> |[ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |以电子数据展示事例的成员身份删除了用户。  <br/> |
|更改的电子数据展示事例成员资格  <br/> |[更新-ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |电子数据展示事例的成员资格列表已更改。 当所有成员都替换为一组新用户时，将记录此活动。 如果添加或删除了单个成员，则**将记录 ComplianceCaseMember**或**ComplianceCaseMember**操作。  <br/> |
|已创建内容搜索  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |已创建新的内容搜索。  <br/> |
|已删除内容搜索  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |已删除现有内容搜索。  <br/> |
|更改内容搜索  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |已更改现有内容搜索。 更改可以包括添加或删除搜索查询和编辑搜索查询中的内容位置。  <br/> |
|已开始内容搜索  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |已启动内容搜索。 使用安全性 & 合规性中心 GUI 创建或更改内容搜索时，将自动启动搜索。 如果使用**new-compliancesearch** Cmdlet 或**new-compliancesearch** cmdlet 创建或更改搜索，则必须运行**new-compliancesearch** cmdlet 以启动搜索的。  <br/> |
|已停止内容搜索  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |正在运行的内容搜索已停止。  <br/> |
|已创建内容搜索操作  <br/> |[新 New-compliancesearchaction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |已创建内容搜索操作。 内容搜索操作包括预览搜索结果、导出搜索结果、为高级电子数据展示中的分析准备搜索结果，以及永久删除与内容搜索的搜索条件匹配的项目。  <br/> |
|已删除内容搜索操作  <br/> |[New-compliancesearchaction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |删除了内容搜索操作。  <br/> |
|已创建搜索权限筛选器  <br/> |[新 New-compliancesecurityfilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |已创建搜索权限筛选器。  <br/> |
|已删除搜索权限筛选器  <br/> |[New-compliancesecurityfilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |已删除搜索权限筛选器。  <br/> |
|已更改的搜索权限筛选器  <br/> |[New-compliancesecurityfilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |已更改搜索权限筛选器。  <br/> |
|创建的电子数据展示管理员  <br/> |[外接 eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |将用户添加为组织中的电子数据展示管理员。  <br/> |
|删除的电子数据展示管理员  <br/> |[EDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |从你的组织中删除了电子数据展示管理员。  <br/> |
|更改了电子数据展示管理员成员身份  <br/> |[更新-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |组织中的电子数据展示管理员的列表已更改。 当电子数据展示管理员的列表被替换为一组新用户时，将记录此活动。 如果添加或删除了单个用户，则会记录**eDiscoveryCaseAdmin**或**Remove-eDiscoveryCaseAdmin**操作。  <br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>电子数据展示活动的详细属性

下表介绍在搜索结果中列出的电子数据展示活动的**详细**信息页上单击 "**详细信息**" 页上包含的属性。 当您导出审核日志搜索结果时，这些属性也包含在 CSV 文件中。 电子数据展示活动的审核日志记录不会包含下面列出的每个详细属性。 
  
> [!TIP]
> 当您导出搜索结果时，CSV 文件包含一个名为**Detail**的列，其中包含多值属性中下表中所述的详细属性。 您可以使用 Excel 中的 Power Query 功能将此列拆分为多个列，这样每个属性都将拥有自己的列。 这将允许您对其中一个或多个属性进行排序和筛选。 有关详细信息，请参阅[search the audit log](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)中的 "将搜索结果导出到文件" 部分。 
  
|**属性**|**说明**|
|:-----|:-----|
|Case  <br/> |已创建、更改或删除的电子数据展示事例的标识（GUID）。  <br/> |
|ClientApplication  <br/> |此属性的电子数据展示 cmdlet 活动的价值为**EMC** 。 这表示活动是使用安全 & 合规性中心 GUI 或在 PowerShell 中运行 cmdlet 来执行的。  <br/> |
|ClientIP  <br/> |记录活动时使用的设备的 IP 地址。 IP 地址显示为 IPv4 或 IPv6 地址格式。  <br/> |
|ClientRequestId  <br/> | 对于电子数据展示活动，此属性通常为空。  <br/> |
|CmdletVersion  <br/> |在您的组织中运行的安全 & 合规中心版本的内部版本号。  <br/> |
|CreationTime  <br/> |在电子数据展示活动完成时的日期和时间（采用协调通用时间（UTC））。  <br/> |
|EffectiveOrganization  <br/> |Microsoft 365 组织的名称。  <br/> |
|ExchangeLocations  <br/> |在内容搜索中包括的 Exchange Online 邮箱或在电子数据展示事例中置于保留状态的 Exchange Online 邮箱。  <br/> |
|项  <br/> |从内容搜索中排除的邮箱或网站位置或电子数据展示事例中的保留。  <br/> |
|ExtendedProperties  <br/> |来自内容搜索、内容搜索操作或保存在电子数据展示事例中的其他属性，如对象 GUID 以及在执行活动时使用的相应 cmdlet 和 cmdlet 参数。  <br/> |
|Id  <br/> |报告条目的 ID。 ID 唯一标识审核日志条目。  <br/> |
|NonPIIParameters  <br/> |与 Operation 属性中标识的 cmdlet 一起使用的参数（不含任何值）的列表。 此属性中列出的参数与 Parameters 属性中列出的参数相同。  <br/> |
|ObjectId  <br/> |由 Operation 属性中列出的活动创建、更改或删除的对象的 GUID 或名称（例如，内容搜索或电子数据展示事例）。 此外，还会在审核日志搜索结果的项列中标识此对象。  <br/> |
|ObjectType  <br/> |用户创建、删除或修改的电子数据展示对象的类型;例如，内容搜索操作（预览、导出或清除）、电子数据展示事例或内容搜索。  <br/> |
|操作  <br/> |与所执行的电子数据展示活动相对应的操作的名称。  <br/> |
|OrganizationId  <br/> |Microsoft 365 组织的 GUID。  <br/> |
|参数  <br/> |与对应的 cmdlet 一起使用的参数的名称和值。  <br/> |
|PublicFolderLocations  <br/> |Exchange Online 中包含在内容搜索中的公用文件夹位置，或在电子数据展示事例中置于保留状态。  <br/> |
|Query  <br/> |与活动相关联的搜索查询，例如内容搜索或基于查询的保留。  <br/> |
|RecordType  <br/> |记录指示的操作类型。 值**18**表示与[电子数据展示 cmdlet 活动](#ediscovery-cmdlet-activities)部分中列出的活动相关的事件。 值为**24**表示与 "[如何搜索并查看电子数据展示活动](#how-to-search-for-and-view-ediscovery-activities)" 一节中列出的活动相关的事件。  <br/> |
|ResultStatus  <br/> |指示操作（在 Operation 属性中指定）成功还是失败。  <br/> |
|SecurityComplianceCenterEventType  <br/> |指示活动是安全 & 合规中心事件。 所有电子数据展示活动的值都为此属性的值为**0** 。  <br/> |
|SharepointLocations  <br/> |内容搜索中包含的 SharePoint Online 网站或在电子数据展示事例中置于保留状态。  <br/> |
|StartTime  <br/> |启动电子数据展示活动时的日期和时间（采用协调通用时间（UTC））。  <br/> |
|UserId  <br/> |执行了导致记录记录的活动（在操作属性中指定）的用户。 由系统帐户（如 NT AUTHORITY\SYSTEM）执行的电子数据展示活动的记录也包含在审核日志中。  <br/> |
|UserKey  <br/> |UserID 属性中标识的用户的备选 ID。 对于电子数据展示活动，此属性的值通常与 UserId 属性相同。  <br/> |
|UserServicePlan  <br/> |您的组织使用的订阅。 对于电子数据展示活动，此属性通常为空。  <br/> |
|UserType  <br/> |执行操作的用户类型。 以下值指示用户类型。  <br/> 0一个常规用户。 2组织中的管理员。 3 A Microsoft 数据中心管理员或数据中心系统帐户。 4系统帐户。 5应用程序。 6 A 服务主体。 |
|版本  <br/> |指示已记录的活动的版本号（由操作属性标识）。  <br/> |
|Workload  <br/> |发生活动的 Theservice。 对于电子数据展示活动，值为**SecurityComplianceCenter**。  <br/> |