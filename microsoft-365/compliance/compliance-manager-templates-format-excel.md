---
title: 在 Microsoft 合规性管理器Excel评估模板数据的格式
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在 Microsoft 合规性管理器Excel评估模板的数据。
ms.openlocfilehash: 899dd42401bb4c7acceb1db5bfe5816b383ae16b
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335654"
---
# <a name="format-assessment-template-data-in-excel-for-microsoft-compliance-manager"></a>在 Microsoft 合规性管理器Excel评估模板数据的格式

在[合规性](compliance-manager-templates-create.md)[管理器中](compliance-manager-templates-modify.md)创建、[](compliance-manager-templates-extend.md)修改或扩展评估模板时，Excel使用特定格式和架构的电子表格。 若要正确导入文件，必须遵循这些规范。

## <a name="download-example-spreadsheet"></a>下载示例电子表格

若要查看示例电子表格， [请下载示例文件](https://go.microsoft.com/fwlink/?linkid=2124865)。 可以使用它作为参考来创建你自己的文件。

如果计划修改现有模板，请首先在合规性管理器中查看模板的详细信息并下载其Excel文件。

## <a name="spreadsheet-format"></a>电子表格格式

该Excel电子表格包含四个选项卡，其中三个选项卡是必需的：

1. [模板](#template-tab) (模板) 
2. [ControlFamily](#controlfamily-tab) (必需) 
3. [需要](#actions-tab) (操作) 
4. [维度 (](#dimensions-tab) 可选) 

使用模板数据填写电子表格时，电子表格必须按上面列出的顺序包含选项卡，否则数据无法成功导入模板。

### <a name="template-tab"></a>"模板"选项卡

" **模板** "选项卡是必需的。 此选项卡中的信息提供有关模板的元数据。 有四个必需列。 这些列必须保留工作表Excel的顺序，如下所示。 您可以在这四列 **后** 添加您自己的列以提供您自己的维度。 如果这样做，请务必将它们添加到" **维度"** 选项卡。

- **title**：这是模板的标题，必须是唯一的。 它不能与合规性管理器中拥有的另一个模板共享名称，包括你自己的模板或合规性管理器模板。

- **product：** 这是一个必需维度。 列出与模板关联的产品。

- **certification：** This is the regulation you're using for the template.

- **inScopeServices：** 这些是此评估处理的服务 (例如，如果将 Office 365 列为产品，Microsoft Teams可能是范围内服务) 。 可以列出用两个分号分隔的多个服务。

> [!NOTE]
> 导入电子表格以创建或自定义模板后，无法编辑在产品和认证单元格中插入的数据。 此外，组不能包含具有相同产品/认证组合的 **两** 个评估。 你可以有多个模板，它们具有相同的产品/认证组合。

### <a name="controlfamily-tab"></a>ControlFamily 选项卡

**"ControlFamily"** 选项卡是必需的。  此选项卡中必须遵循示例电子表格中提供的顺序的必需列包括：

- **controlName：** 这是认证、标准或法规中的控制名称，通常为某种 ID 类型。 控件名称在模板中必须是唯一的。 电子表格中不能有多个同名的控件。

- **controlFamily：** 为 controlFamily 提供一个字词或短语，用于标识控件的广泛分组。 controlFamily 不必是唯一的;它可以在电子表格中多次列出。 同一 controlFamily 也可以列在多个模板中，尽管它们相互之间没有任何关系。 每个 controlFamily 都必须映射到至少一个控件。

- **controlTitle：** 为控件提供标题。 controlName 是参考代码，而标题是一种格式文本格式，通常在法规中可见。

- **controlDescription：** 提供控件的说明。

- **controlActionTitle：** 此字段将控件与一个或多个操作关联，按它们的 actionTitle 列出。 可以通过用两个分号分隔操作来添加多个操作，两者之间没有空格。 列出每个控件都必须包含至少一个现有操作，并且该操作可以在同一电子表格的"操作"选项卡中定义、位于其他模板中或由 Microsoft 创建。 不同的控件可以引用相同的操作。

### <a name="actions-tab"></a>"操作"选项卡

" **操作** "选项卡是必需的。  它指定了由组织管理的改进操作，而不是 Microsoft 的改进操作，这些改进操作已存在于合规性管理器中。 此选项卡的必需列必须遵循示例电子表格中提供的顺序：

- **actionTitle：** 这是操作的标题，是必填字段。 你提供的标题必须是唯一的。 **重要** 提示：如果引用了自己拥有的操作（ (如在其他模板) 中）并修改后续列中的任何元素，这些更改将传播到其他模板中的同一操作。

- **implementationType：** 在此必填字段中，列出以下三种实现类型之一：
- **操作** - 人员和流程为保护组织系统、资产、数据和人员的机密性、完整性和可用性而实施的 (例如：安全意识和培训) 
- **技术** - 使用信息系统的硬件、软件或固件组件中包含的技术和机制完成的操作，以保护组织系统和数据的机密性、完整性和可用性 (例如：多重身份验证) 
- **文档** - 通过记录的策略和过程实施的操作，这些策略和过程建立和定义保护组织系统、资产、数据和人员的机密性、完整性和可用性所需的控件 (例如：信息安全策略) 

- **actionScore：** 在此必填字段中，为操作提供一个数值分数值。 该值必须是一个从 1 到 99 的全数;不能为 0、null 或空白。 数字越大，其改进合规性状态的价值就越高。 下图演示合规性管理器如何对控件进行评分：

  ![合规性管理器控制点值。](../media/compliance-score-action-scoring.png "合规性管理器控制点值")

- **actionDescriptionTitle：** 这是说明的标题，是必需的。 此说明标题允许您在多个模板中执行相同的操作，并在每个模板中显示不同的说明。  此字段可帮助您阐明说明引用的模板。 在大多数情况下，可以在此字段中输入要创建的模板的名称。

- **actionDescription：** 提供操作的说明。 可以应用加粗文本和超链接等格式。 这是必填字段。

- **dimension-Action Purpose**：这是一个可选字段。 如果包含，则标头必须包含"dimension-"前缀。 你在此处包括的任何维度都将用作合规性管理器中的筛选器，并出现在合规性管理器中的改进操作详细信息页面上。

### <a name="dimensions-tab"></a>"维度"选项卡

" **维度"** 选项卡是可选的。 但是，如果在其他地方引用维度，如果已创建的模板或 Microsoft 模板中不存在维度，则需要在此处指定该维度。 下面列出了此选项卡的列：

- **dimensionKey：list** as "product"、"certifications"、"action purpose"
- **dimensionValue**：示例：Office 365、HIPPA、预防、检测

导出现有模板时，导出的电子表格将具有"维度"选项卡，其中列出了模板中使用的所有维度。
