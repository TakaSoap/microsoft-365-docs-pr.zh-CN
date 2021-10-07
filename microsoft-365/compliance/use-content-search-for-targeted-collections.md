---
title: 对目标集合使用内容搜索
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
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: 使用网站集中的内容Microsoft 365 合规中心执行目标集合，该集合可搜索特定邮箱或网站文件夹中的项目。
ms.openlocfilehash: 51989a87d3ba402923f0c5dcaba74d73cb80448d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60187169"
---
# <a name="use-content-search-for-targeted-collections"></a>对目标集合使用内容搜索

内容搜索工具Microsoft 365 合规中心 UI 中直接搜索 Exchange 邮箱或 SharePoint 和 OneDrive for Business 文件夹。 但是，可以搜索特定文件夹 (称为目标集合 *) ，* 具体方法为使用实际搜索查询语法为网站指定电子邮件的文件夹 ID 属性或路径 (DocumentLink) 属性。 当您确信对案例或特权项目做出响应的项目位于特定邮箱或网站文件夹中时，使用内容搜索执行目标集合非常有用。 您可以使用本文中的脚本获取邮箱文件夹的文件夹 ID，或获取 (和 OneDrive for Business SharePoint 网站上文件夹的 DocumentLink) 路径。 然后，可以在搜索查询中使用该文件夹 ID 或路径返回文件夹中的项目。

> [!NOTE]
> 若要返回位于网站或 SharePoint OneDrive for Business 文件夹中的内容，本主题中的脚本使用 DocumentLink 托管属性而不是 Path 属性。 DocumentLink 属性比 Path 属性更可靠，因为它将返回文件夹中的所有内容，而 Path 属性不会返回某些媒体文件。

## <a name="before-you-run-a-targeted-collection"></a>运行目标集合之前

- 您必须是步骤 1 中电子数据展示管理员Microsoft 365 合规中心组的成员，以运行脚本。 有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。

- 还必须在您的组织中分配"邮件收件人"Exchange Online角色。 这是运行脚本中包含的 **Get-MailboxFolderStatistics** cmdlet 所需的。 默认情况下，"邮件收件人"角色分配给组织中"组织管理"和"收件人管理"角色Exchange Online。 有关在角色分配中分配权限Exchange Online，请参阅[管理角色组成员](/exchange/manage-role-group-members-exchange-2013-help)。 您还可以创建自定义角色组，为其分配"邮件收件人"角色，然后添加需要在步骤 1 中运行脚本的成员。 有关详细信息，请参阅管理 [角色组](/Exchange/permissions-exo/role-groups)。

- 本文中的脚本支持新式验证。 如果你是组织成员或组织成员，Microsoft 365使用Microsoft 365 GCC脚本。 如果你是德国Office 365组织、Microsoft 365 GCC高组织或 Microsoft 365 DoD 组织，您必须编辑脚本以成功运行它。 具体而言，您必须编辑行并使用 `Connect-ExchangeOnline` *ExchangeEnvironmentName* 参数 (以及您的组织类型相应的值) 连接到 Exchange Online PowerShell。  此外，您必须编辑行并使用 `Connect-IPPSSession` *ConnectionUri* 和 *AzureADAuthorizationEndpointUri* 参数 (以及组织类型) 的适当值连接到安全 & 合规中心 PowerShell。 有关详细信息，请参阅 连接 Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa)中Exchange Online并连接安全&中心[PowerShell。](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)

- 每次运行脚本时，将创建一个新的远程 PowerShell 会话。 这意味着您可以使用所有可用的远程 PowerShell 会话。 为了防止发生这种情况，请运行以下命令来断开活动远程 PowerShell 会话。

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    有关详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

- 该脚本包括最少的错误处理。 该脚本的主要目的是快速显示邮箱文件夹的 ID 或网站路径的列表，这些地址或路径可用于内容搜索的搜索查询语法以执行目标集合。

- 本主题中提供的示例脚本在任何 Microsoft 标准支持计划或服务下都不受支持。 示例脚本“原样”提供，不提供任何形式的保证。 Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。 由于示例脚本及文档的使用或性能所引起的全部风险均由你承担。 在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>步骤 1：运行脚本，获取邮箱或站点的文件夹列表

第一步中运行的脚本将返回邮箱文件夹或 SharePoint 和 OneDrive for Business 文件夹的列表，以及每个文件夹的相应文件夹 ID 或路径。 运行此脚本时，它将提示您输入以下信息。

- **电子邮件地址或站点 URL：** 键入保管人的电子邮件地址，以返回邮箱Exchange和文件夹 ID 的列表。 或者键入网站或SharePoint网站的 URL OneDrive for Business返回指定网站的路径列表。 下面是一些示例：

  - **Exchange**：`stacig@contoso.onmicrosoft.com`

  - **SharePoint**：`https://contoso.sharepoint.com/sites/marketing`

  - **OneDrive for Business**：`https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com`

- **用户凭据**：脚本将使用你的凭据连接到使用新式Exchange Online PowerShell &安全与合规中心 PowerShell。 如前所述，您必须获得适当的权限才能成功运行此脚本。

若要显示邮箱文件夹列表或网站文档链接 (路径) 名称：

1. 将以下文本保存到Windows PowerShell脚本文件中，使用文件名后缀.ps1;例如， `GetFolderSearchParameters.ps1` 。

   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Microsoft 365 compliance center.            #
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
   # Authenticate with Exchange Online and the Microsoft 365 compliance center (Exchange Online Protection - EOP)
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

2. 在本地计算机上，打开Windows PowerShell转到保存脚本的文件夹。

3. 运行脚本;例如：

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. 输入脚本提示您输入的信息。

    该脚本显示指定用户的邮箱文件夹或站点文件夹的列表。 保持此窗口为打开状态，以便您可以复制文件夹 ID 或文档链接名称并将其粘贴到步骤 2 中的搜索查询。

    > [!TIP]
    > 你可以将脚本的输出重新引导到文本文件，而不是在计算机屏幕上显示文件夹列表。 此文件将保存到脚本所在的文件夹中。 例如，若要将脚本输出重定向到文本文件，请运行步骤 3 中的以下命令：然后，可以从文件复制文件夹 ID 或文档链接以用于搜索  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` 查询。

### <a name="script-output-for-mailbox-folders"></a>邮箱文件夹的脚本输出

如果您收到邮箱文件夹的 ID，脚本将连接到 Exchange Online PowerShell，运行 **Get-MailboxFolderStatisics** cmdlet，然后显示指定邮箱中的文件夹列表。 对于邮箱中每个文件夹，脚本都会显示 **FolderPath** 列中文件夹的名称和 **FolderQuery** 列中的文件夹 ID。 此外，该脚本将 **folderId** (，即邮箱属性的名称) 文件夹 ID。 由于 **folderid** 属性是一个可搜索属性，因此您将在步骤 2 中的搜索查询  `folderid:<folderid>` 中使用该搜索查询来搜索该文件夹。 该脚本最多显示 100 个邮箱文件夹。

> [!IMPORTANT]
> 本文中的脚本包含编码逻辑，该逻辑将 **Get-MailboxFolderStatistics** 返回的 64 个字符的文件夹 ID 值转换为索引为搜索的 48 个字符格式。 如果只需在 PowerShell 中运行 **Get-MailboxFolderStatistics** cmdlet 来获取文件夹 ID (而不是运行本文) 中的脚本，使用该文件夹 ID 值的搜索查询将失败。 您必须运行脚本才能获取可在内容搜索中使用的格式正确的文件夹 ID。

下面是邮箱文件夹的脚本返回的输出示例。

![脚本返回的邮箱文件夹和文件夹 ID 列表的示例。](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

步骤 2 中的示例显示用于搜索用户的"可恢复的项目"文件夹中的"清除"子文件夹的查询。

### <a name="script-output-for-site-folders"></a>网站文件夹的脚本输出

如果要从 SharePoint 或 OneDrive for Business 网站获取 **documentlink** 属性的路径，脚本将连接到安全 & 合规性 PowerShell，创建一个新的内容搜索，在网站中搜索文件夹，然后显示位于指定网站中的文件夹列表。 该脚本显示每个文件夹的名称，并将 **documentlink** 的前缀添加到文件夹 URL。 由于 **documentlink** 属性是一个可搜索属性，因此您将在步骤 2 中的搜索查询中使用 `documentlink:<path>` property：value 对来搜索该文件夹。 脚本最多显示 200 个网站文件夹。 如果网站文件夹超过 200 个，则显示最新文件夹。

下面是脚本返回的网站文件夹的输出示例。

![脚本返回的网站文件夹的文档链接名称列表的示例。](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>步骤 2：使用文件夹 ID 或文档链接执行目标集合

运行脚本以收集特定用户的文件夹 ID 或文档链接列表后，下一步是转到 Microsoft 365 合规中心 并创建新的内容搜索以搜索特定文件夹。 您将在"内容搜索"关键字框 (中配置的搜索查询中使用 `folderid:<folderid>` `documentlink:<path>` 或 property：value 对;如果使用 **New-ComplianceSearch** cmdlet) ，您将使用 or property：value 对作为 *ContentMatchQuery* 参数的值。 您可以将 或  `folderid`  `documentlink` 属性与其他搜索参数或搜索条件组合使用。 如果查询中仅包含 或 属性，  `folderid`  `documentlink` 搜索将返回指定文件夹中的所有项目。

1. 转到 ，然后使用在步骤 1 中用于运行脚本的帐户 <https://compliance.microsoft.com> 和凭据登录。

2. 在合规中心的左窗格中，单击"显示 **所有**  >  **内容搜索**"，然后单击"新建 **搜索"。**

3. 在 **"关键字"** 框中，粘贴由脚本在步骤 1 中返回的 `folderid:<folderid>` 或  `documentlink:<path>/*` 值。

    例如，以下屏幕截图中的查询将搜索用户的"可恢复的项目"文件夹 ("清除"子文件夹的"清除"子文件夹中的任何项目) 步骤 1 的屏幕截图中显示了"清除"子文件夹 `folderid` 的属性值：

    ![将 folderid 或 documentlink 粘贴到搜索查询的关键字框中。](../media/FolderIDSearchQuery.png)
    > [!IMPORTANT]
    > documentlink 搜索需要使用尾随  `asterisk '/*'` 。  

4. 在 **"位置"** 下，**选择"特定位置**"，然后单击"修改 **"。**

5. 根据是搜索邮箱文件夹还是网站文件夹，执行下列操作之一：

    - 在 **"Exchange"** 旁边，单击"选择用户、组或团队"，然后添加在步骤 1 中运行脚本时指定的相同邮箱。

      或

    - 在 **"SharePoint"** 旁边，单击"选择网站"，然后添加在步骤 1 中运行脚本时指定的同一网站 URL。

6. 保存要搜索的内容位置后，单击"保存&**运行**"，键入内容搜索的名称，然后单击"保存"启动目标集合搜索。 

### <a name="examples-of-search-queries-for-targeted-collections"></a>目标集合的搜索查询示例

下面是在搜索查询中使用  `folderid` 和 属性执行目标  `documentlink` 集合的一些示例。 占位符用于 和  `folderid:<folderid>`  `documentlink:<path>` 以节省空间。

- 本示例搜索三个不同的邮箱文件夹。 您可以使用类似的查询语法来搜索用户的"可恢复的项目"文件夹中的隐藏文件夹。

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- 本示例在邮箱文件夹中搜索包含精确短语的项目。

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- 本示例搜索网站文件夹 (以及) 标题中包含字母"NDA"的文档的任何子文件夹。

  ```powershell
  documentlink:"<path>/*" AND filename:nda
  ```

- 本示例在网站文件夹中搜索 (文件夹，) 文件夹中查找日期范围内已更改的文档。

  ```powershell
  documentlink:"<path>/*" AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>更多信息

使用本文中的脚本执行目标集合时，请记住以下事项。

- 脚本不会从结果中删除任何文件夹。 因此，结果中列出的某些文件夹可能无法搜索 (或返回零项目) 因为它们包含系统生成的内容，或者因为它们只包含子文件夹而不是邮箱项目。

- 此脚本仅返回用户的主邮箱的文件夹信息。 它不会返回有关用户存档邮箱中文件夹的信息。 若要返回有关用户存档邮箱中文件夹的信息，可以编辑脚本。 为此，请更改 行 `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` ， `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` 然后保存并运行编辑的脚本。 此更改将返回用户存档邮箱中文件夹和子文件夹的文件夹 ID。 若要搜索整个存档邮箱，可以在搜索查询中连接所有文件夹 ID property：value 对 `OR` 和运算符。

- 搜索邮箱文件夹时，仅 (属性) 标识的指定文件夹;不会搜索 `folderid` 子文件夹。 若要搜索子文件夹，您需要使用要搜索的子文件夹的文件夹 ID。

- 搜索网站文件夹时，文件夹 (`documentlink` 属性标识) 将搜索所有子文件夹。

- 导出仅指定搜索查询中的属性的搜索的结果时，可以选择第一个导出选项"由于其他原因，所有项目（不包括无法识别的格式的项目）都经过加密或未编制索引 `folderid` "。 将始终导出文件夹中的所有项目，无论其索引状态如何，因为文件夹 ID 始终为索引。
