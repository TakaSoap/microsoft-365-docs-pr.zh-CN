---
title: Microsoft SharePoint Syntex 中的文档理解概述
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.customer: intro-overview
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: 了解 Microsoft SharePoint Syntex 中的文档理解。
ms.openlocfilehash: c7488fcb44116f030d538b416af1f04b33382519
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507314"
---
# <a name="document-understanding-overview-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex 中的文档理解概述


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

文档理解使用人工智能 (AI) 模型自动对文件和提取信息进行分类。 它最适用于非结构化文档，例如字母或协定。 这些文档必须包含可以根据短语或图案进行识别的文本。 标识的文本将指定文件类型（分类）和要提取的内容（提取程序）。

> [!NOTE]
> 有关文档理解方案示例的详细信息，请参阅 [SharePoint Syntex 采用：入门指南](./adoption-getstarted.md)。

文档理解模型在一种称为 *内容中心* 的 SharePoint 网站中创建和管理。 应用于 SharePoint 文档库时，该模型与内容类型关联，包含用于存储所提取信息的列。 你创建的内容类型存储在 SharePoint 内容类型库中。 也可以选择使用现有内容类型来使用其架构。

> [!NOTE]
> 只读或密封的内容类型无法更新，因此不能在模型中使用。

将 *分类器**和提取器* 添加到文档理解模型中，以执行以下操作： 

- 分类器用于识别上载到文档库的文档并对其进行分类。 例如，一个分类器可通过“训练有素”来标识上载到库的所有 *合同续订* 文档。 当你创建分类器时，合同续订内容类型由你定义。

- 提取器从这些文档提取信息。 例如，对于文档库中标识的每个合同续订文档，将显示显示每个文档的 *服务* 开始日期和 *客户端* 的列。 

可使用示例文件在模型中培训并测试分类器和提取器。 示例文件提供了有关尝试从文件识别和提取数据时要查找的内容的模型示例。 例如，你将使用公司使用的合同续订文档的示例来训练你的合同续订分类和提取器。 还可以使用示例文件来测试模型的有效性。

发布模型后，请使用内容中心将其应用到你有权访问的任何 SharePoint 文档库。  

## <a name="file-limitations"></a>文件限制

文档了解模型使用光学字符识别 (OCR) 技术扫描 PDF、图像和 TIFF 文件。 在使用示例文件训练模型时，以及针对文档库中的文件运行模型时，将扫描文件。

请注意基于文本的文件Microsoft Office OCR 扫描的文件 (PDF、图像或 TIFF 文件) ：

- Office 文件：截断为 64,000 个字符（在培训中以及针对文档库中的文件运行时）。

- OCR 扫描的文件：存在 20 个页面限制。  

### <a name="requirements"></a>要求

OCR 处理最适用于满足下列要求的文档：

- JPG、PNG 或 PDF 格式（文本或扫描）。 最好使用文本嵌入的 PDF，因为字符提取和位置中不会存在任何错误。

- 如果 PDF 是密码锁定的，必须在提交前解除锁定。

- 每个集合用于培训的文档合并文件大小不得超过 50 MB，并且 PDF 文档不能超过 500 页。

- 对于图像，尺寸必须在 50 × 50 到 10,000 × 10,000 像素之间。
   > [!NOTE]
   > 具有非常宽或特殊尺寸（例如平面图）的图像可能在 OCR 过程中截断，并且会失去准确性。
 
- 对于 PDF 文件，尺寸必须为最大 17 x 17 英寸，相当于 Legal 或 A3 纸张大小或更小。

- 如果从纸质文档扫描，则扫描内容应为高质量图像。

- 必须使用拉丁语字母（英文字符）。

> [!NOTE]
> AI 生成器当前不支持以下类型的表单处理输入数据：<br>- 复选框或单选按钮<br>- 签名<br>- 可填充的 PDF

### <a name="supported-file-types"></a>支持的文件类型

了解文档模型支持以下文件类型：

- doc
- docx
- eml
- Heic
- Heif
- htm
- html
- jpeg
- jpg
- markdown
- md
- msg
- pdf
- png
- ppt
- pptx
- rtf
- tif
- tiff
- txt
- xls
- xlsx

### <a name="supported-languages"></a>支持的语言

文档理解模型 *支持所有* 基于拉丁语的语言，包括：

- 英语
- 法语
- 德语
- 意大利语
- 西班牙语


## <a name="see-also"></a>另请参阅
[创建分类器](create-a-classifier.md)

[创建提取程序](create-an-extractor.md)

[创建内容中心](create-a-content-center.md)

[创建表单处理模型](create-a-form-processing-model.md)

[应用模型](apply-a-model.md)   

[文档理解与表单处理模型之间的差异](difference-between-document-understanding-and-form-processing-model.md)
  
[表单处理概述](form-processing-overview.md)

[SharePoint 整合辅助功能模式](accessibility-mode.md)
