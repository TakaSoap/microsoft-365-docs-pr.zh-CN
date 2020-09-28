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
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="9f53a-103">在 Microsoft SharePoint 中应用文档理解模型 Syntex</span><span class="sxs-lookup"><span data-stu-id="9f53a-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="9f53a-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="9f53a-104">The content in this article is for the the Project Cortex Private Preview.</span></span> <span data-ttu-id="9f53a-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="9f53a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="9f53a-106">发布文档理解模型后，可以将其应用于 Microsoft 365 租户中的 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="9f53a-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="9f53a-107">您只能将模型应用于您有权访问的文档库。</span><span class="sxs-lookup"><span data-stu-id="9f53a-107">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="9f53a-108">将模型应用于文档库。</span><span class="sxs-lookup"><span data-stu-id="9f53a-108">Apply your model to a document library.</span></span>

<span data-ttu-id="9f53a-109">若要将模型应用到 SharePoint 文档库，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9f53a-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="9f53a-110">在模型主页中，在 " **将模型应用于库** " 磁贴上，选择 " **发布模型**"。</span><span class="sxs-lookup"><span data-stu-id="9f53a-110">From the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="9f53a-111">或者，您可以在 "**使用此模型的库**" 部分中选择 " **+ 添加库**"。</span><span class="sxs-lookup"><span data-stu-id="9f53a-111">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![将模型添加到库](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="9f53a-113">选择包含要应用模型的文档库的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="9f53a-113">Select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="9f53a-114">如果网站未显示在列表中，请使用搜索框查找它。</span><span class="sxs-lookup"><span data-stu-id="9f53a-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![选择网站](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="9f53a-116">您必须具有对要向其应用模型的文档库的 " *管理列表* " 权限或 *编辑* 权限。</span><span class="sxs-lookup"><span data-stu-id="9f53a-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="9f53a-117">选择网站后，选择要向其应用模型的文档库。</span><span class="sxs-lookup"><span data-stu-id="9f53a-117">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="9f53a-118">在该示例中，从*Contoso 个案追踪*网站中选择*文档*文档库。</span><span class="sxs-lookup"><span data-stu-id="9f53a-118">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![选择文档库](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="9f53a-120">由于模型与内容类型相关联，因此当您将该模型应用于库时，它会创建内容类型的视图，并将所提取的标签显示为列。</span><span class="sxs-lookup"><span data-stu-id="9f53a-120">Since the model is associated to a content type, when you apply it to the library it creates a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="9f53a-121">默认情况下，此视图是库的默认视图，但您可以选择 " **高级设置** " 并取消选择 " **将此新视图设置为默认值**"，以选择不将其作为默认视图。</span><span class="sxs-lookup"><span data-stu-id="9f53a-121">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![库视图](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="9f53a-123">选择 " **添加** " 将模型应用到库中。</span><span class="sxs-lookup"><span data-stu-id="9f53a-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="9f53a-124">在模型主页上的 " **使用此模型的库** " 部分中，您应该会看到列出的 SharePoint 网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="9f53a-124">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![选定的库](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="9f53a-126">转到您的文档库，并确保您在模型的文档库视图中。</span><span class="sxs-lookup"><span data-stu-id="9f53a-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="9f53a-127">请注意，如果选择文档库名称旁边的 "信息" 按钮，则会出现一条消息，说明您的模型已应用于文档库。</span><span class="sxs-lookup"><span data-stu-id="9f53a-127">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![信息视图](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="9f53a-129">将模型应用于文档库后，可以开始将文档上载到网站并查看结果。</span><span class="sxs-lookup"><span data-stu-id="9f53a-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="9f53a-130">模型标识任何具有模型关联的内容类型的文件，并在视图中列出这些文件。</span><span class="sxs-lookup"><span data-stu-id="9f53a-130">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="9f53a-131">如果您的模型具有任何提取程序，则该视图将显示要从每个文件中提取的数据的列。</span><span class="sxs-lookup"><span data-stu-id="9f53a-131">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="9f53a-132">将模型应用于文档库中已有的文件</span><span class="sxs-lookup"><span data-stu-id="9f53a-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="9f53a-133">应用的模型处理在应用后上载到文档库的所有文件，您还可以执行以下操作，以便在应用模型之前，对文档库中已存在的文件运行模型：</span><span class="sxs-lookup"><span data-stu-id="9f53a-133">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="9f53a-134">在您的文档库中，选择您想要由模型处理的文件。</span><span class="sxs-lookup"><span data-stu-id="9f53a-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="9f53a-135">选择文件后，" **分类和提取** " 将显示在 "文档库" 功能区中。</span><span class="sxs-lookup"><span data-stu-id="9f53a-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="9f53a-136">选择 " **分类并提取**"。</span><span class="sxs-lookup"><span data-stu-id="9f53a-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="9f53a-137">您选择的文件将被添加到队列中进行处理。</span><span class="sxs-lookup"><span data-stu-id="9f53a-137">The files you selected will be added to the queue to be processed.</span></span>

      ![分类和提取](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="9f53a-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f53a-139">See Also</span></span>
[<span data-ttu-id="9f53a-140">创建类元</span><span class="sxs-lookup"><span data-stu-id="9f53a-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="9f53a-141">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="9f53a-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="9f53a-142">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="9f53a-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="9f53a-143">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="9f53a-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  
