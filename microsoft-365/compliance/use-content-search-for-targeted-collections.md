---
title: 使用内容搜索进行目标收集
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
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: 使用 Microsoft 365 合规性中心中的内容搜索来执行目标集合，以确保项位于特定邮箱或网站文件夹中。
ms.openlocfilehash: 0908b8262942e7a1c4d80bc511d4b8cbcc6dc646
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376586"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="0e433-103">使用内容搜索进行目标收集</span><span class="sxs-lookup"><span data-stu-id="0e433-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="0e433-104">Microsoft 365 合规性中心中的内容搜索功能在 UI 中不提供直接的方法来搜索 Exchange 邮箱或 SharePoint 和 OneDrive for business 网站中的特定文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-104">The Content Search feature in the Microsoft 365 compliance center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="0e433-105">但是，可以通过为电子邮件或路径 (DocumentLink) 属性为实际搜索查询语法中的网站指定文件夹 ID 属性，来搜索特定文件夹 (称为 *目标集合*) 。</span><span class="sxs-lookup"><span data-stu-id="0e433-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="0e433-106">当您确信项目响应的情况或特权项目位于特定邮箱或站点文件夹中时，使用内容搜索来执行目标集合非常有用。</span><span class="sxs-lookup"><span data-stu-id="0e433-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="0e433-107">您可以使用本文中的脚本获取邮箱文件夹的文件夹 ID 或 SharePoint 和 OneDrive for Business 网站上的文件夹的路径 (DocumentLink) 。</span><span class="sxs-lookup"><span data-stu-id="0e433-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="0e433-108">然后，您可以在搜索查询中使用文件夹 ID 或路径返回文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="0e433-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="0e433-109">若要返回位于 SharePoint 或 OneDrive for business 网站中的文件夹中的内容，本主题中的脚本使用 DocumentLink 托管属性而不是 Path 属性。</span><span class="sxs-lookup"><span data-stu-id="0e433-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="0e433-110">DocumentLink 属性比 Path 属性更可靠，因为它将返回文件夹中的所有内容，而 Path 属性将不会返回某些媒体文件。</span><span class="sxs-lookup"><span data-stu-id="0e433-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="0e433-111">在运行目标集合之前</span><span class="sxs-lookup"><span data-stu-id="0e433-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="0e433-112">您必须是 Security & 合规中心中的电子数据展示管理器角色组的成员，才能在步骤1中运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="0e433-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="0e433-113">有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="0e433-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

    <span data-ttu-id="0e433-114">此外，还必须在 Exchange Online 组织中为 "邮件收件人" 角色分配。</span><span class="sxs-lookup"><span data-stu-id="0e433-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="0e433-115">这是运行 **get-mailboxfolderstatistics** cmdlet （包含在脚本中）所必需的。</span><span class="sxs-lookup"><span data-stu-id="0e433-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script.</span></span> <span data-ttu-id="0e433-116">默认情况下，将 "邮件收件人" 角色分配给 Exchange Online 中的 "组织管理" 和 "收件人管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="0e433-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="0e433-117">有关在 Exchange Online 中分配权限的详细信息，请参阅 [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102)。</span><span class="sxs-lookup"><span data-stu-id="0e433-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="0e433-118">您还可以创建自定义角色组，将 "邮件收件人" 角色分配给该角色组，然后添加需要在步骤1中运行该脚本的成员。</span><span class="sxs-lookup"><span data-stu-id="0e433-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="0e433-119">有关详细信息，请参阅 [管理角色组](https://go.microsoft.com/fwlink/p/?linkid=730688)。</span><span class="sxs-lookup"><span data-stu-id="0e433-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>

- <span data-ttu-id="0e433-120">本文中的脚本支持新式验证。</span><span class="sxs-lookup"><span data-stu-id="0e433-120">The script in this article supports modern authentication.</span></span> <span data-ttu-id="0e433-121">如果你是 Microsoft 365 或 Microsoft 365 GCC 组织，则可以按如下所示使用脚本。</span><span class="sxs-lookup"><span data-stu-id="0e433-121">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="0e433-122">如果你是 Office 365 德国组织、Microsoft 365 GCC 高组织或 Microsoft 365 DoD 组织，则必须编辑脚本才能成功运行它。</span><span class="sxs-lookup"><span data-stu-id="0e433-122">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="0e433-123">具体来说，您必须编辑行 `Connect-ExchangeOnline` ，并使用 *ExchangeEnvironmentName* 参数 (并为您的组织类型) 连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0e433-123">Specifically, you have to edit the line `Connect-ExchangeOnline` and use the *ExchangeEnvironmentName* parameter (and the appropriate value for your organization type) to connect to Exchange Online PowerShell.</span></span>  <span data-ttu-id="0e433-124">此外，您还必须编辑行 `Connect-IPPSSession` ，并使用 *ConnectionUri* 和 *AzureADAuthorizationEndpointUri* 参数 (和组织类型的相应值) 连接到安全 & 合规中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0e433-124">Also, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="0e433-125">有关详细信息，请参阅 [连接到 Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) 和 [连接到安全 & 合规性中心 powershell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)中的示例。</span><span class="sxs-lookup"><span data-stu-id="0e433-125">For more information, see the examples in [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) and [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="0e433-126">每次运行该脚本时，都会创建一个新的远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="0e433-126">Each time you run the script, a new remote PowerShell session is created.</span></span> <span data-ttu-id="0e433-127">这意味着您可以使用所有可用的远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="0e433-127">That means you can use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="0e433-128">若要防止这种情况发生，请运行以下命令以断开活动的远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="0e433-128">To prevent this from happening, run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="0e433-129">有关详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="0e433-129">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="0e433-130">该脚本包括最少的错误处理。</span><span class="sxs-lookup"><span data-stu-id="0e433-130">The script includes minimal error handling.</span></span> <span data-ttu-id="0e433-131">脚本的主要用途是快速显示邮箱文件夹 Id 或网站路径的列表，该列表可用于内容搜索的搜索查询语法以执行目标集合。</span><span class="sxs-lookup"><span data-stu-id="0e433-131">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="0e433-132">在任何 Microsoft standard 支持计划或服务下，本主题中提供的示例脚本不受支持。</span><span class="sxs-lookup"><span data-stu-id="0e433-132">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="0e433-133">示例脚本按原样提供，而不提供任何种类的担保。</span><span class="sxs-lookup"><span data-stu-id="0e433-133">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="0e433-134">Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。</span><span class="sxs-lookup"><span data-stu-id="0e433-134">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="0e433-135">因使用或性能示例脚本和文档而导致的全部风险都将保留给您。</span><span class="sxs-lookup"><span data-stu-id="0e433-135">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="0e433-136">在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。</span><span class="sxs-lookup"><span data-stu-id="0e433-136">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="0e433-137">步骤1：运行脚本以获取邮箱或网站的文件夹列表</span><span class="sxs-lookup"><span data-stu-id="0e433-137">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="0e433-138">您在此第一步中运行的脚本将返回邮箱文件夹或 SharePoint 和 OneDrive for business 文件夹的列表，以及每个文件夹对应的文件夹 ID 或路径。</span><span class="sxs-lookup"><span data-stu-id="0e433-138">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="0e433-139">运行此脚本时，它将提示您提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="0e433-139">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="0e433-140">**电子邮件地址或网站 URL**：键入保管人的电子邮件地址，以返回 Exchange 邮箱文件夹和文件夹 id 的列表。</span><span class="sxs-lookup"><span data-stu-id="0e433-140">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="0e433-141">或者键入 SharePoint 网站或 OneDrive for business 网站的 URL，以返回指定网站的路径列表。</span><span class="sxs-lookup"><span data-stu-id="0e433-141">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="0e433-142">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="0e433-142">Here are some examples:</span></span>

  - <span data-ttu-id="0e433-143">**Exchange**： <spam> stacig@contoso .onmicrosoft <spam></span><span class="sxs-lookup"><span data-stu-id="0e433-143">**Exchange**: stacig@contoso.onmicrosoft<spam><spam>.com</span></span>

  - <span data-ttu-id="0e433-144">**SharePoint**： https：<span>//</span>contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="0e433-144">**SharePoint**: https<span>://</span>contoso.sharepoint.com/sites/marketing</span></span> 

  - <span data-ttu-id="0e433-145">**OneDrive For business**： https：<span>//</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="0e433-145">**OneDrive for Business**: https<span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 

- <span data-ttu-id="0e433-146">**您的用户凭据**：该脚本将使用新式验证，通过您的凭据连接到 Exchange Online Powershell 或 Security & 合规性中心 powershell。</span><span class="sxs-lookup"><span data-stu-id="0e433-146">**Your user credentials**: The script will use your credentials to connect to Exchange Online PowerShell or Security & Compliance Center PowerShell using modern authentication.</span></span> <span data-ttu-id="0e433-147">如前文所述，您必须分配适当的权限才能成功运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="0e433-147">As previously explained, you have to be assigned the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="0e433-148">若要显示邮箱文件夹或网站 documentlink 的列表，请 (路径) 名称：</span><span class="sxs-lookup"><span data-stu-id="0e433-148">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="0e433-149">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如， `GetFolderSearchParameters.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="0e433-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>

   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Security & Compliance Center.            #
   # The script will then:                                            #
   #    * If an email address is supplied: list the folders for the target mailbox.            #
   #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
   #    * for the site.                                                                                    #
   #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)    #
   #      appended to the folder ID or documentlink to use in a Content Search.                #
   # Notes:                                                #
   #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the     #
   #      the current folder and all sub-folders are searched.                        #
   #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder    #
   #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
   #      each sub-folder that you want to search.                                #
   #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.        #
   #########################################################################################################
   # Collect the target email address or SharePoint Url
   $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
   # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
   }
   elseif ($addressOrSite.IndexOf("http") -ige 0)
   {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Connect to Security & Compliance Center PowerShell
      if (!$SccSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-IPPSSession
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
   }
   else
   {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
   }
   ```

2. <span data-ttu-id="0e433-150">在本地计算机上，打开 Windows PowerShell 并转到保存该脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-150">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="0e433-151">运行脚本;例如：</span><span class="sxs-lookup"><span data-stu-id="0e433-151">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="0e433-152">输入脚本提示您输入的信息。</span><span class="sxs-lookup"><span data-stu-id="0e433-152">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="0e433-153">该脚本将显示指定用户的邮箱文件夹或网站文件夹的列表。</span><span class="sxs-lookup"><span data-stu-id="0e433-153">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="0e433-154">将此窗口保持为打开状态，以便您可以复制文件夹 ID 或 documentlink 名称，并将其粘贴到步骤2中的搜索查询中。</span><span class="sxs-lookup"><span data-stu-id="0e433-154">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="0e433-155">您可以将脚本的输出重新定向到文本文件，而不是在计算机屏幕上显示文件夹的列表。</span><span class="sxs-lookup"><span data-stu-id="0e433-155">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="0e433-156">此文件将保存到脚本所在的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0e433-156">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="0e433-157">例如，若要将脚本输出重定向到文本文件，请在第3步中运行以下命令：  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` 然后，可以从要在搜索查询中使用的文件中复制文件夹 ID 或 documentlink。</span><span class="sxs-lookup"><span data-stu-id="0e433-157">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="0e433-158">邮箱文件夹的脚本输出</span><span class="sxs-lookup"><span data-stu-id="0e433-158">Script output for mailbox folders</span></span>

<span data-ttu-id="0e433-159">如果你获取的是邮箱文件夹 Id，脚本将连接到 Exchange Online PowerShell，运行 **MailboxFolderStatisics** cmdlet，然后显示指定邮箱中的文件夹列表。</span><span class="sxs-lookup"><span data-stu-id="0e433-159">If you're getting mailbox folder IDs, the script connects to Exchange Online PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="0e433-160">对于邮箱中的每个文件夹，该脚本都会在 " **FolderPath** " 列中显示文件夹的名称，并在 " **FolderQuery** " 列中显示文件夹 ID。</span><span class="sxs-lookup"><span data-stu-id="0e433-160">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="0e433-161">此外，该脚本会将 **folderId** (的前缀添加到文件夹 ID) 的邮箱属性的名称。</span><span class="sxs-lookup"><span data-stu-id="0e433-161">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="0e433-162">由于 **folderid** 属性是一个可搜索的属性，因此您将  `folderid:<folderid>` 在步骤2中的搜索查询中使用搜索该文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-162">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="0e433-163">该脚本最多显示100个邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-163">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e433-164">本文中的脚本包含编码逻辑，用于将 **get-mailboxfolderstatistics** 返回的64字符文件夹 Id 值转换为与为搜索编制索引的相同48字符格式。</span><span class="sxs-lookup"><span data-stu-id="0e433-164">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="0e433-165">如果您只在 PowerShell 中运行 **get-mailboxfolderstatistics** cmdlet 来获取文件夹 Id (而不是在本文中运行脚本) ，则使用该文件夹 id 值的搜索查询将失败。</span><span class="sxs-lookup"><span data-stu-id="0e433-165">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="0e433-166">您必须运行脚本才能获取可在内容搜索中使用的格式正确的文件夹 Id。</span><span class="sxs-lookup"><span data-stu-id="0e433-166">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="0e433-167">下面的示例展示了邮箱文件夹的脚本返回的输出。</span><span class="sxs-lookup"><span data-stu-id="0e433-167">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![脚本返回的邮箱文件夹和文件夹 Id 列表的示例](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="0e433-169">步骤2中的示例显示了用于在用户的 "可恢复的项目" 文件夹中搜索 "清除" 子文件夹的查询。</span><span class="sxs-lookup"><span data-stu-id="0e433-169">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="0e433-170">网站文件夹的脚本输出</span><span class="sxs-lookup"><span data-stu-id="0e433-170">Script output for site folders</span></span>

<span data-ttu-id="0e433-171">如果您从 SharePoint 或 OneDrive for Business 网站获取 **documentlink** 属性的路径，则脚本会连接到安全 & 合规性 PowerShell，创建一个新的内容搜索以搜索网站中的文件夹，然后显示位于指定网站中的文件夹的列表。</span><span class="sxs-lookup"><span data-stu-id="0e433-171">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to Security & Compliance PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="0e433-172">该脚本将显示每个文件夹的名称，并将 **documentlink** 的前缀添加到文件夹 URL 中。</span><span class="sxs-lookup"><span data-stu-id="0e433-172">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="0e433-173">由于 **documentlink** 属性是一个可搜索的属性，因此您将在 `documentlink:<path>` 步骤2中的搜索查询中使用属性： value 对来搜索该文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-173">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="0e433-174">该脚本最多显示200个网站文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-174">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="0e433-175">如果网站文件夹多于200，则显示最新的网站文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-175">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="0e433-176">下面的示例展示了网站文件夹的脚本返回的输出。</span><span class="sxs-lookup"><span data-stu-id="0e433-176">Here's an example of the output returned by the script for site folders.</span></span>
  
![脚本返回的网站文件夹的 documentlink 名称列表示例](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="0e433-178">步骤2：使用文件夹 ID 或 documentlink 执行目标集合</span><span class="sxs-lookup"><span data-stu-id="0e433-178">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="0e433-179">在运行脚本以收集特定用户的文件夹 Id 或文档链接列表后，下一步是转到 Microsoft 365 合规性中心，并创建新的内容搜索以搜索特定文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-179">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Microsoft 365 compliance center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="0e433-180">您将在 " `folderid:<folderid>` `documentlink:<path>` 内容搜索关键字" 框中配置的搜索查询中使用 or property： value 对，如果使用 **new-compliancesearch** cmdlet) ，则 (或作为 *ContentMatchQuery* 参数的值。</span><span class="sxs-lookup"><span data-stu-id="0e433-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="0e433-181">您可以将  `folderid` 或  `documentlink` 属性与其他搜索参数或搜索条件结合使用。</span><span class="sxs-lookup"><span data-stu-id="0e433-181">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="0e433-182">如果只  `folderid`  `documentlink` 在查询中包括或属性，则搜索将返回位于指定文件夹中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="0e433-182">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>
  
1. <span data-ttu-id="0e433-183">转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并使用您在步骤1中运行脚本时使用的帐户和凭据登录。</span><span class="sxs-lookup"><span data-stu-id="0e433-183">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the account and credentials that you used to run the script in Step 1.</span></span>

2. <span data-ttu-id="0e433-184">在合规性中心的左侧窗格中，单击 "**显示所有**  >  **内容搜索**"，然后单击 "**新建搜索**"。</span><span class="sxs-lookup"><span data-stu-id="0e433-184">In the left pane of the compliance center, click **Show all** > **Content search**, and then click **New search**.</span></span>

3. <span data-ttu-id="0e433-185">在 " **关键字** " 框中， `folderid:<folderid>` 粘贴  `documentlink:<path>` 步骤1中的脚本返回的 or 值。</span><span class="sxs-lookup"><span data-stu-id="0e433-185">In the **Keywords** box, paste the `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span>

    <span data-ttu-id="0e433-186">例如，下面的屏幕截图中的查询将搜索用户的 "可恢复项目" 文件夹中的 "清除" 子文件夹中的任何项目 (" `folderid` 清除" 子文件夹属性的值在步骤 1) 中的屏幕截图中显示：</span><span class="sxs-lookup"><span data-stu-id="0e433-186">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![将 folderid 或 documentlink 粘贴到搜索查询的关键字框中](../media/FolderIDSearchQuery.png)

4. <span data-ttu-id="0e433-188">在 " **位置**" 下，选择 " **特定位置** "，然后单击 " **修改**"。</span><span class="sxs-lookup"><span data-stu-id="0e433-188">Under **Locations**, select **Specific locations** and then click **Modify**.</span></span>

5. <span data-ttu-id="0e433-189">根据您搜索的是邮箱文件夹还是网站文件夹，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="0e433-189">Do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="0e433-190">在 " **Exchange 电子邮件**" 旁边，单击 " **选择用户、组或团队** "，然后添加您在步骤1中运行脚本时指定的相同邮箱。</span><span class="sxs-lookup"><span data-stu-id="0e433-190">Next to **Exchange email**, click **Choose users, groups, or teams** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="0e433-191">或</span><span class="sxs-lookup"><span data-stu-id="0e433-191">Or</span></span>

    - <span data-ttu-id="0e433-192">在 " **SharePoint 网站**" 旁边，单击 " **选择网站** "，然后添加在步骤1中运行脚本时指定的相同网站 URL。</span><span class="sxs-lookup"><span data-stu-id="0e433-192">Next to **SharePoint sites**, click **Choose sites** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="0e433-193">将内容位置保存到搜索后，单击 " **保存 &**" "运行"，键入内容搜索的名称，然后单击 " **保存** " 以启动目标集合搜索。</span><span class="sxs-lookup"><span data-stu-id="0e433-193">After you save the content location to search, click **Save & run**, type a name for the Content Search, and then click **Save** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="0e433-194">目标集合的搜索查询示例</span><span class="sxs-lookup"><span data-stu-id="0e433-194">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="0e433-195">下面是  `folderid`  `documentlink` 在搜索查询中使用和属性执行目标集合的一些示例。</span><span class="sxs-lookup"><span data-stu-id="0e433-195">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="0e433-196">占位符用于  `folderid:<folderid>`  `documentlink:<path>` 节省空间。</span><span class="sxs-lookup"><span data-stu-id="0e433-196">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="0e433-197">本示例将搜索三个不同的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-197">This example searches three different mailbox folders.</span></span> <span data-ttu-id="0e433-198">可以使用类似的查询语法搜索用户的 "可恢复的项目" 文件夹中的隐藏文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-198">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="0e433-199">本示例将在邮箱文件夹中搜索包含精确短语的项目。</span><span class="sxs-lookup"><span data-stu-id="0e433-199">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="0e433-200">本示例将在标题中搜索包含字母 "NDA" 的文档的 "网站" 文件夹 (和所有子文件夹) 。</span><span class="sxs-lookup"><span data-stu-id="0e433-200">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="0e433-201">本示例将在某个日期范围内的所有已更改的文档 (和子文件夹) 中搜索该文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-201">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="0e433-202">更多信息</span><span class="sxs-lookup"><span data-stu-id="0e433-202">More information</span></span>

<span data-ttu-id="0e433-203">在使用本文中的脚本执行目标集合时，请记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="0e433-203">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="0e433-204">脚本不会从结果中删除任何文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-204">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="0e433-205">因此，在结果中列出的某些文件夹可能会不可搜索 (或返回零个项目) 因为它们包含系统生成的内容，或者它们仅包含子文件夹，而不包含邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="0e433-205">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="0e433-206">此脚本仅返回用户的主邮箱的文件夹信息。</span><span class="sxs-lookup"><span data-stu-id="0e433-206">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="0e433-207">它不会返回有关用户存档邮箱中的文件夹的信息。</span><span class="sxs-lookup"><span data-stu-id="0e433-207">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="0e433-208">若要返回有关用户存档邮箱中的文件夹的信息，您可以编辑该脚本。</span><span class="sxs-lookup"><span data-stu-id="0e433-208">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="0e433-209">若要执行此操作，请将该行更改 `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` 为， `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` 然后保存并运行编辑后的脚本。</span><span class="sxs-lookup"><span data-stu-id="0e433-209">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="0e433-210">此更改将返回用户存档邮箱中的文件夹和子文件夹的文件夹 Id。</span><span class="sxs-lookup"><span data-stu-id="0e433-210">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="0e433-211">若要搜索整个存档邮箱，可以 `OR` 在搜索查询中将所有文件夹 ID 属性：值对与运算符相连接。</span><span class="sxs-lookup"><span data-stu-id="0e433-211">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="0e433-212">搜索邮箱文件夹时，将仅搜索指定的文件夹 (由其 `folderid` 属性) 标识; 不会搜索子文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-212">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="0e433-213">若要搜索子文件夹，您需要使用要搜索的子文件夹的文件夹 ID。</span><span class="sxs-lookup"><span data-stu-id="0e433-213">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="0e433-214">搜索站点文件夹时，文件夹 (由其属性标识 `documentlink`) 并将搜索所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e433-214">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span> 

- <span data-ttu-id="0e433-215">当您在搜索查询中导出仅指定属性的搜索结果时 `folderid` ，可以选择第一个导出选项 "。所有项目（不包括具有不可识别的格式的项目）已加密，或未对其他原因编制索引。</span><span class="sxs-lookup"><span data-stu-id="0e433-215">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="0e433-216">将始终导出文件夹中的所有项目（无论其索引状态如何），因为文件夹 ID 始终编制索引。</span><span class="sxs-lookup"><span data-stu-id="0e433-216">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
