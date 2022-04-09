---
title: 使用预生成模型从 Microsoft SharePoint Syntex 中的发票或收据中提取信息
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: 了解如何在SharePoint Syntex中创建和配置预生成模型。
ms.openlocfilehash: f3b262ca94e0bfc6886a2ce84ae614569c584bf1
ms.sourcegitcommit: 46e796c6b76a01516c48977335bbf5076ca74a06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64738428"
---
# <a name="use-a-prebuilt-model-to-extract-info-from-invoices-or-receipts-in-microsoft-sharepoint-syntex"></a>使用预生成模型从 Microsoft SharePoint Syntex 中的发票或收据中提取信息

预生成模型经过预训练以识别文档中的文档和结构化信息。 无需从头开始创建新的自定义模型，而是可以循环访问现有的预训练模型，以添加符合组织需求的特定字段。 

目前，有两个预生成模型可用：发票和收据。

- *发票预生成模型* 分析并提取销售发票中的关键信息。 API 以各种格式分析发票，并 [提取关键发票信息](/azure/applied-ai-services/form-recognizer/concept-invoice#field-extraction) ，例如客户姓名、计费地址、截止日期和到期金额。

- *回执预生成模型* 分析并提取销售收据中的关键信息。 API 分析印刷的收据和手写收据，并提取商家姓名、商家电话号码、交易日期、税务和事务总计等 [关键收据信息](/azure/applied-ai-services/form-recognizer/concept-receipt#field-extraction) 。

将来的版本中将提供其他预生成模型。

## <a name="create-a-prebuilt-model"></a>创建预生成模型

按照以下步骤创建预生成模型，以对SharePoint Syntex中的文档进行分类。

1. 在 **“模型** ”页中，选择 **“创建模型**”。

    ![显示“创建模型”按钮的“模型”页的屏幕截图。](../media/content-understanding/prebuilt-create-model-button.png) 

2. 在 **“创建模型** ”面板的 **“名称”** 字段中，键入模型的名称。

    ![“新建文档理解模型”面板的屏幕截图，其中显示了可用的模型类型。](../media/content-understanding/prebuilt-create-panel.png) 

3. 在“ **模型类型** ”部分中，选择一个预生成的模型：
   - **发票处理预生成**
   - **预生成的收据处理**

   如果要创建传统的、未经训练的文档理解模型而不是预生成的模型，请选择 **“自定义文档理解**”。

4. 如果要更改内容类型或添加保留标签，请选择 **“高级设置**”。

    > [!NOTE]
    > 敏感度标签目前不适用于预生成模型。

5. 选择“**创建**”。 模型将保存在 **模型** 库中。

## <a name="add-a-file-to-analyze"></a>添加要分析的文件

1. 在 **“模型** ”页上的 **“添加要分析的文件** ”部分中，选择 **“添加文件**”。

    ![新模型页的屏幕截图，其中显示了“添加要分析的文件”部分。](../media/content-understanding/prebuilt-add-file-to-analyze.png) 

2. 在 **“文件”中，选择** “ **添加** ”以查找要使用的文件。

    ![用于分析显示“添加”按钮的模型页的文件屏幕截图。](../media/content-understanding/prebuilt-add-file-button.png) 

3. 在 **训练文件库页的“添加文件** ”页上，选择该文件，然后选择 **“添加**”。

    ![“从训练文件库页添加文件”的屏幕截图。](../media/content-understanding/prebuilt-add-file-from-training-library.png) 

6. 在 **要分析模型页的文件上** ，选择 **“下一步**”。

## <a name="select-extractors-for-your-model"></a>为模型选择提取器

在提取器详细信息页上，你将看到右侧的文档区域和左侧的 **提取器** 面板。 **提取器** 面板显示已在文档中标识的提取程序的列表。

   ![提取器详细信息页和提取器面板的屏幕截图。](../media/content-understanding/prebuilt-extractor-details-page.png) 

文档区域中以绿色突出显示的实体字段是模型在分析文件时检测到的项。 选择要提取的实体时，突出显示的字段将更改为蓝色。 如果以后决定不包含实体，突出显示的字段将更改为灰色。 通过突出显示，可以更轻松地查看所选提取器的当前状态。

> [!TIP]
> 可以使用鼠标上的滚轮或文档区域底部的控件根据需要放大或缩小以读取实体字段。

### <a name="select-an-extractor-entity"></a>选择提取器实体

可以从文档区域或 **提取器** 面板中选择提取器，具体取决于首选项。
 
- 若要从文档区域中选择提取器，请选择实体字段。

    ![显示如何选择实体字段的文档区域的屏幕截图。](../media/content-understanding/prebuilt-document-area-select-field.png) 

- 若要从 **提取器** 面板中选择提取器，请选中实体名称右侧的复选框。

    ![“提取器”面板的屏幕截图，其中显示了如何选择实体字段。](../media/content-understanding/prebuilt-extractors-panel-select-field.png) 

选择提取器时，文档区域中会显示一个 **“选择提取器？”** 框。 该框显示提取器名称、原始值以及将其选作提取器的选项。 对于某些数据类型（如数字或日期），它还会显示提取的值。

   ![提取器详细信息页上“选择提取器”框的屏幕截图。](../media/content-understanding/prebuilt-select-distractor-box.png) 

原始值是文档中的实际值。 提取的值将写入SharePoint中的列中。 将模型应用到库时，可以使用列格式来指定希望它在文档中的外观。

继续选择要使用的其他提取器。 还可以添加用于分析此模型配置的其他文件。

## <a name="rename-an-extractor"></a>重命名提取器

可以从模型主页或提取器面板重命名提取 **器** 。 你可能会考虑重命名选定的提取器，因为当模型应用于库时，这些名称将用作列名称。

若要从模型主页重命名提取器，请执行以下操作：

1. 在 **“提取器”** 部分中，选择要重命名的提取器，然后选择 **“重命名**”。

    ![“提取器”部分的屏幕截图，其中突出显示了“重命名”选项。](../media/content-understanding/prebuilt-model-page-rename-extractor.png) 

2. 在 **“重命名实体提取器** ”面板上，输入提取器的新名称，然后选择 **“重命名**”。

若要从提取器面板重命名 **提取** 器，请执行以下操作：

1. 选择要重命名的提取器，然后选择 **“重命名**”。

    ![“提取器”面板的屏幕截图，其中显示了如何重命名提取器。](../media/content-understanding/prebuilt-extractors-panel-rename-field.png) 

2. 在 **“重命名”提取器** 框中，输入提取器的新名称，然后选择 **“重命名**”。

## <a name="apply-the-model"></a>应用模型

- 若要保存更改并返回到模型主页，请在 **“提取器** ”面板上选择 **“保存”并退出**。

- 如果已准备好将模型应用到库，请在文档区域中选择 **“下一步**”。 在 **“添加到库** ”面板上，选择要向其添加模型的库，然后选择 **“添加**”。

## <a name="change-the-view-in-a-document-library"></a>更改文档库中的视图

[!INCLUDE [Change the view in a document library](../includes/change-library-view.md)]

