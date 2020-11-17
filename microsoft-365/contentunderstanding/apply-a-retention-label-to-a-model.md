---
title: 将保留标签应用于文档理解模型
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: 本文讨论了如何将保留标签应用于文档理解模型
ms.openlocfilehash: 2e6d300b63a173d01488406485cffa44fab4278e
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087471"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="dd0c7-103">将保留标签应用于文档理解模型</span><span class="sxs-lookup"><span data-stu-id="dd0c7-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="dd0c7-104">可以轻松将 [保留标签](https://docs.microsoft.com/microsoft-365/compliance/retention) 应用于 Microsoft SharePoint Syntex 中的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="dd0c7-105">使用保留标签可将保留设置应用于文档理解模型识别的文档。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="dd0c7-106">例如，希望模型不仅可以识别上传到文档库的任何 *保险通知* 文档，还可将 *商务* 保留标记应用于这些文档，以便在指定时间段（如接下来的五个月）中不能从文档库中删除这些文档。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="dd0c7-107">可通过模型主页上的模型设置，将预先存在的保留标签应用于文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="dd0c7-108">对于可应用于内容理解模型的保留标签，需[在 Microsoft 365 合规中心中创建和发布](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="dd0c7-109">将保留标签添加到文档理解模型</span><span class="sxs-lookup"><span data-stu-id="dd0c7-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="dd0c7-110">在模型主页中，选择 **模型设置**。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="dd0c7-111">在 **模型设置** 的 **安全和合规** 部分，选择 **保留标签** 菜单以查看可应用于模型的保留标签列表。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="dd0c7-112">![保留标签菜单](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="dd0c7-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="dd0c7-113">选择要应用于模型的保留标签，然后选择 **保存**。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="dd0c7-114">将保留标签应用于模型后，可将其应用于：</span><span class="sxs-lookup"><span data-stu-id="dd0c7-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="dd0c7-115">新文档库</span><span class="sxs-lookup"><span data-stu-id="dd0c7-115">New document library</span></span>
- <span data-ttu-id="dd0c7-116">已应用模型的文档库</span><span class="sxs-lookup"><span data-stu-id="dd0c7-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="dd0c7-117">将保留标签应用于已应用模型的文档库</span><span class="sxs-lookup"><span data-stu-id="dd0c7-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="dd0c7-118">如果文档理解模型已应用于文档库，可执行以下操作来同步保留标签更新以将其应用于文档库：</span><span class="sxs-lookup"><span data-stu-id="dd0c7-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="dd0c7-119">在模型主页的 **带模型的库** 部分，选择要应用保留标签更新的文档库。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="dd0c7-120">选择 **同步**。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="dd0c7-121">![同步模型](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="dd0c7-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="dd0c7-122">应用更新并将其同步到模型后，可通过执行以下操作来确认此更新已应用：</span><span class="sxs-lookup"><span data-stu-id="dd0c7-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="dd0c7-123">在内容中心的 **带模型的库** 部分，单击应用了已更新模型的库。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="dd0c7-124">在文档库视图中，选择“信息”图标以查看模型属性。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="dd0c7-125">在 **活动模型** 列表中，选择已更新模型。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="dd0c7-126">在 **保留标签** 部分，将看到已应用保留标签的名称。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="dd0c7-127">文档库的模型视图页面将显示新的 **保留标签** 列。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="dd0c7-128">当模型对其标识为属于其内容类型的文件进行分类并将文件在库视图中列出时，保留标签列也将显示通过模型对其应用的保留标签名称。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="dd0c7-129">例如，模型识别的所有 *保险通知* 文档也将拥有已应用的 *商务* 保留标签，以防止在五个月中从文档库中删除这些文档。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="dd0c7-130">如果尝试从文档库中删除文件，将显示一条错误消息，提示由于应用了保留标签，不允许删除文件。</span><span class="sxs-lookup"><span data-stu-id="dd0c7-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd0c7-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd0c7-131">See Also</span></span>
[<span data-ttu-id="dd0c7-132">创建分类器</span><span class="sxs-lookup"><span data-stu-id="dd0c7-132">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="dd0c7-133">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="dd0c7-133">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="dd0c7-134">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="dd0c7-134">Document Understanding overview</span></span>](document-understanding-overview.md)


