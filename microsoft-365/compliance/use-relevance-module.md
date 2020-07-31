---
title: 使用相关性模块分析证据中的数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解相关性模块如何使用相关性工作流的说明以及数据调查（预览）中的培训步骤来分析证据中的数据。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64bd0101fd2a0804da9e513241a97bc9f133880e
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528158"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a><span data-ttu-id="7c4c8-103">使用相关性模块分析证据中的数据</span><span class="sxs-lookup"><span data-stu-id="7c4c8-103">Use the Relevance module to analyze data in evidence</span></span>

<span data-ttu-id="7c4c8-104">在数据调查（预览版）中，相关性模块包括与调查相关的相关文件的相关性培训和审核。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-104">In Data Investigations (Preview), the Relevance module includes the Relevance training and review of files related to an investigation.</span></span> <span data-ttu-id="7c4c8-105">相关性工作流如下所示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7c4c8-105">The Relevance workflow is shown and described as follows:</span></span>
  
![相关性工作流](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="7c4c8-107">**评估和跟踪周期**：</span><span class="sxs-lookup"><span data-stu-id="7c4c8-107">**Cycles of assessment and tracking**:</span></span>

  - <span data-ttu-id="7c4c8-108">**评估**：基于文件的随机样本启用早期评估，并使用此评估来应用决策，以确定预测编码过程的性能。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-108">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 

  - <span data-ttu-id="7c4c8-109">**跟踪**：计算并显示评估的中间结果，同时监视流程的统计有效性。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-109">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 

- <span data-ttu-id="7c4c8-110">**培训和跟踪周期**</span><span class="sxs-lookup"><span data-stu-id="7c4c8-110">**Cycles of training and tracking**</span></span>

  - <span data-ttu-id="7c4c8-111">**标记**：数据调查（预览版）基于专家对各个文件的迭代检查和标记，了解特定于每个问题的相关性条件。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-111">**Tag**: Data Investigations (Preview) learns the Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="7c4c8-112">**跟踪**：计算并显示相关培训的中间结果，同时监视流程的统计有效性。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-112">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="7c4c8-113">**批处理计算**：累积的和已知的相关性条件应用于整个文件集合，并为每个文件生成相关性分数。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-113">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="7c4c8-114">**决定**：应用于整个事例的分析结果在批量计算后显示，并显示用于进行文档审阅决定的数据。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-114">**Decide**: The results of the analysis applied to the entire case are displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="7c4c8-115">**测试**：可以测试结果以验证数据调查（预览）处理的有效性和有效性。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-115">**Test**: Results can be tested to verify the validity and effectiveness of the Data Investigations (Preview) processing.</span></span>

- <span data-ttu-id="7c4c8-116">**搜索**：一旦完成了相关性工作流，则在工作集内运行查询时，可以使用输出（如文档的已读百分比）来解决问题。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-116">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="7c4c8-117">相关培训和审阅指南</span><span class="sxs-lookup"><span data-stu-id="7c4c8-117">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="7c4c8-118">下面概述了相关培训和审查指南：</span><span class="sxs-lookup"><span data-stu-id="7c4c8-118">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="7c4c8-119">**错误和不一致**：如果在培训过程中进行了标记错误，请返回到之前的文件示例以更正这些错误。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-119">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="7c4c8-120">如果要更正的错误太多，或者案例或问题的新透视，则应由管理员重新定义相关性条件，并重新启动相关性培训。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-120">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="7c4c8-121">**标记和培训**：</span><span class="sxs-lookup"><span data-stu-id="7c4c8-121">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="7c4c8-122">应仅根据内容对文件进行标记。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-122">Files should be tagged based on content only.</span></span> <span data-ttu-id="7c4c8-123">请勿考虑元数据，例如保管人、date 或 file path。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-123">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="7c4c8-124">在标记文件时，不要在文本中考虑日期范围指示。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-124">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="7c4c8-125">在标记文件时不考虑嵌入的图形图像。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-125">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="7c4c8-126">"忽略应用于相关性的文本将在相关性中的文本视图中的显示文件内容中删除。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-126">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="7c4c8-127">如果 "忽略文本" 的值是在已启动相关性培训之后定义的，则新的被忽略的文本将应用于从定义该位置创建的示例文件。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-127">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="7c4c8-128">应慎重使用 Ignore Text 功能，因为它的使用可能会降低文件分析的性能</span><span class="sxs-lookup"><span data-stu-id="7c4c8-128">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="7c4c8-129">仅在必要时使用**跳过标签**选项。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-129">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="7c4c8-130">数据调查（预览版）不基于跳过的文件进行训练。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-130">Data Investigations (Preview) doesn't train based on skipped files.</span></span> <span data-ttu-id="7c4c8-131">在评估中，如果很难判断文件是否相关，最好在可能时标记相关（R）或不相关（NR），而不是选择 "**跳过**"。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-131">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="7c4c8-132">当数据调查（预览版）评估培训时，可以看到这些类型的文件的处理效果。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-132">When Data Investigations (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="7c4c8-133">即使具有少量提取文本的文件，也应在训练中将其标记为 R/NR，而不是 "Skip" （如果可能）。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-133">Even files with a small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="7c4c8-134">只要文件可读，并且可以将其标记为 R/NR，标记就会影响分类器。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-134">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="7c4c8-135">"**标记**" 选项卡上的 "显示的示例文件" 列表中的文件序列号允许用户返回到文件的原始显示顺序。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-135">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="7c4c8-136">您可以返回到任何示例并更改评估和培训集文件的标记。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-136">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="7c4c8-137">将在创建下一个示例时应用这些更改。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-137">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="7c4c8-138">在标记文件时，PDF 格式的 Excel 文件的处理方式应与本机 Excel 文件相同。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-138">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="7c4c8-139">如果不确定文件的相关性标记，请咨询专家。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-139">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="7c4c8-140">在相关性培训期间，标记错误可能会导致在进程中的时间丢失，并可能对总体结果的质量产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-140">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="7c4c8-141">关键字列表中定义的关键字将以颜色显示，以帮助用户在标记时确定相关文件。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-141">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="7c4c8-142">**批量计算**：由专家标记为 R/NR 的文件将获得0或100的分数。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-142">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="7c4c8-143">这适用于在批处理计算前进行的标记。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-143">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="7c4c8-144">如果专家在批量计算后将问题切换到空闲并继续标记此问题，则新标记的分数不会是100/0，而是原始分数。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-144">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="7c4c8-145">**问题和采样模式**：当用户工作完成时，将关闭问题（相关性培训为稳定和执行批量计算）、问题取消或其他用户正在处理问题。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-145">**Issues and sampling mode**: Issues are turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="7c4c8-146">相关培训中的步骤</span><span class="sxs-lookup"><span data-stu-id="7c4c8-146">Steps in Relevance training</span></span>

<span data-ttu-id="7c4c8-147">在 "**相关性 \> 跟踪**" 选项卡中，数据调查针对如何在处理过程中进行操作提供了建议，并执行了以下后续步骤。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-147">In the **Relevance \> Track** tab, Data investigations provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="7c4c8-148">如果在相关培训过程中建议执行以下每个步骤，则会对这些含义进行说明。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-148">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="7c4c8-149">标记/继续标记：专家对示例中的每个文件和问题执行的文件审阅和相关性标记。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-149">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="7c4c8-150">暗示：现有示例需要加上标记。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-150">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="7c4c8-151">评估/继续评估：支持早期验证案例问题相关性，并初步了解为当前事例导入的文件填充的相关性。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-151">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="7c4c8-152">暗示：需要或建议进行更多评估。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-152">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="7c4c8-153">培训/继续培训：在此过程中，数据调查从标记文件示例的专家那里获得，并在每个事例的上下文中找出与每个问题相关的相关性条件的功能。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-153">Training / Continue training: Process during which Data investigations learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="7c4c8-154">含义：此问题需要更多培训;应创建并标记下一个示例。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-154">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="7c4c8-155">批量计算：相关性过程，其中的数据调查采用培训阶段获取的知识，并将其应用于整个文件填充。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-155">Batch calculation: Relevance process in which Data investigations take the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="7c4c8-156">将评估相关文件组中的所有文件的相关性，并为其分配相关性分数。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-156">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="7c4c8-157">暗示：问题已稳定，可以执行批处理计算。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-157">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="7c4c8-158">追赶：相关性指示当专家在滚动负载方案中从其他文件加载中查看和标记所选文件的示例时。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-158">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="7c4c8-159">暗示：添加了新的负载，需要追赶才能继续工作。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-159">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="7c4c8-160">标记不一致：进程通过数据调查算法识别可能对分析产生负面影响的文件标记过程中的不一致情况。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-160">Tag inconsistencies: Process identifies, via a Data investigations algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="7c4c8-161">暗示：下一个示例将包含已在之前的示例中标记的文件，并且必须恢复它们的标记。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-161">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="7c4c8-162">更新分类器：允许用户应用标记或种子设定更改。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-162">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="7c4c8-163">暗示：可以应用标记和种子设定更改，而无需手动运行另一个相关性示例。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-163">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="7c4c8-164">保留：相关培训过程已完成。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-164">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="7c4c8-165">暗示：此时不需要相关培训。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-165">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="7c4c8-166">尽管数据调查引导您完成整个过程，但在不同的阶段使用建议的后续步骤，它还允许您在选项卡和页面之间导航，并做出选择，以解决与您的个人案例、问题或文档审阅过程相关的情况。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-166">Although Data investigations guide you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="7c4c8-167">可以接受或覆盖 "数据调查" 下一步处理选择。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-167">It is possible to accept or override Data investigations Next step processing choices.</span></span> <span data-ttu-id="7c4c8-168">如果要执行除建议的下一步之外的步骤，请单击对话框中展开的问题显示中列出的**下一步**，单击下一步旁边的 "**修改**" 按钮，然后选择另一个 "下一步" 选项。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-168">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7c4c8-169">在解锁后，某些选项可能仍处于禁用状态，因为在此过程中不支持使用这些选项。</span><span class="sxs-lookup"><span data-stu-id="7c4c8-169">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="7c4c8-170">更多信息</span><span class="sxs-lookup"><span data-stu-id="7c4c8-170">More information</span></span>

[<span data-ttu-id="7c4c8-171">了解相关性方面的评估</span><span class="sxs-lookup"><span data-stu-id="7c4c8-171">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7c4c8-172">标记和评估</span><span class="sxs-lookup"><span data-stu-id="7c4c8-172">Tagging and assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7c4c8-173">标记和相关性培训</span><span class="sxs-lookup"><span data-stu-id="7c4c8-173">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7c4c8-174">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="7c4c8-174">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7c4c8-175">根据结果做出决定</span><span class="sxs-lookup"><span data-stu-id="7c4c8-175">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7c4c8-176">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="7c4c8-176">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="7c4c8-177">查询证据中的数据</span><span class="sxs-lookup"><span data-stu-id="7c4c8-177">Query the data in evidence</span></span>](evidence-query.md)
