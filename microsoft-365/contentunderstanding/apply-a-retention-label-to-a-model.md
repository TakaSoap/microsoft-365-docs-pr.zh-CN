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
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="81883-103">将保留标签应用于文档理解模型</span><span class="sxs-lookup"><span data-stu-id="81883-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="81883-104">您可以轻松地将 [保留标签](https://docs.microsoft.com/microsoft-365/compliance/retention) 应用于 Microsoft SharePoint Syntex 中的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="81883-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="81883-105">保留标签允许您将保留设置应用于文档理解模型所标识的文档。</span><span class="sxs-lookup"><span data-stu-id="81883-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="81883-106">例如，您希望模型不仅标识上载到文档库中的任何 *保险通知* 文档，还会对其应用 *业务* 保留标记，以便在接下来的五个月 (这些文档不会在指定时间段内从文档库中删除（例如) ）。</span><span class="sxs-lookup"><span data-stu-id="81883-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="81883-107">您可以通过模型主页上的模型设置将预先存在的保留标签应用于文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="81883-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="81883-108">若要使保留标签可应用于内容理解模型，需要 [在 Microsoft 365 合规性中心中创建和发布](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)这些标签。</span><span class="sxs-lookup"><span data-stu-id="81883-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="81883-109">将保留标签添加到文档理解模型</span><span class="sxs-lookup"><span data-stu-id="81883-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="81883-110">从模型主页中，选择 " **模型设置**"。</span><span class="sxs-lookup"><span data-stu-id="81883-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="81883-111">在 " **模型设置**" 中的 " **安全性和合规性** " 部分，选择 " **保留标签** " 菜单，以查看可供您应用到模型的保留标签列表。</span><span class="sxs-lookup"><span data-stu-id="81883-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="81883-112">![保留标签菜单](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="81883-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="81883-113">选择要应用于模型的保留标签，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="81883-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="81883-114">将保留标签应用于您的模型后，可以将其应用于：</span><span class="sxs-lookup"><span data-stu-id="81883-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="81883-115">新建文档库</span><span class="sxs-lookup"><span data-stu-id="81883-115">New document library</span></span>
- <span data-ttu-id="81883-116">模型已应用到的文档库</span><span class="sxs-lookup"><span data-stu-id="81883-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="81883-117">将保留标签应用于已应用该模型的文档库</span><span class="sxs-lookup"><span data-stu-id="81883-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="81883-118">如果您的文档理解模型已应用于文档库，则可以执行以下操作来同步您的保留标签更新以将其应用于文档库：</span><span class="sxs-lookup"><span data-stu-id="81883-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="81883-119">在模型主页上的 " **使用此模型的库** " 部分中，选择要对其应用保留标签更新的文档库。</span><span class="sxs-lookup"><span data-stu-id="81883-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="81883-120">选择 " **同步**"。</span><span class="sxs-lookup"><span data-stu-id="81883-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="81883-121">![同步模型](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="81883-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="81883-122">在应用更新并将其同步到您的模型后，您可以通过执行以下操作来确认是否已应用该更新：</span><span class="sxs-lookup"><span data-stu-id="81883-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="81883-123">在内容中心中的 " **具有此模型的库** " 部分中，单击应用了更新的模型的库。</span><span class="sxs-lookup"><span data-stu-id="81883-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="81883-124">在文档库视图中，选择 "信息" 图标以检查模型属性。</span><span class="sxs-lookup"><span data-stu-id="81883-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="81883-125">在 " **活动模型** " 列表中，选择更新的模型。</span><span class="sxs-lookup"><span data-stu-id="81883-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="81883-126">在 " **保留标签** " 部分，您将看到已应用的保留标签的名称。</span><span class="sxs-lookup"><span data-stu-id="81883-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="81883-127">在您的文档库中的模型的 "视图" 页上，将显示新的 " **保留标签** " 列。</span><span class="sxs-lookup"><span data-stu-id="81883-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="81883-128">当您的模型对其标识为属于其内容类型的文件进行分类，并将其列在库视图中时，保留标签列也会显示通过模型应用于它的保留标签的名称。</span><span class="sxs-lookup"><span data-stu-id="81883-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="81883-129">例如，您的模型标识的所有 *保险通知* 文档也会应用 *业务* 保留标签，以防在五个月内将其从文档库中删除。</span><span class="sxs-lookup"><span data-stu-id="81883-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="81883-130">如果尝试从文档库中删除文件，将显示错误消息，指出由于应用了保留标签而不允许这样做。</span><span class="sxs-lookup"><span data-stu-id="81883-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="81883-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81883-131">See Also</span></span>
[<span data-ttu-id="81883-132">创建类元</span><span class="sxs-lookup"><span data-stu-id="81883-132">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="81883-133">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="81883-133">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="81883-134">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="81883-134">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="81883-135">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="81883-135">Create a form processing model</span></span>](create-a-form-processing-model.md)  
