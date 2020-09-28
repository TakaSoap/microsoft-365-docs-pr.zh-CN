---
title: 文档理解和表单处理模型之间的区别
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 介绍文档理解和表单处理模型之间的关键区别
ms.openlocfilehash: 268a2fa4a0381e5822c17e5df22566c931d37f3c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294744"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>文档理解和表单处理模型之间的区别 

本文中的内容适用于 Project Cortex 私人预览。 了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。

通过项目 Cortex 中的内容理解，可以识别和分类上载到 SharePoint 文档库的文档，以及提取每个文件中的相关信息。  例如，在将文件上载到 SharePoint 文档库时，标识为 *采购订单* 的所有文件都按此进行分类，然后显示在自定义文档库视图中。 此外，还可以从每个文件中提取特定信息 (例如， *PO 号* 和 *总计*) 并将其显示为文档库视图中的一列。 

内容理解使您能够创建 *模型* 以标识和提取所需的信息。 以下是您可以使用的两种模型类型：

- [文档理解模型](document-understanding-overview.md)
- [表单处理模型](form-processing-overview.md)

虽然这两种模型通常用于相同目的，但下面列出的主要区别将影响您可以使用的主要区别。

## <a name="structured-versus-unstructured-and-semi-structured-content"></a>结构化与非结构化和半结构化内容

使用文档理解模型标识并提取非结构化文档（如信函或合同）中的数据，其中要提取的文本实体位于文档的句子或特定区域中。 例如，非结构化文档可以是以不同方式编写的合同续订信函。 但是，信息在每个合同续订文档的正文中始终存在，如文本字符串 "服务开始日期"，后跟实际日期。   

使用表单处理模型来标识文件，并从结构化或半结构化文档（例如表单或发票）中提取数据。 这些文档必须具有明文键值对 (例如， *Date： 10/1/2020*) * 或 table data。 例如，表单处理的一个好候选人是公司订单请求表单，客户端需要为位于文档布局相同区域（如 *姓名*、 *电话号码*、 *总成本*等）中的特定字段提供信息。 "税种" 表单是结构化文档的一个很有用的示例。 

## <a name="where-they-are-created"></a>创建位置

文档理解模型是在 SharePoint 内容中心网站中创建和管理的。 

> [!NOTE]
> 您必须具有对内容中心网站的访问权限，才能创建文档理解模型或将其应用到 SharePoint 文档库。 

表单处理模型在 PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)中创建，但创建是直接从 SharePoint 文档库启动的。 需要在文档库中启用表单处理模型创建，以便用户为其创建表单处理模型，并且管理员可以在内容理解管理设置中执行此操作。 表单处理模型使用 PowerAutomate 流在文件上传到文档库时处理文件。

创建文档理解模型时，将创建一个新的 [sharepoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) ，该类型将保存到 Sharepoint 内容类型库中。 或者，如果需要，可以使用现有内容类型来定义模型。

表单处理模型在 PowerApps [AI 生成器](https://docs.microsoft.com/ai-builder/overview)中创建，但创建是直接从 SharePoint 文档库启动的。 需要在文档库中启用表单处理模型创建，用户才能为其创建表单处理模型。 或者，管理员可以在内容理解管理设置中执行此操作。 表单处理模型使用 PowerAutomate 流在文件上传到文档库时处理文件。

表单处理模型还创建新的 [sharepoint 内容类型](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)，并且也存储在 Sharepoint 内容类型库中。

## <a name="where-they-can-be-applied"></a>可以在何处应用它们

您可以将文档理解模型应用于您有权访问的 SharePoint 文档库。 使用内容中心创建文档理解模型，并将其应用于不同的文档库。 内容中心提供了对文档理解模型的使用及其应用位置的更多集中控制。 注释此信息还必须汇总到内容中心。

表单处理模型目前只能应用于从中创建它们的 SharePoint 文档库。 这将允许具有网站访问权限的授权用户能够创建表单处理模型。

 ## <a name="see-also"></a>另请参阅
[培训：使用 AI 生成器改进业务绩效](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[创建类元](create-a-classifier.md)</br>
[创建提取程序](create-an-extractor.md)</br>
[应用文档理解模型](apply-a-model.md)</br>
[创建表单处理模型](create-a-form-processing-model.md)</br>
