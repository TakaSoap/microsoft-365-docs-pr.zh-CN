---
title: 使用脚本将用户添加到核心电子数据展示案例中的保留项
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
description: 了解如何运行脚本，将 OneDrive for Business &邮箱添加到与 Microsoft 365 合规中心中的电子数据展示案例相关联的新保留中。
ms.openlocfilehash: 278e8e051165eca906e9b454268068cbbe6aef05
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175571"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>使用脚本将用户添加到核心电子数据展示案例中的保留项

安全&中心 PowerShell 提供了 cmdlet，使你可以自动执行与创建和管理电子数据展示事例相关的耗时任务。 目前，使用安全与合规中心&核心电子数据展示案例将大量保管人内容位置放在保留状态需要时间和准备。 例如，创建保留之前，必须收集要保留的每个 OneDrive for Business 网站的 URL。 然后，对于要置于保留状态的每一位用户，你必须将其邮箱及其 OneDrive for Business 网站添加到保留中。 您可以使用本文中的脚本自动执行此过程。
  
该脚本会提示您输入您组织的"我的网站"域 (的名称，例如，在 URL 中，现有电子数据展示案例的名称，与该案例关联的新保留的名称，要置于保留状态的用户的电子邮件地址列表，以及创建基于查询的保留时使用的搜索查询。 `contoso` https://contoso-my.sharepoint.com) 然后，该脚本获取列表中每个用户的 OneDrive for Business 网站的 URL，创建新的保留，然后将列表中每个用户的邮箱和 OneDrive for Business 网站添加到保留。 该脚本还会生成包含有关新保留的信息的日志文件。
  
以下是实现此目标的步骤：
  
[步骤 1：安装 SharePoint Online 命令行管理程序](#step-1-install-the-sharepoint-online-management-shell)
  
[步骤 2：生成用户列表](#step-2-generate-a-list-of-users)
  
[步骤 3：运行脚本以创建保留并添加用户](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>将用户添加到保留之前

- 您必须是安全与合规中心电子数据展示管理员角色组的成员& SharePoint Online 管理员才能在步骤 3 中运行脚本。 有关详细信息，请参阅 Office 365 安全与合规中心& [电子数据展示权限](assign-ediscovery-permissions.md)。

- 最多可将 1，000 个邮箱和 100 个网站添加到与安全与合规中心中的电子数据展示&相关联的保留。 假设要将其保留的每个用户都有一个 OneDrive for Business 网站，则使用本文中的脚本最多可将 100 个用户添加到保留。

- 请务必将步骤 2 中创建的用户列表和步骤 3 中的脚本保存到同一文件夹中。 这样更易于运行脚本。

- 该脚本将用户列表添加到与现有案例关联的新保留中。 在运行脚本之前，请确保已创建要关联保留的大小写。

- 本文中的脚本支持在连接到安全与合规中心 PowerShell & SharePoint Online 命令行管理程序时进行新式验证。 如果你是 Microsoft 365 或 Microsoft 365 GCC 组织，你可以像现在一样使用该脚本。 如果你是 Office 365 Germany 组织、Microsoft 365 GCC High 组织或 Microsoft 365 DoD 组织，您必须编辑脚本以成功运行它。 具体而言，您必须编辑该行并使用 `Connect-IPPSSession` *ConnectionUri* 和 *AzureADAuthorizationEndpointUri* 参数 (以及组织类型) 的适当值来连接到 &安全与合规中心 PowerShell。 有关详细信息，请参阅"连接到安全与合规中心& [PowerShell 中的示例](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)。

- 该脚本会自动从安全与合规& PowerShell 和 SharePoint Online 命令行管理程序断开连接。

- 该脚本包括最少的错误处理。 其主要用途是快速轻松地将每个用户的邮箱和 OneDrive for Business 网站置于保留状态。

- 本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步骤 1：安装 SharePoint Online 命令行管理程序

第一步是在本地计算机上安装 SharePoint Online 命令行管理程序（如果尚未安装）。 不必在此过程中使用命令行管理程序，但必须安装它，因为它包含在步骤 3 中运行的脚本所需的先决条件。 这些先决条件允许脚本与 SharePoint Online 通信，获取 OneDrive for Business 网站的 URL。
  
转到 ["设置 SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) 命令行管理程序Windows PowerShell环境，并执行步骤 1 和步骤 2 以在本地计算机上安装 SharePoint Online 命令行管理程序。

## <a name="step-2-generate-a-list-of-users"></a>步骤 2：生成用户列表

步骤 3 中的脚本将创建与电子数据展示案例关联的保留，并添加用户列表的邮箱和 OneDrive for Business 网站。 只需在文本文件中键入电子邮件地址，或在 Windows PowerShell 中运行命令，获取电子邮件地址列表，并将其保存到位于步骤 3) 中将脚本保存到的同一文件夹中的文件 (。
  
下面是一个 PowerShell 命令 (，通过使用连接到 Exchange Online 组织的远程 PowerShell) 可获取组织中所有用户的电子邮件地址列表，并将其保存到名为 HoldUsers.txt 的文本文件中。
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

运行此命令后，打开文本文件并删除包含属性名称的标题  `PrimarySmtpAddress` 。 然后删除除要添加到将在步骤 3 创建的保留中的用户的电子邮件地址之外的所有电子邮件地址。 确保电子邮件地址列表之前或之后没有空白行。
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>步骤 3：运行脚本以创建保留并添加用户

在此步骤中运行脚本时，它将提示您输入以下信息。 在运行脚本之前，请确保准备好此信息。
  
- **用户凭据：** 该脚本将使用你的凭据通过 PowerShell &安全与合规中心。 它还将使用这些凭据访问 SharePoint Online，获取用户列表的 OneDrive for Business URL。

- **SharePoint 域的名称：** 脚本会提示您输入此名称，以便可以连接到 SharePoint 管理中心。 它还使用组织中 OneDrive URL 的域名。 例如，如果管理中心的 URL 为，而 OneDrive 的 URL 为，则当脚本提示您输入域名时，您将 `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` `contoso` 输入。

- **案例的名称：** 现有案例的名称。 该脚本将创建一个与此案例相关联的新保留。

- **保留的名称：** 脚本将创建保留项的名称并将其与指定案例关联。

- **基于查询的保留的搜索查询：** 您可以创建基于查询的保留，以便仅将满足指定搜索条件的内容置于保留状态。 若要保留所有内容，只需在系统提示您进行搜索查询时按 **Enter。**

- **打开保留：** 可以在脚本创建后将其打开保留，也可以让脚本创建保留，而无需启用它。 如果未将脚本打开为保留状态，可以在以后在安全与合规中心或运行以下 PowerShell &将其打开：

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **包含用户列表的** 文本文件的名称 - 步骤 2 中包含要添加到保留项的用户列表的文本文件的名称。 如果此文件与脚本位于同一文件夹中，只需键入文件的名称 (例如，HoldUsers.txt) 。 如果文本文件位于另一个文件夹中，请键入该文件的完整路径名。

收集脚本将提示您输入的信息后，最后一步是运行脚本以创建新保留并添加用户。
  
1. 使用文件名后缀将以下文本保存到 Windows PowerShell 脚本文件中 `.ps1` 。 例如，`AddUsersToHold.ps1`。

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
foreach($emailAddress in $emailAddresses)
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

4. 输入脚本提示您输入的信息。

   该脚本连接到安全&合规中心 PowerShell，然后在电子数据展示案例中创建新保留，并将邮箱和 OneDrive for Business 添加到列表中的用户。 你可以转到安全与合规中心电子数据 **展示页面上&** 查看新保留。

脚本运行完成后，将创建以下日志文件，并保存到脚本所在的文件夹中。
  
- **LocationsOnHold.txt：** 包含脚本成功置于保留的邮箱和 OneDrive for Business 站点的列表。

- **LocationsNotOnHold.txt：** 包含脚本未置于保留的邮箱和 OneDrive for Business 网站的列表。 如果用户有邮箱，但没有 OneDrive for Business 网站，该用户将包含在未置于保留的 OneDrive for Business 网站列表中。

- **GetCaseHoldPolicy.txt：** 包含新保留的 **Get-CaseHoldPolicy** cmdlet 的输出，脚本将在创建新保留后运行该 cmdlet。 此 cmdlet 返回的信息包括其邮箱和 OneDrive for Business 网站处于保留状态的用户列表，以及是启用还是禁用保留。 

- **GetCaseHoldRule.txt：** 包含新保留的 **Get-CaseHoldRule** cmdlet 的输出，脚本将在创建新保留后运行该 cmdlet。 如果使用脚本创建基于查询的保留，此 cmdlet 返回的信息将包含搜索查询。
