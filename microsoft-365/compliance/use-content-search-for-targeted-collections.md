---
title: 使用内容搜索进行目标收集
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
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: 使用安全与合规&中的内容搜索来执行目标集合，这样可以确保项目位于特定邮箱或网站文件夹中。
ms.openlocfilehash: aa311d0f9226330d9f2d881af6dabbdc6d0a15b5
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814534"
---
# <a name="use-content-search-for-targeted-collections"></a>使用内容搜索进行目标收集

在安全合规中心 &amp; 内的"内容搜索"功能不提供 UI 中搜索 Exchange 邮箱、SharePoint 和 OneDrive for Business 网站中特定文件夹的直接方式。 但是，可以搜索名为 (的特定文件夹 *) ，* 方法是在实际搜索查询语法中指定网站的电子邮件的文件夹 ID 属性或路径 (DocumentLink) 属性。 使用内容搜索来执行目标集合在你确信响应案例或特权项目位于特定邮箱或网站文件夹中时，可使用内容搜索执行目标收集。 您可以使用本文中的脚本获取邮箱文件夹的文件夹 ID，或 SharePoint 和 OneDrive for Business 站点上文件夹的路径 (DocumentLink) 。 然后，可在搜索查询中使用文件夹 ID 或路径返回位于文件夹中的项目。

> [!NOTE]
> 若要返回位于 SharePoint 或 OneDrive for Business 网站中文件夹的内容，本主题中的脚本使用 DocumentLink 托管属性，而不是 Path 属性。 DocumentLink 属性比 Path 属性更加可靠，因为它将返回文件夹中的所有内容，而 Path 属性不会返回某些媒体文件。

## <a name="before-you-use-content-search"></a>使用内容搜索之前

- 你必须是安全合规中心电子数据展示管理员角色 &amp; 组的成员，才能在步骤 1 中运行脚本。 有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。
    
    此外，必须在 Exchange Online 组织中分配有"邮件收件人"角色。 这是运行 **Get-MailboxFolderStatistics** cmdlet 所必需的，后者包含在步骤 1 的脚本中。 默认情况下，Mail Recipients 角色分配给 Exchange Online 中的 组织管理和收件人管理角色组。 有关在 Exchange Online 中分配权限的详细信息，请参阅 [管理角色组成员](https://go.microsoft.com/fwlink/p/?linkid=692102)。 您还可以创建自定义角色组，向其分配 Mail Recipients 角色，然后添加需要在步骤 1 中运行该脚本的成员。 有关详细信息，请参阅"[管理角色组"。](https://go.microsoft.com/fwlink/p/?linkid=730688)
    
- 每次在步骤 1 中运行此脚本时，都将创建新的远程 PowerShell 会话。 因此，你可以使用可用的远程 PowerShell 会话。 若要防止这种情况发生，可以运行以下命令断开与当前的远程 PowerShell 会话的连接。
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    有关详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
- 此脚本包括最少的错误处理。 该脚本的主要目的是快速显示可以在内容搜索的搜索查询语法中用于执行目标集合的邮箱文件夹 ID 或网站路径列表。
    
- 本主题中提供的示例脚本在任何 Microsoft 标准支持程序或服务下都不受支持。 此示例脚本"按 AS"提供，不含任何保证。 Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。 由示例脚本和文档产生的整个风险也将由您自行执行。 在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>步骤 1：运行脚本获取邮箱或站点的文件夹列表

在此第一步中运行的脚本将返回邮箱文件夹或 SharePoint 和 OneDrive for Business 文件夹的列表，以及每个文件夹的相应文件夹 ID 或路径。 运行此脚本时，它将提示您提供以下信息。
  
- **电子邮件地址或网站 URL** 键入保加大学的电子邮件地址以返回 Exchange 邮箱文件夹和文件夹 ID 的列表。 或者键入 SharePoint 网站或 OneDrive for Business 网站的 URL 以返回指定网站的路径列表。 下面是一些示例： 
    
  - **Exchange** - stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **您的用户凭据** - 脚本通过远程 PowerShell 使用您的凭据连接到 Exchange Online &安全合规中心。 如前所述，您必须分配相应的权限才能成功运行此脚本。
    
要显示邮箱文件夹或站点文档链接列表 (，) 名称：
  
1. 使用 .ps1 Windows PowerShell 文件名后缀将以下文本保存到脚本文件的一个移动脚本文件中;例如， `GetFolderSearchParameters.ps1` _
    
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
   if (!$credentials)
   {
      $credentials = Get-Credential
   }
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
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
      # Authenticate with the Security & Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
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

2. 在本地计算机上，打开Windows PowerShell请转到保存该脚本的文件夹。
    
3. 运行脚本;例如：
    
   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. 输入脚本提示你输入的信息。
    
    该脚本显示指定用户的邮箱文件夹或站点文件夹的列表。 将此窗口保持打开状态，以便复制文件夹 ID 或 documentlink 名称并将其粘贴到步骤 2 中的搜索查询中。
    
    > [!TIP]
    > 你可以将脚本的输出重新定向到某个文本文件，而无需在计算机屏幕上显示文件夹列表。 此文件将保存到脚本所在的文件夹中。 例如，若要将脚本输出重定向到文本文件，可在步骤 3 中运行以下命令：然后从该文件中复制文件夹 ID 或  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` documentlink 以用于搜索查询。
  
### <a name="script-output-for-mailbox-folders"></a>邮箱文件夹的脚本输出

如果您在获取邮箱文件夹 ID，脚本将使用远程 PowerShell 连接到 Exchange Online，运行 **Get-MailboxFolderStatisics** cmdlet，然后显示指定邮箱中的文件夹的列表。 对于邮箱中的每个文件夹，脚本会在 **FolderPath 列** 中显示文件夹的名称，在 **FolderQuery** 列中显示文件夹 ID。 此外，该脚本还会为文件夹 ID (添加 **folderId** 参数的前缀，这是) 邮箱属性名称。 由于 **folderid 属性** 是可搜索的属性，因此您将  `folderid:<folderid>` 在步骤 2 的搜索查询中使用该属性来搜索该文件夹。 该脚本最多可以显示 100 个邮箱文件夹。

> [!IMPORTANT]
> 本文中的脚本包括编码逻辑，可将 **Get-MailboxFolderStatistics** 返回的 64 个字符的文件夹 ID 值转换为与编制索引以供搜索的 48 个字符格式。 如果刚刚在 PowerShell **中运行 Get-MailboxFolderStatistics** cmdlet 来获取文件夹 ID (，而不是运行本文) 中的脚本，则使用该文件夹 ID 值的搜索查询将会失败。 您必须运行脚本才能获取可以在内容搜索中使用的格式正确设置的文件夹 ID。
  
下面的示例展示了邮箱文件夹的脚本返回的输出。
  
![该脚本返回的邮箱文件夹和文件夹 ID 的列表的示例](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
步骤 2 中的示例演示用于在用户的"可恢复的项目"文件夹中搜索"清除"子文件夹的查询。
  
### <a name="script-output-for-site-folders"></a>网站文件夹的脚本输出

如果从 SharePoint 或 OneDrive for Business 网站获取 **documentlink** 属性的路径，该脚本使用远程 PowerShell 连接到安全 & 合规中心，新建一个内容搜索，可在网站中搜索文件夹，然后显示指定站点中的文件夹列表。 该脚本显示每个文件夹的名称，并将 documentlink 的 **前缀添加到** 文件夹 URL 中。 由于 **documentlink 属性** 是一个可搜索的属性，因此将在步骤 2 的 `documentlink:<path>` 搜索查询中使用属性：value 对来搜索该文件夹。 该脚本最多可以显示 200 个站点文件夹。 如果有 200 个以上文件夹，将显示新文件夹。
  
下面的示例展示了网站文件夹的脚本返回的输出。
  
![该脚本返回的站点文件夹的 documentlink 名称列表示例](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>步骤 2：使用文件夹 ID 或文档链接执行目标集合

运行脚本收集特定用户的文件夹 ID 或文档链接列表后，下一步可转到安全 & 合规中心，并创建一个新的内容搜索来搜索特定文件夹。 如果使用 New-ComplianceSearch cmdlet 来创建 SharePoint cmdlet，则需要在内容搜索关键字框中 (配置的搜索查询将这 `folderid:<folderid>` `documentlink:<path>` 两个或属性 **/值**对用作*ContentMatchQuery*参数) 。 可以将该属性  `folderid` 与其他  `documentlink` 搜索参数或搜索条件组合使用。 如果您仅在查询  `folderid` 中  `documentlink` 包含或属性，搜索将返回指定文件夹中的所有项目。 
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 使用您在步骤 1 中运行脚本所用的帐户和凭据登录。
    
3. 在安全与合规中心的&窗格中，单击" **搜索** \> **内容搜索"，** 然后单击"新建 **添加** ![ "图标 ](../media/O365-MDM-CreatePolicy-AddIcon.gif) 。
    
4. 在“新建搜索”**** 页上，键入内容搜索的名称。 此名称在组织中必须是唯一的。 
    
5. 在 **哪里，执行以下操作**之一，以确定是搜索邮箱文件夹还是站点文件夹：
    
    - 单击 **"选择要搜索的特定** 邮箱"，然后添加您在步骤 1 中运行该脚本时指定的相同邮箱。 
    
      或
    
    - 单击 **"选择要搜索的特定** 网站"，然后添加您在步骤 1 中运行该脚本时指定的同一网站 URL。 
    
6. 单击“**下一步**”。
    
7. 在您希望我们 **查找页面的操作的关键字框中** ，粘贴  `folderid:<folderid>` 在步骤  `documentlink:<path>` 1 中由该脚本返回的值。 
    
    例如，以下屏幕截图中的查询将在用户的"可恢复的项目"文件夹中的"清除"子文件夹中搜索任何项目 (" `folderid` 清除"子文件夹的属性值将显示在步骤 1 中的屏幕截图) ：
    
    ![将 folderid 或 documentlink 粘贴到搜索查询的关键字框中](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. 单击 **"** 搜索"以启动目标集合搜索。 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>目标集合的搜索查询示例

下面是在搜索查询中使用  `folderid` 和  `documentlink` 属性来执行目标集合的一些示例。 请注意，占位符用于和  `folderid:<folderid>`  `documentlink:<path>` 节省空间。 
  
- 本示例搜索三个不同的邮箱文件夹。 可以使用类似的查询语法来搜索用户的"可恢复的项目"文件夹中的隐藏文件夹。
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- 本示例在邮箱文件夹中搜索包含精确短语的项目。
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- 本示例在标题中包含字母 ("NDA) 及其子文件夹及其所有子文件夹。
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- 此示例在日期范围内对 (网站集) 及其所有子文件夹搜索。
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>更多信息

使用本文中的脚本执行目标集合时，请记住以下内容。
  
- 脚本不会从结果中删除任何文件夹。 因此，结果中列出的某些文件夹可能不可搜索，也 (可能返回零) 因为它们包含系统生成的内容。
    
- This script only returns folder information for the user's primary mailbox. 不会返回有关用户存档邮箱中文件夹的信息。
    
- 在搜索邮箱文件夹时，将仅 (文件夹类型  `folderid`) 搜索;不能搜索子文件夹。 若要搜索子文件夹，您需要为要搜索的子文件夹使用文件夹 ID。 
    
- 搜索站点文件夹时，该文件夹 (属性和  `documentlink`) 系统将搜索所有子文件夹。 
    
- 导出仅在其中指定该属性的搜索的结果时，可 `folderid` 选择第一个导出选项"所有项目（不包括具有不可识别格式的项）、已加密或未编入索引的项。" 将始终导出该文件夹中的所有项目，而不考虑其索引状态，因为它始终为文件夹 ID 编制索引。
