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
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="f9549-103">创建、报告和删除多个内容搜索</span><span class="sxs-lookup"><span data-stu-id="f9549-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="f9549-104">在尝试了解基础数据和搜索的丰富度和质量时，快速创建并报告发现搜索通常是电子数据展示和调查的重要步骤。</span><span class="sxs-lookup"><span data-stu-id="f9549-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="f9549-105">为了帮助你执行此操作，安全 &中心 PowerShell 提供了一组用于自动执行耗时内容搜索任务的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9549-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="f9549-106">这些脚本可以快速、简单地创建多个搜索，然后生成估计的搜索结果报告，以帮助您确定相关数据量。</span><span class="sxs-lookup"><span data-stu-id="f9549-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="f9549-107">还可以使用脚本创建不同版本的搜索来比较每种搜索结果的结果。</span><span class="sxs-lookup"><span data-stu-id="f9549-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="f9549-108">这些脚本有助于快速高效地识别和提示数据。</span><span class="sxs-lookup"><span data-stu-id="f9549-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span>

## <a name="before-you-create-a-content-search"></a><span data-ttu-id="f9549-109">创建内容搜索之前</span><span class="sxs-lookup"><span data-stu-id="f9549-109">Before you create a Content Search</span></span>

- <span data-ttu-id="f9549-110">您必须是安全 & 合规中心电子数据展示管理员角色组的成员才能运行本主题中所述的脚本。</span><span class="sxs-lookup"><span data-stu-id="f9549-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span>

- <span data-ttu-id="f9549-111">若要收集您所在组织中 OneDrive for Business 站点的 URL 列表（可将其添加到步骤 1 中的 CSV 文件），请参阅["创建组织中所有 OneDrive 位置的列表"。](https://docs.microsoft.com/onedrive/list-onedrive-urls)</span><span class="sxs-lookup"><span data-stu-id="f9549-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

- <span data-ttu-id="f9549-112">请务必将本主题中创建的所有文件都保存到同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f9549-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="f9549-113">这将使运行脚本更加容易。</span><span class="sxs-lookup"><span data-stu-id="f9549-113">That will make it easier to run the scripts.</span></span>

- <span data-ttu-id="f9549-114">脚本包含最少的错误处理。</span><span class="sxs-lookup"><span data-stu-id="f9549-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="f9549-115">他们的主要目的是快速创建、报告和删除多个内容搜索。</span><span class="sxs-lookup"><span data-stu-id="f9549-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>

- <span data-ttu-id="f9549-p104">本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。</span><span class="sxs-lookup"><span data-stu-id="f9549-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="f9549-121">步骤 1：创建包含有关您要运行的搜索信息的 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="f9549-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="f9549-122">在此步骤中创建的 (CSV) 文件中的每一行，其中每一行都对应一个需要搜索的各个用户。</span><span class="sxs-lookup"><span data-stu-id="f9549-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="f9549-123">如果已启用存档邮箱及其 OneDrive for Business (，你可以搜索用户的 Exchange Online 邮箱) 和它们的 OneDrive for Business 网站。</span><span class="sxs-lookup"><span data-stu-id="f9549-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="f9549-124">或者，可以仅搜索邮箱或 OneDrive for Business 网站。</span><span class="sxs-lookup"><span data-stu-id="f9549-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="f9549-125">您还可以搜索 SharePoint Online 组织中的所有网站。</span><span class="sxs-lookup"><span data-stu-id="f9549-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="f9549-126">您在步骤 3 中运行的脚本将对 CSV 文件中的每一行单独搜索。</span><span class="sxs-lookup"><span data-stu-id="f9549-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span>

1. <span data-ttu-id="f9549-127">使用记事本将以下文本复制并粘贴到 .txt 文件中。</span><span class="sxs-lookup"><span data-stu-id="f9549-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="f9549-128">将此文件保存到本地计算机上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f9549-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="f9549-129">你还会将其他脚本保存到此文件夹。</span><span class="sxs-lookup"><span data-stu-id="f9549-129">You'll save the other scripts to this folder as well.</span></span>

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   <span data-ttu-id="f9549-130">文件的第一行（或者说标题行）列出 **了将由 New-ComplianceSearch** cmdlet (步骤 3 中脚本中的参数) 创建新的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="f9549-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="f9549-131">每个参数名称都用逗号分隔开。</span><span class="sxs-lookup"><span data-stu-id="f9549-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="f9549-132">确保标题行中没有空格。</span><span class="sxs-lookup"><span data-stu-id="f9549-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="f9549-133">标题行下面的每行都表示每个搜索的参数值。</span><span class="sxs-lookup"><span data-stu-id="f9549-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="f9549-134">一定要用实际数据替换 CSV 文件中的占位符数据。</span><span class="sxs-lookup"><span data-stu-id="f9549-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span>

2. <span data-ttu-id="f9549-135">在 Excel 中打开 .txt 文件，然后使用下表中的信息编辑文件并提供有关每个搜索的信息。</span><span class="sxs-lookup"><span data-stu-id="f9549-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span>

   ****

   |<span data-ttu-id="f9549-136">参数</span><span class="sxs-lookup"><span data-stu-id="f9549-136">Parameter</span></span>|<span data-ttu-id="f9549-137">说明</span><span class="sxs-lookup"><span data-stu-id="f9549-137">Description</span></span>|
   |---|---|
   |`ExchangeLocation`|<span data-ttu-id="f9549-138">用户邮箱的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="f9549-138">The SMTP address of the user's mailbox.</span></span>|
   |`SharePointLocation`|<span data-ttu-id="f9549-139">用户的 OneDrive for Business 网站的 URL 或组织中任何网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="f9549-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="f9549-140">对于 OneDrive for Business 网站的 URL，请使用以下格式 ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` ：</span><span class="sxs-lookup"><span data-stu-id="f9549-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="f9549-141">例如，`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。</span><span class="sxs-lookup"><span data-stu-id="f9549-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>|
   |`ContentMatchQuery`|<span data-ttu-id="f9549-142">搜索的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="f9549-142">The search query for the search.</span></span> <span data-ttu-id="f9549-143">有关创建搜索查询的详细信息，请参阅 [关键字查询和内容搜索的搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="f9549-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>|
   |`StartDate`|<span data-ttu-id="f9549-144">对于电子邮件而说，是收件人接收邮件的日期或发件人发送邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="f9549-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="f9549-145">对于 SharePoint 或 OneDrive for Business 网站上文档的最新日期（有关文档最近修改的日期或之后）。</span><span class="sxs-lookup"><span data-stu-id="f9549-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>|
   |`EndDate`|<span data-ttu-id="f9549-146">对于电子邮件而说，是用户发送邮件发送的日期（与电子邮件打开前或之前） 的邮件。</span><span class="sxs-lookup"><span data-stu-id="f9549-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="f9549-147">对于 SharePoint 或 OneDrive for Business 网站上文档的最新日期（有关文档最近修改的日期或之前的日期）。</span><span class="sxs-lookup"><span data-stu-id="f9549-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>|
   |

3. <span data-ttu-id="f9549-148">将 Excel 文件以 CSV 文件形式保存到你的本地计算机上的某个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f9549-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="f9549-149">您在步骤 3 中创建的脚本将使用此 CSV 文件中的信息创建搜索。</span><span class="sxs-lookup"><span data-stu-id="f9549-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span>

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="f9549-150">步骤 2：连接到安全与合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9549-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="f9549-151">下一步是连接到组织的安全与合规中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f9549-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="f9549-152">有关分步说明，请参阅[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f9549-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="f9549-153">步骤 3：运行脚本以创建并启动搜索</span><span class="sxs-lookup"><span data-stu-id="f9549-153">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="f9549-154">此步骤中的脚本将为您在步骤 1 中创建的 CSV 文件中的每一行分别创建单独的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="f9549-154">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="f9549-155">运行此脚本时，系统会提示您输入两个值：</span><span class="sxs-lookup"><span data-stu-id="f9549-155">When you run this script, you'll be prompted for two values:</span></span>

- <span data-ttu-id="f9549-156">**搜索组 ID** - 该名称提供了一种组织通过 CSV 文件创建的搜索的简便方法。</span><span class="sxs-lookup"><span data-stu-id="f9549-156">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="f9549-157">创建的每个搜索都使用搜索组 ID 命名，然后将一个数字追加到搜索名称之后。</span><span class="sxs-lookup"><span data-stu-id="f9549-157">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="f9549-158">例如，如果输入**ContosoCase**的搜索组 ID，则搜索的名称**分ContosoCase_1、ContosoCase_2** **ContosoCase_2** **、ContosoCase_3，** 等等。</span><span class="sxs-lookup"><span data-stu-id="f9549-158">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="f9549-159">请注意，您键入的名称区分大小写。</span><span class="sxs-lookup"><span data-stu-id="f9549-159">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="f9549-160">当您在步骤 4 和步骤 5 中使用搜索组 ID 时，使用的大小写必须与您创建它时的大小写相同。</span><span class="sxs-lookup"><span data-stu-id="f9549-160">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span>

- <span data-ttu-id="f9549-161">**CSV 文件** - 在步骤 1 中创建的 CSV 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f9549-161">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="f9549-162">请务必包括使用完整文件名，包含文件扩展名 .csv;例如，  `ContosoCase.csv` _</span><span class="sxs-lookup"><span data-stu-id="f9549-162">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

<span data-ttu-id="f9549-163">若要运行该脚本，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f9549-163">To run the script:</span></span>

1. <span data-ttu-id="f9549-164">使用 .ps1 Windows PowerShell 文件名后缀将以下文本保存到脚本文件的一个移动脚本文件中;例如， `CreateSearches.ps1` _</span><span class="sxs-lookup"><span data-stu-id="f9549-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="f9549-165">将该文件保存到保存其他文件所在的相同文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f9549-165">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="f9549-166">在Windows PowerShell中，转到上一步中保存该脚本的文件夹，然后运行该脚本;例如：</span><span class="sxs-lookup"><span data-stu-id="f9549-166">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\CreateSearches.ps1
   ```

3. <span data-ttu-id="f9549-167">在搜索 **组 ID** 提示符下键入搜索组名称，然后按 **Enter**。例如，  `ContosoCase` _</span><span class="sxs-lookup"><span data-stu-id="f9549-167">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="f9549-168">请记住，此名称区分大小写，因此必须按照与后续步骤中的相同方式键入它。</span><span class="sxs-lookup"><span data-stu-id="f9549-168">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>

4. <span data-ttu-id="f9549-169">在 **源 CSV 文件提示** 符下，键入 CSV 文件的名称，包括 .csv 文件扩展名;例如，  `ContosoCase.csv` _</span><span class="sxs-lookup"><span data-stu-id="f9549-169">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

5. <span data-ttu-id="f9549-170">按 **Enter** 继续运行脚本。</span><span class="sxs-lookup"><span data-stu-id="f9549-170">Press **Enter** to continue running the script.</span></span>

   <span data-ttu-id="f9549-171">该脚本显示创建和运行搜索的进度。</span><span class="sxs-lookup"><span data-stu-id="f9549-171">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="f9549-172">脚本完成后，它将返回到提示符。</span><span class="sxs-lookup"><span data-stu-id="f9549-172">When the script is complete, it returns to the prompt.</span></span>

   ![运行该脚本以创建多个合规性搜索的示例输出](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="f9549-174">步骤 4：运行脚本报告搜索估计</span><span class="sxs-lookup"><span data-stu-id="f9549-174">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="f9549-175">创建搜索之后，下一步是运行一个脚本，该脚本显示一个简单的报告，该报告显示在步骤 3 中创建的每个搜索的搜索点数的简单报告。</span><span class="sxs-lookup"><span data-stu-id="f9549-175">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="f9549-176">报告还包含每个搜索的结果大小以及所有搜索的结果总数和总大小。</span><span class="sxs-lookup"><span data-stu-id="f9549-176">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="f9549-177">运行报告脚本时，系统会提示你输入搜索组 ID，如果要将报告保存到 CSV 文件，系统会显示 CSV 文件名。</span><span class="sxs-lookup"><span data-stu-id="f9549-177">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>

1. <span data-ttu-id="f9549-178">使用 .ps1 Windows PowerShell 文件名后缀将以下文本保存到脚本文件的一个移动脚本文件中;例如， `SearchReport.ps1` _</span><span class="sxs-lookup"><span data-stu-id="f9549-178">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="f9549-179">将该文件保存到保存其他文件所在的相同文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f9549-179">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="f9549-180">在Windows PowerShell中，转到上一步中保存该脚本的文件夹，然后运行该脚本;例如：</span><span class="sxs-lookup"><span data-stu-id="f9549-180">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\SearchReport.ps1
   ```

3. <span data-ttu-id="f9549-181">在搜索 **组 ID** 提示符下键入搜索组名称，然后按 **Enter**。例如  `ContosoCase` 。</span><span class="sxs-lookup"><span data-stu-id="f9549-181">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="f9549-182">请记住，此名称区分大小写，因此您必须使用在步骤 3 中运行脚本时所采用的方式来键入它。</span><span class="sxs-lookup"><span data-stu-id="f9549-182">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

4. <span data-ttu-id="f9549-183">在文件 \*\*路径中，将报告保存到 CSV 文件 (将报告保留为空以仅显示报告) \*\* 提示，键入完整文件名路径 (的文件名称，包括 .csv 文件扩展名) 如果您想将报告保存到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="f9549-183">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="f9549-184">CSV 文件的名称，包括 .csv 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="f9549-184">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="f9549-185">例如，可以键入  `ContosoCaseReport.csv` 将其保存到当前目录，也可以键入  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` 将其保存到其他文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f9549-185">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="f9549-186">你也可以将提示留空以显示报表，但不将报表保存到文件中。</span><span class="sxs-lookup"><span data-stu-id="f9549-186">You can also leave the prompt blank to display the report but not save it to a file.</span></span>

5. <span data-ttu-id="f9549-187">按 Enter\*\*\*\* 键。</span><span class="sxs-lookup"><span data-stu-id="f9549-187">Press **Enter**.</span></span>

   <span data-ttu-id="f9549-188">该脚本显示创建和运行搜索的进度。</span><span class="sxs-lookup"><span data-stu-id="f9549-188">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="f9549-189">脚本完成后，将显示报表。</span><span class="sxs-lookup"><span data-stu-id="f9549-189">When the script is complete, the report is displayed.</span></span>

   ![运行搜索报告以显示对搜索组的估计](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> <span data-ttu-id="f9549-191">如果在搜索组的多个搜索中将同一个邮箱或网站指定为内容位置，则报告 (中所有项目和总大小) 的总结果估计值可能包含相同项目的结果。</span><span class="sxs-lookup"><span data-stu-id="f9549-191">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="f9549-192">这是因为，如果同一电子邮件或文档与搜索组中不同搜索的查询相匹配，这会多次计数。</span><span class="sxs-lookup"><span data-stu-id="f9549-192">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span>

## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="f9549-193">步骤 5：运行脚本以删除搜索</span><span class="sxs-lookup"><span data-stu-id="f9549-193">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="f9549-194">由于可能会创建大量搜索，因此，此最后一个脚本只是使快速删除在步骤 3 中创建的搜索轻松。</span><span class="sxs-lookup"><span data-stu-id="f9549-194">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="f9549-195">与其他脚本一样，该脚本也会提示您输入搜索组 ID。</span><span class="sxs-lookup"><span data-stu-id="f9549-195">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="f9549-196">运行此脚本时，搜索名称中搜索组 ID 的所有搜索都将被删除。</span><span class="sxs-lookup"><span data-stu-id="f9549-196">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span>

1. <span data-ttu-id="f9549-197">使用 .ps1 Windows PowerShell 文件名后缀将以下文本保存到脚本文件的一个移动脚本文件中;例如， `DeleteSearches.ps1` _</span><span class="sxs-lookup"><span data-stu-id="f9549-197">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="f9549-198">将该文件保存到保存其他文件所在的相同文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f9549-198">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="f9549-199">在Windows PowerShell中，转到上一步中保存该脚本的文件夹，然后运行该脚本;例如：</span><span class="sxs-lookup"><span data-stu-id="f9549-199">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. <span data-ttu-id="f9549-200">在 **搜索组 ID** 提示符处，为要删除的搜索键入一个搜索组名称，然后按 **Enter**。例如，  `ContosoCase` _</span><span class="sxs-lookup"><span data-stu-id="f9549-200">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="f9549-201">请记住，此名称区分大小写，因此您必须使用在步骤 3 中运行脚本时所采用的方式来键入它。</span><span class="sxs-lookup"><span data-stu-id="f9549-201">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

   <span data-ttu-id="f9549-202">该脚本显示已删除的每个搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="f9549-202">The script displays the name of each search that's deleted.</span></span>

   ![运行该脚本以删除搜索组中的搜索](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
