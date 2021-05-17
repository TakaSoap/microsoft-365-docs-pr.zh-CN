---
title: 使用相关性模块分析数据Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解相关性模块如何分析证据数据，并说明相关性工作流以及 Advanced eDiscovery。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286058"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="a1130-103">使用相关性模块分析数据Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a1130-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="a1130-104">在Advanced eDiscovery中，相关性模块包括与案例相关的文件的相关性培训和审阅。</span><span class="sxs-lookup"><span data-stu-id="a1130-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="a1130-105">若要使用相关性工作流，请转到管理审阅集内的审阅集，然后单击"显示相关性"。</span><span class="sxs-lookup"><span data-stu-id="a1130-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="a1130-106">在启动工作流之前，需要完成几个步骤：</span><span class="sxs-lookup"><span data-stu-id="a1130-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="a1130-107">进程：添加到审阅集的每个负载集在此处将显示为"容器"。</span><span class="sxs-lookup"><span data-stu-id="a1130-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="a1130-108">需要先处理这些文档，然后才能将它们添加到相关性模块;您也可以在这里将它们标记为针对特定问题的种子或预标记。</span><span class="sxs-lookup"><span data-stu-id="a1130-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="a1130-109">添加到相关性：在"相关性加载"下，可以添加已处理到相关性的文档 \> ，使其可用于培训。</span><span class="sxs-lookup"><span data-stu-id="a1130-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="a1130-110">相关性工作流的显示和描述如下：</span><span class="sxs-lookup"><span data-stu-id="a1130-110">The Relevance workflow is shown and described as follows:</span></span>
  
![相关性工作流](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="a1130-112">**评估和跟踪周期**：</span><span class="sxs-lookup"><span data-stu-id="a1130-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="a1130-113">**评估**：启用基于随机文件样本的早期评估，并使用此评估应用决策来确定预测编码过程的性能。</span><span class="sxs-lookup"><span data-stu-id="a1130-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="a1130-114">**跟踪**：在监视过程的统计有效性时计算并显示评估的临时结果。</span><span class="sxs-lookup"><span data-stu-id="a1130-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="a1130-115">**培训和跟踪周期**</span><span class="sxs-lookup"><span data-stu-id="a1130-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="a1130-116">**Tag**：Advanced eDiscovery根据专家的迭代审阅和单个文件标记来了解特定于每个问题的相关性条件。</span><span class="sxs-lookup"><span data-stu-id="a1130-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="a1130-117">**跟踪**：计算并显示相关性培训的临时结果，同时监视过程的统计有效性。</span><span class="sxs-lookup"><span data-stu-id="a1130-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="a1130-118">**批量计算**：累积和学习的相关性条件将应用于整个文件集合，并针对每个文件生成相关性分数。</span><span class="sxs-lookup"><span data-stu-id="a1130-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="a1130-119">**决定**：应用于整个案例的分析结果在批计算后显示，并且用于做出文档审阅决策的数据也显示。</span><span class="sxs-lookup"><span data-stu-id="a1130-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="a1130-120">**测试**：可以测试结果，以验证处理过程的有效性Advanced eDiscovery有效性。</span><span class="sxs-lookup"><span data-stu-id="a1130-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="a1130-121">**搜索**：相关性工作流完成后，在审阅集内运行查询时，可以使用针对问题的文档的读取百分点值等输出。</span><span class="sxs-lookup"><span data-stu-id="a1130-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="a1130-122">相关性培训和审阅指南</span><span class="sxs-lookup"><span data-stu-id="a1130-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="a1130-123">以下是相关性培训和审阅指南的概述：</span><span class="sxs-lookup"><span data-stu-id="a1130-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="a1130-124">**错误和不一致**：如果在培训期间出现标记错误，请返回到以前的文件示例以更正错误。</span><span class="sxs-lookup"><span data-stu-id="a1130-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="a1130-125">如果错误太多需要更正，或者有新的案例或问题视角，则管理员应重新定义相关性条件，并重新启动相关性培训。</span><span class="sxs-lookup"><span data-stu-id="a1130-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="a1130-126">**标记和培训**：</span><span class="sxs-lookup"><span data-stu-id="a1130-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="a1130-127">文件应仅基于内容进行标记。</span><span class="sxs-lookup"><span data-stu-id="a1130-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="a1130-128">不考虑元数据，如保管人、日期或文件路径。</span><span class="sxs-lookup"><span data-stu-id="a1130-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="a1130-129">标记文件时，不考虑文本中的日期范围指示。</span><span class="sxs-lookup"><span data-stu-id="a1130-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="a1130-130">标记文件时，不考虑嵌入的图形图像。</span><span class="sxs-lookup"><span data-stu-id="a1130-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="a1130-131">忽略应用于相关性的文本将在"相关性"的文本视图中的显示文件内容中删除。</span><span class="sxs-lookup"><span data-stu-id="a1130-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="a1130-132">如果 Ignore 文本的值是在相关性培训启动之后定义的，则新的忽略文本将应用于从定义该文本的位置创建的示例文件。</span><span class="sxs-lookup"><span data-stu-id="a1130-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="a1130-133">应谨慎使用"忽略文本"功能，因为该功能的使用可能会降低文件分析的性能</span><span class="sxs-lookup"><span data-stu-id="a1130-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="a1130-134">仅在必要时 **使用"** 跳过标记"选项。</span><span class="sxs-lookup"><span data-stu-id="a1130-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="a1130-135">Advanced eDiscovery未基于跳过的文件进行训练。</span><span class="sxs-lookup"><span data-stu-id="a1130-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="a1130-136">在评估中，如果很难判断文件是否相关，最好尽可能标记为"相关 (R) "或"不相关的 (NR) "，而不是选择"跳过 **"。**</span><span class="sxs-lookup"><span data-stu-id="a1130-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="a1130-137">当Advanced eDiscovery评估培训时，可以看到这些类型的文件的处理情况。</span><span class="sxs-lookup"><span data-stu-id="a1130-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="a1130-138">即使具有非常少量的提取文本的文件也应在培训中标记为 R/NR，而不是"跳过"（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="a1130-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="a1130-139">只要文件可读且可标记为 R/NR，标记就可能会影响分类器。</span><span class="sxs-lookup"><span data-stu-id="a1130-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="a1130-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span><span class="sxs-lookup"><span data-stu-id="a1130-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="a1130-141">你可以返回任何示例并更改评估和培训集文件的标记。</span><span class="sxs-lookup"><span data-stu-id="a1130-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="a1130-142">这些更改将在创建下一个示例时应用。</span><span class="sxs-lookup"><span data-stu-id="a1130-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="a1130-143">在Excel文件时，应处理 PDF 格式Excel扫描的文件。</span><span class="sxs-lookup"><span data-stu-id="a1130-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="a1130-144">如果对文件的相关性标记有疑问，请咨询专家。</span><span class="sxs-lookup"><span data-stu-id="a1130-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="a1130-145">相关性培训期间不正确的标记可能导致稍后在过程中丢失时间，并且也可能对总体结果的质量产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="a1130-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="a1130-146">关键字列表中定义的关键字将显示为颜色，以帮助用户在标记时标识相关文件。</span><span class="sxs-lookup"><span data-stu-id="a1130-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="a1130-147">**批量计算**：由专家标记为 R/NR 的文件将获得 0 或 100 的分数。</span><span class="sxs-lookup"><span data-stu-id="a1130-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="a1130-148">这适用于在批计算之前进行标记。</span><span class="sxs-lookup"><span data-stu-id="a1130-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="a1130-149">如果专家在批计算后将问题切换为 Idle，然后继续标记此问题，则新标记的分数将不会是 100/0，而是原始分数。</span><span class="sxs-lookup"><span data-stu-id="a1130-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="a1130-150">问题和采样模式：问题通常在解决问题时关闭 (相关性培训稳定下来，在问题被取消时或其他用户正在解决问题时执行) 批处理计算。</span><span class="sxs-lookup"><span data-stu-id="a1130-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="a1130-151">相关性培训中的步骤</span><span class="sxs-lookup"><span data-stu-id="a1130-151">Steps in Relevance training</span></span>

<span data-ttu-id="a1130-152">在 **"相关性跟踪 \>**"选项卡Advanced eDiscovery，通过执行下列步骤，可提供有关如何处理的建议。</span><span class="sxs-lookup"><span data-stu-id="a1130-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="a1130-153">当在相关性培训过程中建议执行以下步骤时，将在下面介绍这些含义。</span><span class="sxs-lookup"><span data-stu-id="a1130-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="a1130-154">标记/继续标记：由专家对样本中每个文件和问题执行的文件审阅和相关性标记。</span><span class="sxs-lookup"><span data-stu-id="a1130-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="a1130-155">含义：需要标记现有示例。</span><span class="sxs-lookup"><span data-stu-id="a1130-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="a1130-156">评估/继续评估：允许对案例问题相关性进行早期验证，并初步查看为当前案例导入的文件总体的相关性。</span><span class="sxs-lookup"><span data-stu-id="a1130-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="a1130-157">含义：需要或建议进行更多评估。</span><span class="sxs-lookup"><span data-stu-id="a1130-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="a1130-158">培训/继续培训：此过程Advanced eDiscovery向标记文件示例的专家学习，并能够识别与每个案例上下文中每个问题相关的相关性标准。</span><span class="sxs-lookup"><span data-stu-id="a1130-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="a1130-159">含义：问题需要更多培训;应创建并标记下一个示例。</span><span class="sxs-lookup"><span data-stu-id="a1130-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="a1130-160">批量计算：相关性过程Advanced eDiscovery在培训阶段获取的知识，并应用于整个文件填充。</span><span class="sxs-lookup"><span data-stu-id="a1130-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="a1130-161">相关文件组内的所有文件都进行了相关性评估，并分配了相关性分数。</span><span class="sxs-lookup"><span data-stu-id="a1130-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="a1130-162">含义：问题已稳定，可以执行批量计算。</span><span class="sxs-lookup"><span data-stu-id="a1130-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="a1130-163">跟进：相关性指示专家何时在滚动加载方案期间审阅和标记从其他文件负载选择的文件示例。</span><span class="sxs-lookup"><span data-stu-id="a1130-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="a1130-164">含义：已添加一个新负载，需要 Catch-up 才能继续工作。</span><span class="sxs-lookup"><span data-stu-id="a1130-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="a1130-165">标记不一致：进程Advanced eDiscovery算法识别文件标记过程中可能对分析造成负面影响的不一致情况。</span><span class="sxs-lookup"><span data-stu-id="a1130-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="a1130-166">含义：下一个示例将包括之前示例中已标记的文件，并且必须恢复其标记。</span><span class="sxs-lookup"><span data-stu-id="a1130-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="a1130-167">更新分类器：允许用户应用标记或种子设定更改。</span><span class="sxs-lookup"><span data-stu-id="a1130-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="a1130-168">含义：无需手动运行另一个相关性示例即可应用标记和种子设定更改。</span><span class="sxs-lookup"><span data-stu-id="a1130-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="a1130-169">保留：相关性培训过程已完成。</span><span class="sxs-lookup"><span data-stu-id="a1130-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="a1130-170">含义：此时不需要相关性培训。</span><span class="sxs-lookup"><span data-stu-id="a1130-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="a1130-171">尽管Advanced eDiscovery指导您完成此过程，并指导您在不同阶段执行建议的"下一步"步骤，但它还允许您在选项卡和页面之间导航，并做出选择以解决可能与单个案例、问题或文档审阅过程相关的情况。</span><span class="sxs-lookup"><span data-stu-id="a1130-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="a1130-172">可以接受或替代下一Advanced eDiscovery处理选项。</span><span class="sxs-lookup"><span data-stu-id="a1130-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="a1130-173">如果要执行建议的"下一步"步骤外的其他步骤，请单击对话框中展开的问题显示中列出的"下一步"，单击"下一步"旁边的"修改"按钮，然后选择另一个"下一步"选项。</span><span class="sxs-lookup"><span data-stu-id="a1130-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a1130-174">某些选项在解锁后可能保持禁用状态，因为此时不支持在过程中使用这些选项。</span><span class="sxs-lookup"><span data-stu-id="a1130-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="a1130-175">详细信息</span><span class="sxs-lookup"><span data-stu-id="a1130-175">More information</span></span>

[<span data-ttu-id="a1130-176">了解相关性评估</span><span class="sxs-lookup"><span data-stu-id="a1130-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a1130-177">标记和评估</span><span class="sxs-lookup"><span data-stu-id="a1130-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a1130-178">标记和相关性培训</span><span class="sxs-lookup"><span data-stu-id="a1130-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a1130-179">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="a1130-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a1130-180">根据结果决定</span><span class="sxs-lookup"><span data-stu-id="a1130-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a1130-181">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="a1130-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="a1130-182">查询审阅集中的数据</span><span class="sxs-lookup"><span data-stu-id="a1130-182">Query the data in a review set</span></span>](review-set-search.md)
