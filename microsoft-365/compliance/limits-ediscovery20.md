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
description: 了解 Microsoft 365 中适用于高级电子数据展示解决方案的案例限制、索引限制和搜索限制。
ms.openlocfilehash: abc93acb5f32ea1fdae607d8e1053adc59ad6cea
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49020959"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="c9f23-103">高级电子数据展示中的限制</span><span class="sxs-lookup"><span data-stu-id="c9f23-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="c9f23-104">本文介绍了 Microsoft 365 中的高级电子数据展示解决方案中的限制。</span><span class="sxs-lookup"><span data-stu-id="c9f23-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="c9f23-105">案例和审阅设置限制</span><span class="sxs-lookup"><span data-stu-id="c9f23-105">Case and review set limits</span></span>

<span data-ttu-id="c9f23-106">下表列出了高级电子数据展示中案例和审阅集的限制。</span><span class="sxs-lookup"><span data-stu-id="c9f23-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

|<span data-ttu-id="c9f23-107">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="c9f23-107">**Description of limit**</span></span>|<span data-ttu-id="c9f23-108">**限制**</span><span class="sxs-lookup"><span data-stu-id="c9f23-108">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9f23-109">对事例) 中所有审阅集可添加到事例中的文档的总数 (。</span><span class="sxs-lookup"><span data-stu-id="c9f23-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="c9f23-110">3 百万</span><span class="sxs-lookup"><span data-stu-id="c9f23-110">3 million</span></span> <br/> |
|<span data-ttu-id="c9f23-111">每个加载集的总文件大小。</span><span class="sxs-lookup"><span data-stu-id="c9f23-111">Total file size per load set.</span></span> <span data-ttu-id="c9f23-112">这包括将非 Office 365 加载到评审集中。</span><span class="sxs-lookup"><span data-stu-id="c9f23-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="c9f23-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="c9f23-113">300 GB</span></span> <br/> |
|<span data-ttu-id="c9f23-114">每天在组织中的所有审阅集中加载的数据总量。</span><span class="sxs-lookup"><span data-stu-id="c9f23-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="c9f23-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="c9f23-115">2 TB</span></span> <br/> |
|<span data-ttu-id="c9f23-116">每个事例的最大加载集数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="c9f23-117">200</span><span class="sxs-lookup"><span data-stu-id="c9f23-117">200</span></span> <br/> |
|<span data-ttu-id="c9f23-118">每个案例的最大审阅集数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="c9f23-119">20</span><span class="sxs-lookup"><span data-stu-id="c9f23-119">20</span></span> <br/> |
|<span data-ttu-id="c9f23-120">每个事例的最大标记组数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-120">Maximum number of tag groups per case.</span></span>  <br/> |<span data-ttu-id="c9f23-121">1000</span><span class="sxs-lookup"><span data-stu-id="c9f23-121">1000</span></span> <br/> |
|<span data-ttu-id="c9f23-122">每个事例的最大标记数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-122">Maximum number of tags per case.</span></span>  <br/> |<span data-ttu-id="c9f23-123">1000</span><span class="sxs-lookup"><span data-stu-id="c9f23-123">1000</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="c9f23-124">索引限制</span><span class="sxs-lookup"><span data-stu-id="c9f23-124">Indexing limits</span></span>

<span data-ttu-id="c9f23-125">下表列出了高级电子数据展示中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="c9f23-125">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="c9f23-126">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="c9f23-126">**Description of limit**</span></span>|<span data-ttu-id="c9f23-127">**限制**</span><span class="sxs-lookup"><span data-stu-id="c9f23-127">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="c9f23-128">从单个文件提取的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-128">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="c9f23-129">10000000<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c9f23-129">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="c9f23-130">单个文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="c9f23-130">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="c9f23-131">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c9f23-131">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="c9f23-132">文档中嵌入项目的最大深度。</span><span class="sxs-lookup"><span data-stu-id="c9f23-132">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="c9f23-133">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c9f23-133">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="c9f23-134">由光学字符识别 (OCR) 处理的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="c9f23-134">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="c9f23-135">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c9f23-135">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="c9f23-136">搜索限制</span><span class="sxs-lookup"><span data-stu-id="c9f23-136">Search limits</span></span>

<span data-ttu-id="c9f23-137">本节中描述的限制与使用 **"搜索" 选项卡** 上的搜索工具收集事例数据相关。</span><span class="sxs-lookup"><span data-stu-id="c9f23-137">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="c9f23-138">有关详细信息，请参阅 [在高级电子数据展示中收集数据的大小写](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="c9f23-138">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="c9f23-139">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="c9f23-139">**Description of limit**</span></span>|<span data-ttu-id="c9f23-140">**限制**</span><span class="sxs-lookup"><span data-stu-id="c9f23-140">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9f23-141">可在单个搜索中搜索的邮箱或网站的最大数量。</span><span class="sxs-lookup"><span data-stu-id="c9f23-141">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="c9f23-142">无限制</span><span class="sxs-lookup"><span data-stu-id="c9f23-142">No limit</span></span>  <br/> |
|<span data-ttu-id="c9f23-143">可以同时运行的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-143">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="c9f23-144">无限制</span><span class="sxs-lookup"><span data-stu-id="c9f23-144">No limit</span></span>  <br/> | 
|<span data-ttu-id="c9f23-145">一个用户可以同时启动的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-145">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="c9f23-146">10  </span><span class="sxs-lookup"><span data-stu-id="c9f23-146">10</span></span>  <br/> | 
|<span data-ttu-id="c9f23-147">搜索查询的最大字符数 (包括运算符和条件) 。</span><span class="sxs-lookup"><span data-stu-id="c9f23-147">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="c9f23-148">**邮箱** ：10000</span><span class="sxs-lookup"><span data-stu-id="c9f23-148">**Mailboxes** : 10,000</span></span><br/><span data-ttu-id="c9f23-149">**网站** ：4000搜索所有网站或2000时搜索20个网站 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c9f23-149">**Sites** : 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="c9f23-150">前缀通配符的最小字母字符数;例如，\* *1 \** _ or _*set \**_ 。</span><span class="sxs-lookup"><span data-stu-id="c9f23-150">Minimum number of alpha characters for prefix wildcards; for example \* *one\** _ or _*set\**_.</span></span> <br/> |<span data-ttu-id="c9f23-151">第三章</span><span class="sxs-lookup"><span data-stu-id="c9f23-151">3</span></span>  <br/> |  
|<span data-ttu-id="c9f23-152">使用前缀通配符搜索精确短语或使用前缀通配符和 _ *NEAR* \* Boolean 运算符时返回的最大变体。</span><span class="sxs-lookup"><span data-stu-id="c9f23-152">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the _ *NEAR* \* Boolean operator.</span></span>  <br/> |<span data-ttu-id="c9f23-153">10000 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="c9f23-153">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="c9f23-154">在搜索的预览页面上显示的每个用户邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-154">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="c9f23-155">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="c9f23-155">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="c9f23-156">100</span><span class="sxs-lookup"><span data-stu-id="c9f23-156">100</span></span>  <br/> |
|<span data-ttu-id="c9f23-157">用于搜索的预览页面上显示的所有邮箱中的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-157">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="c9f23-158">1,000</span><span class="sxs-lookup"><span data-stu-id="c9f23-158">1,000</span></span>  <br/> |
|<span data-ttu-id="c9f23-159">可为搜索结果预览的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-159">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="c9f23-160">如果有超过1000个邮箱包含与搜索查询匹配的项目，则仅可预览具有最多结果的前1000个邮箱。</span><span class="sxs-lookup"><span data-stu-id="c9f23-160">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="c9f23-161">1,000</span><span class="sxs-lookup"><span data-stu-id="c9f23-161">1,000</span></span>  <br/> |
|<span data-ttu-id="c9f23-162">SharePoint 和 OneDrive for business 网站上显示的搜索的预览页面上显示的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-162">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="c9f23-163">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="c9f23-163">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="c9f23-164">200</span><span class="sxs-lookup"><span data-stu-id="c9f23-164">200</span></span>  <br/> |
|<span data-ttu-id="c9f23-165">可为搜索结果预览的 SharePoint 和 OneDrive for business 网站的最大数量。</span><span class="sxs-lookup"><span data-stu-id="c9f23-165">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="c9f23-166">如果包含与搜索查询匹配的项目的网站超过200个，则仅可预览具有最多结果的前200个网站。</span><span class="sxs-lookup"><span data-stu-id="c9f23-166">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="c9f23-167">200</span><span class="sxs-lookup"><span data-stu-id="c9f23-167">200</span></span>  <br/> |
|<span data-ttu-id="c9f23-168">在搜索的预览页面上显示的每个公用文件夹邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-168">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="c9f23-169">100</span><span class="sxs-lookup"><span data-stu-id="c9f23-169">100</span></span>  <br/> |
|<span data-ttu-id="c9f23-170">在预览页面上显示的用于搜索的所有公用文件夹邮箱项目中找到的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-170">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="c9f23-171">200</span><span class="sxs-lookup"><span data-stu-id="c9f23-171">200</span></span>  <br/> |
|<span data-ttu-id="c9f23-172">可以预览搜索结果的公用文件夹邮箱的最大数量。</span><span class="sxs-lookup"><span data-stu-id="c9f23-172">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="c9f23-173">如果包含与搜索查询匹配的项目的公用文件夹邮箱超过500个，则仅可预览具有最多结果的前500个邮箱。</span><span class="sxs-lookup"><span data-stu-id="c9f23-173">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="c9f23-174">500</span><span class="sxs-lookup"><span data-stu-id="c9f23-174">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="c9f23-175">查看器限制</span><span class="sxs-lookup"><span data-stu-id="c9f23-175">Viewer limits</span></span>

|<span data-ttu-id="c9f23-176">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="c9f23-176">**Description of limit**</span></span>|<span data-ttu-id="c9f23-177">**限制**</span><span class="sxs-lookup"><span data-stu-id="c9f23-177">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9f23-178">可在本机查看器中查看的 Excel 文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="c9f23-178">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="c9f23-179">4 MB</span><span class="sxs-lookup"><span data-stu-id="c9f23-179">4 MB</span></span>  <br/> |
|||

## <a name="export-limits"></a><span data-ttu-id="c9f23-180">导出限制</span><span class="sxs-lookup"><span data-stu-id="c9f23-180">Export limits</span></span>

|<span data-ttu-id="c9f23-181">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="c9f23-181">**Description of limit**</span></span>|<span data-ttu-id="c9f23-182">**限制**</span><span class="sxs-lookup"><span data-stu-id="c9f23-182">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9f23-183">单个导出的最大大小。</span><span class="sxs-lookup"><span data-stu-id="c9f23-183">Maximum size of a single export.</span></span>|<span data-ttu-id="c9f23-184">3000000个文档或 100 GB （以较小者为准）</span><span class="sxs-lookup"><span data-stu-id="c9f23-184">3 million documents or 100 GB, whichever is smaller</span></span>|
|<span data-ttu-id="c9f23-185">一天中的最大数据量。</span><span class="sxs-lookup"><span data-stu-id="c9f23-185">Maximum amount of data in a single day.</span></span> | <span data-ttu-id="c9f23-186">2 TB</span><span class="sxs-lookup"><span data-stu-id="c9f23-186">2 TB</span></span> |
|<span data-ttu-id="c9f23-187">您的组织中的最大并发导出数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-187">Maximum concurrent exports in your organization.</span></span> | <span data-ttu-id="c9f23-188">10 <sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="c9f23-188">10 <sup>4</sup></span></span> |
|<span data-ttu-id="c9f23-189">每个用户的最大并发导出数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-189">Maximum concurrent exports per user.</span></span> | <span data-ttu-id="c9f23-190">第三章</span><span class="sxs-lookup"><span data-stu-id="c9f23-190">3</span></span> |
|<span data-ttu-id="c9f23-191">单个 PST 文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="c9f23-191">Maximum size of a single PST file.</span></span> | <span data-ttu-id="c9f23-192">10 GB</span><span class="sxs-lookup"><span data-stu-id="c9f23-192">10 GB</span></span> |
|<span data-ttu-id="c9f23-193">每个审阅集的最大并发导出数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-193">Maximum concurrent exports per review set.</span></span> | <span data-ttu-id="c9f23-194">1 </span><span class="sxs-lookup"><span data-stu-id="c9f23-194">1</span></span> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="c9f23-195">查看设置下载限制</span><span class="sxs-lookup"><span data-stu-id="c9f23-195">Review set download limits</span></span>

|<span data-ttu-id="c9f23-196">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="c9f23-196">**Description of limit**</span></span>|<span data-ttu-id="c9f23-197">**限制**</span><span class="sxs-lookup"><span data-stu-id="c9f23-197">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9f23-198">从审阅集下载的文件总大小或最大文档数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-198">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="c9f23-199">3 MB 或50文档 <sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="c9f23-199">3 MB or 50 documents <sup>5</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="c9f23-200"><sup>1</sup> 任何超过单个文件限制的项目将显示为处理错误。</span><span class="sxs-lookup"><span data-stu-id="c9f23-200"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="c9f23-201"><sup>2</sup> 在搜索 SharePoint 和 OneDrive for business 位置时，要搜索的网站的 url 中的字符数超过此限制。</span><span class="sxs-lookup"><span data-stu-id="c9f23-201"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="c9f23-202"><sup>3</sup> 对于非短语查询 (不使用双引号的关键字值) 我们使用特殊的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="c9f23-202"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="c9f23-203">这告诉我们文档中出现了一个词，而不是它在文档中出现的位置。</span><span class="sxs-lookup"><span data-stu-id="c9f23-203">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="c9f23-204">若要执行短语查询 (关键字值加上双引号) ，我们需要将该短语中的单词在文档中的位置进行比较。</span><span class="sxs-lookup"><span data-stu-id="c9f23-204">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="c9f23-205">这意味着我们不能使用短语查询的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="c9f23-205">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="c9f23-206">在这种情况下，我们将使用前缀扩展的所有可能的单词在内部展开查询;例如， **time \* *_ 可展开为 _* "time OR timer OR time OR timex or timeboxed or ..."** 。</span><span class="sxs-lookup"><span data-stu-id="c9f23-206">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  \**time\**_ can expand to  _\* "time OR timer OR times OR timex OR timeboxed OR …"\*\*.</span></span> <span data-ttu-id="c9f23-207">"10000" 的限制是该单词可以扩展到的最大变种数，而不是与查询匹配的文档数。</span><span class="sxs-lookup"><span data-stu-id="c9f23-207">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="c9f23-208">非短语搜索词没有上限。</span><span class="sxs-lookup"><span data-stu-id="c9f23-208">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="c9f23-209"><sup>4</sup> 在所有电子数据展示工具之间共享此限制。</span><span class="sxs-lookup"><span data-stu-id="c9f23-209"><sup>4</sup> This limit is shared across all eDiscovery tools.</span></span> <span data-ttu-id="c9f23-210">这意味着将针对此限制应用内容搜索、核心电子数据展示和高级电子数据展示中的并发导出。</span><span class="sxs-lookup"><span data-stu-id="c9f23-210">This means that concurrent exports in Content search, Core eDiscovery, and Advanced eDiscovery are applied against this limit.</span></span> <br/>
> <span data-ttu-id="c9f23-211"><sup>5</sup> 此限制适用于从审阅集下载所选文档。</span><span class="sxs-lookup"><span data-stu-id="c9f23-211"><sup>5</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="c9f23-212">它不适用于从审阅集导出文档。</span><span class="sxs-lookup"><span data-stu-id="c9f23-212">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="c9f23-213">有关下载和导出文档的详细信息，请参阅 [在高级电子数据展示中导出事例数据](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="c9f23-213">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

