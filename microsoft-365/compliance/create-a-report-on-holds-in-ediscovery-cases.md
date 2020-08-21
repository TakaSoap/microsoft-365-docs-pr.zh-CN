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
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="a3fb7-103">创建电子数据展示事例中的保留的报告</span><span class="sxs-lookup"><span data-stu-id="a3fb7-103">Create a report on holds in eDiscovery cases</span></span>

<span data-ttu-id="a3fb7-104">借助本文中的脚本，电子数据展示管理员和电子数据展示管理员可生成一个报告，报告中包含在 Office 365 或 Microsoft 365 合规性中心中与电子数据展示案件集关联的所有保留项。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="a3fb7-105">该报告包含与服务关联的事例的名称、内容位置以及该保留是否是基于查询的信息。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="a3fb7-106">如果某些情况没有任何保留，脚本将创建另外一个包含未保留情况的事例列表的报告。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="a3fb7-107">请参阅 ["详细信息"](#more-information) 部分，了解报告中所包含信息的详细说明。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>

## <a name="admin-requirements-and-script-information"></a><span data-ttu-id="a3fb7-108">管理员要求和脚本信息</span><span class="sxs-lookup"><span data-stu-id="a3fb7-108">Admin requirements and script information</span></span>

- <span data-ttu-id="a3fb7-109">要生成有关组织中所有电子数据展示案例的报告，你必须是贵组织中的所有电子数据展示管理员。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="a3fb7-110">如果你是电子数据展示管理员，该报告将仅包含可访问的事例的相关信息。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="a3fb7-111">有关电子数据展示权限的详细信息，请参阅分配 [电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="a3fb7-112">本文中的脚本对错误的处理进行了最少的处理。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="a3fb7-113">主要用途是快速创建与组织中电子数据展示事例相关联的保留项的报告。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>

- <span data-ttu-id="a3fb7-p104">本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="a3fb7-119">步骤 1：连接到安全合&合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3fb7-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="a3fb7-120">第一步是连接到组织的&合规性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-120">The first step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="a3fb7-121">有关分步说明，请参阅[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-121">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="a3fb7-122">步骤 2：运行脚本以报告与电子数据展示事例关联的保留项</span><span class="sxs-lookup"><span data-stu-id="a3fb7-122">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="a3fb7-123">连接到安全与合规 &中心 PowerShell 后，下一步是创建并运行收集有关组织中电子数据展示事例的信息的脚本。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-123">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span>

1. <span data-ttu-id="a3fb7-124">使用 .ps1 Windows PowerShell 文件名后缀将以下文本保存到脚本文件的一个移动脚本文件中;例如，CaseHoldsReport.ps1。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-124">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span>

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

2. <span data-ttu-id="a3fb7-125">在步骤 Windows PowerShell打开的文件夹的文件中，转到您将脚本保存到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-125">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="a3fb7-126">运行脚本;例如：</span><span class="sxs-lookup"><span data-stu-id="a3fb7-126">Run the script; for example:</span></span>

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   <span data-ttu-id="a3fb7-127">该脚本将提示选择要将报告保存到的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-127">The script will prompt for a target folder to save the report to.</span></span>

4. <span data-ttu-id="a3fb7-128">键入要将报表保存到的文件夹的完整路径名，然后按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-128">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>

   > [!TIP]
   > <span data-ttu-id="a3fb7-129">若要将该报表保存到该脚本所在的文件夹中，请键入句点 (号点"。) 目标文件夹提示时。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-129">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="a3fb7-130">若要将该报表保存到脚本所在的文件夹所在文件夹的子文件夹中，只需键入该子文件夹的名称即可。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-130">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span>

   <span data-ttu-id="a3fb7-131">脚本开始收集有关组织中的所有电子数据展示事例的信息。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-131">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="a3fb7-132">脚本运行时，请勿访问报告文件。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-132">Don't access the report file while the script is running.</span></span> <span data-ttu-id="a3fb7-133">脚本完成后，在会话中会显示Windows PowerShell消息。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-133">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="a3fb7-134">显示此消息后，您可以访问在步骤 4 中指定的文件夹中的报告。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-134">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="a3fb7-135">报表的文件名 `CaseHoldsReport<DateTimeStamp>.csv` 。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-135">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="a3fb7-136">此外，脚本还创建包含请注意不具有任何保留项的事例列表的报告。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-136">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="a3fb7-137">此报表的文件名是 `CaseswithNoHolds<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="a3fb7-137">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="a3fb7-138">下面是运行 CaseHoldsReport.ps1 脚本的示例。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-138">Here's an example of running the CaseHoldsReport.ps1 script.</span></span>

   ![运行后的输出CaseHoldsReport.ps1脚本](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a><span data-ttu-id="a3fb7-140">更多信息</span><span class="sxs-lookup"><span data-stu-id="a3fb7-140">More information</span></span>

<span data-ttu-id="a3fb7-141">当运行本文中的脚本时创建的事例保留报告包含有关每个保留的以下信息。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-141">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="a3fb7-142">如前所述，必须是电子数据展示管理员才能返回组织中所有保留的信息。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-142">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="a3fb7-143">有关案件集保留的详细信息，请参阅 [电子数据展示事例](ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-143">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>

- <span data-ttu-id="a3fb7-144">保留的名称和与保留相关联的电子数据展示事例的名称。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-144">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>

- <span data-ttu-id="a3fb7-145">电子数据展示事例是否处于活动状态或关闭。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-145">Whether or not the eDiscovery case is active or closed.</span></span>

- <span data-ttu-id="a3fb7-146">是启用还是禁用保留。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-146">Whether or not the hold is enabled or disabled.</span></span>

- <span data-ttu-id="a3fb7-147">与保留相关联的电子数据展示事例的成员。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-147">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="a3fb7-148">事例成员可以查看或管理事例，具体取决于他们分配的电子数据展示权限。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-148">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>

- <span data-ttu-id="a3fb7-149">创建案例的时间和日期。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-149">The time and date the case was created.</span></span>

- <span data-ttu-id="a3fb7-150">如果关闭案例，则关闭它的人员以及关闭时间和日期。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-150">If a case is closed, the person who closed it and the time and date it was closed.</span></span>

- <span data-ttu-id="a3fb7-151">已保留的 Exchange 邮箱和 SharePoint 站点位置。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-151">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>

- <span data-ttu-id="a3fb7-152">如果该保留是基于查询的，则查询语法。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-152">If the hold is query-based, the query syntax.</span></span>

- <span data-ttu-id="a3fb7-153">创建保留的时间和日期以及创建保留项的人员。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-153">The time and date the hold was created and the person who created it.</span></span>

- <span data-ttu-id="a3fb7-154">上次更改保留的时间和日期，以及更改保留的人员。</span><span class="sxs-lookup"><span data-stu-id="a3fb7-154">The time and date the hold was last changed and the person who changed it.</span></span>
