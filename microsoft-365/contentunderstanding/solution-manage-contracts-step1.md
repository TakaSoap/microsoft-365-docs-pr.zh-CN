---
title: 步骤 1. 使用SharePoint Syntex标识合同文件并提取数据
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.localizationpriority: medium
ROBOTS: ''
description: 了解如何使用SharePoint Syntex解决方案识别合同文件并提取Microsoft 365数据。
ms.openlocfilehash: c654c72ef36bf86337b7564efc68e4523516f4f9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173507"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>步骤 1. 使用SharePoint Syntex标识合同文件并提取数据

贵组织需要一种方法从您收到的许多文件中标识所有合同文档并对这些文档进行分类。 此外，还希望快速查看每个标识为 (合同文件中的几个关键元素，例如，客户、承包商和费用) 。    为此，可以使用 SharePoint Syntex创建[](index.md)文档理解模型，并应用到文档库。

## <a name="overview-of-the-process"></a>过程概述

[文档理解](document-understanding-overview.md) 使用人工智能 (AI) 模型来自动分类文件和提取信息。 从非结构化和半结构化文档提取信息时，文档理解模型也是最佳选择，其中您需要的信息未包含在表或表单（如合同）中。 

了解模型时，在通过光学字符识别 （OCR） 技术扫描 PDF、图像和 TIFF 文件时，包括当使用示例文件对模型进行训练时，以及针对文档库中的文件运行模型时。

1. 首先，您需要查找至少五个示例文件，这些文件可用于"训练"模型，以搜索特定于您尝试识别合同内容类型 (的特征) 。 

2. 使用SharePoint Syntex，创建新的文档理解模型。 使用示例文件，需要 [创建分类器](create-a-classifier.md)。 通过使用示例文件对分类器进行培训，可以指导它搜索特定于公司合同内容的特征。 例如，[创建一个"解释"，](create-a-classifier.md#create-an-explanation)搜索您的合同（如服务协议、协议条款和补偿）中的特定 *字符串*。  你甚至可以训练你的解释，以在文档的特定部分中查找这些字符串，或者位于其他字符串旁边。 如果您认为已使用分类器所需的信息对分类器进行培训，您可以对示例文件集测试模型，以查看其效率。 测试后，如果需要，可以选择更改说明，使其更高效。 

3. 在你的模型中，可以创建 [提取程序](create-an-extractor.md) 以从每个合约中提取特定部分的数据。 例如，对于每个合同，您最关心的信息是客户是谁、承包商的名称和总成本。

4. 成功创建模型后，[请应用于SharePoint库](apply-a-model.md)。 当您将文档上载到文档库时，您的文档理解模型将运行，并识别与模型中定义的合同内容类型匹配的所有文件，并对这些文件进行分类。 归类为合同的所有文件都将在自定义库视图中显示。 这些文件还将显示在提取程序中定义的每个合约的值。

   ![文档库中的协定。](../media/content-understanding/doc-lib-solution.png)

5. 如果您有合同保留或安全要求，您还可以使用模型应用保留标签或敏感度标签，以防止在指定的时段[](apply-a-retention-label-to-a-model.md)内删除合同或[](apply-a-sensitivity-label-to-a-model.md)限制可以访问合同的人。

## <a name="steps-to-create-and-train-your-model"></a>创建和训练模型的步骤

> [!NOTE]
> 对于这些步骤，您可以使用合同管理解决方案资产存储库中 [的示例文件](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)。 此存储库中的示例包含文档了解模型文件和用于训练模型的文件。

### <a name="create-a-contract-model"></a>创建合同模型

第一步是创建合同模型。

1. 从内容中心中，选择“**新建**”，然后选择“**创建模型**”。

2. 在" **新建文档理解模型** "窗格的" **名称** "字段中，键入模型的名称。 对于此合同管理解决方案，您可以命名模型 *合同*。

4. 选择 **“创建”**。 这将为该模型创建主页。</br>

    ![合同主页的屏幕截图。](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a>培训模型以对文件类型进行分类

#### <a name="add-example-files-for-your-model"></a>为模型添加示例文件

您需要添加至少五个作为合同文档的示例文件，以及一个不是合同文档的示例文件 (例如，工作) 。 

1. 在"**模型>"** 页上的"**关键操作**  >  **""添加示例文件"下**，选择"**添加文件"。**

   ![显示突出显示"添加示例文件"选项的"合同"页面的屏幕截图。](../media/content-understanding/key-actions-add-example-files.png)

2. 在"**为模型选择示例** 文件"页上，打开"合同"文件夹，选择想要使用的文件，然后选择"添加 **"。** 如果没有示例文件，请选择"Upload **添加它们**"。

#### <a name="label-the-files-as-positive-or-negative-examples"></a>将文件标记为正或负示例

1. On the **Models > Contract** page， under Key **actions** Classify files and  >  **run training，** select Train **classifier**.

   ![显示突出显示了"分类文件并运行培训"选项的"合同"页面的屏幕截图。](../media/content-understanding/key-actions-classify-files.png)

2. 在"模型>合同>分类器"页上，第一个示例文件顶部的查看器中，你将看到询问该文件是否就是您创建的合同模型示例的文本。 如果是正例，请选择 **“是”**。 如果是反例，请选择 **“否”**。

3. 从 **左侧的"已** 标记示例"列表中，选择要用作示例的其他文件，然后标记它们。 

    ![分类器主页。](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a>至少添加一个解释来训练分类器 

1. 在&quot; **模型>合同>&quot;页上** ，选择&quot; **训练&quot;** 选项卡。

2. 在 **&quot;训练文件** &quot;部分，你将看到之前标记的示例文件列表。 从列表中选择一个正文件，以在查看器中显示。

3. 在&quot;**说明&quot;** 部分，选择 **&quot;新建&quot;，** 然后选择&quot;**空白&quot;。**

4. 在“**创建说明**”页面上：

    a. 在 **&quot;名称** &quot;字段中，键入说明名称 (&quot;协议") 。

    b. 在" **说明类型"** 字段中，选择" **短语列表**"，因为您添加了文本字符串。

    c. 在" **短语"列表** 框中，键入字符串 ("AGREEMENT") 。 如果字符串 **需要区分** 大小写，可以选择区分大小写。

    d. 选择 **保存并训练**。

    ![创建说明面板的屏幕截图。](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a>测试模型

你可以对之前未看到的示例文件测试合同模型。 这是可选的，但它可能是一种有用的最佳做法。

1. 在" **合同>分类>"** 页上，选择"测试 **"** 选项卡。这将对未标记的示例文件运行模型。

2. 在 **"测试文件** "列表中，示例文件显示并显示模型是否预测它们为正数或负数。 使用此信息以帮助确定分类器在文档识别中的有效性。

    !["文本文件"列表中未标记文件的屏幕截图。](../media/content-understanding/test-on-files.png) 

3. 完成后，选择退出 **培训**。

### <a name="create-and-train-an-extractor"></a>创建和训练提取程序

1. On the **Models > Contract** page， under Key **actions** Create and  >  **train extractors，** select Create **extractor**.

   ![显示突出显示"创建和训练提取程序"选项的"合同"页面的屏幕截图。](../media/content-understanding/key-actions-create-extractors.png)

2. 在" **新建实体提取程序"** 面板的" **新建名称** "字段中，键入提取程序的名称。 例如， *如果要从每个* 合约中提取客户端的名称，则将它取名称为 Client。

3. 完成后，选择创建 **。**

#### <a name="label-the-entity-you-want-to-extract"></a>标记要提取的实体

创建提取程序时，将打开提取程序页。 此时，将看到示例文件的列表，并在查看器中显示列表中的第一个文件。

!["客户端提取程序标记的示例"页的屏幕截图。](../media/content-understanding/client-extractor-labeled-examples.png) 

若要标记实体，

1. 从查看器中，选择要从文件中提取的数据。 例如，如果要提取 *客户端*，请突出显示本示例中第一个文件 ("最适合您有机 *) ，* 然后选择"保存 **"。** 你将看到"标签"列下的"已标记示例"列表中文件 **显示** 的值。

2. 选择 **"下** 一个文件"以自动保存，然后打开查看器列表中的下一个文件。 或选择 **"保存**"，然后从"已 **标记的示例"列表中选择另一** 个文件。

3. 在查看器中，重复步骤 1 和 2，然后重复，直到将标签保存在所有文件中。

标记文件后，将显示通知横幅，通知你移动到培训。 可以选择标记更多文档或继续培训。

#### <a name="add-an-explanation"></a>添加说明

你可以创建一个说明，该说明提供有关实体格式本身及其在示例文件中可能具有的变体的提示。 例如，日期值可能采用许多不同的格式，例如：

- 10/14/2019
- 2019 年 10 月 14 日
- 星期一，2019 年 10 月 14 日

为了帮助确定 *合同开始日期*，可以创建模式说明。

1. 在"**说明"** 部分，选择 **"新建"，** 然后选择"**空白"。**

2. 在“**创建说明**”页面上：

    a. 在 **"名称** "字段中，键入说明的名称 (如 *Date*) 。

    b. 在"**说明类型"** 字段中，选择"**模式列表"。**

    c. 在 **"值** "字段中，提供显示在示例文件中的日期变体。 例如，如果你的日期格式显示为 0/00/0000，则可在文档中输入显示的任何变体，如：

    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000

4. 选择 **保存并训练**。

#### <a name="test-your-model-again"></a>再次测试模型

你可以对之前未看到的示例文件测试合同模型。 这是可选的，但它可能是一种有用的最佳做法。

1. 在" **合同>分类>"** 页上，选择"测试 **"** 选项卡。这将对未标记的示例文件运行模型。

2. 在 **"测试文件** "列表中，示例文件显示并显示模型能否提取您需要的信息。 使用此信息以帮助确定分类器在文档识别中的有效性。

3. 完成后，选择退出 **培训**。

### <a name="apply-your-model-to-a-document-library"></a>将模型应用到文档库

若要将模型应用到SharePoint库：

1. 在"**模型>"** 页上的"关键 **操作**  >  **将模型应用到库"下，** 选择"**应用模型"。**

   ![Screenshot showing the Contracts page with Apply model to libraries option highlighted.](../media/content-understanding/key-actions-apply-model.png)

2. 在 **"添加** 合同"SharePoint，选择包含要应用模型的文档库的网站。 如果该网站未显示在列表中，请使用搜索框进行查找。 选择“**添加**”。

    > [!NOTE]
    > 你必须拥有 *管理列表* 权限，或者 *编辑* 对应用模型的文档库的权限。

3. 选择网站后，选择要应用模型的文档库。

4. 由于模型与内容类型相关联，因此在将模型应用到库时，它将添加内容类型及其视图，其中提取的标签以列显示。 默认情况下，此视图是库的默认视图，但可以选择不作为默认视图，选择"高级设置"并清除"将这个新视图设置为 **默认视图"** 复选框。

5. 选择 **“添加”** 将模型应用到库中。

6. 在 **"模型>合约**"页上的"具有此模型的库"部分，你将看到列出的SharePoint URL。

    ![显示"具有此模型的库"部分合同主页的屏幕截图。](../media/content-understanding/contract-libraries-with-this-model.png)

7. 在 **设置**  >  **库设置下**：

   - 添加名为"状态 **"的** 列并选择 **"选项** "作为列类型。
   - 应用 **In review、Approved** 和 **Rejected** 值。 

将模型应用到文档库后，您可以开始将文档上载到网站并查看结果。

## <a name="next-step"></a>后续步骤

[步骤 2.使用 Microsoft Teams 创建合同管理通道](solution-manage-contracts-step2.md)