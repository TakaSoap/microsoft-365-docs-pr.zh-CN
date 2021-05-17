---
title: 高级电子数据展示中的标记和评估
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: 查看执行评估培训的步骤，包括标记文件，并查看高级电子数据展示中的评估结果。
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769187"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="e9eab-103">高级电子数据展示中相关性模块中的标记和评估</span><span class="sxs-lookup"><span data-stu-id="e9eab-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="e9eab-104">本节介绍高级电子数据展示中相关性模块中的评估过程。</span><span class="sxs-lookup"><span data-stu-id="e9eab-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="e9eab-105">执行评估培训和分析</span><span class="sxs-lookup"><span data-stu-id="e9eab-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="e9eab-106">在" **相关性跟踪 \> "** 选项卡中，单击" **评估** "以启动案例评估。</span><span class="sxs-lookup"><span data-stu-id="e9eab-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="e9eab-107">例如，在此过程中，将创建一个包含 500 个文件的示例评估集，并显示"标记"选项卡，其中包含"标记"面板、显示的文件内容和其他标记选项。</span><span class="sxs-lookup"><span data-stu-id="e9eab-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![评估的相关性标记选项卡](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="e9eab-109">查看示例中的每个文件，确定每个案例问题的文件相关性，然后使用标记面板窗格中的相关性 (R) 、不相关的 (NR) 和跳过按钮标记 **文件** 。</span><span class="sxs-lookup"><span data-stu-id="e9eab-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="e9eab-110">评估需要 500 个标记文件。</span><span class="sxs-lookup"><span data-stu-id="e9eab-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="e9eab-111">如果文件被"跳过"，您将收到更多要标记的文件。</span><span class="sxs-lookup"><span data-stu-id="e9eab-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="e9eab-112">标记示例中的所有文件后，单击"计算 **"。**</span><span class="sxs-lookup"><span data-stu-id="e9eab-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="e9eab-113">"评估当前误差范围和丰富程度"的计算并显示在"相关性跟踪"选项卡中，并展开每个问题的详细信息，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e9eab-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="e9eab-114">有关此对话框的更多详细信息，请参阅 ["审阅评估结果"部分](#reviewing-assessment-results) 。</span><span class="sxs-lookup"><span data-stu-id="e9eab-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![相关性跟踪 - 评估](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="e9eab-116">默认情况下，建议您在问题的评估进度指示器完成时继续执行默认的"下一步"步骤，指示已审阅评估示例并标记了足够的相关文件。</span><span class="sxs-lookup"><span data-stu-id="e9eab-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="e9eab-117">>否则，如果你想要查看"跟踪"选项卡结果并控制错误边距和下一步，请单击"下一步"旁边的"修改"，选择"继续 **评估**"，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="e9eab-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="e9eab-118">单击 **"** 评估" **复选框右边的** "修改"可查看并指定每个问题的评估参数。</span><span class="sxs-lookup"><span data-stu-id="e9eab-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="e9eab-119">将显示 **每个问题的** "评估级别"对话框，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e9eab-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![评估级别案例问题](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="e9eab-121">将计算问题的以下参数，并显示在"评估级别 **"对话框中：**</span><span class="sxs-lookup"><span data-stu-id="e9eab-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="e9eab-122">**恢复估计的目标误差量**：根据此值，计算需要审阅的其他文件的估计数量。</span><span class="sxs-lookup"><span data-stu-id="e9eab-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="e9eab-123">用于恢复的边距大于 75%，可信度为 95%。</span><span class="sxs-lookup"><span data-stu-id="e9eab-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="e9eab-124">**需要其他评估文件**：指示如果尚未满足当前误差区的要求，还需要多少文件。</span><span class="sxs-lookup"><span data-stu-id="e9eab-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="e9eab-125">若要调整当前误差边距并查看每个问题的不同误差 (的影响) ：</span><span class="sxs-lookup"><span data-stu-id="e9eab-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="e9eab-126">在" **选择问题** "列表中，选择问题。</span><span class="sxs-lookup"><span data-stu-id="e9eab-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="e9eab-127">在 **"针对重新调用估计的目标误差边距"中**，输入一个新值。</span><span class="sxs-lookup"><span data-stu-id="e9eab-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="e9eab-128">单击 **"更新** 值"以查看调整的影响。</span><span class="sxs-lookup"><span data-stu-id="e9eab-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="e9eab-129">单击 **"** 评估 **级别"** 对话框中的"高级"以查看以下其他参数和详细信息：</span><span class="sxs-lookup"><span data-stu-id="e9eab-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![评估级别案例问题高级视图](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="e9eab-131">**估计丰富** 度：根据当前评估结果估计丰富度</span><span class="sxs-lookup"><span data-stu-id="e9eab-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="e9eab-132">**对于假定的调用**：默认情况下，目标误差边距适用于超过 75% 的调用。</span><span class="sxs-lookup"><span data-stu-id="e9eab-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="e9eab-133">如果要 **更改** 此参数并控制不同范围的调用值上的误差范围，请单击"编辑"。</span><span class="sxs-lookup"><span data-stu-id="e9eab-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="e9eab-134">**可信度：** 默认情况下，置信度的建议误差值为 95%。</span><span class="sxs-lookup"><span data-stu-id="e9eab-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="e9eab-135">如果要 **更改** 此参数，请单击"编辑"。</span><span class="sxs-lookup"><span data-stu-id="e9eab-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="e9eab-136">**预期的丰富度误差** 范围：在给定更新的值后，这是查看所有其他评估文件后丰富度的预期误差范围。</span><span class="sxs-lookup"><span data-stu-id="e9eab-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="e9eab-137">**需要其他评估文件**：给定更新的值后，需要检查的其他评估文件数量才能达到目标。</span><span class="sxs-lookup"><span data-stu-id="e9eab-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="e9eab-138">**所需的评估文件总数**：给定更新的值后，需要审阅的评估文件总数。</span><span class="sxs-lookup"><span data-stu-id="e9eab-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="e9eab-139">**评估中的预计相关文件数**：在给定更新值后，查看所有其他评估文件后整个评估中的预期相关文件数。</span><span class="sxs-lookup"><span data-stu-id="e9eab-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="e9eab-140">如果 **参数已更改**，请单击"重新计算值"。</span><span class="sxs-lookup"><span data-stu-id="e9eab-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="e9eab-141">完成后，如果存在一个问题，请单击"确定"，以在存在要审阅或修改的多个 (下一步"中保存更改，然后单击"完成) "。 </span><span class="sxs-lookup"><span data-stu-id="e9eab-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="e9eab-142">如果有多个问题，在审查或调整所有问题后，将显示"评估级别 **：** 摘要"对话框，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="e9eab-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![评估级别摘要](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="e9eab-144">成功完成评估后，继续执行相关性培训的下一个阶段。</span><span class="sxs-lookup"><span data-stu-id="e9eab-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="e9eab-145">查看评估结果</span><span class="sxs-lookup"><span data-stu-id="e9eab-145">Reviewing assessment results</span></span>

<span data-ttu-id="e9eab-146">标记评估示例后，评估结果将计算并显示在"相关性跟踪"选项卡中。</span><span class="sxs-lookup"><span data-stu-id="e9eab-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="e9eab-147">以下结果显示在展开的"跟踪"显示中：</span><span class="sxs-lookup"><span data-stu-id="e9eab-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="e9eab-148">评估调用估计的当前误差量</span><span class="sxs-lookup"><span data-stu-id="e9eab-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="e9eab-149">估计丰富度</span><span class="sxs-lookup"><span data-stu-id="e9eab-149">Estimated richness</span></span>

- <span data-ttu-id="e9eab-150">需要检查 (其他评估) </span><span class="sxs-lookup"><span data-stu-id="e9eab-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="e9eab-151">评估当前误差区是高级电子数据展示建议的误差区。</span><span class="sxs-lookup"><span data-stu-id="e9eab-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="e9eab-152">为"需要其他评估文件"显示的数量对应于该建议。</span><span class="sxs-lookup"><span data-stu-id="e9eab-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="e9eab-153">评估进度指示器显示评估的完成级别（假设当前误差线）。</span><span class="sxs-lookup"><span data-stu-id="e9eab-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="e9eab-154">评估正在进行时，用户将标记另一个评估示例。</span><span class="sxs-lookup"><span data-stu-id="e9eab-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="e9eab-155">当评估进度指示器显示评估已完成时，这意味着评估示例评审已完成，并且标记了足够的相关文件。</span><span class="sxs-lookup"><span data-stu-id="e9eab-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="e9eab-156">展开的"跟踪"显示显示下一步的建议步骤、评估统计信息以及详细结果的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e9eab-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="e9eab-157">当丰富程度非常低时，需要达到最少数量的相关文件以生成有用统计信息所需的其他评估文件数非常高。</span><span class="sxs-lookup"><span data-stu-id="e9eab-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="e9eab-158">然后，高级电子数据展示将建议继续培训。</span><span class="sxs-lookup"><span data-stu-id="e9eab-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="e9eab-159">评估进度指示器将带底纹，并且没有可用的统计信息。</span><span class="sxs-lookup"><span data-stu-id="e9eab-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="e9eab-160">如果没有基于统计的防抖动，则结果的准确性和可信度将较低。</span><span class="sxs-lookup"><span data-stu-id="e9eab-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="e9eab-161">但是，当你不需要知道找到的相关文件的百分比时，这些结果可用于查找相关文件。</span><span class="sxs-lookup"><span data-stu-id="e9eab-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="e9eab-162">同样，此状态可用于对低丰富度问题进行训练，其中相关性分数可以加快对与特定问题相关的文件的访问。</span><span class="sxs-lookup"><span data-stu-id="e9eab-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="e9eab-163">在" **相关性 \> 跟踪"** 选项卡中，展开的问题显示提供了以下查看选项：</span><span class="sxs-lookup"><span data-stu-id="e9eab-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="e9eab-164">建议的下一步（如"下一步 **：** 标记"可以绕过 (每个问题) ，方法是单击其右边的"修改"按钮，然后在"下一步"中选择其他 **步骤**。</span><span class="sxs-lookup"><span data-stu-id="e9eab-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="e9eab-165">评估进度指示器未完成时，评估将是下一个建议选项，用于标记更多评估文件并增加统计信息的准确性。</span><span class="sxs-lookup"><span data-stu-id="e9eab-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="e9eab-166">你可以更改误差范围并评估其影响，方法是单击"修改"，在"评估级别"对话框中，更改"用于撤回估计的目标误差范围"，然后单击"更新 **值"。** </span><span class="sxs-lookup"><span data-stu-id="e9eab-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="e9eab-167">此外，在此对话框中，可以通过单击"高级"来查看高级 **选项**。</span><span class="sxs-lookup"><span data-stu-id="e9eab-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="e9eab-168">可以通过单击"查看"来查看其他评估级别统计信息及其 **影响**。</span><span class="sxs-lookup"><span data-stu-id="e9eab-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="e9eab-169">在显示的"详细信息结果"对话框中，当至少有 500 个标记评估文件且至少有 18 个文件标记为"与问题相关"时，每个问题均会显示统计信息。</span><span class="sxs-lookup"><span data-stu-id="e9eab-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
