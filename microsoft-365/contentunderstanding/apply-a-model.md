---
title: '将文档理解模型应用于文档库 (预览) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何将已发布的模型应用到 SharePoint 文档库。
ms.openlocfilehash: 8a4931f4b7a936caeb99d7f8c07deefdac62919b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950244"
---
# <a name="apply-a-document-understanding-model-preview"></a><span data-ttu-id="8ab2a-103">应用文档理解模型 (预览) </span><span class="sxs-lookup"><span data-stu-id="8ab2a-103">Apply a document understanding model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="8ab2a-104">本文中的内容适用于 Project Cortex 私人预览。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="8ab2a-105">了解[有关 Project Cortex 的详细信息](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="8ab2a-106">发布文档理解模型后，可以将其应用于 Microsoft 365 租户中的 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!Note]
> <span data-ttu-id="8ab2a-107">您只能将模型应用于您有权访问的文档库。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-107">You will only be able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="8ab2a-108">将模型应用于文档库。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-108">Apply your model to a document library.</span></span>

<span data-ttu-id="8ab2a-109">若要将模型应用到 SharePoint 文档库，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8ab2a-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="8ab2a-110">在模型主页上，在 " **将模型应用于库** " 磁贴上，选择 " **发布模型**"。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-110">On the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="8ab2a-111">或者，您可以在 "**使用此模型的库**" 部分中选择 " **+ 添加库**"。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-111">Or you can  select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![将模型添加到库](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="8ab2a-113">然后，您可以选择包含要应用模型的文档库的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-113">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="8ab2a-114">如果网站未显示在列表中，请使用搜索框查找它。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![选择网站](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > <span data-ttu-id="8ab2a-116">您必须具有对要向其应用模型的文档库的 " *管理列表* " 权限或 *编辑* 权限。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="8ab2a-117">选择网站后，需要选择要向其应用模型的文档库。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-117">After selecting the site, you then need to select the document library to which you want to apply the model.</span></span> <span data-ttu-id="8ab2a-118">在此示例中，我们将从*Contoso 个案追踪*网站中选择*文档*文档库。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-118">In the example, we are selecting the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![选择文档库](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="8ab2a-120">由于模型与内容类型相关联，因此当您将其应用到库时，它将为内容类型创建一个视图，并将所提取的标签显示为列。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-120">Since the model is associated to a content type, when you apply it to the library it will create a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="8ab2a-121">默认情况下，此视图将为库的默认视图，但您可以选择 " **高级设置** " 并取消选择 " **将此新视图设置为默认值**"，以选择不将其作为默认视图。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-121">This view will be the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![库视图](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="8ab2a-123">选择 " **添加** " 将模型应用到库中。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="8ab2a-124">在模型主页上的 " **使用此模型的库** " 部分中，您将看到列出的 SharePoint 网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-124">On the model home page, in the **Libraries with this model** section, you will see the URL to the SharePoint site listed.</span></span></br>

    ![库视图](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="8ab2a-126">转到您的文档库，并确保您在模型的文档库视图中。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="8ab2a-127">您会注意到，如果选择文档库名称旁边的 "信息" 按钮，则会出现一条消息，指出您的模型已应用于文档库。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-127">You'll notice that if you select the information button next to the document library name, a message will note that your model has been applied to the document library.</span></span>

    ![库视图](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="8ab2a-129">将模型应用于文档库后，可以开始将文档上载到网站并查看结果。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="8ab2a-130">模型将标识任何具有模型关联的内容类型的文件，并将其列在您的视图中。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-130">The model will identify any files with model’s associated content type and will list them in your view.</span></span> <span data-ttu-id="8ab2a-131">如果模型具有任何提取程序，则视图将显示要从每个文件中提取的数据的列。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-131">If your model has any extractors, the view will display columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="8ab2a-132">将模型应用于文档库中已有的文件</span><span class="sxs-lookup"><span data-stu-id="8ab2a-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="8ab2a-133">当应用的模型将处理上载到文档库的所有文件后，您还可以执行以下操作，以对文档库中已存在的文件运行模型之前已存在的文件：</span><span class="sxs-lookup"><span data-stu-id="8ab2a-133">While an applied model will process all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already existed in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="8ab2a-134">在您的文档库中，选择您想要由模型处理的文件。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="8ab2a-135">选择文件后，" **分类和提取** " 将显示在 "文档库" 功能区中。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="8ab2a-136">选择 " **分类并提取**"。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="8ab2a-137">您选择的文件将被添加到队列中进行处理。</span><span class="sxs-lookup"><span data-stu-id="8ab2a-137">The files you selected will be added to the queue to be processed.</span></span>

      ![分类和提取](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a><span data-ttu-id="8ab2a-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ab2a-139">See Also</span></span>
[<span data-ttu-id="8ab2a-140">创建类元</span><span class="sxs-lookup"><span data-stu-id="8ab2a-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="8ab2a-141">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="8ab2a-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="8ab2a-142">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="8ab2a-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="8ab2a-143">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="8ab2a-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  




