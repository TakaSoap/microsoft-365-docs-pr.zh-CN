---
title: 在 Microsoft SharePoint Syntex 中重命名提取程序
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
description: 了解如何以及为什么在 Microsoft SharePoint Syntex 中重命名提取程序。
ms.openlocfilehash: 0b5c52e00b287b6f4b41e7c8c3070261bccfda96
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195445"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中重命名提取程序

有时，如果希望用不同的名称引用提取的数据字段，可能需要重命名提取程序。 例如，你的组织决定更改合同文档，并在文档中将“Customer” 称为 “Client”。 如果你正在模型中提取 “Customer” 字段，可以选择将其重命名为 “Client”。

将更新后的模型同步到 SharePoint 文档库时，文档库视图中将显示新的 “Client” 列。 对于过往活动，视图将保留 “Customer” 列，但对于模型处理的所有新文档，将更新新的 “Client” 列。 

> [!IMPORTANT]
>  请确保将更新后的模型同步到之前应用于显示新列名称的文档库。 

## <a name="rename-an-extractor"></a>重命名提取程序

请按照以下步骤重命名实体提取程序。

1. 从内容中心中，选择“**模型**”，查看你的模型列表。

2. 在“**模型**”页面的“**名称**”列中，选择希望为其重命名提取程序的模型。

3. 在“**实体提取程序**”下面，选择希望重命名的提取程序的名称，然后选择“**重命名**”。</br>

    ![实体提取程序部分的屏幕截图显示了所选的提取程序，其中突出显示“重命名”选项。](../media/content-understanding/entity-extractor-rename.png) </br>

4. 在“**重命名提取程序**”面板中:

   a. 在“**名称**”下面，输入提取程序的新名称。</br>

    ![屏幕截图显示了“实体”提取程序面板。](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   b. (可选)在“**高级设置**”下，选择是否希望关联现有站网站栏。

5. 选择“**重命名**”。

## <a name="see-also"></a>另请参阅
[创建提取程序](create-an-extractor.md)

[创建分类器](create-a-classifier.md)

[重命名模型](rename-a-model.md)

[说明类型](explanation-types-overview.md)

[创建提取程序时利用术语库分类](leverage-term-store-taxonomy.md)

[文档理解概述](document-understanding-overview.md)

[应用模型](apply-a-model.md) 
