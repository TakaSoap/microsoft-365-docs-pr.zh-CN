---
title: 使用 PowerShell 管理 SharePoint Online 用户和组
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
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
description: 本文将了解如何使用 PowerShell for Microsoft 365管理 SharePoint Online 用户、组和网站。
ms.openlocfilehash: e2166753b1be56c19011a1fc7e20d1584a5d3004
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681185"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>使用 PowerShell 管理 SharePoint Online 用户和组

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

如果你是使用大型用户帐户SharePoint组列表的联机管理员，并且希望使用更简单的方式来管理它们，可以使用 PowerShell 进行Microsoft 365。

在开始之前，本文中的过程需要您连接到 SharePoint Online。 有关说明，请参阅 [连接 SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="get-a-list-of-sites-groups-and-users"></a>获取网站、组和用户的列表

开始管理用户和组之前，你需要获取网站、组和用户的列表。然后可以使用此信息完成本文中的示例。

使用此命令获取租户中的网站列表：

```powershell
Get-SPOSite
```

使用此命令获取租户中的组列表：

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

使用此命令获取租户中的用户列表：

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>将用户添加到网站集管理员组

`Set-SPOUser`可以使用 cmdlet 将用户添加到网站集上的网站集管理员列表中。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

若要使用这些命令，请将引号内的所有内容（包括 < 和 > 字符）替换为正确的名称。

例如，这组命令将 Opal Castillo (用户名 opalc) 添加到 Contoso 租赁的 ContosoTest 网站集上的网站集管理员列表中：

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

您可以将这些命令复制并粘贴到 记事本 中，将 $tenant、$site 和 $user 的变量值更改为环境中的实际值，然后将其粘贴到 SharePoint Online 命令行管理程序窗口中以运行它们。

## <a name="add-a-user-to-other-site-collection-groups"></a>将用户添加到其他网站集组

在此任务中，我们将`Add-SPOUser`使用 cmdlet 将用户添加到网站SharePoint组。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

例如，让我们将一 (用户名称) 添加到 contoso 租赁中 ContosoTest 网站集的审核员组中：

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>创建网站集组

您可以使用 cmdlet `New-SPOSiteGroup` 创建新的组SharePoint组并将其添加到网站集。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

以后可以使用 cmdlet 更新组属性，如权限 `Set-SPOSiteGroup` 级别。

例如，让我们向 contoso 租赁中的 contosotest 网站集添加具有"仅查看"权限的审核员组：

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>从组中删除用户

有时必须从某个网站甚至是所有网站删除用户。 员工可能从一个部门转移到另一个部门，或离开公司。 可以在 UI 中为一名员工轻松完成此操作，但当您需要将整个部门从一个网站移动到另一个网站时，这一点并不轻松。

但是，通过使用 SharePoint命令行管理程序和 CSV 文件，这非常简单快捷。 在本任务中，将使用 Windows PowerShell 将用户从一个网站集安全组删除。 然后使用 CSV 文件从不同的网站删除大量用户。

我们将使用"Remove-SPOUser"cmdlet 从网站集组中删除单个 Microsoft 365 用户，以便我们能看到命令语法。 语法如下所示：

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

例如，让我们从 contoso 租赁的 contosotest 网站集中的网站集 Auditors 组中删除一个为"一名"的用户。

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

假设我们要从他当前的所有组中删除一个用户。 下面是我们执行该工作的原因：

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> 这只是一个示例。 除非确实需要将用户从每个组中删除（例如，用户离开公司），否则不应运行此命令。

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>自动化管理大型用户和组列表

若要向网站添加大量帐户SharePoint授予权限，可以使用 Microsoft 365 管理中心、单个 PowerShell 命令或 PowerShell 和 CSV 文件。 在这些选择中，CSV 文件是自动执行此任务的最快方法。

基本过程是，创建具有与 Windows PowerShell 脚本所需的参数对应的标头（列）的 CSV 文件。 你可以轻松地在列表中创建此类Excel，然后导出为 CSV 文件。 然后使用 Windows PowerShell 脚本循环访问 CSV 文件中的记录（行），将用户添加到组，将组添加到网站。

例如，让我们创建一个 CSV 文件来定义一组网站集、组和权限。 接下来，我们将创建 CSV 文件以使用用户填充组。 最后，我们将创建并运行一个Windows PowerShell组和填充组的脚本。

第一个 CSV 文件将一个或多个组添加到一个或多个网站集，并具有以下结构：

标头：

```powershell
Site,Group,PermissionLevels
```

项目：

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

下面是一个示例文件：

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

第二个 CSV 文件将一个或多个用户添加到一个或多个组，并具有以下结构：

标头：

```powershell
Group,LoginName,Site
```

项目：

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

下面是一个示例文件：

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

然后必须将这两个 CSV 文件保存到驱动器。 下面是使用 CSV 文件以及添加权限和组成员身份的示例命令：

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

脚本导入 CSV 文件内容并使用列中的值填充 **New-SPOSiteGroup** 和 **Add-SPOUser** 命令的参数。 在我们的示例中，我们将此文件保存到驱动器 C 上的 O365Admin 文件夹，但您可以将其保存到任何需要的位置。

现在，让我们使用同一 CSV 文件删除不同网站中多个组的一组人员。 下面是一个示例命令：

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>生成用户报告

您可能希望获取一些网站的报表，并显示这些网站的用户、其权限级别和其他属性。 语法如下所示：

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

将可以获取这三个网站的数据，并将这些数据写入本地驱动器上的文本文件。 参数 –Append 将新内容添加到现有文件。

例如，我们在 Contoso1 租户的 ContosoTest、TeamSite01 和 Project01 网站上运行报告：

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

我们只需更改 **$site 变量。** the **$tenant** variable keeps its value through all three runs of the command.

但是，如果要对每个网站进行此操作，应该怎么做？通过使用以下命令，您无需键入所有这些网站就可以进行操作：

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

此报告相当简单，你可以添加更多代码以创建更多特定报告或包括更多详细信息的报告。 但是，这应该让你了解如何使用 SharePoint Online 命令行管理程序在 SharePoint Online 环境中管理用户。

## <a name="see-also"></a>另请参阅

[连接到 SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[使用 PowerShell 管理 SharePoint Online](create-sharepoint-sites-and-add-users-with-powershell.md)

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)

[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
