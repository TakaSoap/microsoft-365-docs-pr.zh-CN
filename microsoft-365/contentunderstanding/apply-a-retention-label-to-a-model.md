---
title: 将保留标签应用于文档理解模型
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 本文讨论了如何将保留标签应用于文档理解模型
ms.openlocfilehash: b6ace2a11a7205919fdcf767b888401a5c28db0c
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338621"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>将保留标签应用于文档理解模型

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


可以轻松将 [保留标签](https://docs.microsoft.com/microsoft-365/compliance/retention) 应用于 Microsoft SharePoint Syntex 中的文档理解模型。

使用保留标签可将保留设置应用于文档理解模型识别的文档。  例如，希望模型不仅可以识别上传到文档库的任何 *保险通知* 文档，还可将 *商务* 保留标记应用于这些文档，以便在指定时间段（如接下来的五个月）中不能从文档库中删除这些文档。

可通过模型主页上的模型设置，将预先存在的保留标签应用于文档理解模型。 

> [!Important]
> 对于可应用于内容理解模型的保留标签，需[在 Microsoft 365 合规中心中创建和发布](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)。

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>将保留标签添加到文档理解模型

1. 在模型主页中，选择 **模型设置**。</br>
2. 在 **模型设置** 的 **安全和合规** 部分，选择 **保留标签** 菜单以查看可应用于模型的保留标签列表。</br>
 ![保留标签菜单](../media/content-understanding/retention-labels-menu.png)</br> 
3. 选择要应用于模型的保留标签，然后选择 **保存**。</br>

将保留标签应用于模型后，可将其应用于：
- 新文档库
- 已应用模型的文档库
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>将保留标签应用于已应用模型的文档库

如果文档理解模型已应用于文档库，可执行以下操作来同步保留标签更新以将其应用于文档库：</br>

1. 在模型主页的 **带模型的库** 部分，选择要应用保留标签更新的文档库。 </br> 
2. 选择 **同步**。 </br>
 ![同步模型](../media/content-understanding/sync-model.png)</br> 


应用更新并将其同步到模型后，可通过执行以下操作来确认此更新已应用：

1. 在内容中心的 **带模型的库** 部分，单击应用了已更新模型的库。 </br>
2. 在文档库视图中，选择“信息”图标以查看模型属性。</br>  
3. 在 **活动模型** 列表中，选择已更新模型。</br>
4. 在 **保留标签** 部分，将看到已应用保留标签的名称。</br>


文档库的模型视图页面将显示新的 **保留标签** 列。  当模型对其标识为属于其内容类型的文件进行分类并将文件在库视图中列出时，保留标签列也将显示通过模型对其应用的保留标签名称。


例如，模型识别的所有 *保险通知* 文档也将拥有已应用的 *商务* 保留标签，以防止在五个月中从文档库中删除这些文档。 如果尝试从文档库中删除文件，将显示一条错误消息，提示由于应用了保留标签，不允许删除文件。

## <a name="see-also"></a>另请参阅
[创建分类器](create-a-classifier.md)

[创建提取程序](create-an-extractor.md)

[文档理解概述](document-understanding-overview.md)


