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
description: 了解对 Microsoft 365 中解决方案生效的大小写限制、索引Advanced eDiscovery和搜索Microsoft 365。
ms.openlocfilehash: 335e40c6918fc33acc12082546b98f28c319c814
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244572"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="e6fc8-103">高级电子数据展示中的限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="e6fc8-104">本文介绍 Microsoft 365 中 Advanced eDiscovery 解决方案中的Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="e6fc8-105">案例和审阅集限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-105">Case and review set limits</span></span>

<span data-ttu-id="e6fc8-106">下表列出了针对事例和审阅集的限制，Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

| <span data-ttu-id="e6fc8-107">限制说明</span><span class="sxs-lookup"><span data-stu-id="e6fc8-107">Description of limit</span></span> | <span data-ttu-id="e6fc8-108">限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-108">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="e6fc8-109">可以添加到案例的文档总数， (审阅集的) 。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="e6fc8-110">3 百万</span><span class="sxs-lookup"><span data-stu-id="e6fc8-110">3 million</span></span> <br/> |
|<span data-ttu-id="e6fc8-111">每个负载集的总文件大小。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-111">Total file size per load set.</span></span> <span data-ttu-id="e6fc8-112">这包括将非Office 365加载到审阅集。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="e6fc8-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="e6fc8-113">300 GB</span></span> <br/> |
|<span data-ttu-id="e6fc8-114">每天加载到组织的所有审阅集的数据总量。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="e6fc8-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="e6fc8-115">2 TB</span></span> <br/> |
|<span data-ttu-id="e6fc8-116">每个案例的最大负载集数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-116">Maximum number of load sets per case.</span></span>  <br/> |<span data-ttu-id="e6fc8-117">200</span><span class="sxs-lookup"><span data-stu-id="e6fc8-117">200</span></span> <br/> |
|<span data-ttu-id="e6fc8-118">每个案例的最大审阅集数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="e6fc8-119">20</span><span class="sxs-lookup"><span data-stu-id="e6fc8-119">20</span></span> <br/> |
|<span data-ttu-id="e6fc8-120">每个案例的最大标记组数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-120">Maximum number of tag groups per case.</span></span>  <br/> |<span data-ttu-id="e6fc8-121">1000</span><span class="sxs-lookup"><span data-stu-id="e6fc8-121">1000</span></span> <br/> |
|<span data-ttu-id="e6fc8-122">每个案例的最大标记数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-122">Maximum number of tags per case.</span></span>  <br/> |<span data-ttu-id="e6fc8-123">1000</span><span class="sxs-lookup"><span data-stu-id="e6fc8-123">1000</span></span> <br/> |
|<span data-ttu-id="e6fc8-124">将内容添加到审阅集的组织中的最大并发作业数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-124">Maximum concurrent jobs in your organization to add content to a review set.</span></span> <span data-ttu-id="e6fc8-125">这些作业名为 **"将数据添加到审阅集"，** 并显示在案例的" **作业"选项卡** 上。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-125">These jobs are named **Adding data to a review set** and are displayed on the **Jobs** tab in a case.</span></span>| <span data-ttu-id="e6fc8-126">10 <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="e6fc8-126">10 <sup>4</sup></span></span> |
|<span data-ttu-id="e6fc8-127">每个用户向审阅集添加内容的最大并发作业数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-127">Maximum concurrent jobs to add content to a review set per user.</span></span> <span data-ttu-id="e6fc8-128">这些作业名为 **"将数据添加到审阅集"，** 并显示在案例的" **作业"选项卡** 上。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-128">These jobs are named **Adding data to a review set** and are displayed on the **Jobs** tab in a case.</span></span> | <span data-ttu-id="e6fc8-129">3</span><span class="sxs-lookup"><span data-stu-id="e6fc8-129">3</span></span> |
|||

## <a name="hold-limits"></a><span data-ttu-id="e6fc8-130">保留限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-130">Hold limits</span></span>

<span data-ttu-id="e6fc8-131">下表列出了与案例关联的保留Advanced eDiscovery限制。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-131">The following table lists the limits for holds associated with an Advanced eDiscovery case.</span></span>

| <span data-ttu-id="e6fc8-132">限制说明</span><span class="sxs-lookup"><span data-stu-id="e6fc8-132">Description of limit</span></span> | <span data-ttu-id="e6fc8-133">限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-133">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="e6fc8-134">单个案例保留中的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-134">Maximum number of mailboxes in a single case hold.</span></span> <span data-ttu-id="e6fc8-135">此限制包括用户邮箱总数，以及与组、组Microsoft 365组、Microsoft Teams组Yammer邮箱。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-135">This limit includes the combined total of user mailboxes, and the mailboxes associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span> <br/> |<span data-ttu-id="e6fc8-136">1,000</span><span class="sxs-lookup"><span data-stu-id="e6fc8-136">1,000</span></span>  <br/> |
|<span data-ttu-id="e6fc8-137">单个案例保留中的最大网站数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-137">Maximum number of sites in a single case hold.</span></span> <span data-ttu-id="e6fc8-138">此限制包括与 OneDrive for Business 组、SharePoint Microsoft 365 组、Microsoft Teams 组Microsoft Teams关联的网站Yammer总数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-138">This limit includes the combined total of OneDrive for Business sites, SharePoint sites, and the sites associated with Microsoft 365 Groups, Microsoft Teams, and Yammer Groups.</span></span>  <br/> |<span data-ttu-id="e6fc8-139">100</span><span class="sxs-lookup"><span data-stu-id="e6fc8-139">100</span></span>  <br/> |

## <a name="indexing-limits"></a><span data-ttu-id="e6fc8-140">索引限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-140">Indexing limits</span></span>

<span data-ttu-id="e6fc8-141">下表列出了网站中的索引Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-141">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

| <span data-ttu-id="e6fc8-142">限制说明</span><span class="sxs-lookup"><span data-stu-id="e6fc8-142">Description of limit</span></span> | <span data-ttu-id="e6fc8-143">限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-143">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="e6fc8-144">从单个文件提取的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-144">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="e6fc8-145">1000 万<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e6fc8-145">10 million<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="e6fc8-146">单个文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-146">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="e6fc8-147">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e6fc8-147">100 MB<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="e6fc8-148">文档中嵌入项目的最大深度。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-148">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="e6fc8-149">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e6fc8-149">25<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="e6fc8-150">由光学字符识别处理的文件的最大大小 (OCR) 。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-150">Maximum size of files processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="e6fc8-151">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e6fc8-151">24 MB<sup>1</sup></span></span> <br/> 
|<span data-ttu-id="e6fc8-152">每个组织每天的最大索引作业数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-152">Maximum number of indexing jobs per organization per day.</span></span> <br/> |<span data-ttu-id="e6fc8-153">10<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="e6fc8-153">10<sup>6</sup></span></span> <br/>|  
|||

## <a name="search-limits"></a><span data-ttu-id="e6fc8-154">搜索限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-154">Search limits</span></span>

<span data-ttu-id="e6fc8-155">本节中所述的限制与使用"搜索"选项卡上的搜索工具收集案件集数据相关。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-155">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="e6fc8-156">有关详细信息，请参阅 Collect [data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-156">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

| <span data-ttu-id="e6fc8-157">限制说明</span><span class="sxs-lookup"><span data-stu-id="e6fc8-157">Description of limit</span></span> | <span data-ttu-id="e6fc8-158">限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-158">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="e6fc8-159">可以在单个搜索中搜索的最大邮箱或网站数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-159">Maximum number of mailboxes or sites that can be searched in a single search.</span></span> |<span data-ttu-id="e6fc8-160">无限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-160">No limit</span></span>|
|<span data-ttu-id="e6fc8-161">可以同时运行的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-161">Maximum number of searches that can run at the same time.</span></span> |<span data-ttu-id="e6fc8-162">无限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-162">No limit</span></span> |
|<span data-ttu-id="e6fc8-163">单个用户可以同时启动的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-163">Maximum number of searches that a single user can start at the same time.</span></span> |<span data-ttu-id="e6fc8-164">10  </span><span class="sxs-lookup"><span data-stu-id="e6fc8-164">10</span></span> | 
|<span data-ttu-id="e6fc8-165">搜索查询记录的最大字符数 (运算符和条件) 。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-165">Maximum number of characters for a search query (including operators and conditions).</span></span> |<span data-ttu-id="e6fc8-166">10，000 &nbsp; <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e6fc8-166">10,000 &nbsp;<sup>2</sup></span></span>|
|<span data-ttu-id="e6fc8-167">网站和网站搜索查询的最大字符数SharePoint OneDrive for Business包括 (运算符和条件) 。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-167">Maximum number of characters for a search query for SharePoint and OneDrive for Business sites (including operators and conditions).</span></span> |<span data-ttu-id="e6fc8-168">10,000</span><span class="sxs-lookup"><span data-stu-id="e6fc8-168">10,000</span></span><br><span data-ttu-id="e6fc8-169">4，000（带通配符 &nbsp; <sup>2）</sup></span><span class="sxs-lookup"><span data-stu-id="e6fc8-169">4,000 with Wildcards&nbsp;<sup>2</sup></span></span>|
|<span data-ttu-id="e6fc8-170">前缀通配符的最小 alpha 字符数;例如，一 **\* *个 _* 或 \* _ set**。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-170">Minimum number of alpha characters for prefix wildcards; for example, \**one\**_ or _\* set\*\*\*.</span></span>|<span data-ttu-id="e6fc8-171">3</span><span class="sxs-lookup"><span data-stu-id="e6fc8-171">3</span></span> |  
|<span data-ttu-id="e6fc8-172">使用前缀通配符搜索精确短语时，或者使用前缀通配符和 **NEAR** 布尔运算符时返回的最大变量数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-172">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span> |<span data-ttu-id="e6fc8-173">10，000 &nbsp; <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="e6fc8-173">10,000&nbsp;<sup>3</sup></span></span>|
|<span data-ttu-id="e6fc8-174">在搜索的预览页面上显示的每个用户邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-174">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="e6fc8-175">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-175">The newest items are displayed.</span></span> |<span data-ttu-id="e6fc8-176">100</span><span class="sxs-lookup"><span data-stu-id="e6fc8-176">100</span></span>|
|<span data-ttu-id="e6fc8-177">预览页面上显示用于搜索的所有邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-177">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>|<span data-ttu-id="e6fc8-178">1,000</span><span class="sxs-lookup"><span data-stu-id="e6fc8-178">1,000</span></span>|
|<span data-ttu-id="e6fc8-179">可预览搜索结果的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-179">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="e6fc8-180">如果超过 1000 个邮箱包含与搜索查询匹配的项目，则仅前 1，000 个邮箱具有最多结果可供预览。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-180">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="e6fc8-181">1,000</span><span class="sxs-lookup"><span data-stu-id="e6fc8-181">1,000</span></span>|
|<span data-ttu-id="e6fc8-182">预览页面上显示的搜索SharePoint和OneDrive for Business网站的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-182">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="e6fc8-183">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-183">The newest items are displayed.</span></span> |<span data-ttu-id="e6fc8-184">200</span><span class="sxs-lookup"><span data-stu-id="e6fc8-184">200</span></span>|
|<span data-ttu-id="e6fc8-185">可预览SharePoint搜索结果OneDrive for Business网站的最大网站数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-185">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="e6fc8-186">如果包含与搜索查询匹配的项目的网站超过 200 个，则仅具有最多结果的前 200 个网站可供预览。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-186">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>|<span data-ttu-id="e6fc8-187">200</span><span class="sxs-lookup"><span data-stu-id="e6fc8-187">200</span></span>|
|<span data-ttu-id="e6fc8-188">在预览页面上显示用于搜索的公用文件夹邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-188">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span> |<span data-ttu-id="e6fc8-189">100</span><span class="sxs-lookup"><span data-stu-id="e6fc8-189">100</span></span>|
|<span data-ttu-id="e6fc8-190">在预览页面上显示用于搜索的所有公用文件夹邮箱项中查找的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-190">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span> |<span data-ttu-id="e6fc8-191">200</span><span class="sxs-lookup"><span data-stu-id="e6fc8-191">200</span></span>|
|<span data-ttu-id="e6fc8-192">可预览搜索结果的公用文件夹邮箱的最大数量。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-192">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="e6fc8-193">如果超过 500 个公用文件夹邮箱包含与搜索查询匹配的项目，则只有结果最多的前 500 个邮箱可供预览。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-193">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>|<span data-ttu-id="e6fc8-194">500</span><span class="sxs-lookup"><span data-stu-id="e6fc8-194">500</span></span>|
|||

## <a name="search-times"></a><span data-ttu-id="e6fc8-195">搜索时间</span><span class="sxs-lookup"><span data-stu-id="e6fc8-195">Search times</span></span>

<span data-ttu-id="e6fc8-196">Microsoft 收集所有组织运行的搜索的性能信息。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-196">Microsoft collects performance information for searches run by all organizations.</span></span> <span data-ttu-id="e6fc8-197">尽管搜索查询的复杂性可能会影响搜索项，但是影响搜索所需时长的最大因素仍然是搜索的邮箱数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-197">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="e6fc8-198">尽管 Microsoft 不提供用于搜索次数的服务级别协议，但下表根据搜索中包含的邮箱数列出了集合搜索的平均搜索时间。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-198">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for collection searches based on the number of mailboxes included in the search.</span></span>
  
  | <span data-ttu-id="e6fc8-199">邮箱数</span><span class="sxs-lookup"><span data-stu-id="e6fc8-199">Number of mailboxes</span></span> | <span data-ttu-id="e6fc8-200">平均搜索时间</span><span class="sxs-lookup"><span data-stu-id="e6fc8-200">Average search time</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="e6fc8-201">100</span><span class="sxs-lookup"><span data-stu-id="e6fc8-201">100</span></span>  <br/> |<span data-ttu-id="e6fc8-202">30 秒</span><span class="sxs-lookup"><span data-stu-id="e6fc8-202">30 seconds</span></span>  <br/> |
  |<span data-ttu-id="e6fc8-203">1,000</span><span class="sxs-lookup"><span data-stu-id="e6fc8-203">1,000</span></span>  <br/> |<span data-ttu-id="e6fc8-204">45 秒</span><span class="sxs-lookup"><span data-stu-id="e6fc8-204">45 seconds</span></span>  <br/> |
  |<span data-ttu-id="e6fc8-205">10,000</span><span class="sxs-lookup"><span data-stu-id="e6fc8-205">10,000</span></span>  <br/> |<span data-ttu-id="e6fc8-206">4 分钟</span><span class="sxs-lookup"><span data-stu-id="e6fc8-206">4 minutes</span></span>  <br/> |
  |<span data-ttu-id="e6fc8-207">25,000</span><span class="sxs-lookup"><span data-stu-id="e6fc8-207">25,000</span></span>  <br/> |<span data-ttu-id="e6fc8-208">10 分钟</span><span class="sxs-lookup"><span data-stu-id="e6fc8-208">10 minutes</span></span>  <br/> |
  |<span data-ttu-id="e6fc8-209">50,000</span><span class="sxs-lookup"><span data-stu-id="e6fc8-209">50,000</span></span>  <br/> |<span data-ttu-id="e6fc8-210">20 分钟</span><span class="sxs-lookup"><span data-stu-id="e6fc8-210">20 minutes</span></span>  <br/> |
  |<span data-ttu-id="e6fc8-211">100,000</span><span class="sxs-lookup"><span data-stu-id="e6fc8-211">100,000</span></span>  <br/> |<span data-ttu-id="e6fc8-212">25 分钟</span><span class="sxs-lookup"><span data-stu-id="e6fc8-212">25 minutes</span></span>  <br/> |
  |||

## <a name="viewer-limits"></a><span data-ttu-id="e6fc8-213">查看器限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-213">Viewer limits</span></span>

| <span data-ttu-id="e6fc8-214">限制说明</span><span class="sxs-lookup"><span data-stu-id="e6fc8-214">Description of limit</span></span> | <span data-ttu-id="e6fc8-215">限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-215">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="e6fc8-216">可以在本机Excel查看的最大文件大小。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-216">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="e6fc8-217">4 MB</span><span class="sxs-lookup"><span data-stu-id="e6fc8-217">4 MB</span></span>  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a><span data-ttu-id="e6fc8-218">导出限制 - 最终导出审阅集</span><span class="sxs-lookup"><span data-stu-id="e6fc8-218">Export limits - Final export out of Review Set</span></span>

<span data-ttu-id="e6fc8-219">本节中所述的限制与将文档从审阅集导出有关。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-219">The limits described in this section are related to exporting documents out of a review set.</span></span>

| <span data-ttu-id="e6fc8-220">限制说明</span><span class="sxs-lookup"><span data-stu-id="e6fc8-220">Description of limit</span></span> | <span data-ttu-id="e6fc8-221">限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-221">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="e6fc8-222">单个导出的最大大小。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-222">Maximum size of a single export.</span></span>|<span data-ttu-id="e6fc8-223">500 万个文档或 500 GB，以较小者为准</span><span class="sxs-lookup"><span data-stu-id="e6fc8-223">5 million documents or 500 GB, whichever is smaller</span></span>|
|<span data-ttu-id="e6fc8-224">每个审阅集的最大并发导出数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-224">Maximum concurrent exports per review set.</span></span> | <span data-ttu-id="e6fc8-225">1</span><span class="sxs-lookup"><span data-stu-id="e6fc8-225">1</span></span> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="e6fc8-226">查看集下载限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-226">Review set download limits</span></span>

| <span data-ttu-id="e6fc8-227">限制说明</span><span class="sxs-lookup"><span data-stu-id="e6fc8-227">Description of limit</span></span> | <span data-ttu-id="e6fc8-228">限制</span><span class="sxs-lookup"><span data-stu-id="e6fc8-228">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="e6fc8-229">总文件大小或从审阅集下载的最大文档数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-229">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="e6fc8-230">3 MB 或 50 个文档 <sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="e6fc8-230">3 MB or 50 documents <sup>5</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="e6fc8-231"><sup>1</sup> 任何超过单个文件限制的项目都将显示为处理错误。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-231"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span>
>
> <span data-ttu-id="e6fc8-232"><sup>2</sup>在搜索SharePoint和OneDrive for Business位置时，所搜索网站的 URL 中的字符数将计入此限制。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-232"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span> <span data-ttu-id="e6fc8-233">字符总数包含：</span><span class="sxs-lookup"><span data-stu-id="e6fc8-233">The total number of characters consists of:</span></span><br>
> - <span data-ttu-id="e6fc8-234">"用户"和"筛选器"字段中的所有字符。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-234">All characters in both the Users and Filters fields.</span></span>
> - <span data-ttu-id="e6fc8-235">应用于用户的所有搜索权限筛选器。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-235">All search permissions filters that apply to the user.</span></span>
> - <span data-ttu-id="e6fc8-236">搜索中任何位置属性中的字符;这包括 ExchangeLocation、PublicFolderLocation、SharPointLocation、ExchangeLocationExclusion、PublicFolderLocationExclusion、SharePointLocationExclusion、OneDriveLocationExclusion。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-236">The characters from any location properties in the search; this includes ExchangeLocation,PublicFolderLocation,SharPointLocation,ExchangeLocationExclusion,PublicFolderLocationExclusion,SharePointLocationExclusion, OneDriveLocationExclusion.</span></span>
>   <span data-ttu-id="e6fc8-237">例如，包括搜索SharePoint网站和 OneDrive 帐户将计为六个字符，因为 SharePointLocation 和 OneDriveLocation 字段将显示单词"ALL"。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-237">For example, including all SharePoint sites and OneDrive accounts in the search will count as six characters, as the word "ALL" will appear for both the SharePointLocation and OneDriveLocation field.</span></span>
>
> <span data-ttu-id="e6fc8-238"><sup>3</sup> 对于非短语 (使用不使用双引号的关键字) 我们使用了特殊的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-238"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="e6fc8-239">这将告诉我们一个单词在文档中出现，而不是在文档中出现位置。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-239">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="e6fc8-240">若要对包含双引号 (关键字值执行短语查询) ，我们需要比较短语中单词在文档中的位置。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-240">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="e6fc8-241">这意味着不能将前缀索引用于短语查询。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-241">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="e6fc8-242">在这种情况下，我们使用前缀扩展到的所有可能的单词在内部扩展查询;例如 **，time \* *_ 可以展开到 _*"time OR timer OR times OR timex OR timeboxed OR ..."。**</span><span class="sxs-lookup"><span data-stu-id="e6fc8-242">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\**_ can expand to  _*"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="e6fc8-243">限制 10，000 是单词可以扩展到的最大变体数，而不是与查询匹配的文档数。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-243">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="e6fc8-244">非短语搜索词没有上限。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-244">There is no upper limit for non-phrase terms.</span></span>
>
> <span data-ttu-id="e6fc8-245"><sup>4</sup> 此限制与其他电子数据展示工具中的内容导出共享。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-245"><sup>4</sup> This limit is shared with exporting content in other eDiscovery tools.</span></span> <span data-ttu-id="e6fc8-246">这意味着，内容搜索和核心电子数据展示中的并发导出 (以及将内容添加到审核集Advanced eDiscovery) 都针对此限制应用。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-246">This means that concurrent exports in Content search and Core eDiscovery (and adding content to review sets in Advanced eDiscovery) are all applied against this limit.</span></span>
>
> <span data-ttu-id="e6fc8-247"><sup>5</sup> 此限制适用于从审阅集下载所选文档。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-247"><sup>5</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="e6fc8-248">它不适用于从审阅集导出文档。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-248">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="e6fc8-249">有关下载和导出文档的信息[，请参阅导出](exporting-data-ediscover20.md)文档中的Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-249">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span>
>
> <span data-ttu-id="e6fc8-250"><sup>6</sup> 每个组织每天的索引编制限制。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-250"><sup>6</sup> Indexing limits per organization per day.</span></span> <span data-ttu-id="e6fc8-251">作为一种解决方法，您可以在"数据源"选项卡上选择一个案例的多个保管人，然后单击"更新索引"以避免为每个保管人创建单独的索引作业。</span><span class="sxs-lookup"><span data-stu-id="e6fc8-251">As a workaround, you can select multiple custodians on the **Data sources** tab in a case and then click **Update index** to avoid creating a separate index job for each custodian.</span></span> 
