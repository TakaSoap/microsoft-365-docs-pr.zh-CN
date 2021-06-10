---
title: 将保留标签应用于模型
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
localization_priority: Normal
description: 本文讨论如何将保留标签应用于 SharePoint Syntex 中的模型
ms.openlocfilehash: 00a8d255b3274af3cd96527e0dcd2ae2644226ac
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861607"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a><span data-ttu-id="e3b2e-103">在 SharePoint 整合中向模型应用保留标签</span><span class="sxs-lookup"><span data-stu-id="e3b2e-103">Apply a retention label to a model in SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="e3b2e-104">可以轻松将 [保留标签](../compliance/retention.md) 应用于 Microsoft SharePoint Syntex 中的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-104">You can easily apply a [retention label](../compliance/retention.md) to a model in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="e3b2e-105">这可同时针对文档了解和表单处理模型执行这一操作。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-105">You can do this for both document understanding and form processing models.</span></span>

<span data-ttu-id="e3b2e-106">保留标签允许将保留设置应用于模型识别的文档。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-106">Retention labels let you apply retention settings to the documents that your models identify.</span></span>  <span data-ttu-id="e3b2e-107">例如，希望模型不仅可以识别上传到文档库的任何 *保险通知* 文档，还可将 *商务* 保留标记应用于这些文档，以便在指定时间段（如接下来的五个月）中不能从文档库中删除这些文档。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-107">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="e3b2e-108">可以通过模型主页上的模型设置将预先存在的保留标签应用于模型。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-108">You can apply a pre-existing retention label to your model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="e3b2e-109">对于可应用于内容理解模型的保留标签，需[在 Microsoft 365 合规中心中创建和发布](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-109">For retention labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="e3b2e-110">将保留标签添加到文档理解模型</span><span class="sxs-lookup"><span data-stu-id="e3b2e-110">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="e3b2e-111">在模型主页中，选择 **模型设置**。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-111">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="e3b2e-112">在 **模型设置** 的 **安全和合规** 部分，选择 **保留标签** 菜单以查看可应用于模型的保留标签列表。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-112">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="e3b2e-113">![保留标签菜单](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="e3b2e-113">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="e3b2e-114">选择要应用于模型的保留标签，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-114">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="e3b2e-115">将保留标签应用于模型后，可将其应用于：</span><span class="sxs-lookup"><span data-stu-id="e3b2e-115">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="e3b2e-116">新文档库</span><span class="sxs-lookup"><span data-stu-id="e3b2e-116">New document library</span></span>
- <span data-ttu-id="e3b2e-117">已应用模型的文档库</span><span class="sxs-lookup"><span data-stu-id="e3b2e-117">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="e3b2e-118">将保留标签应用于已应用模型的文档库</span><span class="sxs-lookup"><span data-stu-id="e3b2e-118">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="e3b2e-119">如果文档理解模型已应用于文档库，可执行以下操作来同步保留标签更新以将其应用于文档库：</span><span class="sxs-lookup"><span data-stu-id="e3b2e-119">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="e3b2e-120">在模型主页的 **带模型的库** 部分，选择要应用保留标签更新的文档库。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-120">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="e3b2e-121">选择 **同步**。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-121">Select **Sync**.</span></span> </br>
 <span data-ttu-id="e3b2e-122">![同步模型](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="e3b2e-122">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="e3b2e-123">应用更新并将其同步到模型后，可通过执行以下操作来确认此更新已应用：</span><span class="sxs-lookup"><span data-stu-id="e3b2e-123">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="e3b2e-124">在内容中心的 **带模型的库** 部分，单击应用了已更新模型的库。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-124">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="e3b2e-125">在文档库视图中，选择“信息”图标以查看模型属性。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-125">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="e3b2e-126">在 **活动模型** 列表中，选择已更新模型。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-126">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="e3b2e-127">在 **保留标签** 部分，将看到已应用保留标签的名称。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-127">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="e3b2e-128">文档库的模型视图页面将显示新的 **保留标签** 列。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-128">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="e3b2e-129">当模型对其标识为属于其内容类型的文件进行分类并将文件在库视图中列出时，保留标签列也将显示通过模型对其应用的保留标签名称。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-129">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="e3b2e-130">例如，模型识别的所有 *保险通知* 文档也将拥有已应用的 *商务* 保留标签，以防止在五个月中从文档库中删除这些文档。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-130">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="e3b2e-131">如果尝试从文档库中删除文件，将显示一条错误消息，提示由于应用了保留标签，不允许删除文件。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-131">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a><span data-ttu-id="e3b2e-132">向表单处理模型添加保留标签</span><span class="sxs-lookup"><span data-stu-id="e3b2e-132">To add a retention label to a form processing model</span></span>

> [!Important]
> <span data-ttu-id="e3b2e-133">对于可应用于内容理解模型的保留标签，需[在 Microsoft 365 合规中心中创建和发布](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-133">For retention labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

<span data-ttu-id="e3b2e-134">创建模型时，可以将保留标签应用于窗体处理模型，或将标签应用于现有模型。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-134">You can either apply a retention label to a form processing model when you are creating a model, or apply it to an existing model.</span></span>

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a><span data-ttu-id="e3b2e-135">创建表单处理模型时添加保留标签</span><span class="sxs-lookup"><span data-stu-id="e3b2e-135">To add a retention label when you create a form processing model</span></span>

1. <span data-ttu-id="e3b2e-136">在新建 [窗体处理模型时，](./create-a-form-processing-model.md)" <b>"设置。</b></span><span class="sxs-lookup"><span data-stu-id="e3b2e-136">When you are [creating a new form processing model](./create-a-form-processing-model.md), select <b>Advanced settings.</b></span></span>
2. <span data-ttu-id="e3b2e-137">在 <b>高级设置</b>中，在 <b>"保留标签</b> "部分中，选择菜单，然后选择要应用到模型的保留标签。</b></span><span class="sxs-lookup"><span data-stu-id="e3b2e-137">In <b>Advanced settings</b>, in the <b>Retention label</b> section, select the menu and then select the retention label you want to apply to the model.</b></span></span>

 
     ![添加到新的表单处理模型](../media/content-understanding/retention-label-forms.png)</br>

3.  <span data-ttu-id="e3b2e-139">完成其余模型设置后，请选择 <b>创建</b> 以生成模型。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-139">After you've completed your remaining model settings, select <b>Create</b> to build your model.</span></span>

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a><span data-ttu-id="e3b2e-140">将保留标签添加到现有表单处理模型</span><span class="sxs-lookup"><span data-stu-id="e3b2e-140">To add a retention label to an existing form processing model</span></span>

<span data-ttu-id="e3b2e-141">可以通过不同方式将保留标签添加到现有表单处理模型中：</span><span class="sxs-lookup"><span data-stu-id="e3b2e-141">You can add a retention label to an existing form processing model in different ways:</span></span>
- <span data-ttu-id="e3b2e-142">通过文档库中的"自动"菜单</span><span class="sxs-lookup"><span data-stu-id="e3b2e-142">Through the Automate menu in the document library</span></span>
- <span data-ttu-id="e3b2e-143">通过文档库中的活动模型设置</span><span class="sxs-lookup"><span data-stu-id="e3b2e-143">Through the Active model settings in the document library</span></span> 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a><span data-ttu-id="e3b2e-144">通过"自动"菜单将保留标签添加到现有表单处理模型</span><span class="sxs-lookup"><span data-stu-id="e3b2e-144">To add a retention label to an existing form processing model through the Automate menu</span></span>

<span data-ttu-id="e3b2e-145">可以通过应用模型的文档库中的"自动"菜单，将保留标签添加到现有表单处理模型中。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-145">You can add a retention label to an existing form processing model that you own through the Automate menu in the document library in which the model is applied.</span></span>


1. <span data-ttu-id="e3b2e-146">在应用表单处理模型的文档库中，选择" <b>自动执行</b> "菜单，选择 <b>AI Builder</b>，然后选择 <b>"查看表单处理模型的详细信息</b>。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-146">In your document library to which the form processing model is applied, select the <b>Automate</b> menu, select <b>AI Builder</b>, then select <b>View form processing model details</b>.</span></span>

   !["自动"菜单](../media/content-understanding/automate-menu.png)</br>

2. <span data-ttu-id="e3b2e-148">在模型详细信息的" <b>标签"</b> 部分，选择要应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-148">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="e3b2e-149">然后选择“<b>保存</b>”。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-149">Then select <b>Save</b>.</span></span>

     ![添加到现有表单处理模型](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a><span data-ttu-id="e3b2e-151">在活动模型设置中将保留标签添加到现有表单处理模型</span><span class="sxs-lookup"><span data-stu-id="e3b2e-151">To add a retention label to an existing form processing model in the active model settings</span></span>

<span data-ttu-id="e3b2e-152">可以通过应用模型的文档库中的活动模型设置，将保留标签添加到现有表单处理模型中。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-152">You can add a retention label to an existing form processing model that you own through the Active model settings in the document library in which the model is applied.</span></span>

1. <span data-ttu-id="e3b2e-153">在应用模型的 SharePoint 文档库中，选择 <b>查看活动模型</b> 图标，然后选择 <b>查看活动</b>。</b></span><span class="sxs-lookup"><span data-stu-id="e3b2e-153">In the SharePoint document library in which the model is applied, select the <b>View active models</b> icon, and then select <b>View active models</b>.</b></span></span>

   ![查看活动模型](../media/content-understanding/info-du.png)</br> 

2. <span data-ttu-id="e3b2e-155">在 <b>活动</b>中，选择要应用保留标签的窗体处理模型。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-155">In <b>Active models</b>, select the form processing model to which you want to apply the retention label.</span></span>

     ![模型详细信息](../media/content-understanding/retention-label-model-details.png)</br> 


3. <span data-ttu-id="e3b2e-157">在模型详细信息的" <b>标签"</b> 部分，选择要应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-157">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="e3b2e-158">然后选择“<b>保存</b>”。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-158">Then select <b>Save</b>.</span></span>

> [!NOTE]
> <span data-ttu-id="e3b2e-159">您必须是模型设置窗格的模型所有者，然后可编辑。</span><span class="sxs-lookup"><span data-stu-id="e3b2e-159">You must be the model owner for the model settings pane to be editable.</span></span> 


## <a name="see-also"></a><span data-ttu-id="e3b2e-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3b2e-160">See Also</span></span>
[<span data-ttu-id="e3b2e-161">创建分类器</span><span class="sxs-lookup"><span data-stu-id="e3b2e-161">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="e3b2e-162">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="e3b2e-162">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="e3b2e-163">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="e3b2e-163">Document Understanding overview</span></span>](document-understanding-overview.md)
