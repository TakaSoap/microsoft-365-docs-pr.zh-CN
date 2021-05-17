---
title: 高级电子数据展示中的搜索统计信息
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 通过查看在网站集中运行集合搜索后生成的统计信息来验证Advanced eDiscovery。
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750773"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="20361-103">搜索中的搜索Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="20361-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="20361-104">您可以验证搜索结果的一种方式是查看有关结果的统计信息，以确保它们符合您的预期。</span><span class="sxs-lookup"><span data-stu-id="20361-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="20361-105">搜索完成后，搜索详细信息飞出上会显示高级统计信息：</span><span class="sxs-lookup"><span data-stu-id="20361-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="20361-106">搜索检索的项目数和数量</span><span class="sxs-lookup"><span data-stu-id="20361-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="20361-107">在搜索位置找到的部分索引项或未编制索引的项目的数量和数量</span><span class="sxs-lookup"><span data-stu-id="20361-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="20361-108">搜索的邮箱数和位置。</span><span class="sxs-lookup"><span data-stu-id="20361-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="20361-109">若要查看更详细的统计信息，请单击搜索详细信息飞出框的"统计信息"。</span><span class="sxs-lookup"><span data-stu-id="20361-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="20361-110">摘要视图</span><span class="sxs-lookup"><span data-stu-id="20361-110">Summary view</span></span>

<span data-ttu-id="20361-111">在"摘要"视图中，您可以查看按位置类型细分的搜索结果 (例如Exchange) 。</span><span class="sxs-lookup"><span data-stu-id="20361-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="20361-112">对于每个位置类型，你可以看到：</span><span class="sxs-lookup"><span data-stu-id="20361-112">For each location type, you can see:</span></span>

- <span data-ttu-id="20361-113">项目符合搜索条件的位置数量</span><span class="sxs-lookup"><span data-stu-id="20361-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="20361-114">这些位置中符合搜索条件的项目数</span><span class="sxs-lookup"><span data-stu-id="20361-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="20361-115">与搜索条件匹配的项目总数。</span><span class="sxs-lookup"><span data-stu-id="20361-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="20361-116">顶部位置视图</span><span class="sxs-lookup"><span data-stu-id="20361-116">Top locations view</span></span>

<span data-ttu-id="20361-117">在"顶部位置"视图中，可以看到匹配项最多的单个位置。</span><span class="sxs-lookup"><span data-stu-id="20361-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="20361-118">对于每个位置，你将看到：</span><span class="sxs-lookup"><span data-stu-id="20361-118">For each location, you will see:</span></span>

- <span data-ttu-id="20361-119">位置名称 (例如 URL SharePoint URL) </span><span class="sxs-lookup"><span data-stu-id="20361-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="20361-120">位置类型</span><span class="sxs-lookup"><span data-stu-id="20361-120">Location type</span></span>

- <span data-ttu-id="20361-121">与搜索条件匹配的项目数</span><span class="sxs-lookup"><span data-stu-id="20361-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="20361-122">与搜索条件匹配的项目总数。</span><span class="sxs-lookup"><span data-stu-id="20361-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="20361-123">查询视图</span><span class="sxs-lookup"><span data-stu-id="20361-123">Queries view</span></span>

<span data-ttu-id="20361-124">如果在查询中使用了 (c：s) 关键字或关键字行，可以在查询视图中按位置类型查看查询细分。</span><span class="sxs-lookup"><span data-stu-id="20361-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="20361-125">对于每个位置类型，你将看到：</span><span class="sxs-lookup"><span data-stu-id="20361-125">For each location type, you will see:</span></span>

- <span data-ttu-id="20361-126">部分：此列将具有单词"Primary"或"Keyword"。</span><span class="sxs-lookup"><span data-stu-id="20361-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="20361-127">"Primary"表示该行显示整个查询的统计信息，而"Keyword"表示查询组件之一。</span><span class="sxs-lookup"><span data-stu-id="20361-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="20361-128">Query：行引用的实际查询组件。</span><span class="sxs-lookup"><span data-stu-id="20361-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="20361-129">如果 Part 为"Primary"，这将是整个查询;如果 Part 是"Keyword"，你将在此处看到其中一个查询组件。</span><span class="sxs-lookup"><span data-stu-id="20361-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="20361-130">当您通过不指定任何关键字 (搜索邮箱中) 时，实际查询的大小为 (>= 0) 以便返回所有项目</span><span class="sxs-lookup"><span data-stu-id="20361-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="20361-131">当您搜索 SharePoint Online OneDrive for Business网站时，会添加以下两个组件：</span><span class="sxs-lookup"><span data-stu-id="20361-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="20361-132">NOT IsExternalContent：1 - 从本地部署组织SharePoint内容</span><span class="sxs-lookup"><span data-stu-id="20361-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="20361-133">NOT isOneNotePage： 1 - 排除所有OneNote文件，因为这些文件是匹配搜索查询的任何文档的重复项。</span><span class="sxs-lookup"><span data-stu-id="20361-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="20361-134">项目符合搜索条件的位置数。</span><span class="sxs-lookup"><span data-stu-id="20361-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="20361-135">这些位置中与搜索条件匹配的项目数。</span><span class="sxs-lookup"><span data-stu-id="20361-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="20361-136">与搜索条件匹配的项目总数。</span><span class="sxs-lookup"><span data-stu-id="20361-136">Total volume of items that matched the search conditions.</span></span>
