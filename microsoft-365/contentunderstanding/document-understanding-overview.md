---
title: 文档理解概述
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 获取 Microsoft SharePoint Syntex 中的文档理解概述。
ms.openlocfilehash: c0396c8e702d3e32db93d26dba23ab038546bea0
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976515"
---
# <a name="document-understanding-overview"></a>文档理解概述


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

文档理解使用人工智能 (AI) 模型自动对文件和提取信息进行分类。 它最适用于非结构化文档，例如字母或协定。 这些文档必须包含可以根据短语或图案进行识别的文本。 标识的文本将指定文件类型（分类）和要提取的内容（提取程序）。

> [!NOTE]
> 有关文档理解方案示例的详细信息，请参阅 [SharePoint Syntex 采用：入门指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example)。

文档理解模型在一种称为 *内容中心* 的 SharePoint 网站中创建和管理。 应用于 SharePoint 文档库时，该模型与内容类型关联，包含用于存储所提取信息的列。 你创建的内容类型存储在 SharePoint 内容类型库中。 也可以选择使用现有内容类型来使用其架构。

> [!NOTE]
> 只读或密封的内容类型无法更新，因此不能在模型中使用。

向文档理解模型添加 *分类器* 和 *提取器* 以执行以下操作： 

- 分类器用于识别上载到文档库的文档并对其进行分类。 例如，一个分类器可通过“训练有素”来标识上载到库的所有 *合同续订* 文档。 当你创建分类器时，合同续订内容类型由你定义。

- 提取器从这些文档提取信息。 例如，对于文档库中标识的所有合同续订文档，将在视图中显示每个合同续订文档的 *服务开始日期* 和 *客户*。 

可使用示例文件在模型中培训并测试分类器和提取器。 示例文件提供了有关尝试从文件识别和提取数据时要查找的内容的模型示例。 例如，你将使用公司使用的合同续订文档的示例来训练你的合同续订分类和提取器。 还可以使用示例文件来测试模型的有效性。

> [!NOTE]
> 如果您使用光学字符识别（OCR）技术扫描文档，则Syntex的模型训练限制为15页。

发布模型后，请使用内容中心将其应用到你有权访问的任何 SharePoint 文档库。  

## <a name="see-also"></a>另请参阅
[创建分类器](create-a-classifier.md)

[创建提取程序](create-an-extractor.md)

[创建内容中心](create-a-content-center.md)

[创建表单处理模型](create-a-form-processing-model.md)

[应用模型](apply-a-model.md)   

[文档理解与表单处理模型之间的差异](difference-between-document-understanding-and-form-processing-model.md)
  
[表单处理概述](form-processing-overview.md)
