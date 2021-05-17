---
title: 了解评估中的相关性Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 大致了解评估阶段及其在相关性培训期间确定问题丰富的Microsoft 365 Advanced eDiscovery。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769273"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="18421-103">Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="18421-103">Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="18421-104">Advanced eDiscovery启用早期评估，例如，针对已定义的问题和为案例导入的数据。</span><span class="sxs-lookup"><span data-stu-id="18421-104">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case.</span></span> <span data-ttu-id="18421-105">Advanced eDiscovery让专家做出有关已采用方法的决策，并应用这些决策到文档审阅项目。</span><span class="sxs-lookup"><span data-stu-id="18421-105">Advanced eDiscovery lets the expert make decisions about an adopted approach and to apply these decisions to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="18421-106">了解评估</span><span class="sxs-lookup"><span data-stu-id="18421-106">Understanding assessment</span></span>

<span data-ttu-id="18421-107">在评估中，专家审查至少 500 个随机文件集，这些文件用于确定问题的丰富程度并生成反映培训结果的统计信息。</span><span class="sxs-lookup"><span data-stu-id="18421-107">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results.</span></span> <span data-ttu-id="18421-108">如果发现有足够的相关文件达到统计级别，将有助于Advanced eDiscovery相关性，从而提供准确的统计信息并有效确定培训过程中的稳定点，评估成功。</span><span class="sxs-lookup"><span data-stu-id="18421-108">Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="18421-109">评估集内的相关文件数量越高，稳定性算法的统计信息和有效性越准确。</span><span class="sxs-lookup"><span data-stu-id="18421-109">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm.</span></span> <span data-ttu-id="18421-110">评估文件中相关文件的数量取决于问题的丰富程度。</span><span class="sxs-lookup"><span data-stu-id="18421-110">The number of relevant files within the assessment files depends on the richness of the issue.</span></span> <span data-ttu-id="18421-111">丰富度是集合中与问题相关的相关文件的估计百分比。</span><span class="sxs-lookup"><span data-stu-id="18421-111">Richness is the estimated percent of relevant files in the set relevant to an issue.</span></span> <span data-ttu-id="18421-112">与具有较低丰富度的问题比，具有较高丰富度的问题将更快到达更多相关文件。</span><span class="sxs-lookup"><span data-stu-id="18421-112">Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness.</span></span> <span data-ttu-id="18421-113">低丰富度 (例如，2% 或) 将需要一个非常大的评估集，以覆盖大量相关文件。</span><span class="sxs-lookup"><span data-stu-id="18421-113">Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="18421-114">统计信息（在培训期间和批计算后显示在"跟踪"和"决定"选项卡中）包括不同审阅集的调用估计值。</span><span class="sxs-lookup"><span data-stu-id="18421-114">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets.</span></span> <span data-ttu-id="18421-115">在统计信息中，基于示例集 (，评估文件) 包括误差范围和该误差范围可信度。</span><span class="sxs-lookup"><span data-stu-id="18421-115">In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin.</span></span> <span data-ttu-id="18421-116">例如，预计调用 80% 的误差可能为正负 5%，置信度为 95%。</span><span class="sxs-lookup"><span data-stu-id="18421-116">For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%.</span></span> <span data-ttu-id="18421-117">这意味着估计的恢复率实际上为 75%-85%，并且此估计的置信度为 95%。</span><span class="sxs-lookup"><span data-stu-id="18421-117">This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence.</span></span> <span data-ttu-id="18421-118">评估集越大，误差范围越小，统计信息越准确。</span><span class="sxs-lookup"><span data-stu-id="18421-118">The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="18421-119">专家审阅包含 500 个文件的初始评估集后，相关性可确定调用值的当前误差范围。</span><span class="sxs-lookup"><span data-stu-id="18421-119">After the expert reviews an initial assessment set of 500 files, Relevance can determine the current margin of error of the recall values.</span></span> <span data-ttu-id="18421-120">相关性还将建议达到默认误差范围以优化评估集。</span><span class="sxs-lookup"><span data-stu-id="18421-120">Relevance will also recommend a default margin of error to reach to optimize the assessment set.</span></span> <span data-ttu-id="18421-121">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="18421-121">Here are some examples:</span></span>
  
- <span data-ttu-id="18421-122">如果评估集已产生加减 10% 的误差，相关性将建议继续培训 (无需额外评估) 。</span><span class="sxs-lookup"><span data-stu-id="18421-122">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend moving on to training (no additional assessment review is needed).</span></span> 

- <span data-ttu-id="18421-123">如果评估集产生正负 13% 的误差范围，相关性可能会建议审阅另一组评估文件以达到较小的边距。</span><span class="sxs-lookup"><span data-stu-id="18421-123">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 

- <span data-ttu-id="18421-124">如果丰富度非常低，相关性可能会建议停止评估，即使误差范围较大 (则统计信息) 不切实际，因为达到有用误差范围所需的评估集过大。</span><span class="sxs-lookup"><span data-stu-id="18421-124">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>

<span data-ttu-id="18421-125">每个问题都有自己的丰富内容、当前误差量以及估计的额外评估文件数。</span><span class="sxs-lookup"><span data-stu-id="18421-125">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files.</span></span> <span data-ttu-id="18421-126">下一个评估集根据单个评估集 (最多 1，000 个文件数创建) 。</span><span class="sxs-lookup"><span data-stu-id="18421-126">The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="18421-127">您可以接受相关性建议或根据需要调整当前误差区。</span><span class="sxs-lookup"><span data-stu-id="18421-127">You can accept the Relevance recommendations or adjust the current margin of error according to your needs.</span></span> <span data-ttu-id="18421-128">确定错误的默认当前边距，以等于或高于 75% 的返回量。</span><span class="sxs-lookup"><span data-stu-id="18421-128">The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="18421-129">可通过清除每个问题的"评估"复选框，然后清除"所有问题"，在展开的问题的"相关性跟踪"选项卡中绕过评估阶段。 **\>**</span><span class="sxs-lookup"><span data-stu-id="18421-129">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="18421-130">因此，此问题将没有任何统计信息。</span><span class="sxs-lookup"><span data-stu-id="18421-130">As a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="18421-131">只有在 **执行评估** 之前，才能清除"评估"复选框。</span><span class="sxs-lookup"><span data-stu-id="18421-131">Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="18421-132">如果一种情况下存在多个问题，则仅在清除每个问题的复选框时绕过评估。</span><span class="sxs-lookup"><span data-stu-id="18421-132">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue.</span></span>
