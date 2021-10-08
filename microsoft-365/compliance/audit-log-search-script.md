---
title: 使用 PowerShell 脚本搜索审核日志
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: 使用在 Exchange Online 中运行 Search-UnifiedAuditLog cmdlet 的 PowerShell 脚本搜索审核日志。 此脚本经过优化，可返回大量（最多 50,000 个）审核记录。 该脚本会将这些记录导出为 CSV 文件，可在 Excel 中使用 Power Query 查看或转换这些文件。
ms.openlocfilehash: 7f54924cf0f90b976c52c8ee7c53e151f50111b0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173543"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a>使用 PowerShell 脚本搜索审核日志

安全性、合规性和审核成为当今 IT 管理员的首要任务。 Microsoft 365 具有多种内置功能，可帮助组织管理安全性、合规性和审核。 具体来说，统一审核日志记录可以帮助调查安全事件和合规性问题。 可以使用以下方法检索审核日志：

- [Office 365 管理活动 API](/office/office-365-management-api/office-365-management-activity-api-reference)

- Microsoft 365 合规中心的[审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)

- Exchange Online PowerShell 中的 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) cmdle

如果需要定期检索审核日志，应考虑使用 Office 365 管理活动 API 的解决方案，因为它可以为大型组织提供持续检索数百万条审核记录所需的可扩展性和性能。 使用 Microsoft 365 合规中心中的审核日志搜索工具是快速查找较在短时间范围内发生的特定操作的审核记录的好方法。 在审核日志搜索工具中使用较长的时间范围（尤其是对于大型组织），可能会返回过多记录，无法轻松管理或导出。

在某些情况下，需要手动检索特定调查或事件的审核数据，特别是对于大型组织中较长的日期范围，最好使用 **Search-UnifiedAuditLog** cmdlet。 本文包含一个 PowerShell 脚本，该脚本使用 cmdlet 检索多达 50,000 条审核记录，然后将它们导出为 CSV 文件，可以使用 Excel 中的 Power Query 对其进行格式设置以帮助审阅。 使用本文中的脚本还可以将大审核日志搜索在服务中超时的可能性降到最低。

## <a name="before-you-run-the-script"></a>运行此脚本之前

- 必须启用审核日志记录，以便组织成功使用该脚本返回审核记录。 Microsoft 365 和 Office 365 企业版组织默认已打开审核日志搜索。 若要验证组织是否已打开审核日志搜索，可以在 Exchange Online PowerShell 中运行以下命令：

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  **UnifiedAuditLogestionEnabled** 属性的 `True` 值表明已打开审核日志搜索。

- 必须分配有 Exchange Online 中的“仅供查看审核日志”或“审核日志”角色才能成功运行脚本。 默认情况下，在 Exchange 管理中心中的“权限”页上将这些角色分配给“合规性管理”和“组织管理”角色组。 有关详细信息，请参阅[在合规中心搜索审核日志](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log)中的“搜索审核日志的要求”部分。

- 完成该脚本可能需要很长时间。 运行所需的时长取决于配置脚本以为其检索审核记录的日期范围和时间间隔大小。 较大的日期范围和较小的间隔将导致运行时间较长。 请参阅步骤 2 中的表格，了解有关日期范围和间隔的信息。

- 本文中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。

## <a name="step-1-connect-to-exchange-online-powershell"></a>步骤 1：连接到 Exchange Online PowerShell

第一步是连接到 Exchange Online PowerShell。 可以使用新式身份验证或多重身份验证 (MFA) 进行连接。 有关分步说明，请参阅[连接 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a>步骤 2：修改并运行脚本以检索审核记录

连接到 Exchange Online PowerShell 之后，下一步是创建、修改和运行脚本以检索审核数据。 审核日志搜索脚本中的前七行包含以下变量，可以对其进行修改以配置搜索。 请参阅步骤 2 中的表格，了解这些变量的说明。

1. 使用 ps1 文件名后缀将以下文本保存到 Windows PowerShell 脚本。例如，SearchAuditLog.ps1。

   ```powershell
   #Modify the values for the following variables to configure the audit log search.
   $logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
   $outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
   [DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
   [DateTime]$end = [DateTime]::UtcNow
   $record = "AzureActiveDirectory"
   $resultSize = 5000
   $intervalMinutes = 60
   
   #Start script
   [DateTime]$currentStart = $start
   [DateTime]$currentEnd = $start
   
   Function Write-LogFile ([String]$Message)
   {
       $final = [DateTime]::Now.ToUniversalTime().ToString("s") + ":" + $Message
       $final | Out-File $logFile -Append
   }
   
   Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
   Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"
   
   $totalCount = 0
   while ($true)
   {
       $currentEnd = $currentStart.AddMinutes($intervalMinutes)
       if ($currentEnd -gt $end)
       {
           $currentEnd = $end
       }
   
       if ($currentStart -eq $currentEnd)
       {
           break
       }
   
       $sessionID = [Guid]::NewGuid().ToString() + "_" +  "ExtractLogs" + (Get-Date).ToString("yyyyMMddHHmmssfff")
       Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       $currentCount = 0
   
       $sw = [Diagnostics.StopWatch]::StartNew()
       do
       {
           $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize
   
           if (($results | Measure-Object).Count -ne 0)
           {
               $results | export-csv -Path $outputFile -Append -NoTypeInformation
   
               $currentTotal = $results[0].ResultCount
               $totalCount += $results.Count
               $currentCount += $results.Count
               Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"
   
               if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
               {
                   $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                   Write-LogFile $message
                   Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                   ""
                   break
               }
           }
       }
       while (($results | Measure-Object).Count -ne 0)
   
       $currentStart = $currentEnd
   }
   
   Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
   Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green
   ```

2. 修改下表中列出的变量以配置搜索条件。 脚本包括这些变量的示例值，但应对其进行更改（除非另有说明）以满足特定要求。

   <br>

   ****

   |变量|示例值|说明|
   |---|---|---|
   |`$logFile`|"d:\temp\AuditSearchLog.txt"|指定日志文件的名称和位置，其中包含有关脚本执行的审核日志搜索的进度信息。该脚本将 UTC 时间戳写入日志文件。|
   |`$outputFile`|"d:\temp\AuditRecords.csv"|指定包含脚本所返回的审核记录的 CSV 文件的名称和位置。|
   |`[DateTime]$start` 和 `[DateTime]$end`|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|指定审核日志搜索的日期范围。 该脚本将返回指定日期范围内发生的审核活动的记录。 例如，若要返回 2021 年 1 月执行的活动，可使用 `"2021-01-01"` 的开始日期和 `"2021-01-31"` 的结束日期（请确保用双引号括起值）脚本中的示例值将返回过去 24 小时内执行的活动的记录。 如果值中不包含时间戳，则指定日期的默认时间戳为凌晨 12:00（午夜）。|
   |`$record`|"AzureActiveDirectory"|指定要搜索的审计活动（也称为 *操作*）的记录类型。 此属性指示触发了活动的服务或功能。 有关可用于此变量的记录类型的列表，请参阅[审核日志记录类型](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)。 可以使用记录类型名称或 ENUM 值。 <br/><br/>**提示：** 若要返回所有记录类型的审核记录，请使用 `$null` 值（不带双引号）。|
   |`$resultSize`|5000|指定脚本每次调用 **Search-UnifiedAuditLog** cmdlet 时返回的结果数（称为 *结果集*）。 cmdlet 支持的最大值是 5,000。 保留该值。|
   |`$intervalMinutes`|60|为了帮助克服返回 5000 条记录的限制，此变量将采用你指定的数据范围并将其划分到更小的时间间隔中。 现在，每个间隔（并非整个日期范围）都受命令的 5000 条记录输出限制约束。 对于大多数组织来说，日期范围内每 60 分钟间隔 5000 条记录的默认值应该已经足够。 但是，如果脚本返回 `maximum results limitation reached` 的错误，请缩短时间间隔（例如，减少到 30 分钟甚至 15 分钟），然后重新运行脚本。|
   ||||

   上表中列出的大多数变量都对应于 **Search-UnifiedAuditLog** cmdlet 的参数。 有关这些参数的详细信息，请参阅 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)。

3. 在本地计算机上，打开 Windows PowerShell，然后转到保存修改后的脚本的文件夹。

4. 在 Exchange Online PowerShell 中运行脚本；例如：

   ```powershell
   .\SearchAuditLog.ps1
   ```

脚本在运行时将显示进度消息。脚本运行完成后，将创建包含审计记录的日志文件和 CSV 文件，并将它们保存到由 `$logFile` 和 `$outputFile` 变量定义的文件夹中。

> [!IMPORTANT]
> 每次运行此脚本时返回的审计记录数上限为 50,000。 如果运行此脚本并返回 50,000 条结果，则很可能未包含日期范围内发生的活动的审核记录。 如果发生这种情况，建议将日期范围划分为更小的期间，然后针对每个日期范围重新运行脚本。 例如，如果 90 天的日期范围返回 50,000 条结果，则可以重新运行脚本两次，对日期范围中的前 45 天重新运行一次，然后针对接下来 45 天再运行一次。

## <a name="step-3-format-and-view-the-audit-records"></a>步骤 3：设置审核记录格式并查看

运行脚本并将审核记录导出为 CSV 文件后，可能需要设置 CSV 格式，以便查看和分析审核记录。 一种方法是使用 Excel 中的 Power Query JSON 转换功能，将 **AuditData** 列中 JSON 对象的每个属性拆分到各自的列中。 有关分步说明，请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)中的“步骤 2：使用 Power Query 编辑器转换 JSON 对象”。
