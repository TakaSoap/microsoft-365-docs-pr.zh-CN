---
title: 在 Microsoft SharePoint Syntex 中复制模型
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: 学习如何以及为什么在 Microsoft SharePoint Syntex 中复制模型。
ms.openlocfilehash: dc8668ccf407e881bb2114cb679b1ed2049c256e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156434"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中复制模型

如果需要创建新模型，并且明确现有模型与需要的模式非常相似，则复制文档理解模型可以节省时间和精力。

例如，名为“合同”的现有模型对需要使用的相同文件进行分类。 新模型将提取一些现有数据，但需要进行更新，以便提取额外数据。 不必从头开始创建和培训新模型，你可以使用复制模型功能创建“合同”模型的副本，这同时会复制所有关联的培训项目，例如示例文件和实体提取器。

复制模型时，在重命名之后(例如，重命名为“合同续订”)就可进行更新。 例如，可以选择删除一些不需要的现有提取字段，然后训练模型提取新的字段(例如“续订日期”)。

## <a name="duplicate-a-model"></a>复制模型

请按照以下步骤复制文档理解模型。

1. 从内容中心中，选择“**模型**”，查看你的模型列表。

2. 在“**模型**”页面，选择希望复制的模型。

3. 使用功能区或“**显示操作**”按钮(模型名称旁)，选择 **复制**。</br>

    ![“模型”页面的屏幕截图显示了所选模型，其中突出显示“重复”选项。](../media/content-understanding/select-model-duplicate-both.png) </br>

4. 在“**复制模型**”面板上:

   a. 在“**名称**”下面，输入希望复制的模型的新名称。</br>

    ![屏幕截图显示了“复制”模型面板。](../media/content-understanding/duplicate-model-panel.png) </br>

   b. 在“**描述**”下，添加新模型的说明。

   c. (可选)在“**高级设置**”下，选择是否希望关联现有 [内容类型](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)。

5. 选择“**复制**”。

## <a name="see-also"></a>另请参阅
[创建分类器](create-a-classifier.md)

[重命名模型](rename-a-model.md)

[创建提取程序](create-an-extractor.md)

[文档理解概述](document-understanding-overview.md)

[说明类型](explanation-types-overview.md)

[应用模型](apply-a-model.md) 

[SharePoint 整合辅助功能模式](accessibility-mode.md)