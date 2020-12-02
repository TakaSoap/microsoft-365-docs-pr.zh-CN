---
title: 使用脚本将用户添加到核心电子数据展示事例中的保留
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: 了解如何运行脚本将邮箱 & OneDrive for business 网站添加到与 Microsoft 365 合规性中心中的电子数据展示事例关联的新保留中。
ms.openlocfilehash: 31c3bfef4eda4802618020f607bc7706780f3629
ms.sourcegitcommit: 4a9e1b6851b988bcd31e87b184fc185be949840d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "49525611"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>使用脚本将用户添加到核心电子数据展示事例中的保留

Security & 合规性中心 PowerShell 提供了可让您自动执行与创建和管理电子数据展示事例相关的耗时任务的 cmdlet。 目前，使用安全 & 合规中心中的核心电子数据展示事例将大量的保管人内容位置置于保留状态需要花费时间和准备。 例如，在创建保留之前，您必须收集要置于保留状态的每个 OneDrive for business 网站的 URL。 然后，对于要置于保留状态的每个用户，都必须将其邮箱及其 OneDrive for Business 网站添加到保留中。 您可以使用本文中的脚本自动执行此过程。
  
该脚本会提示您组织的 "我的网站" 域的名称 (例如， `contoso` 在 URL 中， https://contoso-my.sharepoint.com) 现有电子数据展示事例的名称、与该事例关联的新保留的名称、要置于保留状态的用户的电子邮件地址列表以及要创建基于查询的保留时要使用的搜索查询。 然后，该脚本获取列表中每个用户的 OneDrive for business 网站的 URL，创建新保留，然后将列表中每个用户的邮箱和 OneDrive for Business 网站添加到保留。 该脚本还会生成包含有关新保留的信息的日志文件。
  
下面介绍了实现这一点的步骤：
  
[步骤 1：安装 SharePoint Online 命令行管理程序](#step-1-install-the-sharepoint-online-management-shell)
  
[步骤2：生成用户列表](#step-2-generate-a-list-of-users)
  
[步骤3：运行脚本以创建保留项并添加用户](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>将用户添加到保留前的准备工作

- 您必须是 Security & 合规性中心中的电子数据展示管理器角色组的成员，SharePoint Online 管理员才能在步骤3中运行该脚本。 有关详细信息，请参阅 [在 Office 365 安全 & 合规中心中分配电子数据展示权限](assign-ediscovery-permissions.md)。

- 最多可以将1000个邮箱和100网站添加到与安全 & 合规中心中的电子数据展示事例相关联的保留中。 假定您要置于保留状态的每个用户都有 OneDrive for business 网站，则可以使用本文中的脚本将最多100个用户添加到保留中。

- 请务必将您在步骤2中创建的用户列表和步骤3中的脚本保存到同一个文件夹中。 这将使脚本运行变得更加简单。

- 该脚本将用户列表添加到与现有事例相关联的新保留中。 在运行脚本之前，请确保已创建要与保留关联的事例。

- 在连接到安全 & 合规中心 PowerShell 时，本文中的脚本支持新式身份验证。 如果你是 Microsoft 365 或 Microsoft 365 GCC 组织，则可以按如下所示使用脚本。 如果你是 Office 365 德国组织、Microsoft 365 GCC 高组织或 Microsoft 365 DoD 组织，则必须编辑脚本才能成功运行它。 具体来说，您必须编辑行 `Connect-IPPSSession` ，并使用 *ConnectionUri* 和 *AzureADAuthorizationEndpointUri* 参数 (和组织类型) 的相应值连接到安全 & 合规性中心 PowerShell。 有关详细信息，请参阅 [Connect To Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)中的示例。

- 每次运行该脚本时，都会创建新的安全 & 合规性 PowerShell 和 SharePoint Online 命令行管理程序会话。 因此，你可以使用所有可供你使用的 PowerShell 会话。 若要防止这种情况发生，可以运行以下命令来断开活动 PowerShell 会话。

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

   ```powershell
   Disconnect-SPOService
   ```

- 该脚本包括最少的错误处理。 其主要目的是快速轻松地将每个用户的邮箱和 OneDrive for Business 网站置于保留状态。

- 本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步骤 1：安装 SharePoint Online 命令行管理程序

第一步是安装 SharePoint Online 命令行管理程序（如果它尚未安装在本地计算机上）。 您不必在此过程中使用命令行管理程序，但必须安装它，因为它包含您在步骤3中运行的脚本所需的必备组件。 这些先决条件允许脚本与 SharePoint Online 通信，以获取 OneDrive for business 网站的 Url。
  
转到 [设置 Sharepoint Online 命令行管理程序 Windows PowerShell 环境](https://go.microsoft.com/fwlink/p/?LinkID=286318) ，并执行步骤1和步骤2，在本地计算机上安装 Sharepoint Online 命令行管理程序。 

## <a name="step-2-generate-a-list-of-users"></a>步骤2：生成用户列表

步骤3中的脚本将创建与电子数据展示事例相关联的保留，并将用户列表中的邮箱和 OneDrive for Business 网站添加到保留。 您可以只在文本文件中键入电子邮件地址，也可以在 Windows PowerShell 中运行命令，以获取电子邮件地址列表，并将其保存到在第3步) 中将脚本保存到同一文件夹中的文件 (。
  
下面是使用连接到 Exchange Online 组织的远程 PowerShell 运行的 PowerShell 命令 () 获取组织中所有用户的电子邮件地址列表，并将其保存到名为 HoldUsers.txt 的文本文件中。
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

运行此命令后，打开文本文件并删除包含属性名称的标头  `PrimarySmtpAddress` 。 然后删除除您要添加到您在步骤3中创建的保留项的用户之外的所有电子邮件地址。 请确保电子邮件地址列表前面或后面没有空行。
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>步骤3：运行脚本以创建保留项并添加用户

在此步骤中运行脚本时，它将提示您提供以下信息。 在运行脚本之前，请务必准备好此信息。
  
- **您的用户凭据：** 该脚本将使用你的凭据连接到安全 & 合规性中心与远程 PowerShell。 此外，它还将使用这些凭据访问 SharePoint Online，以获取用户列表的 OneDrive for business Url。

- **"我的网站" 域的名称：** "我的网站" 域是包含组织中所有 OneDrive for business 网站的域。 例如，如果您的 "我的网站" 域的 URL 为 **https://contoso-my.sharepoint.com** ，那么  `contoso` 当脚本提示您输入 "我的网站" 域的名称时，您就会输入。

- **事例的名称：** 现有事例的名称。 该脚本将创建与此事例关联的新保留。

- **保留的名称：** 将创建脚本的保留名称，并将其与指定的事例相关联。

- **基于查询的保留的搜索查询：** 您可以创建基于查询的保留，以便在保留时仅放置满足指定搜索条件的内容。 若要将所有内容置于保留状态，只需在收到搜索查询时按 **enter** 。

- **打开保留：** 您可以让脚本在创建保留后对其进行启用，也可以让脚本在不启用的情况下创建保留。 如果没有启用保留的脚本，可以稍后在安全 & 合规性中心中或通过运行以下 PowerShell 命令将其打开：

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- 包含 **用户列表的文本文件的名称**-步骤2中包含要添加到保留的用户列表的文本文件的名称。 如果此文件与脚本位于同一文件夹中，只需键入文件的名称 (例如，HoldUsers.txt) 。 如果文本文件在另一个文件夹中，请键入该文件的完整路径名。

收集脚本将提示输入的信息后，最后一步是运行脚本以创建新的保留并向其添加用户。
  
1. 使用文件名后缀将以下文本保存到 Windows PowerShell 脚本文件中 `.ps1` 。 例如，`AddUsersToHold.ps1`。

   ```powershell
   #script begin
   " "
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
   write-host "***********************************************"
   " "
   # Connect to SCC PowerShell using modern authentication
   if (!$SccSession)
   {
     Import-Module ExchangeOnlineManagement
     Connect-IPPSSession
   }
   # Get user credentials to connect to SPO Management Shell
   $credentials = Get-Credential -Message "Type your credentials again to connect to SharePoint Online Management Shell"
   # Load the SharePoint assemblies from the SharePoint Online Management Shell
   # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
   if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
   {
       $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
       $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
       $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
       if (!$SharePointClient)
       {
           Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
           return;
       }
   }
   if (!$spCreds)
   {
       $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
   }
   # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
   ""
   $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
   ""
   # Get other required information
   do{
   $casename = Read-Host "Enter the name of the case"
   $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
   if($caseexists -ne 'True')
   {""
   write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
   ""}
   }While($caseexists -ne 'True')
   ""
   do{
   $holdName = Read-Host "Enter the name of the new hold"
   $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
   if($holdexists -eq 'True')
   {""
   write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
   ""}
   }While($holdexists -eq 'True')
   ""
   $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
   ""
   $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
   do{
   ""
   $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
   ""
   $fileexists = test-path -path $inputfile
   if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
   }while($fileexists -ne 'True')
   #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
       #in the list are unique.
     [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
     [int]$dupl = $emailAddresses.count
     [array]$emailAddresses = $emailAddresses | select-object -unique
     $dupl -= $emailAddresses.count
   #Validate email addresses so the hold creation does not run in to an error.
   if($emailaddresses.count -gt 0){
   write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
   ""
   Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
   ""
   $finallist =@()
   foreach($emailAddress in $emailAddresses)
   {
   if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
   {$finallist += $emailaddress}
   else {"Unable to find the user $emailaddress"
   [array]$excludedlist += $emailaddress}
   }
   ""
   #find user's OneDrive Site URL using email address
   Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
   ""
   $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
   $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
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
   $urls = @()
   foreach($emailAddress in $emailAddresses)
   {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
   }
   if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
   ""
   Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
   if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
   New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
   New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
   }
   else{
   New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
   New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
   }
   ""
   }
   else {"No valid locations were identified. Therefore, the hold wasn't created."}
   #write log files (if needed)
   $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
   $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
   if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
   {
   Write-Host "Generating output files..." -foregroundColor Yellow
   if($ODAdded.count -gt 0){
   "OneDrive Locations" | add-content .\LocationsOnHold.txt
   "==================" | add-content .\LocationsOnHold.txt 
   $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
   if($ODExluded.count -gt 0){ 
   "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
   "================================" | add-content .\LocationsNotOnHold.txt
   $ODExluded | add-content .\LocationsNotOnHold.txt}
   if($finallist.count -gt 0){
   " " | add-content .\LocationsOnHold.txt
   "Exchange Locations" | add-content .\LocationsOnHold.txt
   "==================" | add-content .\LocationsOnHold.txt 
   $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
   if($excludedlist.count -gt 0){
   " "| add-content .\LocationsNotOnHold.txt
   "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
   "===============================" | add-content .\LocationsNotOnHold.txt
   $excludedlist | add-content .\LocationsNotOnHold.txt}
   $FormatEnumerationLimit=-1
   if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
   if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
   }
   }
   else {"The hold wasn't created because no valid entries were found in the text file."}
   ""
   Write-host "Script complete!" -foregroundColor Yellow
   ""
   #script end
   ```

2. 在本地计算机上，打开 Windows PowerShell 并转到保存该脚本的文件夹。

3. 运行脚本;例如：

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. 输入脚本提示您输入的信息。

   该脚本将连接到安全 & 合规性中心 PowerShell，然后在电子数据展示事例中创建新的保留，并为列表中的用户添加邮箱和 OneDrive for Business。 您可以转到 Security & 合规性中心中的 **电子数据展示** 页面上的事例，以查看新的保留。

脚本运行完毕后，它会创建以下日志文件，并将其保存到脚本所在的文件夹中。
  
- **LocationsOnHold.txt：** 包含脚本成功置于保留状态的邮箱和 OneDrive for business 网站的列表。

- **LocationsNotOnHold.txt：** 包含该脚本未置于保留状态的邮箱和 OneDrive for business 网站的列表。 如果用户具有邮箱，而不是 OneDrive for business 网站，则该用户将包含在未置于保留状态的 OneDrive for business 网站列表中。

- **GetCaseHoldPolicy.txt：** 包含新保留的 **CaseHoldPolicy** cmdlet 的输出，在创建新保留后，脚本将运行该脚本。 此 cmdlet 返回的信息包括其邮箱和 OneDrive for Business 网站置于保留状态以及是否启用或禁用保留的用户列表。 

- **GetCaseHoldRule.txt：** 包含新保留的 **new-caseholdrule** cmdlet 的输出，在创建新保留后，脚本将运行该脚本。 如果您使用脚本创建基于查询的保留，则此 cmdlet 返回的信息包括搜索查询。
