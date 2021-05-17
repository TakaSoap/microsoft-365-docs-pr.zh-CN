---
title: 跟踪数据中的相关性Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何查看和解释相关性培训状态和结果，了解 Advanced eDiscovery。
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769177"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="74aed-103">跟踪数据中的相关性Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="74aed-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="74aed-104">在Advanced eDiscovery中，"相关性跟踪"选项卡显示在"标记"选项卡中执行的相关性培训的计算有效性，并指示在相关性的迭代培训过程中要执行的下一步。</span><span class="sxs-lookup"><span data-stu-id="74aed-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="74aed-105">跟踪相关性培训状态</span><span class="sxs-lookup"><span data-stu-id="74aed-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="74aed-106">查看"相关性跟踪"中有关案例问题的以下详细信息，如下面的"问题名称"对话框的 **以下示例** 所示。</span><span class="sxs-lookup"><span data-stu-id="74aed-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="74aed-107">**评估**：此进度指示器显示到此点执行的相关性培训在错误边距方面达到评估目标的程度。</span><span class="sxs-lookup"><span data-stu-id="74aed-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="74aed-108">还会显示相关性培训结果的丰富内容。</span><span class="sxs-lookup"><span data-stu-id="74aed-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="74aed-109">**培训**：此颜色编码的进度指示器和工具提示指示相关性培训结果稳定性，以及显示针对每个问题标记的相关性培训样本数的数字刻度。</span><span class="sxs-lookup"><span data-stu-id="74aed-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="74aed-110">专家监视迭代相关性培训过程的进度。</span><span class="sxs-lookup"><span data-stu-id="74aed-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="74aed-111">**批量计算**：此进度指示器提供有关批计算完成的信息。</span><span class="sxs-lookup"><span data-stu-id="74aed-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="74aed-112">**下一** 步：显示下一步执行的建议。</span><span class="sxs-lookup"><span data-stu-id="74aed-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="74aed-113">示例中显示了一个成功完成的问题评估，由已完成的颜色进度指示器和选中标记指示。</span><span class="sxs-lookup"><span data-stu-id="74aed-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="74aed-114">标记正在进行，但这种情况仍被视为不稳定 (稳定性状态也显示在工具提示) 。</span><span class="sxs-lookup"><span data-stu-id="74aed-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="74aed-115">下一步的建议是"培训"。</span><span class="sxs-lookup"><span data-stu-id="74aed-115">The next step recommendation is "Training".</span></span> 
  
    ![相关性跟踪培训第 1 步](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="74aed-117">展开的视图显示其他信息和选项。</span><span class="sxs-lookup"><span data-stu-id="74aed-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="74aed-118">显示的当前误差区是当前评估状态中撤回的错误边距，因为现有评估 (标记) 文件。</span><span class="sxs-lookup"><span data-stu-id="74aed-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="74aed-119">通过清除每个问题的"评估"复选框，然后清除"所有问题"，可以绕过评估阶段。</span><span class="sxs-lookup"><span data-stu-id="74aed-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="74aed-120">但是，因此，此问题将没有任何统计信息。</span><span class="sxs-lookup"><span data-stu-id="74aed-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="74aed-121">>执行 **评估** 前，才能清除"评估"复选框。</span><span class="sxs-lookup"><span data-stu-id="74aed-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="74aed-122">如果一种情况下存在多个问题，则仅在清除每个问题的复选框时绕过评估</span><span class="sxs-lookup"><span data-stu-id="74aed-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="74aed-123">当第一组示例文件未完成评估时，评估可能是标记更多文件的下一步。</span><span class="sxs-lookup"><span data-stu-id="74aed-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="74aed-124">在 **相关性** \> **跟踪** 中，培训进度指示器和工具提示指示达到稳定性所需的额外样本的估计数量。</span><span class="sxs-lookup"><span data-stu-id="74aed-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="74aed-125">此估计提供了所需的其他培训的指南。</span><span class="sxs-lookup"><span data-stu-id="74aed-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![相关性跟踪培训](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="74aed-127">完成标记后，如果需要继续培训，请单击"**培训"。**</span><span class="sxs-lookup"><span data-stu-id="74aed-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="74aed-128">另一个示例文件集从加载的文件集生成，用于其他培训。</span><span class="sxs-lookup"><span data-stu-id="74aed-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="74aed-129">然后返回到"标记"选项卡，以标记和训练更多文件。</span><span class="sxs-lookup"><span data-stu-id="74aed-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="74aed-130">达到稳定的培训级别</span><span class="sxs-lookup"><span data-stu-id="74aed-130">Reaching stable training levels</span></span>

<span data-ttu-id="74aed-131">在评估文件获得稳定级别的培训后，Advanced eDiscovery准备批量计算。</span><span class="sxs-lookup"><span data-stu-id="74aed-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74aed-132">通常，在三个稳定的培训示例之后，下一步是"批量计算"。</span><span class="sxs-lookup"><span data-stu-id="74aed-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="74aed-133">可能有例外情况，例如，在先前示例中对文件标记进行了更改或添加种子文件时。</span><span class="sxs-lookup"><span data-stu-id="74aed-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="74aed-134">执行批处理计算</span><span class="sxs-lookup"><span data-stu-id="74aed-134">Performing Batch calculation</span></span>

<span data-ttu-id="74aed-135">当进度栏显示稳定培训状态、工具提示中的选中标记和稳定状态时，批计算作为下一步执行。) 批处理计算将相关性培训期间获得的知识应用于整个文件填充，以评估文件的相关性并分配相关性分数。 (</span><span class="sxs-lookup"><span data-stu-id="74aed-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="74aed-136">当存在多个问题时，将按问题进行批量计算。</span><span class="sxs-lookup"><span data-stu-id="74aed-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="74aed-137">在批计算过程中，在处理所有文件时将监视进度。</span><span class="sxs-lookup"><span data-stu-id="74aed-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="74aed-138">此处建议的下一步是"无"，这表示此时无需其他迭代相关性培训。</span><span class="sxs-lookup"><span data-stu-id="74aed-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="74aed-139">下一个阶段是" **相关性决定 \> "** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="74aed-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="74aed-140">如果要在批量计算后导入新文件，管理员可以将导入的文件添加到新负载中。</span><span class="sxs-lookup"><span data-stu-id="74aed-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74aed-141">如果在批 **计算过程中** 单击"取消"，则进程将保存已执行操作。</span><span class="sxs-lookup"><span data-stu-id="74aed-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="74aed-142">如果再次运行批处理计算，则该过程将继续从上次执行点开始。</span><span class="sxs-lookup"><span data-stu-id="74aed-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="74aed-143">评估标记一致性</span><span class="sxs-lookup"><span data-stu-id="74aed-143">Assessing tagging consistency</span></span>

<span data-ttu-id="74aed-144">如果文件标记不一致，可能会影响分析。</span><span class="sxs-lookup"><span data-stu-id="74aed-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="74aed-145">当Advanced eDiscovery不理想或不确定一致性时，可以使用标记一致性过程。</span><span class="sxs-lookup"><span data-stu-id="74aed-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="74aed-146">返回可能标记不一致的文件的列表，并在必要时检查和重新标记这些文件。</span><span class="sxs-lookup"><span data-stu-id="74aed-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74aed-147">在评估后的七个或多个培训轮之后，可以在相关性跟踪问题详细结果培训进度中查看标记一 \>  \>  \>  \> **致性**。</span><span class="sxs-lookup"><span data-stu-id="74aed-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="74aed-148">每次针对一个问题完成此审阅。</span><span class="sxs-lookup"><span data-stu-id="74aed-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="74aed-149">在 **"相关性 \> 跟踪"** 中，展开问题行。</span><span class="sxs-lookup"><span data-stu-id="74aed-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="74aed-150">在"下一步 **"的右侧，单击**"修改 **"。**</span><span class="sxs-lookup"><span data-stu-id="74aed-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="74aed-151">选择 **标记不一** 致作为下一 **步** 选项，在七个培训示例后，**然后单击确定。**</span><span class="sxs-lookup"><span data-stu-id="74aed-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="74aed-152">选择 **"标记不一致"。**</span><span class="sxs-lookup"><span data-stu-id="74aed-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="74aed-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span><span class="sxs-lookup"><span data-stu-id="74aed-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="74aed-154">单击 **"计算** "提交更改。</span><span class="sxs-lookup"><span data-stu-id="74aed-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="74aed-155">标记不一致后的下一步是"培训"。</span><span class="sxs-lookup"><span data-stu-id="74aed-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="74aed-156">查看和使用相关性结果</span><span class="sxs-lookup"><span data-stu-id="74aed-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="74aed-157">在"**相关性 \> 跟踪"** 选项卡中，展开问题行，然后单击"详细结果 **"旁边的**"查看 **"。**</span><span class="sxs-lookup"><span data-stu-id="74aed-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="74aed-158">将显示"详细结果"窗格，如下所示并如下所述。</span><span class="sxs-lookup"><span data-stu-id="74aed-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![相关性培训详细结果](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="74aed-160">标记摘要</span><span class="sxs-lookup"><span data-stu-id="74aed-160">Tagging summary</span></span>

 <span data-ttu-id="74aed-161">在下面的示例中，标记摘要显示每个评估、培训和跟进文件标记过程的总计。</span><span class="sxs-lookup"><span data-stu-id="74aed-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![相关性跟踪标记摘要](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="74aed-163">关键字</span><span class="sxs-lookup"><span data-stu-id="74aed-163">Keywords</span></span>

<span data-ttu-id="74aed-164">关键字是文件中唯一的字符串、字词、短语或字词序列，Advanced eDiscovery标识为文件是否相关的重要指标。</span><span class="sxs-lookup"><span data-stu-id="74aed-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="74aed-165">"包含"列列出标记为"相关"的文件的关键字和权重，"排除"列列出了标记为"不相关"的文件的关键字和权重。</span><span class="sxs-lookup"><span data-stu-id="74aed-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="74aed-166">Advanced eDiscovery负值或正关键字权重值。</span><span class="sxs-lookup"><span data-stu-id="74aed-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="74aed-167">权重越高，在批计算过程中为关键字出现的文件分配的相关性分数越高。</span><span class="sxs-lookup"><span data-stu-id="74aed-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="74aed-168">关键字Advanced eDiscovery列表可用于补充由专家构建的列表，或作为文件审阅过程中任何时间点的间接性检查。</span><span class="sxs-lookup"><span data-stu-id="74aed-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="74aed-169">培训进度</span><span class="sxs-lookup"><span data-stu-id="74aed-169">Training progress</span></span>

<span data-ttu-id="74aed-170">" **培训进度** "窗格包括培训进度图和质量指示器显示，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="74aed-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![相关性跟踪培训进度](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="74aed-172">**培训质量指示器**：显示标记一致性的分级，如下所示：</span><span class="sxs-lookup"><span data-stu-id="74aed-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="74aed-173">**良好**：文件一致标记。</span><span class="sxs-lookup"><span data-stu-id="74aed-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="74aed-174"> (绿色) </span><span class="sxs-lookup"><span data-stu-id="74aed-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="74aed-175">**中**：某些文件标记不一致。</span><span class="sxs-lookup"><span data-stu-id="74aed-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="74aed-176"> (黄色) </span><span class="sxs-lookup"><span data-stu-id="74aed-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="74aed-177">**警告**：许多文件标记不一致。</span><span class="sxs-lookup"><span data-stu-id="74aed-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="74aed-178"> (红色) </span><span class="sxs-lookup"><span data-stu-id="74aed-178">(Red light displayed)</span></span>

<span data-ttu-id="74aed-179">**培训进度图**：显示与 F 度量值比较的许多相关性培训周期后相关性培训稳定性的程度。</span><span class="sxs-lookup"><span data-stu-id="74aed-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="74aed-180">随着我们在整个图中从左向右移动，置信区间将缩小，并随 F 度量一起通过 Advanced eDiscovery Relevance 用于确定相关性培训结果优化时的稳定性。</span><span class="sxs-lookup"><span data-stu-id="74aed-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74aed-181">相关性使用 F2，这是 F 度量指标，其中 Recall 接收的权重是 Precision 的两倍。</span><span class="sxs-lookup"><span data-stu-id="74aed-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="74aed-182">对于高丰富度 (超过 25%) ，相关性使用 F1 (1：1 比率) 。</span><span class="sxs-lookup"><span data-stu-id="74aed-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="74aed-183">F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span><span class="sxs-lookup"><span data-stu-id="74aed-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="74aed-184">批处理计算结果</span><span class="sxs-lookup"><span data-stu-id="74aed-184">Batch calculation results</span></span>

<span data-ttu-id="74aed-185">" **批处理计算结果** "窗格包括按相关性分数的文件数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="74aed-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="74aed-186">**Success**</span><span class="sxs-lookup"><span data-stu-id="74aed-186">**Success**</span></span>
  
- <span data-ttu-id="74aed-187">**空**：不包含文本，例如，仅包含空格/制表符</span><span class="sxs-lookup"><span data-stu-id="74aed-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="74aed-188">**失败**：由于过大或无法读取</span><span class="sxs-lookup"><span data-stu-id="74aed-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="74aed-189">**已** 忽略：由于尺寸过大</span><span class="sxs-lookup"><span data-stu-id="74aed-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="74aed-190">**Neb一**：包含无意义的文本或没有与该问题相关的功能</span><span class="sxs-lookup"><span data-stu-id="74aed-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="74aed-191">Empty、Failed、Ignored 或 Neb一起会收到相关性分数 -1。</span><span class="sxs-lookup"><span data-stu-id="74aed-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="74aed-192">培训统计信息</span><span class="sxs-lookup"><span data-stu-id="74aed-192">Training statistics</span></span>

<span data-ttu-id="74aed-193">"**培训统计信息**"窗格根据相关性培训中的结果Advanced eDiscovery统计信息和图形。</span><span class="sxs-lookup"><span data-stu-id="74aed-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![相关性跟踪培训统计数据](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="74aed-195">此视图显示以下内容：</span><span class="sxs-lookup"><span data-stu-id="74aed-195">This view shows the following:</span></span>
  
- <span data-ttu-id="74aed-196">**Review-recall ratio**： Comparison of results according to Relevance scores in a hypothetically linear review.</span><span class="sxs-lookup"><span data-stu-id="74aed-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="74aed-197">根据审阅集大小集，估计回收时间。</span><span class="sxs-lookup"><span data-stu-id="74aed-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="74aed-198">**参数**：与审阅集相关的累积计算统计信息（相对于整个案例的文件填充）。</span><span class="sxs-lookup"><span data-stu-id="74aed-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="74aed-199">**查看**：要基于此截止时间查看的文件百分比。</span><span class="sxs-lookup"><span data-stu-id="74aed-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="74aed-200">**恢复**：审阅集内相关文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="74aed-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="74aed-201">**按相关性分数分布**：左侧显示深灰色的文件低于截止分数。</span><span class="sxs-lookup"><span data-stu-id="74aed-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="74aed-202">工具提示显示与总文件相关的审阅文件集内文件的相关性分数和相关百分比。</span><span class="sxs-lookup"><span data-stu-id="74aed-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
