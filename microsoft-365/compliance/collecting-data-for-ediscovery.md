---
title: 收集高级电子数据展示中案例的数据
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
description: 了解如何使用高级电子数据展示中的搜索工具在调查中确定要审阅的文档集。
ms.custom: seo-marvel-2020
ms.openlocfilehash: b69127f1a372a9b843b9c7dac1b2909dd80b2988
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751261"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="98389-103">收集高级电子数据展示中案例的数据</span><span class="sxs-lookup"><span data-stu-id="98389-103">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="98389-104">一旦确定了与案例相关保管人和数据源，就该确定要深入探究的文档集了。</span><span class="sxs-lookup"><span data-stu-id="98389-104">Once you've identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="98389-105">您可以使用高级电子数据展示中的搜索工具在 Microsoft 365 中识别来自当前位置和非查询位置的相关文档。</span><span class="sxs-lookup"><span data-stu-id="98389-105">You can use the Search tool in Advanced eDiscovery to identify relevant documents from custodial and non-custodial locations in Microsoft 365.</span></span>

<span data-ttu-id="98389-106">运行搜索后，您可以查看检索到的项目（如与搜索查询匹配项目最多的位置）的统计信息。</span><span class="sxs-lookup"><span data-stu-id="98389-106">After you run a search, you can view statistics on the retrieved items, such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="98389-107">您还可以预览结果的子集。</span><span class="sxs-lookup"><span data-stu-id="98389-107">You can also preview a subset of the results.</span></span> <span data-ttu-id="98389-108">确定要进一步检查的文档集后，可以将搜索结果添加到审阅集以收集和处理。</span><span class="sxs-lookup"><span data-stu-id="98389-108">When you've identified the set of documents you want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="98389-109">创建搜索</span><span class="sxs-lookup"><span data-stu-id="98389-109">Create a search</span></span>

<span data-ttu-id="98389-110">选择 **"搜索**"选项卡上的"新建搜索"将启动向导，引导您完成创建搜索。</span><span class="sxs-lookup"><span data-stu-id="98389-110">Selecting **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="98389-111">若要详细了解如何创建搜索，请参阅 ["创建搜索"以收集数据](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="98389-111">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="98389-112">创建搜索后，将显示包含详细信息的飞出页。</span><span class="sxs-lookup"><span data-stu-id="98389-112">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="98389-113">"**统计信息\*\*\*\*"** 和"预览"按钮最初不可用，因为搜索尚未完成。</span><span class="sxs-lookup"><span data-stu-id="98389-113">The **Statistics** and **Preview** buttons are initially unavailable because the search hasn't completed yet.</span></span> <span data-ttu-id="98389-114">您可以在"搜索"选项卡上跟踪搜索 **进度** 。</span><span class="sxs-lookup"><span data-stu-id="98389-114">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="98389-115">查看搜索结果和统计信息</span><span class="sxs-lookup"><span data-stu-id="98389-115">View search results and statistics</span></span>

<span data-ttu-id="98389-116">内容搜索有两个组件：统计信息 (估计) 预览。</span><span class="sxs-lookup"><span data-stu-id="98389-116">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="98389-117">当每个组件完成时，你将看到"搜索"选项卡上相应列中显示的状态从"已提交"更改为"**正在完成\*\*\*\*"。**</span><span class="sxs-lookup"><span data-stu-id="98389-117">As each of these components complete, you'll see the status displayed in the corresponding columns on the **Searches** tab change from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="98389-118">完成搜索估计后，选择搜索以显示飞出页，其中将显示有关搜索结果的一些高级统计信息。</span><span class="sxs-lookup"><span data-stu-id="98389-118">Once the search estimate is completed, select the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="98389-119">此时，" **统计信息"** 按钮将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="98389-119">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="98389-120">可以选择它以查看搜索统计信息，例如：</span><span class="sxs-lookup"><span data-stu-id="98389-120">You can select it to see search statistics, such as:</span></span>

- <span data-ttu-id="98389-121">摘要</span><span class="sxs-lookup"><span data-stu-id="98389-121">Summary</span></span>
- <span data-ttu-id="98389-122">首要位置</span><span class="sxs-lookup"><span data-stu-id="98389-122">Top locations</span></span>
- <span data-ttu-id="98389-123">查询</span><span class="sxs-lookup"><span data-stu-id="98389-123">Queries</span></span>

<span data-ttu-id="98389-124">有关搜索统计信息详细信息，请参阅 [搜索统计信息](search-statistics-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="98389-124">For more information about search statistics, see [Search statistics](search-statistics-in-advanced-ediscovery.md).</span></span>

<span data-ttu-id="98389-125">预览完成后 **，预览按钮** 将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="98389-125">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="98389-126">选择它可预览结果的样本子集。</span><span class="sxs-lookup"><span data-stu-id="98389-126">Select it to preview a sampled subset of the results.</span></span>

## <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="98389-127">将搜索结果添加到审阅集</span><span class="sxs-lookup"><span data-stu-id="98389-127">Add search results to a review set</span></span>

<span data-ttu-id="98389-128">准备好收集和处理搜索的整个结果后，可以通过将搜索结果添加到审阅集来完成。</span><span class="sxs-lookup"><span data-stu-id="98389-128">When you're ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="98389-129">有关详细信息，请参阅["将数据添加到审阅集"。](add-data-to-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="98389-129">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span>

## <a name="add-non-microsoft-365-data-to-a-review-set"></a><span data-ttu-id="98389-130">将非 Microsoft 365 数据添加到审阅集</span><span class="sxs-lookup"><span data-stu-id="98389-130">Add non-Microsoft 365 data to a review set</span></span>

<span data-ttu-id="98389-131">作为案例收集过程的一部分，您还可以将非 Office 365 数据添加到审阅集，并查看和分析使用搜索工具收集的 Office 365 数据。</span><span class="sxs-lookup"><span data-stu-id="98389-131">As part of the collection process for a case, you can also add non-Office 365 data to a review set and review and analyze together with the Office 365 data that you collected by using the search tool.</span></span> <span data-ttu-id="98389-132">添加非 Office 365 时，必须将其与案例的特定保管人关联。</span><span class="sxs-lookup"><span data-stu-id="98389-132">When you add non-Office 365, you have to associate it with a specific custodian in the case.</span></span> <span data-ttu-id="98389-133">有关详细信息，请参阅将 [非 Microsoft 365 数据加载到审阅集](load-non-Office-365-data-into-a-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="98389-133">For more information, see [Load non-Microsoft 365 data into a review set](load-non-Office-365-data-into-a-review-set.md).</span></span>
