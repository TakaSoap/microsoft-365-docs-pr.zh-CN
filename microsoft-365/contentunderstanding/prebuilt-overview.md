---
title: Microsoft SharePoint Syntex 中的预SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.customer: intro-overview
ms.prod: microsoft-365-enterprise
search.appverid: null
ms.collection:
  - enabler-strategic
  - m365initiative-syntex
ms.localizationpriority: medium
description: 了解 Microsoft SharePoint Syntex 中的预SharePoint Syntex。
---

# <a name="prebuilt-models-overview-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex 中的预SharePoint Syntex

除了文档[了解模型和](document-understanding-overview.md)[表单处理模型](form-processing-overview.md)之外，SharePoint Syntex还提供预构建的模型以自动提取信息。

预构建的模型经过预约束，可识别文档中的文档和结构化信息。 无需从头开始创建新的自定义模型，您可以对现有预约束模型进行访问，以添加满足组织需求的特定字段。 

预内置模型使用光学字符识别 (OCR) 结合深度学习模型来标识和提取特定文档类型通用的预定义文本和数据字段。 首先，根据预内置模型分析其中一个文件。 然后，选择适合您用途的检测到的字段。 如果模型未检测到所需的字段，可以使用其他文件再次分析。

与文档理解模型一样，在内容中心创建和管理预创建的 [模型](create-a-content-center.md)。 应用于文档SharePoint时，模型与内容类型相关联，并且具有用于存储所提取信息的列。 

发布模型后，请使用内容中心将其应用到你有权访问的任何 SharePoint 文档库。  

## <a name="requirements"></a>要求

- 支持的文件格式：JPEG、PNG、BMP、TIFF 和 PDF (嵌入或扫描的文本) 。

- 嵌入文本的 PDF 最好消除字符提取和位置错误的可能性。

- 对于 PDF 和 TIFF，最多可以处理 2，000 个页面。

- 文件大小必须小于 50 MB。

- 图像尺寸必须介于 50 x 50 像素和 10，000 x 10，000 像素之间。

- PDF 尺寸最多为 17 x 17 英寸，对应于法律或 A3 纸张大小或更小。

- 培训数据的总大小为 500 页或更少。

### <a name="file-limitations"></a>文件限制

请注意基于文本的文件Microsoft Office OCR 扫描的文件 (PDF、图像或 TIFF 文件) ：

- Office：在针对文档库中的文件运行时， (截断 64，000 个字符) 。

- OCR 扫描的文件：存在 20 个页面限制。  

## <a name="model-considerations"></a>模型注意事项

- 如果将两个或多个预内置模型应用于同一个库，则使用具有最高平均可信度分数的模型对文件进行分类。 提取的实体将仅来自应用模型。

- 如果将预内置模型应用于具有文档理解模型的库，则使用文档理解模型和该模型的任何经过训练的提取程序对文件进行分类。 如果存在与预内置模型匹配的任何空列，则使用这些提取的值填充这些列。

- 如果将预构建的模型应用于具有自定义表单处理模型的库，则使用预构建的模型和该模型的任何检测到的提取程序对文件进行分类。 如果存在与表单处理模型匹配的任何空列，则使用这些提取的值填充这些列。

- 不支持将多个自定义表单处理模型应用到库。


## <a name="see-also"></a>另请参阅

[使用预想的模型从发票或收据中提取信息](prebuilt-overview.md)
 

