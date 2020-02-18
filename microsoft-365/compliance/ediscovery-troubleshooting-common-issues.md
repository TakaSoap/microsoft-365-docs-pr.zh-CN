---
title: 解决常见的电子数据展示问题
f1.keywords:
- NOCSH
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
description: 调查、解决 Office 365 电子数据展示中的常见问题和解决问题。
siblings_only: true
ms.openlocfilehash: 3ff22ae11a21aef3909e58e03c8fefcf21db6435
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074802"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="45ae3-103">调查、解决和解决常见的电子数据展示问题</span><span class="sxs-lookup"><span data-stu-id="45ae3-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="45ae3-104">本主题介绍了可用于识别和解决电子数据展示搜索或电子数据展示过程中其他位置可能遇到的问题的基本故障排除步骤。</span><span class="sxs-lookup"><span data-stu-id="45ae3-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="45ae3-105">解决其中一些方案需要 Microsoft 支持方面的帮助。</span><span class="sxs-lookup"><span data-stu-id="45ae3-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="45ae3-106">有关何时与 Microsoft 支持人员联系的信息包括在解决步骤中。</span><span class="sxs-lookup"><span data-stu-id="45ae3-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="45ae3-107">错误/问题：不明确的位置</span><span class="sxs-lookup"><span data-stu-id="45ae3-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="45ae3-108">如果您尝试将用户的邮箱位置添加到搜索中，并且在 Exchange Online Protection （EOP）目录中存在具有相同 userID 的重复或冲突的对象，则会收到`The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`此错误：。</span><span class="sxs-lookup"><span data-stu-id="45ae3-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span> 

### <a name="resolution"></a><span data-ttu-id="45ae3-109">分辨率</span><span class="sxs-lookup"><span data-stu-id="45ae3-109">Resolution</span></span>

<span data-ttu-id="45ae3-110">检查是否存在具有相同用户 ID 的重复用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="45ae3-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="45ae3-111">连接到[Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="45ae3-111">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="45ae3-112">运行以下命令以检索用户名的所有实例：</span><span class="sxs-lookup"><span data-stu-id="45ae3-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="45ae3-113">"Useralias@contoso.com" 的输出将类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="45ae3-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="45ae3-114">名称</span><span class="sxs-lookup"><span data-stu-id="45ae3-114">Name</span></span>  |<span data-ttu-id="45ae3-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="45ae3-115">RecipientType</span></span>  |
   > |---------|---------|
   > |<span data-ttu-id="45ae3-116">别名、用户</span><span class="sxs-lookup"><span data-stu-id="45ae3-116">Alias, User</span></span>     |<span data-ttu-id="45ae3-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="45ae3-117">MailUser</span></span>         |
   > |<span data-ttu-id="45ae3-118">别名、用户</span><span class="sxs-lookup"><span data-stu-id="45ae3-118">Alias, User</span></span>     |<span data-ttu-id="45ae3-119">用户</span><span class="sxs-lookup"><span data-stu-id="45ae3-119">User</span></span>         |

3. <span data-ttu-id="45ae3-120">如果返回多个用户，请找到并修复冲突的对象。</span><span class="sxs-lookup"><span data-stu-id="45ae3-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="45ae3-121">错误/问题：搜索在特定位置失败</span><span class="sxs-lookup"><span data-stu-id="45ae3-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="45ae3-122">电子数据展示或内容搜索可能会产生以下错误：</span><span class="sxs-lookup"><span data-stu-id="45ae3-122">An eDiscovery or content search may yield the following error:</span></span>
><span data-ttu-id="45ae3-123">此搜索已完成（#）错误。</span><span class="sxs-lookup"><span data-stu-id="45ae3-123">This search completed with (#) errors.</span></span>  <span data-ttu-id="45ae3-124">是否要对失败的位置重试搜索？</span><span class="sxs-lookup"><span data-stu-id="45ae3-124">Would you like to retry the search on the failed locations?</span></span>

![搜索特定位置发生错误屏幕截图](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="45ae3-126">分辨率</span><span class="sxs-lookup"><span data-stu-id="45ae3-126">Resolution</span></span>

<span data-ttu-id="45ae3-127">如果您收到此错误，我们建议您验证在搜索中失败的位置，然后仅在失败的位置上运行搜索。</span><span class="sxs-lookup"><span data-stu-id="45ae3-127">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="45ae3-128">连接到[Office 365 Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="45ae3-128">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL 
    ```

2. <span data-ttu-id="45ae3-129">从 PowerShell 输出中，查看 "错误" 字段中的失败位置或从搜索输出中的错误的状态详细信息。</span><span class="sxs-lookup"><span data-stu-id="45ae3-129">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="45ae3-130">仅重试失败位置上的电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="45ae3-130">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="45ae3-131">如果继续收到这些错误，请参阅[重试失败的位置](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search)以了解更多疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="45ae3-131">If you continue to receive these errors, see [Retry failed locations](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="45ae3-132">错误/问题：找不到文件</span><span class="sxs-lookup"><span data-stu-id="45ae3-132">Error/issue: File not found</span></span>

<span data-ttu-id="45ae3-133">在运行包含 SharePoint Online 的电子数据展示搜索和一个驱动器用于商业位置时，您可能会`File Not Found`收到错误，尽管文件位于网站上。</span><span class="sxs-lookup"><span data-stu-id="45ae3-133">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="45ae3-134">此错误将出现在导出警告和错误 .csv 中，或已跳过 items .csv。</span><span class="sxs-lookup"><span data-stu-id="45ae3-134">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="45ae3-135">如果在网站上找不到该文件，或者索引已过期，则可能会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="45ae3-135">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="45ae3-136">以下是实际错误的文本（添加了强调）。</span><span class="sxs-lookup"><span data-stu-id="45ae3-136">Here's the text of an actual error (with emphasis added).</span></span>
  
> <span data-ttu-id="45ae3-137">28.06.2019 10：02：19_FailedToExportItem_Failed 下载内容。</span><span class="sxs-lookup"><span data-stu-id="45ae3-137">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="45ae3-138">其他诊断信息： ExportWorker：无法从内容 6ea52149-91cd 4965-b5bb-82ca6a3ec9be--到类型文档的。</span><span class="sxs-lookup"><span data-stu-id="45ae3-138">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="45ae3-139">相关 Id：3bd84722-937b-4c23-b61b-08d6fba9ec32。</span><span class="sxs-lookup"><span data-stu-id="45ae3-139">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="45ae3-140">ServerErrorCode：-2147024894--->***找不到***ServerException： File。</span><span class="sxs-lookup"><span data-stu-id="45ae3-140">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="45ae3-141">在 ClientRequest （Stream responseStream）处的 ProcessResponseStream （Stream）---内部异常堆栈跟踪的结束日期的---</span><span class="sxs-lookup"><span data-stu-id="45ae3-141">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="45ae3-142">分辨率</span><span class="sxs-lookup"><span data-stu-id="45ae3-142">Resolution</span></span>

1. <span data-ttu-id="45ae3-143">检查搜索中标识的位置，以确保文件的位置正确，并将其添加到搜索位置中。</span><span class="sxs-lookup"><span data-stu-id="45ae3-143">Check location identified in the search to ensure the that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="45ae3-144">手动使用这些过程可对[网站、库或列表重新编制索引，以对网站、库或列表进行爬网的请求](https://docs.microsoft.com/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="45ae3-144">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](https://docs.microsoft.com/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="45ae3-145">错误/问题：搜索失败，因为找不到收件人</span><span class="sxs-lookup"><span data-stu-id="45ae3-145">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="45ae3-146">电子数据展示搜索失败，并`recipient not found`出现错误。</span><span class="sxs-lookup"><span data-stu-id="45ae3-146">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="45ae3-147">如果在 Exchange Online Protection （EOP）中找不到用户对象，因为该对象尚未同步，则可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="45ae3-147">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="45ae3-148">分辨率</span><span class="sxs-lookup"><span data-stu-id="45ae3-148">Resolution</span></span>

1. <span data-ttu-id="45ae3-149">连接到 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="45ae3-149">Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="45ae3-150">运行以下命令以检查用户是否已同步到 Exchange Online Protection：</span><span class="sxs-lookup"><span data-stu-id="45ae3-150">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

    ```powershell
    Get-Recipient <userId> | FL
    ```

3. <span data-ttu-id="45ae3-151">应存在用户问题的邮件用户对象。</span><span class="sxs-lookup"><span data-stu-id="45ae3-151">There should be a mail user object for the user question.</span></span> <span data-ttu-id="45ae3-152">如果未返回任何内容，请调查 user 对象。</span><span class="sxs-lookup"><span data-stu-id="45ae3-152">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="45ae3-153">如果无法同步对象，请联系 Microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="45ae3-153">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="45ae3-154">错误/问题：导出搜索结果的速度缓慢</span><span class="sxs-lookup"><span data-stu-id="45ae3-154">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="45ae3-155">在安全与合规中心中导出来自电子数据展示或内容搜索的搜索结果时，下载时间比预期时间长。</span><span class="sxs-lookup"><span data-stu-id="45ae3-155">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="45ae3-156">您可以查看要下载的数据量，并可能增加导出速度。</span><span class="sxs-lookup"><span data-stu-id="45ae3-156">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="45ae3-157">分辨率</span><span class="sxs-lookup"><span data-stu-id="45ae3-157">Resolution</span></span>

1.  <span data-ttu-id="45ae3-158">请尝试使用本文中确定的步骤[提高下载速度](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)。</span><span class="sxs-lookup"><span data-stu-id="45ae3-158">Try using the steps identified in the article [Increase Download Speeds](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results).</span></span>

2.  <span data-ttu-id="45ae3-159">如果仍有问题，请连接到[Office 365 Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="45ae3-159">If you still have issues, connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command:</span></span>

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

4. <span data-ttu-id="45ae3-160">在 SearchResults 和 SearchStatistics 参数中查找要下载的数据量。</span><span class="sxs-lookup"><span data-stu-id="45ae3-160">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

5. <span data-ttu-id="45ae3-161">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="45ae3-161">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

6. <span data-ttu-id="45ae3-162">在 "结果" 字段中，查找已导出的数据并查看遇到的任何错误。</span><span class="sxs-lookup"><span data-stu-id="45ae3-162">In the results field, find the data that has been exported and view any errors encountered.</span></span>

7. <span data-ttu-id="45ae3-163">检查您将内容导出到的目录中的 trace 文件，以查找任何错误。</span><span class="sxs-lookup"><span data-stu-id="45ae3-163">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="45ae3-164">错误/问题： "发生内部服务器错误（500）"</span><span class="sxs-lookup"><span data-stu-id="45ae3-164">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="45ae3-165">在运行电子数据展示搜索时，如果搜索持续失败，并出现类似 "内部服务器错误（500）" 的错误，则可能需要仅在特定邮箱位置上重新运行搜索。</span><span class="sxs-lookup"><span data-stu-id="45ae3-165">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![内部服务器错误500屏幕截图](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="45ae3-167">分辨率</span><span class="sxs-lookup"><span data-stu-id="45ae3-167">Resolution</span></span>

1. <span data-ttu-id="45ae3-168">将搜索拆分为较小的搜索，然后再次运行搜索。</span><span class="sxs-lookup"><span data-stu-id="45ae3-168">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="45ae3-169">请尝试使用较小的日期范围或限制搜索的位置数。</span><span class="sxs-lookup"><span data-stu-id="45ae3-169">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="45ae3-170">连接到[Office 365 Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="45ae3-170">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command:</span></span>

    ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
    Get-ComplianceSearch <searchname> | FL
    ```

3. <span data-ttu-id="45ae3-171">检查结果和错误的输出。</span><span class="sxs-lookup"><span data-stu-id="45ae3-171">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="45ae3-172">检查 trace .log 文件。</span><span class="sxs-lookup"><span data-stu-id="45ae3-172">Examine the trace.log file.</span></span> <span data-ttu-id="45ae3-173">它位于将搜索结果导出到的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="45ae3-173">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="45ae3-174">与 Microsoft 技术支持联系。</span><span class="sxs-lookup"><span data-stu-id="45ae3-174">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="45ae3-175">错误/问题：保留不同步</span><span class="sxs-lookup"><span data-stu-id="45ae3-175">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="45ae3-176">电子数据展示事例保留策略同步分布错误。</span><span class="sxs-lookup"><span data-stu-id="45ae3-176">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="45ae3-177">错误读数为：</span><span class="sxs-lookup"><span data-stu-id="45ae3-177">The error reads:</span></span>

> <span data-ttu-id="45ae3-178">"资源：部署策略所花的时间比预期要长。</span><span class="sxs-lookup"><span data-stu-id="45ae3-178">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="45ae3-179">更新最终部署状态可能需要另外2个小时，因此请在几小时内回来查看。 "</span><span class="sxs-lookup"><span data-stu-id="45ae3-179">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.”</span></span>

### <a name="resolution"></a><span data-ttu-id="45ae3-180">分辨率</span><span class="sxs-lookup"><span data-stu-id="45ae3-180">Resolution</span></span>

1.  <span data-ttu-id="45ae3-181">连接到[Office 365 Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然后为电子数据展示事例保留运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="45ae3-181">Connect to [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

    ```powershell
    Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
    ```

    <span data-ttu-id="45ae3-182">对于保留策略，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="45ae3-182">For a retention policy, run the following command:</span></span>

    ```powershell
    Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
    ```

2. <span data-ttu-id="45ae3-183">检查 DistributionDetail 参数中的值，以查找类似于以下的错误：</span><span class="sxs-lookup"><span data-stu-id="45ae3-183">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>
 
   > <span data-ttu-id="45ae3-184">错误：资源：部署策略所花的时间比预期时间长。</span><span class="sxs-lookup"><span data-stu-id="45ae3-184">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="45ae3-185">更新最终部署状态可能需要另外2个小时，因此请在几小时内回来查看。 "</span><span class="sxs-lookup"><span data-stu-id="45ae3-185">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.”</span></span> 
   
3. <span data-ttu-id="45ae3-186">尝试对所述的策略运行 RetryDistribution 参数：</span><span class="sxs-lookup"><span data-stu-id="45ae3-186">Try running the RetryDistribution parameter on the policy in question:</span></span>
   
    
    <span data-ttu-id="45ae3-187">对于电子数据展示事例保留：</span><span class="sxs-lookup"><span data-stu-id="45ae3-187">For eDiscovery case holds:</span></span>

    ```powershell
    Set-CaseHoldPolicy <policyname> -RetryDistribution
    ```

    <span data-ttu-id="45ae3-188">对于保留策略：</span><span class="sxs-lookup"><span data-stu-id="45ae3-188">For retention policies:</span></span>

    ```powershell
    Set-RetentionCompliancePolicy <policyname> -RetryDistribution
    ``` 

4. <span data-ttu-id="45ae3-189">与 Microsoft 技术支持联系。</span><span class="sxs-lookup"><span data-stu-id="45ae3-189">Contact Microsoft Support.</span></span>

## <a name="see-also"></a><span data-ttu-id="45ae3-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45ae3-190">See Also</span></span>

- [<span data-ttu-id="45ae3-191">避免内容位置错误的提示</span><span class="sxs-lookup"><span data-stu-id="45ae3-191">Tips to avoid content location errors</span></span>](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
