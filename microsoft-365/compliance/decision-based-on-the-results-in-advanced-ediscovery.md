---
title: 根据高级电子数据展示中的结果做出决策
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 了解高级电子数据展示中的"确定"选项卡如何提供可帮助您确定案例文件审阅集的正确大小的数据。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0423a21520375f1d9de8e2eaeca142b979ff1883
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759864"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="0fb35-103">根据高级电子数据展示和经典 (结果做出) </span><span class="sxs-lookup"><span data-stu-id="0fb35-103">Decision based on the results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="0fb35-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="0fb35-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="0fb35-106">在高级电子数据展示中，"决定"选项卡提供用于查看和使用决策支持统计信息以确定案例文件审阅集大小的其他信息。</span><span class="sxs-lookup"><span data-stu-id="0fb35-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="0fb35-107">使用"确定"选项卡</span><span class="sxs-lookup"><span data-stu-id="0fb35-107">Using the Decide tab</span></span>

![相关性决定](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="0fb35-109">此选项卡包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="0fb35-109">This tab includes the following components:</span></span>
  
- <span data-ttu-id="0fb35-110">**问题**：在这里，可以从列表中选择感兴趣的问题。</span><span class="sxs-lookup"><span data-stu-id="0fb35-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="0fb35-111">**Review-recall ratio：** Comparisons of Advanced eDiscovery review according to Relevance scores.</span><span class="sxs-lookup"><span data-stu-id="0fb35-111">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="0fb35-112">图表中的截止点表示要审阅的文件百分比，映射到相关性分数。</span><span class="sxs-lookup"><span data-stu-id="0fb35-112">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="0fb35-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span><span class="sxs-lookup"><span data-stu-id="0fb35-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="0fb35-114">要审阅的文件数的默认截止点位于"撤回"和"精度"之间的最佳平衡点。</span><span class="sxs-lookup"><span data-stu-id="0fb35-114">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="0fb35-115">实际截止点由用户根据目标以及成本权衡 (%review) 和风险 (%recall) 。</span><span class="sxs-lookup"><span data-stu-id="0fb35-115">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="0fb35-116">使用滑块，可以调整截止点，并查看图形和参数的影响、调整要检索的相关文件的百分比以及验证决策之前的效果。</span><span class="sxs-lookup"><span data-stu-id="0fb35-116">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="0fb35-117">**参数**：Review、Recall、Next 相关参数和总成本参数是与整个案例的集合相关的审阅集的累积计算统计信息。</span><span class="sxs-lookup"><span data-stu-id="0fb35-117">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="0fb35-118">这些参数的定义如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fb35-118">Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="0fb35-119">**Review**： Percentage of files to review based on this cutoff.</span><span class="sxs-lookup"><span data-stu-id="0fb35-119">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="0fb35-120">**回顾**：审阅集内相关文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="0fb35-120">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="0fb35-121">**下一个** 相关：查看和标识当前不在审阅集内的其他相关文件的成本。</span><span class="sxs-lookup"><span data-stu-id="0fb35-121">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="0fb35-122">**总成本**：查看此案例文件的百分比的成本。</span><span class="sxs-lookup"><span data-stu-id="0fb35-122">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="0fb35-123">成本参数设置由案例管理器设置。</span><span class="sxs-lookup"><span data-stu-id="0fb35-123">Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="0fb35-124">**按相关性分数分布**：左侧显示深灰色的文件低于截止分数。</span><span class="sxs-lookup"><span data-stu-id="0fb35-124">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="0fb35-125">工具提示显示相关性分数和审阅文件集内文件相对于总文件的相关百分比。</span><span class="sxs-lookup"><span data-stu-id="0fb35-125">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="0fb35-126">展开的"详细信息"窗格将显示其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="0fb35-126">The expanded Details pane displays additional details.</span></span> <span data-ttu-id="0fb35-127">集合图中的文件不包括空文件或 neb一文件。</span><span class="sxs-lookup"><span data-stu-id="0fb35-127">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="0fb35-128">系列文件数字表示未在相关性中加载但仍作为系列一部分的文件。</span><span class="sxs-lookup"><span data-stu-id="0fb35-128">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
