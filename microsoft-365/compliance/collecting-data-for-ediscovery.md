---
title: 在高级电子数据展示中收集事例数据
f1.keywords:
- NOCSH
ms.author: esclee
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
description: ''
ms.openlocfilehash: a6b86d9f86edc427e10c02a99e3cda3e5e79db66
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595849"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="27dc0-102">在高级电子数据展示中收集事例数据</span><span class="sxs-lookup"><span data-stu-id="27dc0-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="27dc0-103">确定了您的保管人和数据源对您的情况有意义之后，就可以确定要深入研究的文档集。</span><span class="sxs-lookup"><span data-stu-id="27dc0-103">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="27dc0-104">您可以使用高级电子数据展示中的搜索工具，在 Office 365 中从 custodial 和非 custodial 位置进行识别。</span><span class="sxs-lookup"><span data-stu-id="27dc0-104">You can use the Search tool in Advanced eDiscovery to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="27dc0-105">运行搜索后，可以查看检索的项目的统计信息，例如与搜索查询匹配项目数最多的位置。</span><span class="sxs-lookup"><span data-stu-id="27dc0-105">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="27dc0-106">您还可以预览结果的子集。</span><span class="sxs-lookup"><span data-stu-id="27dc0-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="27dc0-107">在确定要进一步检查的文档集后，可以将搜索结果添加到审阅集以供收集和处理。</span><span class="sxs-lookup"><span data-stu-id="27dc0-107">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="27dc0-108">创建搜索</span><span class="sxs-lookup"><span data-stu-id="27dc0-108">Create a search</span></span>

<span data-ttu-id="27dc0-109">在 "**搜索**" 选项卡上选择 "**新建搜索**" 将启动向导，指导您完成创建搜索。</span><span class="sxs-lookup"><span data-stu-id="27dc0-109">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="27dc0-110">有关如何创建搜索的详细信息，请参阅[创建搜索以收集数据](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="27dc0-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="27dc0-111">创建搜索后，会显示包含详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="27dc0-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="27dc0-112">"**统计信息**" 和 "**预览**" 按钮最初不可用，因为搜索尚未完成。</span><span class="sxs-lookup"><span data-stu-id="27dc0-112">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="27dc0-113">您可以在 "**搜索**" 选项卡上跟踪搜索进度。</span><span class="sxs-lookup"><span data-stu-id="27dc0-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="27dc0-114">查看搜索结果和统计信息</span><span class="sxs-lookup"><span data-stu-id="27dc0-114">View search results and statistics</span></span>

<span data-ttu-id="27dc0-115">内容搜索有两个组件：统计信息（估计）和预览。</span><span class="sxs-lookup"><span data-stu-id="27dc0-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="27dc0-116">每个组件完成后，您将看到 "**搜索**" 选项卡上的相应列中显示的状态将从 "已**提交**到**进行中**" 更改为 "**已完成**"。</span><span class="sxs-lookup"><span data-stu-id="27dc0-116">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="27dc0-117">完成搜索估计后，选择搜索以显示弹出页面，这将显示有关搜索结果的一些高级统计信息。</span><span class="sxs-lookup"><span data-stu-id="27dc0-117">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="27dc0-118">在这种情况下，"**统计**" 按钮将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="27dc0-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="27dc0-119">您可以选择它以查看搜索统计信息，例如：</span><span class="sxs-lookup"><span data-stu-id="27dc0-119">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="27dc0-120">摘要</span><span class="sxs-lookup"><span data-stu-id="27dc0-120">Summary</span></span>
- <span data-ttu-id="27dc0-121">顶部位置</span><span class="sxs-lookup"><span data-stu-id="27dc0-121">Top locations</span></span>
- <span data-ttu-id="27dc0-122">Queries</span><span class="sxs-lookup"><span data-stu-id="27dc0-122">Queries</span></span>

<span data-ttu-id="27dc0-123">有关搜索统计信息的详细信息，请参阅[搜索统计](search-statistics.md)信息。</span><span class="sxs-lookup"><span data-stu-id="27dc0-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="27dc0-124">完成预览后，**预览**按钮将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="27dc0-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="27dc0-125">选择它可预览结果的样本子集。</span><span class="sxs-lookup"><span data-stu-id="27dc0-125">Select it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-review-set"></a><span data-ttu-id="27dc0-126">将搜索结果添加到审阅集</span><span class="sxs-lookup"><span data-stu-id="27dc0-126">Adding search results to a review set</span></span>

<span data-ttu-id="27dc0-127">当您准备收集和处理整个搜索结果时，您可以通过将其添加到审阅集来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="27dc0-127">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="27dc0-128">有关详细信息，请参阅[将数据添加到审阅集](add-data-to-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="27dc0-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>
