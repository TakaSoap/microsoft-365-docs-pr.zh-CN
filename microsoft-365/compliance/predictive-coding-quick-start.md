---
title: Advanced eDiscovery中的预测编码 - 快速入门
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
description: 了解如何开始使用 Advanced eDiscovery 中的预测编码模块。 本文将引导你完成使用预测编码来标识与调查最相关的审阅集内容的端到端过程。
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822484"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a><span data-ttu-id="e759f-104">快速入门：预览Advanced eDiscovery (预测) </span><span class="sxs-lookup"><span data-stu-id="e759f-104">Quick start: Predictive coding in Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="e759f-105">本文介绍在 Advanced eDiscovery 中使用预测编码的快速入门。</span><span class="sxs-lookup"><span data-stu-id="e759f-105">This article presents a quick start for using predictive coding in Advanced eDiscovery.</span></span> <span data-ttu-id="e759f-106">Advanced eDiscovery中的预测编码模块使用 Advanced eDiscovery 中的智能机器学习功能，以帮助你减少要审阅的内容量。</span><span class="sxs-lookup"><span data-stu-id="e759f-106">The predictive coding module in Advanced eDiscovery uses the intelligent, machine learning capabilities in Advanced eDiscovery to help you reduce the amount of content to review.</span></span> <span data-ttu-id="e759f-107">预测编码可帮助你减少大量案例内容并将其剔除到一组相关项目，你可以优先查看这些项目。</span><span class="sxs-lookup"><span data-stu-id="e759f-107">Predictive coding helps you reduce and cull large volumes of case content to a relevant set of items that you can prioritize for review.</span></span> <span data-ttu-id="e759f-108">这是通过创建和培训自己的预测编码模型来完成的，这些模型可帮助您确定审阅集内最相关项目的优先级。</span><span class="sxs-lookup"><span data-stu-id="e759f-108">This is accomplished by creating and training your own predictive coding models that help you prioritize the review of the most relevant items in a review set.</span></span>

<span data-ttu-id="e759f-109">以下是预测编码过程的快速概述：</span><span class="sxs-lookup"><span data-stu-id="e759f-109">Here's an a quick overview of the predictive coding process:</span></span>

![预测编码的快速启动过程](..\media\PredictiveCodingQuickStartProcess.png)

<span data-ttu-id="e759f-111">To get started， you create a model， label as few as 50 items as relevant or not relevant.</span><span class="sxs-lookup"><span data-stu-id="e759f-111">To get started, you create a model, label as few as 50 items as relevant or not relevant.</span></span> <span data-ttu-id="e759f-112">然后，系统使用此培训将预测分数应用于审阅集内的每一项。</span><span class="sxs-lookup"><span data-stu-id="e759f-112">The system then uses this training to apply prediction scores to every item in the review set.</span></span> <span data-ttu-id="e759f-113">这样，你可以根据预测分数筛选项目，这允许你首先查看最相关的 (或不相关的) 项。</span><span class="sxs-lookup"><span data-stu-id="e759f-113">This lets you filter items based on the prediction score, which  allows you to review the most relevant (or non-relevant) items first.</span></span> <span data-ttu-id="e759f-114">如果你想要使用更高的功能和调用率对模型进行培训，可以在后续培训轮中继续标记项目，直到模型稳定下来。</span><span class="sxs-lookup"><span data-stu-id="e759f-114">If you want to train models with higher accuracies and recall rates, you can continue labeling items in subsequent training rounds until the model stabilizes.</span></span> <span data-ttu-id="e759f-115">一旦模型稳定下来，你可以应用最终预测筛选器来设置要审阅项目的优先级。</span><span class="sxs-lookup"><span data-stu-id="e759f-115">Once the model is stabilized, you can apply the final prediction filter to prioritize items to review.</span></span>

<span data-ttu-id="e759f-116">有关预测编码的详细概述，请参阅了解预测[编码在Advanced eDiscovery。](predictive-coding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e759f-116">For a detailed overview of predictive coding, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span></span>

## <a name="step-1-create-a-new-predictive-coding-model"></a><span data-ttu-id="e759f-117">步骤 1：创建新的预测编码模型</span><span class="sxs-lookup"><span data-stu-id="e759f-117">Step 1: Create a new predictive coding model</span></span>

<span data-ttu-id="e759f-118">第一步是在审阅集内创建新的预测编码模型</span><span class="sxs-lookup"><span data-stu-id="e759f-118">The first step is to create a new predictive coding model in the review set</span></span>

1. <span data-ttu-id="e759f-119">在"Microsoft 365合规中心"中，打开Advanced eDiscovery案例，然后选择"**审阅集"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e759f-119">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="e759f-120">打开审阅集，然后单击分析 **管理** 预测  >  **编码 (预览) 。**</span><span class="sxs-lookup"><span data-stu-id="e759f-120">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

   ![单击审阅集的"分析"下拉菜单以转到预测编码页面](..\media\ManagePredictiveCoding.png)

3. <span data-ttu-id="e759f-122">在"**预测编码模型 (预览) ，** 单击"新建 **模型"。**</span><span class="sxs-lookup"><span data-stu-id="e759f-122">On the **Predictive coding models (preview)** page, click **New model**.</span></span>

4. <span data-ttu-id="e759f-123">在飞出页面上，键入模型名称和可选说明。</span><span class="sxs-lookup"><span data-stu-id="e759f-123">On the flyout page, type a name for the model and an optional description.</span></span>

5. <span data-ttu-id="e759f-124">单击 **"保存** "创建模型。</span><span class="sxs-lookup"><span data-stu-id="e759f-124">Click **Save** to create the model.</span></span>

   <span data-ttu-id="e759f-125">系统需要几分钟的时间准备模型。</span><span class="sxs-lookup"><span data-stu-id="e759f-125">It will take a couple minutes for the system to prepare your model.</span></span> <span data-ttu-id="e759f-126">准备就绪后，你可以执行第一轮培训。</span><span class="sxs-lookup"><span data-stu-id="e759f-126">After it's ready, you can perform the first round of training.</span></span>

<span data-ttu-id="e759f-127">有关更详细的说明，请参阅创建 [预测编码模型](predictive-coding-create-model.md)。</span><span class="sxs-lookup"><span data-stu-id="e759f-127">For more detailed instructions, see [Create a predictive coding model](predictive-coding-create-model.md).</span></span>

## <a name="step-2-perform-the-first-training-round"></a><span data-ttu-id="e759f-128">步骤 2：执行第一个培训轮</span><span class="sxs-lookup"><span data-stu-id="e759f-128">Step 2: Perform the first training round</span></span>

<span data-ttu-id="e759f-129">创建模型后，下一步是通过标记相关项或不相关项来完成第一轮培训。</span><span class="sxs-lookup"><span data-stu-id="e759f-129">After you create the model, the next step is to complete the first training round by labeling items as relevant or not relevant.</span></span>

1. <span data-ttu-id="e759f-130">打开审阅集，然后单击分析 **管理** 预测编码  >  **(预览) 。**</span><span class="sxs-lookup"><span data-stu-id="e759f-130">Open the review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

2. <span data-ttu-id="e759f-131">在" **预测编码模型 (预览)** 页面上，选择要训练的模型。</span><span class="sxs-lookup"><span data-stu-id="e759f-131">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

3. <span data-ttu-id="e759f-132">在"**概述"** 选项卡上的"**第 1 轮"下**，单击"**开始下一个培训轮"。**</span><span class="sxs-lookup"><span data-stu-id="e759f-132">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="e759f-133">将显示 **"** 培训"选项卡，其中包含要标记的 50 个项目。</span><span class="sxs-lookup"><span data-stu-id="e759f-133">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

4. <span data-ttu-id="e759f-134">查看每个文档，**然后选择阅读窗格** 底部的"相关"或"不相关"按钮以标记该文档。</span><span class="sxs-lookup"><span data-stu-id="e759f-134">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![将每个文档标记为相关或不相关](..\media\TrainModel1.png)

5. <span data-ttu-id="e759f-136">标记完所有 50 个项目后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="e759f-136">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="e759f-137">系统需要几分钟时间从你的标签"学习"并更新模型。</span><span class="sxs-lookup"><span data-stu-id="e759f-137">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="e759f-138">此过程完成后，将在"预测编码模型和预览模型"页上为模型 (**就绪)** 状态。</span><span class="sxs-lookup"><span data-stu-id="e759f-138">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

<span data-ttu-id="e759f-139">有关更详细的说明，请参阅 [训练预测编码模型](predictive-coding-train-model.md)。</span><span class="sxs-lookup"><span data-stu-id="e759f-139">For more detailed instructions, see [Train a predictive coding model](predictive-coding-train-model.md).</span></span>

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a><span data-ttu-id="e759f-140">步骤 3：将预测分数筛选器应用于审阅集内的项目</span><span class="sxs-lookup"><span data-stu-id="e759f-140">Step 3: Apply the prediction score filter to items in review set</span></span>

<span data-ttu-id="e759f-141">在租用一轮培训后，可以将预测分数筛选器应用于审阅集内的项目。</span><span class="sxs-lookup"><span data-stu-id="e759f-141">After you perform at lease one training round, you can apply the prediction score filter to items in review set.</span></span> <span data-ttu-id="e759f-142">这样，你可以查看模型已预测为相关或不相关的项目。</span><span class="sxs-lookup"><span data-stu-id="e759f-142">This lets you review the items the model has predicted as relevant or not relevant.</span></span>   

1. <span data-ttu-id="e759f-143">打开审阅集。</span><span class="sxs-lookup"><span data-stu-id="e759f-143">Open the review set.</span></span>

   ![单击"筛选器"以显示"筛选器"飞出页](..\media\PredictionScoreFilter0.png)

   <span data-ttu-id="e759f-145">预加载的默认筛选器显示在审阅集页面的顶部。</span><span class="sxs-lookup"><span data-stu-id="e759f-145">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="e759f-146">你可以将这些设置保留为 **Any**。</span><span class="sxs-lookup"><span data-stu-id="e759f-146">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="e759f-147">单击 **"筛选器** "以显示" **筛选器** "飞出页。</span><span class="sxs-lookup"><span data-stu-id="e759f-147">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="e759f-148">展开 **"分析&** 编码"部分以显示一组筛选器。</span><span class="sxs-lookup"><span data-stu-id="e759f-148">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![分析与预测编码部分&分数筛选器](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="e759f-150">预测分数筛选器的命名约定是预测 **(模型名称) 。**</span><span class="sxs-lookup"><span data-stu-id="e759f-150">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="e759f-151">例如，名为模型 **A** 的模型预测分数筛选器名称是模型 **A** 预测 (预测) 。</span><span class="sxs-lookup"><span data-stu-id="e759f-151">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="e759f-152">选择想要使用预测分数筛选器，然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="e759f-152">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="e759f-153">在评价集页面上，单击预测分数筛选器下拉列表，然后键入预测分数范围的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="e759f-153">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="e759f-154">例如，以下屏幕截图显示了一个介于 **.5** 和 **1.0 之间的预测分数范围**。</span><span class="sxs-lookup"><span data-stu-id="e759f-154">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![预测分数筛选器的最小值和最大值](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="e759f-156">单击筛选器外部以自动将筛选器应用于审阅集。</span><span class="sxs-lookup"><span data-stu-id="e759f-156">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="e759f-157">在审阅集页面上显示指定范围内具有预测分数的文档列表。</span><span class="sxs-lookup"><span data-stu-id="e759f-157">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span>

<span data-ttu-id="e759f-158">有关更详细的说明，请参阅 [将预测筛选器应用于审阅集](predictive-coding-apply-prediction-filter.md)。</span><span class="sxs-lookup"><span data-stu-id="e759f-158">For more detailed instructions, see [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>

## <a name="step-4-perform-more-training-rounds"></a><span data-ttu-id="e759f-159">步骤 4：执行更多培训轮</span><span class="sxs-lookup"><span data-stu-id="e759f-159">Step 4: Perform more training rounds</span></span>

<span data-ttu-id="e759f-160">很可能，您必须执行更多培训轮，以对模块进行培训，以更好地预测审阅集内的相关和非相关项目。</span><span class="sxs-lookup"><span data-stu-id="e759f-160">More than likely, you'll have to perform more training rounds to train the module to better predict relevant and non-relevant items in the review set.</span></span> <span data-ttu-id="e759f-161">一般情况下，你将对模型进行足够的训练，直到它稳定到足以满足你的要求。</span><span class="sxs-lookup"><span data-stu-id="e759f-161">In general, you'll train the model enough times until it stabilizes enough to meet your requirements.</span></span>

<span data-ttu-id="e759f-162">有关详细信息，请参阅执行 [其他培训轮](predictive-coding-train-model.md#perform-additional-training-rounds)</span><span class="sxs-lookup"><span data-stu-id="e759f-162">For more information, see [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span></span>

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a><span data-ttu-id="e759f-163">步骤 5：应用最终预测分数筛选器，确定审阅的优先级</span><span class="sxs-lookup"><span data-stu-id="e759f-163">Step 5: Apply the final prediction score filter to prioritize review</span></span>

<span data-ttu-id="e759f-164">重复步骤 3 中的说明，将最终预测分数应用于审阅集，以在完成所有培训轮次并稳定模型后确定相关和非相关项目的审阅优先级。</span><span class="sxs-lookup"><span data-stu-id="e759f-164">Repeat the instructions in Step 3 to apply the final prediction score to the review set to prioritize the review of relevant and non-relevant items after you complete all the training rounds and stabilize the model.</span></span>
