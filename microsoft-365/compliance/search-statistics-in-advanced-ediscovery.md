---
title: 提前电子数据展示中的搜索统计信息
f1.keywords:
- NOCSH
ms.author: markjjo
author: esclee
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
description: 通过查看在高级电子数据展示中运行集合搜索后生成的统计信息，验证您的搜索结果。
ms.openlocfilehash: ef5653a76d94272ba5f608149648f1421198929a
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286078"
---
# <a name="search-statistics-in-advanced-ediscovery"></a><span data-ttu-id="9cd77-103">高级电子数据展示中的搜索统计信息</span><span class="sxs-lookup"><span data-stu-id="9cd77-103">Search statistics in Advanced eDiscovery</span></span>

<span data-ttu-id="9cd77-104">验证搜索结果的一种方法是查看结果周围的统计信息，以确保它们符合您的预期。</span><span class="sxs-lookup"><span data-stu-id="9cd77-104">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations.</span></span> <span data-ttu-id="9cd77-105">搜索完成后，"搜索详细信息" 浮出控件上将显示高级别统计信息：</span><span class="sxs-lookup"><span data-stu-id="9cd77-105">When a search completes, high-level statistics are shown on the search details flyout:</span></span>

- <span data-ttu-id="9cd77-106">搜索检索到的项目数和数量</span><span class="sxs-lookup"><span data-stu-id="9cd77-106">Number and volume of items retrieved by the search</span></span>

- <span data-ttu-id="9cd77-107">在搜索位置中找到的部分索引或未编制索引的项目的编号和数量</span><span class="sxs-lookup"><span data-stu-id="9cd77-107">Number and volume of partially indexed or unindexed items that were found in the search locations</span></span>

- <span data-ttu-id="9cd77-108">搜索的邮箱和位置的数量。</span><span class="sxs-lookup"><span data-stu-id="9cd77-108">Number of mailboxes and locations searched.</span></span>
<span data-ttu-id="9cd77-109">若要查看更详细的统计信息，请单击 "搜索详细信息" 浮出控件中的 "统计信息"。</span><span class="sxs-lookup"><span data-stu-id="9cd77-109">In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary-view"></a><span data-ttu-id="9cd77-110">摘要视图</span><span class="sxs-lookup"><span data-stu-id="9cd77-110">Summary view</span></span>

<span data-ttu-id="9cd77-111">在摘要视图中，您可以查看按位置类型划分的搜索结果 (例如，Exchange) 。</span><span class="sxs-lookup"><span data-stu-id="9cd77-111">In the Summary view, you can see the search results broken down by location type (e.g. Exchange).</span></span> <span data-ttu-id="9cd77-112">对于每个位置类型，您可以查看以下内容：</span><span class="sxs-lookup"><span data-stu-id="9cd77-112">For each location type, you can see:</span></span>

- <span data-ttu-id="9cd77-113">包含符合搜索条件的项目的位置数</span><span class="sxs-lookup"><span data-stu-id="9cd77-113">Number of locations that had items that matched the search conditions</span></span>

- <span data-ttu-id="9cd77-114">来自符合搜索条件的这些位置的项目数</span><span class="sxs-lookup"><span data-stu-id="9cd77-114">Number of items from these locations that matched the search conditions</span></span>

- <span data-ttu-id="9cd77-115">符合搜索条件的项的总数量。</span><span class="sxs-lookup"><span data-stu-id="9cd77-115">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations-view"></a><span data-ttu-id="9cd77-116">顶部位置视图</span><span class="sxs-lookup"><span data-stu-id="9cd77-116">Top locations view</span></span>

<span data-ttu-id="9cd77-117">在 "顶部位置" 视图中，可以看到具有最匹配项的各个位置。</span><span class="sxs-lookup"><span data-stu-id="9cd77-117">In the Top locations view, you see the individual locations with the most matches.</span></span> <span data-ttu-id="9cd77-118">对于每个位置，您将看到：</span><span class="sxs-lookup"><span data-stu-id="9cd77-118">For each location, you will see:</span></span>

- <span data-ttu-id="9cd77-119">位置名称 (例如 SharePoint URL) </span><span class="sxs-lookup"><span data-stu-id="9cd77-119">Location name (e.g. SharePoint URL)</span></span>

- <span data-ttu-id="9cd77-120">位置类型</span><span class="sxs-lookup"><span data-stu-id="9cd77-120">Location type</span></span>

- <span data-ttu-id="9cd77-121">匹配搜索条件的项目数</span><span class="sxs-lookup"><span data-stu-id="9cd77-121">Number of items that matched the search conditions</span></span>

- <span data-ttu-id="9cd77-122">符合搜索条件的项的总数量。</span><span class="sxs-lookup"><span data-stu-id="9cd77-122">Total volume of items that matched the search conditions.</span></span>

## <a name="queries-view"></a><span data-ttu-id="9cd77-123">查询视图</span><span class="sxs-lookup"><span data-stu-id="9cd77-123">Queries view</span></span>

<span data-ttu-id="9cd77-124">如果您已在查询中使用 (c:s) 关键字或关键字行，则可以在 "每个位置的查询视图" 类型中查看查询细目。</span><span class="sxs-lookup"><span data-stu-id="9cd77-124">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type.</span></span> <span data-ttu-id="9cd77-125">对于每个位置类型，您将看到：</span><span class="sxs-lookup"><span data-stu-id="9cd77-125">For each location type, you will see:</span></span>

- <span data-ttu-id="9cd77-126">部分：此列将包含 "Primary" 或 "关键字" 一词。</span><span class="sxs-lookup"><span data-stu-id="9cd77-126">Part: this column will either have the word "Primary" or "Keyword".</span></span> <span data-ttu-id="9cd77-127">"Primary" 表示该行显示整个查询的统计信息，而 "关键字" 表示查询组件之一。</span><span class="sxs-lookup"><span data-stu-id="9cd77-127">"Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="9cd77-128">查询：行所引用的实际查询组件。</span><span class="sxs-lookup"><span data-stu-id="9cd77-128">Query: the actual query component the row refers to.</span></span> <span data-ttu-id="9cd77-129">如果 Part 为 "Primary"，则为整个查询;如果 Part 为 "关键字"，你将在此处看到一个查询组件。</span><span class="sxs-lookup"><span data-stu-id="9cd77-129">If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="9cd77-130">当您在未指定任何关键字) 的情况下搜索所有 contentin 邮箱时 (，实际查询 (大小 >= 0) 以便返回所有项目</span><span class="sxs-lookup"><span data-stu-id="9cd77-130">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="9cd77-131">当您搜索 SharePoint Online 和 OneDrive for Business 网站时，将添加以下两个组件：</span><span class="sxs-lookup"><span data-stu-id="9cd77-131">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="9cd77-132">NOT IsExternalContent： 1-排除本地 SharePoint 组织中的任何内容</span><span class="sxs-lookup"><span data-stu-id="9cd77-132">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="9cd77-133">NOT isOneNotePage： 1-排除所有 OneNote 文件，因为这些文件是与搜索查询相匹配的任何文档的重复项。</span><span class="sxs-lookup"><span data-stu-id="9cd77-133">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="9cd77-134">包含符合搜索条件的项目的位置的数量。</span><span class="sxs-lookup"><span data-stu-id="9cd77-134">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="9cd77-135">来自这些位置的符合搜索条件的项目数。</span><span class="sxs-lookup"><span data-stu-id="9cd77-135">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="9cd77-136">符合搜索条件的项的总数量。</span><span class="sxs-lookup"><span data-stu-id="9cd77-136">Total volume of items that matched the search conditions.</span></span>
