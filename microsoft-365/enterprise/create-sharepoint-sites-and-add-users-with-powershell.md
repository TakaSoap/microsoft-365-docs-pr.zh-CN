---
title: 使用 PowerShell 创建 SharePoint Online 网站并添加用户
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: landing-page
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: 摘要：使用 PowerShell 创建新的 SharePoint Online 网站，然后将用户和组添加到这些网站。
ms.openlocfilehash: 95bd3fb5647a5c6680fd9a07ebdf45e106acb095
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681361"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>使用 PowerShell 创建 SharePoint Online 网站并添加用户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

使用 PowerShell for Microsoft 365创建 SharePoint Online 网站和添加用户时，快速重复执行任务的速度比在 Microsoft 365 管理中心 中快得多。 还可以执行在任务管理中无法Microsoft 365 管理中心。

## <a name="connect-to-sharepoint-online"></a>连接到 SharePoint Online

本主题中的过程需要您连接到 SharePoint Online。 有关说明，请参阅 [连接 SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="step-1-create-new-site-collections-using-powershell"></a>步骤 1：使用 PowerShell 创建新的网站集

使用 PowerShell 创建多个网站，以及.csv示例代码创建的网站文件，记事本。 在此步骤中，你将使用你自己的网站和租户特定信息替换括号中显示的占位符信息。 此过程允许你创建单个文件并运行使用该文件的单个 PowerShell 命令。 这使得所采取的操作具有可重复性和可移植性，并可以减少许多（如果不是全部）因向 SharePoint Online 命令行管理程序键入长命令而导致的错误。 此步骤包括两个部分。 首先，创建一个.csv文件，然后使用 PowerShell 引用该.csv文件，它将使用其内容创建网站。

PowerShell cmdlet 导入 .csv 文件，然后通过管道将该文件通过管道传输至大括号内的循环，该循环将读取文件的第一行作为列标题。 然后，PowerShell cmdlet 将访问其余记录，为每个记录创建新的网站集，并按列标题分配网站集的属性。

### <a name="create-a-csv-file"></a>创建 .csv 文件

> [!NOTE]
> 资源配额参数仅适用于经典网站。 如果在新式网站上使用此参数，您可能会收到一条警告消息，指出已弃用此参数。

1. 打开记事本，然后向其中粘贴以下文本块：

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   其中 *，tenant* 是租户的名称， *owner* 是租户上要授予其主要网站集管理员角色的用户的用户名。

    (使用 Ctrl+H 进行快速批量记事本请按 Ctrl+H。) 

2. 将桌面上的文件另存为 **SiteCollections.csv**。

> [!TIP]
> 在使用此脚本文件.csv或Windows PowerShell脚本文件之前，一定要确保没有多余的或非打印字符。 在 Word 中打开该文件，在功能区单击“段落”图标以显示非打印字符。 应该没有多余的非打印字符。 例如，除了文件末尾的最后一个段落标记之外，应该没有其他任何段落标记。

### <a name="run-the-windows-powershell-command"></a>运行 Windows PowerShell 命令

1. 在命令Windows PowerShell，键入或复制并粘贴以下命令，然后按 Enter：

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   其中 *MyAlias* 等于您的用户别名。

2. 等待 Windows PowerShell 提示符重新出现。可能需要一两分钟。

3. 在 Windows PowerShell 提示符处键入或复制并粘贴以下 cmdlet，然后按 Enter 键：

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. 请注意列表中的新网站集。 使用示例 CSV 文件，你将看到以下网站集： **TeamSite01**、 **Blog01**、 **Project01** 和 **Community01**

就是这样。 已使用您创建的 .csv 和一个 Windows PowerShell 命令创建多个网站集。 现在，可以创建用户并将其分配给这些网站。

## <a name="step-2-add-users-and-groups"></a>步骤 2：添加用户和组

现在，您将创建用户并将其添加到网站集组中。然后，您将使用 .csv 文件批量上载新的组和用户。

以下过程继续使用示例网站 TeamSite01、Blog01、Project01 和 Community01。

### <a name="create-csv-and-ps1-files"></a>创建 .csv 和 .ps1 文件

1. 打开记事本，然后向其中粘贴以下文本块：

   ```powershell
   Site,Group,PermissionLevels
   https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
   https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
   https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
   https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
   https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
   https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
   https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
   https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
   ```

   其中 *tenant* 等于你的租户名称。

2. 将文件另存 **为桌面GroupsAndPermissions.csv**。

3. 打开记事本的新实例，然后向其中粘贴以下文本块：

   ```powershell
   Group,LoginName,Site
   Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
   XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
   XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
   Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
   Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
   Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
   ```

   其中 *，tenant* 等于租户名称， *username* 等于现有用户的用户名。

4. 将文件另存 **为桌面Users.csv**。

5. 打开记事本的新实例，然后向其中粘贴以下文本块：

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   其中 MyAlias 等于当前登录的用户的用户名。

6. 将文件另存 **为桌面UsersAndGroups.ps1**。 这是一个简单的 Windows PowerShell 脚本。

现在，您可以运行 UsersAndGroup.ps1 脚本以向多个网站集中添加用户和组。

### <a name="run-usersandgroupsps1-script"></a>运行 UsersAndGroups.ps1 脚本

1. 返回到 SharePoint Online 命令行管理程序。

2. 在 Windows PowerShell 提示符下键入或复制并粘贴以下行，然后按 Enter 键：

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. 在确认提示符下，按 **Y**。

4. 在 Windows PowerShell 提示符下键入或复制并粘贴以下内容，然后按 Enter 键：

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   其中 *MyAlias* 等于您的用户名。

5. 在继续之前，请等待提示符返回。首先，您将看到这些组在创建时的样子。然后，您将看到添加用户后的重复组列表。

## <a name="see-also"></a>另请参阅

[连接到 SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[使用 PowerShell 管理 SharePoint Online 网站用户组](manage-sharepoint-site-groups-with-powershell.md)

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)

[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
