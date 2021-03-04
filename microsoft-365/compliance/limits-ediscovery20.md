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
description: 了解适用于 Microsoft 365 高级电子数据展示解决方案的情况限制、索引限制和搜索限制。
ms.openlocfilehash: 9b36407868a0f426b71a0a551d2f702d0a20b777
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423433"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="ee6dd-103">高级电子数据展示中的限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="ee6dd-104">本文介绍了 Microsoft 365 中高级电子数据展示解决方案中的限制。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="ee6dd-105">案例和审阅集限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-105">Case and review set limits</span></span>

<span data-ttu-id="ee6dd-106">下表列出了高级电子数据展示中事例和审阅集的限制。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

| <span data-ttu-id="ee6dd-107">限制说明</span><span class="sxs-lookup"><span data-stu-id="ee6dd-107">Description of limit</span></span> | <span data-ttu-id="ee6dd-108">限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-108">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ee6dd-109">可添加到案例审阅集的文档总数 (用于案例集) 。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="ee6dd-110">3 百万</span><span class="sxs-lookup"><span data-stu-id="ee6dd-110">3 million</span></span> <br/> |
|<span data-ttu-id="ee6dd-111">每个负载集的总文件大小。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-111">Total file size per load set.</span></span> <span data-ttu-id="ee6dd-112">这包括将非 Office 365 加载到审阅集。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="ee6dd-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="ee6dd-113">300 GB</span></span> <br/> |
|<span data-ttu-id="ee6dd-114">每天加载到组织的所有审阅集的总数据量。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="ee6dd-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="ee6dd-115">2 TB</span></span> <br/> |
|<span data-ttu-id="ee6dd-116">每个情况的最大负载集数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="ee6dd-117">200</span><span class="sxs-lookup"><span data-stu-id="ee6dd-117">200</span></span> <br/> |
|<span data-ttu-id="ee6dd-118">每个案例的最大审阅集数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="ee6dd-119">20</span><span class="sxs-lookup"><span data-stu-id="ee6dd-119">20</span></span> <br/> |
|<span data-ttu-id="ee6dd-120">每个案例的最大标记组数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-120">Maximum number of tag groups per case.</span></span>  <br/> |<span data-ttu-id="ee6dd-121">1000</span><span class="sxs-lookup"><span data-stu-id="ee6dd-121">1000</span></span> <br/> |
|<span data-ttu-id="ee6dd-122">每个案例的最大标记数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-122">Maximum number of tags per case.</span></span>  <br/> |<span data-ttu-id="ee6dd-123">1000</span><span class="sxs-lookup"><span data-stu-id="ee6dd-123">1000</span></span> <br/> |
|||

## <a name="hold-limits"></a><span data-ttu-id="ee6dd-124">保留限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-124">Hold limits</span></span>

<span data-ttu-id="ee6dd-125">下表列出了与高级电子数据展示案例关联的保留的限制。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-125">The following table lists the limits for holds associated with an Advanced eDiscovery case.</span></span>

| <span data-ttu-id="ee6dd-126">限制说明</span><span class="sxs-lookup"><span data-stu-id="ee6dd-126">Description of limit</span></span> | <span data-ttu-id="ee6dd-127">限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-127">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ee6dd-128">单个案例保留中的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-128">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="ee6dd-129">此限制包括用户邮箱总数以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-129">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span> <br/> |<span data-ttu-id="ee6dd-130">1,000</span><span class="sxs-lookup"><span data-stu-id="ee6dd-130">1,000</span></span>  <br/> |
|<span data-ttu-id="ee6dd-131">单个案例保留中的最大网站数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-131">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="ee6dd-132">此限制包括 OneDrive for Business 网站、SharePoint 网站以及与 Microsoft 365 组、Microsoft Teams 和 Yammer 组关联的网站的组合总数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-132">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="ee6dd-133">100</span><span class="sxs-lookup"><span data-stu-id="ee6dd-133">100</span></span>  <br/> |

## <a name="indexing-limits"></a><span data-ttu-id="ee6dd-134">索引限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-134">Indexing limits</span></span>

<span data-ttu-id="ee6dd-135">下表列出了高级电子数据展示中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-135">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

| <span data-ttu-id="ee6dd-136">限制说明</span><span class="sxs-lookup"><span data-stu-id="ee6dd-136">Description of limit</span></span> | <span data-ttu-id="ee6dd-137">限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-137">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ee6dd-138">从单个文件提取的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-138">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="ee6dd-139">1000 万<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ee6dd-139">10 million<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="ee6dd-140">单个文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-140">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="ee6dd-141">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ee6dd-141">100 MB<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="ee6dd-142">文档中嵌入项目的最大深度。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-142">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="ee6dd-143">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ee6dd-143">25<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="ee6dd-144">由光学字符识别处理的文件的最大大小 (OCR) 。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-144">Maximum size of files processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="ee6dd-145">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ee6dd-145">24 MB<sup>1</sup></span></span> <br/> 
|<span data-ttu-id="ee6dd-146">每个组织每天的最大索引作业数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-146">Maximum number of indexing jobs per organization per day.</span></span> <br/> |<span data-ttu-id="ee6dd-147">10<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="ee6dd-147">10<sup>6</sup></span></span> <br/>|  
|||

## <a name="search-limits"></a><span data-ttu-id="ee6dd-148">搜索限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-148">Search limits</span></span>

<span data-ttu-id="ee6dd-149">本节中所述的限制与使用"搜索"选项卡上的搜索工具收集案例数据相关。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-149">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="ee6dd-150">有关详细信息，请参阅 ["收集高级电子数据展示](collecting-data-for-ediscovery.md)"中案例的数据。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-150">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

| <span data-ttu-id="ee6dd-151">限制说明</span><span class="sxs-lookup"><span data-stu-id="ee6dd-151">Description of limit</span></span> | <span data-ttu-id="ee6dd-152">限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-152">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ee6dd-153">可以在单个搜索中搜索的最大邮箱数或网站数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-153">Maximum number of mailboxes or sites that can be searched in a single search.</span></span> |<span data-ttu-id="ee6dd-154">无限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-154">No limit</span></span>|
|<span data-ttu-id="ee6dd-155">可以同时运行的搜索的最大数量。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-155">Maximum number of searches that can run at the same time.</span></span> |<span data-ttu-id="ee6dd-156">无限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-156">No limit</span></span> |
|<span data-ttu-id="ee6dd-157">单个用户可以同时启动的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-157">Maximum number of searches that a single user can start at the same time.</span></span> |<span data-ttu-id="ee6dd-158">10  </span><span class="sxs-lookup"><span data-stu-id="ee6dd-158">10</span></span> | 
|<span data-ttu-id="ee6dd-159">搜索查询查询的最大字符数， (运算符和条件) 。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-159">Maximum number of characters for a search query (including operators and conditions).</span></span> |<span data-ttu-id="ee6dd-160">10，000 &nbsp; <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ee6dd-160">10,000&nbsp;<sup>2</sup></span></span>|
|<span data-ttu-id="ee6dd-161">前缀通配符的最小 alpha 字符数;例如，一 **\* *_ 或* \* _ set**。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-161">Minimum number of alpha characters for prefix wildcards; for example, \**one\**_ or _\* set\*\*\*.</span></span>|<span data-ttu-id="ee6dd-162">3 </span><span class="sxs-lookup"><span data-stu-id="ee6dd-162">3</span></span> |  
|<span data-ttu-id="ee6dd-163">使用前缀通配符搜索精确短语时，或者使用前缀通配符和 **NEAR** 布尔运算符时返回的最大变量数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-163">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span> |<span data-ttu-id="ee6dd-164">10，000 &nbsp; <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ee6dd-164">10,000&nbsp;<sup>3</sup></span></span>|
|<span data-ttu-id="ee6dd-165">在预览页上显示用于搜索的每个用户邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-165">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="ee6dd-166">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-166">The newest items are displayed.</span></span> |<span data-ttu-id="ee6dd-167">100</span><span class="sxs-lookup"><span data-stu-id="ee6dd-167">100</span></span>|
|<span data-ttu-id="ee6dd-168">预览页上显示用于搜索的所有邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-168">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>|<span data-ttu-id="ee6dd-169">1,000</span><span class="sxs-lookup"><span data-stu-id="ee6dd-169">1,000</span></span>|
|<span data-ttu-id="ee6dd-170">可以预览搜索结果的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-170">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="ee6dd-171">如果包含与搜索查询匹配的项目超过 1000 个邮箱，则只有结果最多的前 1，000 个邮箱可供预览。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-171">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="ee6dd-172">1,000</span><span class="sxs-lookup"><span data-stu-id="ee6dd-172">1,000</span></span>|
|<span data-ttu-id="ee6dd-173">预览页上显示用于搜索的 SharePoint 和 OneDrive for Business 网站的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-173">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="ee6dd-174">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-174">The newest items are displayed.</span></span> |<span data-ttu-id="ee6dd-175">200</span><span class="sxs-lookup"><span data-stu-id="ee6dd-175">200</span></span>|
|<span data-ttu-id="ee6dd-176">可预览搜索结果的 SharePoint 和 OneDrive for Business 网站的最大数量。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-176">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="ee6dd-177">如果包含与搜索查询匹配的项目的网站超过 200 个，则只有结果最多的前 200 个网站可供预览。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-177">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>|<span data-ttu-id="ee6dd-178">200</span><span class="sxs-lookup"><span data-stu-id="ee6dd-178">200</span></span>|
|<span data-ttu-id="ee6dd-179">预览页上显示用于搜索的公用文件夹邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-179">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span> |<span data-ttu-id="ee6dd-180">100</span><span class="sxs-lookup"><span data-stu-id="ee6dd-180">100</span></span>|
|<span data-ttu-id="ee6dd-181">在预览页上显示用于搜索的所有公用文件夹邮箱项中发现的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-181">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span> |<span data-ttu-id="ee6dd-182">200</span><span class="sxs-lookup"><span data-stu-id="ee6dd-182">200</span></span>|
|<span data-ttu-id="ee6dd-183">可预览搜索结果的公用文件夹邮箱的最大数量。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-183">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="ee6dd-184">如果超过 500 个公用文件夹邮箱包含与搜索查询匹配的项目，则只有结果最多的前 500 个邮箱可供预览。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-184">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="ee6dd-185">500</span><span class="sxs-lookup"><span data-stu-id="ee6dd-185">500</span></span>|
|||

## <a name="search-times"></a><span data-ttu-id="ee6dd-186">搜索时间</span><span class="sxs-lookup"><span data-stu-id="ee6dd-186">Search times</span></span>

<span data-ttu-id="ee6dd-187">Microsoft 收集所有组织运行的搜索的性能信息。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-187">Microsoft collects performance information for searches run by all organizations.</span></span> <span data-ttu-id="ee6dd-188">尽管搜索查询的复杂性可能会影响搜索项，但是影响搜索所需时长的最大因素仍然是搜索的邮箱数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-188">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="ee6dd-189">尽管 Microsoft 不提供搜索时间服务级别协议，但下表根据搜索中包含的邮箱数列出了集合搜索的平均搜索时间。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-189">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for collection searches based on the number of mailboxes included in the search.</span></span>
  
  |<span data-ttu-id="ee6dd-190">**邮箱数**</span><span class="sxs-lookup"><span data-stu-id="ee6dd-190">**Number of mailboxes**</span></span>|<span data-ttu-id="ee6dd-191">**平均搜索时间**</span><span class="sxs-lookup"><span data-stu-id="ee6dd-191">**Average search time**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="ee6dd-192">100</span><span class="sxs-lookup"><span data-stu-id="ee6dd-192">100</span></span>  <br/> |<span data-ttu-id="ee6dd-193">30 秒</span><span class="sxs-lookup"><span data-stu-id="ee6dd-193">30 seconds</span></span>  <br/> |
  |<span data-ttu-id="ee6dd-194">1,000</span><span class="sxs-lookup"><span data-stu-id="ee6dd-194">1,000</span></span>  <br/> |<span data-ttu-id="ee6dd-195">45 秒</span><span class="sxs-lookup"><span data-stu-id="ee6dd-195">45 seconds</span></span>  <br/> |
  |<span data-ttu-id="ee6dd-196">10,000</span><span class="sxs-lookup"><span data-stu-id="ee6dd-196">10,000</span></span>  <br/> |<span data-ttu-id="ee6dd-197">4 分钟</span><span class="sxs-lookup"><span data-stu-id="ee6dd-197">4 minutes</span></span>  <br/> |
  |<span data-ttu-id="ee6dd-198">25,000</span><span class="sxs-lookup"><span data-stu-id="ee6dd-198">25,000</span></span>  <br/> |<span data-ttu-id="ee6dd-199">10 分钟</span><span class="sxs-lookup"><span data-stu-id="ee6dd-199">10 minutes</span></span>  <br/> |
  |<span data-ttu-id="ee6dd-200">50,000</span><span class="sxs-lookup"><span data-stu-id="ee6dd-200">50,000</span></span>  <br/> |<span data-ttu-id="ee6dd-201">20 分钟</span><span class="sxs-lookup"><span data-stu-id="ee6dd-201">20 minutes</span></span>  <br/> |
  |<span data-ttu-id="ee6dd-202">100,000</span><span class="sxs-lookup"><span data-stu-id="ee6dd-202">100,000</span></span>  <br/> |<span data-ttu-id="ee6dd-203">25 分钟</span><span class="sxs-lookup"><span data-stu-id="ee6dd-203">25 minutes</span></span>  <br/> |
  |||

## <a name="viewer-limits"></a><span data-ttu-id="ee6dd-204">查看器限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-204">Viewer limits</span></span>

| <span data-ttu-id="ee6dd-205">限制说明</span><span class="sxs-lookup"><span data-stu-id="ee6dd-205">Description of limit</span></span> | <span data-ttu-id="ee6dd-206">限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-206">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ee6dd-207">可在本机查看器中查看的 Excel 文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-207">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="ee6dd-208">4 MB</span><span class="sxs-lookup"><span data-stu-id="ee6dd-208">4 MB</span></span>  <br/> |
|||

## <a name="export-limits"></a><span data-ttu-id="ee6dd-209">导出限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-209">Export limits</span></span>

| <span data-ttu-id="ee6dd-210">限制说明</span><span class="sxs-lookup"><span data-stu-id="ee6dd-210">Description of limit</span></span> | <span data-ttu-id="ee6dd-211">限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-211">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ee6dd-212">单个导出的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-212">Maximum size of a single export.</span></span>|<span data-ttu-id="ee6dd-213">300 万个文档或 100 GB（以较小者为准）</span><span class="sxs-lookup"><span data-stu-id="ee6dd-213">3 million documents or 100 GB, whichever is smaller</span></span>|
|<span data-ttu-id="ee6dd-214">一天中的最大数据量。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-214">Maximum amount of data in a single day.</span></span> | <span data-ttu-id="ee6dd-215">2 TB</span><span class="sxs-lookup"><span data-stu-id="ee6dd-215">2 TB</span></span> |
|<span data-ttu-id="ee6dd-216">组织中的最大并发导出数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-216">Maximum concurrent exports in your organization.</span></span> | <span data-ttu-id="ee6dd-217">10 <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="ee6dd-217">10 <sup>4</sup></span></span> |
|<span data-ttu-id="ee6dd-218">每个用户的最大并发导出数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-218">Maximum concurrent exports per user.</span></span> | <span data-ttu-id="ee6dd-219">3 </span><span class="sxs-lookup"><span data-stu-id="ee6dd-219">3</span></span> |
|<span data-ttu-id="ee6dd-220">单个 PST 文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-220">Maximum size of a single PST file.</span></span> | <span data-ttu-id="ee6dd-221">10 GB</span><span class="sxs-lookup"><span data-stu-id="ee6dd-221">10 GB</span></span> |
|<span data-ttu-id="ee6dd-222">每个审阅集的最大并发导出数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-222">Maximum concurrent exports per review set.</span></span> | <span data-ttu-id="ee6dd-223">1 </span><span class="sxs-lookup"><span data-stu-id="ee6dd-223">1</span></span> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="ee6dd-224">查看集下载限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-224">Review set download limits</span></span>

| <span data-ttu-id="ee6dd-225">限制说明</span><span class="sxs-lookup"><span data-stu-id="ee6dd-225">Description of limit</span></span> | <span data-ttu-id="ee6dd-226">限制</span><span class="sxs-lookup"><span data-stu-id="ee6dd-226">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="ee6dd-227">总文件大小或从审阅集下载的最大文档数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-227">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="ee6dd-228">3 MB 或 50 个文档 <sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="ee6dd-228">3 MB or 50 documents <sup>5</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="ee6dd-229"><sup>1</sup> 超过单个文件限制的任何项目都将显示为处理错误。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-229"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span>
>
> <span data-ttu-id="ee6dd-230"><sup>2</sup> 在搜索 SharePoint 和 OneDrive for Business 位置时，要搜索的网站的 URL 中的字符将计入此限制。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-230"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span>
>
> <span data-ttu-id="ee6dd-231"><sup>3</sup> 对于非短语查询 (不使用双引号的关键字值，) 特殊前缀索引。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-231"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="ee6dd-232">这将告诉我们一个单词在文档中出现，而不是出现在文档中。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-232">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="ee6dd-233">若要使用双引号 (关键字值执行短语查询) ，我们需要比较短语中单词在文档中的位置。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-233">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="ee6dd-234">这意味着不能将前缀索引用于短语查询。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-234">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="ee6dd-235">在这种情况下，我们使用前缀扩展到的所有可能的单词在内部扩展查询;例如 **，time \* *_ 可以展开到 _*"time OR timer OR times OR timex OR timeboxed OR ..."。**</span><span class="sxs-lookup"><span data-stu-id="ee6dd-235">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\**_ can expand to  _*"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="ee6dd-236">限制为 10，000 是单词可以扩展到的最大变体数，而不是与查询匹配的文档数。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-236">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="ee6dd-237">非短语搜索词没有上限。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-237">There is no upper limit for non-phrase terms.</span></span>
>
> <span data-ttu-id="ee6dd-238"><sup>4</sup> 此限制在所有电子数据展示工具之间共享。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-238"><sup>4</sup> This limit is shared across all eDiscovery tools.</span></span> <span data-ttu-id="ee6dd-239">这意味着将针对此限制应用内容搜索、核心电子数据展示和高级电子数据展示中的并发导出。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-239">This means that concurrent exports in Content search, Core eDiscovery, and Advanced eDiscovery are applied against this limit.</span></span>
>
> <span data-ttu-id="ee6dd-240"><sup>5</sup> 此限制适用于从审阅集下载所选文档。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-240"><sup>5</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="ee6dd-241">它不适用于从审阅集导出文档。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-241">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="ee6dd-242">有关下载和导出文档的信息，请参阅"在高级电子数据展示[中导出案例数据"。](exporting-data-ediscover20.md)</span><span class="sxs-lookup"><span data-stu-id="ee6dd-242">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span>
>
> <span data-ttu-id="ee6dd-243">每个组织每天<sup>6</sup>个索引限制。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-243"><sup>6</sup> Indexing limits per organization per day.</span></span> <span data-ttu-id="ee6dd-244">作为一种解决方法，可以在"数据源"选项卡上选择多个保管人，然后单击"更新索引"以避免为每个保管人创建单独的索引作业。</span><span class="sxs-lookup"><span data-stu-id="ee6dd-244">As a workaround, you can select multiple custodians on the **Data sources** tab in a case and then click **Update index** to avoid creating a separate index job for each custodian.</span></span> 
