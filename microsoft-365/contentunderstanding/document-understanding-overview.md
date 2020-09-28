---
title: 文档理解概述
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Microsoft SharePoint Syntex 中的文档理解的概述。
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294756"
---
# <a name="document-understanding-overview"></a>文档理解概述


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

文档理解使用人工智能 (AI) 模型自动对文件和信息提取进行分类。 它最适用于非结构化文档，如信函或合同。 这些文档必须包含可根据短语或模式进行标识的文本。 标识的文本同时指定它 (其分类) 的文件类型，以及要 (其提取程序) 提取的内容。

文档理解模型在一种称为 *内容中心*的 SharePoint 网站中创建和管理。 当应用于 SharePoint 文档库时，模型与内容类型相关联的列用于存储要提取的信息。 您创建的内容类型存储在 SharePoint 内容类型库中。 您还可以选择使用现有内容类型来使用其架构。

向文档中添加 *分类* 器和 *提取程序* 了解模型以执行以下操作： 

- 分类器用于标识和分类上载到文档库的文档。 例如，可以 "训练有素" 分类器来识别上载到库中的所有 *合同续订* 文档。 创建分类器时，将会定义合同续订内容类型。

- 提取程序从这些文档中提取信息。 例如，对于您的文档库中标识的所有合同续订文档，在视图中显示的列也显示了每个合同续订文档的 *服务开始日期* 和  *客户端* 。 

您可以使用示例文件在模型中培训和测试分类器和提取程序。 示例文件提供了在尝试标识文件中的数据并从中提取数据时要查找的内容的模型示例。 例如，您需要使用贵公司使用的合同续订文档的示例来培训合同续订分类和提取程序。 您还可以使用示例文件来测试模型的有效性。

发布模型后，使用内容中心将其应用于您有权访问的任何 SharePoint 文档库。  


## <a name="see-also"></a>另请参阅
[创建类元](create-a-classifier.md)</br>
[创建提取程序](create-an-extractor.md)</br>
[创建内容中心](create-a-content-center.md) 
[创建表单处理模型](create-a-form-processing-model.md)</br>
[应用模型](apply-a-model.md)   
[文档理解与表单处理模型之间的区别](difference-between-document-understanding-and-form-processing-model.md)  
[表单处理概述](form-processing-overview.md)
