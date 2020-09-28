---
title: 将保留标签应用于文档理解模型
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
description: 本文讨论如何将保留标签应用于文档理解模型
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294911"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>将保留标签应用于文档理解模型

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

您可以轻松地将 [保留标签](https://docs.microsoft.com/microsoft-365/compliance/retention) 应用于 Microsoft SharePoint Syntex 中的文档理解模型。

保留标签允许您将保留设置应用于文档理解模型所标识的文档。  例如，您希望模型不仅标识上载到文档库中的任何 *保险通知* 文档，还会对其应用 *业务* 保留标记，以便在接下来的五个月 (这些文档不会在指定时间段内从文档库中删除（例如) ）。

您可以通过模型主页上的模型设置将预先存在的保留标签应用于文档理解模型。 

> [!Important]
> 若要使保留标签可应用于内容理解模型，需要 [在 Microsoft 365 合规性中心中创建和发布](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)这些标签。

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>将保留标签添加到文档理解模型

1. 从模型主页中，选择 " **模型设置**"。</br>
2. 在 " **模型设置**" 中的 " **安全性和合规性** " 部分，选择 " **保留标签** " 菜单，以查看可供您应用到模型的保留标签列表。</br>
 ![保留标签菜单](../media/content-understanding/retention-labels-menu.png)</br> 
3. 选择要应用于模型的保留标签，然后选择 " **保存**"。</br>

将保留标签应用于您的模型后，可以将其应用于：
- 新建文档库
- 模型已应用到的文档库
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>将保留标签应用于已应用该模型的文档库

如果您的文档理解模型已应用于文档库，则可以执行以下操作来同步您的保留标签更新以将其应用于文档库：</br>

1. 在模型主页上的 " **使用此模型的库** " 部分中，选择要对其应用保留标签更新的文档库。 </br> 
2. 选择 " **同步**"。 </br>
 ![同步模型](../media/content-understanding/sync-model.png)</br> 


在应用更新并将其同步到您的模型后，您可以通过执行以下操作来确认是否已应用该更新：

1. 在内容中心中的 " **具有此模型的库** " 部分中，单击应用了更新的模型的库。 </br>
2. 在文档库视图中，选择 "信息" 图标以检查模型属性。</br>  
3. 在 " **活动模型** " 列表中，选择更新的模型。</br>
4. 在 " **保留标签** " 部分，您将看到已应用的保留标签的名称。</br>


在您的文档库中的模型的 "视图" 页上，将显示新的 " **保留标签** " 列。  当您的模型对其标识为属于其内容类型的文件进行分类，并将其列在库视图中时，保留标签列也会显示通过模型应用于它的保留标签的名称。


例如，您的模型标识的所有 *保险通知* 文档也会应用 *业务* 保留标签，以防在五个月内将其从文档库中删除。 如果尝试从文档库中删除文件，将显示错误消息，指出由于应用了保留标签而不允许这样做。

## <a name="see-also"></a>另请参阅
[创建类元](create-a-classifier.md)</br>
[创建提取程序](create-an-extractor.md)</br>
[文档理解概述](document-understanding-overview.md)</br>
[创建表单处理模型](create-a-form-processing-model.md)  
