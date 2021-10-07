---
title: 创建电子数据展示事例中的保留的报告
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: 了解如何生成包含与电子数据展示事例关联的所有保留的信息的报告。
ms.openlocfilehash: 953b2aaa1b133d79b82f17e5f75603947cc5d6d7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200565"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>创建电子数据展示事例中的保留的报告

本文中的脚本允许电子数据展示管理员和电子数据展示管理员生成一个报告，其中包含有关与 Office 365 或 Microsoft 365 合规中心中的电子数据展示事例关联的所有保留的信息。 报告包含诸如与保留关联的案例的名称、置于保留状态的内容位置以及保留是否基于查询的信息。 如果存在没有任何保留的情况，脚本将创建一个附加报告，其中包含不含保留的事例列表。

有关 [报告中包含的](#more-information) 信息的详细说明，请参阅详细信息部分。

## <a name="admin-requirements-and-script-information"></a>管理员要求和脚本信息

- 若要生成有关组织中所有电子数据展示事例的报告，你必须是组织中电子数据展示管理员。 如果您是电子数据展示管理员，则报告将仅包含有关可以访问的事例的信息。 有关电子数据展示权限详细信息，请参阅分配 [电子数据展示权限](assign-ediscovery-permissions.md)。

- 本文中的脚本具有最少的错误处理。 主要用途是快速创建与组织中电子数据展示事例相关联的保留的报告。

- 本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。

## <a name="step-1-connect-to-security--compliance-center-powershell"></a>步骤 1：连接到安全与合规中心 PowerShell

第一步是为组织连接到安全与合规中心 PowerShell。 有关分步说明，请参阅[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>步骤 2：运行脚本以报告与电子数据展示事例关联的保留

连接到安全与合规& PowerShell 后，下一步是创建并运行收集组织中电子数据展示事例相关信息的脚本。

1. 将以下文本保存到Windows PowerShell脚本文件中，使用文件名后缀.ps1;例如，CaseHoldsReport.ps1。

   ```powershell
   #script begin
   " "
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "***********************************************"
   " "
   #prompt users to specify a path to store the output files
   $time=get-date
   $Path = Read-Host 'Enter a file path to save the report to a .csv file'
   $outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   $noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   #add case details to the csv file
   function add-tocasereport{
   Param([string]$casename,
   [String]$casestatus,
   [datetime]$casecreatedtime,
   [string]$casemembers,
   [datetime]$caseClosedDateTime,
   [string]$caseclosedby,
   [string]$holdname,
   [String]$Holdenabled,
   [string]$holdcreatedby,
   [string]$holdlastmodifiedby,
   [string]$ExchangeLocation,
   [string]$sharePointlocation,
   [string]$ContentMatchQuery,
   [datetime]$holdcreatedtime,
   [datetime]$holdchangedtime
   )
   $addRow = New-Object PSObject
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
   $allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
   $allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii
   }
   #get information on the cases and pass values to the case report function
   " "
   write-host "Gathering a list of cases and holds..."
   " "
   $edc =Get-ComplianceCase -ErrorAction SilentlyContinue
   foreach($cc in $edc)
   {
   write-host "Working on case :" $cc.name
   if($cc.status -eq 'Closed')
   {
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers
   }
   else{
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   $policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
   if ($policies -ne $NULL)
   {
   foreach ($policy in $policies)
   {
   $rule=Get-CaseHoldRule -Policy $policy.name
   add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
   }
   }
   else{
   write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
   " "
   [string]$cc.name | out-file -filepath $noholdsfilepath -append
   }
   }
   }

   " "
   Write-host "Script complete! Report files saved to this folder: '$Path'"
   " "
   #script end
   ```

2. 在Windows PowerShell 1 中打开的会话，转到保存脚本的文件夹。

3. 运行脚本;例如：

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   脚本将提示目标文件夹将报告保存到该文件夹。

4. 键入要保存报告的文件夹的完整路径名称，然后按 **Enter。**

   > [!TIP]
   > 若要将报告保存在脚本所在的同一文件夹中，请键入一个 ("。") 目标文件夹时显示。 若要将报表保存在脚本所在的文件夹的子文件夹中，只需键入子文件夹的名称。

   脚本开始收集有关组织中所有电子数据展示事例的信息。 脚本运行时，请勿访问报告文件。 脚本完成后，在脚本会话中将显示一条Windows PowerShell消息。 显示此消息后，可以访问在步骤 4 中指定的文件夹中的报告。 报告的文件名为 `CaseHoldsReport<DateTimeStamp>.csv` 。

   此外，脚本还会创建一个包含没有任何保留案例列表的报告。 此报告的文件名为 `CaseswithNoHolds<DateTimeStamp>.csv` 。

   下面是运行 CaseHoldsReport.ps1 脚本的示例。

   ![运行脚本后的输出CaseHoldsReport.ps1脚本。](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>更多信息

在您运行本文中的脚本时创建的保留报告包含有关每个保留的以下信息。 如前所述，你必须是电子数据展示管理员才能返回组织中所有保留的信息。 有关事例保留详细信息，请参阅 [电子数据展示事例](./get-started-core-ediscovery.md)。

- 保留的名称和与保留关联的电子数据展示案例的名称。

- 电子数据展示案例是否处于活动状态或已关闭。

- 是否启用或禁用保留。

- 与保留关联的电子数据展示案例的成员。 案例成员可以查看或管理案例，具体取决于他们分配了电子数据展示权限。

- 案例的创建时间和日期。

- 如果案例已关闭，则关闭案例的人以及关闭它的时间和日期。

- The Exchange mailboxes and SharePoint sites locations that are on hold.

- 如果保留基于查询，则查询语法。

- 创建保留的时间和日期以及创建它的人。

- 上次更改保留的时间和日期以及更改它的人。