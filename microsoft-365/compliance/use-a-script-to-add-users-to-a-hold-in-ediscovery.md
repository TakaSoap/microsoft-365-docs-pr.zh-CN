---
title: 使用脚本将用户添加到核心电子数据展示案例中的保留
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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
description: 了解如何运行脚本，将网站& OneDrive for Business邮箱添加到与Microsoft 365 合规中心中电子数据展示案例关联的新保留。
ms.openlocfilehash: a678649ebd15a34bdfe5765449d41feae1b14901
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64761232"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>使用脚本将用户添加到核心电子数据展示案例中的保留

安全&合规中心 PowerShell 提供 cmdlet，可用于自动执行与创建和管理电子数据展示事例相关的耗时任务。 目前，使用Microsoft 365 合规中心中的核心电子数据展示案例将大量保管人内容位置置于保留状态需要时间和准备时间。 例如，在创建保留之前，必须收集要保留的每个OneDrive for Business站点的 URL。 然后，对于要保留的每个用户，必须将其邮箱及其OneDrive for Business网站添加到保留。 可以使用本文中的脚本自动执行此过程。
  
脚本会提示你输入组织的“我的网站”域的名称 (例如， `contoso` 在 URL https://contoso-my.sharepoint.com)中，现有电子数据展示案例的名称、与案例关联的新保留的名称、要保留的用户的电子邮件地址列表，以及要创建基于查询的保留时要使用的搜索查询。 然后，该脚本获取列表中每个用户的OneDrive for Business站点的 URL，创建新的保留，然后将列表中每个用户的邮箱和OneDrive for Business网站添加到保留。 该脚本还会生成包含有关新保留的信息的日志文件。
  
下面是实现此目的的步骤：
  
[步骤 1：安装 SharePoint Online 命令行管理程序](#step-1-install-the-sharepoint-online-management-shell)
  
[步骤 2：生成用户列表](#step-2-generate-a-list-of-users)
  
[步骤 3：运行脚本以创建保留并添加用户](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>将用户添加到保留之前

- 你必须是Microsoft 365 合规中心中的电子数据展示管理器角色组的成员，并且必须是SharePoint联机管理员才能在步骤 3 中运行脚本。 有关详细信息，请参阅[Office 365安全&合规中心分配电子数据展示权限](assign-ediscovery-permissions.md)。

- 最多可以将 1，000 个邮箱和 100 个网站添加到与Microsoft 365 合规中心中的电子数据展示案例关联的保留中。 假设要保留的每个用户都有一个OneDrive for Business站点，则可以使用本文中的脚本将最多 100 个用户添加到保留。

- 请务必将步骤 2 中创建的用户列表和步骤 3 中的脚本保存到同一文件夹。 这样可以更轻松地运行脚本。

- 该脚本将用户列表添加到与现有事例关联的新保留。 运行脚本之前，请确保已创建要将保留与之关联的情况。

- 本文中的脚本在连接到安全&合规中心 PowerShell 和 SharePoint Online Management Shell 时支持新式身份验证。 如果是Microsoft 365或Microsoft 365 GCC组织，则可以按计划使用脚本。 如果你是Office 365德国组织、Microsoft 365 GCC高组织或 Microsoft 365 DoD 组织，则必须编辑脚本才能成功运行它。 具体而言，必须编辑行 `Connect-IPPSSession` 并使用 *ConnectionUri* 和 *AzureADAuthorizationEndpointUri* 参数 (和组织类型的适当值) 连接到安全&合规中心 PowerShell。 有关详细信息，请参阅[连接安全&合规中心 PowerShell 中的](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)示例。

- 该脚本自动与安全&合规中心 PowerShell 和 SharePoint Online Management Shell 断开连接。

- 该脚本包含最少的错误处理。 其主要目的是快速轻松地将每个用户的邮箱和OneDrive for Business网站置于保留状态。

- 本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步骤 1：安装 SharePoint Online 命令行管理程序

第一步是安装 SharePoint Online Management Shell（如果尚未安装在本地计算机上）。 不必在此过程中使用 shell，但必须安装它，因为它包含在步骤 3 中运行的脚本所需的先决条件。 这些先决条件允许脚本与 SharePoint Online 通信，以获取OneDrive for Business网站的 URL。
  
转到[设置 SharePoint Online Management Shell Windows PowerShell环境](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)，并执行步骤 1 和步骤 2，在本地计算机上安装 SharePoint Online Management Shell。

## <a name="step-2-generate-a-list-of-users"></a>步骤 2：生成用户列表

步骤 3 中的脚本将创建与电子数据展示案例关联的保留，并将用户列表的邮箱和OneDrive for Business网站添加到保留。 只需在文本文件中键入电子邮件地址，也可以在Windows PowerShell中运行命令以获取电子邮件地址列表，并将其保存到文件 (位于将脚本保存到步骤 3) 中的同一文件夹中。
  
下面是通过使用连接到Exchange Online组织的远程 PowerShell 运行的 PowerShell 命令 () 获取组织中所有用户的电子邮件地址列表，并将其保存到名为HoldUsers.txt的文本文件中。
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

运行此命令后，打开文本文件并删除包含属性名称  `PrimarySmtpAddress`的标头。 然后删除所有电子邮件地址，但要添加到将在步骤 3 中创建的保留的用户除外。 确保电子邮件地址列表之前或之后没有空白行。
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>步骤 3：运行脚本以创建保留并添加用户

在此步骤中运行脚本时，它会提示你获取以下信息。 运行脚本之前，请务必准备好此信息。
  
- **用户凭据：** 该脚本将使用凭据通过 PowerShell 连接到安全&合规中心。 它还将使用这些凭据访问 SharePoint Online，以获取用户列表的OneDrive for Business URL。

- **SharePoint域的名称：** 脚本提示输入此名称，以便它可以连接到 <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint管理中心</a>。 它还使用组织中OneDrive URL 的域名。 例如，如果管理中心的 URL 为 `https://contoso-admin.sharepoint.com` URL 且OneDrive的 URL 为，`https://contoso-my.sharepoint.com`则`contoso`在脚本提示你输入域名时输入。

- **案例的名称：** 现有事例的名称。 该脚本将创建与这种情况关联的新保留。

- **保留的名称：** 脚本将创建保留的名称并将其与指定的案例相关联。

- **搜索基于查询的保留的查询：** 可以创建基于查询的保留，以便仅保留符合指定搜索条件的内容。 若要将所有内容置于保留状态，只需在提示输入搜索查询时按 **Enter** 即可。

- **打开保留或不打开：** 创建脚本后，可以打开该脚本，也可以让脚本创建保留，而无需启用它。 如果没有打开该脚本，则可在稍后的Microsoft 365 合规中心或运行以下 PowerShell 命令将其打开：

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **包含用户列表的文本文件的名称** - 步骤 2 中包含要添加到保留的用户列表的文本文件的名称。 如果此文件与脚本位于同一文件夹中，只需键入文件的名称 (例如，HoldUsers.txt) 。 如果文本文件在另一个文件夹中，请键入该文件的完整路径名。

收集脚本将提示你提供的信息后，最后一步是运行脚本以创建新保留，并向其添加用户。
  
1. 使用文件名后缀`.ps1`将以下文本保存到Windows PowerShell脚本文件。 例如，`AddUsersToHold.ps1`。

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

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
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $finallist)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $false | out-null
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
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. 在本地计算机上，打开Windows PowerShell并转到保存脚本的文件夹。

3. 运行脚本;例如：

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. 输入脚本提示的信息。

   该脚本连接到安全&合规中心 PowerShell，然后在电子数据展示案例中创建新保留，并为列表中的用户添加邮箱和OneDrive for Business。 可以在Microsoft 365 合规中心的 **电子数据展示** 页上转到案例以查看新保留。

脚本运行完毕后，它会创建以下日志文件，并将其保存到脚本所在的文件夹。
  
- **LocationsOnHold.txt：** 包含脚本成功保留的邮箱和OneDrive for Business网站的列表。

- **LocationsNotOnHold.txt：** 包含脚本未保留的邮箱和OneDrive for Business网站的列表。 如果用户有邮箱而不是OneDrive for Business网站，则用户将包含在未被搁置的OneDrive for Business网站列表中。

- **GetCaseHoldPolicy.txt：** 包含新保留的 **Get-CaseHoldPolicy** cmdlet 的输出，脚本在创建新保留后运行。 此 cmdlet 返回的信息包括一个用户列表，这些用户的邮箱和OneDrive for Business网站被搁置，以及是否启用或禁用了保留。 

- **GetCaseHoldRule.txt：** 包含新保留的 **Get-CaseHoldRule** cmdlet 的输出，脚本在创建新保留后运行。 如果使用脚本创建基于查询的保留，则此 cmdlet 返回的信息包括搜索查询。
