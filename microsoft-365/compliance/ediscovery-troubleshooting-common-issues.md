---
title: 解决常见的电子数据展示问题
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
ms.openlocfilehash: 0d411976ecf6adba9df1f75eb8a45409647b3e1a
ms.sourcegitcommit: c7f7ff463141f7d7f0970b64e5a04341db7e4fa8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37378634"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>调查、解决和解决常见的电子数据展示问题

本主题介绍了可用于识别和解决电子数据展示搜索或电子数据展示过程中其他位置可能遇到的问题的基本故障排除步骤。 解决其中一些方案需要 Microsoft 支持方面的帮助。 有关何时与 Microsoft 支持人员联系的信息包括在解决步骤中。

## <a name="errorissue-ambiguous-location"></a>错误/问题：不明确的位置

如果您尝试将用户的邮箱位置添加到搜索中，并且在 Exchange Online Protection （EOP）目录中存在具有相同 userID 的重复或冲突的对象，您将收到此`The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`错误：。 

### <a name="resolution"></a>分辨率

检查是否存在具有相同用户 ID 的重复用户或通讯组列表。

1. 连接到[Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

2. 检索用户名的所有实例，请键入：

    ```powershell
    Get-Recipient <username>
    ```

"Useralias@contoso.com" 的输出将类似于以下内容：

> 
> |名称  |RecipientType  |
> |---------|---------|
> |别名、用户     |MailUser         |
> |别名、用户     |用户         |

3. 如果返回多个用户，请找到并修复冲突的对象。

## <a name="errorissue-search-fails-on-specific-locations"></a>错误/问题：搜索在特定位置失败

电子数据展示或内容搜索可能会产生以下错误：
>此搜索已完成（#）错误。  是否要对失败的位置重试搜索？

![搜索特定位置发生错误屏幕截图]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>分辨率

如果您收到此错误，我们建议您验证在搜索中失败的位置，然后仅在失败的位置上运行搜索。

1. 连接到[Office 365 Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然后输入以下命令：

    ```powershell
    Get-ComplianceSearch <searchname> | FL 
    ```

2. 从 PowerShell 输出中，查看 "错误" 字段中的失败位置或从搜索输出中的错误的状态详细信息。

3. 仅重试失败位置上的电子数据展示搜索。

4. 如果继续收到这些错误，请参阅[重试失败的位置](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search)以了解更多疑难解答步骤。

## <a name="errorissue-file-not-found"></a>错误/问题：找不到文件

在运行包含 SharePoint Online 的电子数据展示搜索和一个驱动器用于商业位置时，您可能会`File Not Found`收到错误，尽管文件位于网站上。 此错误将出现在导出警告和错误 .csv 中，或已跳过 items .csv。 如果无法在网站上找到该文件或索引已过期，则可能会出现此情况。 下面是一个实际错误的文本，其中添加了强调。
  
> 28.06.2019 10：02：19_FailedToExportItem_Failed 下载内容。 其他诊断信息： ExportWorker：无法从内容 6ea52149-91cd 4965-b5bb-82ca6a3ec9be--到类型文档的。 相关 Id：3bd84722-937b-4c23-b61b-08d6fba9ec32。 ServerErrorCode：-2147024894--->***找不到***ServerException： File。 在 ClientRequest （Stream responseStream）处的 ProcessResponseStream （Stream）---内部异常堆栈跟踪的结束日期的---

### <a name="resolution"></a>分辨率

1. 检查搜索中标识的位置，以确保文件的位置正确，并将其添加到搜索位置中。

2. 在[手动请求对网站、库或列表重新编制索引网站的爬网和重新编制索引的过程中，](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content)使用这些过程。

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>错误/问题：搜索失败，因为找不到收件人

电子数据展示搜索失败，并`recipient not found`出现错误。 如果在 Exchange Online Protection （EOP）中找不到用户对象，因为该对象尚未同步，则可能会发生此错误。

### <a name="resolution"></a>分辨率

1. 连接到 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

2. 检查以查看是否已将 user 对象同步到 Exchange Online Protection 类型：

    ```powershell
    Get-Recipient <userId> | FL
    ```

3. 应存在用户问题的邮件用户对象。 如果未返回任何内容，请调查 user 对象。 如果无法同步对象，请联系 Microsoft 支持部门。

## <a name="errorissue-exporting-search-results-is-slow"></a>错误/问题：导出搜索结果的速度缓慢

在安全与合规中心中导出来自电子数据展示或内容搜索的搜索结果时，下载时间比预期时间长。  您可以查看要下载的数据量，并可能增加导出速度。

### <a name="resolution"></a>分辨率

1.  请尝试使用本文中确定的步骤[提高下载速度](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)。

2.  如果仍有问题，请连接到[Office 365 Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然后输入以下命令：

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

4. 在 SearchResults 和 SearchStatistics 参数中查找要下载的数据量。

5. 输入以下命令：

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

6. 在 "结果" 字段中，查找已导出的数据并查看遇到的任何错误。

7. 检查您将内容导出到的目录中的 trace 文件，以查找任何错误。

## <a name="errorissue-internal-server-error-500-occurred"></a>错误/问题： "发生内部服务器错误（500）"

在运行电子数据展示搜索时，如果搜索持续失败，并出现类似 "内部服务器错误（500）" 的错误，则可能需要仅在特定邮箱位置上重新运行搜索。

![内部服务器错误500屏幕截图](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>分辨率

1. 将搜索拆分为较小的搜索，然后再次运行搜索。  请尝试使用较小的日期范围或限制搜索的位置数。

2. 连接到[Office 365 Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然后输入以下命令：

    ```powershell
    Get-ComplianceSearch <searchname> | FL
    ```

3. 检查结果和错误的输出。

4. 检查 trace .log 文件。 它将位于您向其发送导出的同一文件夹中。

5. 与 Microsoft 技术支持联系。

## <a name="errorissue-holds-dont-sync"></a>错误/问题：保留不同步

电子数据展示事例保留策略同步分布错误。 错误读数为：

> "资源：部署策略所花的时间比预期要长。 更新最终部署状态可能需要另外两个小时，因此请在几小时内回来查看。 "

### <a name="resolution"></a>分辨率

1.  连接到[Office 365 Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) ，然后输入以下命令：

    ```powershell
    Get-RetentionCompliancePolicy  <policyname> - DistributionDetail | FL
    ```

2. 检查 DistributionDetail 参数中的值，以查找类似于以下的错误：

   > 如果存在错误，请创建到 PG 的升级以强制对策略进行手动重新同步。

3. 与 Microsoft 技术支持联系。

## <a name="see-also"></a>另请参阅

- [避免内容位置错误的提示](retry-failed-content-search.md#tips-to-avoid-content-location-errors)