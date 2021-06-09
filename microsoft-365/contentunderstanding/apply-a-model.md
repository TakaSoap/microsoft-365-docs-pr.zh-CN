---
title: 将文档理解模型应用于文档库
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
description: 了解如何将已发布的模型应用于 SharePoint 文档库
ms.openlocfilehash: cda9de43d0139c52f950527eb75d050602005fd2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843290"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="f9ac2-103">在 Microsoft SharePoint Syntex 中应用文档理解模型</span><span class="sxs-lookup"><span data-stu-id="f9ac2-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="f9ac2-104">发布文档理解模型后，可将其应用到 Microsoft 365 租户中的一个或多个 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="f9ac2-105">只能将模型应用到你有权访问的文档库。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="f9ac2-106">将模型应用于文档库。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-106">Apply your model to a document library.</span></span>

<span data-ttu-id="f9ac2-107">要将模型应用到 SharePoint 文档库，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f9ac2-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="f9ac2-108">在模型主页上，在 **“将模型应用于库”** 平铺中，选择 **“发布模型”**。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="f9ac2-109">或者，你可以在 **应用了模型的库** 部分选择 **“+ 添加库”**。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![向库添加模型](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="f9ac2-111">然后，你可以选择包含要应用模型的文档库的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="f9ac2-112">如果该网站未显示在列表中，请使用搜索框进行查找。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![选择站点](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="f9ac2-114">你必须拥有 *管理列表* 权限，或者 *编辑* 对应用模型的文档库的权限。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="f9ac2-115">选择网站后，选择要向其应用模型的文档库。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="f9ac2-116">在此示例中，从 *Contoso Case 跟踪* 网站中，选择 “*文档"* 文档库。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![选择文档库](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="f9ac2-118">由于模型与内容类型相关联，因此将其应用到库时，它将添加该内容类型及其视图，其中包含作为列显示的已提取标签。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="f9ac2-119">默认情况下，此视图是库的默认视图，但是你可以选择 **“高级设置”** ，然后取消选定 **“将此新视图设置为默认”**，不让其成为默认视图。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![库视图](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="f9ac2-121">选择 **“添加”** 将模型应用到库中。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="f9ac2-122">在模型主页上，在 **应用了此模型库** 部分，你会看到列出的 SharePoint 网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![已选择 的库](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="f9ac2-124">转到你的文档库，并确保你处于模型的文档库视图中。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="f9ac2-125">请注意，如果选择文档库名称旁的“信息”按钮，会显示一条消息，说明文档库已应用一个模型。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-125">Notice that if you select the information button next to the document library name, a message notes that the document library has a model applied to it.</span></span>

    ![信息视图](../media/content-understanding/info-du.png)</br> 

    <span data-ttu-id="f9ac2-127">你可以选择 **“查看活动模型”** 来查看应用于文档库的任何模型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-127">You can the select **View active models** to see details about any models that are applied to the document library.</span></span>

8. <span data-ttu-id="f9ac2-128">在 **“活动模型”** 窗格中，你可以看到应用于文档库的模型。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-128">In the **Active models** pane, you can see the models that are applied to the document library.</span></span> <span data-ttu-id="f9ac2-129">选择一个模型以查看关于它的更多详细信息，例如模型的描述、发布该模型的人，以及该模型是否将保留标签应用于它所分类的文件。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-129">Select a model to see more details about it, such as a description of the model, who published the model, and if the model applies a retention label to the files it classifies.</span></span>

    ![活动模型窗格](../media/content-understanding/active-models.png)</br> 

<span data-ttu-id="f9ac2-131">将模型应用到文档库之后，你可以开始将文档上传到网站并查看结果。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-131">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="f9ac2-132">模型将标识任何具有模型的关联内容类型的文件，并将其列在视图中。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-132">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="f9ac2-133">如果你的模型有任何提取器，则视图会显示每个文件中正在提取的数据的列。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-133">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="f9ac2-134">将模型应用于文档库中已有的文件</span><span class="sxs-lookup"><span data-stu-id="f9ac2-134">Apply the model to files already in the document library</span></span>

<span data-ttu-id="f9ac2-135">应用的模型将处理在应用后上载到文档库的所有文件，还可执行以下操作，在应用模型之前对文档库中已存在的文件运行该模型：</span><span class="sxs-lookup"><span data-stu-id="f9ac2-135">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="f9ac2-136">在文档库中，选择要由模型处理的文件。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-136">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="f9ac2-137">选择文件后，**“分类和提取”** 将在文档库功能区中显示。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-137">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="f9ac2-138">选择 **“分类和提取”**。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-138">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="f9ac2-139">将向队列添加所选的文件进行处理。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-139">The files you selected will be added to the queue to be processed.</span></span>

      ![分类和提取](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> <span data-ttu-id="f9ac2-141">您可以将单个文件复制到库中，然后将其应用于模型，但不能应用于文件夹。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-141">You can copy individual files to a library and apply them to a model, but not folders.</span></span>

### <a name="the-classification-date-field"></a><span data-ttu-id="f9ac2-142">分类日期字段</span><span class="sxs-lookup"><span data-stu-id="f9ac2-142">The Classification Date field</span></span>

<span data-ttu-id="f9ac2-143">SharePoint Syntex 文档理解模型或表单处理模型应用于文档库时，文档库架构包含一个<b>“分类日期”</b>字段。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-143">When a SharePoint Syntex document understanding or form processing model is applied to a document library, a <b> Classification date </b> field is included in the library schema.</span></span> <span data-ttu-id="f9ac2-144">默认情况下，此字段为空，但由模型处理和分类文档时，此字段会更新为完成日期时间戳。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-144">By default this field is empty, but when documents are processed and classified by a model, this field is updated with a date-time stamp of completion.</span></span> 

   ![分类日期列](../media/content-understanding/class-date-column.png)</br> 

<span data-ttu-id="f9ac2-146">分类日期字段由[<b>“内容理解模型对文件进行分类时”</b>触发器](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model)使用，以便在 Syntex 内容理解模型完成处理文件并更新“分类日期”字段后运行 Power Automate 流程。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-146">The Classification date field is used by the [<b>When a file is classified by a content understanding model</b> trigger](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) to run a Power Automate flow after a Syntex content understanding model has finished processing a file and updated the "Classification date" field.</span></span>

   ![流程触发器](../media/content-understanding/trigger.png)</br>

<span data-ttu-id="f9ac2-148"><b>“内容理解模型对文件进行分类时”</b>触发器然后可用于使用从文件中提取的任何信息启动另一个工作流。</span><span class="sxs-lookup"><span data-stu-id="f9ac2-148">The <b>When a file is classified by a content understanding model</b> trigger can then be used to start another workflow using any  extracted information from the file.</span></span>



## <a name="see-also"></a><span data-ttu-id="f9ac2-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9ac2-149">See Also</span></span>
[<span data-ttu-id="f9ac2-150">创建分类器</span><span class="sxs-lookup"><span data-stu-id="f9ac2-150">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="f9ac2-151">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="f9ac2-151">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="f9ac2-152">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="f9ac2-152">Document Understanding overview</span></span>](document-understanding-overview.md)
