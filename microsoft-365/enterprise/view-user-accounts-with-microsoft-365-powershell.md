---
title: 使用 powerShell Microsoft 365用户帐户
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: 了解如何使用 PowerShell 以不同方式查看、Microsoft 365或显示用户帐户。
ms.openlocfilehash: da1ae30f04ba2c5ee69047361113fe468938c4ad
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60212757"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>使用 powerShell Microsoft 365用户帐户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

可以使用帐户Microsoft 365 管理中心查看你的租户Microsoft 365帐户。 PowerShell for Microsoft 365可实现此功能，但也提供了其他功能。
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
### <a name="view-all-accounts"></a>查看所有帐户

若要显示用户帐户的完整列表，请运行以下命令：
  
```powershell
Get-AzureADUser
```

应获取与以下类似的信息：
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a>查看特定帐户

若要显示特定用户帐户，请运行以下命令。 填写用户帐户的登录帐户名称，也称为 UPN (用户) 。 删除"<"和">"字符。
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

下面是一个示例：
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>查看特定帐户的其他属性值

默认情况下 **，Get-AzureADUser** cmdlet 仅显示帐户的 *ObjectID、DisplayName* 和 *UserPrincipalName* 属性。 

若要对要显示的属性更具选择性，请结合使用 **Select** cmdlet 和 **Get-AzureADUser** cmdlet。 若要组合这两个 cmdlet，请使用"pipe"字符 ("|") ，指示 Azure Active Directory PowerShell Graph接受一个命令的结果并将其发送到下一个命令。 下面是显示每个用户帐户的 *DisplayName、Department* 和 *UsageLocation* 的示例命令：
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

此命令指示 PowerShell：
  
1. 获取 **Get-AzureADUser** (用户帐户的所有信息) 并将其发送到下一个 **|** () 。
    
1.  仅显示用户帐户名称、部门以及使用情况位置 (**选择 DisplayName、Department、UsageLocation**) 。
  
To see all the properties for a specific user account， use the **Select** cmdlet and the wildcard character (*) . 下面是一个示例：
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

再如，运行以下命令以检查特定用户帐户的启用状态：
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>查看帐户同步状态

用户帐户有两个来源： 

- Windows Server Active Directory (AD) ，即从本地 AD 同步到云的帐户。

- Azure Active Directory (Azure AD) AD 帐户，这些帐户直接在云中创建。


以下命令指示 PowerShell 获取属性 *DirSyncEnabled* 设置为 True 的 *所有用户*。 可以使用它查找正在从本地 AD 同步的帐户。

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

以下命令指示 PowerShell 获取属性 *DirSyncEnabled* 设置为 False 的 *所有用户*。 可以使用它查找仅云帐户。

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>查看基于通用属性的帐户

若要对要显示的帐户列表更具选择性，可以将 **Where** cmdlet 与 **Get-AzureADUser** cmdlet 结合使用。 若要组合这两个 cmdlet，请使用"pipe"字符 ("|") ，指示 Azure Active Directory PowerShell Graph接受一个命令的结果并将其发送到下一个命令。 下面是一个示例命令，该命令仅显示未指定使用位置的用户帐户：
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

此命令指示Azure Active Directory PowerShell Graph：
  
1. 获取 **Get-AzureADUser** (用户帐户的所有信息) 并将其发送到下一个 **|** () 。
    
1. 在 Where {$ 中查找未指定使用位置 (**用户帐户 \_ 。UsageLocation -eq $Null}**) 。 在括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性所针对的帐户 **$ \_ (。UsageLocation**) 未指定 -eq (**-eq** $Null) 。
    
**UsageLocation** 属性只是与用户帐户关联的众多属性之一。 若要显示特定用户帐户的所有属性，请使用 **Select** cmdlet 和通配符 (*) 。 下面是一个示例：
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

例如 **，City** 是用户帐户属性的名称。 可以使用以下命令列出居住在伦敦的用户的所有帐户：
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
> 这些示例中 **Where** cmdlet 的语法为 **Where {$ \_ 。** [用户帐户属性名称][比较运算符][value] **}**.> [comparison operator] is **-eq** for equals， **-ne** for not equals， **-lt** for less than， **-gt** for greater than， and others.  [value] 通常是一个字符串， (字母、数字和其他字符序列、) 、数字值 **$Null未指定。** 有关详细信息，请参阅 [Where](/powershell/module/microsoft.powershell.core/where-object)。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="view-all-accounts"></a>查看所有帐户

若要显示用户帐户的完整列表，请运行以下命令：
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。 从 Windows PowerShell 运行这些 cmdlet。
>

应获取与以下类似的信息：
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

**Get-MsolUser** cmdlet 也有一组参数可用于筛选显示的用户帐户组。 例如，对于未授权用户列表 (已添加到 Microsoft 365但尚未获得使用任何服务许可证的用户) ，请运行以下命令：
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

应获取与以下类似的信息：
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

有关用于筛选显示的用户帐户集的其他参数的信息，请参阅 [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100))。
  
### <a name="view-a-specific-account"></a>查看特定帐户

若要显示特定用户帐户，请运行以下命令。 填写用户帐户的登录名，也称为 UPN (用户) 。 删除"<"和">"字符。
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>查看基于通用属性的帐户

若要对要显示的帐户列表更具选择性，可以将 **Where** cmdlet 与 **Get-MsolUser** cmdlet 结合使用。 若要组合这两个 cmdlet，请使用"pipe"字符 ("|") ，指示 PowerShell 接受一个命令的结果并将其发送到下一个命令。 下面的示例仅显示未指定使用位置的用户帐户：
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

此命令指示 PowerShell：
  
1. 获取 **Get-MsolUser** (用户帐户) 并将其发送到下一个 **|** () 。
    
1. 在 Where {$ 中查找所有未指定使用 (**用户帐户 \_ 。UsageLocation -eq $Null}**) 。 在括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性所针对的帐户 **$ \_ (。UsageLocation**) 未指定 -eq (**-eq** $Null) 。
    
应获取与以下类似的信息：
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

*UsageLocation* 属性只是与用户帐户关联的众多属性之一。 若要查看用户帐户的所有属性，请使用 **Select** cmdlet 和通配符 (*) 显示特定用户帐户的所有属性。 下面是一个示例：
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

例如 *，City* 是用户帐户属性的名称。 可以使用以下命令列出居住在伦敦的用户的所有用户帐户：
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
> 这些示例中 **Where** cmdlet 的语法为 **Where {$ \_ 。** [用户帐户属性名称][比较运算符][value] **}**.  [comparison operator] is **-eq** for equals， **-ne** for not equals， **-lt** for less than， **-gt** for greater than， and others.  [value] 通常是一个字符串， (字母、数字和其他字符序列、) 、数字值 **$Null未指定。** 有关详细信息，请参阅 [Where](/powershell/module/microsoft.powershell.core/where-object)。
  
若要检查用户帐户的阻止状态，请使用以下命令：
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>查看帐户的其他属性值

默认情况下 **，Get-MsolUser** cmdlet 显示用户帐户的以下三个属性：
  
- UserPrincipalName

- DisplayName

- isLicensed

如果您需要其他属性（如用户工作部门以及他们使用 Microsoft 365 服务的国家/地区），您可以结合 **Select** cmdlet 运行 **Get-MsolUser** 以指定用户帐户属性列表。 下面是一个示例：
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

此命令指示 PowerShell：
  
1. 获取 **Get-MsolUser** (用户帐户的所有) 并将其发送到下一个 **|** () 。
    
1. 仅显示用户帐户名称、部门以及使用情况位置 (**选择 DisplayName、Department、UsageLocation**) 。
    
应获取与以下类似的信息：
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

Select  cmdlet 允许您选择要显示的属性。 若要显示特定用户帐户的所有属性，请使用通配符 (*) 。 下面是一个示例：
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

若要对要显示的帐户列表进行更多选择，您还可以使用 **Where** cmdlet。 下面是一个示例命令，该命令仅显示未指定使用位置的用户帐户：
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

此命令指示 PowerShell：
  
1. 获取 **Get-MsolUser** (用户帐户) 并将其发送到下一个 **|** () 。
    
1. 查找具有未指定使用位置的所有用户帐户 (**Where {$ \_ 。UsageLocation -eq $Null}**) ，并将结果信息发送到下一个命令 **|** () 。 在括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性所针对的帐户 **$ \_ (。UsageLocation**) 未指定 -eq (**-eq** $Null) 。
    
1. 仅显示用户帐户名称、部门以及使用情况位置 (**选择 DisplayName、Department、UsageLocation**) 。
    
应获取与以下类似的信息：
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

如果使用目录同步创建和管理 Microsoft 365 用户，可以显示已计划Microsoft 365的本地帐户。 以下示例假定：

- Azure AD 连接配置为使用 ObjectGUID 的默认源定位标记。  (有关配置源定位标记的信息，请参阅[Azure AD 连接：设计概](/azure/active-directory/hybrid/plan-connect-design-concepts)念) 。
- 已安装用于 PowerShell 的 Active Directory 域服务模块 ([RSAT 工具](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)) 。

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)