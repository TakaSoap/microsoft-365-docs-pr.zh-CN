---
title: 步骤 1. 使用 SharePoint Syntex 标识协定文件并提取数据
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何使用 SharePoint Syntex 来识别合约文件，并使用 Microsoft 365 提取数据。
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281088"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>步骤 1. 使用 SharePoint Syntex 标识协定文件并提取数据

贵组织需要一种方法从您收到的许多文件中标识所有合同文档并对这些文档进行分类。 您还需要能够快速查看每个识别为 (合同文件中的几个关键元素，例如，Client、Contract 和 Fee  *amount*) 。  为此，可以使用[Syntex](index.md) SharePoint文档理解模型，并应用到文档库。

[文档理解](document-understanding-overview.md) 使用人工智能 (AI) 模型来自动分类文件和提取信息。 从非结构化和半结构化文档提取信息时，文档理解模型也是最佳选择，其中您需要的信息未包含在表或表单（如合同）中。

1. 首先，您需要查找至少五个示例文件，您可以使用这些文件对模型进行"训练"，以搜索特定于您尝试识别合同内容类型 (的特征) 。 

2. 使用 SharePoint Syntex，创建新的文档理解模型。 使用示例文件，需要 [创建分类器](create-a-classifier.md)。 通过使用示例文件对分类器进行培训，可以指导它搜索特定于公司合同内容的特征。 例如，[创建一个"说明"，](create-a-classifier.md#create-an-explanation)搜索您的合同（如服务协议、协议条款和补偿）中的特定 *字符串*。  甚至可以对说明进行培训，以在文档的特定节中查找这些字符串，或查找位于其他字符串旁边的字符串。 如果您认为已使用分类器所需的信息对分类器进行培训，您可以对示例文件集测试模型，以查看其效率。 测试后，如果需要，可以选择更改说明，使其更高效。 

3. 在你的模型中，可以创建 [提取程序](create-an-extractor.md) 以从每个合约中提取特定部分的数据。 例如，对于每个合同，您最关心的信息是客户是谁、承包商的名称和总成本。

4. 成功创建模型后，[请应用于SharePoint库](apply-a-model.md)。 当您将文档上载到文档库时，您的文档理解模型将运行，并识别与模型中定义的合同内容类型匹配的所有文件，并对这些文件进行分类。 归类为合同的所有文件都将在自定义库视图中显示。 这些文件还将显示在提取程序中定义的每个合约的值。

   ![文档库中的协定](../media/content-understanding/doc-lib-solution.png)

5. 此外，如果您有合同保留要求，您还可以使用模型应用保留标签，以防止在指定的时段内[](apply-a-retention-label-to-a-model.md)删除合同。

## <a name="next-step"></a>后续步骤

[步骤 2.使用Microsoft Teams创建合同管理通道](solution-manage-contracts-step2.md)