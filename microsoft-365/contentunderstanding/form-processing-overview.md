---
title: 表单处理概述
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 了解 Microsoft SharePoint Syntex 中的表单处理
ms.openlocfilehash: 9b5b9b1c54220037e1c10f2722a641b526592f84
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338609"
---
# <a name="form-processing-overview"></a>表单处理概述

 ![AI 生成器](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex 使用 Microsoft PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)表单处理在 SharePoint 文档库中创建模型。

可使用 AI 生成器表单处理创建使用机器学习技术标识和提取结构化或半结构化文档（如表单和发票）中的键值对和表格数据的 AI 模型。

组织通常从多种来源（如邮件、传真、电子邮件等）接收大量发票。处理这些文档并手动将其输入到数据库中可能需要花费大量时间。 通过使用 AI 提取文档中的文本、键/值对和表格，表单处理可自动执行此过程。 

> [!NOTE]
> 有关表单处理方案示例的详细信息，请参阅 [SharePoint Syntex 采用：入门指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)。

例如，可以创建一个表单处理模型来标识上传到文档库的所有采购订单文档。 可从每个采购订单提取并显示对你非常重要的特定数据，如 *PO 编号*、 *日期*或*总成本*。

![文档库视图](../media/content-understanding/doc-lib-done.png)</br>  

你也可以使用示例文件来训练模型，并定义将从表单提取的信息。 通过训练模型来学习文档的布局，它将学习如何从表单中的类似位置提取数据，因为它们具有类似的结构化布局。 

至少需要 5 个表单文档才能开始操作。 AI 构建分析示例文件中的键 - 值对，然后手动识别可能没有检测到的键 - 值对。  可通过 AI 生成器测试示例文件的模型准确性。

训练和发布模型后，使用它来创建将文件上传到 SharePoint 文档库后运行的 [Power Automate 流程](https://docs.microsoft.com/power-automate/getting-started)。 然后提取模型中标识的数据。 提取的数据将显示在模型的文档库视图的列中。

你可以使用示例文件来训练模型，并定义将从表单提取的信息。 文档的布局通过培训你的模型获知。 只需 5 个表单文档即可开始操作。 AI 生成器将分析示例文件中的键 - 值对，你也可以手动识别可能没有检测到的键 - 值对。  可通过 AI 生成器测试示例文件的模型准确性。

训练并发布模型后，模型将创建 [Power Automate 流程](https://docs.microsoft.com/power-automate/getting-started)。 将文件上传到 SharePoint 文档库时将运行该流程，并提取模型中标识的数据。 提取的数据将显示在模型的文档库视图的列中。

Office 365 管理员需要为 SharePoint 文档库[启用表单处理](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) ，以便用户能够从中 [创建表单处理模型](create-a-form-processing-model.md)。 设置过程中或设置完成后，可在管理设置中选择网站。



## <a name="see-also"></a>另请参阅
  
[Power Automate 流程](https://docs.microsoft.com/power-automate/)

[创建表单处理模型](create-a-form-processing-model.md)

[文档理解概述](document-understanding-overview.md)

[培训：使用 AI 生成器提高业务绩效](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
