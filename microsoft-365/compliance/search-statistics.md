---
title: 搜索统计信息
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
description: 搜索统计信息是验证搜索结果并在 "搜索详细信息" 弹出页面上的 "状态" 下显示的有效方式。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 24de99cf0a7ae21b5966811b988c93d64abd5148
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286088"
---
# <a name="search-statistics-in-data-investigations-preview"></a><span data-ttu-id="55191-103">"数据调查" 中的搜索统计信息 (预览) </span><span class="sxs-lookup"><span data-stu-id="55191-103">Search statistics in Data Investigations (preview)</span></span>

<span data-ttu-id="55191-104">在调查数据事件时，验证搜索结果的有效方法是查看有关搜索结果的统计信息，以确保它们符合您的预期。</span><span class="sxs-lookup"><span data-stu-id="55191-104">An effective way to validate your search results when investigation a data incident is to view the statistics about your search results to make sure they align with your expectations.</span></span> <span data-ttu-id="55191-105">当搜索运行完毕时，将在 "搜索详细信息" 弹出页面上的 " **状态** " 下显示以下高级统计信息：</span><span class="sxs-lookup"><span data-stu-id="55191-105">When a search as finished running, the following high-level statistics are displayed under **Status** on the search details flyout page:</span></span>

![在 "搜索详细信息" 弹出页面上搜索 statisics](../media/SearchDetailsFlyout.png)

- <span data-ttu-id="55191-107">与搜索条件匹配的项目的估计数量和大小。</span><span class="sxs-lookup"><span data-stu-id="55191-107">The estimated number and size of items that matched the search criteria.</span></span>

- <span data-ttu-id="55191-108">部分已编制索引的项目的数量和大小 (也称为未编制索引的项目) ，这些 *项目* 不可搜索，但在搜索中包含的内容位置中找到。</span><span class="sxs-lookup"><span data-stu-id="55191-108">The number and size of partially indexed items (also called *unindexed items*) that aren't searchable but that were found in the content locations that were included in the search.</span></span>

- <span data-ttu-id="55191-109">已搜索的邮箱和网站的数量。</span><span class="sxs-lookup"><span data-stu-id="55191-109">The number of mailboxes and sites that were searched.</span></span>

<span data-ttu-id="55191-110">若要查看更多详细统计信息，请单击 "搜索详细信息" 弹出页面上的 "**统计**</span><span class="sxs-lookup"><span data-stu-id="55191-110">To view more detailed statistics, click **Statistics** on the search details flyout page.</span></span> <span data-ttu-id="55191-111">在 " **搜索统计信息** " 页上，您可以查看搜索摘要、包含与搜索结果匹配的项目的顶部位置以及有关搜索查询的详细统计信息。</span><span class="sxs-lookup"><span data-stu-id="55191-111">On the **Search statistics** page, you can view the search summary, the top location that contained items that matched the search results, and detailed statistics about the search query.</span></span>

![搜索统计信息下拉列表](../media/SearchStatisticsDropDownList.png)

## <a name="summary"></a><span data-ttu-id="55191-113">摘要</span><span class="sxs-lookup"><span data-stu-id="55191-113">Summary</span></span>

<span data-ttu-id="55191-114">在 **摘要** 视图中，可以看到按位置类型划分的搜索结果 (例如，位置包括 Exchange 邮箱和 SharePoint 网站) 。</span><span class="sxs-lookup"><span data-stu-id="55191-114">In the **Summary** view, you can see the search results broken down by location type (for example, locations include Exchange mailboxes and SharePoint sites).</span></span> <span data-ttu-id="55191-115">将为每个位置类型显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="55191-115">The following information is displayed for each location type:</span></span>

- <span data-ttu-id="55191-116">包含符合搜索条件的项目的位置数。</span><span class="sxs-lookup"><span data-stu-id="55191-116">The number of locations that had items that matched the search criteria.</span></span>

- <span data-ttu-id="55191-117">与搜索条件匹配的每个位置类型中的项目总数。</span><span class="sxs-lookup"><span data-stu-id="55191-117">The total number of items from each location type that matched the search criteria.</span></span>

- <span data-ttu-id="55191-118">与搜索条件匹配的每个位置类型中的项目的总大小。</span><span class="sxs-lookup"><span data-stu-id="55191-118">The total size of items from each location type that matched the search criteria.</span></span>

## <a name="top-locations"></a><span data-ttu-id="55191-119">顶部位置</span><span class="sxs-lookup"><span data-stu-id="55191-119">Top locations</span></span>

<span data-ttu-id="55191-120">在 " **顶部位置** " 视图中，您将看到与搜索条件匹配项最多的各个内容位置。</span><span class="sxs-lookup"><span data-stu-id="55191-120">In the **Top locations** view, you see the individual content locations with the most items that matched the search criteria.</span></span> <span data-ttu-id="55191-121">对于每个内容位置，将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="55191-121">For each content location, the following information is displayed:</span></span>

- <span data-ttu-id="55191-122">位置的名称;邮箱的电子邮件地址和 SharePoint 网站的 URL</span><span class="sxs-lookup"><span data-stu-id="55191-122">The name of the location; the email address for mailboxes and the URL for SharePoint sites</span></span>

- <span data-ttu-id="55191-123">位置类型</span><span class="sxs-lookup"><span data-stu-id="55191-123">The location type</span></span>

- <span data-ttu-id="55191-124">与搜索条件匹配的项目数</span><span class="sxs-lookup"><span data-stu-id="55191-124">Number of items that matched the search criteria</span></span>

- <span data-ttu-id="55191-125">与搜索条件匹配的所有项目的总大小。</span><span class="sxs-lookup"><span data-stu-id="55191-125">The total size of all items that matched the search criteria.</span></span>

## <a name="queries"></a><span data-ttu-id="55191-126">Queries</span><span class="sxs-lookup"><span data-stu-id="55191-126">Queries</span></span>

<span data-ttu-id="55191-127">在 " **查询** " 视图中，可以查看搜索查询每个组件的详细统计信息。</span><span class="sxs-lookup"><span data-stu-id="55191-127">In the **Queries** view, you can see detailed statistics for each component of the search query.</span></span> <span data-ttu-id="55191-128">如果您在搜索查询中使用关键字列表，则可以在 " **查询** " 视图中查看增强的统计信息，以显示与每个关键字或关键字短语匹配的项目数。</span><span class="sxs-lookup"><span data-stu-id="55191-128">If you used the keyword list in the search query, you can view enhanced statistics in the **Queries** view  that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="55191-129">这可帮助您快速确定查询的哪些部分是最 (的，并且) 效率最少。</span><span class="sxs-lookup"><span data-stu-id="55191-129">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> 

<span data-ttu-id="55191-130">**查询**视图中显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="55191-130">The following information is displayed in the **Queries** view:</span></span>

 - <span data-ttu-id="55191-131">**位置类型** -行中显示的统计信息的内容位置类型。</span><span class="sxs-lookup"><span data-stu-id="55191-131">**Location type** - The type of content location for the statistics displayed in the row.</span></span>

- <span data-ttu-id="55191-132">**Part** -此列将显示以下值之一： **Primary** 或 **关键字**。</span><span class="sxs-lookup"><span data-stu-id="55191-132">**Part** - This column will display one of the following values: **Primary** or **Keyword**.</span></span> <span data-ttu-id="55191-133">**主要** 是指该行显示整个查询的统计信息; **关键字** 表示行中的统计信息是查询组件之一。</span><span class="sxs-lookup"><span data-stu-id="55191-133">**Primary** means the row presents statistics on the entire query; **Keyword** means the statistics in the row are for one of the query components.</span></span>

- <span data-ttu-id="55191-134">**条件** -行引用的搜索查询的实际查询组件。</span><span class="sxs-lookup"><span data-stu-id="55191-134">**Condition** - The actual query component of the search query the row refers to.</span></span> <span data-ttu-id="55191-135">如果 **Part** 列中的值 **为主**，则显示整个搜索查询的统计信息;如果值为 **关键字**，则显示在 **查询** 列中显示的查询组件的统计信息。</span><span class="sxs-lookup"><span data-stu-id="55191-135">If the value in the **Part** column is **Primary**, then the statistics for the entire search query are displayed; if the value is **Keyword**, then the statistics for the component of the query shown in the **Query** column are displayed.</span></span> <span data-ttu-id="55191-136">例如，如果使用了关键字列表，则会显示其中一个关键字的统计信息。</span><span class="sxs-lookup"><span data-stu-id="55191-136">For example, if the keyword list was used, then the statistics one of the keywords are displayed.</span></span>

  <span data-ttu-id="55191-137">下面是有关 " **查询** " 列中显示的统计信息的一些其他事项：</span><span class="sxs-lookup"><span data-stu-id="55191-137">Here are some other things to know about the statistics displayed in the **Queries** column:</span></span>
  
  - <span data-ttu-id="55191-138">当您在邮箱 (中搜索所有内容时，如果未指定任何关键字) ，实际查询 \*\* (大小 >= 0) \*\* 以便返回所有项目</span><span class="sxs-lookup"><span data-stu-id="55191-138">When you search for all content in mailboxes (by not specifying any keywords), the actual query is **(size >= 0)** so that all items are returned</span></span>
  
  - <span data-ttu-id="55191-139">当您搜索 SharePoint 和 OneDrive 网站时，将在搜索查询中添加以下两个组件：</span><span class="sxs-lookup"><span data-stu-id="55191-139">When you search SharePoint and OneDrive sites, the two following components are added to the search query:</span></span>
    
    <span data-ttu-id="55191-140">**NOT IsExternalContent： 1** -排除本地 SharePoint 组织中的任何内容</span><span class="sxs-lookup"><span data-stu-id="55191-140">**NOT IsExternalContent:1** - This excludes any content from an on-premises SharePoint organization</span></span>
    
    <span data-ttu-id="55191-141">**NOT isOneNotePage： 1** -这将排除所有 OneNote 文件，因为这些文件是与搜索查询相匹配的任何文档的重复项。</span><span class="sxs-lookup"><span data-stu-id="55191-141">**NOT isOneNotePage:1** - This excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="55191-142">**搜索中的位置** 包含行中显示的部分/条件与搜索查询匹配的项目的内容位置数。</span><span class="sxs-lookup"><span data-stu-id="55191-142">**Locations in search** The number of content locations that had items that matched the search query for the part/condition displayed in the row.</span></span> <span data-ttu-id="55191-143">请注意，如果存档邮箱包含与搜索条件匹配的项目，则会将其计为一个单独的位置。</span><span class="sxs-lookup"><span data-stu-id="55191-143">Note that archive mailboxes are counted as a separate location if they contain items that match the search criteria.</span></span>

- <span data-ttu-id="55191-144">**Items** -与行中显示的部件/条件的搜索条件匹配的项目总数。</span><span class="sxs-lookup"><span data-stu-id="55191-144">**Items** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

- <span data-ttu-id="55191-145">**Size** -与行中显示的 part/condition 的搜索条件匹配的项目总数。</span><span class="sxs-lookup"><span data-stu-id="55191-145">**Size** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

