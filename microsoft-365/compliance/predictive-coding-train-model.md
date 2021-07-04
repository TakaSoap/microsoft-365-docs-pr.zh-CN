---
title: 在 Advanced eDiscovery 中训练预测编码Advanced eDiscovery
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
description: ''
ms.openlocfilehash: 84ec1ad42f2cec2487debe7160a3f24e09bdd830
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288187"
---
# <a name="train-a-predictive-coding-model-preview"></a><span data-ttu-id="d9849-102">训练预测编码模型 (预览) </span><span class="sxs-lookup"><span data-stu-id="d9849-102">Train a predictive coding model (preview)</span></span>

<span data-ttu-id="d9849-103">在 Advanced eDiscovery 创建预测编码模型后，下一步是执行第一个培训轮，以针对审阅集内的相关内容和非相关内容对模型进行培训。</span><span class="sxs-lookup"><span data-stu-id="d9849-103">After you create a predictive coding model in Advanced eDiscovery, the next step is to performing the first training round to train the model on what is relevant and non-relevant content in your review set.</span></span> <span data-ttu-id="d9849-104">完成第一轮培训后，可以执行后续培训轮，以提高模型预测相关和非相关内容的能力。</span><span class="sxs-lookup"><span data-stu-id="d9849-104">After you complete the first round of training, you can perform subsequent training rounds to improve the model's ability to predict relevant and non-relevant content.</span></span>

<span data-ttu-id="d9849-105">若要查看预测编码工作流，请参阅[了解预测编码Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)</span><span class="sxs-lookup"><span data-stu-id="d9849-105">To review the predictive coding workflow, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md#the-predictive-coding-workflow)</span></span>

## <a name="before-you-train-a-model"></a><span data-ttu-id="d9849-106">在训练模型之前</span><span class="sxs-lookup"><span data-stu-id="d9849-106">Before you train a model</span></span>

- <span data-ttu-id="d9849-107">在培训轮中，根据文档中内容的相关性将项目标记为"相关"或"不相关"。</span><span class="sxs-lookup"><span data-stu-id="d9849-107">During a training round, label items as **Relevant** or **Not relevant** based on the relevancy of the content in the document.</span></span> <span data-ttu-id="d9849-108">不要将决策基于元数据字段中的值。</span><span class="sxs-lookup"><span data-stu-id="d9849-108">Don't base your decision on the values in the metadata fields.</span></span> <span data-ttu-id="d9849-109">例如，对于电子邮件或Teams对话，不要根据邮件参与者做出标签决定。</span><span class="sxs-lookup"><span data-stu-id="d9849-109">For example, for email messages or Teams conversations, don't base your labeling decision on the message participants.</span></span>

## <a name="train-a-model-for-the-first-time"></a><span data-ttu-id="d9849-110">首次训练模型</span><span class="sxs-lookup"><span data-stu-id="d9849-110">Train a model for the first time</span></span>

1. <span data-ttu-id="d9849-111">In the Microsoft 365 合规中心， open an Advanced eDiscovery case and then select the **Review sets** tab.</span><span class="sxs-lookup"><span data-stu-id="d9849-111">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="d9849-112">打开审阅集，然后单击分析 **管理** 预测  >  **编码 (预览) 。**</span><span class="sxs-lookup"><span data-stu-id="d9849-112">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

3. <span data-ttu-id="d9849-113">在" **预测编码模型 (预览)** 页面上，选择要训练的模型。</span><span class="sxs-lookup"><span data-stu-id="d9849-113">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

4. <span data-ttu-id="d9849-114">在"**概述"** 选项卡上的"**第 1 轮"下**，单击"**开始下一个培训轮"。**</span><span class="sxs-lookup"><span data-stu-id="d9849-114">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="d9849-115">将显示 **"** 培训"选项卡，其中包含要标记的 50 个项目。</span><span class="sxs-lookup"><span data-stu-id="d9849-115">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

5. <span data-ttu-id="d9849-116">查看每个文档，**然后选择阅读窗格** 底部的"相关"或"不相关"按钮以标记该文档。</span><span class="sxs-lookup"><span data-stu-id="d9849-116">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![将每个文档标记为相关或不相关](..\media\TrainModel1.png)

6. <span data-ttu-id="d9849-118">标记完所有 50 个项目后，单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="d9849-118">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="d9849-119">系统需要几分钟时间从你的标签"学习"并更新模型。</span><span class="sxs-lookup"><span data-stu-id="d9849-119">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="d9849-120">此过程完成后，将在"预测编码模型和预览模型"页上为模型 (**就绪)** 状态。</span><span class="sxs-lookup"><span data-stu-id="d9849-120">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

## <a name="perform-additional-training-rounds"></a><span data-ttu-id="d9849-121">执行其他培训轮</span><span class="sxs-lookup"><span data-stu-id="d9849-121">Perform additional training rounds</span></span>

<span data-ttu-id="d9849-122">执行第一轮培训后，可以按照上一部分中的步骤执行后续培训轮。</span><span class="sxs-lookup"><span data-stu-id="d9849-122">After you perform the first round of training, you can perform subsequent training rounds by following the steps in the previous section.</span></span> <span data-ttu-id="d9849-123">唯一的区别是，将在"模型概述"选项卡上更新培训 **轮** 的数量。例如，执行第一轮培训后，可以 **单击"开始** 下一个培训轮"开始第二轮培训。</span><span class="sxs-lookup"><span data-stu-id="d9849-123">The only difference is the number of the training round will be updated on the model **Overview** tab. For example, after performing the first training round, you can click **Start next training round** to start the second round of training.</span></span> <span data-ttu-id="d9849-124">等等。</span><span class="sxs-lookup"><span data-stu-id="d9849-124">And so on.</span></span>

<span data-ttu-id="d9849-125">每组培训 (进行中和已完成) 都将显示在模型的"培训"选项卡上。 </span><span class="sxs-lookup"><span data-stu-id="d9849-125">Each round of training (both those in progress and those that are complete) is displayed on the **Training** tab for the model.</span></span> <span data-ttu-id="d9849-126">选择培训轮时，将显示一个包含该轮的信息和指标的飞出页。</span><span class="sxs-lookup"><span data-stu-id="d9849-126">When you select a training round, a flyout page with information and metrics for the round is displayed.</span></span>

## <a name="what-happens-after-you-perform-a-training-round"></a><span data-ttu-id="d9849-127">执行培训轮后会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="d9849-127">What happens after you perform a training round</span></span>

<span data-ttu-id="d9849-128">执行第一个培训轮之后，将启动一个执行下列操作的工作：</span><span class="sxs-lookup"><span data-stu-id="d9849-128">After you perform the first training round, a job is started that does the following things:</span></span>

- <span data-ttu-id="d9849-129">根据你在培训集内标记 40 个项目时如何，模型会从你的标签中学习并更新自身，以变得更准确。</span><span class="sxs-lookup"><span data-stu-id="d9849-129">Based on how you labeled the 40 items in the training set, the model learns from your labeling and updates itself to become more accurate.</span></span>

- <span data-ttu-id="d9849-130">然后，模型将处理整个审阅集内的每一项，并分配一个介于 0 和 **1** 之间（不相关的 () 和 **1 (相关的) ）。**</span><span class="sxs-lookup"><span data-stu-id="d9849-130">The model then processes each item in the entire review set and assigns a prediction score between **0** (not relevant) and **1** (relevant).</span></span>

- <span data-ttu-id="d9849-131">模型为在培训轮中标记的控件集的 10 个项目分配预测分数。</span><span class="sxs-lookup"><span data-stu-id="d9849-131">The model assigns a prediction score to the 10 items in the control set that you labeled during the training round.</span></span> <span data-ttu-id="d9849-132">模型会将这 10 个项目的预测分数与在培训轮中分配给该项目的实际标签进行比较。</span><span class="sxs-lookup"><span data-stu-id="d9849-132">The model compares the prediction score of these 10 items with the actual label that you assigned to the item during the training round.</span></span> <span data-ttu-id="d9849-133">基于此比较，模型标识了 (控件集混淆矩阵) 评估模型预测性能的分类方法：</span><span class="sxs-lookup"><span data-stu-id="d9849-133">Based on this comparison, the model identifies the following classification (called the *Control set confusion matrix*) to assess the model's prediction performance:</span></span>

  <br>

  ****

  |<span data-ttu-id="d9849-134">标签</span><span class="sxs-lookup"><span data-stu-id="d9849-134">Label</span></span>|<span data-ttu-id="d9849-135">模型预测项目相关</span><span class="sxs-lookup"><span data-stu-id="d9849-135">Model predicts item is relevant</span></span>|<span data-ttu-id="d9849-136">模型预测项目不相关</span><span class="sxs-lookup"><span data-stu-id="d9849-136">Model predicts item is not relevant</span></span>|
  |---|---|---|
  |<span data-ttu-id="d9849-137">**审阅者标签项（如相关）**</span><span class="sxs-lookup"><span data-stu-id="d9849-137">**Reviewer labels item as relevant**</span></span>|<span data-ttu-id="d9849-138">True positive</span><span class="sxs-lookup"><span data-stu-id="d9849-138">True positive</span></span>|<span data-ttu-id="d9849-139">误报</span><span class="sxs-lookup"><span data-stu-id="d9849-139">False positive</span></span>|
  |<span data-ttu-id="d9849-140">**审阅者标签项不相关**</span><span class="sxs-lookup"><span data-stu-id="d9849-140">**Reviewer labels item as not relevant**</span></span>|<span data-ttu-id="d9849-141">假负</span><span class="sxs-lookup"><span data-stu-id="d9849-141">False negative</span></span>|<span data-ttu-id="d9849-142">True negative</span><span class="sxs-lookup"><span data-stu-id="d9849-142">True negative</span></span>|
  |

  <span data-ttu-id="d9849-143">基于这些比较，模型派生 F 分数、精度和调用指标的值以及每个指标的误差范围。</span><span class="sxs-lookup"><span data-stu-id="d9849-143">Based on these comparisons, the model derives values for the F-score, precision, and recall metrics and the margin of error for each one.</span></span> <span data-ttu-id="d9849-144">这些模型性能指标的分数显示在培训轮的飞出页面上。</span><span class="sxs-lookup"><span data-stu-id="d9849-144">Scores for these model performance metrics are displayed on a flyout page for the training round.</span></span> <span data-ttu-id="d9849-145">有关这些指标的说明，请参阅预测 [编码参考](predictive-coding-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="d9849-145">For a description of these metrics, see [Predictive coding reference](predictive-coding-reference.md).</span></span>

- <span data-ttu-id="d9849-146">最后，模型确定将用于下一个培训轮的接下来的 50 个项目。</span><span class="sxs-lookup"><span data-stu-id="d9849-146">Finally, the model determines the next 50 items that will be used for the next training round.</span></span> <span data-ttu-id="d9849-147">这一次，模型可能会从控件集选择 20 个项目和审阅集的 30 个新项，并指定这些项目作为下一轮的培训集。</span><span class="sxs-lookup"><span data-stu-id="d9849-147">This time, the model might select 20 items from the control set and 30 new items from the review set and designate them as the training set for the next round.</span></span> <span data-ttu-id="d9849-148">下一轮培训的采样未进行统一采样。</span><span class="sxs-lookup"><span data-stu-id="d9849-148">The sampling for the next training round is not uniformly sampled.</span></span> <span data-ttu-id="d9849-149">模型将优化审阅集内项目的采样选择，以选择预测不明确的项目，这意味着预测分数在 0.5 范围内。</span><span class="sxs-lookup"><span data-stu-id="d9849-149">The model will optimize the sampling selection of items from the review set to select items where the prediction is ambiguous, which means the prediction score is in the 0.5 range.</span></span> <span data-ttu-id="d9849-150">此过程称为偏 *置选择*。</span><span class="sxs-lookup"><span data-stu-id="d9849-150">This process is known as *biased selection*.</span></span>

### <a name="what-happens-after-you-perform-subsequent-training-rounds"></a><span data-ttu-id="d9849-151">执行后续培训轮后会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="d9849-151">What happens after you perform subsequent training rounds</span></span>

<span data-ttu-id="d9849-152">执行第一个培训 (之后执行后续培训) ，模型将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d9849-152">After you perform subsequent training rounds (after the first training round), the model does the following things:</span></span>

- <span data-ttu-id="d9849-153">模型将基于你应用于该轮培训中培训集的标签进行更新。</span><span class="sxs-lookup"><span data-stu-id="d9849-153">The model is updated based on the labels that you applied to the training set in that round of training.</span></span>

- <span data-ttu-id="d9849-154">系统计算模型对控件集内项目预测的分数，并检查该分数是否与控件集内项目的标记方式一致。</span><span class="sxs-lookup"><span data-stu-id="d9849-154">The system evaluates the model's prediction score on the items in the control set and check whether the score aligns with how you labeled items in the control set.</span></span> <span data-ttu-id="d9849-155">评估针对所有培训轮的控件集的所有标记项目执行。</span><span class="sxs-lookup"><span data-stu-id="d9849-155">The evaluation is performed on all labeled items from control set for all training rounds.</span></span> <span data-ttu-id="d9849-156">此评估的结果将合并到模型"概述 **"** 选项卡上的仪表板中。</span><span class="sxs-lookup"><span data-stu-id="d9849-156">The results of this evaluation are incorporated in the dashboard on the **Overview** tab for the model.</span></span>

- <span data-ttu-id="d9849-157">更新的模型重新处理审阅集内的每一项，并为每个项分配更新后预测分数。</span><span class="sxs-lookup"><span data-stu-id="d9849-157">The updated model reprocesses every item in the review set and assign each item an updated prediction score.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d9849-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d9849-158">Next steps</span></span>

<span data-ttu-id="d9849-159">执行第一轮培训后，可以执行更多培训轮或将模型预测分数筛选器应用于审阅集，以查看模型已预测为相关或不相关的项目。</span><span class="sxs-lookup"><span data-stu-id="d9849-159">After you perform the first training round, you can perform more training rounds or apply the model's prediction score filter to the review set to view the items the model has predicted as relevant or not relevant.</span></span> <span data-ttu-id="d9849-160">有关详细信息，请参阅将 [预测分数筛选器应用于审阅集](predictive-coding-apply-prediction-filter.md)。</span><span class="sxs-lookup"><span data-stu-id="d9849-160">For more information, see [Apply a prediction score filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>
