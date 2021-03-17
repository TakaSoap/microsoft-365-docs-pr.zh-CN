---
title: 查看内容搜索结果的关键字统计信息
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: 了解如何使用搜索统计信息功能在安全与合规中心内显示和比较&搜索的统计信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12c51c47045996e450772c081bd26ef4a520b5f
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838695"
---
# <a name="view-keyword-statistics-for-content-search-results"></a><span data-ttu-id="a303a-103">查看内容搜索结果的关键字统计信息</span><span class="sxs-lookup"><span data-stu-id="a303a-103">View keyword statistics for Content Search results</span></span>

<span data-ttu-id="a303a-104">创建并运行内容搜索后，您可以查看有关估计搜索结果的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-104">After you create and run a Content Search, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="a303a-105">这包括搜索结果 (类似于详细信息窗格) 中显示的估计搜索结果的摘要、查询统计信息（如包含与搜索查询匹配的项目的内容位置数）和具有最匹配项目的内容位置的名称。</span><span class="sxs-lookup"><span data-stu-id="a303a-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed in the details pane), the query statistics such as the number of content locations with items that match the search query, and the name of content locations that have the most matching items.</span></span> <span data-ttu-id="a303a-106">可以显示一个或多个内容搜索的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-106">You can display statistics for one or more content searches.</span></span> <span data-ttu-id="a303a-107">这样，您可以快速比较多个搜索的结果，并做出有关搜索查询有效性的决策。</span><span class="sxs-lookup"><span data-stu-id="a303a-107">This lets you to quickly compare the results for multiple searches and make decisions about the effectiveness of your search queries.</span></span>
  
<span data-ttu-id="a303a-108">此外，还可以配置新的和现有的搜索，以返回搜索查询中每个关键字的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-108">Additionally, you can configure new and existing searches to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="a303a-109">这样，您可以比较查询中每个关键字的结果数，并比较来自多个搜索的关键字统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-109">This lets you compare the number of results for each keyword in a query and to compare the keyword statistics from multiple searches.</span></span>
  
<span data-ttu-id="a303a-110">还可以将搜索统计信息和关键字统计信息下载为 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="a303a-110">You can also download the search statistics and keyword statistics to a CSV file.</span></span> <span data-ttu-id="a303a-111">此操作使你能够使用 Excel 中的筛选和排序功能来比较结果，并准备搜索结果报告。</span><span class="sxs-lookup"><span data-stu-id="a303a-111">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-content-searches"></a><span data-ttu-id="a303a-112">获取内容搜索的统计信息</span><span class="sxs-lookup"><span data-stu-id="a303a-112">Get statistics for Content Searches</span></span>

<span data-ttu-id="a303a-113">显示内容搜索的统计信息：</span><span class="sxs-lookup"><span data-stu-id="a303a-113">To display statistics for Content searches:</span></span>
  
1. <span data-ttu-id="a303a-114">在 Microsoft 365 合规中心，转到"**显示所有**  >  **内容搜索"。**</span><span class="sxs-lookup"><span data-stu-id="a303a-114">In the Microsoft 365 compliance center, go to **Show all** > **Content search**.</span></span>

2. <span data-ttu-id="a303a-115">在搜索列表中，选择两个或多个搜索，然后单击 **"批量操作**"飞出页上的"搜索统计信息"。</span><span class="sxs-lookup"><span data-stu-id="a303a-115">In the list of searches, select two or more searches, and then click **Search statistics** on the **Bulk actions** flyout page.</span></span>
    
    ![选择多个搜索，然后单击"搜索统计信息"](../media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. <span data-ttu-id="a303a-117">在" **搜索统计信息"** 页上，单击以下链接之一以显示有关所选搜索的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-117">On the **Search statistics** page, click one of the following links to display statistics about the selected searches.</span></span> 
    
    <span data-ttu-id="a303a-118">**摘要**</span><span class="sxs-lookup"><span data-stu-id="a303a-118">**Summary**</span></span>
    
    <span data-ttu-id="a303a-119">此页面显示的统计信息与内容搜索页上的详细信息窗格中显示的 **统计信息** 类似。</span><span class="sxs-lookup"><span data-stu-id="a303a-119">This page displays statistics similar to the ones displayed in the details pane on the **Content search** page.</span></span> <span data-ttu-id="a303a-120">将显示所有选定搜索的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-120">Statistics for all selected searches are displayed.</span></span> <span data-ttu-id="a303a-121">请注意，您还可以从此页重新运行所选搜索以更新统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-121">Note that you can also re-run the selected searches from this page to update the statistics.</span></span> 
    
    ![所选搜索的统计信息摘要](../media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    <span data-ttu-id="a303a-123">a.</span><span class="sxs-lookup"><span data-stu-id="a303a-123">a.</span></span>  <span data-ttu-id="a303a-124">内容搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="a303a-124">The name of the Content Search.</span></span> <span data-ttu-id="a303a-125">如前所述，可以显示和比较多个搜索的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-125">As previously stated, you can display and compare statistics for multiple searches.</span></span>
    
    <span data-ttu-id="a303a-126">b.</span><span class="sxs-lookup"><span data-stu-id="a303a-126">b.</span></span> <span data-ttu-id="a303a-127">搜索的内容位置的类型。</span><span class="sxs-lookup"><span data-stu-id="a303a-127">The type of content location that was searched.</span></span> <span data-ttu-id="a303a-128">每行显示指定搜索中的邮箱、网站和公用文件夹的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-128">Each row displays statistics for mailboxes, sites, and public folders from the specified search.</span></span>
    
    <span data-ttu-id="a303a-129">c.</span><span class="sxs-lookup"><span data-stu-id="a303a-129">c.</span></span> <span data-ttu-id="a303a-130">包含与搜索查询匹配的项的内容位置的数量。</span><span class="sxs-lookup"><span data-stu-id="a303a-130">The number of content locations containing items that match the search query.</span></span> <span data-ttu-id="a303a-131">对于邮箱，此统计信息还包括包含与搜索查询匹配的项目的存档邮箱数。</span><span class="sxs-lookup"><span data-stu-id="a303a-131">For mailboxes, this statistic also includes the number of archive mailboxes that contain items that match the search query.</span></span>
    
    <span data-ttu-id="a303a-132">d.</span><span class="sxs-lookup"><span data-stu-id="a303a-132">d.</span></span> <span data-ttu-id="a303a-133">与搜索查询匹配的所有指定内容位置的项总数。</span><span class="sxs-lookup"><span data-stu-id="a303a-133">The total number of items of all specified content locations that match the search query.</span></span> <span data-ttu-id="a303a-134">项目类型的示例包括电子邮件、日历项目和文档。</span><span class="sxs-lookup"><span data-stu-id="a303a-134">Examples of item types include email messages, calendar items, and documents.</span></span> <span data-ttu-id="a303a-135">如果某个项目包含要搜索的关键字的多个实例，则该项目在项目总数中只计数一次。</span><span class="sxs-lookup"><span data-stu-id="a303a-135">If an item contains multiple instances of a keyword that is being searched for, it's only counted once in the total number of items.</span></span> <span data-ttu-id="a303a-136">例如，如果要搜索单词"stock"或"fraud"，并且电子邮件包含三个"stock"实例，则"项目"列中只计数 **一次。**</span><span class="sxs-lookup"><span data-stu-id="a303a-136">For example, if you're searching for words "stock" or "fraud" and an email message contains three instances of the word "stock", it's only counted once in the **Items** column.</span></span> 
    
    <span data-ttu-id="a303a-137">e.</span><span class="sxs-lookup"><span data-stu-id="a303a-137">e.</span></span> <span data-ttu-id="a303a-138">在与搜索查询匹配的指定内容位置找到的所有项目的总大小。</span><span class="sxs-lookup"><span data-stu-id="a303a-138">The total size of all items that were found in the specified content location that match the search query.</span></span> 
    
    <span data-ttu-id="a303a-139">**Queries**</span><span class="sxs-lookup"><span data-stu-id="a303a-139">**Queries**</span></span>
    
    <span data-ttu-id="a303a-140">此页面显示有关搜索查询的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-140">This page displays statistics about the search query.</span></span>
    
    ![所选搜索的搜索查询统计信息](../media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    <span data-ttu-id="a303a-142">a.</span><span class="sxs-lookup"><span data-stu-id="a303a-142">a.</span></span> <span data-ttu-id="a303a-143">行包含查询统计信息的内容搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="a303a-143">The name of the Content Search that the row contains query statistics for.</span></span>
    
    <span data-ttu-id="a303a-144">b.</span><span class="sxs-lookup"><span data-stu-id="a303a-144">b.</span></span> <span data-ttu-id="a303a-145">查询统计信息适用于的内容位置的类型。</span><span class="sxs-lookup"><span data-stu-id="a303a-145">The type of content location that the query statistics are applicable to.</span></span>
    
    <span data-ttu-id="a303a-146">c.</span><span class="sxs-lookup"><span data-stu-id="a303a-146">c.</span></span> <span data-ttu-id="a303a-147">此列指示统计信息适用于的搜索查询的哪个部分。</span><span class="sxs-lookup"><span data-stu-id="a303a-147">This column indicates which part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="a303a-148">**Primary** 指示整个搜索查询。</span><span class="sxs-lookup"><span data-stu-id="a303a-148">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="a303a-149">如果您在创建或编辑搜索查询时使用关键字列表，则此表中将包含查询的每个组件的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-149">If you use a keyword list when you create or edit a search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="a303a-150">有关详细信息， [请参阅本文中的](#get-keyword-statistics-for-content-searches) 获取内容搜索的关键字统计信息部分。</span><span class="sxs-lookup"><span data-stu-id="a303a-150">See the [Get keyword statistics for Content Searches](#get-keyword-statistics-for-content-searches) section in this article for more information.</span></span> 
    
    <span data-ttu-id="a303a-151">d.</span><span class="sxs-lookup"><span data-stu-id="a303a-151">d.</span></span> <span data-ttu-id="a303a-152">此列包含内容搜索工具运行的实际搜索查询。</span><span class="sxs-lookup"><span data-stu-id="a303a-152">This column contains the actual search query that run by the Content Search tool.</span></span> <span data-ttu-id="a303a-153">请注意，该工具会自动将几个其他组件添加到您创建的查询中。</span><span class="sxs-lookup"><span data-stu-id="a303a-153">Note that the tool automatically adds a few additional components to the query that you create.</span></span> 

    - <span data-ttu-id="a303a-154">当您通过未指定关键字 (搜索邮箱中) ，实际关键字查询是以便  `size>=0` 返回所有项目。</span><span class="sxs-lookup"><span data-stu-id="a303a-154">When you search for all content in mailboxes (by not specifying any keywords), the actual key word query is  `size>=0` so that all items are returned.</span></span> 
    
     - <span data-ttu-id="a303a-155">搜索 SharePoint Online 和 OneDrive for Business 网站时，会添加以下两个组件：</span><span class="sxs-lookup"><span data-stu-id="a303a-155">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
          <span data-ttu-id="a303a-156">**NOT IsExternalContent：1** - 排除本地 SharePoint 组织的任何内容。</span><span class="sxs-lookup"><span data-stu-id="a303a-156">**NOT IsExternalContent:1** - Excludes any content from an on-premises SharePoint organization.</span></span> 
    
          <span data-ttu-id="a303a-157">**NOT IsOneNotePage：1** - 排除所有 OneNote 文件，因为这些文件是匹配搜索查询的任何文档的重复项。</span><span class="sxs-lookup"><span data-stu-id="a303a-157">**NOT IsOneNotePage:1** - Excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span> 

    
    <span data-ttu-id="a303a-158">e.</span><span class="sxs-lookup"><span data-stu-id="a303a-158">e.</span></span> <span data-ttu-id="a303a-159">由 \*\* Location type \*\* 列 (指定的内容位置) 包含与"查询"列中列出的搜索查询 **匹配的项。**</span><span class="sxs-lookup"><span data-stu-id="a303a-159">The number of the content locations (specified by the \*\* Location type \*\* column) that contain items that match the search query listed in the **Query** column.</span></span> 
    
    <span data-ttu-id="a303a-160">f.</span><span class="sxs-lookup"><span data-stu-id="a303a-160">f.</span></span> <span data-ttu-id="a303a-161">指定内容位置 (查询) "查询"列中列出的 **项目数。**</span><span class="sxs-lookup"><span data-stu-id="a303a-161">The number of items (from the specified content location) that match the search query listed in the **Query** column.</span></span> <span data-ttu-id="a303a-162">如前所述，如果一个项目包含要搜索的关键字的多个实例，则此列中只计算一次。</span><span class="sxs-lookup"><span data-stu-id="a303a-162">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in the this column.</span></span> 
    
    <span data-ttu-id="a303a-163">g.</span><span class="sxs-lookup"><span data-stu-id="a303a-163">g.</span></span> <span data-ttu-id="a303a-164">与"查询"列中的搜索查询 (匹配) 内容位置找到的所有 **项目** 的总大小。</span><span class="sxs-lookup"><span data-stu-id="a303a-164">The total size of all items that were found (in the specified content location) that match the search query in the **Query** column.</span></span> 
    
    <span data-ttu-id="a303a-165">**热门位置**</span><span class="sxs-lookup"><span data-stu-id="a303a-165">**Top locations**</span></span>
    
    <span data-ttu-id="a303a-166">此页面显示与所搜索的每个内容位置中的搜索查询匹配的项数的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-166">This page displays statistics about the number of items that match the search query in each content location that was searched.</span></span> <span data-ttu-id="a303a-167">将会显示前 1,000 个位置。</span><span class="sxs-lookup"><span data-stu-id="a303a-167">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="a303a-168">如果查看多个搜索的统计信息，将显示每个搜索的前 1，000 个位置。</span><span class="sxs-lookup"><span data-stu-id="a303a-168">If you view statistics for multiple searches, the top 1,000 locations for each search are displayed.</span></span> <span data-ttu-id="a303a-169">请注意，如果内容位置不包含与搜索查询匹配的任何项目，该位置将不包含在此页面上。</span><span class="sxs-lookup"><span data-stu-id="a303a-169">Note that a content location isn't included on this page if it doesn't contain any items that match the search query.</span></span>
    
    ![有关在搜索的内容位置找到的项目数的统计信息](../media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    <span data-ttu-id="a303a-171">a.</span><span class="sxs-lookup"><span data-stu-id="a303a-171">a.</span></span> <span data-ttu-id="a303a-172">内容位置的名称。</span><span class="sxs-lookup"><span data-stu-id="a303a-172">The name of the content location.</span></span>
    
    <span data-ttu-id="a303a-173">b.</span><span class="sxs-lookup"><span data-stu-id="a303a-173">b.</span></span> <span data-ttu-id="a303a-174">位置统计信息适用于的内容位置类型。</span><span class="sxs-lookup"><span data-stu-id="a303a-174">The type of content location that the location statistics are applicable to.</span></span>
    
    <span data-ttu-id="a303a-175">c.</span><span class="sxs-lookup"><span data-stu-id="a303a-175">c.</span></span> <span data-ttu-id="a303a-176">显示统计信息的每个搜索都有一些列。</span><span class="sxs-lookup"><span data-stu-id="a303a-176">There are columns for each search that you're displaying statistics for.</span></span> <span data-ttu-id="a303a-177">此列显示与 (位置) 查询匹配的项数和总大小。</span><span class="sxs-lookup"><span data-stu-id="a303a-177">This column shows the number (and total size) of items that match the search query in each content location.</span></span> <span data-ttu-id="a303a-178">请注意，当您显示多个搜索的统计信息时，此列中的"NA"指示该搜索中不包含内容位置。</span><span class="sxs-lookup"><span data-stu-id="a303a-178">Note that when you're displaying statistics for multiple searches, the "NA" in this column indicates that the content location wasn't included in that search.</span></span> 

## <a name="get-keyword-statistics-for-content-searches"></a><span data-ttu-id="a303a-179">获取内容搜索的关键字统计信息</span><span class="sxs-lookup"><span data-stu-id="a303a-179">Get keyword statistics for Content Searches</span></span>

<span data-ttu-id="a303a-180">如前文所示，" **查询** "页显示搜索查询，以及 (查询) 项的大小和大小。</span><span class="sxs-lookup"><span data-stu-id="a303a-180">As previous explained, the **Queries** page shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="a303a-181">如果您在创建或编辑搜索查询时使用关键字列表，您可以获取增强统计信息，以显示与每个关键字或关键字短语匹配的项数。</span><span class="sxs-lookup"><span data-stu-id="a303a-181">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="a303a-182">这可以帮助您快速确定查询的哪些部分最有效 (最) 有效。</span><span class="sxs-lookup"><span data-stu-id="a303a-182">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="a303a-183">例如，如果关键字返回大量项目，您可以选择优化关键字查询以缩小搜索结果范围。</span><span class="sxs-lookup"><span data-stu-id="a303a-183">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span> <span data-ttu-id="a303a-184">您可以在创建或编辑内容搜索时设置关键字列表。</span><span class="sxs-lookup"><span data-stu-id="a303a-184">You can set up a keyword list when you create or edit a Content Search.</span></span> 

<span data-ttu-id="a303a-185">若要创建关键字列表并查看内容搜索的关键字统计信息，</span><span class="sxs-lookup"><span data-stu-id="a303a-185">To create a keyword list and view keyword statistics for a Content Search:</span></span>
  
1. <span data-ttu-id="a303a-186">在 Microsoft 365 合规中心，转到"**显示所有**  >  **内容搜索"。**</span><span class="sxs-lookup"><span data-stu-id="a303a-186">In the Microsoft 365 compliance center, go to **Show all** > **Content search**.</span></span>
    
2. <span data-ttu-id="a303a-187">在内容搜索列表中，单击并搜索，然后单击"编辑 **编辑"** ![ 图标 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="a303a-187">In the list of content searches, click and a search, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="a303a-188">单击 **"** 查询"，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a303a-188">Click **Query** and then do the following things:</span></span> 
    
    ![单击"显示关键字列表"复选框，在每行中键入一个关键字](../media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    <span data-ttu-id="a303a-190">a.</span><span class="sxs-lookup"><span data-stu-id="a303a-190">a.</span></span> <span data-ttu-id="a303a-191">单击" **显示关键字列表** "复选框。</span><span class="sxs-lookup"><span data-stu-id="a303a-191">Click the **Show keyword list** check box.</span></span> 
    
    <span data-ttu-id="a303a-192">b.</span><span class="sxs-lookup"><span data-stu-id="a303a-192">b.</span></span> <span data-ttu-id="a303a-193">在关键字表中的行中键入关键字或关键字阶段。</span><span class="sxs-lookup"><span data-stu-id="a303a-193">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="a303a-194">例如，第一行中键入 **budget，\*\*\*\*然后在第二** 行中键入 security。</span><span class="sxs-lookup"><span data-stu-id="a303a-194">For example, type **budget** in the first row and then type **security** in the second row.</span></span> 
    
4. <span data-ttu-id="a303a-195">添加要搜索的关键字并获取其统计信息后，单击" **搜索** "运行修订后的搜索。</span><span class="sxs-lookup"><span data-stu-id="a303a-195">After adding the keywords that you want to search and get statistics for, click **Search** to run the revised search.</span></span> 
    
5. <span data-ttu-id="a303a-196">搜索完成后，在搜索列表中选择它，然后单击搜索 **统计信息** 搜索 ![ 统计信息按钮 ](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) 。</span><span class="sxs-lookup"><span data-stu-id="a303a-196">When the search is completed, select it in the list of searches, and then click **Search statistics** ![Search Statistics button](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png).</span></span> <span data-ttu-id="a303a-197">还可以显示和比较多个搜索的关键字统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-197">You can also display and compare keyword statistics for multiple searches.</span></span>
    
6. <span data-ttu-id="a303a-198">在" **搜索统计信息"** 页上， **单击"** 查询"以显示所选搜索的关键字统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-198">On the **Search statistics** page, click **Query** to display the keyword statistics for the selected searches.</span></span> 
    
    ![将显示选定搜索的每个关键字的统计信息](../media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    <span data-ttu-id="a303a-200">如前面的屏幕截图中所示，将显示每个关键字的统计信息;这包括：</span><span class="sxs-lookup"><span data-stu-id="a303a-200">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span> 
    
    - <span data-ttu-id="a303a-201">搜索中包含的每种类型的内容位置的关键字统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-201">The keyword statistics for each type of content location included in the search.</span></span>
    
    - <span data-ttu-id="a303a-202">每个关键字的实际搜索查询，其中包括搜索查询的任何条件。</span><span class="sxs-lookup"><span data-stu-id="a303a-202">The actual search query for each keyword, which includes any conditions from the search query.</span></span> 
    
    - <span data-ttu-id="a303a-203">完整的搜索查询 (**部件** 列中标识) 主查询和完整查询的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a303a-203">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query.</span></span> <span data-ttu-id="a303a-204">请注意，这些统计信息与"摘要"页上 **显示的** 统计信息相同。</span><span class="sxs-lookup"><span data-stu-id="a303a-204">Note these are the same statistics displayed on the **Summary** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="a303a-205">为了帮助减少由大型关键字列表导致的问题，现在搜索查询的关键字列表中最多只能有 20 行。</span><span class="sxs-lookup"><span data-stu-id="a303a-205">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>
