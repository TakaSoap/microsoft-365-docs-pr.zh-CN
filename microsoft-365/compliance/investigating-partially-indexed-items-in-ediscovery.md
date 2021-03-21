---
title: 调查电子数据展示中的部分索引项
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: 了解如何在组织中管理部分索引 (，也称为) Exchange、SharePoint 和 OneDrive for Business 中的未编制索引的项目。
ms.openlocfilehash: 5d30c0f7c6ae77236ba7fd9f2dbfcc7a0397ae21
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922576"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="3f0a0-103">调查电子数据展示中的部分索引项</span><span class="sxs-lookup"><span data-stu-id="3f0a0-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="3f0a0-104">在运行搜索时，从 Microsoft 365 合规中心运行电子数据展示搜索会自动在估计的搜索结果中包含部分索引项。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="3f0a0-105">部分索引项目是 Exchange 邮箱项目以及 SharePoint 和 OneDrive for Business 网站上由于某种原因未完全编制索引进行搜索的文档。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="3f0a0-106">大多数电子邮件和网站文档都已成功编制索引，因为它们在电子邮件 [的索引限制范围内](limits-for-content-search.md#indexing-limits-for-email-messages)。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="3f0a0-107">但是，某些项目可能会超出这些索引限制，并且将被部分索引。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="3f0a0-108">以下是在运行电子数据展示搜索时无法对项目编制索引并作为部分索引项返回的其他原因：</span><span class="sxs-lookup"><span data-stu-id="3f0a0-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="3f0a0-109">电子邮件具有一个附加文件，没有有效的处理程序，如图像文件;这是部分索引电子邮件项目的最常见原因。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="3f0a0-110">附加到电子邮件的文件过多。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="3f0a0-111">附加到电子邮件的文件过大。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="3f0a0-112">文件类型支持检索，但是特定文件出现检索错误。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="3f0a0-113">尽管内容量不同，但大多数组织客户的内容量少于 1%，而按部分索引大小表示的内容少于 12%。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="3f0a0-114">卷与大小之间的区别在于，较大的文件包含无法完全编制索引的内容的可能性较高。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="3f0a0-115">为什么部分索引项计数会更改搜索？</span><span class="sxs-lookup"><span data-stu-id="3f0a0-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="3f0a0-116">运行电子数据展示搜索后，搜索位置中部分索引项的总数和大小将在搜索结果统计信息中列出，搜索结果统计信息显示在搜索的详细统计信息中。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="3f0a0-117">请注意，这些  *项在搜索统计信息*  中称为未索引项。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="3f0a0-118">下面是将影响搜索结果中返回的部分索引项数的一些事项：</span><span class="sxs-lookup"><span data-stu-id="3f0a0-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="3f0a0-119">如果某个项目已部分编制索引且与搜索查询匹配，则它同时包含在搜索结果项的计数 (和) 索引项和部分索引项的大小中。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="3f0a0-120">但是，导出同一搜索的结果时，该项目仅包含在一组搜索结果中;它不包含为部分索引项。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="3f0a0-121">如果通过将搜索查询 (包括在关键字查询中或通过使用条件) 来为搜索查询 (指定日期范围，则任何与日期范围不匹配的部分索引项不会包含在部分索引项的计数中。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-121">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="3f0a0-122">日期范围内的部分索引项包含在索引项的计数中。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-122">Partially indexed items that fall within date range are included in the count of indexed items.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3f0a0-123">SharePoint 和 OneDrive 网站中的部分索引项不包括在搜索的详细统计信息中显示的部分索引项的估计值中。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-123">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="3f0a0-124">但是，在导出电子数据展示搜索的结果时，可以导出部分索引项。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-124">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="3f0a0-125">例如，如果您仅搜索网站，则估计的部分索引项数将为 0。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-125">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="3f0a0-126">计算组织中部分索引项的比率</span><span class="sxs-lookup"><span data-stu-id="3f0a0-126">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="3f0a0-127">若要了解组织对部分索引项目的暴露情况，可以使用空白关键字查询查询来运行对 (邮箱中所有内容) 。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-127">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="3f0a0-128">在下面的示例中，有 56，208 (4，830 MB) 完全索引项和 470 (316 MB) 部分索引项。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-128">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![显示部分索引项的搜索统计信息示例](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="3f0a0-130">可以使用以下计算来确定部分索引项的百分比。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-130">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="3f0a0-131">**要计算组织中部分索引项的比率，请执行以下各项：**</span><span class="sxs-lookup"><span data-stu-id="3f0a0-131">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

<span data-ttu-id="3f0a0-132">通过使用上一示例中的搜索结果，所有邮箱项目的 .84% 部分索引。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-132">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="3f0a0-133">**若要计算组织中部分索引项大小的百分比，请执行以下设置：**</span><span class="sxs-lookup"><span data-stu-id="3f0a0-133">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="3f0a0-134">因此，在上一示例中，6.54% 的邮箱项目总大小来自部分索引项目。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-134">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="3f0a0-135">如前所述，大多数组织客户的内容量少于 1%，而按内容大小（部分索引）则少于 12%。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-135">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="3f0a0-136">处理部分索引项</span><span class="sxs-lookup"><span data-stu-id="3f0a0-136">Working with partially indexed items</span></span>

<span data-ttu-id="3f0a0-137">在需要检查部分项目以验证它们不包含相关信息的情况下，可以导出包含部分索引项信息的内容搜索报告[](export-a-content-search-report.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-137">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="3f0a0-138">导出内容搜索报告时，请确保选择包含部分索引项的导出选项之一。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-138">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![选择第二个或第三个选项以导出部分索引项](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="3f0a0-140">使用这些选项之一导出电子数据展示搜索结果或搜索报告时，导出包括名为 Unindexed Items.csv。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-140">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="3f0a0-141">此报告包含大多数与文件相同的ResultsLog.csv信息;但是，Unindexed Items.csv还包含两个与部分索引项相关的字段： **错误标记** 和 **错误属性**。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-141">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="3f0a0-142">这些字段包含有关每个部分索引项的索引错误的信息。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-142">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="3f0a0-143">使用这两个字段中的信息可以帮助您确定特定字段的索引错误是否会影响调查。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-143">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="3f0a0-144">如果是这样，可以执行定向搜索，并检索和导出特定电子邮件和 SharePoint 或 OneDrive 文档，以便检查它们以确定它们是否与你的调查相关。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-144">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="3f0a0-145">有关分步说明，请参阅 Prepare [a CSV file for a targeted search in Office 365。](csv-file-for-an-id-list-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="3f0a0-145">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3f0a0-146">Unindexed Items.csv还包含名为 **Error Type** 和 Error **Message 的字段**。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-146">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="3f0a0-147">这些是旧字段，包含的信息与"**错误** 标记"和"错误属性"字段中的信息类似，但信息不太详细。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-147">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="3f0a0-148">可以安全地忽略这些旧字段。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-148">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="3f0a0-149">与部分索引项相关的错误</span><span class="sxs-lookup"><span data-stu-id="3f0a0-149">Errors related to partially indexed items</span></span>

<span data-ttu-id="3f0a0-150">错误标记由两条信息（错误和文件类型）决定。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-150">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="3f0a0-151">例如，在此错误/文件类型对中：</span><span class="sxs-lookup"><span data-stu-id="3f0a0-151">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="3f0a0-152">`parseroutputsize` 是错误 `xls` ，也是发生错误的文件的文件类型。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-152">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="3f0a0-153">如果无法识别文件类型或文件类型未应用于错误，则会看到值来表示文件类型 `noformat` 。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-153">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="3f0a0-154">下面列出了索引错误以及错误可能原因的说明。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-154">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="3f0a0-155">错误标记</span><span class="sxs-lookup"><span data-stu-id="3f0a0-155">Error tag</span></span> | <span data-ttu-id="3f0a0-156">说明</span><span class="sxs-lookup"><span data-stu-id="3f0a0-156">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="3f0a0-157">电子邮件的附件过多，其中一些附件未处理。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-157">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="3f0a0-158">内容检索和文档分析程序发现嵌套在其他附件中的附件级别过多。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-158">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="3f0a0-159">其中某些附件未处理。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-159">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="3f0a0-160">附件解码失败，因为它受 RMS 保护。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-160">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="3f0a0-161">附加到电子邮件的文件太大，无法处理。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-161">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="3f0a0-162">将已处理的电子邮件写入索引时，其中一个可编制索引的属性太大，被截断。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-162">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="3f0a0-163">截断的属性列在"错误属性"字段中。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-163">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="3f0a0-164">电子邮件包含无法作为有效 Unicode 处理的文本。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-164">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="3f0a0-165">此项的索引编制可能不完整。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-165">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="3f0a0-166">附件或电子邮件的内容已加密，Microsoft 365 无法解码内容。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-166">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="3f0a0-167">分析过程中出现未知错误。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-167">An unknown error occurred during parsing.</span></span> <span data-ttu-id="3f0a0-168">这通常由软件 Bug 或服务崩溃导致。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-168">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="3f0a0-169">附件太大，分析程序无法处理，并且该附件的解析未发生或未完成。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-169">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="3f0a0-170">附件格式不正确，无法由分析程序处理。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-170">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="3f0a0-171">此结果可能是由于文件格式旧、不兼容的软件创建的文件或冒充声明的病毒。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-171">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="3f0a0-172">分析附件的输出太大，必须截断。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-172">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="3f0a0-173">附件具有 Microsoft 365 无法检测到的文件类型。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-173">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="3f0a0-174">附件具有 Office 365 可以检测到的文件类型，但不支持分析该文件类型。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-174">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="3f0a0-175">Exchange 存储中的电子邮件属性的值太大，无法检索，且无法处理邮件。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-175">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="3f0a0-176">这通常仅适用于电子邮件的 body 属性。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-176">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="3f0a0-177">内容检索器无法解码受 RMS 保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-177">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="3f0a0-178">在编制索引期间，文档中标识的单词过多。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-178">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="3f0a0-179">当达到限制时，将停止对属性的处理，并且该属性将被截断。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-179">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="3f0a0-180">错误字段描述哪些字段受"错误标记"字段中列出的处理错误的影响。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-180">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="3f0a0-181">如果要搜索诸如 或 等属性，邮件正文中的错误不会影响  `subject`  `participants` 搜索结果。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-181">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="3f0a0-182">当准确确定哪些部分索引项可能需要进一步调查时，这可能很有用。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-182">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="3f0a0-183">使用 PowerShell 脚本确定组织对部分索引电子邮件项目的曝光</span><span class="sxs-lookup"><span data-stu-id="3f0a0-183">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="3f0a0-184">以下步骤显示如何运行 PowerShell 脚本，该脚本在所有 Exchange 邮箱中搜索所有项目，然后根据计数和大小) 生成有关组织部分索引电子邮件项目 (的比率的报告，并显示发生的每个索引错误的项目数 (及其文件类型) 。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-184">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="3f0a0-185">使用上一节中的错误标记说明来标识索引错误。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-185">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="3f0a0-186">使用文件名后缀 .ps1 将以下文本Windows PowerShell脚本文件;例如， `PartiallyIndexedItems.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-186">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

   ```powershell
     write-host "**************************************************"
     write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "**************************************************"
     " " 
     # Create a search with Error Tags Refinders enabled
     Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
     New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
     Start-ComplianceSearch "RefinerTest"
     # Loop while search is in progress
     do{
         Write-host "Waiting for search to complete..."
         Start-Sleep -s 5
         $complianceSearch = Get-ComplianceSearch "RefinerTest"
     }while ($complianceSearch.Status -ne 'Completed')
     $refiners = $complianceSearch.Refiners | ConvertFrom-Json
     $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
     $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
     $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
     " "
     "===== Partially indexed items ====="
     "         Total          Ratio"
     "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
     "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
     " "
     Write-Host ===== Reasons for partially indexed items =====
     foreach($errorTagProperty in $errorTagProperties)
     {
         $name = $refiners.Entries.($errorTagProperty.Name).Name
         $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
         $frag = $name.Split("{_}")
         $errorTag = $frag[0]
         $fileType = $frag[1]
         if ($errorTag -ne $lastErrorTag)
         {
             $errorTag
         }
         "    " + $fileType + " => " + $count
         $lastErrorTag = $errorTag
     }
   ```

2. <span data-ttu-id="3f0a0-187">[连接到安全与合规中心 PowerShell](/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-187">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

3. <span data-ttu-id="3f0a0-188">在安全&合规中心 PowerShell 中，转到步骤 1 中保存脚本的文件夹，然后运行脚本;例如：</span><span class="sxs-lookup"><span data-stu-id="3f0a0-188">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="3f0a0-189">下面是脚本返回的输出的示例。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-189">Here's an example fo the output returned by the script.</span></span>
  
![生成有关组织对部分索引电子邮件项目的曝光的报告的脚本输出示例](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="3f0a0-191">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="3f0a0-191">Note the following:</span></span>
>  
> - <span data-ttu-id="3f0a0-192">电子邮件项目的总数和大小，以及组织的部分索引电子邮件项目的比率 (计数和大小) 。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-192">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="3f0a0-193">列表错误标记以及发生错误的相应文件类型。</span><span class="sxs-lookup"><span data-stu-id="3f0a0-193">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3f0a0-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f0a0-194">See also</span></span>

[<span data-ttu-id="3f0a0-195">电子数据展示中的部分索引项</span><span class="sxs-lookup"><span data-stu-id="3f0a0-195">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)