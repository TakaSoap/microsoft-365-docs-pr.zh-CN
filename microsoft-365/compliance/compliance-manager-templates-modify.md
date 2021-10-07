---
title: 修改 Microsoft 合规性管理器中的评估模板
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何修改 Microsoft 合规性管理器中的评估模板。
ms.openlocfilehash: 846c3bc02105a50863afa7caca6041d9f72a5d95
ms.sourcegitcommit: 81533e5d3e1aee0823539a7c9bdc20dba6541a02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2021
ms.locfileid: "60223494"
---
# <a name="modify-assessment-templates-in-microsoft-compliance-manager"></a>修改 Microsoft 合规性管理器中的评估模板

在合规性管理器中处理评估时，可能需要修改已创建的评估模板。 此过程类似于模板[创建](compliance-manager-templates-create.md)过程，你将上载包含模板数据的格式化Excel文件。

但是，当您使用对现有模板数据的更改设置文件格式时，请注意一些详细信息。 **我们建议您仔细阅读这些说明，以确保不会覆盖要保留的任何现有数据。**

若要了解有关此电子表格格式的信息，请参阅 Format [your template data with Excel](compliance-manager-templates-format-excel.md)。

## <a name="format-your-excel-file-to-modify-an-existing-template"></a>设置Excel文件的格式以修改现有模板

从 **评估模板页面中**   ，选择要修改的模板，这将显示其详细信息页面。 然后选择导出 **到Excel。** 将Excel模板数据的文件。 将文件保存到本地计算机。

若要使用此文件，请跳转到下面的部分，以快速找到所需的说明：

- [编辑主模板属性](#edit-the-main-template-attributes)
- [添加改进操作](#add-an-improvement-action)
- [编辑改进操作的信息](#edit-an-improvement-actions-information)
- [更改改进操作的名称](#change-an-improvement-actions-name)
- [删除改进操作](#remove-an-improvement-action)
- [删除控件](#remove-a-control)

### <a name="edit-the-main-template-attributes"></a>编辑主模板属性

在 **"模板"** 选项卡上，可以编辑标题列 **、inScopeServices** 列以及您可能已添加的其他任何列中的任何内容。 但是，你无法编辑产品或 **认证** 列中 **的任何** 内容。

### <a name="add-an-improvement-action"></a>添加改进操作

1. 转到" **操作"** 选项卡。将信息添加到现有操作下第一个空行的必填字段中。
2. 转到 **"ControlFamily"** 选项卡。查找包含改进操作映射到的控件的行。 将新操作添加到该行的 **controlActionTitle** 列 (请记住，用两个分号分隔此字段中的多个操作，两者之间没有空格) 。
3. 保存电子表格。

### <a name="edit-an-improvement-actions-information"></a>编辑改进操作的信息

您可以更改除标题 之外的任何 *改进操作的信息*。 您可以编辑 B 列前向的任何单元格，当您将文件导入回模板时，该模板中的改进操作现在将包含更新的数据。

您无法编辑 A **列** (操作) ，因为如果您这样做，合规性管理器会认为这是一个新的改进操作。 如果要更改改进操作的名称，请参阅下面的说明。

### <a name="change-an-improvement-actions-name"></a>更改改进操作的名称

如果要更改改进操作的名称，您必须在电子表格中明确指定将现有名称替换为新名称。 请按以下步骤操作：

1. 在电子表格 **的"** 操作"选项卡中，在 A 列之后向电子表格添加新列。
2. 在此新列（现在为 B 列）中，放在第 1 行中作为标题 **：oldActionTitle**。
3. 复制 A 列的内容并将其粘贴到 B 列。这会将现有改进操作标题（即要更改的标题）放入 B 列。
4. 在列 A **和 actionTitle** 中，删除旧名称，并将其替换为改进操作的新名称。

请注意，对于改进操作和 Microsoft 操作，操作标题都必须以英语编写，才能在控件中引用时被识别。

### <a name="remove-an-improvement-action"></a>删除改进操作

若要从模板中删除改进操作，需要将其从引用它的每个控件中删除。 请按照以下步骤修改电子表格：

1. 在 **ControlFamily** 选项卡上，搜索要删除的改进操作的标题。
2. 在显示改进操作的单元格中删除它的标题。 如果改进操作是该行上的唯一操作，请删除该行 (删除控件) 。
3. 在 **"操作** "选项卡上，删除包含要删除的改进操作的行。
4. 保存电子表格。

当您将电子表格导入回模板时，您的改进操作将从模板中删除。

从模板中删除改进操作不会从合规性管理器中完全删除改进操作。 该操作仍可由另一个模板引用。

### <a name="remove-a-control"></a>删除控件

若要删除控件，请执行以下步骤修改电子表格，然后重新导入电子表格：

1. 在 **ControlFamily** 选项卡上，在 controlName 列中查找要 **删除的** 控件。
2. 删除该控件的行。
    - 如果此已删除控件包含任何其他控件未引用的改进操作，则需要从"操作"选项卡中删除 **这些改进** 操作。否则，您将收到验证错误。

3. 保存电子表格。

将电子表格导入回模板时，控件将从模板中删除。

## <a name="modify-template-info-in-compliance-manager"></a>在合规性管理器中修改模板信息

完成并Excel文件后，请按照以下步骤操作。

1. 再次打开评估模板页面并选择你的模板。 在模板的详细信息页上，选择 **"修改模板** "以启动修改向导。
2. 在 **"Upload文件**"屏幕上，选择"浏览"查找并上载Excel文件。
3. 如果文件没有问题，下一个屏幕将显示已上传文件的名称。 如果需要 **更改** (，请选择"下一步"以继续Upload **文件) 。**
    - 如果文件有问题，顶部会显示一条错误消息，说明错误所在。 你将需要修复文件并再次上传它。 如果电子表格的格式不正确，或者某些字段中的信息无效，则会导致错误。

4. " **审阅和完成"** 屏幕显示改进操作和控件的数量以及模板的最大分数。 准备好批准后，选择"下一 **步"。**
5. 最后一个屏幕确认模板已修改。 选择 **"完成** "退出向导。

您的模板现在将包含您所做的更改。 使用此修改后模板的任何评估现在将显示挂起的更新，你将需要接受对评估的更新以反映在模板中所做的更改。 详细了解评估 [更新](compliance-manager-assessments.md#accept-updates-to-assessments)。

> [!NOTE]
> 如果使用英语版本外的其他语言使用合规性管理器，则你会注意到，导出模板进行自定义时，某些文本Excel。 操作标题 (改进操作，如果适用，Microsoft) 必须英语，控件必须识别这些操作。 如果对操作标题进行更改，请确保以英语编写它，以便正确导入文件。
