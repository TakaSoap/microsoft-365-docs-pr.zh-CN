---
title: 使用 PowerShell Microsoft 365用户帐户
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/23/2020
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: 了解如何在 PowerShell 中使用不同的模块来删除Microsoft 365用户帐户。
ms.openlocfilehash: dc1e5c53f2d356f0585da5a0a5285b9af28dc8f0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171911"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>使用 PowerShell Microsoft 365用户帐户

可以使用 PowerShell for Microsoft 365删除和还原用户帐户。

>[!Note]
>了解如何使用[Microsoft 365 管理中心。](../admin/add-users/restore-user.md)
>
>有关其他资源的列表，请参阅管理 [用户和组](/admin)。
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

连接后，使用以下语法删除单个用户帐户：
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

本示例删除用户帐户 *fabricec litwareinc.com。 \@*
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> **Remove-AzureADUser** cmdlet 中的 *-ObjectID* 参数接受帐户的登录名（也称为用户主体名称）或帐户的对象 ID。
  
若要显示基于用户名的帐户名称，请使用下列命令：
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

本示例显示用户 *Caleb Sills 的帐户名称*。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

若要删除基于用户显示名称的帐户，请使用下列命令：
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

当您通过 Microsoft Azure Active Directory 模块删除用户帐户Windows PowerShell，该帐户不会永久删除。 您可以在 30 天内还原已删除的用户帐户。

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

若要删除一个用户帐户，请使用下面的语法：
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。 从 Windows PowerShell 运行这些 cmdlet。
>

此示例删除用户帐户 *BelindaN@litwareinc.com。*
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

若要在 30 天的宽限期内还原已删除的用户帐户，请使用下面的语法：
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

本示例将恢复已删除的帐户 *BelindaN \@ litwareinc.com*。
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> 若要查看可以还原的已删除用户的列表，请运行以下命令：
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> 如果用户帐户的初始用户主体名称已被另一个帐户使用，那么在还原用户帐户时，请使用 _NewUserPrincipalName_ 参数而不是 _UserPrincipalName_ 来指定一个不同的用户主体名称。


## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)