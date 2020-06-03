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
description: 了解对 Microsoft 365 中的高级电子数据展示解决方案的有效限制。 这包括使用搜索工具收集事例数据时的大小写限制、索引限制和搜索限制。
ms.openlocfilehash: babc05cc5c74f435f0be6fbc8eafd80f09a77b75
ms.sourcegitcommit: 33be6075fcc89d4c0a48fa7e59f3b3ebc605d9f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "44520144"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="78d42-104">高级电子数据展示中的限制</span><span class="sxs-lookup"><span data-stu-id="78d42-104">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="78d42-105">本文介绍了 Microsoft 365 中的高级电子数据展示解决方案中的限制。</span><span class="sxs-lookup"><span data-stu-id="78d42-105">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="78d42-106">案例和审阅设置限制</span><span class="sxs-lookup"><span data-stu-id="78d42-106">Case and review set limits</span></span>

<span data-ttu-id="78d42-107">下表列出了高级电子数据展示中案例和审阅集的限制。</span><span class="sxs-lookup"><span data-stu-id="78d42-107">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

|<span data-ttu-id="78d42-108">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="78d42-108">**Description of limit**</span></span>|<span data-ttu-id="78d42-109">**限制**</span><span class="sxs-lookup"><span data-stu-id="78d42-109">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="78d42-110">可添加到案例中的文档的总数（案例中的所有审阅集）。</span><span class="sxs-lookup"><span data-stu-id="78d42-110">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="78d42-111">100 万</span><span class="sxs-lookup"><span data-stu-id="78d42-111">1 million</span></span>  <br/> |
|<span data-ttu-id="78d42-112">每个加载集的总文件大小。</span><span class="sxs-lookup"><span data-stu-id="78d42-112">Total file size per load set.</span></span> <span data-ttu-id="78d42-113">这包括将非 Office 365 加载到评审集中。</span><span class="sxs-lookup"><span data-stu-id="78d42-113">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="78d42-114">100 GB</span><span class="sxs-lookup"><span data-stu-id="78d42-114">100 GB</span></span>  <br/> |
|<span data-ttu-id="78d42-115">每天在组织中的所有审阅集中加载的数据总量。</span><span class="sxs-lookup"><span data-stu-id="78d42-115">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="78d42-116">2 TB</span><span class="sxs-lookup"><span data-stu-id="78d42-116">2 TB</span></span> <br/> |
|<span data-ttu-id="78d42-117">每个事例的最大加载集数。</span><span class="sxs-lookup"><span data-stu-id="78d42-117">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="78d42-118">15 </span><span class="sxs-lookup"><span data-stu-id="78d42-118">15</span></span> <br/> |
|<span data-ttu-id="78d42-119">每个案例的最大审阅集数。</span><span class="sxs-lookup"><span data-stu-id="78d42-119">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="78d42-120">20</span><span class="sxs-lookup"><span data-stu-id="78d42-120">20</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="78d42-121">索引限制</span><span class="sxs-lookup"><span data-stu-id="78d42-121">Indexing limits</span></span>

<span data-ttu-id="78d42-122">下表列出了高级电子数据展示中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="78d42-122">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="78d42-123">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="78d42-123">**Description of limit**</span></span>|<span data-ttu-id="78d42-124">**限制**</span><span class="sxs-lookup"><span data-stu-id="78d42-124">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="78d42-125">从单个文件提取的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="78d42-125">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="78d42-126">10000000<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="78d42-126">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="78d42-127">单个文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="78d42-127">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="78d42-128">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="78d42-128">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="78d42-129">文档中嵌入项目的最大深度。</span><span class="sxs-lookup"><span data-stu-id="78d42-129">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="78d42-130">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="78d42-130">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="78d42-131">由光学字符识别（OCR）处理的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="78d42-131">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="78d42-132">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="78d42-132">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="78d42-133">搜索限制</span><span class="sxs-lookup"><span data-stu-id="78d42-133">Search limits</span></span>

<span data-ttu-id="78d42-134">本节中描述的限制与使用 **"搜索" 选项卡**上的搜索工具收集事例数据相关。</span><span class="sxs-lookup"><span data-stu-id="78d42-134">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="78d42-135">有关详细信息，请参阅[在高级电子数据展示中收集数据的大小写](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="78d42-135">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="78d42-136">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="78d42-136">**Description of limit**</span></span>|<span data-ttu-id="78d42-137">**限制**</span><span class="sxs-lookup"><span data-stu-id="78d42-137">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="78d42-138">可在单个搜索中搜索的邮箱或网站的最大数量。</span><span class="sxs-lookup"><span data-stu-id="78d42-138">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="78d42-139">无限制</span><span class="sxs-lookup"><span data-stu-id="78d42-139">No limit</span></span>  <br/> |
|<span data-ttu-id="78d42-140">可以同时运行的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="78d42-140">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="78d42-141">无限制</span><span class="sxs-lookup"><span data-stu-id="78d42-141">No limit</span></span>  <br/> | 
|<span data-ttu-id="78d42-142">一个用户可以同时启动的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="78d42-142">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="78d42-143">10  </span><span class="sxs-lookup"><span data-stu-id="78d42-143">10</span></span>  <br/> | 
|<span data-ttu-id="78d42-144">搜索查询的最大字符数（包括运算符和条件）。</span><span class="sxs-lookup"><span data-stu-id="78d42-144">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="78d42-145">**邮箱**：10000</span><span class="sxs-lookup"><span data-stu-id="78d42-145">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="78d42-146">**网站**：4000搜索所有网站或2000时搜索20个网站<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="78d42-146">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="78d42-147">前缀通配符的最小字母字符数;例如**一个或 \* 一个** \*\*set \* \*\*。</span><span class="sxs-lookup"><span data-stu-id="78d42-147">Minimum number of alpha characters for prefix wildcards; for example **one\*** or **set\***.</span></span> <br/> |<span data-ttu-id="78d42-148">第三章</span><span class="sxs-lookup"><span data-stu-id="78d42-148">3</span></span>  <br/> |  
|<span data-ttu-id="78d42-149">使用前缀通配符搜索精确短语或使用前缀通配符和**接近**的布尔运算符时返回的最大变体。</span><span class="sxs-lookup"><span data-stu-id="78d42-149">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="78d42-150">10000 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="78d42-150">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="78d42-151">在搜索的预览页面上显示的每个用户邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="78d42-151">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="78d42-152">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="78d42-152">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="78d42-153">100</span><span class="sxs-lookup"><span data-stu-id="78d42-153">100</span></span>  <br/> |
|<span data-ttu-id="78d42-154">用于搜索的预览页面上显示的所有邮箱中的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="78d42-154">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="78d42-155">1,000</span><span class="sxs-lookup"><span data-stu-id="78d42-155">1,000</span></span>  <br/> |
|<span data-ttu-id="78d42-156">可为搜索结果预览的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="78d42-156">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="78d42-157">如果有超过1000个邮箱包含与搜索查询匹配的项目，则仅可预览具有最多结果的前1000个邮箱。</span><span class="sxs-lookup"><span data-stu-id="78d42-157">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="78d42-158">1,000</span><span class="sxs-lookup"><span data-stu-id="78d42-158">1,000</span></span>  <br/> |
|<span data-ttu-id="78d42-159">SharePoint 和 OneDrive for business 网站上显示的搜索的预览页面上显示的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="78d42-159">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="78d42-160">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="78d42-160">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="78d42-161">200</span><span class="sxs-lookup"><span data-stu-id="78d42-161">200</span></span>  <br/> |
|<span data-ttu-id="78d42-162">可为搜索结果预览的 SharePoint 和 OneDrive for business 网站的最大数量。</span><span class="sxs-lookup"><span data-stu-id="78d42-162">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="78d42-163">如果包含与搜索查询匹配的项目的网站超过200个，则仅可预览具有最多结果的前200个网站。</span><span class="sxs-lookup"><span data-stu-id="78d42-163">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="78d42-164">200</span><span class="sxs-lookup"><span data-stu-id="78d42-164">200</span></span>  <br/> |
|<span data-ttu-id="78d42-165">在搜索的预览页面上显示的每个公用文件夹邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="78d42-165">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="78d42-166">100</span><span class="sxs-lookup"><span data-stu-id="78d42-166">100</span></span>  <br/> |
|<span data-ttu-id="78d42-167">在预览页面上显示的用于搜索的所有公用文件夹邮箱项目中找到的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="78d42-167">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="78d42-168">200</span><span class="sxs-lookup"><span data-stu-id="78d42-168">200</span></span>  <br/> |
|<span data-ttu-id="78d42-169">可以预览搜索结果的公用文件夹邮箱的最大数量。</span><span class="sxs-lookup"><span data-stu-id="78d42-169">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="78d42-170">如果包含与搜索查询匹配的项目的公用文件夹邮箱超过500个，则仅可预览具有最多结果的前500个邮箱。</span><span class="sxs-lookup"><span data-stu-id="78d42-170">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="78d42-171">500</span><span class="sxs-lookup"><span data-stu-id="78d42-171">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="78d42-172">查看器限制</span><span class="sxs-lookup"><span data-stu-id="78d42-172">Viewer limits</span></span>

|<span data-ttu-id="78d42-173">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="78d42-173">**Description of limit**</span></span>|<span data-ttu-id="78d42-174">**限制**</span><span class="sxs-lookup"><span data-stu-id="78d42-174">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="78d42-175">可在本机查看器中查看的 Excel 文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="78d42-175">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="78d42-176">4 MB</span><span class="sxs-lookup"><span data-stu-id="78d42-176">4 MB</span></span>  <br/> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="78d42-177">查看设置下载限制</span><span class="sxs-lookup"><span data-stu-id="78d42-177">Review set download limits</span></span>

|<span data-ttu-id="78d42-178">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="78d42-178">**Description of limit**</span></span>|<span data-ttu-id="78d42-179">**限制**</span><span class="sxs-lookup"><span data-stu-id="78d42-179">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="78d42-180">从审阅集下载的文件总大小或最大文档数。</span><span class="sxs-lookup"><span data-stu-id="78d42-180">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="78d42-181">3 MB 或50文档<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="78d42-181">3 MB or 50 documents <sup>4</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="78d42-182"><sup>1</sup>任何超过单个文件限制的项目将显示为处理错误。</span><span class="sxs-lookup"><span data-stu-id="78d42-182"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="78d42-183"><sup>2</sup>在搜索 SharePoint 和 OneDrive for business 位置时，要搜索的网站的 url 中的字符数超过此限制。</span><span class="sxs-lookup"><span data-stu-id="78d42-183"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="78d42-184"><sup>3</sup>对于非短语查询（不使用双引号的关键字值），我们使用特殊的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="78d42-184"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="78d42-185">这告诉我们文档中出现了一个词，而不是它在文档中出现的位置。</span><span class="sxs-lookup"><span data-stu-id="78d42-185">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="78d42-186">若要执行短语查询（带有双引号的关键字值），我们需要将文档中的单词的位置与短语中的单词进行比较。</span><span class="sxs-lookup"><span data-stu-id="78d42-186">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="78d42-187">这意味着我们不能使用短语查询的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="78d42-187">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="78d42-188">在这种情况下，我们将使用前缀扩展的所有可能的单词在内部展开查询;例如， \*\*time \* \*\*可以扩展为 **"time OR timer OR time OR timex or timeboxed or ..."**。</span><span class="sxs-lookup"><span data-stu-id="78d42-188">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\*** can expand to  **"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="78d42-189">"10000" 的限制是该单词可以扩展到的最大变种数，而不是与查询匹配的文档数。</span><span class="sxs-lookup"><span data-stu-id="78d42-189">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="78d42-190">非短语搜索词没有上限。</span><span class="sxs-lookup"><span data-stu-id="78d42-190">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="78d42-191"><sup>4</sup>此限制适用于从审阅集下载所选文档。</span><span class="sxs-lookup"><span data-stu-id="78d42-191"><sup>4</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="78d42-192">它不适用于从审阅集导出文档。</span><span class="sxs-lookup"><span data-stu-id="78d42-192">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="78d42-193">有关下载和导出文档的详细信息，请参阅[在高级电子数据展示中导出事例数据](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="78d42-193">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

