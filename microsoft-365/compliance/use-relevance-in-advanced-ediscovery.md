---
title: 使用高级电子数据展示中的相关性模块
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: 了解高级电子数据展示中的相关性模块，包括用于培训和文件审阅的工作流和指南和步骤。
ms.openlocfilehash: 0319ac378fb891d96437f53931213429b111d61d
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663281"
---
# <a name="use-the-relevance-module-in-advanced-ediscovery-classic"></a><span data-ttu-id="83cd4-103">在高级电子数据展示和经典电子数据展示 (相关) </span><span class="sxs-lookup"><span data-stu-id="83cd4-103">Use the Relevance module in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="83cd4-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="83cd4-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="83cd4-106">在高级电子数据展示中，相关性模块包括相关性培训和与案例相关的文件审阅。</span><span class="sxs-lookup"><span data-stu-id="83cd4-106">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="83cd4-107">显示并描述相关性工作流，如下所示：</span><span class="sxs-lookup"><span data-stu-id="83cd4-107">The Relevance workflow is shown and described as follows:</span></span>
  
![相关性工作流](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="83cd4-109">**评估和跟踪周期**：</span><span class="sxs-lookup"><span data-stu-id="83cd4-109">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="83cd4-110">**评估**：高级电子数据展示支持基于随机文件样本的早期评估，并使用此评估应用决策以确定预测编码过程的性能。</span><span class="sxs-lookup"><span data-stu-id="83cd4-110">**Assessment**: Advanced eDiscovery enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="83cd4-111">**Track**： Advanced eDiscovery calculates and displays interim results of the assessment while monitoring 统计 valid of the process.</span><span class="sxs-lookup"><span data-stu-id="83cd4-111">**Track**: Advanced eDiscovery calculates and displays interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="83cd4-112">**培训和跟踪周期**：</span><span class="sxs-lookup"><span data-stu-id="83cd4-112">**Cycles of training and tracking**:</span></span>
    
  - <span data-ttu-id="83cd4-113">**Tag**： Advanced eDiscovery learn Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span><span class="sxs-lookup"><span data-stu-id="83cd4-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="83cd4-114">**Track**： Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring 统计 valid of the process.</span><span class="sxs-lookup"><span data-stu-id="83cd4-114">**Track**: Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="83cd4-115">**批量计算**：高级电子数据展示采用累积和学习的相关性条件，应用于整个文件集合，并生成每个文件的相关性分数。</span><span class="sxs-lookup"><span data-stu-id="83cd4-115">**Batch calculation**: Advanced eDiscovery takes the accumulated and learned Relevance criteria, applies it to the entire file collection, and generates Relevance scores for each file.</span></span>
    
- <span data-ttu-id="83cd4-116">**决定**：高级电子数据展示在批计算后显示应用于整个案例的分析结果，并显示用于做出文档审阅决策的数据。</span><span class="sxs-lookup"><span data-stu-id="83cd4-116">**Decide**: Advanced eDiscovery displays the results of the analysis applied to the entire case after Batch calculation and displays data for making document review decisions.</span></span>
    
- <span data-ttu-id="83cd4-117">**测试**：可以测试高级电子数据展示结果，以验证高级电子数据展示处理的有效性和有效性。</span><span class="sxs-lookup"><span data-stu-id="83cd4-117">**Test**: Advanced eDiscovery results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="83cd4-118">相关性培训和审阅指南</span><span class="sxs-lookup"><span data-stu-id="83cd4-118">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="83cd4-119">以下是相关性培训和审阅指南的概述：</span><span class="sxs-lookup"><span data-stu-id="83cd4-119">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="83cd4-120">**错误和不一** 致：如果在培训期间出现标记错误，请返回到以前的文件示例进行更正。</span><span class="sxs-lookup"><span data-stu-id="83cd4-120">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="83cd4-121">如果错误太多需要更正，或者有新的案例或问题角度，则管理员应重新定义相关性条件，并重新启动相关性培训。</span><span class="sxs-lookup"><span data-stu-id="83cd4-121">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="83cd4-122">**标记和培训**：</span><span class="sxs-lookup"><span data-stu-id="83cd4-122">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="83cd4-123">文件应仅基于内容进行标记。</span><span class="sxs-lookup"><span data-stu-id="83cd4-123">Files should be tagged based on content only.</span></span> <span data-ttu-id="83cd4-124">不考虑元数据，如保管人、日期或文件路径。</span><span class="sxs-lookup"><span data-stu-id="83cd4-124">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="83cd4-125">标记文件时，不考虑文本中的日期范围指示。</span><span class="sxs-lookup"><span data-stu-id="83cd4-125">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="83cd4-126">标记文件时，不考虑嵌入的图形图像。</span><span class="sxs-lookup"><span data-stu-id="83cd4-126">Do not consider embedded graphical images when tagging files.</span></span>
    
  - <span data-ttu-id="83cd4-127">如果在标记时使用 **格式化的文本视图** 图标查看文件，则不考虑文本的格式。</span><span class="sxs-lookup"><span data-stu-id="83cd4-127">If viewing a file using the **formatted text view** icon while tagging, do not consider the formatting of text.</span></span> <span data-ttu-id="83cd4-128">例如，相关性仍将带删除线 (一条水平线在其中心) 表示删除的单词仍被视为所分析文本的一部分。</span><span class="sxs-lookup"><span data-stu-id="83cd4-128">For example, a word displayed with a strikethrough (a horizontal line through its center indicating deletion) is still considered by Relevance as part of the analyzed text.</span></span> 
    
  - <span data-ttu-id="83cd4-129">忽略应用于相关性 (由案例管理器或管理员设置) 将在相关性的文本视图中显示的文件内容中删除。</span><span class="sxs-lookup"><span data-stu-id="83cd4-129">Ignore text applied to Relevance (as set by the Case Manager or Administrator) will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="83cd4-130">如果在相关性培训启动后定义了 Ignore 文本的值，则新的忽略文本将应用于从定义该文本的位置创建的示例文件。</span><span class="sxs-lookup"><span data-stu-id="83cd4-130">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="83cd4-131">应谨慎使用"忽略文本"功能，因为该功能的使用可能会降低文件分析的性能</span><span class="sxs-lookup"><span data-stu-id="83cd4-131">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="83cd4-132">仅在必要时 **使用"跳过标记** "选项。</span><span class="sxs-lookup"><span data-stu-id="83cd4-132">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="83cd4-133">高级电子数据展示不会基于跳过的文件进行训练。</span><span class="sxs-lookup"><span data-stu-id="83cd4-133">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="83cd4-134">在评估中，如果很难判断文件是否相关，最好尽可能标记为相关 (R) 或不相关的 (NR) ，而不是选择"跳过 **"。**</span><span class="sxs-lookup"><span data-stu-id="83cd4-134">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="83cd4-135">当高级电子数据展示评估培训时，可以看到这些类型的文件的处理情况。</span><span class="sxs-lookup"><span data-stu-id="83cd4-135">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="83cd4-136">即使提取的文本非常少的文件也应在培训中标记为 R/NR，而不是"跳过"（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="83cd4-136">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="83cd4-137">只要文件可读且可标记为 R/NR，标记就可以影响分类器。</span><span class="sxs-lookup"><span data-stu-id="83cd4-137">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="83cd4-138">"标记"选项卡上显示的示例文件列表上的文件序列号允许用户返回到文件的原始显示顺序。</span><span class="sxs-lookup"><span data-stu-id="83cd4-138">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="83cd4-139">你可以返回任何示例并更改评估和培训集文件的标记。</span><span class="sxs-lookup"><span data-stu-id="83cd4-139">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="83cd4-140">创建下一个示例时将应用更改。</span><span class="sxs-lookup"><span data-stu-id="83cd4-140">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="83cd4-141">标记文件时，应该将 PDF 格式的扫描的 Excel 文件视为与本机 Excel 文件相同。</span><span class="sxs-lookup"><span data-stu-id="83cd4-141">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="83cd4-142">如果对文件的相关性标记有疑问，请咨询专家。</span><span class="sxs-lookup"><span data-stu-id="83cd4-142">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="83cd4-143">相关性培训期间不正确的标记可能导致此过程稍后丢失时间，并且也可能对总体结果的质量产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="83cd4-143">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="83cd4-144">关键字列表中定义的关键字将按颜色显示，以帮助用户在标记时标识相关文件。</span><span class="sxs-lookup"><span data-stu-id="83cd4-144">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="83cd4-145">**批量计算**：专家标记为 R/NR 的文件将收到 0 或 100 的分数。</span><span class="sxs-lookup"><span data-stu-id="83cd4-145">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="83cd4-146">这适用于在批计算之前进行标记。</span><span class="sxs-lookup"><span data-stu-id="83cd4-146">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="83cd4-147">如果专家在批计算后将问题切换为"空闲"并继续标记此问题，则新标记的分数不是 100/0，而是原始分数。</span><span class="sxs-lookup"><span data-stu-id="83cd4-147">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="83cd4-148">问题和采样模式：问题通常在工作完成后关闭 (相关性培训稳定下来，) 、取消问题时或其他用户正在解决问题时执行批计算。</span><span class="sxs-lookup"><span data-stu-id="83cd4-148">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="83cd4-149">相关性培训的步骤</span><span class="sxs-lookup"><span data-stu-id="83cd4-149">Steps in Relevance training</span></span>

<span data-ttu-id="83cd4-150">在 **"相关性 \> 跟踪** "选项卡中，高级电子数据展示提供了有关如何处理的建议，并提供了以下步骤。</span><span class="sxs-lookup"><span data-stu-id="83cd4-150">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="83cd4-151">在相关性培训过程中建议执行以下步骤时，将在下面介绍这些含义。</span><span class="sxs-lookup"><span data-stu-id="83cd4-151">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="83cd4-152">标记/继续标记：由专家针对示例中每个文件和问题执行的文件审阅和相关性标记。</span><span class="sxs-lookup"><span data-stu-id="83cd4-152">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="83cd4-153">含义：需要标记现有示例。</span><span class="sxs-lookup"><span data-stu-id="83cd4-153">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="83cd4-154">评估/继续评估：支持对案例问题相关性进行早期验证，并初步了解为当前案例导入的文件总体的相关性。</span><span class="sxs-lookup"><span data-stu-id="83cd4-154">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="83cd4-155">含义：需要或建议进行更多评估。</span><span class="sxs-lookup"><span data-stu-id="83cd4-155">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="83cd4-156">培训/继续培训：高级电子数据展示从标记文件示例的专家学习并获取识别与每个案例上下文中每个问题相关的相关性标准的能力的过程。</span><span class="sxs-lookup"><span data-stu-id="83cd4-156">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="83cd4-157">含义：问题需要更多培训;应创建并标记下一个示例。</span><span class="sxs-lookup"><span data-stu-id="83cd4-157">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="83cd4-158">批量计算：高级电子数据展示在培训阶段获取的知识并应用于整个文件填充的相关性过程。</span><span class="sxs-lookup"><span data-stu-id="83cd4-158">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="83cd4-159">相关文件组内的所有文件都针对相关性进行评估，并分配有相关性分数。</span><span class="sxs-lookup"><span data-stu-id="83cd4-159">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="83cd4-160">含义：问题已稳定，可以执行批计算。</span><span class="sxs-lookup"><span data-stu-id="83cd4-160">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="83cd4-161">Up-up： Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Load scenario.</span><span class="sxs-lookup"><span data-stu-id="83cd4-161">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="83cd4-162">含义：已添加新负载，需要进行跟进才能继续工作。</span><span class="sxs-lookup"><span data-stu-id="83cd4-162">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="83cd4-163">标记不一致：进程通过高级电子数据展示算法识别文件标记过程中可能对分析产生负面影响的不一致情况。</span><span class="sxs-lookup"><span data-stu-id="83cd4-163">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="83cd4-164">含义：下一个示例将包括之前示例中已标记的文件，并且必须重新标记它们。</span><span class="sxs-lookup"><span data-stu-id="83cd4-164">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="83cd4-165">更新分类器：允许用户应用标记或种子设定更改。</span><span class="sxs-lookup"><span data-stu-id="83cd4-165">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="83cd4-166">含义：无需手动运行另一个相关性示例即可应用标记和种子设定更改。</span><span class="sxs-lookup"><span data-stu-id="83cd4-166">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="83cd4-167">保留：相关性培训过程已完成。</span><span class="sxs-lookup"><span data-stu-id="83cd4-167">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="83cd4-168">含义：此时不需要相关性培训。</span><span class="sxs-lookup"><span data-stu-id="83cd4-168">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="83cd4-169">虽然高级电子数据展示可指导你完成此过程，但建议在不同阶段执行下一步，它还允许你在选项卡和页面之间导航，并做出选择以解决可能与单个案例、问题或文档审阅过程相关的情况。</span><span class="sxs-lookup"><span data-stu-id="83cd4-169">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="83cd4-170">可以接受或替代高级电子数据展示下一步处理选项。</span><span class="sxs-lookup"><span data-stu-id="83cd4-170">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="83cd4-171">如果要执行建议下一步外的步骤，请单击对话框中展开的问题显示中列出的下一步，单击下一步旁边的"修改"按钮，然后选择另一个"下一步"选项。</span><span class="sxs-lookup"><span data-stu-id="83cd4-171">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="83cd4-172">某些选项在解锁后可能仍处于禁用状态，因为此时不支持在过程中使用这些选项。</span><span class="sxs-lookup"><span data-stu-id="83cd4-172">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="83cd4-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83cd4-173">See also</span></span>

[<span data-ttu-id="83cd4-174">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="83cd4-174">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="83cd4-175">了解相关性评估</span><span class="sxs-lookup"><span data-stu-id="83cd4-175">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="83cd4-176">标记和评估</span><span class="sxs-lookup"><span data-stu-id="83cd4-176">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="83cd4-177">标记和相关性培训</span><span class="sxs-lookup"><span data-stu-id="83cd4-177">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="83cd4-178">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="83cd4-178">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="83cd4-179">根据结果决定</span><span class="sxs-lookup"><span data-stu-id="83cd4-179">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="83cd4-180">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="83cd4-180">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

