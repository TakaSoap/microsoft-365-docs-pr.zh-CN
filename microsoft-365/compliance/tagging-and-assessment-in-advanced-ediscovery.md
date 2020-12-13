---
title: 高级电子数据展示中的标记和评估
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: 查看执行评估培训的步骤，包括标记文件，并查看高级电子数据展示中的评估结果。
ms.openlocfilehash: c8c6f82e7cfb3e2eddcc482039582ea27a702494
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663457"
---
# <a name="tagging-and-assessment-in-advanced-ediscovery-classic"></a><span data-ttu-id="5ceb7-103">高级电子数据展示和经典电子数据展示 (和评估) </span><span class="sxs-lookup"><span data-stu-id="5ceb7-103">Tagging and Assessment in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="5ceb7-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="5ceb7-106">本节介绍高级电子数据展示相关性评估模块的过程。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="5ceb7-107">执行评估培训和分析</span><span class="sxs-lookup"><span data-stu-id="5ceb7-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="5ceb7-108">在 **"相关性 \> 跟踪"** 选项卡中，单击 **"评估** "以启动案例评估。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="5ceb7-109">例如，在此过程中创建一个包含 500 个文件的示例评估集，并显示"标记"选项卡，其中包含标记面板、显示的文件内容和其他标记选项。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![评估的相关性标记选项卡](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="5ceb7-111">查看示例中的每个文件，确定每个案例问题的文件相关性，然后使用"标记"面板窗格中的相关性 (R) 、不相关的 (NR) 和"跳过"按钮标记文件。 </span><span class="sxs-lookup"><span data-stu-id="5ceb7-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="5ceb7-112">评估需要 500 个标记文件。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-112">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="5ceb7-113">如果文件被"跳过"，您将收到更多要标记的文件。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-113">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="5ceb7-114">标记示例中的所有文件后，单击"计算 **"。**</span><span class="sxs-lookup"><span data-stu-id="5ceb7-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="5ceb7-115">评估当前误差范围和丰富程度在"相关性跟踪"选项卡中计算并显示，并展开每个问题的详细信息，如下所示。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-115">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="5ceb7-116">有关此对话框的更多详细信息，请参阅稍后的"审阅评估结果"部分。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-116">More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![相关性跟踪 - 评估](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="5ceb7-118">默认情况下，建议您在问题的评估进度指示器完成时继续执行默认的"下一步"，指示已审阅评估示例并标记了足够的相关文件。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-118">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="5ceb7-119">>否则，如果你想要查看"跟踪"选项卡结果并控制错误边距和下一步，请单击"修改相邻的下一步"，选择"继续 **评估**"，然后单击"**确定"。** </span><span class="sxs-lookup"><span data-stu-id="5ceb7-119">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="5ceb7-120">单击 **"** 评估"复选框右边的"修改"可查看并指定每个问题的评估参数。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-120">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="5ceb7-121">将显示 **每个问题的** "评估级别"对话框，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5ceb7-121">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![评估级别案例问题](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="5ceb7-123">将计算该问题的以下参数，并显示在"评估级别 **"** 对话框中：</span><span class="sxs-lookup"><span data-stu-id="5ceb7-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="5ceb7-124">**恢复估计的目标误差边距**：根据此值计算需要审阅的其他文件的估计数量。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-124">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="5ceb7-125">用于恢复的边距大于 75%，可信度为 95%。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-125">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="5ceb7-126">**需要其他评估文件**：指示如果尚未满足当前误差区的要求，还需要多少文件。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="5ceb7-127">若要调整当前误差边距并查看每个问题的不同误差 (的影响) ：</span><span class="sxs-lookup"><span data-stu-id="5ceb7-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="5ceb7-128">在 **"选择问题** "列表中，选择问题。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="5ceb7-129">在 **"重新调用估计的目标误差区"中**，输入一个新值。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="5ceb7-130">单击 **"更新** 值"以查看调整的影响。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="5ceb7-131">单击 **"** 评估级别 **"** 对话框中的"高级"以查看以下其他参数和详细信息：</span><span class="sxs-lookup"><span data-stu-id="5ceb7-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![评估级别案例问题高级视图](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="5ceb7-133">**估计丰富度**：根据当前评估结果估计丰富度</span><span class="sxs-lookup"><span data-stu-id="5ceb7-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="5ceb7-134">**对于假定的调用**：默认情况下，目标误差边距适用于超过 75% 的调用。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-134">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="5ceb7-135">如果要 **更改** 此参数并控制不同范围的调用值上的误差范围，请单击"编辑"。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-135">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="5ceb7-136">**可信度：** 默认情况下，置信度的建议误差值为 95%。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-136">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="5ceb7-137">如果要 **更改** 此参数，请单击"编辑"。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-137">Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="5ceb7-138">**预期的丰富度误差** 范围：在给定更新的值后，这是查看所有其他评估文件后丰富度的预期误差范围。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="5ceb7-139">**需要其他评估文件**：根据更新的值，需要审阅的其他评估文件的数量才能达到目标。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="5ceb7-140">**所需的评估文件总数**：给定更新的值后，需要审阅的评估文件总数。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="5ceb7-141">**评估中的** 预计相关文件数：根据更新的值，在审查所有其他评估文件后，整个评估中预期的相关文件数量。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="5ceb7-142">如果 **参数已更改**，请单击"重新计算值"。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-142">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="5ceb7-143">完成后，如果出现一个问题，请单击"确定"， (或 **下** 一步中查看或修改多个问题，然后完成) 。  </span><span class="sxs-lookup"><span data-stu-id="5ceb7-143">When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="5ceb7-144">如果有多个问题，在审阅或调整所有问题后，将显示"评估级别 **：** 摘要"对话框，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![评估级别摘要](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="5ceb7-146">成功完成评估后，继续执行相关性培训的下一阶段。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="5ceb7-147">查看评估结果</span><span class="sxs-lookup"><span data-stu-id="5ceb7-147">Reviewing assessment results</span></span>

<span data-ttu-id="5ceb7-148">标记评估示例后，评估结果将计算并显示在相关性跟踪选项卡中。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="5ceb7-149">展开的轨显示中将显示以下结果：</span><span class="sxs-lookup"><span data-stu-id="5ceb7-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="5ceb7-150">评估调用估计的当前误差量</span><span class="sxs-lookup"><span data-stu-id="5ceb7-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="5ceb7-151">估计丰富度</span><span class="sxs-lookup"><span data-stu-id="5ceb7-151">Estimated richness</span></span>
    
- <span data-ttu-id="5ceb7-152">查看项目所需的 (评估) </span><span class="sxs-lookup"><span data-stu-id="5ceb7-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="5ceb7-153">评估当前误差区是高级电子数据展示建议的错误边距。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-153">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="5ceb7-154">为"所需的其他评估文件"显示的数量对应于该建议。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-154">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="5ceb7-155">评估进度指示器显示评估的完成级别（鉴于当前误差线）。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-155">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="5ceb7-156">评估正在进行时，用户将标记另一个评估示例。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-156">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="5ceb7-157">当评估进度指示器显示评估已完成时，这意味着评估示例评审已完成，并且标记了足够的相关文件。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="5ceb7-158">展开的跟踪显示显示建议的下一步、评估统计信息以及详细结果的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="5ceb7-159">当丰富程度非常低时，需要达到最少数量的相关文件以生成有用统计信息所需的其他评估文件数非常高。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-159">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="5ceb7-160">然后，高级电子数据展示将建议继续培训。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-160">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="5ceb7-161">评估进度指示器将带底纹，并且不会提供统计信息。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-161">The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="5ceb7-162">如果没有基于统计的防抖动，则结果的准确性和可信度将较低。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-162">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="5ceb7-163">但是，当不需要知道找到的相关文件的百分比时，这些结果可用于查找相关文件。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-163">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="5ceb7-164">同样，此状态可用于以低丰富度来训练问题，其中相关性分数可以加快对与特定问题相关的文件的访问。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-164">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="5ceb7-165">在"相关性跟踪"选项卡中展开的问题显示中，以下查看选项可用：> 建议下一步，例如"下一步 **：** 标记"可以绕过 (每个问题) ，方法是单击其右边的"修改"按钮，然后在下一步中选择其他步骤。 **\>** </span><span class="sxs-lookup"><span data-stu-id="5ceb7-165">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="5ceb7-166">当评估进度指示器尚未完成时，评估将是下一个建议选项，用于标记更多评估文件并增加统计信息的准确性。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-166">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> <span data-ttu-id="5ceb7-167">>可以通过单击"修改"，在"评估级别"对话框中更改恢复估计的目标误差范围，然后单击"更新值"，来更改误差范围并评估 **其影响**。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-167">> You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="5ceb7-168">此外，在此对话框中，可以通过单击"高级"来查看高级 **选项**。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-168">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> <span data-ttu-id="5ceb7-169">>单击"查看"可以查看其他评估级别统计信息及其 **影响**。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-169">> You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="5ceb7-170">在显示的"详细信息结果"对话框中，当至少有 500 个标记评估文件和至少 18 个文件标记为与问题相关时，每个问题均会显示统计信息。</span><span class="sxs-lookup"><span data-stu-id="5ceb7-170">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5ceb7-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ceb7-171">See also</span></span>

[<span data-ttu-id="5ceb7-172">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="5ceb7-172">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="5ceb7-173">了解相关性评估</span><span class="sxs-lookup"><span data-stu-id="5ceb7-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5ceb7-174">标记和相关性培训</span><span class="sxs-lookup"><span data-stu-id="5ceb7-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5ceb7-175">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="5ceb7-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5ceb7-176">根据结果决定</span><span class="sxs-lookup"><span data-stu-id="5ceb7-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5ceb7-177">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="5ceb7-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

