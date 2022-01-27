---
title: 在 SharePoint 整合中向模型应用保留标签
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
ms.localizationpriority: medium
description: 了解如何将保留标签应用于 SharePoint Syntex。
ms.openlocfilehash: 112b48af5e07d09faab61bd656c5629b449d9a1c
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241791"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a>在 SharePoint 整合中向模型应用保留标签

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


可以轻松将 [保留标签](../compliance/retention.md) 应用于 Microsoft SharePoint Syntex 中的文档理解模型。 这可同时针对文档了解和表单处理模型执行这一操作。

保留标签允许将保留设置应用于模型识别的文档。  例如，希望模型不仅可以识别上传到文档库的任何 *保险通知* 文档，还可将 *商务* 保留标记应用于这些文档，以便在指定时间段（如接下来的五个月）中不能从文档库中删除这些文档。

可以通过模型主页上的模型设置将预先存在的保留标签应用于模型。 

> [!Important]
> 若要将保留标签应用于文档理解模型，需要在文档理解模型中创建和发布Microsoft 365 合规中心。 [](../compliance/file-plan-manager.md#create-retention-labels) [](../compliance/create-apply-retention-labels.md#how-to-publish-retention-labels)

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>将保留标签添加到文档理解模型

1. 在模型主页中，选择 **模型设置**。</br>
2. 在 **模型设置** 的 **安全和合规** 部分，选择 **保留标签** 菜单以查看可应用于模型的保留标签列表。</br>
 !["保留标签"菜单。](../media/content-understanding/retention-labels-menu.png)</br> 
3. 选择要应用于模型的保留标签，然后选择 **保存**。</br>

将保留标签应用于模型后，可将其应用于：
- 新文档库
- 已应用模型的文档库
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>将保留标签应用于已应用模型的文档库

如果文档理解模型已应用于文档库，可执行以下操作来同步保留标签更新以将其应用于文档库：</br>

1. 在模型主页的 **带模型的库** 部分，选择要应用保留标签更新的文档库。 </br> 
2. 选择 **同步**。 </br>
 ![同步模型。](../media/content-understanding/sync-model.png)</br> 


应用更新并将其同步到模型后，可通过执行以下操作来确认此更新已应用：

1. 在内容中心的 **带模型的库** 部分，单击应用了已更新模型的库。 </br>
2. 在文档库视图中，选择“信息”图标以查看模型属性。</br>  
3. 在 **活动模型** 列表中，选择已更新模型。</br>
4. 在 **保留标签** 部分，将看到已应用保留标签的名称。</br>


文档库的模型视图页面将显示新的 **保留标签** 列。  当模型对其标识为属于其内容类型的文件进行分类并将文件在库视图中列出时，保留标签列也将显示通过模型对其应用的保留标签名称。


例如，模型识别的所有 *保险通知* 文档也将拥有已应用的 *商务* 保留标签，以防止在五个月中从文档库中删除这些文档。 如果尝试从文档库中删除文件，将显示一条错误消息，提示由于应用了保留标签，不允许删除文件。

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a>向表单处理模型添加保留标签

> [!Important]
> 若要将保留标签应用于表单处理模型，需要在表单处理模型中创建和发布Microsoft 365 合规中心。 [](../compliance/file-plan-manager.md#create-retention-labels) [](../compliance/create-apply-retention-labels.md#how-to-publish-retention-labels)

创建模型时，可以将保留标签应用于窗体处理模型，或将标签应用于现有模型。

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a>创建表单处理模型时添加保留标签

1. 在新建 [窗体处理模型时，](./create-a-form-processing-model.md)" <b>"设置。</b>
2. 在 <b>高级设置</b>中，在 <b>"保留标签</b> "部分中，选择菜单，然后选择要应用到模型的保留标签。</b>

 
     ![添加到新的表单处理模型。](../media/content-understanding/retention-label-forms.png)</br>

3.  完成其余模型设置后，请选择 <b>创建</b> 以生成模型。

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a>将保留标签添加到现有表单处理模型

可以通过不同方式将保留标签添加到现有表单处理模型中：
- 通过文档库中的"自动"菜单
- 通过文档库中的活动模型设置 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a>通过"自动"菜单将保留标签添加到现有表单处理模型

可以通过应用模型的文档库中的"自动"菜单，将保留标签添加到现有表单处理模型中。


1. 在应用表单处理模型的文档库中，选择" <b>自动执行</b> "菜单，选择 <b>AI Builder</b>，然后选择 <b>"查看表单处理模型的详细信息</b>。

   ![自动菜单。](../media/content-understanding/automate-menu.png)</br>

2. 在模型详细信息的" <b>标签"</b> 部分，选择要应用保留标签。  然后选择“<b>保存</b>”。

     ![添加到现有表单处理模型。](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a>在活动模型设置中将保留标签添加到现有表单处理模型

可以通过应用模型的文档库中的活动模型设置，将保留标签添加到现有表单处理模型中。

1. 在应用模型的 SharePoint 文档库中，选择 <b>查看活动模型</b> 图标，然后选择 <b>查看活动</b>。</b>

   ![查看活动模型。](../media/content-understanding/info-du.png)</br> 

2. 在 <b>活动</b>中，选择要应用保留标签的窗体处理模型。

     ![模型详细信息。](../media/content-understanding/retention-label-model-details.png)</br> 


3. 在模型详细信息的" <b>标签"</b> 部分，选择要应用保留标签。  然后选择“<b>保存</b>”。

> [!NOTE]
> 您必须是模型设置窗格的模型所有者，然后可编辑。 


## <a name="see-also"></a>另请参阅
[创建分类器](create-a-classifier.md)

[创建提取程序](create-an-extractor.md)

[文档理解概述](document-understanding-overview.md)
