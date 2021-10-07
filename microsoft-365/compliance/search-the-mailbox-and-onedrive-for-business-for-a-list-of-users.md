---
title: 在邮箱& OneDrive for Business网站中搜索具有内容搜索的用户列表
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: 使用本文中的内容搜索和脚本搜索一组OneDrive for Business邮箱和网站。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 12a97cddaa26fbd6f63f9af60bcebe9105b970ec
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197457"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>使用内容搜索在邮箱和 OneDrive for Business 站点中搜索用户列表

安全&中心 PowerShell 提供了许多 cmdlet，可让你自动执行与电子数据展示相关的耗时任务。 目前，在 Microsoft 365 合规中心创建内容搜索以搜索大量保管人内容位置需要时间和准备工作。 创建搜索之前，必须收集每个 OneDrive for Business 网站的 URL，然后将每个邮箱和OneDrive for Business网站添加到搜索中。 在将来的版本中，此操作将更容易在 Microsoft 365 合规中心。 在此之前，您可以使用本文中的脚本自动执行此过程。 此脚本会提示您输入组织的 MySite 域 (例如，URL) 中的 **contoso、** 用户电子邮件地址列表、新内容搜索的名称以及使用的搜索 `https://contoso-my.sharepoint.com` 查询。 该脚本获取列表中每个用户的 OneDrive for Business URL，然后使用您提供的搜索查询创建并启动内容搜索，以搜索列表中的每个用户的邮箱和 OneDrive for Business 网站。
  
## <a name="permissions-and-script-information"></a>权限和脚本信息

- 您必须是 Microsoft 365 合规中心 中的电子数据展示管理员角色组的成员，以及 SharePoint Online 全局管理员才能运行步骤 3 中的脚本。

- 请确保将步骤 2 中创建的用户列表和步骤 3 中的脚本保存到同一文件夹中。 这样更易于运行脚本。

- 该脚本包括最少的错误处理。 其主要用途是快速而轻松地搜索每个用户OneDrive for Business和网站。

- 本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步骤 1：安装 SharePoint Online 命令行管理程序

第一步是安装 SharePoint 命令行管理程序。 不必在此过程中使用命令行管理程序，但必须安装它，因为它包含步骤 3 中运行的脚本所需的先决条件。 这些先决条件允许脚本与 SharePoint Online 进行通信，以便获取网站OneDrive for Business URL。
  
转到设置[SharePoint Online 命令行](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)管理程序 Windows PowerShell 环境，并执行步骤 1 和步骤 2 以安装 SharePoint Online 命令行管理程序。
  
## <a name="step-2-generate-a-list-of-users"></a>步骤 2：生成用户列表

步骤 3 中的脚本将创建内容搜索，以搜索邮箱OneDrive帐户查找用户列表。 只需在文本文件中键入电子邮件地址，或在 Windows PowerShell 中运行命令，获取电子邮件地址列表并将其保存到位于步骤 3) 中将脚本保存到的同一文件夹中的 (文件中。
  
下面是一个[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)命令，您可以运行该命令获取组织中所有用户的电子邮件地址列表，并将其保存到名为 的文本文件 `Users.txt` 中。 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

运行此命令后，请确保打开 文件并删除包含属性名称 的 标头  `PrimarySmtpAddress` 。 该文本文件应只包含电子邮件地址列表，而不包含任何其他内容。 确保电子邮件地址列表之前或之后没有空行。
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>步骤 3：运行脚本以创建和启动搜索

在此步骤中运行脚本时，它将提示您输入以下信息。 在运行脚本之前，请务必准备好此信息。
  
- **用户凭据**- 脚本将使用你的凭据访问 SharePoint Online，获取 OneDrive for Business URL 并连接到安全&中心 PowerShell。 
    
- **MySite 域** 的名称 - MySite 域是包含组织中所有OneDrive for Business网站的域。 例如，如果 MySite 域的 URL 为 ，则当脚本提示您输入 MySite 域的名称时， **https://contoso-my.sharepoint.com**  `contoso` 您将输入 。 
    
- **步骤 2 中的** 文本文件的路径名 - 在步骤 2 中创建的文本文件的路径名。 如果文本文件和脚本位于同一文件夹中，请输入文本文件的名称。 否则，输入文本文件的完整路径名。 
    
- **内容搜索的名称** - 脚本将创建的内容搜索的名称。 
    
- **搜索查询** - 创建并运行将用于内容搜索的搜索查询。 有关搜索查询详细信息，请参阅关键字 [查询和电子数据展示的搜索条件](keyword-queries-and-search-conditions.md)。


**若要运行该脚本，请执行下列操作：**
    
1. 将以下文本保存到Windows PowerShell脚本文件中，使用文件名后缀 .ps1;例如， `SearchEXOOD4B.ps1` 。 将文件保存到步骤 2 中保存用户列表的同一文件夹中。
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. 打开Windows PowerShell，然后转到步骤 2 中保存脚本和用户列表的文件夹。
    
3. 启动脚本;例如：
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. 当系统提示输入凭据时，请输入您的电子邮件地址和密码，然后单击"确定 **"。** 
    
5. 在脚本提示时输入以下信息。 键入每段信息，然后按 **Enter。**
    
    - MySite 域的名称。 
    
    - 包含用户列表的文本文件的路径名。
    
    - 内容搜索的名称。
    
    - 搜索查询 (留空，以返回内容位置或网站) 。
    
    该脚本获取每个网站OneDrive for Business URL，然后创建并启动搜索。 您可以在安全 & 合规中心 PowerShell 中运行 **Get-ComplianceSearch** cmdlet 以显示搜索统计信息和结果，也可以转到 Microsoft 365 合规中心 中的"内容"搜索页查看有关搜索的信息。
