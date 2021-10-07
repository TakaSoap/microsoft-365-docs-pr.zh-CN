---
title: 使用 PowerShell Microsoft 365用户帐户分配角色
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
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: 本文将了解如何快速轻松地使用 PowerShell for Microsoft 365向用户帐户分配管理员角色。
ms.openlocfilehash: 0b0fc0a5da1a6b84d4f13f95ace4846e367ae111
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193131"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>使用 PowerShell 将Microsoft 365角色分配给用户帐户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

通过使用 PowerShell for Microsoft 365，可以轻松地将角色分配给用户帐户。

>[!Note]
>了解如何将[管理员角色分配给](../admin/add-users/assign-admin-roles.md)用户帐户以及Microsoft 365 管理中心。
>
>有关其他资源的列表，请参阅管理 [用户和组](/admin)。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，使用 **Azure AD DC 管理员**、**云应用程序** 管理员或 **全局** 管理员帐户连接到你的 Microsoft 365 [租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
 
有关详细信息，请参阅 [关于管理员角色](/microsoft-365/admin/add-users/about-admin-roles?)。

接下来，确定要添加到角色角色中的用户帐户的登录名 (示例：fredsm \@ contoso.com) 。 这也称为 UPN (用户主体) 。

接下来，确定角色的名称。 请参阅 [Azure AD 内置角色](/azure/active-directory/roles/permissions-reference)。

>[!Note]
>请注意本文中的说明。 对于 Azure AD Azure Active Directory (PowerShell，) 不同。 例如，SharePoint *中的* Microsoft 365 管理中心 管理员角色SharePoint Azure AD PowerShell 中的服务管理员。 
>

接下来，填写登录名和角色名称并运行以下命令：
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

下面是一个完成的命令集示例，该命令集将 SharePoint 服务管理员角色分配给 *belindan \@* contoso.com 帐户：
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

若要显示特定管理员角色的用户名列表，请使用以下命令。

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，使用全局管理员帐户[连接到你的Microsoft 365租户。](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
### <a name="for-a-single-role-change"></a>对于单个角色更改

指定用户帐户的最常见方法就是使用其 显示名称 或电子邮件名称（也称为登录名或用户主体名称 (UPN) ）。

#### <a name="display-names-of-user-accounts"></a>显示用户帐户的名称

如果您习惯使用用户帐户的显示名称，请确定以下信息：
  
- 要配置的用户帐户
    
    若要指定用户帐户，您必须确定其显示名称。 若要获取帐户的完整列表，请使用此命令：
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    此命令列出用户帐户的显示名称，按显示名称排序，一次显示一个屏幕。 可以使用 Where cmdlet 将列表筛选为较小的集合。 请参阅以下示例。

   >[!Note]
   >PowerShell Core 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。 从 Windows PowerShell 运行这些 cmdlet。
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    此命令仅列出显示名称以"John"开头的用户帐户。
    
- 要分配的角色
    
    若要显示可分配给用户帐户的可用管理员角色列表，请使用以下命令：
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

确定帐户的显示名称和角色名称后，请使用以下命令将角色分配给该帐户：
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

将命令粘贴到记事本。 对于 *$dispName* 和 *$roleName，* 请将说明文本替换为其值。 删除 \< and > 字符，但保留引号。 将修改的行粘贴到 Microsoft Azure Active Directory 模块中Windows PowerShell以运行这些行。 或者，您可以使用 ISE Windows PowerShell集成脚本 (脚本) 。
  
下面是已完成的命令集的示例：
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>用户帐户的登录名

如果您习惯使用用户帐户的登录名或 UPN，请确定以下信息：
  
- 用户帐户的 UPN
    
    如果您不知道 UPN，请使用以下命令：
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    此命令将列出用户帐户的 UPN，按 UPN 排序，一次列出一个屏幕。 可以使用 Where **cmdlet** 筛选列表。 下面是一个示例：
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    此命令仅列出显示名称以"John"开头的用户帐户。
    
- 要分配的角色
    
    若要显示可分配给用户帐户的可用角色列表，请使用以下命令：
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

拥有帐户的 UPN 和角色名称后，请使用以下命令将角色分配给帐户：
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

复制命令并将其粘贴到记事本。 对于 **$upnName** 和 **$roleName** 变量。 将说明文本替换为其值。 删除 \< and > 字符，但保留引号。 将修改的行粘贴到Microsoft Azure Active Directory模块中Windows PowerShell以运行这些行。 或者，可以使用 ISE Windows PowerShell ISE。
  
下面是已完成的命令集的示例：
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>多个角色更改

对于多个角色更改，请确定以下信息：
  
- 要配置哪些用户帐户。 可以使用上一节中的方法收集一组显示名称或 UPN。
    
- 要分配给每个用户帐户的角色。 若要显示可分配给用户帐户的可用角色列表，请使用以下命令：
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

接下来，使用 CSV (或) 或 UPN 和角色名称显示名称创建一个逗号分隔值。 在管理中，你可以轻松Microsoft Excel。

下面是显示名称的示例：
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

接下来，填写 CSV 文件的位置，在 PowerShell 命令提示符处运行生成的命令。
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

下面是 UPN 的示例：
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

接下来，填写 CSV 文件的位置，在 PowerShell 命令提示符处运行生成的命令。
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>另请参阅

- [使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
- [PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
