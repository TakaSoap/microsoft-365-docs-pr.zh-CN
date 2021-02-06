---
title: 停用高级电子数据展示中的相关性模块
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 高级电子数据展示中的相关性模块将于 2021 年 3 月 10 日停用。 本文介绍在相关性停用之前要执行哪些工作。 具体而言，通过运行批计算完成任何未完成的模型，以便可以保留模型中的元数据。
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122523"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="1dec5-105">停用高级电子数据展示中的相关性模块</span><span class="sxs-lookup"><span data-stu-id="1dec5-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="1dec5-106">2021 年 3 月 10 日，我们将停用高级电子数据展示中的相关性模块。</span><span class="sxs-lookup"><span data-stu-id="1dec5-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="1dec5-107">此停用意味着组织将无法再访问相关性模块 (，方法为在高级电子数据展示案例) 中管理审阅集相关性，或能够访问任何现有相关性  >  模型。</span><span class="sxs-lookup"><span data-stu-id="1dec5-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="1dec5-108">即将停用的当前相关性模块将在 2021 年第 2 季度替换为新的预测编码解决方案。</span><span class="sxs-lookup"><span data-stu-id="1dec5-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="1dec5-109">这一新功能将允许组织在更轻松、更直观的工作流中构建自己的预测编码模型。</span><span class="sxs-lookup"><span data-stu-id="1dec5-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="1dec5-110">为准备即将停用，我们建议使用相关性模块的组织通过运行所有现有模型的批量计算，在停用日期之前导出其模型的输出。</span><span class="sxs-lookup"><span data-stu-id="1dec5-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="1dec5-111">模型的所有相关性分数将永久存储在相应的审阅集内，在导出文档时可访问。</span><span class="sxs-lookup"><span data-stu-id="1dec5-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="1dec5-112">相关性分数也会作为元数据保留在加载文件中。</span><span class="sxs-lookup"><span data-stu-id="1dec5-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="1dec5-113">此外，你仍然能够基于相关性分数筛选审阅集内的内容，并有权访问相关性模型生成的所有元数据。</span><span class="sxs-lookup"><span data-stu-id="1dec5-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="1dec5-114">完成未完成的模型</span><span class="sxs-lookup"><span data-stu-id="1dec5-114">Complete unfinished models</span></span>

<span data-ttu-id="1dec5-115">对于任何未完成的相关性模型，请完成评估、培训和批量计算，以便可以将模型应用于审阅集内的文档。</span><span class="sxs-lookup"><span data-stu-id="1dec5-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="1dec5-116">完成批计算将在相关性模块停用日期后保留信息。</span><span class="sxs-lookup"><span data-stu-id="1dec5-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="1dec5-117">以下是完成任何未完成模型的步骤：</span><span class="sxs-lookup"><span data-stu-id="1dec5-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="1dec5-118">对模型进行训练，直到其稳定下来并准备好进行批计算。</span><span class="sxs-lookup"><span data-stu-id="1dec5-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="1dec5-119">请参阅 [标记和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="1dec5-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="1dec5-120">以下屏幕截图显示了一个可供批量计算的模块。</span><span class="sxs-lookup"><span data-stu-id="1dec5-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="1dec5-121">请注意，评估和培训已完成，下一步是运行批计算。</span><span class="sxs-lookup"><span data-stu-id="1dec5-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![可供批量计算的模型屏幕截图](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="1dec5-123">运行批处理计算。</span><span class="sxs-lookup"><span data-stu-id="1dec5-123">Run the Batch calculation.</span></span> <span data-ttu-id="1dec5-124">请参阅["执行批处理计算"。](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)</span><span class="sxs-lookup"><span data-stu-id="1dec5-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="1dec5-125">验证批计算是否成功。</span><span class="sxs-lookup"><span data-stu-id="1dec5-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="1dec5-126">请参阅 [批计算结果](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)。</span><span class="sxs-lookup"><span data-stu-id="1dec5-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="1dec5-127">有关完成未完成的相关性模型的帮助，请联系 Microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="1dec5-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
