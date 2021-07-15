---
title: 使用文件计划在整个内容生命周期中管理保留标签
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 文件计划为保留标签提供了高级管理功能。
ms.custom: seo-marvel-may2020
ms.openlocfilehash: 920a613cdc3a32267415d42cebe962e62ff6831a
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419759"
---
# <a name="use-file-plan-to-manage-retention-labels"></a>使用文件计划管理保留标签

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

尽管可以从 Microsoft 365 合规性中心的“**信息管理**”创建和管理保留标签，但是“**记录管理**”中的文件计划具有其他管理功能：

- 可以通过从电子表格中导入相关信息来批量创建保留标签。

- 可以从现有保留标签中导出信息，从而进行分析和脱机协作。

- 显示有关保留标签的更多信息，以使可以更轻松地从一个视图查看和查看所有保留标签的设置。

- 文件计划描述符支持每个标签的附加和可选信息。

文件计划可用于所有保留标签，即使未将内容标记为记录也是如此。

![文件计划页面](../media/compliance-file-plan.png)

若要了解什么是保留标签以及如何使用它们，请参阅[了解保留策略和保留标签](retention.md)。

## <a name="accessing-file-plan"></a>访问文件计划

要访问文件计划，您必须具有以下管理员角色之一：
    
- 保留管理者

- 仅拥有查看权限的保留管理者

在 Microsoft 365 合规性中心中，转到“**解决方案**” > “**记录管理**” > “**文件计划**”。 

如果“**记录管理**”未显示在导航窗格中，请首先向下滚动并选择“**全部显示**”。

![文件计划页面](../media/compliance-file-plan.png)

## <a name="navigating-your-file-plan"></a>浏览文件计划

如果已经从 Microsoft 365 合规性中心中的“**信息治理**”创建了保留标签，则这些标签会自动显示在文件计划中。 

同样，如果现在在文件计划中创建保留标签，则如果未将标签配置为将内容标记为记录，则也可以从 **信息治理** 中使用。

在“**文件计划**”页面上，将看到所有标签及其状态和设置、可选的文件计划描述符、用于分析或启用标签脱机审阅的导出选项，以及用于创建保留标签的导入选项。 

### <a name="label-settings-columns"></a>“标签设置”列

通过选择“**自定义列**”选项，可以显示或隐藏除标签“**名称**”之外的所有列。 但是默认情况下，前几列显示有关标签状态及其设置的信息： 

- **状态** 标识标签是包含在标签策略中还是自动应用策略中（**活动**）或不（**非活动**）。

- **基于** 标识保留期的方式或时间。 有效值：
    - 事件
    - 创建时间
    - 上次修改时间
    - 标记时间

- **是记录** 标识在应用标签时是否将该项目标记为记录。 有效值：
    - 否
    - 是
    - 是(法规)

- **保留期限** 标识保留期限。 有效值：
    - 天
    - 月
    - 年限
    - 永久
    - 无

- “**处置类型**”列指明在保留期到期时如何处置内容。 有效值：
    - 无操作
    - 自动删除
    - 需评审

### <a name="file-plan-descriptors-columns"></a>文件计划描述符列

文件计划可将详细信息包含在保留标签中。 这些文件计划描述符提供了更多选项，可用于改进要标记的内容的易管理性和组织性。

默认情况下，从 **引用 ID** 开始，接下来的几列会显示这些可选的文件计划描述符，它们可以在创建保留标签或编辑现有标签时进行指定。 

为了帮助你开始使用，以下文件计划描述符有一些现成的值： 
- 企业机能/部门
- 类别
- 颁发机构类型
- 预配/引文 

创建或编辑保留标签时的文件计划描述符示例：

![创建或编辑保留标签时的文件计划描述符](../media/file-plan-descriptors.png)

文件计划描述符列示例视图：

![文件计划描述符列](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-retention-labels-to-analyze-or-enable-offline-reviews"></a>导出所有保留标签以分析或启用脱机评审

在文件计划中，可以将所有保留标签的详细信息都导出到 .csv 文件中，有助于推动定期与组织中数据管理利益干系人一起执行合规性评审。

要导出所有保留标签：在“**文件计划**”页上，单击“**导出**”：

![文件计划导出选项](../media/compliance-file-plan-export-labels.png)

将打开包含所有现有保留标签的 *.csv 文件，例如:

![包含所有保留标签的 CSV 文件](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a>向文件计划导入保留标签

在文件计划中，可以使用具有特定格式的 .csv 文件批量导入新的保留标签。 导入标签后，可以在 .csv 文件中进行编辑并再次导入文件，从而更轻松地批量编辑现有保留标签。

若要导入新的保留标签和修改现有保留标签，请执行以下操作： 

1. 在“**文件计划**”页面上，单击“**导入**”，以使用“**填写并导入文件计划**” 页面：

   ![文件计划导入选项](../media/compliance-file-plan-import-labels.png)

   ![空白文件计划模板下载选项](../media/file-plan-blank-template-option.png)

2. 按照说明下载空白模板:

   ![在 Excel 中打开空白文件计划模板](../media/file-plan-blank-template.png)

3. 使用以下信息填写模板，这些信息描述了每个属性的属性和有效值。对于导入，一些值具有最大长度:
    
    - **LabelName**：最大长度为 64 个字符
    - **Comment** 和 **Notes**：最大程度为 1024 个字符
    - 所有其他值：长度不受限制
    <br/>
    
   |属性|类型|必需|有效值|
   |:-----|:-----|:-----|:-----|
   |LabelName|字符串|是|此属性指定保留标签的名称，且必须为租户中的唯一属性。|
   |评论|字符串|否|使用此属性可以添加有关管理员的保留标签的说明。 此说明仅对在合规中心管理保留标签的管理员显示。|
   |注释|字符串|否|使用此属性可以添加有关用户的保留标签的说明。 当用户将鼠标悬停在 Outlook、SharePoint 和 OneDrive 等应用的标签上时，将显示此说明。 如果将此属性保留为空白，则会显示默认说明，用于说明标签的保留设置。 |
   |IsRecordLabel|字符串|否，除非 **法规** 为 **TRUE**|此属性指定标签是否将内容标记为记录。有效值包含:</br>**TRUE**: 标签将该项目标记为记录和结果，因此此项目无法删除。 </br>**FALSE**: 标签不会将内容标记为记录。 此值为默认值。 </br> </br> 组依赖项: 在指定此属性时，还必须指定 RetentionAction、RetentionDuration 以及 RetentionType。|
   |RetentionAction|字符串|否，除非指定了 **RetentionDuration**、**RetentionType** 或 **ReviewerEmail**|此属性指定在 RetentionDuration 属性指定的值(如果指定)过期后要执行的操作。有效值包含:</br>**Delete**：早于 RetentionDuration 属性指定的值的项目将被删除。</br>**Keep**：在 RetentionDuration 属性指定的保留期内保留项目，然后在保留期到期时不执行任何操作。 </br>**KeepAndDelete**：在 RetentionDuration 属性指定的保留期内保留项目，然后在保留期到期时删除这些项目。 </br> </br> 组依赖项: 指定此属性时，还必须指定 RetentionDuration 和 RetentionType。 |
   |RetentionDuration|String|否，除非指定了 **RetentionAction** 或 **RetentionType**|此属性指定保留内容的天数。有效值包含:</br>**无限制**: 项目将无限期保留。 </br>**_n_*: 正整数(以天为单位)；例如，**365**。 支持的最大数为 24,855，即 68 年。 如果需要的时间超过此最大值，请改用“无限制”。</br> </br> 组依赖项: 指定此属性时，还必须指定 RetentionAction 和 RetentionType。
   |RetentionType|字符串|否，除非指定了 **RetentionAction** 或 **RetentionDuration**|此属性指定是从内容创建日期、事件日期、标记日期还是从上次修改日期计算保留持续时间(如果指定)。有效值包含:</br>**CreationAgeInDays**</br>**EventAgeInDays**</br>**TaggedAgeInDays**</br>**ModificationAgeInDays** </br> </br> 组依赖项: 指定此属性时，还必须指定 RetentionAction 和 RetentionDuraction。|
   |ReviewerEmail|SmtpAddress|否|指定此属性后，保留持续时间到期时将触发处置评审。 此属性指定 **KeepAndDelete** 保留操作的审阅者的电子邮件地址。 </br> </br> 可以在租户中包含单个用户、分发组或安全组的电子邮件地址。 指定多个电子邮件地址，用分号分隔。 </br> </br> 组依赖项: 指定此属性时，还必须指定 **RetentionAction** (必须为 **KeepAndDelete**)、 **RetentionDuration** 以及 **RetentionType**。|
   |ReferenceId|字符串|否|该属性指定在 **参考 ID** 文件计划描述符中显示的值，可将其用作组织的唯一值。| 
   |Departmentname|字符串|否|该属性指定在 **功能/部门** 文件计划描述符中显示的值。|
   |类别|字符串|否|该属性指定在 **类别** 文件计划描述符中显示的值。|
   |SubCategory|字符串|否|该属性指定在 **子类别** 文件计划描述符中显示的值。|
   |AuthorityType|字符串|否|该属性指定在 **权限类型** 文件计划描述符中显示的值。|
   |CitationName|字符串|否|该属性指定在 **预配/引文** 文件计划描述符中显示的引文名称。 例如，“2002 年萨班斯-奥克斯利法案”。 |
   |CitationUrl|字符串|否|该属性指定在 **预配/引文** 文件计划描述符中显示的 URL。|
   |CitationJurisdiction|字符串|否|此属性指定在 **规定/引文** 文件计划描述符中显示的管辖权地或机构；例如“美国证券交易委员会 (SEC)”。|
   |Regulatory|字符串|否|此属性指定标签是否将内容标记为法规记录，该记录比记录 [更具限制性](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)。 要使用此标签配置，必须将租户配置为 [显示将内容标记为法规记录的选项](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record)，否则导入验证将失败。 有效值包含: </br>**TRUE**: 标签将项目标记为法规记录。 还必须将 **IsRecordLabel** 属性设置为 TRUE。</br>**FALSE**: 标签不将内容标记为法规记录。 此为默认值。|
   |EventType|String|否，除非 **RetentionType** 为 **EventAgeInDays**|此属性指定用于 [基于事件的保留](event-driven-retention.md) 的事件类型。 指定 **记录管理** > **事件** > **管理事件类型** 中显示的现有事件类型。 或使用 [Get-ComplianceRetentionEventType](/powershell/module/exchange/get-complianceretentioneventtype) cmdlet 查看可用的事件类型。 虽然存在一些内置事件类型，例如 **员工活动** 和 **产品寿命**，但你仍然可以创建自己的事件类型。 </br> </br> 如果你指定自己的事件类型，则事件类型必须出现在导入之前，因为作为导入流程的一部分名称需进行验证。|
   |||

   下面是包含有关保留标签的信息的模板示例。

   ![填写了信息的文件计划模板](../media/file-plan-filled-out-template.png)

4. 在 **填写并导入文件计划** 页面中的第 3 步下，点击 **浏览文件** 以上传填写的模板，然后选择 **下一步**。

   文件计划会上传文件并验证条目，显示导入统计信息。

   ![文件计划导入统计信息](../media/file-plan-import-statistics.png)

5. 具体取决于验证结果:
    
    - 如果验证失败: 备注行号和列名以在导入文件中进行更正。 选择 **关闭**，然后选择 **是** 进行确认。 在文件中更正错误并进行保存，再次选择 **导入** 选项，然后返回步骤 4。
    
    - 如果验证通过: 可以选择 **上线** 以使保留标签在租户中可用。 或选择页面中的“关闭”图标，并选择 **是** 以确认要关闭向导，此时保留标签在租户中不可用。

将导入的标签添加到租户后，现在可以将其添加到新的保留标签策略中，或进行自动应用。 可以在“**文件计划**”页上执行以下操作，方法是选择 **+创建标签**，然后选择“**发布标签策略**”或“**自动应用标签**”。

## <a name="next-steps"></a>后续步骤

若要详细了解如何创建和编辑保留标签及其策略，请参阅以下指南：
- [创建保留标签并在应用中应用它们](create-apply-retention-labels.md)
- [自动向内容应用保留标签](apply-retention-labels-automatically.md)