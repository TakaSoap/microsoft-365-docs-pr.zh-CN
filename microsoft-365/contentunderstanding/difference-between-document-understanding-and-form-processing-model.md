---
title: 文档理解与表单处理模型之间的差异
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
description: 描述文档理解与表单处理模型之间的主要差异
ms.openlocfilehash: f57d220eb77a783de5ac352f3cf684364252a163
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975873"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>文档理解与表单处理模型之间的差异 


通过 Microsoft SharePoint Syntex 中的内容理解功能，你可以识别上传到 SharePoint 文档库的文档、对其进行分类并从每个文件中提取相关信息。  例如，当文件上传到 SharePoint 文档库中时，所有被识别为 *采购订单* 的文件都被归类为采购订单，然后在自定义文档库视图中显示。 此外，可从每个文件中提取特定信息（例如， *PO 编号* 和 *总数*），并将其显示为文档库视图中的一列。 

内容理解使你能够创建 *模型* 来识别和提取所需的信息。 模型在帮助解决搜索、业务流程、合规性等业务问题上具有价值。

有两种模型类型可以使用：

- [文档理解模型 ](document-understanding-overview.md)
- [表单处理模型](form-processing-overview.md)

虽然这两种模型通常用于相同的用途，但下面列出的主要差异会影响你使用的区别。

> [!NOTE]
> 有关表单处理和文档理解方案示例的详细信息，请参阅 [SharePoint Syntex 采纳：入门指南](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)。


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>结构化内容与非结构化和半结构化内容的比较

使用文档理解模型从信件或合同等非结构化文档中识别和提取数据，在这些文档中，所需提取的文本实体位于文档的句子或特定区域中。 例如，一个非结构化的文件可以是一份可以用不同的方式来写的续签合同书。 然而，每份合同续签文档的正文中都有一致的信息，例如 *服务开始日期* 的文本字符串，后是实际日期。

使用表单处理模型来识别文件，并从结构化或半结构化的文件（如表单或发票）中提取数据。 表单处理模型将通过示例文档来进行训练，从而了解表单的布局，并学会从相似的位置查找需要提取的数据。 表单通常具有结构化程度更高的布局，其中的实体均位于同一位置（例如，纳税表单中的社会保险号）。

> [!NOTE]
> 必须有访问内容中心站点的权限，才能创建文档理解模型或将其应用于SharePoint文档库。 


## <a name="where-models-are-created"></a>模型创建位置

文档理解模型在 SharePoint 内容中心站点中创建和管理。 

> [!NOTE]
> 有关输入文档的详细信息，请参阅 [表单处理模型的要求和限制](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)。 

表单处理模型在 PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)中创建而成，但创建活动是直接从 SharePoint 文档库开始的。 文档库必须启用表单处理模型创建，用户才能为其创建表单处理模型。 管理员可以在内容理解管理员设置中启用表单处理模型创建。 当文件上传到文档库时，表格处理模型会使用 PowerAutomate 流来处理文件。

创建文档理解模型时，将创建一个新的 [SharePoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) 保存到 SharePoint 内容类型库中。 或者如果需要的话，可使用现有的内容类型来定义模型。

表单处理模型还可创建新 [SharePoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，并且还存储在 SharePoint 内容类型库中。

## <a name="where-they-can-be-applied"></a>可适用的地方

可将文档理解模型应用于有权访问的 SharePoint 文档库中。 使用内容中心创建文档理解模型，并将其应用于不同的文档库。 内容中心可以让你更集中地控制文档理解模型的使用方式和应用位置。 注意，这些信息也必须滚动到内容中心。

表单处理模型目前只能应用于创建它们的 SharePoint 文档库。 这使得拥有网站访问权限的许可用户能够创建表单处理模型。 请注意，管理员需要在 SharePoint 文档库中启用表单处理功能，以便供许可用户使用。

 ## <a name="see-also"></a>另请参阅
[培训：使用 AI 生成器提高业务绩效](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[文档理解概述](document-understanding-overview.md)

[表单处理概述](form-processing-overview.md)

[SharePoint Syntex 简介](index.md)
