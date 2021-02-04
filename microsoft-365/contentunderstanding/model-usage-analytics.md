---
title: 文档理解模型使用情况分析
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
localization_priority: Priority
description: 了解如何将保留标签应用于文档理解模型
ms.openlocfilehash: 92115d8b1985fa84cd72671442aca18f255355de
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080410"
---
# <a name="document-understanding-model-usage-analytics"></a><span data-ttu-id="4d4ba-103">文档理解模型使用情况分析</span><span class="sxs-lookup"><span data-stu-id="4d4ba-103">Document understanding model usage analytics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhX]  

</br>


<span data-ttu-id="4d4ba-104">Microsoft SharePoint Syntex 内容中心可提供模型使用情况分析，即提供有关如何使用内容中心中已发布的模型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-104">Your Microsoft SharePoint Syntex content center provides you model usage analytics to provide more information about how your models that have been published from the content center are being used.</span></span> <span data-ttu-id="4d4ba-105">内容中心的<b>模型最近 30 天的运行情况</b>部分包括以下图表和列表中提供的 30 天使用情况分析数据汇总：</span><span class="sxs-lookup"><span data-stu-id="4d4ba-105">The <b>How your models are performing in the last 30 days</b> section of the content center includes a 30 day roll-up of usage analytics data provided in the following charts and lists:</span></span>

- <span data-ttu-id="4d4ba-106">按模型分类</span><span class="sxs-lookup"><span data-stu-id="4d4ba-106">Classification by model</span></span>
- <span data-ttu-id="4d4ba-107">按库分类</span><span class="sxs-lookup"><span data-stu-id="4d4ba-107">Classification by library</span></span>
- <span data-ttu-id="4d4ba-108">模型使用情况</span><span class="sxs-lookup"><span data-stu-id="4d4ba-108">Model usage</span></span> 

 ![模型分析](../media/content-understanding/model-analytics.png) </br>

### <a name="roll-up-of-model-usage-data-in-the-default-content-center"></a><span data-ttu-id="4d4ba-110">在默认内容中心汇总模型使用数据</span><span class="sxs-lookup"><span data-stu-id="4d4ba-110">Roll up of model usage data in the default content center</span></span>

<span data-ttu-id="4d4ba-111">在 SharePoint Syntex 中，在设置过程中创建默认内容中心。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-111">In SharePoint Syntex, the default content center is created during setup.</span></span> <span data-ttu-id="4d4ba-112">也可以根据需要创建其他内容中心。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-112">Additional content centers can also be created as needed.</span></span> <span data-ttu-id="4d4ba-113">例如，部门可创建自己的内容中心来创建和管理其模型。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-113">For example, departments might create their own content centers to create and manage their models.</span></span> 

<span data-ttu-id="4d4ba-114">对于模型使用情况分析，请注意：</span><span class="sxs-lookup"><span data-stu-id="4d4ba-114">In regards to model usage analytics, note that:</span></span>

- <span data-ttu-id="4d4ba-115">默认内容中心将显示组织内所有内容中心和模型的模型使用情况分析，包括在其他内容中心中创建的模型。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-115">Your default content center will show model usage analytics for all content centers and models in your org, including ones created in additional content centers.</span></span> <span data-ttu-id="4d4ba-116">这为内容管理者和其他利益干系人提供了一个集中式门户，用于管理和监督整个公司的内容中心和模型。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-116">This gives content managers and other stakeholders a centralized portal to manage and oversee the content centers and models across the company.</span></span>  
- <span data-ttu-id="4d4ba-117">其他内容中心将仅显示在其中创建的模型的模型使用情况分析。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-117">Other content centers will only show model usage analytics for the models that were created in them.</span></span> <span data-ttu-id="4d4ba-118">这使内容管理员可以仅深入了解所关注模型的使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-118">This gives content managers insights into usage data for only the models they are concerned with.</span></span>


## <a name="classification-by-model"></a><span data-ttu-id="4d4ba-119">按模型分类</span><span class="sxs-lookup"><span data-stu-id="4d4ba-119">Classification by model</span></span>

   ![总模型百分比](../media/content-understanding/total-model-percentage.png) </br>

<span data-ttu-id="4d4ba-121">**按模型分类** 饼图显示已对大多数文件进行分类的模型。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-121">The **Classification by model** pie chart displays which models have classified the most files.</span></span> <span data-ttu-id="4d4ba-122">它将每个已发布模型显示为内容中心中所有已发布模型处理的总文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-122">It shows each published model as a percentage of the total files processed by all published models on the content center.</span></span>

<span data-ttu-id="4d4ba-123">每个模型还显示 **完整率**，即由模型成功分析的已上传文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-123">Each model also shows the **Completeness Rate**, the percentage of uploaded files that were successfully analyzed by the model.</span></span> <span data-ttu-id="4d4ba-124">完整率低可能意味着模型或正在分析的文件存在问题。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-124">A low completeness rate may mean that there are issues with either the model or the files that are being analyzed.</span></span>

## <a name="classification-by-library"></a><span data-ttu-id="4d4ba-125">按库分类</span><span class="sxs-lookup"><span data-stu-id="4d4ba-125">Classification by library</span></span>

   ![处理的文件](../media/content-understanding/files-processed-over-time.png) </br>

<span data-ttu-id="4d4ba-127">**按库分类** 条形图可帮助确定组织中内容理解的有效性。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-127">The **Classification by library** bar chart helps you determine the effectiveness of content understanding in your organization.</span></span>  <span data-ttu-id="4d4ba-128">条形图不仅显示每个模型一段时间内处理的文件数，通过选择图标中的列，还会显示应用模型的文档库。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-128">It shows you not only the number of files processed over time for each model, but by selecting a column in chart, it will also show you the document libraries to which the model was applied.</span></span>


## <a name="model-usage"></a><span data-ttu-id="4d4ba-129">模型使用情况</span><span class="sxs-lookup"><span data-stu-id="4d4ba-129">Model usage</span></span>

<span data-ttu-id="4d4ba-130">“模型使用情况”列表将显示通过内容中心创建的模型的使用情况分析。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-130">The Model Usage list will show usage analytics for the models created through the content center.</span></span>  

> [!NOTE]
> <span data-ttu-id="4d4ba-131">如果你位于默认资源中心，并且组织中有其他资源中心，则模型使用情况列表将按资源中心分组。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-131">If you are in the default content center and have additional content centers in your organization, the model usage list will be grouped by content center.</span></span>

<span data-ttu-id="4d4ba-132">模型使用情况列表中的每个模型都将显示使用情况数据：</span><span class="sxs-lookup"><span data-stu-id="4d4ba-132">Each model in the model usage list will show the usage data:</span></span>

- <span data-ttu-id="4d4ba-133">已分类项目计数：模型处理的文件数。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-133">Classified item count: Number of files processed by the model.</span></span>
- <span data-ttu-id="4d4ba-134">平均置信度分数：对文件运行模型的平均准确度分数。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-134">Average confidence score: Average accuracy score of the model when run against files.</span></span>
- <span data-ttu-id="4d4ba-135">目标列表 URL：应用模型的 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="4d4ba-135">Target list URL: The SharePoint document library to which the model is applied.</span></span>



## <a name="see-also"></a><span data-ttu-id="4d4ba-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d4ba-136">See Also</span></span>
[<span data-ttu-id="4d4ba-137">创建分类器</span><span class="sxs-lookup"><span data-stu-id="4d4ba-137">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="4d4ba-138">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="4d4ba-138">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="4d4ba-139">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="4d4ba-139">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="4d4ba-140">创建表单处理模型</span><span class="sxs-lookup"><span data-stu-id="4d4ba-140">Create a form processing model</span></span>](create-a-form-processing-model.md)  
