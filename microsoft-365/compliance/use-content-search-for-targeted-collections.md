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
# <a name="use-content-search-for-targeted-collections"></a>使用内容搜索进行目标收集

Microsoft 365 合规性中心中的内容搜索功能在 UI 中不提供直接的方法来搜索 Exchange 邮箱或 SharePoint 和 OneDrive for business 网站中的特定文件夹。 但是，可以通过为电子邮件或路径 (DocumentLink) 属性为实际搜索查询语法中的网站指定文件夹 ID 属性，来搜索特定文件夹 (称为 *目标集合*) 。 当您确信项目响应的情况或特权项目位于特定邮箱或站点文件夹中时，使用内容搜索来执行目标集合非常有用。 您可以使用本文中的脚本获取邮箱文件夹的文件夹 ID 或 SharePoint 和 OneDrive for Business 网站上的文件夹的路径 (DocumentLink) 。 然后，您可以在搜索查询中使用文件夹 ID 或路径返回文件夹中的项目。

> [!NOTE]
> 若要返回位于 SharePoint 或 OneDrive for business 网站中的文件夹中的内容，本主题中的脚本使用 DocumentLink 托管属性而不是 Path 属性。 DocumentLink 属性比 Path 属性更可靠，因为它将返回文件夹中的所有内容，而 Path 属性将不会返回某些媒体文件。

## <a name="before-you-run-a-targeted-collection"></a>在运行目标集合之前

- 您必须是 Security & 合规中心中的电子数据展示管理器角色组的成员，才能在步骤1中运行该脚本。 有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。

    此外，还必须在 Exchange Online 组织中为 "邮件收件人" 角色分配。 这是运行 **get-mailboxfolderstatistics** cmdlet （包含在脚本中）所必需的。 默认情况下，将 "邮件收件人" 角色分配给 Exchange Online 中的 "组织管理" 和 "收件人管理" 角色组。 有关在 Exchange Online 中分配权限的详细信息，请参阅 [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102)。 您还可以创建自定义角色组，将 "邮件收件人" 角色分配给该角色组，然后添加需要在步骤1中运行该脚本的成员。 有关详细信息，请参阅 [管理角色组](https://go.microsoft.com/fwlink/p/?linkid=730688)。

- 本文中的脚本支持新式验证。 如果你是 Microsoft 365 或 Microsoft 365 GCC 组织，则可以按如下所示使用脚本。 如果你是 Office 365 德国组织、Microsoft 365 GCC 高组织或 Microsoft 365 DoD 组织，则必须编辑脚本才能成功运行它。 具体来说，您必须编辑行 `Connect-ExchangeOnline` ，并使用 *ExchangeEnvironmentName* 参数 (并为您的组织类型) 连接到 Exchange Online PowerShell。  此外，您还必须编辑行 `Connect-IPPSSession` ，并使用 *ConnectionUri* 和 *AzureADAuthorizationEndpointUri* 参数 (和组织类型的相应值) 连接到安全 & 合规中心 PowerShell。 有关详细信息，请参阅 [连接到 Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) 和 [连接到安全 & 合规性中心 powershell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)中的示例。

- 每次运行该脚本时，都会创建一个新的远程 PowerShell 会话。 这意味着您可以使用所有可用的远程 PowerShell 会话。 若要防止这种情况发生，请运行以下命令以断开活动的远程 PowerShell 会话。

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    有关详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)。

- 该脚本包括最少的错误处理。 脚本的主要用途是快速显示邮箱文件夹 Id 或网站路径的列表，该列表可用于内容搜索的搜索查询语法以执行目标集合。

- 在任何 Microsoft standard 支持计划或服务下，本主题中提供的示例脚本不受支持。 示例脚本按原样提供，而不提供任何种类的担保。 Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。 因使用或性能示例脚本和文档而导致的全部风险都将保留给您。 在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>步骤1：运行脚本以获取邮箱或网站的文件夹列表

您在此第一步中运行的脚本将返回邮箱文件夹或 SharePoint 和 OneDrive for business 文件夹的列表，以及每个文件夹对应的文件夹 ID 或路径。 运行此脚本时，它将提示您提供以下信息。
  
- **电子邮件地址或网站 URL**：键入保管人的电子邮件地址，以返回 Exchange 邮箱文件夹和文件夹 id 的列表。 或者键入 SharePoint 网站或 OneDrive for business 网站的 URL，以返回指定网站的路径列表。 下面是一些示例：

  - **Exchange**： <spam> stacig@contoso .onmicrosoft <spam>

  - **SharePoint**： https：<span>//</span>contoso.sharepoint.com/sites/marketing 

  - **OneDrive For business**： https：<span>//</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 

- **您的用户凭据**：该脚本将使用新式验证，通过您的凭据连接到 Exchange Online Powershell 或 Security & 合规性中心 powershell。 如前文所述，您必须分配适当的权限才能成功运行此脚本。

若要显示邮箱文件夹或网站 documentlink 的列表，请 (路径) 名称：
  
1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如， `GetFolderSearchParameters.ps1` 。

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

2. 在本地计算机上，打开 Windows PowerShell 并转到保存该脚本的文件夹。

3. 运行脚本;例如：

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. 输入脚本提示您输入的信息。

    该脚本将显示指定用户的邮箱文件夹或网站文件夹的列表。 将此窗口保持为打开状态，以便您可以复制文件夹 ID 或 documentlink 名称，并将其粘贴到步骤2中的搜索查询中。

    > [!TIP]
    > 您可以将脚本的输出重新定向到文本文件，而不是在计算机屏幕上显示文件夹的列表。 此文件将保存到脚本所在的文件夹中。 例如，若要将脚本输出重定向到文本文件，请在第3步中运行以下命令：  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` 然后，可以从要在搜索查询中使用的文件中复制文件夹 ID 或 documentlink。
  
### <a name="script-output-for-mailbox-folders"></a>邮箱文件夹的脚本输出

如果你获取的是邮箱文件夹 Id，脚本将连接到 Exchange Online PowerShell，运行 **MailboxFolderStatisics** cmdlet，然后显示指定邮箱中的文件夹列表。 对于邮箱中的每个文件夹，该脚本都会在 " **FolderPath** " 列中显示文件夹的名称，并在 " **FolderQuery** " 列中显示文件夹 ID。 此外，该脚本会将 **folderId** (的前缀添加到文件夹 ID) 的邮箱属性的名称。 由于 **folderid** 属性是一个可搜索的属性，因此您将  `folderid:<folderid>` 在步骤2中的搜索查询中使用搜索该文件夹。 该脚本最多显示100个邮箱文件夹。

> [!IMPORTANT]
> 本文中的脚本包含编码逻辑，用于将 **get-mailboxfolderstatistics** 返回的64字符文件夹 Id 值转换为与为搜索编制索引的相同48字符格式。 如果您只在 PowerShell 中运行 **get-mailboxfolderstatistics** cmdlet 来获取文件夹 Id (而不是在本文中运行脚本) ，则使用该文件夹 id 值的搜索查询将失败。 您必须运行脚本才能获取可在内容搜索中使用的格式正确的文件夹 Id。
  
下面的示例展示了邮箱文件夹的脚本返回的输出。
  
![脚本返回的邮箱文件夹和文件夹 Id 列表的示例](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
步骤2中的示例显示了用于在用户的 "可恢复的项目" 文件夹中搜索 "清除" 子文件夹的查询。
  
### <a name="script-output-for-site-folders"></a>网站文件夹的脚本输出

如果您从 SharePoint 或 OneDrive for Business 网站获取 **documentlink** 属性的路径，则脚本会连接到安全 & 合规性 PowerShell，创建一个新的内容搜索以搜索网站中的文件夹，然后显示位于指定网站中的文件夹的列表。 该脚本将显示每个文件夹的名称，并将 **documentlink** 的前缀添加到文件夹 URL 中。 由于 **documentlink** 属性是一个可搜索的属性，因此您将在 `documentlink:<path>` 步骤2中的搜索查询中使用属性： value 对来搜索该文件夹。 该脚本最多显示200个网站文件夹。 如果网站文件夹多于200，则显示最新的网站文件夹。
  
下面的示例展示了网站文件夹的脚本返回的输出。
  
![脚本返回的网站文件夹的 documentlink 名称列表示例](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>步骤2：使用文件夹 ID 或 documentlink 执行目标集合

在运行脚本以收集特定用户的文件夹 Id 或文档链接列表后，下一步是转到 Microsoft 365 合规性中心，并创建新的内容搜索以搜索特定文件夹。 您将在 " `folderid:<folderid>` `documentlink:<path>` 内容搜索关键字" 框中配置的搜索查询中使用 or property： value 对，如果使用 **new-compliancesearch** cmdlet) ，则 (或作为 *ContentMatchQuery* 参数的值。 您可以将  `folderid` 或  `documentlink` 属性与其他搜索参数或搜索条件结合使用。 如果只  `folderid`  `documentlink` 在查询中包括或属性，则搜索将返回位于指定文件夹中的所有项目。
  
1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并使用您在步骤1中运行脚本时使用的帐户和凭据登录。

2. 在合规性中心的左侧窗格中，单击 "**显示所有**  >  **内容搜索**"，然后单击 "**新建搜索**"。

3. 在 " **关键字** " 框中， `folderid:<folderid>` 粘贴  `documentlink:<path>` 步骤1中的脚本返回的 or 值。

    例如，下面的屏幕截图中的查询将搜索用户的 "可恢复项目" 文件夹中的 "清除" 子文件夹中的任何项目 (" `folderid` 清除" 子文件夹属性的值在步骤 1) 中的屏幕截图中显示：

    ![将 folderid 或 documentlink 粘贴到搜索查询的关键字框中](../media/FolderIDSearchQuery.png)

4. 在 " **位置**" 下，选择 " **特定位置** "，然后单击 " **修改**"。

5. 根据您搜索的是邮箱文件夹还是网站文件夹，执行下列操作之一：

    - 在 " **Exchange 电子邮件**" 旁边，单击 " **选择用户、组或团队** "，然后添加您在步骤1中运行脚本时指定的相同邮箱。

      或

    - 在 " **SharePoint 网站**" 旁边，单击 " **选择网站** "，然后添加在步骤1中运行脚本时指定的相同网站 URL。

6. 将内容位置保存到搜索后，单击 " **保存 &**" "运行"，键入内容搜索的名称，然后单击 " **保存** " 以启动目标集合搜索。 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>目标集合的搜索查询示例

下面是  `folderid`  `documentlink` 在搜索查询中使用和属性执行目标集合的一些示例。 占位符用于  `folderid:<folderid>`  `documentlink:<path>` 节省空间。 
  
- 本示例将搜索三个不同的邮箱文件夹。 可以使用类似的查询语法搜索用户的 "可恢复的项目" 文件夹中的隐藏文件夹。

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- 本示例将在邮箱文件夹中搜索包含精确短语的项目。

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- 本示例将在标题中搜索包含字母 "NDA" 的文档的 "网站" 文件夹 (和所有子文件夹) 。

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- 本示例将在某个日期范围内的所有已更改的文档 (和子文件夹) 中搜索该文件夹。

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>更多信息

在使用本文中的脚本执行目标集合时，请记住以下事项。
  
- 脚本不会从结果中删除任何文件夹。 因此，在结果中列出的某些文件夹可能会不可搜索 (或返回零个项目) 因为它们包含系统生成的内容，或者它们仅包含子文件夹，而不包含邮箱项目。

- 此脚本仅返回用户的主邮箱的文件夹信息。 它不会返回有关用户存档邮箱中的文件夹的信息。 若要返回有关用户存档邮箱中的文件夹的信息，您可以编辑该脚本。 若要执行此操作，请将该行更改 `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` 为， `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` 然后保存并运行编辑后的脚本。 此更改将返回用户存档邮箱中的文件夹和子文件夹的文件夹 Id。 若要搜索整个存档邮箱，可以 `OR` 在搜索查询中将所有文件夹 ID 属性：值对与运算符相连接。

- 搜索邮箱文件夹时，将仅搜索指定的文件夹 (由其 `folderid` 属性) 标识; 不会搜索子文件夹。 若要搜索子文件夹，您需要使用要搜索的子文件夹的文件夹 ID。

- 搜索站点文件夹时，文件夹 (由其属性标识 `documentlink`) 并将搜索所有子文件夹。 

- 当您在搜索查询中导出仅指定属性的搜索结果时 `folderid` ，可以选择第一个导出选项 "。所有项目（不包括具有不可识别的格式的项目）已加密，或未对其他原因编制索引。 将始终导出文件夹中的所有项目（无论其索引状态如何），因为文件夹 ID 始终编制索引。
