---
title: 使用 PowerShell 管理 SharePoint Online 网站用户组
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/17/2019
audience: Admin
ms.topic: hub-page
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
description: 本文介绍使用 PowerShell for Microsoft 365管理 SharePoint Online 网站组的过程。
ms.openlocfilehash: deef41118789a9df4353fa188c88d827909dc863
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328773"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>使用 PowerShell 管理 SharePoint Online 网站用户组

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

尽管您可以使用 Microsoft 365 管理中心，但您也可以使用 PowerShell for Microsoft 365管理 SharePoint Online 网站组。

## <a name="before-you-begin"></a>准备工作

本文中的过程需要您连接到 SharePoint Online。 有关说明，请参阅[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>使用 powerShell SharePoint Online Microsoft 365

SharePoint Online 管理中心提供一些易于使用的方法来管理网站组。 例如，假设您要查看网站的组和 `https://litwareinc.sharepoint.com/sites/finance` 组成员。 下面是您必须执行以下工作：

1. 从SharePoint管理中心，选择 <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**"活动站点**</a>"，然后选择网站的 URL。
2. 在网站页面上，<a href="https://go.microsoft.com/fwlink/?linkid=2185072" target="_blank">**设置**</a> (位于页面右上角的"网站) ，然后选择"网站 **权限"**。

然后对您要查看的下一个网站重复此过程。

若要使用 PowerShell for Microsoft 365获取组列表，可以使用以下命令：

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

在命令行管理程序联机命令行管理程序命令提示符SharePoint运行此命令集的方法有两种：

- 将命令复制到 记事本 (或其他文本编辑器) ，修改 **$siteURL** 变量的值，选择命令，然后将其粘贴到 SharePoint Online 命令行管理程序命令提示符中。 执行时，PowerShell 将在提示符下停止 **>>** 。 按 Enter 执行 `foreach` 命令。<br/>
- 将命令复制到记事本（或其他文本编辑器），修改 **$siteURL** 变量值，然后在合适的文件夹中使用一个名称和.ps1 扩展名保存该文本文件。 接下来，通过指定脚本的路径和文件名SharePoint命令行管理程序命令提示符运行脚本。 下面是一个示例命令：

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

在这两种情况下，应该会看到类似下面的内容：

![SharePoint Online 网站组。](../media/SPO-site-groups.png)

这些是为网站创建的所有 `https://litwareinc.sharepoint.com/sites/finance`组，以及分配给这些组的所有用户。 组名为黄色，以帮助你从其成员中辨别组名。

另一个示例是，下面是一个命令集，用于列出所有 SharePoint Online 网站的组和组成员身份。

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```

## <a name="see-also"></a>另请参阅

[连接到 SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[使用 PowerShell 创建 SharePoint Online 网站并添加用户](create-sharepoint-sites-and-add-users-with-powershell.md)

[使用 PowerShell 管理 SharePoint Online 用户和组](manage-sharepoint-users-and-groups-with-powershell.md)

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)

[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
