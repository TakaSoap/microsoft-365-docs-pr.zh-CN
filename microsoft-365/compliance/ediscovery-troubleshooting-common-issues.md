---
title: Troublshooting 常见的电子数据展示问题
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 调查、解决 Office 365 电子数据展示中的常见问题并解决这些问题。
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207286"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="db437-103">调查、解决和解决常见的电子数据展示问题</span><span class="sxs-lookup"><span data-stu-id="db437-103">Investigate, troubleshoot and resolve common eDiscovery issues</span></span>

<span data-ttu-id="db437-104">本主题介绍了可用于识别和解决电子数据展示搜索或电子数据展示过程中其他位置可能遇到的问题的基本故障排除步骤。</span><span class="sxs-lookup"><span data-stu-id="db437-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="db437-105">解决其中一些方案需要客户支持服务（CSS）方面的帮助。</span><span class="sxs-lookup"><span data-stu-id="db437-105">Resolving some of these scenarios requires help from Customer Support Services (CSS).</span></span> <span data-ttu-id="db437-106">有关何时联系 CSS 的信息包含在解决步骤中。</span><span class="sxs-lookup"><span data-stu-id="db437-106">Information on when to contact CSS is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="db437-107">错误/问题位置不明确</span><span class="sxs-lookup"><span data-stu-id="db437-107">Error/issue ambiguous location</span></span>

<span data-ttu-id="db437-108">如果您尝试将用户的邮箱位置添加到搜索，并且 Exchange `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` Online PROTECTION （EOP）中存在具有相同用户 id 的重复或冲突对象，则会收到此错误 "合规性搜索" 将包含以下无效位置。文件夹.</span><span class="sxs-lookup"><span data-stu-id="db437-108">You'll receive this error "The compliance search contains the following invalid location `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` if you tried to add user’s mailbox location to search and there are duplicate or conflicting objects with the same user id in the Exchange Online Protection (EOP) directory.</span></span>

### <a name="resolution"></a><span data-ttu-id="db437-109">分辨率</span><span class="sxs-lookup"><span data-stu-id="db437-109">Resolution</span></span>

<span data-ttu-id="db437-110">检查是否存在具有相同用户 ID 的重复用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="db437-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="db437-111">连接到 [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="db437-111">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="db437-112">检索用户名的所有实例，请键入：</span><span class="sxs-lookup"><span data-stu-id="db437-112">Retrieve all instances of the username, type:</span></span>

```powershell
Get-Recipient <username>
```

<span data-ttu-id="db437-113">"Useralias@contoso.com" 的输出可能是</span><span class="sxs-lookup"><span data-stu-id="db437-113">The output for 'useralias@contoso.com' might be</span></span>

> 
> |<span data-ttu-id="db437-114">Name</span><span class="sxs-lookup"><span data-stu-id="db437-114">Name</span></span>  |<span data-ttu-id="db437-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="db437-115">RecipientType</span></span>  |
> |---------|---------|
> |<span data-ttu-id="db437-116">别名、用户</span><span class="sxs-lookup"><span data-stu-id="db437-116">Alias, User</span></span>     |<span data-ttu-id="db437-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="db437-117">MailUser</span></span>         |
> |<span data-ttu-id="db437-118">别名、用户</span><span class="sxs-lookup"><span data-stu-id="db437-118">Alias, User</span></span>     |<span data-ttu-id="db437-119">用户</span><span class="sxs-lookup"><span data-stu-id="db437-119">User</span></span>         |

3. <span data-ttu-id="db437-120">如果返回多个用户，请找到并修复冲突的对象。</span><span class="sxs-lookup"><span data-stu-id="db437-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="db437-121">错误/问题搜索在特定位置失败</span><span class="sxs-lookup"><span data-stu-id="db437-121">Error/issue search fails on specific locations</span></span>

<span data-ttu-id="db437-122">电子数据展示或内容搜索可能会产生以下错误：</span><span class="sxs-lookup"><span data-stu-id="db437-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="db437-123">此搜索已完成（#）错误。</span><span class="sxs-lookup"><span data-stu-id="db437-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="db437-124">是否要对失败的位置重试搜索？</span><span class="sxs-lookup"><span data-stu-id="db437-124">Would you like to retry the search on the failed locations?</span></span>

![搜索特定位置发生错误屏幕截图]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="db437-126">分辨率</span><span class="sxs-lookup"><span data-stu-id="db437-126">Resolution</span></span>

<span data-ttu-id="db437-127">如果您收到此错误，我们建议您验证在搜索中失败的位置，然后仅在出现故障的位置上重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="db437-127">If you receive this error, we recommend that you verify the locations that failed in the search  then re-run the search only on the failed locations.</span></span>

1. <span data-ttu-id="db437-128">连接到[Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="db437-128">Connect to [Exchange Online Protection Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="db437-129">类型：</span><span class="sxs-lookup"><span data-stu-id="db437-129">Type:</span></span>

```powershell
Get-Compliancesearch searchname|fl 
```

3. <span data-ttu-id="db437-130">从 PowerShell 输出中，查看 "错误" 字段中的失败位置或从搜索输出中的错误的状态详细信息。</span><span class="sxs-lookup"><span data-stu-id="db437-130">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>
1. <span data-ttu-id="db437-131">仅重试失败位置上的电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="db437-131">Retry the eDiscovery search on the failed locations only.</span></span>
1. <span data-ttu-id="db437-132">如果继续收到这些错误，请参阅[重试失败的位置](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search)以了解其他故障排除步骤。</span><span class="sxs-lookup"><span data-stu-id="db437-132">If you continue to receive these error, see [Retry failed locations](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search) for additional troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="db437-133">找不到错误/问题文件</span><span class="sxs-lookup"><span data-stu-id="db437-133">Error/issue file not found</span></span>

<span data-ttu-id="db437-134">在运行包含 SharePoint Online 的电子数据展示搜索和一个驱动器用于商业位置时，您可能会`File Not Found`收到错误，尽管文件位于网站上。</span><span class="sxs-lookup"><span data-stu-id="db437-134">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="db437-135">此错误将出现在导出警告和错误中。 csv 或已跳过的项目。如果文件无法位于网站上或索引已过期，则可能会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="db437-135">This error will be in the export warnings and errors.csv or skipped items.csv  This may occur if the file cannot be located on the site or the index is out of date.</span></span> <span data-ttu-id="db437-136">下面是一个实际错误的文本，其中添加了强调。</span><span class="sxs-lookup"><span data-stu-id="db437-136">Here's the text of an actual error, with emphasis added.</span></span>
  
> <span data-ttu-id="db437-137">28.06.2019 10：02：19_FailedToExportItem_Failed 下载内容。</span><span class="sxs-lookup"><span data-stu-id="db437-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="db437-138">其他诊断信息： ExportWorker：无法从内容 6ea52149-91cd 4965-b5bb-82ca6a3ec9be--到类型文档的。</span><span class="sxs-lookup"><span data-stu-id="db437-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="db437-139">相关 Id：3bd84722-937b-4c23-b61b-08d6fba9ec32。</span><span class="sxs-lookup"><span data-stu-id="db437-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="db437-140">ServerErrorCode：-2147024894--->***找不到***ServerException： File。</span><span class="sxs-lookup"><span data-stu-id="db437-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="db437-141">在 ClientRequest （Stream responseStream）处的 ProcessResponseStream （Stream）---内部异常堆栈跟踪的结束日期的---</span><span class="sxs-lookup"><span data-stu-id="db437-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="db437-142">分辨率</span><span class="sxs-lookup"><span data-stu-id="db437-142">Resolution</span></span>

1. <span data-ttu-id="db437-143">检查搜索中标识的位置，以确保文件的位置正确，并将其添加到搜索位置中。</span><span class="sxs-lookup"><span data-stu-id="db437-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>
2. <span data-ttu-id="db437-144">在[手动请求对网站、库或列表重新编制索引网站的爬网和重新编制索引的过程中，](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content)使用这些过程。</span><span class="sxs-lookup"><span data-stu-id="db437-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content) to re-index the site.</span></span>

## <a name="errorissue-search-fails-recipient-not-found"></a><span data-ttu-id="db437-145">错误/问题搜索无法找到收件人</span><span class="sxs-lookup"><span data-stu-id="db437-145">Error/issue search fails recipient not found</span></span>

<span data-ttu-id="db437-146">电子数据展示搜索失败`recipient not found`，并出现错误。</span><span class="sxs-lookup"><span data-stu-id="db437-146">eDiscovery search fails with error `recipient not found`.</span></span> <span data-ttu-id="db437-147">如果在 Exchange Online Protection （EOP）中找不到用户对象，因为该对象尚未同步，则可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="db437-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="db437-148">分辨率</span><span class="sxs-lookup"><span data-stu-id="db437-148">Resolution</span></span>

1. <span data-ttu-id="db437-149">连接到[Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="db437-149">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
1. <span data-ttu-id="db437-150">检查以查看是否已将 user 对象同步到 Exchange Online Protection 类型：</span><span class="sxs-lookup"><span data-stu-id="db437-150">Check to see if the user object is synced to Exchange Online Protection type:</span></span>

```powershell
Get-Recipient userId|fl
```

3. <span data-ttu-id="db437-151">对于用户问题，应该有一个 mailuser 对象。</span><span class="sxs-lookup"><span data-stu-id="db437-151">There should be a mailuser object for the user question.</span></span> <span data-ttu-id="db437-152">如果未返回任何内容，请调查 user 对象。</span><span class="sxs-lookup"><span data-stu-id="db437-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="db437-153">如果对象无法同步，请联系 CSS。</span><span class="sxs-lookup"><span data-stu-id="db437-153">Contact CSS if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="db437-154">错误/问题导出搜索结果缓慢</span><span class="sxs-lookup"><span data-stu-id="db437-154">Error/issue exporting search results is slow</span></span>

<span data-ttu-id="db437-155">在安全与合规中心中导出来自电子数据展示或内容搜索的搜索结果时，下载时间比预期时间长。</span><span class="sxs-lookup"><span data-stu-id="db437-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="db437-156">您可以查看要下载的数据量，并可能增加导出速度。</span><span class="sxs-lookup"><span data-stu-id="db437-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="db437-157">分辨率</span><span class="sxs-lookup"><span data-stu-id="db437-157">Resolution</span></span>

1.  <span data-ttu-id="db437-158">请尝试使用本文中确定的步骤[提高下载速度](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)。</span><span class="sxs-lookup"><span data-stu-id="db437-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>
2.  <span data-ttu-id="db437-159">如果仍有问题，请连接到[Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)并键入：</span><span class="sxs-lookup"><span data-stu-id="db437-159">If you still have issues, connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname\fl
```

4. <span data-ttu-id="db437-160">在 SearchResults 和 SearchStatistics 参数中查找要下载的数据量。</span><span class="sxs-lookup"><span data-stu-id="db437-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>
5. <span data-ttu-id="db437-161">类型：</span><span class="sxs-lookup"><span data-stu-id="db437-161">Type:</span></span>

```powershell
Get-ComplianceSearchAction |fl
```

6. <span data-ttu-id="db437-162">在 "结果" 字段中，找到已导出的数据并查看遇到的任何错误。</span><span class="sxs-lookup"><span data-stu-id="db437-162">In the results field find the data that has been exported and view any errors encountered.</span></span>
7. <span data-ttu-id="db437-163">检查您将内容导出到的目录中的 trace 文件，以查找任何错误。</span><span class="sxs-lookup"><span data-stu-id="db437-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="db437-164">错误/问题 "发生内部服务器错误（500）"</span><span class="sxs-lookup"><span data-stu-id="db437-164">Error/issue "Internal server error (500) occurred"</span></span>

<span data-ttu-id="db437-165">在运行电子数据展示搜索时，如果搜索持续失败，并出现类似 "内部服务器错误（500）" 的错误，则可能需要在特定邮箱位置上重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="db437-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need re-run the search only on specific mailbox locations.</span></span>

![内部服务器错误500屏幕截图](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="db437-167">分辨率</span><span class="sxs-lookup"><span data-stu-id="db437-167">Resolution</span></span>

1. <span data-ttu-id="db437-168">将搜索拆分为较小的搜索，然后再次运行搜索。</span><span class="sxs-lookup"><span data-stu-id="db437-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="db437-169">请尝试使用较小的日期范围或限制搜索的位置数。</span><span class="sxs-lookup"><span data-stu-id="db437-169">Try using a smaller date range or limit the number of locations being searched.</span></span>
2. <span data-ttu-id="db437-170">连接到[Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)并键入：</span><span class="sxs-lookup"><span data-stu-id="db437-170">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-ComplianceSearch searchname |fl
```

3. <span data-ttu-id="db437-171">检查结果和错误的输出。</span><span class="sxs-lookup"><span data-stu-id="db437-171">Examine the output for results and errors.</span></span>
3. <span data-ttu-id="db437-172">检查 trace .log 文件。</span><span class="sxs-lookup"><span data-stu-id="db437-172">Examine the trace.log file.</span></span> <span data-ttu-id="db437-173">它将位于您向其发送导出的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="db437-173">It will be in the same folder that you sent the export to.</span></span>
4. <span data-ttu-id="db437-174">联系支持 CSS。</span><span class="sxs-lookup"><span data-stu-id="db437-174">Contact Support CSS.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="db437-175">错误/问题保留不同步</span><span class="sxs-lookup"><span data-stu-id="db437-175">Error/issue holds don't sync</span></span>

<span data-ttu-id="db437-176">电子数据展示事例保留策略同步分布错误。</span><span class="sxs-lookup"><span data-stu-id="db437-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="db437-177">错误读数为：</span><span class="sxs-lookup"><span data-stu-id="db437-177">The error reads:</span></span>

> <span data-ttu-id="db437-178">"资源：部署策略所花的时间比预期要长。</span><span class="sxs-lookup"><span data-stu-id="db437-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="db437-179">更新最终部署状态可能需要另外两个小时，因此请在几小时内回来查看。 "</span><span class="sxs-lookup"><span data-stu-id="db437-179">It might take an additional two hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="db437-180">分辨率</span><span class="sxs-lookup"><span data-stu-id="db437-180">Resolution</span></span>

1.  <span data-ttu-id="db437-181">连接到[Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)并键入：</span><span class="sxs-lookup"><span data-stu-id="db437-181">Connect to [Exchange Online Protection PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps) and type:</span></span>

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. <span data-ttu-id="db437-182">检查 Distributiondetail 参数中的值，以查找类似于以下的错误：</span><span class="sxs-lookup"><span data-stu-id="db437-182">Examine the value in the Distributiondetail parameter for errors like the following:</span></span>

> <span data-ttu-id="db437-183">如果存在错误，请创建到 PG 的升级以强制对策略进行手动重新同步。</span><span class="sxs-lookup"><span data-stu-id="db437-183">If error exists, create escalation to PG to force a manual re-sync on the Policy.</span></span>

3. <span data-ttu-id="db437-184">联系 CSS。</span><span class="sxs-lookup"><span data-stu-id="db437-184">Contact CSS.</span></span>

## <a name="see-also"></a><span data-ttu-id="db437-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db437-185">See Also</span></span>
- [<span data-ttu-id="db437-186">避免内容位置错误的提示</span><span class="sxs-lookup"><span data-stu-id="db437-186">Tips to avoid content location errors</span></span>](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)