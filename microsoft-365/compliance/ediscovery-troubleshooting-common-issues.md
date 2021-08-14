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
ms.openlocfilehash: 1ec120edcbccc64046b57507cd6cd6044fb583c5129c336e28890b67f369cd46
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53820135"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>调查、排查并解决常见的电子数据展示问题

本主题介绍为识别和解决在电子数据展示搜索过程中或电子数据展示过程中其他位置可能遇到的问题而可以执行的基本疑难解答步骤。 解决其中某些方案需要 Microsoft 支持人员的帮助。 有关何时联系 Microsoft 支持的信息包含在解决方案步骤中。

## <a name="errorissue-ambiguous-location"></a>错误/问题：位置不明确

如果您尝试添加要搜索的用户邮箱位置，并且 Exchange Online Protection (EOP) 目录中存在具有相同 userID 的重复或冲突对象，则会收到此错误 `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` ：。

### <a name="resolution"></a>解决方案

检查具有相同用户 ID 的重复用户或通讯组列表。

1. 连接安全[与&中心 PowerShell。](/powershell/exchange/connect-to-scc-powershell)

2. 运行以下命令以检索用户名的所有实例：

    ```powershell
    Get-Recipient <username>
    ```

   "useralias@contoso.com"的输出将类似于以下内容：

   > 
   > |名称|RecipientType|
   > |---|---|
   > |别名、用户|MailUser|
   > |别名、用户|用户|

3. 如果返回多个用户，请找到并修复冲突对象。

## <a name="errorissue-search-fails-on-specific-locations"></a>错误/问题：搜索特定位置失败

电子数据展示或内容搜索可能会生成以下错误： `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![搜索特定位置失败错误屏幕截图](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>解决方案

如果您收到此错误，我们建议您验证搜索失败的位置，然后仅在失败的位置重新运行搜索。

1. 连接安全&[合规中心 PowerShell，](/powershell/exchange/connect-to-scc-powershell)然后运行以下命令：

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. 从 PowerShell 输出中，从搜索输出中查看错误字段中的失败位置或错误的状态详细信息。

3. 仅对失败的位置重试电子数据展示搜索。

4. 如果继续收到这些错误，请参阅重试失败 [位置](/Office365/SecurityCompliance/retry-failed-content-search) 了解更多疑难解答步骤。

## <a name="errorissue-file-not-found"></a>错误/问题：未找到文件

当运行包括 SharePoint Online 和 One Drive For Business 位置的电子数据展示搜索时，你可能会收到错误，尽管该文件 `File Not Found` 位于网站上。 此错误将位于导出警告中，errors.csv或跳过items.csv。 如果网站上找不到该文件或索引已过期，则可能会发生这种情况。 下面是实际错误的文本，其中 (强调) 。

> 28.06.2019 10：02：19_FailedToExportItem_Failed下载内容。 其他诊断信息：Microsoft。Office。Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure：无法从类型为 Document 的内容 6ea52149-91cd-4965-b5bb-82ca6a3ec9be 下载。 相关 ID：3bd84722-937b-4c23-b61b-08d6fba9ec32。 ServerErrorCode：-2147024894 ---> Microsoft。SharePoint。Client.ServerException：***未找到文件***。 位于 Microsoft。SharePoint。Client.ClientRequest.ProcessResponseStream (Microsoft) Stream responseStream。SharePoint。Client.ClientRequest.ProcessResponse () ---内部异常堆栈跟踪结束---

### <a name="resolution"></a>解决方案

1. 检查搜索中标识的位置，以确保文件的位置正确无误，并添加到搜索位置。

2. 使用 [Manually request crawling and re-indexing of a site， a library， or a list](/sharepoint/crawl-site-content) 中的过程对网站重新编制索引。

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a>错误/问题：此文件未导出，因为它不再存在。 该文件包含在估计的搜索结果计数中，因为它仍在索引中列出。 文件最终将从索引中删除，并且将来不会引发错误。

运行包括"联机"和"One Drive for Business"SharePoint电子数据展示搜索时可能会看到该错误。 电子数据展示依赖 SPO 索引来标识文件位置。 如果文件已删除，但 SPO 索引尚未更新，则可能会发生此错误。

### <a name="resolution"></a>解决方案 
打开 SPO 位置并验证此文件是否确实不存在。
建议的解决方案是手动对网站重新索引，或等到自动后台进程对网站重新索引。


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artifact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a>错误/问题：此搜索结果未下载，因为此搜索结果是一个无法自行下载的文件夹或其他项目，将下载文件夹或库内的任何项目。

运行包括"联机"和"One Drive for Business"SharePoint电子数据展示搜索时可能会看到该错误。 这意味着我们将尝试导出索引中报告的项目，但它却变成一个文件夹，因此我们没有导出它。 如错误所述，我们不会导出文件夹项目，但会导出其内容。


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>错误/问题：搜索失败，因为未找到收件人

电子数据展示搜索失败，出现错误 `recipient not found` 。 如果在 EOP 服务器中找不到用户对象，则Exchange Online Protection (，) 对象尚未同步。

### <a name="resolution"></a>解决方案

1. 连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 运行以下命令，检查用户是否同步到Exchange Online Protection：

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. 应存在用户问题的邮件用户对象。 如果未返回任何值，请调查用户对象。 如果对象无法同步，请与 Microsoft 支持部门联系。

## <a name="errorissue-exporting-search-results-is-slow"></a>错误/问题：导出搜索结果的速度很慢

从核心电子数据展示或内容搜索中导出搜索结果时Microsoft 365 合规中心下载时间超过预期。  你可以查看要下载的数据量，并可能提高导出速度。

### <a name="resolution"></a>解决方案

1. 连接安全&[合规中心 PowerShell，](/powershell/exchange/connect-to-scc-powershell)然后运行以下命令：

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. 在 SearchResults 和 SearchStatistics 参数中查找要下载的数据量。

3. 运行以下命令：

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. 在结果字段中，查找已导出的数据并查看遇到的任何错误。

5. 检查位于日志文件的目录中的 trace.日志文件，了解是否有错误。

6. 如果仍有问题，请考虑将返回大量结果的搜索划分为较小的搜索。 例如，您可以使用搜索查询中的日期范围返回一组较小的结果，可以更快地下载结果。

## <a name="errorissue-export-process-not-progressing-or-is-stuck"></a>错误/问题：导出过程未进行或卡住

从核心电子数据展示或内容搜索中导出搜索结果时Microsoft 365 合规中心导出过程未进行或似乎卡住。

### <a name="resolution"></a>解决方案

1. 如有必要，请重新运行搜索。 如果上次运行搜索的时间超过 7 天，您必须重新运行搜索。

2. 重新启动导出。

## <a name="errorissue-internal-server-error-500-occurred"></a>错误/问题："发生了 500 (内部) 错误"

在运行电子数据展示搜索时，如果搜索不断失败，出现错误类似于"发生内部服务器错误 (500) "，可能需要仅在特定邮箱位置重新运行搜索。

![内部服务器错误 500 屏幕截图](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>解决方案

1. 将搜索分解为较小的搜索，然后再次运行搜索。  请尝试使用较小的日期范围或限制要搜索的位置数。

2. 连接安全&[合规中心 PowerShell，](/powershell/exchange/connect-to-scc-powershell)然后运行以下命令：

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. 检查结果和错误的输出。

4. 检查 trace.日志文件。 它位于将搜索结果导出到的同一文件夹中。

5. 与 Microsoft 技术支持联系。

## <a name="errorissue-holds-dont-sync"></a>错误/问题：保留未同步

电子数据展示案例保留策略同步分发错误。 错误显示为：

> "资源：部署策略所花时间超过预期。 更新最终部署状态可能需要另外 2 个小时，因此请在几小时后重新检查。"

### <a name="resolution"></a>解决方案

1. 连接安全&合规中心[PowerShell，](/powershell/exchange/connect-to-scc-powershell)然后运行以下针对电子数据展示案例保留的命令：

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    对于保留策略，请运行以下命令：

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. 检查 DistributionDetail 参数中的值，了解错误，如下所示：

   > 错误：资源：部署策略所花时间超过预期。 更新最终部署状态可能需要另外 2 个小时，因此请在几小时后重新检查。"

3. 尝试对问题策略运行 RetryDistribution 参数：

   对于电子数据展示案例保留：

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   对于保留策略：

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. 与 Microsoft 技术支持联系。

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>错误："不满足使用 HTTP (标头) 条件"

使用电子数据展示导出工具下载搜索结果时，您可能会收到以下错误：这是暂时性错误，通常发生在 Azure 存储 `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 位置。

### <a name="resolution"></a>解决方案

若要解决此问题，请 [重试下载搜索结果](export-search-results.md#step-2-download-the-search-results)，这将重新启动电子数据展示导出工具。

## <a name="errorissue-downloaded-export-shows-no-results"></a>错误/问题：已下载的导出未显示任何结果

成功导出后，通过导出工具完成的下载将在结果中显示零文件。

### <a name="resolution"></a>解决方案

这是客户端问题。 若要修正它，请按照以下步骤操作：

1. 请尝试使用另一个客户端/计算机进行下载。

2. 使用 [Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) cmdlet 删除不再需要的旧搜索。

3. 确保下载到本地驱动器。

4. 确保病毒扫描程序未运行。

5. 确保没有任何其他导出内容下载到同一文件夹或任何父文件夹。

6. 如果前面的步骤不起作用，则禁用 zipping 和重复数据删除。

7. 如果此操作有效，则问题由本地病毒扫描程序或磁盘问题导致。
