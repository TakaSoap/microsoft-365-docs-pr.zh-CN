---
title: 高级电子数据展示限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解适用于 Microsoft 365 高级电子数据展示解决方案的情况限制、索引编制限制和搜索限制。
ms.openlocfilehash: 145d5de5027a9d6171215c0602a733ced5265657
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445318"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="ccca6-103">高级电子数据展示中的限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="ccca6-104">本文介绍了 Microsoft 365 高级电子数据展示解决方案中的限制。</span><span class="sxs-lookup"><span data-stu-id="ccca6-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="ccca6-105">案例和审阅集限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-105">Case and review set limits</span></span>

<span data-ttu-id="ccca6-106">下表列出了高级电子数据展示中事例和审阅集的限制。</span><span class="sxs-lookup"><span data-stu-id="ccca6-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

| <span data-ttu-id="ccca6-107">限制说明</span><span class="sxs-lookup"><span data-stu-id="ccca6-107">Description of limit</span></span> | <span data-ttu-id="ccca6-108">限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-108">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ccca6-109">可以添加到案例的文档总数， (审阅集的) 。</span><span class="sxs-lookup"><span data-stu-id="ccca6-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="ccca6-110">3 百万</span><span class="sxs-lookup"><span data-stu-id="ccca6-110">3 million</span></span> <br/> |
|<span data-ttu-id="ccca6-111">每个负载集的总文件大小。</span><span class="sxs-lookup"><span data-stu-id="ccca6-111">Total file size per load set.</span></span> <span data-ttu-id="ccca6-112">这包括将非 Office 365 加载到审阅集。</span><span class="sxs-lookup"><span data-stu-id="ccca6-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="ccca6-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="ccca6-113">300 GB</span></span> <br/> |
|<span data-ttu-id="ccca6-114">每天加载到组织的所有审阅集的数据总量。</span><span class="sxs-lookup"><span data-stu-id="ccca6-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="ccca6-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="ccca6-115">2 TB</span></span> <br/> |
|<span data-ttu-id="ccca6-116">每个案例的最大负载集数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-116">Maximum number of load sets per case.</span></span>  <br/> |<span data-ttu-id="ccca6-117">200</span><span class="sxs-lookup"><span data-stu-id="ccca6-117">200</span></span> <br/> |
|<span data-ttu-id="ccca6-118">每个案例的最大审阅集数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="ccca6-119">20</span><span class="sxs-lookup"><span data-stu-id="ccca6-119">20</span></span> <br/> |
|<span data-ttu-id="ccca6-120">每个案例的最大标记组数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-120">Maximum number of tag groups per case.</span></span>  <br/> |<span data-ttu-id="ccca6-121">1000</span><span class="sxs-lookup"><span data-stu-id="ccca6-121">1000</span></span> <br/> |
|<span data-ttu-id="ccca6-122">每个案例的最大标记数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-122">Maximum number of tags per case.</span></span>  <br/> |<span data-ttu-id="ccca6-123">1000</span><span class="sxs-lookup"><span data-stu-id="ccca6-123">1000</span></span> <br/> |
|<span data-ttu-id="ccca6-124">将内容添加到审阅集的组织中的最大并发作业数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-124">Maximum concurrent jobs in your organization to add content to a review set.</span></span> <span data-ttu-id="ccca6-125">这些作业名为 **"将数据添加到审阅集"，** 并显示在案例的" **作业"选项卡** 上。</span><span class="sxs-lookup"><span data-stu-id="ccca6-125">These jobs are named **Adding data to a review set** and are displayed on the **Jobs** tab in a case.</span></span>| <span data-ttu-id="ccca6-126">10 <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ccca6-126">10 <sup>4</sup></span></span> |
|<span data-ttu-id="ccca6-127">每个用户向审阅集添加内容的最大并发作业数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-127">Maximum concurrent jobs to add content to a review set per user.</span></span> <span data-ttu-id="ccca6-128">这些作业名为 **"将数据添加到审阅集"，** 并显示在案例的" **作业"选项卡** 上。</span><span class="sxs-lookup"><span data-stu-id="ccca6-128">These jobs are named **Adding data to a review set** and are displayed on the **Jobs** tab in a case.</span></span> | <span data-ttu-id="ccca6-129">3</span><span class="sxs-lookup"><span data-stu-id="ccca6-129">3</span></span> |
|||

## <a name="hold-limits"></a><span data-ttu-id="ccca6-130">保留限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-130">Hold limits</span></span>

<span data-ttu-id="ccca6-131">下表列出了与高级电子数据展示案例相关联的保留的限制。</span><span class="sxs-lookup"><span data-stu-id="ccca6-131">The following table lists the limits for holds associated with an Advanced eDiscovery case.</span></span>

| <span data-ttu-id="ccca6-132">限制说明</span><span class="sxs-lookup"><span data-stu-id="ccca6-132">Description of limit</span></span> | <span data-ttu-id="ccca6-133">限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-133">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ccca6-134">单个案例保留中的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-134">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="ccca6-135">此限制包括用户邮箱总数，以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的邮箱总数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-135">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span> <br/> |<span data-ttu-id="ccca6-136">1,000</span><span class="sxs-lookup"><span data-stu-id="ccca6-136">1,000</span></span>  <br/> |
|<span data-ttu-id="ccca6-137">单个案例保留中的最大网站数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-137">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="ccca6-138">此限制包括 OneDrive for Business 网站、SharePoint 网站以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的网站总数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-138">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="ccca6-139">100</span><span class="sxs-lookup"><span data-stu-id="ccca6-139">100</span></span>  <br/> |

## <a name="indexing-limits"></a><span data-ttu-id="ccca6-140">索引限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-140">Indexing limits</span></span>

<span data-ttu-id="ccca6-141">下表列出了高级电子数据展示中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="ccca6-141">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

| <span data-ttu-id="ccca6-142">限制说明</span><span class="sxs-lookup"><span data-stu-id="ccca6-142">Description of limit</span></span> | <span data-ttu-id="ccca6-143">限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-143">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ccca6-144">从单个文件提取的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-144">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="ccca6-145">1000 万<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ccca6-145">10 million<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="ccca6-146">单个文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ccca6-146">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="ccca6-147">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ccca6-147">100 MB<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="ccca6-148">文档中嵌入项目的最大深度。</span><span class="sxs-lookup"><span data-stu-id="ccca6-148">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="ccca6-149">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ccca6-149">25<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="ccca6-150">由光学字符识别处理的文件的最大大小 (OCR) 。</span><span class="sxs-lookup"><span data-stu-id="ccca6-150">Maximum size of files processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="ccca6-151">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ccca6-151">24 MB<sup>1</sup></span></span> <br/> 
|<span data-ttu-id="ccca6-152">每个组织每天的最大索引作业数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-152">Maximum number of indexing jobs per organization per day.</span></span> <br/> |<span data-ttu-id="ccca6-153">10<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="ccca6-153">10<sup>6</sup></span></span> <br/>|  
|||

## <a name="search-limits"></a><span data-ttu-id="ccca6-154">搜索限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-154">Search limits</span></span>

<span data-ttu-id="ccca6-155">本节中所述的限制与使用"搜索"选项卡上的搜索工具收集案件集数据相关。</span><span class="sxs-lookup"><span data-stu-id="ccca6-155">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="ccca6-156">有关详细信息，请参阅收集高级 [电子数据展示中案例的数据](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="ccca6-156">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

| <span data-ttu-id="ccca6-157">限制说明</span><span class="sxs-lookup"><span data-stu-id="ccca6-157">Description of limit</span></span> | <span data-ttu-id="ccca6-158">限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-158">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ccca6-159">可以在单个搜索中搜索的最大邮箱或网站数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-159">Maximum number of mailboxes or sites that can be searched in a single search.</span></span> |<span data-ttu-id="ccca6-160">无限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-160">No limit</span></span>|
|<span data-ttu-id="ccca6-161">可以同时运行的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-161">Maximum number of searches that can run at the same time.</span></span> |<span data-ttu-id="ccca6-162">无限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-162">No limit</span></span> |
|<span data-ttu-id="ccca6-163">单个用户可以同时启动的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-163">Maximum number of searches that a single user can start at the same time.</span></span> |<span data-ttu-id="ccca6-164">10  </span><span class="sxs-lookup"><span data-stu-id="ccca6-164">10</span></span> | 
|<span data-ttu-id="ccca6-165">搜索查询记录的最大字符数 (运算符和条件) 。</span><span class="sxs-lookup"><span data-stu-id="ccca6-165">Maximum number of characters for a search query (including operators and conditions).</span></span> |<span data-ttu-id="ccca6-166">10，000 &nbsp; <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ccca6-166">10,000&nbsp;<sup>2</sup></span></span>|
|<span data-ttu-id="ccca6-167">前缀通配符的最小 alpha 字符数;例如，一 **\* *个 _* 或 \* _ set**。</span><span class="sxs-lookup"><span data-stu-id="ccca6-167">Minimum number of alpha characters for prefix wildcards; for example, \**one\**_ or _\* set\*\*\*.</span></span>|<span data-ttu-id="ccca6-168">3</span><span class="sxs-lookup"><span data-stu-id="ccca6-168">3</span></span> |  
|<span data-ttu-id="ccca6-169">使用前缀通配符搜索精确短语时，或者使用前缀通配符和 **NEAR** 布尔运算符时返回的最大变量数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-169">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span> |<span data-ttu-id="ccca6-170">10，000 &nbsp; <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ccca6-170">10,000&nbsp;<sup>3</sup></span></span>|
|<span data-ttu-id="ccca6-171">在搜索的预览页面上显示的每个用户邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-171">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="ccca6-172">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="ccca6-172">The newest items are displayed.</span></span> |<span data-ttu-id="ccca6-173">100</span><span class="sxs-lookup"><span data-stu-id="ccca6-173">100</span></span>|
|<span data-ttu-id="ccca6-174">预览页面上显示用于搜索的所有邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-174">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>|<span data-ttu-id="ccca6-175">1,000</span><span class="sxs-lookup"><span data-stu-id="ccca6-175">1,000</span></span>|
|<span data-ttu-id="ccca6-176">可预览搜索结果的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-176">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="ccca6-177">如果超过 1000 个邮箱包含与搜索查询匹配的项目，则仅前 1，000 个邮箱具有最多结果可供预览。</span><span class="sxs-lookup"><span data-stu-id="ccca6-177">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="ccca6-178">1,000</span><span class="sxs-lookup"><span data-stu-id="ccca6-178">1,000</span></span>|
|<span data-ttu-id="ccca6-179">预览页面上显示用于搜索的 SharePoint 和 OneDrive for Business 网站的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-179">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="ccca6-180">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="ccca6-180">The newest items are displayed.</span></span> |<span data-ttu-id="ccca6-181">200</span><span class="sxs-lookup"><span data-stu-id="ccca6-181">200</span></span>|
|<span data-ttu-id="ccca6-182">可预览搜索结果的 SharePoint 和 OneDrive for Business 网站的最大数量。</span><span class="sxs-lookup"><span data-stu-id="ccca6-182">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="ccca6-183">如果包含与搜索查询匹配的项目的网站超过 200 个，则仅具有最多结果的前 200 个网站可供预览。</span><span class="sxs-lookup"><span data-stu-id="ccca6-183">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>|<span data-ttu-id="ccca6-184">200</span><span class="sxs-lookup"><span data-stu-id="ccca6-184">200</span></span>|
|<span data-ttu-id="ccca6-185">在预览页面上显示用于搜索的公用文件夹邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-185">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span> |<span data-ttu-id="ccca6-186">100</span><span class="sxs-lookup"><span data-stu-id="ccca6-186">100</span></span>|
|<span data-ttu-id="ccca6-187">在预览页面上显示用于搜索的所有公用文件夹邮箱项中查找的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-187">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span> |<span data-ttu-id="ccca6-188">200</span><span class="sxs-lookup"><span data-stu-id="ccca6-188">200</span></span>|
|<span data-ttu-id="ccca6-189">可预览搜索结果的公用文件夹邮箱的最大数量。</span><span class="sxs-lookup"><span data-stu-id="ccca6-189">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="ccca6-190">如果超过 500 个公用文件夹邮箱包含与搜索查询匹配的项目，则只有结果最多的前 500 个邮箱可供预览。</span><span class="sxs-lookup"><span data-stu-id="ccca6-190">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="ccca6-191">500</span><span class="sxs-lookup"><span data-stu-id="ccca6-191">500</span></span>|
|||

## <a name="search-times"></a><span data-ttu-id="ccca6-192">搜索时间</span><span class="sxs-lookup"><span data-stu-id="ccca6-192">Search times</span></span>

<span data-ttu-id="ccca6-193">Microsoft 收集所有组织运行的搜索的性能信息。</span><span class="sxs-lookup"><span data-stu-id="ccca6-193">Microsoft collects performance information for searches run by all organizations.</span></span> <span data-ttu-id="ccca6-194">尽管搜索查询的复杂性可能会影响搜索项，但是影响搜索所需时长的最大因素仍然是搜索的邮箱数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-194">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="ccca6-195">尽管 Microsoft 不提供用于搜索次数的服务级别协议，但下表根据搜索中包含的邮箱数列出了集合搜索的平均搜索时间。</span><span class="sxs-lookup"><span data-stu-id="ccca6-195">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for collection searches based on the number of mailboxes included in the search.</span></span>
  
  |<span data-ttu-id="ccca6-196">**邮箱数**</span><span class="sxs-lookup"><span data-stu-id="ccca6-196">**Number of mailboxes**</span></span>|<span data-ttu-id="ccca6-197">**平均搜索时间**</span><span class="sxs-lookup"><span data-stu-id="ccca6-197">**Average search time**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="ccca6-198">100</span><span class="sxs-lookup"><span data-stu-id="ccca6-198">100</span></span>  <br/> |<span data-ttu-id="ccca6-199">30 秒</span><span class="sxs-lookup"><span data-stu-id="ccca6-199">30 seconds</span></span>  <br/> |
  |<span data-ttu-id="ccca6-200">1,000</span><span class="sxs-lookup"><span data-stu-id="ccca6-200">1,000</span></span>  <br/> |<span data-ttu-id="ccca6-201">45 秒</span><span class="sxs-lookup"><span data-stu-id="ccca6-201">45 seconds</span></span>  <br/> |
  |<span data-ttu-id="ccca6-202">10,000</span><span class="sxs-lookup"><span data-stu-id="ccca6-202">10,000</span></span>  <br/> |<span data-ttu-id="ccca6-203">4 分钟</span><span class="sxs-lookup"><span data-stu-id="ccca6-203">4 minutes</span></span>  <br/> |
  |<span data-ttu-id="ccca6-204">25,000</span><span class="sxs-lookup"><span data-stu-id="ccca6-204">25,000</span></span>  <br/> |<span data-ttu-id="ccca6-205">10 分钟</span><span class="sxs-lookup"><span data-stu-id="ccca6-205">10 minutes</span></span>  <br/> |
  |<span data-ttu-id="ccca6-206">50,000</span><span class="sxs-lookup"><span data-stu-id="ccca6-206">50,000</span></span>  <br/> |<span data-ttu-id="ccca6-207">20 分钟</span><span class="sxs-lookup"><span data-stu-id="ccca6-207">20 minutes</span></span>  <br/> |
  |<span data-ttu-id="ccca6-208">100,000</span><span class="sxs-lookup"><span data-stu-id="ccca6-208">100,000</span></span>  <br/> |<span data-ttu-id="ccca6-209">25 分钟</span><span class="sxs-lookup"><span data-stu-id="ccca6-209">25 minutes</span></span>  <br/> |
  |||

## <a name="viewer-limits"></a><span data-ttu-id="ccca6-210">查看器限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-210">Viewer limits</span></span>

| <span data-ttu-id="ccca6-211">限制说明</span><span class="sxs-lookup"><span data-stu-id="ccca6-211">Description of limit</span></span> | <span data-ttu-id="ccca6-212">限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-212">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ccca6-213">可在本机查看器中查看的 Excel 文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ccca6-213">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="ccca6-214">4 MB</span><span class="sxs-lookup"><span data-stu-id="ccca6-214">4 MB</span></span>  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a><span data-ttu-id="ccca6-215">导出限制 - 最终导出审阅集</span><span class="sxs-lookup"><span data-stu-id="ccca6-215">Export limits - Final export out of Review Set</span></span>

<span data-ttu-id="ccca6-216">本节中所述的限制与将文档从审阅集导出有关。</span><span class="sxs-lookup"><span data-stu-id="ccca6-216">The limits described in this section are related to exporting documents out of a review set.</span></span>

| <span data-ttu-id="ccca6-217">限制说明</span><span class="sxs-lookup"><span data-stu-id="ccca6-217">Description of limit</span></span> | <span data-ttu-id="ccca6-218">限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-218">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ccca6-219">单个导出的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ccca6-219">Maximum size of a single export.</span></span>|<span data-ttu-id="ccca6-220">300 万个文档或 100 GB，以较小者为准</span><span class="sxs-lookup"><span data-stu-id="ccca6-220">3 million documents or 100 GB, whichever is smaller</span></span>|
|<span data-ttu-id="ccca6-221">每个审阅集的最大并发导出数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-221">Maximum concurrent exports per review set.</span></span> | <span data-ttu-id="ccca6-222">1</span><span class="sxs-lookup"><span data-stu-id="ccca6-222">1</span></span> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="ccca6-223">查看集下载限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-223">Review set download limits</span></span>

| <span data-ttu-id="ccca6-224">限制说明</span><span class="sxs-lookup"><span data-stu-id="ccca6-224">Description of limit</span></span> | <span data-ttu-id="ccca6-225">限制</span><span class="sxs-lookup"><span data-stu-id="ccca6-225">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ccca6-226">总文件大小或从审阅集下载的最大文档数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-226">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="ccca6-227">3 MB 或 50 个文档 <sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ccca6-227">3 MB or 50 documents <sup>5</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="ccca6-228"><sup>1</sup> 任何超过单个文件限制的项目都将显示为处理错误。</span><span class="sxs-lookup"><span data-stu-id="ccca6-228"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span>
>
> <span data-ttu-id="ccca6-229"><sup>2</sup> 在搜索 SharePoint 和 OneDrive for Business 位置时，所搜索网站的 URL 中的字符数将计入此限制。</span><span class="sxs-lookup"><span data-stu-id="ccca6-229"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span>
>
> <span data-ttu-id="ccca6-230"><sup>3</sup> 对于非短语 (使用不使用双引号的关键字) 我们使用了特殊的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="ccca6-230"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="ccca6-231">这将告诉我们一个单词在文档中出现，而不是在文档中出现位置。</span><span class="sxs-lookup"><span data-stu-id="ccca6-231">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="ccca6-232">若要对包含双引号 (关键字值执行短语查询) ，我们需要比较短语中单词在文档中的位置。</span><span class="sxs-lookup"><span data-stu-id="ccca6-232">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="ccca6-233">这意味着不能将前缀索引用于短语查询。</span><span class="sxs-lookup"><span data-stu-id="ccca6-233">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="ccca6-234">在这种情况下，我们使用前缀扩展到的所有可能的单词在内部扩展查询;例如 **，time \* *_ 可以展开到 _*"time OR timer OR times OR timex OR timeboxed OR ..."。**</span><span class="sxs-lookup"><span data-stu-id="ccca6-234">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\**_ can expand to  _*"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="ccca6-235">限制 10，000 是单词可以扩展到的最大变体数，而不是与查询匹配的文档数。</span><span class="sxs-lookup"><span data-stu-id="ccca6-235">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="ccca6-236">非短语搜索词没有上限。</span><span class="sxs-lookup"><span data-stu-id="ccca6-236">There is no upper limit for non-phrase terms.</span></span>
>
> <span data-ttu-id="ccca6-237"><sup>4</sup> 此限制与其他电子数据展示工具中的内容导出共享。</span><span class="sxs-lookup"><span data-stu-id="ccca6-237"><sup>4</sup> This limit is shared with exporting content in other eDiscovery tools.</span></span> <span data-ttu-id="ccca6-238">这意味着内容搜索和核心电子数据展示中的并发导出 (以及向高级电子数据展示服务中的审阅集添加内容) 都针对此限制应用。</span><span class="sxs-lookup"><span data-stu-id="ccca6-238">This means that concurrent exports in Content search and Core eDiscovery (and adding content to review sets in Advanced eDiscovery) are all applied against this limit.</span></span>
>
> <span data-ttu-id="ccca6-239"><sup>5</sup> 此限制适用于从审阅集下载所选文档。</span><span class="sxs-lookup"><span data-stu-id="ccca6-239"><sup>5</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="ccca6-240">它不适用于从审阅集导出文档。</span><span class="sxs-lookup"><span data-stu-id="ccca6-240">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="ccca6-241">有关下载和导出文档的信息，请参阅在高级电子数据展示 [中导出案例数据](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="ccca6-241">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span>
>
> <span data-ttu-id="ccca6-242"><sup>6</sup> 每个组织每天的索引编制限制。</span><span class="sxs-lookup"><span data-stu-id="ccca6-242"><sup>6</sup> Indexing limits per organization per day.</span></span> <span data-ttu-id="ccca6-243">作为一种解决方法，您可以在"数据源"选项卡上选择一个案例的多个保管人，然后单击"更新索引"以避免为每个保管人创建单独的索引作业。</span><span class="sxs-lookup"><span data-stu-id="ccca6-243">As a workaround, you can select multiple custodians on the **Data sources** tab in a case and then click **Update index** to avoid creating a separate index job for each custodian.</span></span> 
