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
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: 使用 PowerShell 脚本运行 Search-UnifiedAuditLog cmdlet 来搜索审核日志。 此脚本经过优化，可返回大量（最多 50,000 个）审核记录。 该脚本会将这些记录导出为 CSV 文件，可在 Excel 中使用 Power Query 查看或转换这些文件。
ms.openlocfilehash: d4fcf59297747d0499f6616438299ad8cbe96d7f
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094783"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a><span data-ttu-id="1584c-105">使用 PowerShell 脚本搜索审核日志</span><span class="sxs-lookup"><span data-stu-id="1584c-105">Use a PowerShell script to search the audit log</span></span>

<span data-ttu-id="1584c-106">安全性、合规性和审核成为当今 IT 管理员的首要任务。</span><span class="sxs-lookup"><span data-stu-id="1584c-106">Security, compliance, and auditing have become a top priority for IT administrators in today’s world.</span></span> <span data-ttu-id="1584c-107">Microsoft 365 具有多种内置功能，可帮助组织管理安全性、合规性和审核。</span><span class="sxs-lookup"><span data-stu-id="1584c-107">Microsoft 365 has several built-in capabilities to help organizations manage security, compliance, and auditing.</span></span> <span data-ttu-id="1584c-108">具体来说，统一审核日志记录可以帮助调查安全事件和合规性问题。</span><span class="sxs-lookup"><span data-stu-id="1584c-108">In particular, unified audit logging can help you investigate security incidents and compliance issues.</span></span> <span data-ttu-id="1584c-109">可以使用以下方法检索审核日志：</span><span class="sxs-lookup"><span data-stu-id="1584c-109">You can retrieve audit logs by using the following methods:</span></span>

- [<span data-ttu-id="1584c-110">Office 365 管理活动 API</span><span class="sxs-lookup"><span data-stu-id="1584c-110">The Office 365 Management Activity API</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

- <span data-ttu-id="1584c-111">Microsoft 365 合规中心的[审核日志搜索工具](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="1584c-111">The [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center</span></span>

- <span data-ttu-id="1584c-112">Exchange Online PowerShell 中的 [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) cmdle</span><span class="sxs-lookup"><span data-stu-id="1584c-112">The [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell</span></span>

<span data-ttu-id="1584c-113">如果需要定期检索审核日志，应考虑使用 Office 365 管理活动 API 的解决方案，因为它可以为大型组织提供持续检索数百万条审核记录所需的可扩展性和性能。</span><span class="sxs-lookup"><span data-stu-id="1584c-113">If you need to retrieve audit logs on a regular basis, you should consider a solution that uses the Office 365 Management Activity API because it that can provide large organizations with the scalability and performance to retrieve millions of audit records on an ongoing basis.</span></span> <span data-ttu-id="1584c-114">使用 Microsoft 365 合规中心中的审核日志搜索工具是快速查找较在短时间范围内发生的特定操作的审核记录的好方法。</span><span class="sxs-lookup"><span data-stu-id="1584c-114">Using the audit log search tool in Microsoft 365 compliance center is a good way to quickly find audit records for specific operations that occur in shorter time range.</span></span> <span data-ttu-id="1584c-115">在审核日志搜索工具中使用较长的时间范围（尤其是对于大型组织），可能会返回过多记录，无法轻松管理或导出。</span><span class="sxs-lookup"><span data-stu-id="1584c-115">Using longer time ranges in the audit log search tool, especially for large organizations, might return too many records to easily manage or export.</span></span>

<span data-ttu-id="1584c-116">在某些情况下，需要手动检索特定调查或事件的审核数据，特别是对于大型组织中较长的日期范围，最好使用 **Search-UnifiedAuditLog** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1584c-116">When there are situations where you need to manually retrieve auditing data for a specific investigation or incident, particularly for longer date ranges in larger organizations, using the **Search-UnifiedAuditLog** cmdlet may be the best option.</span></span> <span data-ttu-id="1584c-117">本文包含一个 PowerShell 脚本，该脚本使用 cmdlet 检索多达 50,000 条审核记录，然后将它们导出为 CSV 文件，可以使用 Excel 中的 Power Query 对其进行格式设置以帮助审阅。</span><span class="sxs-lookup"><span data-stu-id="1584c-117">This article includes a PowerShell script that uses the cmdlet to retrieve up to 50,000 audit records and then export them to a CSV file that you can format using Power Query in Excel to help with your review.</span></span> <span data-ttu-id="1584c-118">使用本文中的脚本还可以将大审核日志搜索在服务中超时的可能性降到最低。</span><span class="sxs-lookup"><span data-stu-id="1584c-118">Using the script in this article also minimizes the chance that large audit log searches will time out in the service.</span></span>

## <a name="before-you-run-the-script"></a><span data-ttu-id="1584c-119">运行此脚本之前</span><span class="sxs-lookup"><span data-stu-id="1584c-119">Before you run the script</span></span>

- <span data-ttu-id="1584c-120">必须启用审核日志记录，以便组织成功使用该脚本返回审核记录。</span><span class="sxs-lookup"><span data-stu-id="1584c-120">Audit logging has to be enabled for your organization to successfully use the script to return audit records.</span></span> <span data-ttu-id="1584c-121">Microsoft 365 和 Office 365 企业版组织默认已打开审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1584c-121">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="1584c-122">若要验证组织是否已打开审核日志搜索，可以在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1584c-122">To verify that audit log search is turned on for your organization, you can run the following command in Exchange Online PowerShell:</span></span>

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```
  
  <span data-ttu-id="1584c-123">**UnifiedAuditLogestionEnabled** 属性的 `True` 值表明已打开审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1584c-123">The value of `True` for the **UnifiedAuditLogIngestionEnabled** property indicates that audit log search is turned on.</span></span>

- <span data-ttu-id="1584c-124">必须分配有 Exchange Online 中的“仅供查看审核日志”或“审核日志”角色才能成功运行脚本。</span><span class="sxs-lookup"><span data-stu-id="1584c-124">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to run successfully the script.</span></span> <span data-ttu-id="1584c-125">默认情况下，在 Exchange 管理中心中的“权限”页上将这些角色分配给“合规性管理”和“组织管理”角色组。</span><span class="sxs-lookup"><span data-stu-id="1584c-125">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="1584c-126">有关详细信息，请参阅[在合规中心搜索审核日志](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log)中的“搜索审核日志的要求”部分。</span><span class="sxs-lookup"><span data-stu-id="1584c-126">For more information, see the "Requirements to search the audit log" section in [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span>

- <span data-ttu-id="1584c-127">完成该脚本可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="1584c-127">It may take a long time for the script to complete.</span></span> <span data-ttu-id="1584c-128">运行所需的时长取决于配置脚本以为其检索审核记录的日期范围和时间间隔大小。</span><span class="sxs-lookup"><span data-stu-id="1584c-128">How long it takes to run depends on the date range and the size of the interval that you configure the script to retrieve audit records for.</span></span> <span data-ttu-id="1584c-129">较大的日期范围和较小的间隔将导致运行时间较长。</span><span class="sxs-lookup"><span data-stu-id="1584c-129">Larger date ranges and smaller intervals will result in a long running time.</span></span> <span data-ttu-id="1584c-130">请参阅步骤 2 中的表格，了解有关日期范围和间隔的信息。</span><span class="sxs-lookup"><span data-stu-id="1584c-130">See the table in Step 2 for more information about the date range and intervals.</span></span>

- <span data-ttu-id="1584c-131">本文中提供的示例脚本在任何 Microsoft 标准支持程序或服务下都不受支持。</span><span class="sxs-lookup"><span data-stu-id="1584c-131">The sample script provided in this article isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="1584c-132">示例脚本“原样”提供，不提供任何形式的保证。</span><span class="sxs-lookup"><span data-stu-id="1584c-132">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="1584c-133">Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。</span><span class="sxs-lookup"><span data-stu-id="1584c-133">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="1584c-134">由于示例脚本及文档的使用或性能所引起的全部风险均由你承担。</span><span class="sxs-lookup"><span data-stu-id="1584c-134">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="1584c-135">在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。</span><span class="sxs-lookup"><span data-stu-id="1584c-135">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="1584c-136">步骤 1：连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1584c-136">Step 1: Connect to Exchange Online PowerShell</span></span>

<span data-ttu-id="1584c-137">第一步是连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1584c-137">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="1584c-138">可以使用新式身份验证或多重身份验证 (MFA) 进行连接。</span><span class="sxs-lookup"><span data-stu-id="1584c-138">You can connect using modern authentication or with multi-factor authentication (MFA).</span></span> <span data-ttu-id="1584c-139">有关分步说明，请参阅[连接 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1584c-139">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a><span data-ttu-id="1584c-140">步骤 2：修改并运行脚本以检索审核记录</span><span class="sxs-lookup"><span data-stu-id="1584c-140">Step 2: Modify and run the script to retrieve audit records</span></span>

<span data-ttu-id="1584c-141">连接到 Exchange Online PowerShell 之后，下一步是创建、修改和运行脚本以检索审核数据。</span><span class="sxs-lookup"><span data-stu-id="1584c-141">After you've connected to Exchange Online PowerShell, the next step is to create, modify, and run the script to retrieve the auditing data.</span></span> <span data-ttu-id="1584c-142">审核日志搜索脚本中的前七行包含以下变量，可以对其进行修改以配置搜索。</span><span class="sxs-lookup"><span data-stu-id="1584c-142">The first seven lines in the audit log search script contain the following variables that you can modify to configure your search.</span></span> <span data-ttu-id="1584c-143">请参阅步骤 2 中的表格，了解这些变量的说明。</span><span class="sxs-lookup"><span data-stu-id="1584c-143">See the table in step 2 for a description of these variables.</span></span>

1. <span data-ttu-id="1584c-144">使用 ps1 文件名后缀将以下文本保存到 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="1584c-144">Save the following text to a Windows PowerShell script by using a filename suffix of .ps1.</span></span> <span data-ttu-id="1584c-145">例如，SearchAuditLog.ps1。</span><span class="sxs-lookup"><span data-stu-id="1584c-145">For example, SearchAuditLog.ps1.</span></span>

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
    $final = [DateTime]::Now.ToString("s") + ":" + $Message
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

    $sessionID = [DateTime]::Now.ToString("s")
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

2. <span data-ttu-id="1584c-146">修改下表中列出的变量以配置搜索条件。</span><span class="sxs-lookup"><span data-stu-id="1584c-146">Modify the variables listed in the following table to configure the search criteria.</span></span> <span data-ttu-id="1584c-147">脚本包括这些变量的示例值，但应对其进行更改（除非另有说明）以满足特定要求。</span><span class="sxs-lookup"><span data-stu-id="1584c-147">The script includes sample values for these variables, but you should change them (unless stated otherwise) to meet your specific requirements.</span></span>

   |<span data-ttu-id="1584c-148">变量</span><span class="sxs-lookup"><span data-stu-id="1584c-148">Variable</span></span>|<span data-ttu-id="1584c-149">示例值</span><span class="sxs-lookup"><span data-stu-id="1584c-149">Sample value</span></span>|<span data-ttu-id="1584c-150">说明</span><span class="sxs-lookup"><span data-stu-id="1584c-150">Description</span></span>|
   |---|---|---|
   |`$logFile`|<span data-ttu-id="1584c-151">"d:\temp\AuditSearchLog.txt"</span><span class="sxs-lookup"><span data-stu-id="1584c-151">"d:\temp\AuditSearchLog.txt"</span></span>|<span data-ttu-id="1584c-152">指定日志文件的名称和位置，其中包含有关脚本执行的审核日志搜索的进度信息。</span><span class="sxs-lookup"><span data-stu-id="1584c-152">Specifies the name and location for the log file that contains information about the progress of the audit log search performed by the script.</span></span>|
   |`$outputFile`|<span data-ttu-id="1584c-153">"d:\temp\AuditRecords.csv"</span><span class="sxs-lookup"><span data-stu-id="1584c-153">"d:\temp\AuditRecords.csv"</span></span>|<span data-ttu-id="1584c-154">指定包含脚本所返回的审核记录的 CSV 文件的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="1584c-154">Specifies the name and location of the CSV file that contains the audit records returned by the script.</span></span>|
   |<span data-ttu-id="1584c-155">`[DateTime]$start` 和 `[DateTime]$end`</span><span class="sxs-lookup"><span data-stu-id="1584c-155">`[DateTime]$start` and `[DateTime]$end`</span></span>|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|<span data-ttu-id="1584c-158">指定审核日志搜索的日期范围。</span><span class="sxs-lookup"><span data-stu-id="1584c-158">Specifies the date range for the audit log search.</span></span> <span data-ttu-id="1584c-159">该脚本将返回指定日期范围内发生的审核活动的记录。</span><span class="sxs-lookup"><span data-stu-id="1584c-159">The script will return records for audit activities that occurred within the specified date range.</span></span> <span data-ttu-id="1584c-160">例如，若要返回 2021 年 1 月执行的活动，可使用 `"2021-01-01"` 的开始日期和 `"2021-01-31"` 的结束日期（请确保用双引号括起值）脚本中的示例值将返回过去 24 小时内执行的活动的记录。</span><span class="sxs-lookup"><span data-stu-id="1584c-160">For example, to return activities performed in January 2021, you can use a start date of `"2021-01-01"` and an end date of `"2021-01-31"` (be sure to surround the values in double-quotation marks) The sample value in the script returns records for activities performed in the previous 24 hours.</span></span> <span data-ttu-id="1584c-161">如果值中不包含时间戳，则指定日期的默认时间戳为凌晨 12:00（午夜）。</span><span class="sxs-lookup"><span data-stu-id="1584c-161">If you don't include a timestamp in the value, the default timestamp is 12:00 AM (midnight) on the specified date.</span></span>|
   |`$record`|<span data-ttu-id="1584c-162">"AzureActiveDirectory"</span><span class="sxs-lookup"><span data-stu-id="1584c-162">"AzureActiveDirectory"</span></span>|<span data-ttu-id="1584c-163">指定要搜索的审计活动（也称为 *操作*）的记录类型。</span><span class="sxs-lookup"><span data-stu-id="1584c-163">Specifies the record type of the audit activities (also called *operations*) to search for.</span></span> <span data-ttu-id="1584c-164">此属性指示触发了活动的服务或功能。</span><span class="sxs-lookup"><span data-stu-id="1584c-164">This property indicates the service or feature that an activity was triggered in.</span></span> <span data-ttu-id="1584c-165">有关可用于此变量的记录类型的列表，请参阅[审核日志记录类型](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)。</span><span class="sxs-lookup"><span data-stu-id="1584c-165">For a list of record types that you can use for this variable, see [Audit log record type](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span> <span data-ttu-id="1584c-166">可以使用记录类型名称或 ENUM 值。</span><span class="sxs-lookup"><span data-stu-id="1584c-166">You can use the record type name or ENUM value.</span></span> <br/><br/><span data-ttu-id="1584c-167">**提示：** 若要返回所有记录类型的审核记录，请使用 `$null` 值（不带双引号）。</span><span class="sxs-lookup"><span data-stu-id="1584c-167">**Tip:** To return audit records for all record types, use the value `$null` (without double-quotations marks).</span></span>|
   |`$resultSize`|<span data-ttu-id="1584c-168">5000</span><span class="sxs-lookup"><span data-stu-id="1584c-168">5000</span></span>|<span data-ttu-id="1584c-169">指定脚本每次调用 **Search-UnifiedAuditLog** cmdlet 时返回的结果数（称为 *结果集*）。</span><span class="sxs-lookup"><span data-stu-id="1584c-169">Specifies the number of results returned each time the **Search-UnifiedAuditLog** cmdlet is called by the script (called a *result set*).</span></span> <span data-ttu-id="1584c-170">cmdlet 支持的最大值是 5,000。</span><span class="sxs-lookup"><span data-stu-id="1584c-170">The value of 5,000 is the maximum value supported by the cmdlet.</span></span> <span data-ttu-id="1584c-171">保留该值。</span><span class="sxs-lookup"><span data-stu-id="1584c-171">Leave this value as-is.</span></span>|
   |`$intervalMinutes`|<span data-ttu-id="1584c-172">60</span><span class="sxs-lookup"><span data-stu-id="1584c-172">60</span></span>|<span data-ttu-id="1584c-173">为了帮助克服返回 5000 条记录的限制，此变量将采用你指定的数据范围并将其划分到更小的时间间隔中。</span><span class="sxs-lookup"><span data-stu-id="1584c-173">To help overcome the limit of 5000 records returned, this variable takes the data range you specified and slices it up into smaller time intervals.</span></span> <span data-ttu-id="1584c-174">现在，每个间隔（并非整个日期范围）都受命令的 5000 条记录输出限制约束。</span><span class="sxs-lookup"><span data-stu-id="1584c-174">Now each interval, not the entire date range, is subject to the 5000 record output limit of the command.</span></span> <span data-ttu-id="1584c-175">对于大多数组织来说，日期范围内每 60 分钟间隔 5000 条记录的默认值应该已经足够。</span><span class="sxs-lookup"><span data-stu-id="1584c-175">The default value of 5000 records per 60-minute interval within the date range should be sufficient for most organizations.</span></span> <span data-ttu-id="1584c-176">但是，如果脚本返回 `maximum results limitation reached` 的错误，请缩短时间间隔（例如，减少到 30 分钟甚至 15 分钟），然后重新运行脚本。</span><span class="sxs-lookup"><span data-stu-id="1584c-176">But, if the script returns an error that says, `maximum results limitation reached`, decrease the time interval (for example, to 30 minutes or even 15 minutes) and rerun the script.</span></span>|
   ||||

   <span data-ttu-id="1584c-177">上表中列出的大多数变量都对应于 **Search-UnifiedAuditLog** cmdlet 的参数。</span><span class="sxs-lookup"><span data-stu-id="1584c-177">Most of the variables listed in the previous table correspond to parameters for the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="1584c-178">有关这些参数的详细信息，请参阅 [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)。</span><span class="sxs-lookup"><span data-stu-id="1584c-178">For more information about these parameters, see [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).</span></span>

3. <span data-ttu-id="1584c-179">在本地计算机上，打开 Windows PowerShell，然后转到保存修改后的脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1584c-179">On your local computer, open Windows PowerShell and go to the folder where you saved the modified script.</span></span>

4. <span data-ttu-id="1584c-180">在 Exchange Online PowerShell 中运行脚本；例如：</span><span class="sxs-lookup"><span data-stu-id="1584c-180">Run the script in Exchange Online PowerShell; for example:</span></span>

   ```powershell
   .\SearchAuditLog.ps1
   ```

<span data-ttu-id="1584c-181">该脚本在运行时显示进度消息。</span><span class="sxs-lookup"><span data-stu-id="1584c-181">The script displays progress messages while it's running.</span></span> <span data-ttu-id="1584c-182">脚本运行完成后，将创建包含审计记录的日志文件和 CSV 文件，并将它们保存到由 `$logFile` 和 `$outputFile` 变量定义的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1584c-182">After the script is finished running, it creates the log file and the CSV file that contains the audit records and saves them to the folders defined by the `$logFile` and `$outputFile` variables.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1584c-183">每次运行此脚本时返回的审计记录数上限为 50,000。</span><span class="sxs-lookup"><span data-stu-id="1584c-183">There is a 50,000 limit for the maximum number of audit records returned each time you run this script.</span></span> <span data-ttu-id="1584c-184">如果运行此脚本并返回 50,000 条结果，则很可能未包含日期范围内发生的活动的审核记录。</span><span class="sxs-lookup"><span data-stu-id="1584c-184">If you run this script and it returns 50,000 results, then it's likely that audit records for activities that occurred within the date range weren't included.</span></span> <span data-ttu-id="1584c-185">如果发生这种情况，建议将日期范围划分为更小的期间，然后针对每个日期范围重新运行脚本。</span><span class="sxs-lookup"><span data-stu-id="1584c-185">If this happens, we recommend that you divide the date range into smaller durations and then rerun the script for each date range.</span></span> <span data-ttu-id="1584c-186">例如，如果 90 天的日期范围返回 50,000 条结果，则可以重新运行脚本两次，对日期范围中的前 45 天重新运行一次，然后针对接下来 45 天再运行一次。</span><span class="sxs-lookup"><span data-stu-id="1584c-186">For example, if a date range of 90 days returns 50,000 results then you can rerun the script twice, once for the first 45 days in the date range and then again for the next 45 days.</span></span>

## <a name="step-3-format-and-view-the-audit-records"></a><span data-ttu-id="1584c-187">步骤 3：设置审核记录格式并查看</span><span class="sxs-lookup"><span data-stu-id="1584c-187">Step 3: Format and view the audit records</span></span>

<span data-ttu-id="1584c-188">运行脚本并将审核记录导出为 CSV 文件后，可能需要设置 CSV 格式，以便查看和分析审核记录。</span><span class="sxs-lookup"><span data-stu-id="1584c-188">After you've run the script and exported the audit records to a CSV file, you may want to format the CSV to make easier to review and analyze the audit records.</span></span> <span data-ttu-id="1584c-189">一种方法是使用 Excel 中的 Power Query JSON 转换功能，将 **AuditData** 列中 JSON 对象的每个属性拆分到各自的列中。</span><span class="sxs-lookup"><span data-stu-id="1584c-189">One way to do this is to the Power Query JSON transform feature in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="1584c-190">有关分步说明，请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)中的“步骤 2：使用 Power Query 编辑器转换 JSON 对象”。</span><span class="sxs-lookup"><span data-stu-id="1584c-190">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>
