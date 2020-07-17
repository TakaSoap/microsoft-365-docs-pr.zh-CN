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
description: 了解 Microsoft 365 中适用于高级电子数据展示解决方案的案例限制、索引限制和搜索限制。
ms.openlocfilehash: 4f8222abaea0e8920e48f2f7b506d9477e93bc84
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126865"
---
# <a name="limits-in-advanced-ediscovery"></a><span data-ttu-id="65d2a-103">高级电子数据展示中的限制</span><span class="sxs-lookup"><span data-stu-id="65d2a-103">Limits in Advanced eDiscovery</span></span>

<span data-ttu-id="65d2a-104">本文介绍了 Microsoft 365 中的高级电子数据展示解决方案中的限制。</span><span class="sxs-lookup"><span data-stu-id="65d2a-104">This article describes the limits in the Advanced eDiscovery solution in Microsoft 365.</span></span>

## <a name="case-and-review-set-limits"></a><span data-ttu-id="65d2a-105">案例和审阅设置限制</span><span class="sxs-lookup"><span data-stu-id="65d2a-105">Case and review set limits</span></span>

<span data-ttu-id="65d2a-106">下表列出了高级电子数据展示中案例和审阅集的限制。</span><span class="sxs-lookup"><span data-stu-id="65d2a-106">The following table lists the limits for cases and review sets in Advanced eDiscovery.</span></span>

|<span data-ttu-id="65d2a-107">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="65d2a-107">**Description of limit**</span></span>|<span data-ttu-id="65d2a-108">**限制**</span><span class="sxs-lookup"><span data-stu-id="65d2a-108">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="65d2a-109">可添加到案例中的文档的总数（案例中的所有审阅集）。</span><span class="sxs-lookup"><span data-stu-id="65d2a-109">Total number of documents that can be added to a case (for all review sets in a case).</span></span>  <br/> |<span data-ttu-id="65d2a-110">3 百万</span><span class="sxs-lookup"><span data-stu-id="65d2a-110">3 million</span></span> <br/> |
|<span data-ttu-id="65d2a-111">每个加载集的总文件大小。</span><span class="sxs-lookup"><span data-stu-id="65d2a-111">Total file size per load set.</span></span> <span data-ttu-id="65d2a-112">这包括将非 Office 365 加载到评审集中。</span><span class="sxs-lookup"><span data-stu-id="65d2a-112">This includes loading non-Office 365 into a review set.</span></span>  <br/> |<span data-ttu-id="65d2a-113">300 GB</span><span class="sxs-lookup"><span data-stu-id="65d2a-113">300 GB</span></span> <br/> |
|<span data-ttu-id="65d2a-114">每天在组织中的所有审阅集中加载的数据总量。</span><span class="sxs-lookup"><span data-stu-id="65d2a-114">Total amount of data loaded into all review sets in the organization per day.</span></span><br/> |<span data-ttu-id="65d2a-115">2 TB</span><span class="sxs-lookup"><span data-stu-id="65d2a-115">2 TB</span></span> <br/> |
|<span data-ttu-id="65d2a-116">每个事例的最大加载集数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-116">Maximum number of loads sets per case.</span></span>  <br/> |<span data-ttu-id="65d2a-117">15 </span><span class="sxs-lookup"><span data-stu-id="65d2a-117">15</span></span> <br/> |
|<span data-ttu-id="65d2a-118">每个案例的最大审阅集数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-118">Maximum number of review sets per case.</span></span>  <br/> |<span data-ttu-id="65d2a-119">20</span><span class="sxs-lookup"><span data-stu-id="65d2a-119">20</span></span> <br/> |
|||

## <a name="indexing-limits"></a><span data-ttu-id="65d2a-120">索引限制</span><span class="sxs-lookup"><span data-stu-id="65d2a-120">Indexing limits</span></span>

<span data-ttu-id="65d2a-121">下表列出了高级电子数据展示中的索引限制。</span><span class="sxs-lookup"><span data-stu-id="65d2a-121">The following table lists the indexing limits in Advanced eDiscovery.</span></span>

|<span data-ttu-id="65d2a-122">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="65d2a-122">**Description of limit**</span></span>|<span data-ttu-id="65d2a-123">**限制**</span><span class="sxs-lookup"><span data-stu-id="65d2a-123">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="65d2a-124">从单个文件提取的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-124">Maximum number of characters extracted from a single file.</span></span>  <br/> |<span data-ttu-id="65d2a-125">10000000<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="65d2a-125">10 million<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="65d2a-126">单个文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="65d2a-126">Maximum size of a single file.</span></span>   <br/> |<span data-ttu-id="65d2a-127">100 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="65d2a-127">100 MB<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="65d2a-128">文档中嵌入项目的最大深度。</span><span class="sxs-lookup"><span data-stu-id="65d2a-128">Maximum depth of embedded items in a document.</span></span>  <br/> |<span data-ttu-id="65d2a-129">25<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="65d2a-129">25<sup>1</sup></span></span> <br/> |
  |<span data-ttu-id="65d2a-130">由光学字符识别（OCR）处理的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="65d2a-130">Maximum size of file processed by Optical Character Recognition (OCR).</span></span>  <br/> |<span data-ttu-id="65d2a-131">24 MB<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="65d2a-131">24 MB<sup>1</sup></span></span> <br/> |  
|||

## <a name="search-limits"></a><span data-ttu-id="65d2a-132">搜索限制</span><span class="sxs-lookup"><span data-stu-id="65d2a-132">Search limits</span></span>

<span data-ttu-id="65d2a-133">本节中描述的限制与使用 **"搜索" 选项卡**上的搜索工具收集事例数据相关。</span><span class="sxs-lookup"><span data-stu-id="65d2a-133">The limits described in this section are related to using the search tool on the **Searches** tab to collect data for a case.</span></span> <span data-ttu-id="65d2a-134">有关详细信息，请参阅[在高级电子数据展示中收集数据的大小写](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="65d2a-134">For more information, see [Collect data for a case in Advanced eDiscovery](collecting-data-for-ediscovery.md).</span></span>

|<span data-ttu-id="65d2a-135">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="65d2a-135">**Description of limit**</span></span>|<span data-ttu-id="65d2a-136">**限制**</span><span class="sxs-lookup"><span data-stu-id="65d2a-136">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="65d2a-137">可在单个搜索中搜索的邮箱或网站的最大数量。</span><span class="sxs-lookup"><span data-stu-id="65d2a-137">Maximum number of mailboxes or sites that can be searched in a single search.</span></span>  <br/> |<span data-ttu-id="65d2a-138">无限制</span><span class="sxs-lookup"><span data-stu-id="65d2a-138">No limit</span></span>  <br/> |
|<span data-ttu-id="65d2a-139">可以同时运行的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-139">Maximum number of searches that can run at the same time.</span></span>  <br/> |<span data-ttu-id="65d2a-140">无限制</span><span class="sxs-lookup"><span data-stu-id="65d2a-140">No limit</span></span>  <br/> | 
|<span data-ttu-id="65d2a-141">一个用户可以同时启动的最大搜索数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-141">Maximum number of searches that a single user can start at the same time.</span></span>  <br/> |<span data-ttu-id="65d2a-142">10 </span><span class="sxs-lookup"><span data-stu-id="65d2a-142">10</span></span>  <br/> | 
|<span data-ttu-id="65d2a-143">搜索查询的最大字符数（包括运算符和条件）。</span><span class="sxs-lookup"><span data-stu-id="65d2a-143">Maximum number of characters for a search query (including operators and conditions).</span></span>  <br/> |<span data-ttu-id="65d2a-144">**邮箱**：10000</span><span class="sxs-lookup"><span data-stu-id="65d2a-144">**Mailboxes**: 10,000</span></span><br/><span data-ttu-id="65d2a-145">**网站**：4000搜索所有网站或2000时搜索20个网站<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="65d2a-145">**Sites**: 4,000 when searching all sites or 2,000 when searching up to 20 sites <sup>2</sup></span></span> <br/> |
|<span data-ttu-id="65d2a-146">前缀通配符的最小字母字符数;例如**一个或 \* 一个** \*\*set \* \*\*。</span><span class="sxs-lookup"><span data-stu-id="65d2a-146">Minimum number of alpha characters for prefix wildcards; for example **one\*** or **set\***.</span></span> <br/> |<span data-ttu-id="65d2a-147">3 </span><span class="sxs-lookup"><span data-stu-id="65d2a-147">3</span></span>  <br/> |  
|<span data-ttu-id="65d2a-148">使用前缀通配符搜索精确短语或使用前缀通配符和**接近**的布尔运算符时返回的最大变体。</span><span class="sxs-lookup"><span data-stu-id="65d2a-148">Maximum variants returned when using prefix wildcard to search for an exact phrase or when using a prefix wildcard and the **NEAR** Boolean operator.</span></span>  <br/> |<span data-ttu-id="65d2a-149">10000 <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="65d2a-149">10,000 <sup>3</sup></span></span> <br/> |
|<span data-ttu-id="65d2a-150">在搜索的预览页面上显示的每个用户邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-150">Maximum number of items per user mailbox that are displayed on preview page for searches.</span></span> <span data-ttu-id="65d2a-151">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="65d2a-151">The newest items are displayed.</span></span>   <br/> |<span data-ttu-id="65d2a-152">100</span><span class="sxs-lookup"><span data-stu-id="65d2a-152">100</span></span>  <br/> |
|<span data-ttu-id="65d2a-153">用于搜索的预览页面上显示的所有邮箱中的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-153">Maximum number of items from all mailboxes displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="65d2a-154">1,000</span><span class="sxs-lookup"><span data-stu-id="65d2a-154">1,000</span></span>  <br/> |
|<span data-ttu-id="65d2a-155">可为搜索结果预览的最大邮箱数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-155">Maximum number of mailboxes that can be previewed for search results.</span></span>  <span data-ttu-id="65d2a-156">如果有超过1000个邮箱包含与搜索查询匹配的项目，则仅可预览具有最多结果的前1000个邮箱。</span><span class="sxs-lookup"><span data-stu-id="65d2a-156">If there are more than 1000 mailboxes that contain items that match the search query, only the top 1,000 mailboxes with the most results are available for preview.</span></span><br/> |<span data-ttu-id="65d2a-157">1,000</span><span class="sxs-lookup"><span data-stu-id="65d2a-157">1,000</span></span>  <br/> |
|<span data-ttu-id="65d2a-158">SharePoint 和 OneDrive for business 网站上显示的搜索的预览页面上显示的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-158">Maximum number of items from SharePoint and OneDrive for Business sites displayed on preview page for searches.</span></span> <span data-ttu-id="65d2a-159">显示最新项目。</span><span class="sxs-lookup"><span data-stu-id="65d2a-159">The newest items are displayed.</span></span>  <br/> |<span data-ttu-id="65d2a-160">200</span><span class="sxs-lookup"><span data-stu-id="65d2a-160">200</span></span>  <br/> |
|<span data-ttu-id="65d2a-161">可为搜索结果预览的 SharePoint 和 OneDrive for business 网站的最大数量。</span><span class="sxs-lookup"><span data-stu-id="65d2a-161">Maximum number of SharePoint and OneDrive for Business sites that can be previewed for search results.</span></span> <span data-ttu-id="65d2a-162">如果包含与搜索查询匹配的项目的网站超过200个，则仅可预览具有最多结果的前200个网站。</span><span class="sxs-lookup"><span data-stu-id="65d2a-162">If there are more than 200 sites that contain items that match the search query, only the top 200 sites with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="65d2a-163">200</span><span class="sxs-lookup"><span data-stu-id="65d2a-163">200</span></span>  <br/> |
|<span data-ttu-id="65d2a-164">在搜索的预览页面上显示的每个公用文件夹邮箱的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-164">Maximum number of items per public folder mailbox displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="65d2a-165">100</span><span class="sxs-lookup"><span data-stu-id="65d2a-165">100</span></span>  <br/> |
|<span data-ttu-id="65d2a-166">在预览页面上显示的用于搜索的所有公用文件夹邮箱项目中找到的最大项目数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-166">Maximum number of items found in all public folder mailbox items displayed on preview page for searches.</span></span>  <br/> |<span data-ttu-id="65d2a-167">200</span><span class="sxs-lookup"><span data-stu-id="65d2a-167">200</span></span>  <br/> |
|<span data-ttu-id="65d2a-168">可以预览搜索结果的公用文件夹邮箱的最大数量。</span><span class="sxs-lookup"><span data-stu-id="65d2a-168">Maximum number of public folder mailboxes that can be previewed for search results.</span></span> <span data-ttu-id="65d2a-169">如果包含与搜索查询匹配的项目的公用文件夹邮箱超过500个，则仅可预览具有最多结果的前500个邮箱。</span><span class="sxs-lookup"><span data-stu-id="65d2a-169">If there are more than 500 public folder mailboxes that contain items that match the search query, only the top 500 mailboxes with the most results are available for preview.</span></span>  <br/> |<span data-ttu-id="65d2a-170">500</span><span class="sxs-lookup"><span data-stu-id="65d2a-170">500</span></span>  <br/> |
|||

## <a name="viewer-limits"></a><span data-ttu-id="65d2a-171">查看器限制</span><span class="sxs-lookup"><span data-stu-id="65d2a-171">Viewer limits</span></span>

|<span data-ttu-id="65d2a-172">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="65d2a-172">**Description of limit**</span></span>|<span data-ttu-id="65d2a-173">**限制**</span><span class="sxs-lookup"><span data-stu-id="65d2a-173">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="65d2a-174">可在本机查看器中查看的 Excel 文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="65d2a-174">Maximum size of Excel file that can be viewed in the native viewer.</span></span>  <br/> |<span data-ttu-id="65d2a-175">4 MB</span><span class="sxs-lookup"><span data-stu-id="65d2a-175">4 MB</span></span>  <br/> |
|||

## <a name="review-set-download-limits"></a><span data-ttu-id="65d2a-176">查看设置下载限制</span><span class="sxs-lookup"><span data-stu-id="65d2a-176">Review set download limits</span></span>

|<span data-ttu-id="65d2a-177">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="65d2a-177">**Description of limit**</span></span>|<span data-ttu-id="65d2a-178">**限制**</span><span class="sxs-lookup"><span data-stu-id="65d2a-178">**Limit**</span></span>|
|:-----|:-----|
|<span data-ttu-id="65d2a-179">从审阅集下载的文件总大小或最大文档数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-179">Total file size or maximum number of documents downloaded from a review set.</span></span>  <br/> |<span data-ttu-id="65d2a-180">3 MB 或50文档<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="65d2a-180">3 MB or 50 documents <sup>4</sup></span></span>|
|||

<br/>
<br/>

> [!NOTE]
> <span data-ttu-id="65d2a-181"><sup>1</sup>任何超过单个文件限制的项目将显示为处理错误。</span><span class="sxs-lookup"><span data-stu-id="65d2a-181"><sup>1</sup> Any item that exceeds a single file limit will show up as a processing error.</span></span><br/>
> <span data-ttu-id="65d2a-182"><sup>2</sup>在搜索 SharePoint 和 OneDrive for business 位置时，要搜索的网站的 url 中的字符数超过此限制。</span><span class="sxs-lookup"><span data-stu-id="65d2a-182"><sup>2</sup> When searching SharePoint and OneDrive for Business locations, the characters in the URLs of the sites being searched count against this limit.</span></span><br/>
> <span data-ttu-id="65d2a-183"><sup>3</sup>对于非短语查询（不使用双引号的关键字值），我们使用特殊的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="65d2a-183"><sup>3</sup> For non-phrase queries (a keyword value that doesn't use double quotation marks) we use a special prefix index.</span></span> <span data-ttu-id="65d2a-184">这告诉我们文档中出现了一个词，而不是它在文档中出现的位置。</span><span class="sxs-lookup"><span data-stu-id="65d2a-184">This tells us that a word occurs in a document, but not where it occurs in the document.</span></span> <span data-ttu-id="65d2a-185">若要执行短语查询（带有双引号的关键字值），我们需要将文档中的单词的位置与短语中的单词进行比较。</span><span class="sxs-lookup"><span data-stu-id="65d2a-185">To do a phrase query (a keyword value with double quotation marks), we need to compare the position within the document for the words in the phrase.</span></span> <span data-ttu-id="65d2a-186">这意味着我们不能使用短语查询的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="65d2a-186">This means that we can't use the prefix index for phrase queries.</span></span> <span data-ttu-id="65d2a-187">在这种情况下，我们将使用前缀扩展的所有可能的单词在内部展开查询;例如， \*\*time \* \*\*可以扩展为 **"time OR timer OR time OR timex or timeboxed or ..."**。</span><span class="sxs-lookup"><span data-stu-id="65d2a-187">In this case, we internally expand the query with all possible words that the prefix expands to; for example,  **time\*** can expand to  **"time OR timer OR times OR timex OR timeboxed OR …"**.</span></span> <span data-ttu-id="65d2a-188">"10000" 的限制是该单词可以扩展到的最大变种数，而不是与查询匹配的文档数。</span><span class="sxs-lookup"><span data-stu-id="65d2a-188">The limit of 10,000 is the maximum number of variants the word can expand to, not the number of documents matching the query.</span></span> <span data-ttu-id="65d2a-189">非短语搜索词没有上限。</span><span class="sxs-lookup"><span data-stu-id="65d2a-189">There is no upper limit for non-phrase terms.</span></span><br/>
> <span data-ttu-id="65d2a-190"><sup>4</sup>此限制适用于从审阅集下载所选文档。</span><span class="sxs-lookup"><span data-stu-id="65d2a-190"><sup>4</sup> This limit applies to downloading selected documents from a review set.</span></span> <span data-ttu-id="65d2a-191">它不适用于从审阅集导出文档。</span><span class="sxs-lookup"><span data-stu-id="65d2a-191">It doesn't apply to exporting documents from a review set.</span></span> <span data-ttu-id="65d2a-192">有关下载和导出文档的详细信息，请参阅[在高级电子数据展示中导出事例数据](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="65d2a-192">For more information about downloading and exporting documents, see [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).</span></span> <br/>

