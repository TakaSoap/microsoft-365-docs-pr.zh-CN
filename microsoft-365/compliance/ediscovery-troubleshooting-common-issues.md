---
title: 常见电子数据展示问题疑难解答
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解解决电子数据展示中常见问题Office 365步骤。
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 26ca41774e1e09619fdf5e518258f8acf3a9d938
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809115"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="ff939-103">调查、排查并解决常见的电子数据展示问题</span><span class="sxs-lookup"><span data-stu-id="ff939-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="ff939-104">本主题介绍为识别和解决在电子数据展示搜索过程中或电子数据展示过程中其他位置可能遇到的问题而可以执行的基本疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="ff939-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="ff939-105">解决其中某些方案需要 Microsoft 支持人员的帮助。</span><span class="sxs-lookup"><span data-stu-id="ff939-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="ff939-106">有关何时联系 Microsoft 支持的信息包含在解决方案步骤中。</span><span class="sxs-lookup"><span data-stu-id="ff939-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="ff939-107">错误/问题：位置不明确</span><span class="sxs-lookup"><span data-stu-id="ff939-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="ff939-108">如果您尝试添加要搜索的用户邮箱位置，并且 Exchange Online Protection (EOP) 目录中存在具有相同 userID 的重复或冲突对象，则会收到此错误 `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` ：。</span><span class="sxs-lookup"><span data-stu-id="ff939-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="ff939-109">解决方案</span><span class="sxs-lookup"><span data-stu-id="ff939-109">Resolution</span></span>

<span data-ttu-id="ff939-110">检查具有相同用户 ID 的重复用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="ff939-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="ff939-111">连接安全[与&中心 PowerShell。](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="ff939-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="ff939-112">运行以下命令以检索用户名的所有实例：</span><span class="sxs-lookup"><span data-stu-id="ff939-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="ff939-113">"useralias@contoso.com"的输出将类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="ff939-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="ff939-114">名称</span><span class="sxs-lookup"><span data-stu-id="ff939-114">Name</span></span>|<span data-ttu-id="ff939-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="ff939-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="ff939-116">别名、用户</span><span class="sxs-lookup"><span data-stu-id="ff939-116">Alias, User</span></span>|<span data-ttu-id="ff939-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="ff939-117">MailUser</span></span>|
   > |<span data-ttu-id="ff939-118">别名、用户</span><span class="sxs-lookup"><span data-stu-id="ff939-118">Alias, User</span></span>|<span data-ttu-id="ff939-119">用户</span><span class="sxs-lookup"><span data-stu-id="ff939-119">User</span></span>|

3. <span data-ttu-id="ff939-120">如果返回多个用户，请找到并修复冲突对象。</span><span class="sxs-lookup"><span data-stu-id="ff939-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="ff939-121">错误/问题：搜索特定位置失败</span><span class="sxs-lookup"><span data-stu-id="ff939-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="ff939-122">电子数据展示或内容搜索可能会生成以下错误： `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="ff939-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![搜索特定位置失败错误屏幕截图](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="ff939-124">解决方案</span><span class="sxs-lookup"><span data-stu-id="ff939-124">Resolution</span></span>

<span data-ttu-id="ff939-125">如果您收到此错误，我们建议您验证搜索失败的位置，然后仅在失败的位置重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="ff939-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="ff939-126">连接安全&[合规中心 PowerShell，](/powershell/exchange/connect-to-scc-powershell)然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ff939-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="ff939-127">从 PowerShell 输出中，从搜索输出中查看错误字段中的失败位置或错误的状态详细信息。</span><span class="sxs-lookup"><span data-stu-id="ff939-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="ff939-128">仅对失败的位置重试电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="ff939-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="ff939-129">如果继续收到这些错误，请参阅重试失败 [位置](/Office365/SecurityCompliance/retry-failed-content-search) 了解更多疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="ff939-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="ff939-130">错误/问题：未找到文件</span><span class="sxs-lookup"><span data-stu-id="ff939-130">Error/issue: File not found</span></span>

<span data-ttu-id="ff939-131">当运行包括 SharePoint Online 和 One Drive For Business 位置的电子数据展示搜索时，你可能会收到错误，尽管该文件 `File Not Found` 位于网站上。</span><span class="sxs-lookup"><span data-stu-id="ff939-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="ff939-132">此错误将位于导出警告中，errors.csv或跳过items.csv。</span><span class="sxs-lookup"><span data-stu-id="ff939-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="ff939-133">如果网站上找不到该文件或索引已过期，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="ff939-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="ff939-134">下面是实际错误的文本，其中 (强调) 。</span><span class="sxs-lookup"><span data-stu-id="ff939-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="ff939-135">28.06.2019 10：02：19_FailedToExportItem_Failed下载内容。</span><span class="sxs-lookup"><span data-stu-id="ff939-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="ff939-136">其他诊断信息：Microsoft。Office。Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure：无法从类型为 Document 的内容 6ea52149-91cd-4965-b5bb-82ca6a3ec9be 下载。</span><span class="sxs-lookup"><span data-stu-id="ff939-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="ff939-137">相关 ID：3bd84722-937b-4c23-b61b-08d6fba9ec32。</span><span class="sxs-lookup"><span data-stu-id="ff939-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="ff939-138">ServerErrorCode：-2147024894 ---> Microsoft。SharePoint。Client.ServerException：***未找到文件***。</span><span class="sxs-lookup"><span data-stu-id="ff939-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="ff939-139">位于 Microsoft。SharePoint。Client.ClientRequest.ProcessResponseStream (Microsoft) Stream responseStream。SharePoint。Client.ClientRequest.ProcessResponse () ---内部异常堆栈跟踪结束---</span><span class="sxs-lookup"><span data-stu-id="ff939-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="ff939-140">解决方案</span><span class="sxs-lookup"><span data-stu-id="ff939-140">Resolution</span></span>

1. <span data-ttu-id="ff939-141">检查搜索中标识的位置，以确保文件的位置正确无误，并添加到搜索位置。</span><span class="sxs-lookup"><span data-stu-id="ff939-141">Check location identified in the search to ensure that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="ff939-142">使用 [Manually request crawling and re-indexing of a site， a library， or a list](/sharepoint/crawl-site-content) 中的过程对网站重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="ff939-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a><span data-ttu-id="ff939-143">错误/问题：此文件未导出，因为它不再存在。</span><span class="sxs-lookup"><span data-stu-id="ff939-143">Error/issue: This file wasn't exported because it doesn't exist anymore.</span></span> <span data-ttu-id="ff939-144">该文件包含在估计的搜索结果计数中，因为它仍在索引中列出。</span><span class="sxs-lookup"><span data-stu-id="ff939-144">The file was included in the count of estimated search results because it's still listed in the index.</span></span> <span data-ttu-id="ff939-145">文件最终将从索引中删除，并且将来不会引发错误。</span><span class="sxs-lookup"><span data-stu-id="ff939-145">The file will eventually be removed from the index, and won't cause an error in the future.</span></span>

<span data-ttu-id="ff939-146">运行包括"联机"和"One Drive for Business"SharePoint电子数据展示搜索时可能会看到该错误。</span><span class="sxs-lookup"><span data-stu-id="ff939-146">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="ff939-147">电子数据展示依赖 SPO 索引来标识文件位置。</span><span class="sxs-lookup"><span data-stu-id="ff939-147">eDiscovery relies on teh SPO index to identify the file locations.</span></span> <span data-ttu-id="ff939-148">如果文件已删除，但 SPO 索引尚未更新，则可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="ff939-148">If the file was deleted but the SPO index was not yet updated this error may occur.</span></span>

### <a name="resolution"></a><span data-ttu-id="ff939-149">解决方案</span><span class="sxs-lookup"><span data-stu-id="ff939-149">Resolution</span></span> 
<span data-ttu-id="ff939-150">打开 SPO 位置并验证此文件是否确实不存在。</span><span class="sxs-lookup"><span data-stu-id="ff939-150">Open the SPO location and verify that this file indeed is not there.</span></span>
<span data-ttu-id="ff939-151">建议的解决方案是手动对网站重新索引，或等到自动后台进程对网站重新索引。</span><span class="sxs-lookup"><span data-stu-id="ff939-151">Suggested solution is to manually reindex the site, or wait till the site reindexes by the automatic background process.</span></span>


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artefact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a><span data-ttu-id="ff939-152">错误/问题：此搜索结果未下载，因为此搜索结果是一个无法自行下载的文件夹或其他项目，将下载文件夹或库内的任何项目。</span><span class="sxs-lookup"><span data-stu-id="ff939-152">Error/issue: This search result was not downloaded as it is a folder or other artefact that can't be downloaded by itself, any items inside the folder or library will be downloaded.</span></span>

<span data-ttu-id="ff939-153">运行包括"联机"和"One Drive for Business"SharePoint电子数据展示搜索时可能会看到该错误。</span><span class="sxs-lookup"><span data-stu-id="ff939-153">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="ff939-154">这意味着我们将尝试导出索引中报告的项目，但它却变成一个文件夹，因此我们没有导出它。</span><span class="sxs-lookup"><span data-stu-id="ff939-154">It means that we were going to try and export the item reported in the index, but it turned out to be a folder so we did not export it.</span></span> <span data-ttu-id="ff939-155">如错误所述，我们不会导出文件夹项目，但会导出其内容。</span><span class="sxs-lookup"><span data-stu-id="ff939-155">As mentioned in the error, we don't export folder items but we do export their contents.</span></span>


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="ff939-156">错误/问题：搜索失败，因为未找到收件人</span><span class="sxs-lookup"><span data-stu-id="ff939-156">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="ff939-157">电子数据展示搜索失败，出现错误 `recipient not found` 。</span><span class="sxs-lookup"><span data-stu-id="ff939-157">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="ff939-158">如果在 EOP 服务器中找不到用户对象，则Exchange Online Protection (，) 对象尚未同步。</span><span class="sxs-lookup"><span data-stu-id="ff939-158">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="ff939-159">解决方案</span><span class="sxs-lookup"><span data-stu-id="ff939-159">Resolution</span></span>

1. <span data-ttu-id="ff939-160">连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ff939-160">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ff939-161">运行以下命令，检查用户是否同步到Exchange Online Protection：</span><span class="sxs-lookup"><span data-stu-id="ff939-161">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="ff939-162">应存在用户问题的邮件用户对象。</span><span class="sxs-lookup"><span data-stu-id="ff939-162">There should be a mail user object for the user question.</span></span> <span data-ttu-id="ff939-163">如果未返回任何值，请调查用户对象。</span><span class="sxs-lookup"><span data-stu-id="ff939-163">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="ff939-164">如果对象无法同步，请与 Microsoft 支持部门联系。</span><span class="sxs-lookup"><span data-stu-id="ff939-164">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="ff939-165">错误/问题：导出搜索结果的速度很慢</span><span class="sxs-lookup"><span data-stu-id="ff939-165">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="ff939-166">在安全与合规中心内从电子数据展示或内容搜索导出搜索结果时，下载时间超过预期。</span><span class="sxs-lookup"><span data-stu-id="ff939-166">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="ff939-167">你可以查看要下载的数据量，并可能提高导出速度。</span><span class="sxs-lookup"><span data-stu-id="ff939-167">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="ff939-168">解决方案</span><span class="sxs-lookup"><span data-stu-id="ff939-168">Resolution</span></span>

1. <span data-ttu-id="ff939-169">连接安全&[合规中心 PowerShell，](/powershell/exchange/connect-to-scc-powershell)然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ff939-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="ff939-170">在 SearchResults 和 SearchStatistics 参数中查找要下载的数据量。</span><span class="sxs-lookup"><span data-stu-id="ff939-170">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="ff939-171">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ff939-171">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="ff939-172">在结果字段中，查找已导出的数据并查看遇到的任何错误。</span><span class="sxs-lookup"><span data-stu-id="ff939-172">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="ff939-173">检查位于日志文件的目录中的 trace.日志文件，了解是否有错误。</span><span class="sxs-lookup"><span data-stu-id="ff939-173">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="ff939-174">如果仍有问题，请考虑将返回大量结果的搜索划分为较小的搜索。</span><span class="sxs-lookup"><span data-stu-id="ff939-174">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="ff939-175">例如，您可以使用搜索查询中的日期范围返回一组较小的结果，可以更快地下载结果。</span><span class="sxs-lookup"><span data-stu-id="ff939-175">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="ff939-176">错误/问题："发生了 500 (内部) 错误"</span><span class="sxs-lookup"><span data-stu-id="ff939-176">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="ff939-177">在运行电子数据展示搜索时，如果搜索不断失败，出现错误类似于"发生内部服务器错误 (500) "，可能需要仅在特定邮箱位置重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="ff939-177">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![内部服务器错误 500 屏幕截图](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="ff939-179">解决方案</span><span class="sxs-lookup"><span data-stu-id="ff939-179">Resolution</span></span>

1. <span data-ttu-id="ff939-180">将搜索分解为较小的搜索，然后再次运行搜索。</span><span class="sxs-lookup"><span data-stu-id="ff939-180">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="ff939-181">请尝试使用较小的日期范围或限制要搜索的位置数。</span><span class="sxs-lookup"><span data-stu-id="ff939-181">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="ff939-182">连接安全&[合规中心 PowerShell，](/powershell/exchange/connect-to-scc-powershell)然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ff939-182">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="ff939-183">检查结果和错误的输出。</span><span class="sxs-lookup"><span data-stu-id="ff939-183">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="ff939-184">检查 trace.日志文件。</span><span class="sxs-lookup"><span data-stu-id="ff939-184">Examine the trace.log file.</span></span> <span data-ttu-id="ff939-185">它位于将搜索结果导出到的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ff939-185">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="ff939-186">与 Microsoft 技术支持联系。</span><span class="sxs-lookup"><span data-stu-id="ff939-186">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="ff939-187">错误/问题：保留未同步</span><span class="sxs-lookup"><span data-stu-id="ff939-187">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="ff939-188">电子数据展示案例保留策略同步分发错误。</span><span class="sxs-lookup"><span data-stu-id="ff939-188">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="ff939-189">错误显示为：</span><span class="sxs-lookup"><span data-stu-id="ff939-189">The error reads:</span></span>

> <span data-ttu-id="ff939-190">"资源：部署策略所花时间超过预期。</span><span class="sxs-lookup"><span data-stu-id="ff939-190">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="ff939-191">更新最终部署状态可能需要另外 2 个小时，因此请在几小时后重新检查。"</span><span class="sxs-lookup"><span data-stu-id="ff939-191">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="ff939-192">解决方案</span><span class="sxs-lookup"><span data-stu-id="ff939-192">Resolution</span></span>

1. <span data-ttu-id="ff939-193">连接安全&合规中心[PowerShell，](/powershell/exchange/connect-to-scc-powershell)然后运行以下针对电子数据展示案例保留的命令：</span><span class="sxs-lookup"><span data-stu-id="ff939-193">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="ff939-194">对于保留策略，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ff939-194">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="ff939-195">检查 DistributionDetail 参数中的值，了解错误，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ff939-195">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="ff939-196">错误：资源：部署策略所花时间超过预期。</span><span class="sxs-lookup"><span data-stu-id="ff939-196">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="ff939-197">更新最终部署状态可能需要另外 2 个小时，因此请在几小时后重新检查。"</span><span class="sxs-lookup"><span data-stu-id="ff939-197">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="ff939-198">尝试对问题策略运行 RetryDistribution 参数：</span><span class="sxs-lookup"><span data-stu-id="ff939-198">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="ff939-199">对于电子数据展示案例保留：</span><span class="sxs-lookup"><span data-stu-id="ff939-199">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="ff939-200">对于保留策略：</span><span class="sxs-lookup"><span data-stu-id="ff939-200">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="ff939-201">与 Microsoft 技术支持联系。</span><span class="sxs-lookup"><span data-stu-id="ff939-201">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="ff939-202">错误："不满足使用 HTTP (标头) 条件"</span><span class="sxs-lookup"><span data-stu-id="ff939-202">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="ff939-203">使用电子数据展示导出工具下载搜索结果时，您可能会收到以下错误：这是暂时性错误，通常发生在 Azure 存储 `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 位置。</span><span class="sxs-lookup"><span data-stu-id="ff939-203">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="ff939-204">解决方案</span><span class="sxs-lookup"><span data-stu-id="ff939-204">Resolution</span></span>

<span data-ttu-id="ff939-205">若要解决此问题，请 [重试下载搜索结果](export-search-results.md#step-2-download-the-search-results)，这将重新启动电子数据展示导出工具。</span><span class="sxs-lookup"><span data-stu-id="ff939-205">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="ff939-206">错误/问题：已下载的导出未显示任何结果</span><span class="sxs-lookup"><span data-stu-id="ff939-206">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="ff939-207">成功导出后，通过导出工具完成的下载将在结果中显示零文件。</span><span class="sxs-lookup"><span data-stu-id="ff939-207">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="ff939-208">解决方案</span><span class="sxs-lookup"><span data-stu-id="ff939-208">Resolution</span></span>

<span data-ttu-id="ff939-209">这是一个客户端问题，为了修正此问题，请尝试以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ff939-209">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="ff939-210">请尝试使用另一个客户端/计算机进行下载。</span><span class="sxs-lookup"><span data-stu-id="ff939-210">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="ff939-211">使用 [Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch] cmdlet 删除不再需要的旧搜索。</span><span class="sxs-lookup"><span data-stu-id="ff939-211">Remove old searches that are no longer needed using [Remove-ComplianceSearch][/powershell/module/exchange/remove-compliancesearch] cmdlet.</span></span>

3. <span data-ttu-id="ff939-212">确保下载到本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="ff939-212">Make sure to download to a local drive.</span></span>

4. <span data-ttu-id="ff939-213">确保病毒扫描程序未运行。</span><span class="sxs-lookup"><span data-stu-id="ff939-213">Make sure the virus scanner is not running.</span></span>

5. <span data-ttu-id="ff939-214">确保没有任何其他导出内容下载到同一文件夹或任何父文件夹。</span><span class="sxs-lookup"><span data-stu-id="ff939-214">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

6. <span data-ttu-id="ff939-215">如果上述步骤不起作用，则禁用压缩和重复数据删除。</span><span class="sxs-lookup"><span data-stu-id="ff939-215">If the previous steps did not work, disable zipping and de-duplication.</span></span>

7. <span data-ttu-id="ff939-216">如果此操作有效，则问题由本地病毒扫描程序或磁盘问题导致。</span><span class="sxs-lookup"><span data-stu-id="ff939-216">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
