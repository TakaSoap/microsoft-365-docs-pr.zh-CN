---
title: 使用 PowerShell 查看许可和未经许可的Microsoft 365用户
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/21/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: 本文介绍如何使用 PowerShell 查看许可和未经许可的Microsoft 365用户帐户。
ms.openlocfilehash: 1be54b20d3b50985fea8eb665a1b6098a26aa703
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823622"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>使用 PowerShell 查看许可和未经许可的Microsoft 365用户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

你的Microsoft 365组织中的用户帐户可能具有一些、全部或没有从组织中提供的许可计划分配给他们的可用许可证。 可以使用 PowerShell 进行Microsoft 365，快速查找组织中的许可用户和未经许可的用户。

## <a name="use-the-microsoft-graph-powershell-sdk"></a>使用 Microsoft Graph PowerShell SDK

首先，[连接到Microsoft 365租户](/graph/powershell/get-started#authentication)。

读取用户属性（包括许可证详细信息）需要 User.Read.All 权限范围或[“获取用户”图形 API参考页](/graph/api/user-get)中列出的其他权限之一。

需要组织.Read.All 权限范围才能读取租户中可用的许可证。

```powershell
Connect-Graph -Scopes User.Read.All, Organization.Read.All
```

若要查看特定用户帐户的许可证详细信息，请运行以下命令：
  
```powershell
Get-MgUserLicenseDetail -UserId "<user sign-in name (UPN)>"
```

例如：

```powershell
Get-MgUserLicenseDetail -UserId "belindan@litwareinc.com"
```

若要查看组织中未分配任何许可计划的所有用户帐户的列表， (未经许可的用户) ，请运行以下命令：
  
```powershell
Get-MgUser -Filter 'assignedLicenses/$count eq 0' -ConsistencyLevel eventual -CountVariable unlicensedUserCount -All

Write-Host "Found $unlicensedUserCount unlicensed users."
```

若要查看所有成员用户帐户的列表 (不包括组织中未分配任何许可计划)  (未授权用户) 的来宾，请运行以下命令：
  
```powershell
Get-MgUser -Filter "assignedLicenses/`$count eq 0 and userType eq 'Member'" -ConsistencyLevel eventual -CountVariable unlicensedUserCount -All

Write-Host "Found $unlicensedUserCount unlicensed users (excluding guests)."
```

若要查看组织中已分配任何许可计划的所有用户帐户的列表， (许可用户) ，请运行以下命令：
  
```powershell
Get-MgUser -Filter 'assignedLicenses/$count ne 0' -ConsistencyLevel eventual -CountVariable licensedUserCount -All -Select UserPrincipalName,DisplayName,AssignedLicenses | Format-Table -Property UserPrincipalName,DisplayName,AssignedLicenses

Write-Host "Found $licensedUserCount licensed users."
```

若要查看组织中分配了 E5 许可证的所有用户帐户的列表，请运行以下命令：

```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'

Get-MgUser -Filter "assignedLicenses/any(x:x/skuId eq $($e5sku.SkuId) )" -ConsistencyLevel eventual -CountVariable e5licensedUserCount -All

Write-Host "Found $e5licensedUserCount E5 licensed users."
```

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 
若要查看组织中未分配任何许可计划的所有用户帐户的列表， (未经许可的用户) ，请运行以下命令：
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

若要查看组织中已分配任何许可计划的所有用户帐户的列表， (许可用户) ，请运行以下命令：
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>若要列出订阅中的所有用户，请使用该 `Get-AzureAdUser -All $true` 命令。
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

若要查看组织中所有用户帐户及其许可状态的列表，请在 PowerShell 中运行以下命令：
  
```powershell
Get-MsolUser -All
```

>[!Note]
>PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。 若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。
>

若要查看组织中所有未授权用户帐户的列表，请运行以下命令：
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

若要查看组织中所有授权用户帐户的列表，请运行以下命令：
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
