---
title: '文档理解和表单处理模型之间的差异 (预览) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 描述文档理解和表单处理模型之间的关键差异。
ms.openlocfilehash: ceea3a6e7898d8971ea458222d6164b496fcb8b7
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950056"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a>文档理解和表单处理模型之间的差异 (预览) 

> [!Note] 
> 本文中的内容适用于 Project Cortex 私人预览。 了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。

通过项目 Cortex 中的内容理解，可以识别和分类上载到 SharePoint 文档库的文档，以及提取每个文件中的相关信息。  例如，在将文件上载到 SharePoint 文档库时，标识为 *采购订单* 的所有文件都将按此方式分类，并显示在显示它们的自定义文档库视图中。 此外，还可以从每个文件中提取特定信息 (例如， *PO 编号* 和 *总计*) 并将其显示在文档库视图中的列中。 


内容理解使您能够创建 *模型* 以标识和提取所需的信息。  可以使用以下两种类型的模型：

- [文档理解模型](document-understanding-overview.md)
- [表单处理模型](form-processing-overview.md)

虽然这两种模型通常用于相同目的，但有一些主要差异会影响您可能选择使用哪一种模型。


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>结构化与非结构化和半结构化内容

使用文档理解模型标识并提取非结构化文档（如信函或合同）中的数据，其中要提取的文本实体位于文档的句子或特定区域中。 例如，非结构化文档可以是以不同方式编写的合同续订信函。 但是，每个合同续订文档的正文中都存在一致的信息，例如文本字符串 "服务开始日期"，后跟实际日期。   

使用表单处理模型来标识文件，并从结构化或半结构化文档（如窗体或发票）中提取数据，其中包含清楚的键值 (对，例如， *日期： 10/1/2020*) * 或表数据。 例如，表单处理的一个好候选人是公司的订单请求表单，客户端需要为位于文档布局相同区域（如 *姓名*、 *电话号码*、 *总成本*等）中的特定字段提供信息。 "税种" 表单是结构化文档的一个很有用的示例。 

## <a name="where-they-are-created"></a>创建位置

文档理解模型是在 SharePoint 内容中心网站中创建和管理的。 您必须具有对内容中心网站的访问权限，才能创建文档理解模型或将其应用到 SharePoint 文档库。 

创建文档理解模型时，将创建一个新的 [sharepoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) ，该类型将保存到 Sharepoint 内容类型库中。 如果需要，您可以选择使用现有内容类型来定义模型。

表单处理模型在 PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)中创建，但创建是直接从 SharePoint 文档库启动的。 需要在文档库中启用表单处理模型创建，以便用户为其创建表单处理模型，并且管理员可以在内容理解管理设置中执行此操作。 表单处理模型使用 PowerAutomate 流在文件上传到文档库时处理文件。

表单处理模型还会创建新的 [sharepoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，这些类型也存储在 Sharepoint 内容类型库中。

## <a name="where-they-can-be-applied"></a>可以在何处应用它们

文档理解模型可应用于您有权访问的不同 SharePoint 文档库。 您可以使用内容中心不仅创建文档理解模型，还可以将其应用于不同的文档库。 内容中心提供了对文档理解模型的使用方式和应用位置的更大的集中控制，因为此信息必须汇总到内容中心。

表单处理模型目前只能应用于从中创建它们的 SharePoint 文档库。 这将允许任何有权访问该网站的授权用户创建表单处理模型。




 ## <a name="see-also"></a>另请参阅
[培训：使用 AI 生成器改进业务绩效](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[创建类元](create-a-classifier.md)</br>
[创建提取程序](create-an-extractor.md)</br>
[应用文档理解模型](apply-a-model.md)</br>
[创建表单处理模型](create-a-form-processing-model.md)</br>



  
  



