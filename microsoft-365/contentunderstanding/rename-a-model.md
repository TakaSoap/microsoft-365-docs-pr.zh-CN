---
title: 在 Microsoft SharePoint Syntex 中重命名模型
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
description: 学习如何以及为什么在 Microsoft SharePoint Syntex 中重命名模型。
ms.openlocfilehash: e5cf6069e1b417e186563013a9924ebf7f89630c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197445"
---
# <a name="rename-a-model-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中重命名模型

有时，你可能希望重命名文档理解模型。 一个常见示例是，在创建模型初稿时，你可能未对最终名称做过多思考(例如，你可能将模型命名为”AlexWilburModel1“)。 当快完成模型并将其投入使用时，你发现取名为“合同续订”更加恰当，因而你希望重命名模型。  

另一个示例是，你的组织决定使用不同名称引用流程或文档类型。 例如，当你创建好模型并准备应用后，组织可能强制所有“合同”正式被称为“协议”。 如果需要，你可以选择将模型从“合同续订”重命名为“协议续订”。

> [!IMPORTANT]
> 只有在文档理解模型尚未应用于文档库时，才可对其进行重命名。 

重命名模型同时也会重命名与之关联的[内容类型](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)。

## <a name="rename-a-model"></a>重命名模型

请按照以下步骤重命名文档理解模型。

1. 从内容中心中，选择“**模型**”，查看你的模型列表。

2. 在“**模型**”页面，选择希望重命名的模型。

3. 使用功能区或“**显示操作**”按钮(模型名称旁)，选择 **重命名**。 </br>

    ![“模型”页面的屏幕截图显示了所选的模型，其中突出显示了“重命名”选项。](../media/content-understanding/select-model-rename-both.png) </br>

4. 在“**重命名模型**”面板中:

   a. 在“**新名称**”下面，输入希望重命名的模型的新名称。</br>

    ![屏幕截图显示了“重命名”模型面板。](../media/content-understanding/rename-model-panel.png) </br>

   b. (可选)在“**高级设置**”下，选择是否希望关联现有 [内容类型](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)。 如果选择“**使用现有内容类型**”，则将重命名模型，从而匹配所选的内容类型。

5. 选择“**重命名**”。

## <a name="see-also"></a>另请参阅
[创建分类器](create-a-classifier.md)

[创建提取程序](create-an-extractor.md)

[重命名提取程序](rename-an-extractor.md)

[文档理解概述](document-understanding-overview.md)

[说明类型](explanation-types-overview.md)

[应用模型](apply-a-model.md) 
