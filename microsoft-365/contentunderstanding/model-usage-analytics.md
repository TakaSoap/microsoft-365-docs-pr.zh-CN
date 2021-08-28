---
title: Microsoft SharePoint Syntex 中的文档理解模型使用情况分析
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
localization_priority: Priority
description: 了解如何查找和使用文档理解模型的使用情况分析。
ms.openlocfilehash: d39b2417a90716200d33831bfef7e9cb2ff1d523
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58574035"
---
# <a name="document-understanding-model-usage-analytics-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex 中的文档理解模型使用情况分析

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhX]  

</br>


SharePoint Syntex 内容中心可提供模型使用情况分析，即提供有关如何使用内容中心中已发布的模型的详细信息。 内容中心的<b>模型最近 30 天的运行情况</b>部分包括以下图表和列表中提供的 30 天使用情况分析数据汇总：

- 按模型分类
- 按库分类
- 模型使用情况 

 ![模型分析。](../media/content-understanding/model-analytics.png) </br>

### <a name="roll-up-of-model-usage-data-in-the-default-content-center"></a>在默认内容中心汇总模型使用数据

在 SharePoint Syntex 中，在设置过程中创建默认内容中心。 也可以根据需要创建其他内容中心。 例如，部门可创建自己的内容中心来创建和管理其模型。 

对于模型使用情况分析，请注意：

- 默认内容中心将显示组织内所有内容中心和模型的模型使用情况分析，包括在其他内容中心中创建的模型。 这为内容管理者和其他利益干系人提供了一个集中式门户，用于管理和监督整个公司的内容中心和模型。  
- 其他内容中心将仅显示在其中创建的模型的模型使用情况分析。 这使内容管理员可以仅深入了解所关注模型的使用情况数据。


## <a name="classification-by-model"></a>按模型分类

   ![总模型百分比。](../media/content-understanding/total-model-percentage.png) </br>

**按模型分类** 饼图显示已对大多数文件进行分类的模型。 它将每个已发布模型显示为内容中心中所有已发布模型处理的总文件的百分比。

每个模型还显示 **完整率**，即由模型成功分析的已上传文件的百分比。 完整率低可能意味着模型或正在分析的文件存在问题。

## <a name="classification-by-library"></a>按库分类

   ![已处理文件。](../media/content-understanding/files-processed-over-time.png) </br>

**按库分类** 条形图可帮助确定组织中内容理解的有效性。  条形图不仅显示每个模型一段时间内处理的文件数，通过选择图标中的列，还会显示应用模型的文档库。


## <a name="model-usage"></a>模型使用情况

“模型使用情况”列表将显示通过内容中心创建的模型的使用情况分析。  

> [!NOTE]
> 如果你位于默认资源中心，并且组织中有其他资源中心，则模型使用情况列表将按资源中心分组。

模型使用情况列表中的每个模型都将显示使用情况数据：

- 已分类项目计数：模型处理的文件数。
- 平均置信度分数：对文件运行模型的平均准确度分数。
- 目标列表 URL：应用模型的 SharePoint 文档库。



## <a name="see-also"></a>另请参阅
[创建分类器](create-a-classifier.md)

[创建提取程序](create-an-extractor.md)

[文档理解概述](document-understanding-overview.md)

[创建表单处理模型](create-a-form-processing-model.md)  
