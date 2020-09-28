---
title: 创建提取器时利用术语存储分类
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 在 Microsoft SharePoint Syntex 中的文档理解模型中创建提取器时，利用术语库分类。
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295742"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>创建提取器时利用术语存储分类


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

当您在 SharePoint Syntex 中的文档理解模型中创建提取器时，可以利用 [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) 术语库分类来显示您提取的数据的首选术语。  

例如，您的模型标识并分类所有上载到文档库的 **合同** 文档。  此外，该模型还会从每个合同中提取 **合同服务** 值，并将其显示在库视图中的列中。 在合同的各种合同服务值中，您的公司不再使用且已重命名的几个旧值。 例如，对术语 " *设计*"、" *图形*" 或 " *拓扑* 服务" 合同服务的所有引用现在都称为 " *创造性*"。 只要您的模型从合同文档中提取了一个过期的术语，您就希望它在库视图中显示当前术语 "创作"。 在下面的示例中，在培训模型时，我们看到一个示例文档包含了已过期的 *设计*术语。

   ![术语库](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a>术语集同义词 

在 SharePoint 管理中心的 Managed Metadata services 术语库中配置术语集。 在下面的示例中，*合同服务*[术语集](https://docs.microsoft.com/sharepoint/managed-metadata#term-set)配置为包含许多术语，包括*创造性*。  它的详细信息表明，术语包含三个同义词 (*设计*、 *图形*和 *拓扑*) ，并且应将同义词转换为 *创造性*。

   ![术语集](../media/content-understanding/term-store.png)</br>

<Mike，我不确定如何描述此内容。  什么操作告诉模型当我创建提取程序以提取并显示合同服务列时，该专栏是如何 "标记" 以将 managed metadata 术语集用于创造性服务？ >

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a>为托管元数据字段配置文档库网站栏


   ![创建托管元数据](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a>另请参阅
[托管元数据简介](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[创建提取程序](create-an-extractor.md)</br>
[创建托管元数据列](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





