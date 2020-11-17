---
title: 创建提取器时利用术语库分类
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: 在文档中创建提取器的术语库分类 Microsoft SharePoint Syntex 中的理解模型。
ms.openlocfilehash: 0008dd02ef46401e9f0c9414b8363cff034c18eb
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087317"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>创建提取器时利用术语库分类

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>


在 SharePoint Syntex 中的文档理解模型中创建提取器时，可利用[托管元数据服务](https://docs.microsoft.com/sharepoint/managed-metadata#terms)术语库分类，显示提取的数据的首选条款。  

例如，你的模型标识并分类上传到文档库的所有 **合同** 文档。  此外，该模型还会提取每个合同中的 **合同服务** 值，并将其显示在库视图中的一列中。 在合同中的各种合同服务值之间，有一些你的公司不再使用且已重命名了的旧值。 例如，对术语 *Design*、*Graphics* 或 *Topography* 合同服务的所有引用现在都应称为 *创意*。 每当你的模型提取合同文档中的某个过时字词时，你都希望它在你的库视图中显示当前术语“Creative ”。 在下面的示例中，对模型进行训练时，我们看到的是一个示例文档，其中包含已过时的 *Design* 条款。

   ![术语库](../media/content-understanding/design.png)</br>


## <a name="use-a-managed-metadata-column-in-your-extractor"></a>在提取器使用托管元数据列

在 SharePoint 管理中心的托管元数据服务术语库中配置术语集。 在下面的示例中， *合同服务*[术语集](https://docs.microsoft.com/sharepoint/managed-metadata#term-set)配置为包含许多条款，包括 *创意*。  它的详细信息显示该术语有三个同义词（*Design*、*Graphics* 和 *Topography*），并且同义词应翻译为 *创意*。 

   ![术语集](../media/content-understanding/term-store.png)</br>

在术语集中使用同义词可能有很多原因。 例如，组织部门的命名中可能存在已过时的术语、已重命名的术语或差异。

若要使托管元数据字段在模型中创建提取器时可供选择，需要[将其添加为](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f)托管元数据网站列。 添加网站列后，当为模型创建提取器时，就可以选择它了。

   ![合同服务](../media/content-understanding/contract-services.png)</br>


将模型应用到文档库之后，将文档上传到库中时，当提取器发现任意同义词值（*Design*、*Graphics* 和 *Topography*）时，*创意服务* 列将显示首选术语（*创意*）。

   ![合同服务列](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a>另请参阅
[托管元数据简介](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[创建提取器](create-an-extractor.md)

[创建托管元数据列](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





