---
title: 在 Microsoft 合规性管理器中修改评估模板
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
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
description: 了解如何在 Microsoft 合规性管理器中修改评估模板。
ms.openlocfilehash: 589e13e766e35d38eed985a0e7bb9e21544c370d
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64758522"
---
# <a name="modify-assessment-templates-in-microsoft-compliance-manager"></a>在 Microsoft 合规性管理器中修改评估模板

在合规性管理器中使用评估时，可能需要修改已创建的评估模板。 此过程类似于[模板创建](compliance-manager-templates-create.md)过程，因为将使用模板数据上传格式化Excel文件。

但是，在设置文件格式并更改现有模板数据时，需要注意一些详细信息。 **建议仔细查看这些说明，确保不会覆盖任何要保留的现有数据。**

若要详细了解此电子表格的格式，请参阅使用[Excel设置模板数据的格式](compliance-manager-templates-format-excel.md)。

## <a name="format-your-excel-file-to-modify-an-existing-template"></a>设置Excel文件的格式以修改现有模板

在 **评估模板** 页中，选择要修改的模板，这将显示其详细信息页。 然后选择 **“导出”以Excel**。 将下载包含所有模板数据的Excel文件。 将文件保存到本地计算机。

若要处理此文件，请跳转到以下部分，快速找到所需的说明：

- [编辑主模板属性](#edit-the-main-template-attributes)
- [添加改进操作](#add-an-improvement-action)
- [编辑改进操作的信息](#edit-an-improvement-actions-information)
- [更改改进操作的名称](#change-an-improvement-actions-name)
- [删除改进操作](#remove-an-improvement-action)
- [删除控件](#remove-a-control)

### <a name="edit-the-main-template-attributes"></a>编辑主模板属性

在 **“模板”** 选项卡上，可以编辑 **标题** 列、 **inScopeServices** 列和可能添加的任何其他列中的任何内容。 但是，无法编辑 **产品** 或 **认证** 列中的任何内容。

### <a name="add-an-improvement-action"></a>添加改进操作

1. 转到 **“操作”** 选项卡。将信息添加到现有操作下的第一个空行中所需的字段中。
2. 转到 **ControlFamily** 选项卡。查找包含改进操作映射到的控件的行。 将新操作添加到该行中的 **controlActionTitle** 列 (请记住使用两个分号分隔此字段中的多个操作，) 之间没有空格。
3. 保存电子表格。

### <a name="edit-an-improvement-actions-information"></a>编辑改进操作的信息

可以更改任何改进操作的信息， *但其标题除外*。 可以从 B 列向上编辑任何单元格，将文件导入模板后，该模板中的改进操作现在将包含更新的数据。

无法编辑 (列 A) 的 **actionTitle** ，因为如果编辑，合规性管理器会认为这是一个新的改进操作。 如果要更改改进操作的名称，请参阅下面的说明。

### <a name="change-an-improvement-actions-name"></a>更改改进操作的名称

若要更改改进操作的名称，必须在电子表格中显式指定要将现有名称替换为新名称。 请按以下步骤操作：

1. 在电子表格的 **“操作”** 选项卡中，将新列添加到 A 列之后的电子表格中。
2. 在此新列（现为列 B）中，将其标头放在第 1 行： **oldActionTitle** 中。
3. 复制 A 列的内容并将其粘贴到 B 列中。这会将你现有的改进操作标题（这是你想要更改的内容）放入 B 列。
4. 在 A 列 **中的 actionTitle** 中，删除旧名称并将其替换为改进操作的新名称。

请注意，对于改进操作和 Microsoft 操作，操作标题都必须采用英语编写，才能在控件中引用时识别。

### <a name="remove-an-improvement-action"></a>删除改进操作

若要从模板中删除改进操作，需要将其从引用它的每个控件中删除。 按照以下步骤修改电子表格：

1. 在 **“ControlFamily”** 选项卡上，搜索要删除的改进操作的标题。
2. 在显示该操作的单元格中删除改进操作的标题。 如果改进操作是该行上的唯一操作，请删除删除控件) 的整行 (。
3. 在 **“操作”** 选项卡上，删除包含要删除的改进操作的行。
4. 保存电子表格。

将电子表格导入模板后，改进操作将从模板中删除。

从模板中删除改进操作不会完全从合规性管理器中删除改进操作。 此操作仍可由另一个模板引用。

### <a name="remove-a-control"></a>删除控件

若要删除控件，请按照以下步骤修改电子表格，然后重新导入电子表格：

1. 在 **ControlFamily** 选项卡上，在 **controlName** 列中找到要删除的控件。
2. 删除该控件的行。
    - 如果此已删除的控件包含任何其他控件未引用的改进操作，则需要从“ **操作”** 选项卡中删除这些改进操作。否则，你将收到验证错误。

3. 保存电子表格。

将电子表格导入模板后，控件将从模板中删除。

## <a name="modify-template-info-in-compliance-manager"></a>修改合规性管理器中的模板信息

完成并保存Excel文件后，请执行以下步骤。

1. 再次打开评估模板页，然后选择模板。 在模板的详细信息页上，选择 **“修改”模板** 以启动修改向导。
2. 在 **Upload文件** 屏幕上，选择 **“浏览”** 查找并上传Excel文件。
3. 如果文件没有问题，下一个屏幕将显示上传的文件的名称。 如果需要更改文件，请选择 **“下** 一步”继续 (，**选择Upload其他文件**) 。
    - 如果文件出现问题，顶部的错误消息将说明问题所在。 需要修复文件并再次上传。 如果电子表格格式不正确，或者某些字段中的信息无效，则会产生错误。

4. “ **审阅”和“完成** ”屏幕显示改进操作和控件的数量以及模板的最大分数。 准备好审批后，选择 **“下一步**”。
5. 最后一个屏幕确认模板已修改。 选择 **“完成”** 以退出向导。

模板现在将包含所做的更改。 使用此修改后的模板的任何评估现在都将显示挂起的更新，你需要接受评估的更新，以反映模板中所做的更改。 详细了解 [评估更新](compliance-manager-assessments.md#accept-updates-to-assessments)。

> [!NOTE]
> 如果在英语以外的语言中使用合规性管理器，则在将模板导出到Excel时，会发现某些文本以英语显示。 操作的标题 (改进操作，如果适用，Microsoft 操作) 必须采用英语才能被控件识别。 如果对操作标题进行更改，请务必用英语编写它，以便文件正确导入。
