---
title: 在 Microsoft SharePoint Syntex 中创建提取程序时利用术语库分类
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
ms.custom: admindeeplinkSPO
ms.localizationpriority: medium
description: 使用 Microsoft SharePoint Syntex 在文档理解模型中创建提取器时，请使用术语库分类。
ms.openlocfilehash: 909f26026ddf26163a12e1d14c1790f4af93a160
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328801"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中创建提取程序时利用术语库分类

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

使用 SharePoint Syntex 在文档理解模型中创建提取器时，可利用 [术语库](/sharepoint/managed-metadata) 中的全局性术语集显示提取数据的首选术语。  

例如，你的模型标识并分类上传到文档库的所有 **合同** 文档。  此外，该模型还会提取每个合同中的 **合同服务** 值，并将其显示在库视图中的一列中。 在合同中的各种合同服务值之间，有一些你的公司不再使用且已重命名了的旧值。 例如，对术语 *Design*、*Graphics* 或 *Topography* 合同服务的所有引用现在都应称为 *创意*。 每当你的模型提取合同文档中的某个过时字词时，你都希望它在你的库视图中显示当前术语“Creative ”。 在下面的示例中，对模型进行训练时，我们看到的是一个示例文档，其中包含已过时的 *Design* 条款。

   ![术语库。](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a>在提取器使用托管元数据列

术语集在 Managed Metadata Services (MMS) 管理中心的术语SharePoint<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">配置</a>。 在下面的示例中，“*合同服务*”[术语集](/sharepoint/managed-metadata#term-set)被配置为包含多个术语，包括“*创意*”。  它的详细信息显示该术语有三个同义词（*Design*、*Graphics* 和 *Topography*），并且同义词应翻译为 *创意*。 

   ![术语集。](../media/content-understanding/term-store.png)</br>

在术语集中使用同义词的原因可能有很多。 例如，组织部门的命名中可能存在已过时的术语、已重命名的术语或差异。

若要确保在模型中创建提取器时托管元数据字段可供选择，需要[将其添加为托管元数据网站列](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f)。 添加该网站列后，便可以在为模型创建提取器时选择该字段。

   ![合同服务。](../media/content-understanding/contract-services.png)</br>

将模型应用到文档库之后，将文档上传到库中时，当提取器发现任意同义词值（*Design*、*Graphics* 和 *Topography*）时，*创意服务* 列将显示首选术语（*创意*）。

   ![合同服务列。](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a>另请参阅
[托管元数据简介](/sharepoint/managed-metadata#terms)

[创建提取器](create-an-extractor.md)

[创建托管元数据列](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)