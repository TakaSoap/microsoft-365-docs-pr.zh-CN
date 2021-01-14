---
title: 使用 Microsoft 合规性管理器中的评估模板
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用和管理模板以在 Microsoft 合规性管理器中生成评估。 使用格式化的 Excel 文件创建和修改模板。
ms.openlocfilehash: 34adb79392b235152cc0e00f5b7d661e90c9005e
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849606"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>使用合规性管理器中的评估模板

**本文内容：** 了解 **模板如何工作****以及如何从评估模板** 页管理它们。 获取有关创建新 **模板**、修改现有模板、使用 **Excel** 设置模板数据格式以及导出模板报表 **的说明**。

> [!IMPORTANT]
> 组织可用的评估模板取决于您的许可协议。 [查看详细信息](https://go.microsoft.com/fwlink/?linkid=2132371)。

## <a name="templates-overview"></a>模板概述

模板是在合规性管理器中创建评估的框架。 它们包含用于满足使用特定产品的认证要求的控件。 合规性管理器提供了一组全面的模板，可帮助组织遵守管理数据收集和使用的国家、区域和行业特定要求。

## <a name="list-of-pre-built-templates-for-assessments"></a>用于评估的预建模板列表

合规性管理器提供用于构建评估的模板，以帮助您遵守各种法规和标准。 查看 [合规性管理器提供的](compliance-manager-templates-list.md) 模板列表。 定期添加新模板，因此请经常检查列表。

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>从评估模板页查看和管理模板

合规性管理器中的"评估模板"页显示模板列表和关键详细信息。 该列表包括合规性管理器提供的模板以及组织已修改或创建的任何模板。 你可以应用筛选器，以根据认证、产品范围、国家/地区、行业、创建模板的人以及模板是否已启用评估创建来查找模板。

从模板行中选择一个模板，以显示其详细信息页面。 此页面包含模板的说明，以及有关认证、范围和控件详细信息的详细信息。 在此页中，可以选择相应的按钮来创建评估、将模板数据导出到 Excel 或修改模板。

## <a name="creating-and-modifying-templates-overview"></a>创建和修改模板概述

若要修改现有模板或创建自己的新模板，将使用特殊格式的 Excel 电子表格 (下载示例) 组合必要的控件数据。 [](https://go.microsoft.com/fwlink/?linkid=2124865) 完成电子表格后，在创建或修改模板的过程中将其导入合规性管理器。

> [!NOTE]
> 电子表格具有必须使用的特定格式和架构，否则无法正确导入合规性管理器。 格式 [说明](#formatting-your-template-data-with-excel) 如下。

**所需角色**

只有具有全局管理员或合规性管理器管理角色的用户才能创建和修改模板。 详细了解角色 [和权限](compliance-manager-setup.md#set-user-permissions-and-assign-roles)。

## <a name="create-a-new-template"></a>创建新模板

若要创建自己的新模板 (生成自定义评估) ，请按照以下步骤操作。

1. 转到合规性 **管理器中的** 评估模板页面。
2. 选择 **"新建模板"。** 模板创建向导将打开。
3. 选择要创建的模板类型。 在这种情况下，选择 **"创建自定义模板"，** 然后选择"下一 **步"。**
4. 在"上载 **文件**"屏幕上，选择"浏览"查找并上载包含所有所需模板数据的格式化 Excel 文件 (查看正确设置文件 [](#formatting-your-template-data-with-excel)格式的说明) 。
5. 如果文件没有问题，将显示上载的文件的名称。 选择 **"下一** 步"继续。  (如果需要更改文件，请选择"上载 **其他文件** ") 。
    - 如果文件出错，顶部的错误消息将说明错误。 你将需要修复文件并再次上载。 如果电子表格的格式不正确，或者某些字段中的信息无效，则 (重新参考格式设置) 。 [](#formatting-your-template-data-with-excel)  
    
6. " **审阅和完成** "屏幕显示改进操作和控件的数量以及模板的最高分数。 准备好批准后，选择" **创建模板"。**  (如果需要进行更改，请选择"上一步") 
7. 最后一个屏幕确认已创建一个新模板。 选择 **"** 完成"退出向导。
8. 你将到达新模板的详细信息页面，可在其中 [创建评估](compliance-manager-assessments.md#create-your-own-custom-assessment)。

## <a name="formatting-your-template-data-with-excel"></a>使用 Excel 设置模板数据的格式

用于创建模板的 Excel 电子表格包含四个选项卡，其中三个选项卡是必需的：

1. [模板](#template-tab) (是必需的) 
2. [ControlFamily](#controlfamily-tab) (必需) 
3. [需要](#actions-tab) (操作) 
4. [维度 (](#dimensions-tab) 可选) 

使用模板数据填写电子表格时，电子表格必须按上面列出的顺序包含选项卡，否则数据无法成功导入模板。

##### <a name="template-tab"></a>"模板"选项卡

" **模板"** 选项卡是必需的。 此选项卡中的信息提供有关模板的元数据。 有四个必需列。 列必须保留 Excel 工作表上的顺序，如下所示。 您可以在这 **四列之后** 添加自己的列，以提供您自己的维度。 如果这样做，请务必按照下面的说明将其添加到 **"** 维度" [选项卡](#dimensions-tab)。

- **title**： This is the title for your template， which must be unique. 它不能与合规性管理器中具有的另一个模板共享名称，包括你自己的模板或合规性管理器模板。

- **product：** This is a required dimension. 列出与模板关联的产品。

- **认证**：这是你要用于模板的法规。

- **inScopeServices：** 这些是此评估针对的产品中的服务 (例如，如果将 Office 365 列为产品，则 Microsoft Teams 可能是范围内服务) 。 可以列出用两个分号分隔的多个服务。

> [!NOTE]
> 导入电子表格以创建或自定义模板后，无法编辑在产品和认证单元格中插入的数据。 此外，组不能包含两个具有相同的产品/认证组合 **的评估** 。 你可以有多个模板，它们具有相同的产品/认证组合。

##### <a name="controlfamily-tab"></a>ControlFamily 选项卡

**"ControlFamily"** 选项卡是必需的。  此选项卡中必须遵循示例电子表格中提供的顺序的必需列包括：

- **controlName：** 这是认证、标准或法规中的控制名称，通常为某种类型的 ID。 控件名称在模板中必须是唯一的。 电子表格中不能有多个同名的控件。

- **controlFamily：** 为 controlFamily 提供一个单词或短语，用于标识控件的广泛分组。 controlFamily 不必是唯一的;它可以在电子表格中多次列出。 同一 controlFamily 也可以列在多个模板中，尽管它们相互之间没有任何关系。 每个 controlFamily 都必须映射到至少一个控件。

- **controlTitle：** 提供控件的标题。 虽然 controlName 是参考代码，但标题是一种格式文本格式，通常在法规中可见。

- **controlDescription：** 提供控件的说明。

- **controlActionTitle：** 这是要与此控件相关的操作的标题。 可以通过用两个分号分隔来添加多个操作，两者之间没有空格。 您列出的每一个控件都必须包括至少一个操作，并且该操作必须存在 (这意味着您可以列出您在同一电子表格的"操作"选项卡上列出的操作、存在于不同模板中的操作或由 Microsoft) 创建的操作。 不同的控件可以引用相同的操作。

##### <a name="actions-tab"></a>"操作"选项卡

" **操作"** 选项卡是必需的。  它指定了由组织管理的改进操作，而不是 Microsoft 的改进操作，这些操作已存在于合规性管理器中。 此选项卡的必需列必须遵循示例电子表格中提供的顺序：

- **actionTitle：** 这是操作的标题，是必填字段。 你提供的标题必须是唯一的。 **重要** 提示：如果引用自己拥有的操作（如在其他模板 (中) 并修改后续列中的任何元素，这些更改将传播到其他模板中的相同操作。

- **implementationType：** 在此必填字段中，列出以下三种实现类型之一：
    - **操作** - 人员和流程实施的操作，以保护组织系统、资产、数据和人员的机密性、完整性和可用性 (例如：安全意识和培训) 
    - **技术** - 使用信息系统的硬件、软件或固件组件中包含的技术和机制完成的操作，以保护组织系统和数据的机密性、完整性和可用性 (例如：多重身份验证) 
    - **文档** - 通过记录的策略和过程实现的操作，这些策略和过程建立和定义保护组织系统、资产、数据和人员的机密性、完整性和可用性所需的 (例如：信息安全策略) 

- **actionScore**：在此必填字段中，提供操作的数字分数值。 它必须是一个从 1 到 99 的全数;不能为 0、null 或空白。 数字越大，它越能改善合规性状态。 下图演示合规性管理器如何对控制措施进行评分：

![合规性管理器控制点值](../media/compliance-score-action-scoring.png "合规性管理器控制点值")

- **actionDescriptionTitle：** 这是说明的标题，是必需的。 此说明标题允许您在多个模板中执行相同的操作，并在每个模板中显示不同的说明。  此字段可帮助您阐明说明所引用的模板。 在大多数情况下，可以将要创建的模板的名称放在此字段中。

- **actionDescription：** 提供操作的说明。 可以应用加粗文本和超链接等格式。 这是必填字段。

- **dimension-Action Purpose**： This is an optional field. 如果包含，则标头必须包含"dimension-"前缀。 你在此处包括的任何维度都将用作合规性管理器中的筛选器，并显示在合规性管理器中的改进操作详细信息页上。

##### <a name="dimensions-tab"></a>"维度"选项卡

" **维度"** 选项卡是可选的。 但是，如果引用了其他位置的维度，如果已创建的模板或 Microsoft 模板中不存在维度，则需要在此处指定它。 下面列出了此选项卡的列：

- **dimensionKey**： list as "product"， "certifications，" "action purpose"
- **dimensionValue**： examples： Office 365， HIPPA， 预防， 检测

可以通过进入"租户管理"并选择"维度"选项卡来查看 **现有** 维度。此外，只要导出现有模板，导出的电子表格就会有"维度"选项卡，其中列出了模板中使用的所有维度。

## <a name="modify-a-template"></a>修改模板

您可能需要修改已创建的模板，例如添加控件，或者添加或删除改进操作。 此过程类似于模板创建过程，因为您将使用模板数据上载格式化的 Excel 文件。

但是，在将文件格式化为对现有模板数据进行更改时，需要了解一些特定的详细信息。 **我们建议您仔细阅读这些说明，以确保不会覆盖要保留的任何现有数据。**

### <a name="template-modification-process-steps"></a>模板修改过程步骤

若要修改模板，请按照以下步骤操作：

1. 从 **评估模板页面中** ，选择要修改的模板，这将显示其详细信息页面。
2. 选择 **"导出到 Excel"。** 将下载包含所有模板数据的 Excel 文件。 将文件保存到本地计算机。
3. 使用下面的说明修改 [Excel 文件，以更改模板](#formatting-your-excel-file-to-modify-a-template)。
4. 对 Excel 文件进行更改后，保存该文件。
5. 在模板的详细信息页上，选择 **"修改模板** "以启动修改向导。 
6. 在" **上载文件** "屏幕上，选择 **"浏览** "查找并上载 Excel 文件。
7. 如果文件没有问题，下一个屏幕将显示已上载文件的名称。 如果需要 **更改** (，请选择"下一步"继续) 。 
    - 如果文件有问题，顶部会显示一条错误消息，说明错误所在。 你将需要修复文件并再次上载。 如果电子表格的格式不正确，或者某些字段中的信息无效，则会导致错误。

8. " **审阅和完成** "屏幕显示改进操作和控件的数量以及模板的最高分数。 准备好批准时，选择"下一 **步"。**
9. 最后一个屏幕确认模板已修改。 选择 **"** 完成"退出向导。

您的模板现在将包含您所做的更改。 使用此修改后模板的任何评估现在将显示挂起的更新，你将需要接受对评估的更新以反映在模板中所做的更改。 了解有关评估 [更新的信息](compliance-manager-assessments.md#accepting-updates-to-assessments)。

> [!NOTE]
> 如果使用英语外的其他语言使用合规性管理器，则你会注意到，将模板导出到 Excel 时，某些文本以英语显示。 改进操作 (Microsoft 操作的标题) 英语，控件必须识别这些操作。 如果对操作标题进行更改，请确保以英语编写它，以便文件正确导入。

### <a name="formatting-your-excel-file-to-modify-a-template"></a>设置 Excel 文件的格式以修改模板

跳转到下面的部分，快速找到所需的说明：

- [编辑主模板属性](#edit-the-main-template-attributes)
- [添加改进操作](#add-an-improvement-action)
- [编辑改进操作的信息](#edit-an-improvement-actions-information)
- [更改改进操作的名称](#change-an-improvement-actions-name)
- [删除改进操作](#remove-an-improvement-action)
- [删除控件](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>编辑主模板属性

在 **"模板"** 选项卡上，可以编辑标题列 **、inScopeServices** 列和您可能已添加的其他任何列中的任何内容。 但是，你无法编辑产品或 **认证列中****的任何** 内容。

#### <a name="add-an-improvement-action"></a>添加改进操作

1. 转到" **操作"** 选项卡。将信息添加到现有操作下第一个空行的必填字段中。
2. 转到 **"ControlFamily"** 选项卡。查找包含改进操作映射到的控件的行。 将新操作添加到该行中的 **controlActionTitle** 列 (请记住，用两个分号分隔此字段中的多个操作，两者之间没有空格) 。
3. 保存电子表格。

#### <a name="edit-an-improvement-actions-information"></a>编辑改进操作的信息

你可以更改除标题之外的任何 *改进操作的信息*。 可以编辑 B 列前向的任何单元格，当您将文件导入回模板时，该模板中的改进操作现在将包含更新的数据。

您无法编辑 A **列** (操作) ，因为如果您这样做，合规性管理器会认为这是一个新的改进操作。 如果要更改改进操作的名称，请参阅下面的说明。

#### <a name="change-an-improvement-actions-name"></a>更改改进操作的名称

如果要更改改进操作的名称，您必须在电子表格中明确指定要用新名称替换现有名称。 请按以下步骤操作：

1. 在 **电子表格的** "操作"选项卡中，在 A 列之后向电子表格添加新列。
2. 在此新列（现在为 B 列）中，作为第 1 行的标题 **：oldActionTitle。**
3. 复制 A 列的内容并将其粘贴到 B 列。这会将现有改进操作标题（即要更改的标题）放入 B 列。
4. 在列 A **中的 actionTitle** 中，删除旧名称并将其替换为改进操作的新名称。

请注意，对于改进操作和 Microsoft 操作，操作标题都必须以英语编写，才能在控件中引用时被识别。

#### <a name="remove-an-improvement-action"></a>删除改进操作

若要从模板中删除改进操作，您需要将其从引用它的每个控件中删除。 按照以下步骤修改电子表格：

1. 在 **ControlFamily** 选项卡上，搜索要删除的改进操作的标题。
2. 删除其出现的单元格中的改进操作的标题。 如果改进操作是该行上的唯一操作，请删除该行 (删除控件) 。
3. 在 **"操作** "选项卡上，删除包含要删除的改进操作行。
4. 保存电子表格。

将电子表格导入回模板时，将从模板中删除改进操作。

从模板中删除改进操作不会从合规性管理器中完全删除改进操作。 该操作仍可由另一个模板引用。

#### <a name="remove-a-control"></a>删除控件

若要删除控件，请执行以下步骤修改电子表格，然后重新导入电子表格：

1. 在 **ControlFamily** 选项卡上，在 **controlName** 列中查找要删除的控件。
2. 删除该控件的行。
    - 如果此已删除的控件包含任何其他控件未引用的改进操作，则需要从"操作"选项卡中删除 **这些** 改进操作。否则，您将收到验证错误。

3. 保存电子表格。

将电子表格导入回模板后，控件将从模板中删除。

## <a name="export-a-template"></a>导出模板

可以导出包含所有模板数据的 Excel 文件。 您需要导出模板才能修改模板，因为这将是在修改过程中编辑和上载的 Excel [文件](#modify-a-template)。

若要导出模板，请转到模板详细信息页面，然后选择" **导出到 Excel"** 按钮。

请注意，导出从合规性管理器模板扩展的模板时，导出的文件将仅包含您添加到模板的属性。 导出的文件不包括 Microsoft 提供的原始模板数据。 若要获取此类报告，请参阅导出 [评估报告的说明](compliance-manager-assessments.md#export-an-assessment-report)。