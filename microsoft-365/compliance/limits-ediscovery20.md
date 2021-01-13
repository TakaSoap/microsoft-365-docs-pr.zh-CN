---
title: 高级电子数据展示限制
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解适用于 Microsoft 365 高级电子数据展示解决方案的情况限制、索引限制和搜索限制。
ms.openlocfilehash: 8238a86df2d4e6b487571a3c0f9a380d90607729
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799679"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="bec2f-103">高级电子数据展示中的限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="bec2f-104">本文介绍了 Microsoft 365 中高级电子数据展示解决方案中的限制。</span><span class="sxs-lookup"><span data-stu-id="bec2f-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="bec2f-105">案例和审阅集限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-105">Case and review set limits</span></span>

<span data-ttu-id="bec2f-106">下表列出了高级电子数据展示中事例和审阅集的限制。</span><span class="sxs-lookup"><span data-stu-id="bec2f-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

| <span data-ttu-id="bec2f-107">限制说明</span><span class="sxs-lookup"><span data-stu-id="bec2f-107">Description of limit</span></span> | <span data-ttu-id="bec2f-108">限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-108">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="bec2f-109">可添加到案例审阅记录的文档总数 (审阅集的所有审阅) 。</span><span class="sxs-lookup"><span data-stu-id="bec2f-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="bec2f-110">3 百万</span><span class="sxs-lookup"><span data-stu-id="bec2f-110">3 million</span></span> <br/> |
|<span data-ttu-id="bec2f-111">每个负载集的总文件大小。</span><span class="sxs-lookup"><span data-stu-id="bec2f-111">Total file size per load set.</span></span> <span data-ttu-id="bec2f-112">这包括将非 Office 365 加载到审阅集。</span><span class="sxs-lookup"><span data-stu-id="bec2f-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="bec2f-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="bec2f-113">300 GB</span></span> <br/> |
|<span data-ttu-id="bec2f-114">每天加载到组织的所有审阅集的数据总量。</span><span class="sxs-lookup"><span data-stu-id="bec2f-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="bec2f-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="bec2f-115">2 TB</span></span> <br/> |
|<span data-ttu-id="bec2f-116">每个情况的最大负载集数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="bec2f-117">200</span><span class="sxs-lookup"><span data-stu-id="bec2f-117">200</span></span> <br/> |
|<span data-ttu-id="bec2f-118">每个案例的最大审阅集数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="bec2f-119">20</span><span class="sxs-lookup"><span data-stu-id="bec2f-119">20</span></span> <br/> |
|<span data-ttu-id="bec2f-120">每个案例的最大标记组数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-120">Maximum number of tag groups per case.</span></span>  <br/> |<span data-ttu-id="bec2f-121">1000</span><span class="sxs-lookup"><span data-stu-id="bec2f-121">1000</span></span> <br/> |
|<span data-ttu-id="bec2f-122">每个案例的最大标记数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-122">Maximum number of tags per case.</span></span>  <br/> |<span data-ttu-id="bec2f-123">1000</span><span class="sxs-lookup"><span data-stu-id="bec2f-123">1000</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="bec2f-124">索引限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-124">Indexing limits</span></span>

<span data-ttu-id="bec2f-125">下表列出了高级电子数据展示中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="bec2f-125">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

| <span data-ttu-id="bec2f-126">限制说明</span><span class="sxs-lookup"><span data-stu-id="bec2f-126">Description of limit</span></span> | <span data-ttu-id="bec2f-127">限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-127">Limit</span></span> |
  |:-----|:-----|
  |<span data-ttu-id="bec2f-128">从单个文件中提取的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-128">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="bec2f-129">1，000<sup>万 1</sup></span><span class="sxs-lookup"><span data-stu-id="bec2f-129">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="bec2f-130">单个文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="bec2f-130">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="bec2f-131">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bec2f-131">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="bec2f-132">文档中嵌入项目的最大深度。</span><span class="sxs-lookup"><span data-stu-id="bec2f-132">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="bec2f-133">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bec2f-133">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="bec2f-134">由光学字符识别处理的文件的最大 (OCR) 。</span><span class="sxs-lookup"><span data-stu-id="bec2f-134">Maximum size of files processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="bec2f-135">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bec2f-135">24 MB<sup>1</sup></span></span> <br/> 
  |<span data-ttu-id="bec2f-136">每个组织每天的最大索引作业数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-136">Maximum number of indexing jobs per organization per day.</span></span> <br/> |<span data-ttu-id="bec2f-137">10<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="bec2f-137">10<sup>6</sup></span></span> <br/>|  
|||

## <a name="search-limits"></a><span data-ttu-id="bec2f-138">搜索限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-138">Search limits</span></span>

<span data-ttu-id="bec2f-139">本节中所述的限制与使用"搜索"选项卡上的搜索工具收集案例数据相关。</span><span class="sxs-lookup"><span data-stu-id="bec2f-139">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="bec2f-140">有关详细信息，请参阅["收集高级电子数据展示中案例的数据"。](collecting-data-for-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="bec2f-140">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

| <span data-ttu-id="bec2f-141">限制说明</span><span class="sxs-lookup"><span data-stu-id="bec2f-141">Description of limit</span></span> | <span data-ttu-id="bec2f-142">限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-142">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="bec2f-143">可以在单个搜索中搜索的最大邮箱或网站数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-143">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="bec2f-144">无限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-144">No limit</span></span>  <br/> |
|<span data-ttu-id="bec2f-145">可以同时运行的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-145">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="bec2f-146">无限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-146">No limit</span></span>  <br/> | 
|<span data-ttu-id="bec2f-147">单个用户可以同时启动的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-147">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="bec2f-148">10 </span><span class="sxs-lookup"><span data-stu-id="bec2f-148">10</span></span>  <br/> | 
|<span data-ttu-id="bec2f-149">搜索查询查询的最大字符数 (运算符和条件) 。</span><span class="sxs-lookup"><span data-stu-id="bec2f-149">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="bec2f-150">**邮箱**：10，000</span><span class="sxs-lookup"><span data-stu-id="bec2f-150">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="bec2f-151">**网站**：搜索所有网站时为 4，000，搜索最多 20 个网站时为 2，000 <sup>个 2</sup></span><span class="sxs-lookup"><span data-stu-id="bec2f-151">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="bec2f-152">前缀通配符的最小 alpha 字符数;例如， **\* one* _ 或 _*set \*\*_。</span><span class="sxs-lookup"><span data-stu-id="bec2f-152">Minimum number of alpha characters for prefix wildcards; for example, **one\** _ or _*set\*\*_.</span></span> <br/> |<span data-ttu-id="bec2f-153">3 </span><span class="sxs-lookup"><span data-stu-id="bec2f-153">3</span></span>  <br/> |  
|<span data-ttu-id="bec2f-154">使用前缀通配符搜索精确短语时，或者使用前缀通配符和 _ *NEAR*\* 布尔运算符时返回的最大变量数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-154">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the _ *NEAR*\* Boolean operator.</span></span>  <br/> |<span data-ttu-id="bec2f-155">10，000 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="bec2f-155">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="bec2f-156">在预览页上显示用于搜索的每个用户邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-156">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="bec2f-157">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="bec2f-157">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="bec2f-158">100</span><span class="sxs-lookup"><span data-stu-id="bec2f-158">100</span></span>  <br/> |
|<span data-ttu-id="bec2f-159">预览页上显示用于搜索的所有邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-159">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="bec2f-160">1,000</span><span class="sxs-lookup"><span data-stu-id="bec2f-160">1,000</span></span>  <br/> |
|<span data-ttu-id="bec2f-161">可预览搜索结果的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-161">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="bec2f-162">如果包含与搜索查询匹配的项目超过 1000 个邮箱，则只有结果最多的前 1，000 个邮箱可供预览。</span><span class="sxs-lookup"><span data-stu-id="bec2f-162">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="bec2f-163">1,000</span><span class="sxs-lookup"><span data-stu-id="bec2f-163">1,000</span></span>  <br/> |
|<span data-ttu-id="bec2f-164">预览页上显示用于搜索的 SharePoint 和 OneDrive for Business 网站的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-164">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="bec2f-165">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="bec2f-165">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="bec2f-166">200</span><span class="sxs-lookup"><span data-stu-id="bec2f-166">200</span></span>  <br/> |
|<span data-ttu-id="bec2f-167">可预览搜索结果的 SharePoint 和 OneDrive for Business 网站的最大数量。</span><span class="sxs-lookup"><span data-stu-id="bec2f-167">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="bec2f-168">如果包含与搜索查询匹配的项目的网站超过 200 个，则只有结果最多的前 200 个网站可供预览。</span><span class="sxs-lookup"><span data-stu-id="bec2f-168">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="bec2f-169">200</span><span class="sxs-lookup"><span data-stu-id="bec2f-169">200</span></span>  <br/> |
|<span data-ttu-id="bec2f-170">预览页上显示用于搜索的公用文件夹邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-170">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="bec2f-171">100</span><span class="sxs-lookup"><span data-stu-id="bec2f-171">100</span></span>  <br/> |
|<span data-ttu-id="bec2f-172">在预览页上显示用于搜索的所有公用文件夹邮箱项目中发现的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-172">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="bec2f-173">200</span><span class="sxs-lookup"><span data-stu-id="bec2f-173">200</span></span>  <br/> |
|<span data-ttu-id="bec2f-174">可预览搜索结果的公用文件夹邮箱的最大数量。</span><span class="sxs-lookup"><span data-stu-id="bec2f-174">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="bec2f-175">如果超过 500 个公用文件夹邮箱包含与搜索查询匹配的项目，则只有结果最多的前 500 个邮箱可供预览。</span><span class="sxs-lookup"><span data-stu-id="bec2f-175">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="bec2f-176">500</span><span class="sxs-lookup"><span data-stu-id="bec2f-176">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="bec2f-177">查看器限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-177">Viewer limits</span></span>

| <span data-ttu-id="bec2f-178">限制说明</span><span class="sxs-lookup"><span data-stu-id="bec2f-178">Description of limit</span></span> | <span data-ttu-id="bec2f-179">限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-179">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="bec2f-180">可在本机查看器中查看的 Excel 文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="bec2f-180">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="bec2f-181">4 MB</span><span class="sxs-lookup"><span data-stu-id="bec2f-181">4 MB</span></span>  <br/> |
|||

## <a name="export-limits"></a><span data-ttu-id="bec2f-182">导出限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-182">Export limits</span></span>

| <span data-ttu-id="bec2f-183">限制说明</span><span class="sxs-lookup"><span data-stu-id="bec2f-183">Description of limit</span></span> | <span data-ttu-id="bec2f-184">限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-184">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="bec2f-185">单个导出的最大大小。</span><span class="sxs-lookup"><span data-stu-id="bec2f-185">Maximum size of a single export.</span></span>|<span data-ttu-id="bec2f-186">300 万个文档或 100 GB（以较小者为准）</span><span class="sxs-lookup"><span data-stu-id="bec2f-186">3 million documents or 100 GB, whichever is smaller</span></span>|
|<span data-ttu-id="bec2f-187">一天中的最大数据量。</span><span class="sxs-lookup"><span data-stu-id="bec2f-187">Maximum amount of data in a single day.</span></span> | <span data-ttu-id="bec2f-188">2 TB</span><span class="sxs-lookup"><span data-stu-id="bec2f-188">2 TB</span></span> |
|<span data-ttu-id="bec2f-189">组织中的最大并发导出数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-189">Maximum concurrent exports in your organization.</span></span> | <span data-ttu-id="bec2f-190">10 <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="bec2f-190">10 <sup>4</sup></span></span> |
|<span data-ttu-id="bec2f-191">每个用户的最大并发导出数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-191">Maximum concurrent exports per user.</span></span> | <span data-ttu-id="bec2f-192">3 </span><span class="sxs-lookup"><span data-stu-id="bec2f-192">3</span></span> |
|<span data-ttu-id="bec2f-193">单个 PST 文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="bec2f-193">Maximum size of a single PST file.</span></span> | <span data-ttu-id="bec2f-194">10 GB</span><span class="sxs-lookup"><span data-stu-id="bec2f-194">10 GB</span></span> |
|<span data-ttu-id="bec2f-195">每个审阅集的最大并发导出数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-195">Maximum concurrent exports per review set.</span></span> | <span data-ttu-id="bec2f-196">1 </span><span class="sxs-lookup"><span data-stu-id="bec2f-196">1</span></span> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="bec2f-197">查看集下载限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-197">Review set download limits</span></span>

| <span data-ttu-id="bec2f-198">限制说明</span><span class="sxs-lookup"><span data-stu-id="bec2f-198">Description of limit</span></span> | <span data-ttu-id="bec2f-199">限制</span><span class="sxs-lookup"><span data-stu-id="bec2f-199">Limit</span></span> |
|:-----|:-----|
|<span data-ttu-id="bec2f-200">总文件大小或从审阅集下载的最大文档数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-200">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="bec2f-201">3 MB 或 50 个文档 <sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="bec2f-201">3 MB or 50 documents <sup>5</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="bec2f-202"><sup>1</sup> 超过单个文件限制的任何项目都将显示为处理错误。</span><span class="sxs-lookup"><span data-stu-id="bec2f-202"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span>
>
> <span data-ttu-id="bec2f-203"><sup>2</sup> 在搜索 SharePoint 和 OneDrive for Business 位置时，要搜索的网站的 URL 中的字符将计入此限制。</span><span class="sxs-lookup"><span data-stu-id="bec2f-203"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span>
>
> <span data-ttu-id="bec2f-204"><sup>3</sup> 对于非短语查询 (不使用双引号的关键字值，) 特殊前缀索引。</span><span class="sxs-lookup"><span data-stu-id="bec2f-204"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="bec2f-205">这告诉我们一个单词在文档中出现，而不是出现在文档中。</span><span class="sxs-lookup"><span data-stu-id="bec2f-205">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="bec2f-206">若要使用双引号 (关键字值执行短语查询) ，我们需要比较短语中单词在文档中的位置。</span><span class="sxs-lookup"><span data-stu-id="bec2f-206">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="bec2f-207">这意味着不能将前缀索引用于短语查询。</span><span class="sxs-lookup"><span data-stu-id="bec2f-207">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="bec2f-208">在这种情况下，我们使用前缀扩展到的所有可能的单词在内部扩展查询;例如 **，time \* *_ 可以展开到 _*"time OR timer OR times OR timex OR timeboxed OR ..."。**</span><span class="sxs-lookup"><span data-stu-id="bec2f-208">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\**_ can expand to  _*"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="bec2f-209">限制为 10，000 是单词可以扩展到的最大变体数，而不是与查询匹配的文档数。</span><span class="sxs-lookup"><span data-stu-id="bec2f-209">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="bec2f-210">非短语搜索词没有上限。</span><span class="sxs-lookup"><span data-stu-id="bec2f-210">There is no upper limit for non-phrase terms.</span></span>
>
> <span data-ttu-id="bec2f-211"><sup>4</sup> 此限制在所有电子数据展示工具之间共享。</span><span class="sxs-lookup"><span data-stu-id="bec2f-211"><sup>4</sup> This limit is shared across all eDiscovery tools.</span></span> <span data-ttu-id="bec2f-212">这意味着将针对此限制应用内容搜索、核心电子数据展示和高级电子数据展示中的并发导出。</span><span class="sxs-lookup"><span data-stu-id="bec2f-212">This means that concurrent exports in Content search, Core eDiscovery, and Advanced eDiscovery are applied against this limit.</span></span>
>
> <span data-ttu-id="bec2f-213"><sup>5</sup> 此限制适用于从审阅集下载所选文档。</span><span class="sxs-lookup"><span data-stu-id="bec2f-213"><sup>5</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="bec2f-214">它不适用于从审阅集导出文档。</span><span class="sxs-lookup"><span data-stu-id="bec2f-214">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="bec2f-215">有关下载和导出文档的信息，请参阅["在高级电子数据展示中导出案例数据"。](exporting-data-ediscover20.md)</span><span class="sxs-lookup"><span data-stu-id="bec2f-215">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span>
>
> <span data-ttu-id="bec2f-216">每个组织每天<sup>6</sup>个索引限制。</span><span class="sxs-lookup"><span data-stu-id="bec2f-216"><sup>6</sup> Indexing limits per organization per day.</span></span> <span data-ttu-id="bec2f-217">作为解决方法，可以在"数据源"选项卡上选择一个案例的多个保管人，然后单击"更新索引"以避免为每个保管人创建单独的索引作业。</span><span class="sxs-lookup"><span data-stu-id="bec2f-217">As a workaround, you can select multiple custodians on the **Data sources** tab in a case and then click **Update index** to avoid creating a separate index job for each custodian.</span></span> 
