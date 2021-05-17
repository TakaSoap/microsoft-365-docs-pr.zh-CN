---
title: 根据项目结果Advanced eDiscovery
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
description: 了解 Advanced eDiscovery 中的"决定"选项卡如何提供可帮助您确定审阅案例文件集的正确大小的数据。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769147"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="9bfe9-103">基于相关性结果的决策Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9bfe9-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="9bfe9-104">在 Advanced eDiscovery 的"相关性"模块中，"决定"选项卡提供用于查看和使用决策支持统计信息以确定案例文件审阅集大小的其他信息。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="9bfe9-105">使用"决定"选项卡</span><span class="sxs-lookup"><span data-stu-id="9bfe9-105">Using the Decide tab</span></span>

![相关性决定](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="9bfe9-107">此选项卡包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="9bfe9-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="9bfe9-108">**问题**：从此处，可以从列表中选择感兴趣的问题。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="9bfe9-109">**Review-recall ratio**：根据相关性Advanced eDiscovery审阅的比较。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="9bfe9-110">图表中的截止点表示要审阅的文件百分比，映射到相关性分数。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="9bfe9-111">此阈值在相关性测试阶段使用，并用作剔除的导出阈值。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="9bfe9-112">要审阅的文件数的默认截止点位于"调用次数"和"精度"之间的最佳平衡点。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="9bfe9-113">实际截止点应该由用户根据目标以及成本权衡 (%审阅) 和风险 (%recall) 。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="9bfe9-114">使用滑块，可以调整截止点并查看图形和参数的影响、调整要检索的相关文件的百分比时以及验证决策之前的效果。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="9bfe9-115">**参数**：Review、Recall、Next 相关参数和总成本参数是相对于整个案例的集合与审阅集相关的累积计算统计信息。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="9bfe9-116">这些参数的定义如下：</span><span class="sxs-lookup"><span data-stu-id="9bfe9-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="9bfe9-117">**查看**：要基于此截止时间查看的文件百分比。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="9bfe9-118">**撤回**：审阅集内相关文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="9bfe9-119">**下一个** 相关 ：查看和标识当前不在审阅集内的另一个相关文件的成本。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="9bfe9-120">**总成本：** 查看此百分比案例文件的成本。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="9bfe9-121">成本参数设置可通过案例管理器进行设置。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="9bfe9-122">**按相关性分数分布**：左侧显示深灰色的文件低于截止分数。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="9bfe9-123">工具提示显示与总文件相关的审阅文件集内文件的相关性分数和相关百分比。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="9bfe9-124">展开的 **"详细信息"** 窗格将显示更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="9bfe9-125">集合图中的文件不包括空文件或空文件。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="9bfe9-126">系列文件数字表示未在相关性中加载，但仍作为系列一部分进行计数的文件。</span><span class="sxs-lookup"><span data-stu-id="9bfe9-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
