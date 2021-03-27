---
title: '高级电子数据展示预览版 (编码模块) '
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
description: 高级电子数据展示中的新预测编码模块使用机器学习来分析审阅集内的文档，以预测哪些文档与案例或调查相关。
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382950"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a><span data-ttu-id="b5d81-103">高级电子数据展示预览版 (编码模块) </span><span class="sxs-lookup"><span data-stu-id="b5d81-103">Predictive coding module for Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="b5d81-104">使用高级电子数据展示中新的预测编码模块，可以创建和构建一个模型，以优先查看以最相关的文档开始的文档。</span><span class="sxs-lookup"><span data-stu-id="b5d81-104">Using the new predictive coding module in Advanced eDiscovery, you can create and build a model to prioritize review of documents starting with the most relevant documents.</span></span> <span data-ttu-id="b5d81-105">若要开始，您可以创建一个模型，将文档标记为 50 个，然后按模型预测分数筛选文档，以查看相关的非相关文档。</span><span class="sxs-lookup"><span data-stu-id="b5d81-105">To get started, you can create a model, label as few as 50 documents, and then filter documents by model prediction scores to review relevant non-relevant documents.</span></span>

<span data-ttu-id="b5d81-106">以下是工作流的快速概述：</span><span class="sxs-lookup"><span data-stu-id="b5d81-106">Here’s a quick overview of the workflow:</span></span>

1. <span data-ttu-id="b5d81-107">打开审阅集内预测编码模块。</span><span class="sxs-lookup"><span data-stu-id="b5d81-107">Open the predictive coding module in a review set.</span></span>

   ![单击评论中的"分析"下拉列表以转到预测编码模块](..\media\PredictiveCoding1.png)

2. <span data-ttu-id="b5d81-109">在" **预测编码模型"** 页上，单击" **新建模型** "以创建新的预测编码模型。</span><span class="sxs-lookup"><span data-stu-id="b5d81-109">On the **Predictive coding models** page, click **New model** to create a new predictive coding model.</span></span>

   ![创建新模型](..\media\PredictiveCoding2.png)

3. <span data-ttu-id="b5d81-111">将至少 50 个文档标记为 **"相关**"或"**不相关"。**</span><span class="sxs-lookup"><span data-stu-id="b5d81-111">Label at least 50 documents as **Relevant** or **Not relevant**.</span></span> <span data-ttu-id="b5d81-112">此标记用于训练系统。</span><span class="sxs-lookup"><span data-stu-id="b5d81-112">This labeling is used to train the system.</span></span>

   ![将文档标记为与系统培训相关或不相关](..\media\PredictiveCoding3.png)

4. <span data-ttu-id="b5d81-114">将 **模型预测分数** 筛选器应用于评价集。</span><span class="sxs-lookup"><span data-stu-id="b5d81-114">Apply the **Prediction score** filter for your model to the review set.</span></span> <span data-ttu-id="b5d81-115">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5d81-115">To do this:</span></span>

   1. <span data-ttu-id="b5d81-116">在审阅集内，单击"筛选器 **"。**</span><span class="sxs-lookup"><span data-stu-id="b5d81-116">In the review set, click **Filters**.</span></span>
   2. <span data-ttu-id="b5d81-117">在"**筛选器**"飞出页中，展开 **"分析/ML"** 部分，然后选中要应用的模型的"预测分数"复选框。</span><span class="sxs-lookup"><span data-stu-id="b5d81-117">In the **Filters** flyout page, expand the **Analytics/ML** section and then select **Prediction score** checkbox for the model you want to apply.</span></span>
   3. <span data-ttu-id="b5d81-118">在预测 **分数** 筛选器中，指定预测分数。</span><span class="sxs-lookup"><span data-stu-id="b5d81-118">In the **Prediction score** filter, specify a prediction score.</span></span> <span data-ttu-id="b5d81-119">筛选器将显示审阅集内与预测分数匹配的文档。</span><span class="sxs-lookup"><span data-stu-id="b5d81-119">The filter will display the documents in the review set that match the prediction score.</span></span>

      ![指定用于筛选文档预测分数](..\media\PredictiveCoding4.png)

5. <span data-ttu-id="b5d81-121">监视模型的性能、状态和稳定性。</span><span class="sxs-lookup"><span data-stu-id="b5d81-121">Monitor the performance, status, and stability of your model.</span></span>

   ![监视模型的性能、状态和稳定性](..\media\PredictiveCoding5.png)
