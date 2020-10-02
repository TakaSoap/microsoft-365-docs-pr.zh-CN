---
title: 将文档理解模型应用于文档库
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 了解如何将已发布的模型应用于 SharePoint 文档库
ms.openlocfilehash: 771b0f451d404c6e90f62091ca466bfaf34bae39
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338669"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="458c6-103">在 Microsoft SharePoint Syntex 中应用文档理解模型</span><span class="sxs-lookup"><span data-stu-id="458c6-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="458c6-104">发布文档理解模型后，可将其应用到 Microsoft 365 租户中的一个或多个 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="458c6-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="458c6-105">只能将模型应用到你有权访问的文档库。</span><span class="sxs-lookup"><span data-stu-id="458c6-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="458c6-106">将模型应用于文档库。</span><span class="sxs-lookup"><span data-stu-id="458c6-106">Apply your model to a document library.</span></span>

<span data-ttu-id="458c6-107">要将模型应用到 SharePoint 文档库，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="458c6-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="458c6-108">在模型主页上，在 **“将模型应用于库”** 平铺中，选择 **“发布模型”**。</span><span class="sxs-lookup"><span data-stu-id="458c6-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="458c6-109">或者，你可以在**应用了模型的库**部分选择 **“+ 添加库”**。</span><span class="sxs-lookup"><span data-stu-id="458c6-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![向库添加模型](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="458c6-111">然后，你可以选择包含要应用模型的文档库的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="458c6-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="458c6-112">如果该网站未显示在列表中，请使用搜索框进行查找。</span><span class="sxs-lookup"><span data-stu-id="458c6-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![选择站点](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="458c6-114">你必须拥有*管理列表 \* 权限，或者*编辑 \* 对应用模型的文档库的权限。</span><span class="sxs-lookup"><span data-stu-id="458c6-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="458c6-115">选择网站后，选择要向其应用模型的文档库。</span><span class="sxs-lookup"><span data-stu-id="458c6-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="458c6-116">在此示例中，从 *Contoso Case 跟踪*网站中，选择 “*文档"* 文档库。</span><span class="sxs-lookup"><span data-stu-id="458c6-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![选择文档库](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="458c6-118">由于模型与内容类型相关联，因此将其应用到库时，它将添加该内容类型及其视图，其中包含作为列显示的已提取标签。</span><span class="sxs-lookup"><span data-stu-id="458c6-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="458c6-119">默认情况下，此视图是库的默认视图，但是你可以选择 **“高级设置”** ，然后取消选定 **“将此新视图设置为默认”**，不让其成为默认视图。</span><span class="sxs-lookup"><span data-stu-id="458c6-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![库视图](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="458c6-121">选择 **“添加”** 将模型应用到库中。</span><span class="sxs-lookup"><span data-stu-id="458c6-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="458c6-122">在模型主页上，在**应用了此模型库**部分，你会看到列出的 SharePoint 网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="458c6-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![已选择 的库](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="458c6-124">转到你的文档库，并确保你处于模型的文档库视图中。</span><span class="sxs-lookup"><span data-stu-id="458c6-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="458c6-125">请注意，如果选择文档库名称旁的“信息”按钮，会显示一条消息，说明你的模型已应用于文档库。</span><span class="sxs-lookup"><span data-stu-id="458c6-125">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![信息视图](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="458c6-127">将模型应用到文档库之后，你可以开始将文档上传到网站并查看结果。</span><span class="sxs-lookup"><span data-stu-id="458c6-127">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="458c6-128">模型将标识任何具有模型的关联内容类型的文件，并将其列在视图中。</span><span class="sxs-lookup"><span data-stu-id="458c6-128">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="458c6-129">如果你的模型有任何提取器，则视图会显示每个文件中正在提取的数据的列。</span><span class="sxs-lookup"><span data-stu-id="458c6-129">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="458c6-130">将模型应用于文档库中已有的文件</span><span class="sxs-lookup"><span data-stu-id="458c6-130">Apply the model to files already in the document library</span></span>

<span data-ttu-id="458c6-131">应用的模型将处理在应用后上载到文档库的所有文件，还可执行以下操作，在应用模型之前对文档库中已存在的文件运行该模型：</span><span class="sxs-lookup"><span data-stu-id="458c6-131">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="458c6-132">在文档库中，选择要由模型处理的文件。</span><span class="sxs-lookup"><span data-stu-id="458c6-132">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="458c6-133">选择文件后，**“分类和提取”** 将在文档库功能区中显示。</span><span class="sxs-lookup"><span data-stu-id="458c6-133">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="458c6-134">选择 **“分类和提取”**。</span><span class="sxs-lookup"><span data-stu-id="458c6-134">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="458c6-135">将向队列添加所选的文件进行处理。</span><span class="sxs-lookup"><span data-stu-id="458c6-135">The files you selected will be added to the queue to be processed.</span></span>

      ![分类和提取](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="458c6-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="458c6-137">See Also</span></span>
[<span data-ttu-id="458c6-138">创建分类器</span><span class="sxs-lookup"><span data-stu-id="458c6-138">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="458c6-139">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="458c6-139">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="458c6-140">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="458c6-140">Document Understanding overview</span></span>](document-understanding-overview.md)


