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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: 了解如何生成包含与电子数据展示案例关联的所有保留信息的报告。
ms.openlocfilehash: 4da2b93ad9055363a5f8a7d61eff04270dfd00dc
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845864"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>创建电子数据展示事例中的保留的报告

借助本文中的脚本，电子数据展示管理员和电子数据展示管理员可生成一个报告，报告中包含在 Office 365 或 Microsoft 365 合规性中心中与电子数据展示案件集关联的所有保留项。 该报告包含与服务关联的事例的名称、内容位置以及该保留是否是基于查询的信息。 如果某些情况没有任何保留，脚本将创建另外一个包含未保留情况的事例列表的报告。

请参阅 ["详细信息"](#more-information) 部分，了解报告中所包含信息的详细说明。

## <a name="admin-requirements-and-script-information"></a>管理员要求和脚本信息

- 要生成有关组织中所有电子数据展示案例的报告，你必须是贵组织中的所有电子数据展示管理员。 如果你是电子数据展示管理员，该报告将仅包含可访问的事例的相关信息。 有关电子数据展示权限的详细信息，请参阅分配 [电子数据展示权限](assign-ediscovery-permissions.md)。

- 本文中的脚本对错误的处理进行了最少的处理。 主要用途是快速创建与组织中电子数据展示事例相关联的保留项的报告。

- 本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>步骤 1：连接到安全合&合规中心 PowerShell

第一步是连接到组织的&合规性中心 PowerShell。 有关分步说明，请参阅[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>步骤 2：运行脚本以报告与电子数据展示事例关联的保留项

连接到安全与合规 &中心 PowerShell 后，下一步是创建并运行收集有关组织中电子数据展示事例的信息的脚本。

1. 使用 .ps1 Windows PowerShell 文件名后缀将以下文本保存到脚本文件的一个移动脚本文件中;例如，CaseHoldsReport.ps1。

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

2. 在步骤 Windows PowerShell打开的文件夹的文件中，转到您将脚本保存到的文件夹。

3. 运行脚本;例如：

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   该脚本将提示选择要将报告保存到的目标文件夹。

4. 键入要将报表保存到的文件夹的完整路径名，然后按 **Enter**。

   > [!TIP]
   > 若要将该报表保存到该脚本所在的文件夹中，请键入句点 (号点"。) 目标文件夹提示时。 若要将该报表保存到脚本所在的文件夹所在文件夹的子文件夹中，只需键入该子文件夹的名称即可。

   脚本开始收集有关组织中的所有电子数据展示事例的信息。 脚本运行时，请勿访问报告文件。 脚本完成后，在会话中会显示Windows PowerShell消息。 显示此消息后，您可以访问在步骤 4 中指定的文件夹中的报告。 报表的文件名 `CaseHoldsReport<DateTimeStamp>.csv` 。

   此外，脚本还创建包含请注意不具有任何保留项的事例列表的报告。 此报表的文件名是 `CaseswithNoHolds<DateTimeStamp>.csv` .

   下面是运行 CaseHoldsReport.ps1 脚本的示例。

   ![运行后的输出CaseHoldsReport.ps1脚本](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>更多信息

当运行本文中的脚本时创建的事例保留报告包含有关每个保留的以下信息。 如前所述，必须是电子数据展示管理员才能返回组织中所有保留的信息。 有关案件集保留的详细信息，请参阅 [电子数据展示事例](ediscovery-cases.md)。

- 保留的名称和与保留相关联的电子数据展示事例的名称。

- 电子数据展示事例是否处于活动状态或关闭。

- 是启用还是禁用保留。

- 与保留相关联的电子数据展示事例的成员。 事例成员可以查看或管理事例，具体取决于他们分配的电子数据展示权限。

- 创建案例的时间和日期。

- 如果关闭案例，则关闭它的人员以及关闭时间和日期。

- 已保留的 Exchange 邮箱和 SharePoint 站点位置。

- 如果该保留是基于查询的，则查询语法。

- 创建保留的时间和日期以及创建保留项的人员。

- 上次更改保留的时间和日期，以及更改保留的人员。
