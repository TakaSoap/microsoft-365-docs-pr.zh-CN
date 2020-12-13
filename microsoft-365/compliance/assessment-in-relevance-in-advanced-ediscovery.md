---
title: 了解高级电子数据展示中的相关性评估
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 大致了解评估阶段及其在 Microsoft 365 高级电子数据展示中相关性培训期间确定问题丰富的角色。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28bbe15a6e3f5611041cf446bd053f59de395d54
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663077"
---
# <a name="understand-assessment-in-relevance-in-advanced-ediscovery-classic"></a><span data-ttu-id="375de-103">了解高级电子数据展示和经典 (相关性评估) </span><span class="sxs-lookup"><span data-stu-id="375de-103">Understand Assessment in Relevance in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="375de-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="375de-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="375de-106">高级电子数据展示支持早期评估，例如，针对定义的问题和为案例导入的数据。</span><span class="sxs-lookup"><span data-stu-id="375de-106">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case.</span></span> <span data-ttu-id="375de-107">高级电子数据展示可让专家做出有关采用的方法的决策，并应用这些决策至文档审阅项目。</span><span class="sxs-lookup"><span data-stu-id="375de-107">Advanced eDiscovery lets the expert make decisions about an adopted approach and to apply these decisions to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="375de-108">了解评估</span><span class="sxs-lookup"><span data-stu-id="375de-108">Understanding assessment</span></span>

<span data-ttu-id="375de-109">在评估中，专家会审阅至少 500 个随机文件集，这些文件用于确定问题的丰富程度并生成反映培训结果的统计信息。</span><span class="sxs-lookup"><span data-stu-id="375de-109">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results.</span></span> <span data-ttu-id="375de-110">如果发现有足够的相关文件达到统计级别，可帮助高级电子数据展示相关性提供准确的统计信息并有效确定培训过程中的稳定点，评估就会成功。</span><span class="sxs-lookup"><span data-stu-id="375de-110">Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="375de-111">评估集内相关文件的数量越高，统计和稳定性算法的有效性就越高。</span><span class="sxs-lookup"><span data-stu-id="375de-111">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm.</span></span> <span data-ttu-id="375de-112">评估文件中相关文件的数量取决于问题的丰富程度。</span><span class="sxs-lookup"><span data-stu-id="375de-112">The number of relevant files within the assessment files depends on the richness of the issue.</span></span> <span data-ttu-id="375de-113">丰富度是与问题相关的集合中相关文件的估计百分比。</span><span class="sxs-lookup"><span data-stu-id="375de-113">Richness is the estimated percent of relevant files in the set relevant to an issue.</span></span> <span data-ttu-id="375de-114">与具有较低丰富度的问题相较，具有较高丰富度的问题将更快到达更多相关文件。</span><span class="sxs-lookup"><span data-stu-id="375de-114">Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness.</span></span> <span data-ttu-id="375de-115">具有非常低的丰富度 (例如，2% 或更少) 将需要一个非常大的评估集，以覆盖大量相关文件。</span><span class="sxs-lookup"><span data-stu-id="375de-115">Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="375de-116">在培训和批计算后，"跟踪"和"决定"选项卡中显示的统计数据包括不同审阅集的调用估计。</span><span class="sxs-lookup"><span data-stu-id="375de-116">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets.</span></span> <span data-ttu-id="375de-117">在统计信息中，基于此示例集的 (，评估) 包括误差范围和该误差范围可信度。</span><span class="sxs-lookup"><span data-stu-id="375de-117">In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin.</span></span> <span data-ttu-id="375de-118">例如，预计调用 80% 的误差可能为正负 5%，置信水平为 95%。</span><span class="sxs-lookup"><span data-stu-id="375de-118">For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%.</span></span> <span data-ttu-id="375de-119">这意味着估计的恢复率实际上为 75%-85%，并且此估计可信度为 95%。</span><span class="sxs-lookup"><span data-stu-id="375de-119">This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence.</span></span> <span data-ttu-id="375de-120">评估集越大，误差范围越小，统计越准确。</span><span class="sxs-lookup"><span data-stu-id="375de-120">The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="375de-121">专家审阅包含 500 个文件的初始评估集后，相关性可以确定调用值的当前误差范围。</span><span class="sxs-lookup"><span data-stu-id="375de-121">After the expert reviews an initial assessment set of 500 files, Relevance can determine the current margin of error of the recall values.</span></span> <span data-ttu-id="375de-122">相关性还将建议达到默认误差范围以优化评估集。</span><span class="sxs-lookup"><span data-stu-id="375de-122">Relevance will also recommend a default margin of error to reach to optimize the assessment set.</span></span> <span data-ttu-id="375de-123">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="375de-123">Here are some examples:</span></span>
  
- <span data-ttu-id="375de-124">如果评估集的误差量已加或减 10%，相关性建议继续培训 (无需额外评估) 。</span><span class="sxs-lookup"><span data-stu-id="375de-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend moving on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="375de-125">如果评估集产生正负 13% 的误差范围，相关性可能会建议审阅另一组评估文件，以达到较小的边距。</span><span class="sxs-lookup"><span data-stu-id="375de-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="375de-126">如果丰富度非常低，相关性可能会建议停止评估，即使误差范围很大 (使统计信息变得不切实际) ，因为达到有用误差范围所需的评估集过大。</span><span class="sxs-lookup"><span data-stu-id="375de-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="375de-127">每个问题都有其自己的丰富程度、当前误差量以及估计的其他评估文件数。</span><span class="sxs-lookup"><span data-stu-id="375de-127">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files.</span></span> <span data-ttu-id="375de-128">下一个评估集根据单个评估集 (最多 1，000 个文件数创建) 。</span><span class="sxs-lookup"><span data-stu-id="375de-128">The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="375de-129">您可以接受相关性建议或根据需要调整当前误差区。</span><span class="sxs-lookup"><span data-stu-id="375de-129">You can accept the Relevance recommendations or adjust the current margin of error according to your needs.</span></span> <span data-ttu-id="375de-130">对于等于或高于 75% 的恢复，确定默认的当前误差边距。</span><span class="sxs-lookup"><span data-stu-id="375de-130">The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="375de-131">可通过清除每个问题的"评估"复选框，然后清除"所有问题"来绕过评估阶段，在展开的视图的"相关性跟踪"选项卡中。 **\>**</span><span class="sxs-lookup"><span data-stu-id="375de-131">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="375de-132">但是，因此，此问题没有统计信息。</span><span class="sxs-lookup"><span data-stu-id="375de-132">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="375de-133">>执行 **评估之前** ，才能清除"评估"复选框。</span><span class="sxs-lookup"><span data-stu-id="375de-133">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="375de-134">如果一种情况下存在多个问题，则仅在清除每个问题的复选框时绕过评估</span><span class="sxs-lookup"><span data-stu-id="375de-134">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="375de-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="375de-135">Related topics</span></span>

[<span data-ttu-id="375de-136">高级电子数据展示（经典）</span><span class="sxs-lookup"><span data-stu-id="375de-136">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="375de-137">标记和评估</span><span class="sxs-lookup"><span data-stu-id="375de-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="375de-138">标记和相关性培训</span><span class="sxs-lookup"><span data-stu-id="375de-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="375de-139">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="375de-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="375de-140">根据结果决定</span><span class="sxs-lookup"><span data-stu-id="375de-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="375de-141">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="375de-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

