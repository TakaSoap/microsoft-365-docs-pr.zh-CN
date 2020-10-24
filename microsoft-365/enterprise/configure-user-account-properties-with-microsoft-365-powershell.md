---
title: 使用 PowerShell 配置 Microsoft 365 用户帐户属性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: 使用 PowerShell for Microsoft 365 在 Microsoft 365 租户中配置单个或多个用户帐户的属性。
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754324"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>使用 PowerShell 配置 Microsoft 365 用户帐户属性

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

可以使用 Microsoft 365 管理中心配置 Microsoft 365 租户的用户帐户的属性。 在 PowerShell 中，您还可以执行此操作，以及在管理中心中无法执行的一些其他操作。
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

若要在 Azure Active Directory PowerShell for Graph 模块中配置用户帐户的属性，请使用 [**AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet 并指定要设置或更改的属性。

首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
   
### <a name="change-properties-for-a-specific-user-account"></a>更改特定用户帐户的属性

使用 *-ObjectID* 参数标识帐户，并使用其他参数设置或更改特定属性。 下面列出了最常见的参数：
  
- -部门 " \<department name> "
    
- -DisplayName " \<full user name> "
    
- -FacsimilieTelephoneNumber " \<fax number> "
    
- -GivenName " \<user first name> "
    
- -姓 " \<user last name> "
    
- -移动 " \<mobile phone number> "
    
- -JobTitle " \<job title> "
    
- -PreferredLanguage " \<language> "
    
- -StreetAddress " \<street address> "
    
- -市/县 " \<city name> "
    
- -状态 " \<state name> "
    
- - \<postal code> 邮政编码 "
    
- -国家/地区 " \<country name> "
    
- -TelephoneNumber " \<office phone number> "
    
- -UsageLocation " \<2-character country or region code> "
    
    这是 ISO 3166-1 alpha-2 (A2) 双字母国家或地区代码。
    
有关其他参数，请参阅 [AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) 。

>[!Note]
>在将许可证分配给用户帐户之前，必须分配使用位置。
>

若要显示用户帐户的用户主体名称，请运行以下命令。
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

此命令指示 PowerShell：
  
1. 获取用户帐户 (**AzureADUser**) 的所有信息，并将其发送到下一个命令 (**|**) 。
    
1. 按字母顺序对用户主体名称列表进行排序 (**对 UserPrincipalName 进行排序**) 并将其发送到下一个命令 (**|**) 。
    
1. 仅显示每个帐户的 "用户主体名称" 属性 (**选择 "UserPrincipalName**) "。

1. 每次显示一屏 (**更**) 。
    
若要根据其显示名称显示帐户的用户主体名称 (名和姓) ，请运行以下命令。 填写 *$userName* 变量，并删除 \< and > 以下字符：
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

本示例显示具有显示名称 *Caleb Sills*的用户帐户的用户主体名称。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

通过使用 *$upn* 变量，可以根据各个帐户的显示名称对其进行更改。 下面的示例将 *Belinda Newman*的使用位置设置为法国。 但它指定了她的显示名称而不是她的用户主体名称：
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>更改所有用户帐户的属性

若要更改所有用户的属性，您可以使用 **AzureADUser** 和 **AzureADUser** cmdlet 的组合。 下面的示例将所有用户的使用位置更改为 *法国*：
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

此命令指示 PowerShell：
  
1. 获取用户帐户上的所有信息 (**AzureADUser**) 并将其发送到下一个命令 (**|**) 。
    
1. 将用户位置设置为 "法国 (**AzureADUser-UsageLocation" "FR"**) 。
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>更改特定用户帐户集的属性

若要更改特定用户帐户集的属性，您可以使用 **AzureADUser**、 **Where**和 **AzureADUser** cmdlet 的组合。 下面的示例将记帐部门中所有用户的使用位置更改为 " *法国*"：
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

此命令指示 PowerShell：
  
1. 获取用户帐户 (**AzureADUser**) 的所有信息，并将其发送到下一个命令 (**|**) 。
    
1.  查找其 " *部门* " 属性设置为 "记帐" (**其中 {$ _）的所有用户帐户。部门-eq "记帐"}**) ，并将生成的信息发送到下一个命令 (**|**) 。
    
1. 将用户位置设置为 "法国 (**AzureADUser-UsageLocation" "FR"**) 。
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

若要使用适用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块配置用户帐户的属性，请使用 **get-msoluser** cmdlet 并指定要设置或更改的属性。

首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
  
>[!Note]
>PowerShell Core 不支持 Windows PowerShell 模块的 Microsoft Azure Active Directory 模块以及在其名称中带有 *Msol* 的 cmdlet。 从 Windows PowerShell 运行这些 cmdlet。
>

### <a name="change-properties-for-a-specific-user-account"></a>更改特定用户帐户的属性

若要配置特定用户帐户的属性，请使用 [**get-msoluser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet 并指定要设置或更改的属性。 

使用 *-UserPrincipalName* 参数标识帐户，并使用其他参数设置或更改特定属性。 下面列出了最常见的参数。
  
- -市/县 " \<city name> "
    
- -国家/地区 " \<country name> "
    
- -部门 " \<department name> "
    
- -DisplayName " \<full user name> "
    
- -传真 " \<fax number> "
    
- -FirstName " \<user first name> "
    
- -LastName " \<user last name> "
    
- -MobilePhone " \<mobile phone number> "
    
- -Office " \<office location> "
    
- -PhoneNumber " \<office phone number> "
    
- - \<postal code> 邮政编码 "
    
- -PreferredLanguage " \<language> "
    
- -状态 " \<state name> "
    
- -StreetAddress " \<street address> "
    
- -标题 " \<title name> "
    
- -UsageLocation " \<2-character country or region code> "
    
    这是 ISO 3166-1 alpha-2 (A2) 双字母国家或地区代码。
    
有关其他参数，请参阅 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))。

若要查看所有用户的用户主体名称，请运行以下命令：
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

此命令指示 PowerShell：
  
1. 获取用户帐户的所有信息 (**get-msoluser**) 并将其发送到下一个命令 (**|**) 。
    
1. 按字母顺序对用户主体名称列表进行排序 (**对 UserPrincipalName 进行排序**) 并将其发送到下一个命令 (**|**) 。
    
1. 仅显示每个帐户的 "用户主体名称" 属性 (**选择 "UserPrincipalName**) "。
    
1. 每次显示一屏 (**更**) 。
    
若要根据其显示名称显示帐户的用户主体名称 (名和姓) ，请运行以下命令。 填写 *$userName* 变量，并删除这些 \< and > 字符。
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

本示例显示名为 Caleb Sills 的用户的用户主体名称：
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

通过使用 *$upn* 变量，可以根据各个帐户的显示名称对其进行更改。 下面的示例将 *Belinda Newman*的使用位置设置为 *法国*，但指定了她的显示名称而不是她的用户主体名称：
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>更改所有用户帐户的属性

若要更改所有用户的属性，请使用 **get-msoluser** 和 **get-msoluser** cmdlet 的组合。 下面的示例将所有用户的使用位置更改为 *法国*：
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

此命令指示 PowerShell：
  
1. 获取用户帐户的所有信息 (**get-msoluser**) 并将其发送到下一个命令 (**|**) 。
    
1. 将用户位置设置为 "法国 (**get-msoluser-UsageLocation" "FR"**) 。
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>更改特定用户帐户集的属性

若要更改特定用户帐户集的属性，您可以使用 **get-msoluser**、 **Where**和 **get-msoluser** cmdlet 的组合。 下面的示例将记帐部门中所有用户的使用位置更改为 " *法国*"：
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

此命令指示 PowerShell：
  
1. 获取用户帐户的所有信息 (**get-msoluser**) 并将其发送到下一个命令 (**|**) 。
    
1. 查找其 " *部门* " 属性设置为 "记帐" (**其中 {$ _）的所有用户帐户。部门-eq "记帐"}**) 并将生成的信息发送到下一个命令 (**|**) 。
    
1. 将用户位置设置为 "法国 (**get-msoluser-UsageLocation" "FR"**) 。

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
