---
title: 将预测分数筛选器应用于审阅集内的项目
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 使用预测分数筛选器显示预测编码模型预测为相关或不相关的项目。
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822476"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a><span data-ttu-id="11569-103">将预测分数筛选器应用于预览版 (审阅) </span><span class="sxs-lookup"><span data-stu-id="11569-103">Apply a prediction score filter to a review set (preview)</span></span>

<span data-ttu-id="11569-104">在 Advanced eDiscovery 中创建预测编码模型并将其训练到稳定点后，可以应用预测分数筛选器来显示模型已确定的审阅集项目是相关的 (或不相关的) 。</span><span class="sxs-lookup"><span data-stu-id="11569-104">After you create a predictive coding model in Advanced eDiscovery and train it to the point where it's stable, you can apply the prediction score filter to display review set items that the model has determined are relevant (or not relevant).</span></span> <span data-ttu-id="11569-105">创建模型时，还会创建相应的预测分数筛选器。</span><span class="sxs-lookup"><span data-stu-id="11569-105">When you create a model, a corresponding prediction score filter is also created.</span></span> <span data-ttu-id="11569-106">可以使用此筛选器显示指定范围内分配了预测分数的项目。</span><span class="sxs-lookup"><span data-stu-id="11569-106">You can use this filter to display items assigned a prediction score within a specified range.</span></span> <span data-ttu-id="11569-107">通常 **，0** 和 **0 之间的** 预测分数分配给模型已预测的项并不相关。</span><span class="sxs-lookup"><span data-stu-id="11569-107">In general, prediction scores between **0** and **.5** are assigned to items that model has predicted are not relevant.</span></span> <span data-ttu-id="11569-108">分配了预测分数介于 **0.5** 和 **1.0** 之间的项目是模型所预测的相关项。</span><span class="sxs-lookup"><span data-stu-id="11569-108">Items assigned prediction scores between **.5** and **1.0** are items the model has predicted are relevant.</span></span>

<span data-ttu-id="11569-109">以下是两种使用预测分数筛选器的方法：</span><span class="sxs-lookup"><span data-stu-id="11569-109">Here are two ways you can use the prediction score filter:</span></span>

- <span data-ttu-id="11569-110">确定模型所预测的相关审阅集内项目的审阅优先级。</span><span class="sxs-lookup"><span data-stu-id="11569-110">Prioritize the review of items in a review set that the model has predicted are relevant.</span></span>

- <span data-ttu-id="11569-111">从模型预测的审阅集剔除项目不相关。</span><span class="sxs-lookup"><span data-stu-id="11569-111">Cull items from the review set that the model has predicted are not relevant.</span></span> <span data-ttu-id="11569-112">或者，您可以使用预测分数筛选器取消对非相关项目的审阅的优先级。</span><span class="sxs-lookup"><span data-stu-id="11569-112">Alternative, you can use the prediction score filter to de-prioritize the review of non-relevant items.</span></span>

## <a name="before-you-apply-a-prediction-score-filter"></a><span data-ttu-id="11569-113">应用预测分数筛选器之前</span><span class="sxs-lookup"><span data-stu-id="11569-113">Before you apply a prediction score filter</span></span>

- <span data-ttu-id="11569-114">创建预测编码模型，以便创建相应的预测分数筛选器。</span><span class="sxs-lookup"><span data-stu-id="11569-114">Create a predictive coding model so that a corresponding prediction score filter is created.</span></span>

- <span data-ttu-id="11569-115">可以在任何培训轮之后应用预测分数筛选器。</span><span class="sxs-lookup"><span data-stu-id="11569-115">You can apply a prediction score filter after any of the training rounds.</span></span> <span data-ttu-id="11569-116">但是，你可能想要在执行几轮之后等待，或者等到模型稳定之后再使用预测分数筛选器。</span><span class="sxs-lookup"><span data-stu-id="11569-116">But you may want to wait after performing several rounds or until the model is stable before using the prediction score filter.</span></span>

## <a name="apply-a-prediction-score-filter"></a><span data-ttu-id="11569-117">应用预测分数筛选器</span><span class="sxs-lookup"><span data-stu-id="11569-117">Apply a prediction score filter</span></span>

1. <span data-ttu-id="11569-118">在合规性Microsoft 365中，打开Advanced eDiscovery案例，选择"审阅集"选项卡，然后打开审阅集。</span><span class="sxs-lookup"><span data-stu-id="11569-118">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then open the review set.</span></span>

   ![单击"筛选器"以显示"筛选器"飞出页](..\media\PredictionScoreFilter0.png)   

   <span data-ttu-id="11569-120">预加载的默认筛选器显示在审阅集页面的顶部。</span><span class="sxs-lookup"><span data-stu-id="11569-120">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="11569-121">你可以将这些设置保留为 **Any**。</span><span class="sxs-lookup"><span data-stu-id="11569-121">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="11569-122">单击 **"筛选器** "以显示" **筛选器** "飞出页。</span><span class="sxs-lookup"><span data-stu-id="11569-122">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="11569-123">展开 **"分析&** 编码"部分以显示一组筛选器。</span><span class="sxs-lookup"><span data-stu-id="11569-123">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![分析与预测编码部分&分数筛选器](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="11569-125">预测分数筛选器的命名约定是预测 **(模型名称) 。**</span><span class="sxs-lookup"><span data-stu-id="11569-125">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="11569-126">例如，名为模型 **A** 的模型预测分数筛选器名称是模型 **A** 预测 (预测) 。</span><span class="sxs-lookup"><span data-stu-id="11569-126">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="11569-127">选择想要使用预测分数筛选器，然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="11569-127">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="11569-128">在评价集页面上，单击预测分数筛选器下拉列表，然后键入预测分数范围的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="11569-128">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="11569-129">例如，以下屏幕截图显示了一个介于 **.5** 和 **1.0 之间的预测分数范围**。</span><span class="sxs-lookup"><span data-stu-id="11569-129">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![预测分数筛选器的最小值和最大值](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="11569-131">单击筛选器外部以自动将筛选器应用于审阅集。</span><span class="sxs-lookup"><span data-stu-id="11569-131">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="11569-132">在审阅集页面上显示指定范围内具有预测分数的文档列表。</span><span class="sxs-lookup"><span data-stu-id="11569-132">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span> 

  > [!TIP]
  > <span data-ttu-id="11569-133">若要查看分配给文档的实际预测分数，可以单击阅读窗格中的" **元数据** "选项卡。</span><span class="sxs-lookup"><span data-stu-id="11569-133">To view the actual prediction score assign to a document, you can click the **Metadata** tab in the reading pane.</span></span> <span data-ttu-id="11569-134">审阅集内所有模型预测的分数都显示在 **RelevanceScores** 元数据属性中。</span><span class="sxs-lookup"><span data-stu-id="11569-134">The prediction scores for all models in the review set are displayed in the **RelevanceScores** metadata property.</span></span>

## <a name="more-information"></a><span data-ttu-id="11569-135">详细信息</span><span class="sxs-lookup"><span data-stu-id="11569-135">More information</span></span>

- <span data-ttu-id="11569-136">有关使用筛选器的信息，请参阅查询 [和筛选审阅集的内容](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="11569-136">For more information about using filters, see [Query and filter content in a review set](review-set-search.md).</span></span>
