---
title: 克隆内容搜索
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: 使用本文中的 PowerShell 脚本快速克隆 Office 365 或 Microsoft 365 合规中心中的现有内容搜索。
ms.openlocfilehash: c64cec2415819dc53f30c303c241e3902f34017d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918058"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="c73f8-103">克隆内容搜索</span><span class="sxs-lookup"><span data-stu-id="c73f8-103">Clone a Content Search</span></span>

<span data-ttu-id="c73f8-104">在 Office 365 或 Microsoft 365 合规中心内创建搜索多个邮箱或 SharePoint 和 OneDrive for Business 网站的内容搜索可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="c73f8-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="c73f8-105">如果键入的 URL 错误，指定要搜索的网站也容易出错。</span><span class="sxs-lookup"><span data-stu-id="c73f8-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="c73f8-106">若要避免这些问题，您可以使用本文中的 Windows PowerShell 脚本快速克隆现有内容搜索。</span><span class="sxs-lookup"><span data-stu-id="c73f8-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="c73f8-107">克隆搜索时，会创建一 (名称为) 的新搜索，其中包含与原始搜索相同的属性 (如内容位置和搜索查询) 。</span><span class="sxs-lookup"><span data-stu-id="c73f8-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="c73f8-108">然后，您可以通过更改关键字查询或日期范围来编辑新的搜索，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="c73f8-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="c73f8-109">为什么要克隆内容搜索？</span><span class="sxs-lookup"><span data-stu-id="c73f8-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="c73f8-110">比较在同一内容位置运行的不同关键字搜索查询的结果。</span><span class="sxs-lookup"><span data-stu-id="c73f8-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="c73f8-111">为了节省在创建新搜索时必须重新输入大量内容位置的问题。</span><span class="sxs-lookup"><span data-stu-id="c73f8-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="c73f8-112">减小搜索结果的大小。</span><span class="sxs-lookup"><span data-stu-id="c73f8-112">To decrease the size of the search results.</span></span> <span data-ttu-id="c73f8-113">例如，如果您有一个返回过多结果以导出的搜索，您可以克隆搜索，然后添加基于日期范围的搜索条件以减少搜索结果数量。</span><span class="sxs-lookup"><span data-stu-id="c73f8-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="script-information"></a><span data-ttu-id="c73f8-114">脚本信息</span><span class="sxs-lookup"><span data-stu-id="c73f8-114">Script information</span></span>

- <span data-ttu-id="c73f8-115">您必须是安全与合规中心内电子数据展示管理员&组的成员，以运行本主题中所述的脚本。</span><span class="sxs-lookup"><span data-stu-id="c73f8-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="c73f8-116">该脚本包括最少的错误处理。</span><span class="sxs-lookup"><span data-stu-id="c73f8-116">The script includes minimal error handling.</span></span> <span data-ttu-id="c73f8-117">该脚本的主要目的是快速克隆内容搜索。</span><span class="sxs-lookup"><span data-stu-id="c73f8-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="c73f8-118">该脚本会创建新的内容搜索，但不启动它。</span><span class="sxs-lookup"><span data-stu-id="c73f8-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="c73f8-119">此脚本会考虑要克隆的内容搜索是否与电子数据展示案例关联。</span><span class="sxs-lookup"><span data-stu-id="c73f8-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="c73f8-120">如果搜索与案例关联，则新搜索也将与同一案例关联。</span><span class="sxs-lookup"><span data-stu-id="c73f8-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="c73f8-121">如果现有搜索未与案例关联，则新搜索将列在合规性中心的内容搜索页面上。 </span><span class="sxs-lookup"><span data-stu-id="c73f8-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="c73f8-122">本主题中提供的示例脚本在任何 Microsoft 标准支持计划或服务下都不受支持。</span><span class="sxs-lookup"><span data-stu-id="c73f8-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="c73f8-123">示例脚本“原样”提供，不提供任何形式的保证。</span><span class="sxs-lookup"><span data-stu-id="c73f8-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="c73f8-124">Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。</span><span class="sxs-lookup"><span data-stu-id="c73f8-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="c73f8-125">由于示例脚本及文档的使用或性能所引起的全部风险均由你承担。</span><span class="sxs-lookup"><span data-stu-id="c73f8-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="c73f8-126">在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。</span><span class="sxs-lookup"><span data-stu-id="c73f8-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="c73f8-127">步骤 1：运行脚本以克隆搜索</span><span class="sxs-lookup"><span data-stu-id="c73f8-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="c73f8-128">此步骤中的脚本通过克隆现有内容搜索来创建新的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="c73f8-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="c73f8-129">运行此脚本时，系统将提示您输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="c73f8-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="c73f8-130">**你的用户凭据** - 脚本将使用你的凭据，通过 & 连接到组织的安全与合规Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c73f8-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="c73f8-131">如前所述，你必须是安全中心电子数据展示管理员角色组&运行脚本。</span><span class="sxs-lookup"><span data-stu-id="c73f8-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="c73f8-132">**现有搜索的名称** - 这是要克隆的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="c73f8-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="c73f8-133">**将创建** 的新搜索的名称 - 如果将此值留空，脚本将为基于要克隆的搜索的名称的新搜索创建一个名称。</span><span class="sxs-lookup"><span data-stu-id="c73f8-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="c73f8-134">克隆搜索：</span><span class="sxs-lookup"><span data-stu-id="c73f8-134">To clone a search:</span></span>
  
1. <span data-ttu-id="c73f8-135">使用文件名后缀 .ps1 将以下文本Windows PowerShell脚本文件;例如， `CloneSearch.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="c73f8-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. <span data-ttu-id="c73f8-136">打开Windows PowerShell，然后转到保存脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c73f8-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="c73f8-137">运行脚本;例如：</span><span class="sxs-lookup"><span data-stu-id="c73f8-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="c73f8-138">当系统提示输入凭据时，请输入您的电子邮件地址和密码，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="c73f8-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="c73f8-139">在脚本提示时输入以下信息。</span><span class="sxs-lookup"><span data-stu-id="c73f8-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="c73f8-140">键入每段信息，然后按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="c73f8-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="c73f8-141">现有搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="c73f8-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="c73f8-142">新搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="c73f8-142">The name of the new search.</span></span>
    
    <span data-ttu-id="c73f8-143">该脚本将创建新的内容搜索，但不启动它。</span><span class="sxs-lookup"><span data-stu-id="c73f8-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="c73f8-144">这样，您有机会在下一步中编辑和运行搜索。</span><span class="sxs-lookup"><span data-stu-id="c73f8-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="c73f8-145">可以通过运行 **Get-ComplianceSearch** cmdlet 或进入合规性中心的内容搜索或电子 **数据** 展示页面来查看新搜索的属性，具体取决于新搜索是否与案例关联。</span><span class="sxs-lookup"><span data-stu-id="c73f8-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="c73f8-146">步骤 2：在合规中心编辑并运行克隆的搜索</span><span class="sxs-lookup"><span data-stu-id="c73f8-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="c73f8-147">运行脚本以克隆现有内容搜索后，下一步是转到合规中心编辑并运行新搜索。</span><span class="sxs-lookup"><span data-stu-id="c73f8-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="c73f8-148">如前所述，您可以通过更改关键字搜索查询以及添加或删除搜索条件来编辑搜索。</span><span class="sxs-lookup"><span data-stu-id="c73f8-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="c73f8-149">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c73f8-149">For more information, see:</span></span>
  
- [<span data-ttu-id="c73f8-150">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="c73f8-150">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="c73f8-151">内容搜索的关键字查询和搜索条件</span><span class="sxs-lookup"><span data-stu-id="c73f8-151">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="c73f8-152">电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="c73f8-152">eDiscovery cases</span></span>](./get-started-core-ediscovery.md)