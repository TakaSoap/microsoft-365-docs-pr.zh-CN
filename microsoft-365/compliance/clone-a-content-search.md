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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: 使用本文中的 PowerShell 脚本快速克隆合规性中心中的现有内容搜索，Office 365或Microsoft 365。
ms.openlocfilehash: 763bd6ac49841e5b55bbbc187631ef74426d9d0a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60153206"
---
# <a name="clone-a-content-search"></a>克隆内容搜索

在 Office 365 或 Microsoft 365 合规性中心创建内容搜索SharePoint搜索多个邮箱或SharePoint OneDrive for Business可能需要一段时间。 如果键入的 URL 错误，指定要搜索的网站也容易出错。 若要避免这些问题，您可以使用本文中的 Windows PowerShell 脚本快速克隆现有内容搜索。 克隆搜索时，会创建一 (名称为) 的新搜索，其中包含与原始搜索相同的属性 (如内容位置和搜索) 搜索查询。 然后，可以通过更改关键字查询或日期范围来编辑新的搜索，然后运行它。
  
为什么要克隆内容搜索？
  
- 比较在同一内容位置运行的不同关键字搜索查询的结果。
    
- 为了节省在创建新搜索时必须重新输入大量内容位置的问题。
    
- 减小搜索结果的大小。 例如，如果您有一个返回过多结果以导出的搜索，您可以克隆搜索，然后添加基于日期范围的搜索条件以减少搜索结果数量。
  
## <a name="script-information"></a>脚本信息

- 您必须是 Microsoft 365 合规中心 中电子数据展示管理员角色组的成员，以运行本主题中所述的脚本。
    
- 该脚本包括最少的错误处理。 该脚本的主要目的是快速克隆内容搜索。
    
- 该脚本会创建新的内容搜索，但不启动它。
    
- 此脚本会考虑要克隆的内容搜索是否与电子数据展示案例关联。 如果搜索与案例关联，则新搜索也将与同一案例关联。 如果现有搜索未与案例关联，则新搜索将列在合规性中心的内容搜索页面上。  
    
- 本主题中提供的示例脚本在任何 Microsoft 标准支持计划或服务下都不受支持。 示例脚本“原样”提供，不提供任何形式的保证。 Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。 由于示例脚本及文档的使用或性能所引起的全部风险均由你承担。 在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>步骤 1：运行脚本以克隆搜索

此步骤中的脚本通过克隆现有内容搜索来创建新的内容搜索。 运行此脚本时，系统将提示您输入以下信息：
  
- **你的用户凭据** - 脚本将使用你的凭据连接到安全&中心 PowerShell。 如前所述，你必须是安全中心电子数据展示管理员角色组&运行脚本。 
    
- **现有搜索的名称** - 这是要克隆的内容搜索。 
    
- **将创建** 的新搜索的名称 - 如果将此值留空，脚本将为基于要克隆的搜索的名称的新搜索创建一个名称。 
    
克隆搜索：
  
1. 将以下文本保存到Windows PowerShell脚本文件中，使用文件名后缀.ps1;例如， `CloneSearch.ps1` 。
    
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

2. 打开Windows PowerShell，然后转到保存脚本的文件夹。
    
3. 运行脚本;例如：
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. 当系统提示输入凭据时，请输入您的电子邮件地址和密码，然后单击"确定 **"。**
    
5. 在脚本提示时输入以下信息。 键入每段信息，然后按 **Enter。**
    
    - 现有搜索的名称。
    
    - 新搜索的名称。
    
    该脚本将创建新的内容搜索，但不启动它。 这样，您有机会在下一步中编辑和运行搜索。 可以通过运行 **Get-ComplianceSearch** cmdlet 或进入合规性中心的内容搜索或电子 **数据** 展示页面来查看新搜索的属性，具体取决于新搜索是否与案例关联。 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>步骤 2：在合规中心编辑并运行克隆的搜索

运行脚本以克隆现有内容搜索后，下一步是转到合规中心编辑并运行新搜索。 如前所述，您可以通过更改关键字搜索查询以及添加或删除搜索条件来编辑搜索。 有关详细信息，请参阅：
  
- [Office 365 中的内容搜索](content-search.md)
    
- [内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
    
- [电子数据展示案例](./get-started-core-ediscovery.md)