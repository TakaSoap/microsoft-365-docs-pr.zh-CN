---
title: 将文档理解模型应用于文档库
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
description: 了解如何将已发布的模型应用到 SharePoint 文档库
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295486"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint 中应用文档理解模型 Syntex

本文中的内容适用于 Project Cortex 私人预览。 了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

发布文档理解模型后，可以将其应用于 Microsoft 365 租户中的 SharePoint 文档库。

> [!NOTE]
> 您只能将模型应用于您有权访问的文档库。


## <a name="apply-your-model-to-a-document-library"></a>将模型应用于文档库。

若要将模型应用到 SharePoint 文档库，请执行以下操作：

1. 在模型主页中，在 " **将模型应用于库** " 磁贴上，选择 " **发布模型**"。 或者，您可以在 "**使用此模型的库**" 部分中选择 " **+ 添加库**"。 </br>

    ![将模型添加到库](../media/content-understanding/apply-to-library.png)</br>

2. 选择包含要应用模型的文档库的 SharePoint 网站。 如果网站未显示在列表中，请使用搜索框查找它。</br>

    ![选择网站](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > 您必须具有对要向其应用模型的文档库的 " *管理列表* " 权限或 *编辑* 权限。</br>

3. 选择网站后，选择要向其应用模型的文档库。 在该示例中，从*Contoso 个案追踪*网站中选择*文档*文档库。</br>

    ![选择文档库](../media/content-understanding/select-doc-library.png)</br>

4. 由于模型与内容类型相关联，因此当您将该模型应用于库时，它会创建内容类型的视图，并将所提取的标签显示为列。 默认情况下，此视图是库的默认视图，但您可以选择 " **高级设置** " 并取消选择 " **将此新视图设置为默认值**"，以选择不将其作为默认视图。</br>

    ![库视图](../media/content-understanding/library-view.png)</br>

5. 选择 " **添加** " 将模型应用到库中。 
6. 在模型主页上的 " **使用此模型的库** " 部分中，您应该会看到列出的 SharePoint 网站的 URL。</br>

    ![选定的库](../media/content-understanding/selected-library.png)</br>

7. 转到您的文档库，并确保您在模型的文档库视图中。 请注意，如果选择文档库名称旁边的 "信息" 按钮，则会出现一条消息，说明您的模型已应用于文档库。

    ![信息视图](../media/content-understanding/info-du.png)</br> 


将模型应用于文档库后，可以开始将文档上载到网站并查看结果。

模型标识任何具有模型关联的内容类型的文件，并在视图中列出这些文件。 如果您的模型具有任何提取程序，则该视图将显示要从每个文件中提取的数据的列。

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>将模型应用于文档库中已有的文件

应用的模型处理在应用后上载到文档库的所有文件，您还可以执行以下操作，以便在应用模型之前，对文档库中已存在的文件运行模型：

1. 在您的文档库中，选择您想要由模型处理的文件。
2. 选择文件后，" **分类和提取** " 将显示在 "文档库" 功能区中。 选择 " **分类并提取**"。
3. 您选择的文件将被添加到队列中进行处理。

      ![分类和提取](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a>另请参阅
[创建类元](create-a-classifier.md)</br>
[创建提取程序](create-an-extractor.md)</br>
[文档理解概述](document-understanding-overview.md)</br>
[创建表单处理模型](create-a-form-processing-model.md)  
