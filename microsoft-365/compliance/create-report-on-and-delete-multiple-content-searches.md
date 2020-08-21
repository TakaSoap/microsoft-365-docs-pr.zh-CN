---
title: 创建、报告和删除多个内容搜索
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 了解如何自动执行内容搜索任务，如在 Office 365 的安全与&合规中心内通过 PowerShell 脚本创建搜索和运行报告。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d748e12942fa2d634f27c04de37ccf5b3ec19297
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845894"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>创建、报告和删除多个内容搜索

 在尝试了解基础数据和搜索的丰富度和质量时，快速创建并报告发现搜索通常是电子数据展示和调查的重要步骤。 为了帮助你执行此操作，安全 &中心 PowerShell 提供了一组用于自动执行耗时内容搜索任务的 cmdlet。 这些脚本可以快速、简单地创建多个搜索，然后生成估计的搜索结果报告，以帮助您确定相关数据量。 还可以使用脚本创建不同版本的搜索来比较每种搜索结果的结果。 这些脚本有助于快速高效地识别和提示数据。

## <a name="before-you-create-a-content-search"></a>创建内容搜索之前

- 您必须是安全 & 合规中心电子数据展示管理员角色组的成员才能运行本主题中所述的脚本。

- 若要收集您所在组织中 OneDrive for Business 站点的 URL 列表（可将其添加到步骤 1 中的 CSV 文件），请参阅["创建组织中所有 OneDrive 位置的列表"。](https://docs.microsoft.com/onedrive/list-onedrive-urls)

- 请务必将本主题中创建的所有文件都保存到同一文件夹中。 这将使运行脚本更加容易。

- 脚本包含最少的错误处理。 他们的主要目的是快速创建、报告和删除多个内容搜索。

- 本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>步骤 1：创建包含有关您要运行的搜索信息的 CSV 文件

在此步骤中创建的 (CSV) 文件中的每一行，其中每一行都对应一个需要搜索的各个用户。 如果已启用存档邮箱及其 OneDrive for Business (，你可以搜索用户的 Exchange Online 邮箱) 和它们的 OneDrive for Business 网站。 或者，可以仅搜索邮箱或 OneDrive for Business 网站。 您还可以搜索 SharePoint Online 组织中的所有网站。 您在步骤 3 中运行的脚本将对 CSV 文件中的每一行单独搜索。

1. 使用记事本将以下文本复制并粘贴到 .txt 文件中。 将此文件保存到本地计算机上的文件夹中。 你还会将其他脚本保存到此文件夹。

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   文件的第一行（或者说标题行）列出 **了将由 New-ComplianceSearch** cmdlet (步骤 3 中脚本中的参数) 创建新的内容搜索。 每个参数名称都用逗号分隔开。 确保标题行中没有空格。 标题行下面的每行都表示每个搜索的参数值。 一定要用实际数据替换 CSV 文件中的占位符数据。

2. 在 Excel 中打开 .txt 文件，然后使用下表中的信息编辑文件并提供有关每个搜索的信息。

   ****

   |参数|说明|
   |---|---|
   |`ExchangeLocation`|用户邮箱的 SMTP 地址。|
   |`SharePointLocation`|用户的 OneDrive for Business 网站的 URL 或组织中任何网站的 URL。 对于 OneDrive for Business 网站的 URL，请使用以下格式 ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` ： 例如，`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。|
   |`ContentMatchQuery`|搜索的搜索查询。 有关创建搜索查询的详细信息，请参阅 [关键字查询和内容搜索的搜索条件](keyword-queries-and-search-conditions.md)。|
   |`StartDate`|对于电子邮件而说，是收件人接收邮件的日期或发件人发送邮件的日期。 对于 SharePoint 或 OneDrive for Business 网站上文档的最新日期（有关文档最近修改的日期或之后）。|
   |`EndDate`|对于电子邮件而说，是用户发送邮件发送的日期（与电子邮件打开前或之前） 的邮件。 对于 SharePoint 或 OneDrive for Business 网站上文档的最新日期（有关文档最近修改的日期或之前的日期）。|
   |

3. 将 Excel 文件以 CSV 文件形式保存到你的本地计算机上的某个文件夹中。 您在步骤 3 中创建的脚本将使用此 CSV 文件中的信息创建搜索。

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>步骤 2：连接到安全与合规中心 PowerShell

下一步是连接到组织的安全与合规中心 PowerShell。 有关分步说明，请参阅[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>步骤 3：运行脚本以创建并启动搜索

此步骤中的脚本将为您在步骤 1 中创建的 CSV 文件中的每一行分别创建单独的内容搜索。 运行此脚本时，系统会提示您输入两个值：

- **搜索组 ID** - 该名称提供了一种组织通过 CSV 文件创建的搜索的简便方法。 创建的每个搜索都使用搜索组 ID 命名，然后将一个数字追加到搜索名称之后。 例如，如果输入**ContosoCase**的搜索组 ID，则搜索的名称**分ContosoCase_1、ContosoCase_2** **ContosoCase_2** **、ContosoCase_3，** 等等。 请注意，您键入的名称区分大小写。 当您在步骤 4 和步骤 5 中使用搜索组 ID 时，使用的大小写必须与您创建它时的大小写相同。

- **CSV 文件** - 在步骤 1 中创建的 CSV 文件的名称。 请务必包括使用完整文件名，包含文件扩展名 .csv;例如，  `ContosoCase.csv` _

若要运行该脚本，请执行下列操作：

1. 使用 .ps1 Windows PowerShell 文件名后缀将以下文本保存到脚本文件的一个移动脚本文件中;例如， `CreateSearches.ps1` _ 将该文件保存到保存其他文件所在的相同文件夹中。

   ```Powershell
   # Get the Search Group ID and the location of the CSV input file
   $searchGroup = Read-Host 'Search Group ID'
   $csvFile = Read-Host 'Source CSV file'

   # Do a quick check to make sure our group name will not collide with other searches
   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

     $searchName = $searchGroup +'_' + $searchCounter
     $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
     if ($search)
     {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
     }
     $searchCounter++
   }

   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

     # Create the query
     $query = $_.ContentMatchQuery
     if(($_.StartDate -or $_.EndDate))
     {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
     }

     # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
     $exchangeLocation = $null
     if ( $_.ExchangeLocation)
     {
           $exchangeLocation = $_.ExchangeLocation
     }

     # Create and run the search
     $searchName = $searchGroup +'_' + $searchCounter
     Write-Host "Creating and running search: " $searchName -NoNewline
     $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query

     # Start and wait for each search to complete
     Start-ComplianceSearch $search.Name
     while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
     {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
     }
     Write-Host ""

     $searchCounter++
   }
   ```

2. 在Windows PowerShell中，转到上一步中保存该脚本的文件夹，然后运行该脚本;例如：

   ```Powershell
   .\CreateSearches.ps1
   ```

3. 在搜索 **组 ID** 提示符下键入搜索组名称，然后按 **Enter**。例如，  `ContosoCase` _ 请记住，此名称区分大小写，因此必须按照与后续步骤中的相同方式键入它。

4. 在 **源 CSV 文件提示** 符下，键入 CSV 文件的名称，包括 .csv 文件扩展名;例如，  `ContosoCase.csv` _

5. 按 **Enter** 继续运行脚本。

   该脚本显示创建和运行搜索的进度。 脚本完成后，它将返回到提示符。

   ![运行该脚本以创建多个合规性搜索的示例输出](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>步骤 4：运行脚本报告搜索估计

创建搜索之后，下一步是运行一个脚本，该脚本显示一个简单的报告，该报告显示在步骤 3 中创建的每个搜索的搜索点数的简单报告。 报告还包含每个搜索的结果大小以及所有搜索的结果总数和总大小。 运行报告脚本时，系统会提示你输入搜索组 ID，如果要将报告保存到 CSV 文件，系统会显示 CSV 文件名。

1. 使用 .ps1 Windows PowerShell 文件名后缀将以下文本保存到脚本文件的一个移动脚本文件中;例如， `SearchReport.ps1` _ 将该文件保存到保存其他文件所在的相同文件夹中。

   ```Powershell
   $searchGroup = Read-Host 'Search Group ID'
   $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
   $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
   $allSearchStats = @()
   foreach ($partialObj in $searches)
   {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
   }
   # Calculate the totals
   $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
   # Convert the total size to MB and round to the nearst 100th
   $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
   $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
   # Get the total successful searches and total of all searches
   $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
   $allCount = $allSearchStats.Count
   $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
   # Totals Row
   $totalSearchStats = New-Object PSObject
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
   $allSearchStats += $totalSearchStats
   # Just get the columns we're interested in showing
   $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
   # Print the results to the screen
   $allSearchStatsPrime |ft -AutoSize -Wrap
   # Save the results to a CSV file
   if ($outputFile)
   {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
   }
   ```

2. 在Windows PowerShell中，转到上一步中保存该脚本的文件夹，然后运行该脚本;例如：

   ```Powershell
   .\SearchReport.ps1
   ```

3. 在搜索 **组 ID** 提示符下键入搜索组名称，然后按 **Enter**。例如  `ContosoCase` 。 请记住，此名称区分大小写，因此您必须使用在步骤 3 中运行脚本时所采用的方式来键入它。

4. 在文件 **路径中，将报告保存到 CSV 文件 (将报告保留为空以仅显示报告) ** 提示，键入完整文件名路径 (的文件名称，包括 .csv 文件扩展名) 如果您想将报告保存到 CSV 文件。 CSV 文件的名称，包括 .csv 文件扩展名。 例如，可以键入  `ContosoCaseReport.csv` 将其保存到当前目录，也可以键入  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` 将其保存到其他文件夹中。 你也可以将提示留空以显示报表，但不将报表保存到文件中。

5. 按 Enter**** 键。

   该脚本显示创建和运行搜索的进度。 脚本完成后，将显示报表。

   ![运行搜索报告以显示对搜索组的估计](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> 如果在搜索组的多个搜索中将同一个邮箱或网站指定为内容位置，则报告 (中所有项目和总大小) 的总结果估计值可能包含相同项目的结果。 这是因为，如果同一电子邮件或文档与搜索组中不同搜索的查询相匹配，这会多次计数。

## <a name="step-5-run-the-script-to-delete-the-searches"></a>步骤 5：运行脚本以删除搜索

由于可能会创建大量搜索，因此，此最后一个脚本只是使快速删除在步骤 3 中创建的搜索轻松。 与其他脚本一样，该脚本也会提示您输入搜索组 ID。 运行此脚本时，搜索名称中搜索组 ID 的所有搜索都将被删除。

1. 使用 .ps1 Windows PowerShell 文件名后缀将以下文本保存到脚本文件的一个移动脚本文件中;例如， `DeleteSearches.ps1` _ 将该文件保存到保存其他文件所在的相同文件夹中。

   ```Powershell
   # Delete all searches in a search group
   $searchGroup = Read-Host 'Search Group ID'
   Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
   }
   ```

2. 在Windows PowerShell中，转到上一步中保存该脚本的文件夹，然后运行该脚本;例如：

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. 在 **搜索组 ID** 提示符处，为要删除的搜索键入一个搜索组名称，然后按 **Enter**。例如，  `ContosoCase` _ 请记住，此名称区分大小写，因此您必须使用在步骤 3 中运行脚本时所采用的方式来键入它。

   该脚本显示已删除的每个搜索的名称。

   ![运行该脚本以删除搜索组中的搜索](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
