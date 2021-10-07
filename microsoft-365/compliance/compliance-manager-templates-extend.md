---
title: 在 Microsoft 合规性管理器中扩展评估模板
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
description: 了解如何扩展 Microsoft 合规性管理器中的评估模板，以添加和修改控制措施。
ms.openlocfilehash: a255b3787a1da66be5882f00854d5a73cfe0352e
ms.sourcegitcommit: 81533e5d3e1aee0823539a7c9bdc20dba6541a02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2021
ms.locfileid: "60223492"
---
# <a name="extend-assessment-templates-in-microsoft-compliance-manager"></a>在 Microsoft 合规性管理器中扩展评估模板

合规性管理器提供向现有模板添加自己的控件和改进操作的选项。 此过程称为扩展模板。

若要扩展模板，将根据是扩展评估模板还是通用评估模板来Microsoft 365模板数据的特殊说明。

## <a name="extend-microsoft-365-assessment-templates"></a>扩展Microsoft 365评估模板

扩展 Microsoft 365 模板时，它仍然可以接收 Microsoft 发布的更新，当相关法规或产品策略发生更改时，可能会 (接受评估更新) 。 [](compliance-manager-assessments.md#accept-updates-to-assessments)

### <a name="prepare-template-data-and-create-extension"></a>准备模板数据和创建扩展

若要准备，您需要组合一个特殊格式的电子表格Excel导入必要的模板数据。 这些Excel文件遵循使用 Excel 设置评估模板数据[](compliance-manager-templates-format-excel.md)格式中列出的相同格式，但扩展有特殊要求。 请参阅以下其他要点以帮助防止错误：

- 电子表格应仅包含要添加到评估的操作和控制。
- 电子表格不能包含要修改的评估中已存在的任何控件或操作。
- 请考虑在模板标题中包括"扩展名"，例如，"GDPR – [你的公司名称]扩展名"。 这样，与 Microsoft 提供的标准模板或名称相似的自定义模板不同，更易于在评估模板页面上的列表中进行标识。

设置电子表格格式后，请按照以下步骤操作。

1. 转到评估 **模板页面，** 然后选择 **创建新模板**。 将打开模板创建向导。

2. 选择要创建的模板类型。 在这种情况下，请选择"**扩展 Microsoft 模板"，** 然后选择"**选择 Microsoft 模板"。**

3. 模板选择飞出窗格显示在屏幕的右侧，其中显示所有模板的列表及其活动状态或非活动状态。 激活 **的模板** 计数器显示当前使用的模板数，该数量与可供使用的模板总数之比。 如果超过限制，消息栏将发出通知。

4. 模板选择飞出窗格显示在屏幕的右侧。 使用 **搜索** 应用筛选器以查找您想要的模板

5. 找到模板后，选择其名称左侧的单选按钮，然后选择"保存 **"。**

6. 下一个屏幕将显示所选的模板。 如果正确，请选择"下一 **步"。**  (如果不正确，请选择" **选择其他模板** "以再次选择。) 

7. 在 **"Upload文件**"屏幕上，选择"浏览"查找并上载包含所有所需Excel模板数据的格式化文件。

8. 如果文件没有问题，下一个屏幕将显示已上传文件的名称。 如果需要 **更改** (，请选择"下一步"以继续Upload **文件) 。**

    - 如果文件有问题，顶部会显示一条错误消息，说明错误所在。 你需要修复并重新上传文件。 如果电子表格的格式不正确，或者某些字段中的信息无效，则会导致错误。

9. " **审阅和完成"** 屏幕显示改进操作和控件的数量以及模板的最大分数。 准备好批准后，选择"下一 **步"。**  (如果需要进行更改，请选择Upload **文件 .)**

10. 最后一个屏幕确认已创建一个新模板。 选择 **"完成** "退出向导。

11. 你将到达新模板的详细信息页面。 从此处，可以通过选择创建评估 **来创建评估**。 有关指导，请参阅 [生成和管理评估](compliance-manager-assessments.md#create-assessments)。

## <a name="extend-universal-assessment-templates"></a>扩展通用评估模板

还可以扩展模板的通用版本以自定义特定于产品的评估。 在使用通用模板创建评估且评估具有独特的产品和认证组合时，你将收到一个特殊的扩展模板。 可以修改此文件以满足你的需求。 有关如何编辑模板的指南，请参阅有关修改 [模板的说明](compliance-manager-templates-modify.md)。

编辑通用模板时，可更改模板中所有的内容，但这样做会中断与父模板的继承关系。 这意味着，如果刷新父模板，它将不再自动接收来自 Microsoft 的更新。
