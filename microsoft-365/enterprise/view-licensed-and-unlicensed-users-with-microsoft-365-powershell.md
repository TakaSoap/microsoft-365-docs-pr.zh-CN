---
title: 使用 PowerShell 查看许可Microsoft 365未授权的用户
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
description: 本文介绍如何使用 PowerShell 查看用户帐户的许可和Microsoft 365授权。
ms.openlocfilehash: 015cb63fd692131d77799fe30fc94c6214bb01d3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208201"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>使用 PowerShell 查看许可Microsoft 365未授权的用户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

你的组织Microsoft 365中的用户帐户可能从组织中可用的许可计划中分配了部分、全部或没有任何可用许可证。 可以使用 PowerShell for Microsoft 365快速查找组织中许可和未授权的用户。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 
若要查看组织中尚未分配任何许可计划的所有用户帐户列表 (未授权) ，请运行以下命令：
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

若要查看组织中已分配给许可用户的任何许可计划的所有用户帐户列表 (许可) ，请运行以下命令：
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>若要列出订阅中的所有用户，请使用 `Get-AzureAdUser -All $true` 命令。
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

若要查看组织中所有用户帐户的列表及其许可状态，请运行 PowerShell 中的以下命令：
  
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
