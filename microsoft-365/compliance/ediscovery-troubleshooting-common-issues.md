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
description: 了解解决 Office 365 电子数据展示中的常见问题时可以执行的基本疑难解答步骤。
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a867ed2e55c73fe4bbd890273d78cf57f4bfbd2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926542"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="5ace2-103">调查、排查并解决常见的电子数据展示问题</span><span class="sxs-lookup"><span data-stu-id="5ace2-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="5ace2-104">本主题介绍为识别和解决在电子数据展示搜索过程中或电子数据展示过程中其他位置可能遇到的问题而可以执行的基本疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="5ace2-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="5ace2-105">解决其中某些方案需要 Microsoft 支持人员的帮助。</span><span class="sxs-lookup"><span data-stu-id="5ace2-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="5ace2-106">有关何时联系 Microsoft 支持的信息包含在解决方案步骤中。</span><span class="sxs-lookup"><span data-stu-id="5ace2-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="5ace2-107">错误/问题：位置不明确</span><span class="sxs-lookup"><span data-stu-id="5ace2-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="5ace2-108">如果您尝试添加要搜索的用户邮箱位置，并且 Exchange Online Protection (EOP) 目录中存在具有相同 userID 的重复或冲突对象，则会收到此错误 `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` ：。</span><span class="sxs-lookup"><span data-stu-id="5ace2-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="5ace2-109">解决方案</span><span class="sxs-lookup"><span data-stu-id="5ace2-109">Resolution</span></span>

<span data-ttu-id="5ace2-110">检查具有相同用户 ID 的重复用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="5ace2-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="5ace2-111">连接到安全[&合规中心 PowerShell。](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="5ace2-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="5ace2-112">运行以下命令以检索用户名的所有实例：</span><span class="sxs-lookup"><span data-stu-id="5ace2-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="5ace2-113">"useralias@contoso.com"的输出将类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="5ace2-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="5ace2-114">名称</span><span class="sxs-lookup"><span data-stu-id="5ace2-114">Name</span></span>|<span data-ttu-id="5ace2-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="5ace2-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="5ace2-116">别名、用户</span><span class="sxs-lookup"><span data-stu-id="5ace2-116">Alias, User</span></span>|<span data-ttu-id="5ace2-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="5ace2-117">MailUser</span></span>|
   > |<span data-ttu-id="5ace2-118">别名、用户</span><span class="sxs-lookup"><span data-stu-id="5ace2-118">Alias, User</span></span>|<span data-ttu-id="5ace2-119">User</span><span class="sxs-lookup"><span data-stu-id="5ace2-119">User</span></span>|

3. <span data-ttu-id="5ace2-120">如果返回多个用户，请找到并修复冲突对象。</span><span class="sxs-lookup"><span data-stu-id="5ace2-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="5ace2-121">错误/问题：搜索特定位置失败</span><span class="sxs-lookup"><span data-stu-id="5ace2-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="5ace2-122">电子数据展示或内容搜索可能会生成以下错误： `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="5ace2-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![搜索特定位置失败错误屏幕截图](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="5ace2-124">解决方案</span><span class="sxs-lookup"><span data-stu-id="5ace2-124">Resolution</span></span>

<span data-ttu-id="5ace2-125">如果您收到此错误，我们建议您验证搜索失败的位置，然后仅在失败的位置重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="5ace2-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="5ace2-126">连接到 [安全&合规中心 PowerShell，](/powershell/exchange/connect-to-scc-powershell) 然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5ace2-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="5ace2-127">从 PowerShell 输出中，从搜索输出中查看错误字段中的失败位置或错误的状态详细信息。</span><span class="sxs-lookup"><span data-stu-id="5ace2-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="5ace2-128">仅对失败的位置重试电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="5ace2-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="5ace2-129">如果继续收到这些错误，请参阅重试失败 [位置](/Office365/SecurityCompliance/retry-failed-content-search) 了解更多疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="5ace2-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="5ace2-130">错误/问题：未找到文件</span><span class="sxs-lookup"><span data-stu-id="5ace2-130">Error/issue: File not found</span></span>

<span data-ttu-id="5ace2-131">运行包括 SharePoint Online 和 One Drive For Business 位置的电子数据展示搜索时，您可能会收到错误，尽管该文件 `File Not Found` 位于网站上。</span><span class="sxs-lookup"><span data-stu-id="5ace2-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="5ace2-132">此错误将位于导出警告中，errors.csv或跳过items.csv。</span><span class="sxs-lookup"><span data-stu-id="5ace2-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="5ace2-133">如果网站上找不到该文件或索引已过期，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="5ace2-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="5ace2-134">下面是实际错误的文本，其中 (强调) 。</span><span class="sxs-lookup"><span data-stu-id="5ace2-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="5ace2-135">28.06.2019 10：02：19_FailedToExportItem_Failed下载内容。</span><span class="sxs-lookup"><span data-stu-id="5ace2-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="5ace2-136">其他诊断信息：Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure：无法从类型为 Document 的内容 6ea52149-91cd-4965-b5bb-82ca6a3ec9be 下载。</span><span class="sxs-lookup"><span data-stu-id="5ace2-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="5ace2-137">相关 ID：3bd84722-937b-4c23-b61b-08d6fba9ec32。</span><span class="sxs-lookup"><span data-stu-id="5ace2-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="5ace2-138">ServerErrorCode：-2147024894 ---> Microsoft.SharePoint.Client.ServerException： ***未找到文件***。</span><span class="sxs-lookup"><span data-stu-id="5ace2-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="5ace2-139">位于 Microsoft.SharePoint.Client.ClientRequest.ProcessResponse (Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse () --- End of inner exception stack trace ---</span><span class="sxs-lookup"><span data-stu-id="5ace2-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="5ace2-140">解决方案</span><span class="sxs-lookup"><span data-stu-id="5ace2-140">Resolution</span></span>

1. <span data-ttu-id="5ace2-141">检查搜索中标识的位置，以确保文件的位置正确无误，并添加到搜索位置。</span><span class="sxs-lookup"><span data-stu-id="5ace2-141">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="5ace2-142">使用 [Manually request crawling and re-indexing of a site， a library， or a list](/sharepoint/crawl-site-content) 中的过程对网站重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="5ace2-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="5ace2-143">错误/问题：搜索失败，因为未找到收件人</span><span class="sxs-lookup"><span data-stu-id="5ace2-143">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="5ace2-144">电子数据展示搜索失败，出现错误 `recipient not found` 。</span><span class="sxs-lookup"><span data-stu-id="5ace2-144">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="5ace2-145">如果由于用户对象尚未同步，在 Exchange Online Protection (EOP) 可能发生此错误。</span><span class="sxs-lookup"><span data-stu-id="5ace2-145">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="5ace2-146">解决方案</span><span class="sxs-lookup"><span data-stu-id="5ace2-146">Resolution</span></span>

1. <span data-ttu-id="5ace2-147">连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5ace2-147">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="5ace2-148">运行以下命令检查用户是否同步到 Exchange Online Protection：</span><span class="sxs-lookup"><span data-stu-id="5ace2-148">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="5ace2-149">应存在用户问题的邮件用户对象。</span><span class="sxs-lookup"><span data-stu-id="5ace2-149">There should be a mail user object for the user question.</span></span> <span data-ttu-id="5ace2-150">如果未返回任何值，请调查用户对象。</span><span class="sxs-lookup"><span data-stu-id="5ace2-150">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="5ace2-151">如果对象无法同步，请与 Microsoft 支持部门联系。</span><span class="sxs-lookup"><span data-stu-id="5ace2-151">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="5ace2-152">错误/问题：导出搜索结果的速度很慢</span><span class="sxs-lookup"><span data-stu-id="5ace2-152">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="5ace2-153">在安全与合规中心内从电子数据展示或内容搜索导出搜索结果时，下载时间超过预期。</span><span class="sxs-lookup"><span data-stu-id="5ace2-153">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="5ace2-154">你可以查看要下载的数据量，并可能提高导出速度。</span><span class="sxs-lookup"><span data-stu-id="5ace2-154">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="5ace2-155">解决方案</span><span class="sxs-lookup"><span data-stu-id="5ace2-155">Resolution</span></span>

1. <span data-ttu-id="5ace2-156">连接到 [安全&合规中心 PowerShell，](/powershell/exchange/connect-to-scc-powershell) 然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5ace2-156">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="5ace2-157">在 SearchResults 和 SearchStatistics 参数中查找要下载的数据量。</span><span class="sxs-lookup"><span data-stu-id="5ace2-157">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="5ace2-158">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5ace2-158">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="5ace2-159">在结果字段中，查找已导出的数据并查看遇到的任何错误。</span><span class="sxs-lookup"><span data-stu-id="5ace2-159">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="5ace2-160">检查位于日志文件的目录中的 trace.日志文件，了解是否有错误。</span><span class="sxs-lookup"><span data-stu-id="5ace2-160">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="5ace2-161">如果仍有问题，请考虑将返回大量结果的搜索划分为较小的搜索。</span><span class="sxs-lookup"><span data-stu-id="5ace2-161">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="5ace2-162">例如，您可以使用搜索查询中的日期范围返回一组较小的结果，可以更快地下载结果。</span><span class="sxs-lookup"><span data-stu-id="5ace2-162">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="5ace2-163">错误/问题："发生了 500 (内部) 错误"</span><span class="sxs-lookup"><span data-stu-id="5ace2-163">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="5ace2-164">在运行电子数据展示搜索时，如果搜索不断失败，出现错误类似于"发生内部服务器错误 (500) "，可能需要仅在特定邮箱位置重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="5ace2-164">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![内部服务器错误 500 屏幕截图](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="5ace2-166">解决方案</span><span class="sxs-lookup"><span data-stu-id="5ace2-166">Resolution</span></span>

1. <span data-ttu-id="5ace2-167">将搜索分解为较小的搜索，然后再次运行搜索。</span><span class="sxs-lookup"><span data-stu-id="5ace2-167">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="5ace2-168">请尝试使用较小的日期范围或限制要搜索的位置数。</span><span class="sxs-lookup"><span data-stu-id="5ace2-168">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="5ace2-169">连接到 [安全&合规中心 PowerShell，](/powershell/exchange/connect-to-scc-powershell) 然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5ace2-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="5ace2-170">检查结果和错误的输出。</span><span class="sxs-lookup"><span data-stu-id="5ace2-170">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="5ace2-171">检查 trace.日志文件。</span><span class="sxs-lookup"><span data-stu-id="5ace2-171">Examine the trace.log file.</span></span> <span data-ttu-id="5ace2-172">它位于将搜索结果导出到的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5ace2-172">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="5ace2-173">与 Microsoft 技术支持联系。</span><span class="sxs-lookup"><span data-stu-id="5ace2-173">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="5ace2-174">错误/问题：保留未同步</span><span class="sxs-lookup"><span data-stu-id="5ace2-174">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="5ace2-175">电子数据展示案例保留策略同步分发错误。</span><span class="sxs-lookup"><span data-stu-id="5ace2-175">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="5ace2-176">错误显示为：</span><span class="sxs-lookup"><span data-stu-id="5ace2-176">The error reads:</span></span>

> <span data-ttu-id="5ace2-177">"资源：部署策略所花时间超过预期。</span><span class="sxs-lookup"><span data-stu-id="5ace2-177">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="5ace2-178">更新最终部署状态可能需要另外 2 个小时，因此请在几小时后重新检查。"</span><span class="sxs-lookup"><span data-stu-id="5ace2-178">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="5ace2-179">解决方案</span><span class="sxs-lookup"><span data-stu-id="5ace2-179">Resolution</span></span>

1. <span data-ttu-id="5ace2-180">连接到 [安全&合规中心 PowerShell，](/powershell/exchange/connect-to-scc-powershell) 然后针对电子数据展示案例保留运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5ace2-180">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="5ace2-181">对于保留策略，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5ace2-181">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="5ace2-182">检查 DistributionDetail 参数中的值，了解错误，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ace2-182">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="5ace2-183">错误：资源：部署策略所花时间超过预期。</span><span class="sxs-lookup"><span data-stu-id="5ace2-183">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="5ace2-184">更新最终部署状态可能需要另外 2 个小时，因此请在几小时后重新检查。"</span><span class="sxs-lookup"><span data-stu-id="5ace2-184">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="5ace2-185">尝试对问题策略运行 RetryDistribution 参数：</span><span class="sxs-lookup"><span data-stu-id="5ace2-185">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="5ace2-186">对于电子数据展示案例保留：</span><span class="sxs-lookup"><span data-stu-id="5ace2-186">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="5ace2-187">对于保留策略：</span><span class="sxs-lookup"><span data-stu-id="5ace2-187">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="5ace2-188">与 Microsoft 技术支持联系。</span><span class="sxs-lookup"><span data-stu-id="5ace2-188">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="5ace2-189">错误："不满足使用 HTTP (标头) 条件"</span><span class="sxs-lookup"><span data-stu-id="5ace2-189">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="5ace2-190">使用电子数据展示导出工具下载搜索结果时，可能会收到以下错误：这是暂时性错误，通常发生在 Azure 存储 `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 位置。</span><span class="sxs-lookup"><span data-stu-id="5ace2-190">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="5ace2-191">解决方案</span><span class="sxs-lookup"><span data-stu-id="5ace2-191">Resolution</span></span>

<span data-ttu-id="5ace2-192">若要解决此问题，请 [重试下载搜索结果](export-search-results.md#step-2-download-the-search-results)，这将重新启动电子数据展示导出工具。</span><span class="sxs-lookup"><span data-stu-id="5ace2-192">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="5ace2-193">错误/问题：已下载的导出未显示任何结果</span><span class="sxs-lookup"><span data-stu-id="5ace2-193">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="5ace2-194">成功导出后，通过导出工具完成的下载将在结果中显示零文件。</span><span class="sxs-lookup"><span data-stu-id="5ace2-194">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="5ace2-195">解决方案</span><span class="sxs-lookup"><span data-stu-id="5ace2-195">Resolution</span></span>

<span data-ttu-id="5ace2-196">这是一个客户端问题，为了修正此问题，请尝试以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5ace2-196">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="5ace2-197">请尝试使用另一个客户端/计算机进行下载。</span><span class="sxs-lookup"><span data-stu-id="5ace2-197">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="5ace2-198">确保下载到本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="5ace2-198">Make sure to download to a local drive.</span></span>

3. <span data-ttu-id="5ace2-199">确保病毒扫描程序未运行。</span><span class="sxs-lookup"><span data-stu-id="5ace2-199">Make sure the virus scanner is not running.</span></span>

4. <span data-ttu-id="5ace2-200">确保没有任何其他导出内容下载到同一文件夹或任何父文件夹。</span><span class="sxs-lookup"><span data-stu-id="5ace2-200">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

5. <span data-ttu-id="5ace2-201">如果上述步骤不起作用，则禁用压缩和重复数据删除。</span><span class="sxs-lookup"><span data-stu-id="5ace2-201">If the previous steps did not work, disable zipping and de-duplication.</span></span>

6. <span data-ttu-id="5ace2-202">如果此操作有效，则问题由本地病毒扫描程序或磁盘问题导致。</span><span class="sxs-lookup"><span data-stu-id="5ace2-202">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>