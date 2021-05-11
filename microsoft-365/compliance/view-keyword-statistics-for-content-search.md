---
title: 查看电子数据展示搜索结果的统计信息
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 了解如何使用搜索统计信息功能在合规性中心中显示与核心电子数据展示案例关联的内容搜索Microsoft 365统计信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311090"
---
# <a name="view-statistics-for-ediscovery-search-results"></a><span data-ttu-id="67feb-103">查看电子数据展示搜索结果的统计信息</span><span class="sxs-lookup"><span data-stu-id="67feb-103">View statistics for eDiscovery search results</span></span>

<span data-ttu-id="67feb-104">创建并运行内容搜索或与核心电子数据展示案例关联的搜索后，可以查看有关估计搜索结果的统计信息。</span><span class="sxs-lookup"><span data-stu-id="67feb-104">After you create and run a Content search or a search associated with a Core eDiscovery case, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="67feb-105">这包括搜索结果 (类似于显示在搜索飞出页) 上的估计搜索结果摘要、查询统计信息（如具有与搜索查询匹配的项目的内容位置数量）和具有最匹配项目的内容位置的标识。</span><span class="sxs-lookup"><span data-stu-id="67feb-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed on the search flyout page), the query statistics such as the number of content locations with items that match the search query, and the identity of content locations that have the most matching items.</span></span>
  
<span data-ttu-id="67feb-106">此外，您可以使用关键字列表配置搜索以返回搜索查询中每个关键字的统计信息。</span><span class="sxs-lookup"><span data-stu-id="67feb-106">Additionally, you can use the keywords list to configure a search to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="67feb-107">这样，您可以比较查询中每个关键字返回的结果数。</span><span class="sxs-lookup"><span data-stu-id="67feb-107">This lets you compare the number of results returned by each keyword in a query.</span></span>
  
<span data-ttu-id="67feb-108">还可以将搜索统计信息下载到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="67feb-108">You can also download search statistics to a CSV file.</span></span> <span data-ttu-id="67feb-109">此操作使你能够使用 Excel 中的筛选和排序功能来比较结果，并准备搜索结果报告。</span><span class="sxs-lookup"><span data-stu-id="67feb-109">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-searches"></a><span data-ttu-id="67feb-110">获取搜索统计信息</span><span class="sxs-lookup"><span data-stu-id="67feb-110">Get statistics for searches</span></span>

<span data-ttu-id="67feb-111">显示内容搜索或与核心电子数据展示案例关联的搜索的统计信息：</span><span class="sxs-lookup"><span data-stu-id="67feb-111">To display statistics for a Content search or a search associated with a Core eDiscovery case.:</span></span>
  
1. <span data-ttu-id="67feb-112">在Microsoft 365合规中心 **，单击"** 全部显示"，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="67feb-112">In the Microsoft 365 compliance center, click **Show all**, and then do one of the following:</span></span>

   - <span data-ttu-id="67feb-113">单击 **"内容** 搜索"，然后选择一个搜索以显示该飞出页。</span><span class="sxs-lookup"><span data-stu-id="67feb-113">Click **Content search** and then select a search to display the flyout page.</span></span>

     <span data-ttu-id="67feb-114">OR</span><span class="sxs-lookup"><span data-stu-id="67feb-114">OR</span></span>

   - <span data-ttu-id="67feb-115">单击 **"电子数据展示** 核心"，选择一个案例，然后在"搜索"选项卡上选择搜索以显示  >  该飞出页面。 </span><span class="sxs-lookup"><span data-stu-id="67feb-115">Click **eDiscovery** > **Core**, select a case, and then select a search on the **Searches** tab to display the flyout page.</span></span>

2. <span data-ttu-id="67feb-116">在所选搜索的飞出页面上，单击" **搜索统计信息"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="67feb-116">On the flyout page of the selected search, click the **Search statistics** tab.</span></span>
  
   !["搜索统计信息"选项卡](../media/SearchStatistics1.png)

<span data-ttu-id="67feb-118">" **搜索统计信息** "选项卡包含以下部分，其中包含有关搜索的不同类型的统计信息。</span><span class="sxs-lookup"><span data-stu-id="67feb-118">The **Search statistics** tab contains for following sections that contain different types of statistics about the search.</span></span>

### <a name="search-content"></a><span data-ttu-id="67feb-119">搜索内容</span><span class="sxs-lookup"><span data-stu-id="67feb-119">Search content</span></span>

<span data-ttu-id="67feb-120">此部分显示搜索返回的估计项目的图形摘要。</span><span class="sxs-lookup"><span data-stu-id="67feb-120">This section displays a graphical summary of the estimated items returned by the search.</span></span> <span data-ttu-id="67feb-121">这指示与搜索条件匹配的项目数。</span><span class="sxs-lookup"><span data-stu-id="67feb-121">This indicates the number of items that match the search criteria.</span></span> <span data-ttu-id="67feb-122">通过此信息，您可以了解搜索返回的预计项目数。</span><span class="sxs-lookup"><span data-stu-id="67feb-122">This information gives you an idea about the estimated number of items returned by the search.</span></span>

![搜索估计值](../media/SearchContentReport.png)

- <span data-ttu-id="67feb-124">**按位置估计的项目**：搜索返回的估计项目总数。</span><span class="sxs-lookup"><span data-stu-id="67feb-124">**Estimated items by locations**: The total number of estimated items returned by the search.</span></span> <span data-ttu-id="67feb-125">还会显示位于邮箱和网站中的特定数量的项目。</span><span class="sxs-lookup"><span data-stu-id="67feb-125">The specific number of items located in mailboxes and located in sites is also displayed.</span></span>

- <span data-ttu-id="67feb-126">**估计发生位置**：包含搜索返回的项目的内容位置总数。</span><span class="sxs-lookup"><span data-stu-id="67feb-126">**Estimated locations with hits**: The total number of content locations that contain items returned by the search.</span></span> <span data-ttu-id="67feb-127">还会显示特定数量的邮箱和站点位置。</span><span class="sxs-lookup"><span data-stu-id="67feb-127">The specific number of mailbox and site locations is also displayed.</span></span>

- <span data-ttu-id="67feb-128">**按位置数据量 (MB) ：** 搜索返回的所有估计项目的总大小。</span><span class="sxs-lookup"><span data-stu-id="67feb-128">**Data volume by location (in MB)**: The total size of all estimated items returned by the search.</span></span> <span data-ttu-id="67feb-129">还会显示邮箱项目和网站项目的特定大小。</span><span class="sxs-lookup"><span data-stu-id="67feb-129">The specific size of mailbox items and site items is also displayed.</span></span>

### <a name="condition-report"></a><span data-ttu-id="67feb-130">条件报告</span><span class="sxs-lookup"><span data-stu-id="67feb-130">Condition report</span></span>

<span data-ttu-id="67feb-131">此部分显示有关搜索查询和与搜索查询的不同部分匹配的估计项目数的统计信息。</span><span class="sxs-lookup"><span data-stu-id="67feb-131">This section displays statistics about the search query and the number of estimated items that matched different parts of the search query.</span></span> <span data-ttu-id="67feb-132">可以使用这些统计信息来分析与搜索查询的每个组件匹配的项数。</span><span class="sxs-lookup"><span data-stu-id="67feb-132">You can use these statistics to analyze the number of items that match each component of search query.</span></span> <span data-ttu-id="67feb-133">这可以帮助您优化搜索条件，并在必要时缩小范围。</span><span class="sxs-lookup"><span data-stu-id="67feb-133">This can help you refine the search criteria and if necessary narrow the scope of the scope.</span></span> <span data-ttu-id="67feb-134">您还可以下载 CSV 格式的此报告副本。</span><span class="sxs-lookup"><span data-stu-id="67feb-134">You can also download a copy of this report in CSV format.</span></span>

![条件报告](../media/SearchContentReportNoKeywordList.png)

- <span data-ttu-id="67feb-136">**位置** 类型：查询统计信息适用于的内容位置的类型。</span><span class="sxs-lookup"><span data-stu-id="67feb-136">**Location type**: The type of content location that the query statistics are applicable to.</span></span> <span data-ttu-id="67feb-137">值 **Exchange邮箱** 位置;值 **SharePoint站点** 位置。</span><span class="sxs-lookup"><span data-stu-id="67feb-137">The value of **Exchange** indicates a mailbox location; a value of **SharePoint** indicates a site location.</span></span>

- <span data-ttu-id="67feb-138">**部分**：统计信息适用于的搜索查询部分。</span><span class="sxs-lookup"><span data-stu-id="67feb-138">**Part**: The part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="67feb-139">**Primary** 指示整个搜索查询。</span><span class="sxs-lookup"><span data-stu-id="67feb-139">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="67feb-140">**Keyword** 指示行中的统计信息用于特定关键字。</span><span class="sxs-lookup"><span data-stu-id="67feb-140">**Keyword** indicates the statistics in the row are for a specific keyword.</span></span> <span data-ttu-id="67feb-141">如果使用关键字列表进行搜索查询，则此表中将包含查询的每个组件的统计信息。</span><span class="sxs-lookup"><span data-stu-id="67feb-141">If you use a keyword list for search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="67feb-142">有关详细信息，请参阅获取 [搜索的关键字统计信息](#get-keyword-statistics-for-searches)。</span><span class="sxs-lookup"><span data-stu-id="67feb-142">For more information, see [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span></span>

- <span data-ttu-id="67feb-143">**条件**：实际组件 (关键字或) 返回相应行中显示的统计信息的搜索查询的关键字或条件。</span><span class="sxs-lookup"><span data-stu-id="67feb-143">**Condition**: The actual component (keyword or condition) of the search query that returned the statistics displayed in the corresponding row.</span></span>

- <span data-ttu-id="67feb-144">**命中位置**：由"位置类型"列 (指定) 包含与条件列中列出的主查询或关键字查询匹配的项的内容 **位置** 的数量。</span><span class="sxs-lookup"><span data-stu-id="67feb-144">**Locations with hits**: The number of the content locations (specified by the **Location type** column) that contain items that match the primary or keyword query listed in the **Condition** column.</span></span>

- <span data-ttu-id="67feb-145">**Items**：指定内容 (与条件列中列出的) 匹配 **的项目数。**</span><span class="sxs-lookup"><span data-stu-id="67feb-145">**Items**: The number of items (from the specified content location) that match the query listed in the **Condition** column.</span></span> <span data-ttu-id="67feb-146">如前所述，如果一个项目包含要搜索的关键字的多个实例，则此列中只计算一次。</span><span class="sxs-lookup"><span data-stu-id="67feb-146">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in this column.</span></span>

- <span data-ttu-id="67feb-147">**大小 (MB) ：** 在"条件"列中 (搜索查询匹配的) 位置找到的所有 **项目** 的总大小。</span><span class="sxs-lookup"><span data-stu-id="67feb-147">**Size (MB)**: The total size of all items that were found (in the specified content location) that match the search query in the **Condition** column.</span></span>

### <a name="top-locations"></a><span data-ttu-id="67feb-148">热门位置</span><span class="sxs-lookup"><span data-stu-id="67feb-148">Top locations</span></span>

<span data-ttu-id="67feb-149">此部分显示搜索返回的项目最多的特定内容位置的统计信息。</span><span class="sxs-lookup"><span data-stu-id="67feb-149">This section displays statistics about the specific content locations with the most items returned by the search.</span></span> <span data-ttu-id="67feb-150">将会显示前 1,000 个位置。</span><span class="sxs-lookup"><span data-stu-id="67feb-150">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="67feb-151">您还可以下载 CSV 格式的此报告副本。</span><span class="sxs-lookup"><span data-stu-id="67feb-151">You can also download a copy of this report in CSV format.</span></span>

- <span data-ttu-id="67feb-152">位置名称的名称 (邮箱的电子邮件地址和网站名称的 URL) 。</span><span class="sxs-lookup"><span data-stu-id="67feb-152">The name of the location name (the email address of mailboxes and the URL for sites).</span></span>

- <span data-ttu-id="67feb-153">邮箱 (网站的位置类型) 。</span><span class="sxs-lookup"><span data-stu-id="67feb-153">Location type (a mailbox or site).</span></span>

- <span data-ttu-id="67feb-154">搜索返回的内容位置中的估计项目数。</span><span class="sxs-lookup"><span data-stu-id="67feb-154">Estimated number of items in the content location returned by the search.</span></span>

- <span data-ttu-id="67feb-155">每个内容位置中估计项目的总大小。</span><span class="sxs-lookup"><span data-stu-id="67feb-155">The total size of estimated items in each content location.</span></span>

## <a name="get-keyword-statistics-for-searches"></a><span data-ttu-id="67feb-156">获取搜索的关键字统计信息</span><span class="sxs-lookup"><span data-stu-id="67feb-156">Get keyword statistics for searches</span></span>

<span data-ttu-id="67feb-157">如前 **文所述，** 条件报告部分显示搜索查询，以及 (查询) 项的大小和大小。</span><span class="sxs-lookup"><span data-stu-id="67feb-157">As previous explained, the **Condition report** section shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="67feb-158">如果您在创建或编辑搜索查询时使用关键字列表，您可以获取增强统计信息，以显示与每个关键字或关键字短语匹配的项数。</span><span class="sxs-lookup"><span data-stu-id="67feb-158">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="67feb-159">这可以帮助您快速确定查询的哪些部分最有效 (最) 有效。</span><span class="sxs-lookup"><span data-stu-id="67feb-159">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="67feb-160">例如，如果关键字返回大量项目，您可以选择优化关键字查询以缩小搜索结果范围。</span><span class="sxs-lookup"><span data-stu-id="67feb-160">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span>

<span data-ttu-id="67feb-161">若要创建关键字列表并查看搜索的关键字统计信息，</span><span class="sxs-lookup"><span data-stu-id="67feb-161">To create a keyword list and view keyword statistics for a search:</span></span>
  
1. <span data-ttu-id="67feb-162">在Microsoft 365中心，创建新的内容搜索或与核心电子数据展示案例关联的搜索。</span><span class="sxs-lookup"><span data-stu-id="67feb-162">In the Microsoft 365 compliance center, create a new Content search or a search associated with a Core eDiscovery case.</span></span>

2. <span data-ttu-id="67feb-163">在搜索 **向导** 的"条件"页上。</span><span class="sxs-lookup"><span data-stu-id="67feb-163">On the **Conditions** page of the search wizard.</span></span> <span data-ttu-id="67feb-164">选中" **显示关键字列表"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="67feb-164">select the **Show keyword list** checkbox.</span></span>

   ![显示关键字列表复选框](../media/SearchKeywordsList1.png)

3. <span data-ttu-id="67feb-166">在关键字表中的行中键入关键字或关键字阶段。</span><span class="sxs-lookup"><span data-stu-id="67feb-166">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="67feb-167">例如，第一行中键入 **budget，** 第二行键入 **security，** 第三行键入 **FY2021。**</span><span class="sxs-lookup"><span data-stu-id="67feb-167">For example, type **budget** in the first row, type **security** in the second row, and type **FY2021** in the third row.</span></span>

   ![在列表中键入最多 20 个关键字或关键字短语](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > <span data-ttu-id="67feb-169">为了帮助减少由大型关键字列表导致的问题，搜索查询的关键字列表中最多只能有 20 行。</span><span class="sxs-lookup"><span data-stu-id="67feb-169">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

4. <span data-ttu-id="67feb-170">将关键字添加到要搜索并获取其统计信息的列表后，运行搜索。</span><span class="sxs-lookup"><span data-stu-id="67feb-170">After adding the keywords to the list that you want to search and get statistics for, run the search.</span></span>

5. <span data-ttu-id="67feb-171">搜索完成后，选择它以显示飞出页面。</span><span class="sxs-lookup"><span data-stu-id="67feb-171">When the search is completed, select it to display the flyout page.</span></span>

6. <span data-ttu-id="67feb-172">在"**搜索统计信息**"选项卡上，单击"条件"报告以显示搜索的关键字统计信息。</span><span class="sxs-lookup"><span data-stu-id="67feb-172">On the **Search statistics** tab, click the **Condition report** to display the keyword statistics for the search.</span></span>

    ![将显示每个关键字的统计信息](../media/SearchKeywordsList3.png)
  
    <span data-ttu-id="67feb-174">如前面的屏幕截图中所示，将显示每个关键字的统计信息;这包括：</span><span class="sxs-lookup"><span data-stu-id="67feb-174">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span>

    - <span data-ttu-id="67feb-175">搜索中包含的每种类型的内容位置的关键字统计信息。</span><span class="sxs-lookup"><span data-stu-id="67feb-175">The keyword statistics for each type of content location included in the search.</span></span>

    - <span data-ttu-id="67feb-176">未索引邮箱项目的数量。</span><span class="sxs-lookup"><span data-stu-id="67feb-176">The number of unindexed mailbox items.</span></span>

    - <span data-ttu-id="67feb-177">每个关键字的实际搜索查询和结果 (在"部件"列中标识为) 关键字，其中包括搜索查询的任何条件。</span><span class="sxs-lookup"><span data-stu-id="67feb-177">The actual search query and results for each keyword (identified as **Keyword** in the **Part** column), which includes any conditions from the search query.</span></span>

    - <span data-ttu-id="67feb-178">完整的搜索查询 (在"部件"列中) **标识** 为"主要"，并且每个位置类型的完整查询的统计信息。</span><span class="sxs-lookup"><span data-stu-id="67feb-178">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query for each location type.</span></span> <span data-ttu-id="67feb-179">请注意，这些统计信息与"摘要"选项卡 **上显示的** 统计信息相同。</span><span class="sxs-lookup"><span data-stu-id="67feb-179">Note these are the same statistics displayed on the **Summary** tab.</span></span>
