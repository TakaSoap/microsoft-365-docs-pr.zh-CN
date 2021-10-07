---
title: 使用 Microsoft 365 PowerShell 配置用户帐户属性
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
- admindeeplinkMAC
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: 使用 PowerShell for Microsoft 365配置租户中单个或多个用户帐户Microsoft 365属性。
ms.openlocfilehash: 01b17837e4babc31d385be66f9387129baf87da1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178907"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>使用 Microsoft 365 PowerShell 配置用户帐户属性

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

可以使用 Microsoft 365 管理中心为<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a>租户的用户帐户配置Microsoft 365属性。 在 PowerShell 中，还可以执行此操作，以及一些在管理中心中无法执行的其他操作。
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

若要在 Azure Active Directory PowerShell for Graph 模块中配置用户帐户的属性，请使用 [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser) cmdlet 并指定要设置或更改的属性。

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="change-properties-for-a-specific-user-account"></a>更改特定用户帐户的属性

可以使用 *-ObjectID* 参数标识帐户，然后使用其他参数设置或更改特定属性。 以下是最常见的参数列表：
  
- -Department " \<department name> "

- -DisplayName " \<full user name> "

- -FacsimilieTelephoneNumber \<fax number> " "

- -GivenName " \<user first name> "

- -Surname " \<user last name> "

- -Mobile " \<mobile phone number> "

- -JobTitle " \<job title> "

- -PreferredLanguage " \<language> "

- -StreetAddress " \<street address> "

- -City " \<city name> "

- -State " \<state name> "

- -PostalCode " \<postal code> "

- -Country " \<country name> "

- -TelephoneNumber " \<office phone number> "

- -UsageLocation " \<2-character country or region code> "

    这是 ISO 3166-1 alpha-2 (A2) 两个字母的国家/地区代码。

有关其他参数，请参阅 [Set-AzureADUser](/powershell/module/azuread/set-azureaduser)。

> [!NOTE]
> 必须先分配使用位置，然后才能将许可证分配给用户帐户。

若要显示用户帐户的用户主体名称，请运行以下命令。
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

此命令指示 PowerShell：
  
1. 获取 **Get-AzureADUser** (用户帐户) 并将其发送到下一个 **|** () 。

1. 按字母顺序对 **UserPrincipalName** (用户主体名称列表进行排序) 并将其发送到下一个 **|** () 。

1. 只显示 Select **UserPrincipalName** (帐户的用户主体名称) 。

1. 一次显示一个屏幕 (**更多**) 。

若要根据帐户的用户名和姓氏显示名称 (用户主体名称) ，请运行以下命令。 填写 *$userName* 变量，然后删除 \< and > 字符：
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

本示例显示具有 *Caleb Sills 显示名称用户帐户的用户主体名称*。
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

通过使用 *$upn* 变量，可以基于单个帐户的用户帐户显示名称。 下面的示例将 *Belinda Newman* 的使用位置设置到法国。 但它指定其显示名称而不是用户主体名称：
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>更改所有用户帐户的属性

若要更改所有用户的属性，可以使用 **Get-AzureADUser** 和 **Set-AzureADUser** cmdlet 的组合。 以下示例将所有用户的使用位置更改到 *法国*：
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

此命令指示 PowerShell：
  
1. 获取 **Get-AzureADUser** (用户帐户的所有信息) 并将其发送到下一个 **|** () 。

1. 将用户位置设置为法国 (**Set-AzureADUser -UsageLocation "FR"**) 。

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>更改一组特定用户帐户的属性

若要更改一组特定用户帐户的属性，可以使用 **Get-AzureADUser、Where** 和 **Set-AzureADUser** cmdlet 的组合。  以下示例将 Accounting 部门所有用户的使用位置更改为 *法国*：
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

此命令指示 PowerShell：
  
1. 获取 **Get-AzureADUser** (用户帐户) ，并将其发送到下一个 **|** () 。

1.  在 Where {$_中查找其 *Department* 属性设置为"Accounting" (**用户帐户。Department -eq "Accounting"}**) ，并将生成的信息发送到下一个命令 **|** () 。

1. 将用户位置设置为法国 (**Set-AzureADUser -UsageLocation "FR"**) 。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

若要为用户帐户配置 Microsoft Azure Active Directory 模块Windows PowerShell，请使用 **Set-MsolUser** cmdlet 并指定要设置或更改的属性。

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
  
> [!NOTE]
> PowerShell Core 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。 从 Windows PowerShell 运行这些 cmdlet。

### <a name="change-properties-for-a-specific-user-account"></a>更改特定用户帐户的属性

若要为特定用户帐户配置属性，请使用 [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet 并指定要设置或更改的属性。 

使用 *-UserPrincipalName* 参数标识帐户，然后使用其他参数设置或更改特定属性。 下面是最常见的参数列表。
  
- -City " \<city name> "

- -Country " \<country name> "

- -Department " \<department name> "

- -DisplayName " \<full user name> "

- -Fax " \<fax number> "

- -FirstName " \<user first name> "

- -LastName " \<user last name> "

- -MobilePhone " \<mobile phone number> "

- -Office " \<office location> "

- -PhoneNumber " \<office phone number> "

- -PostalCode " \<postal code> "

- -PreferredLanguage " \<language> "

- -State " \<state name> "

- -StreetAddress " \<street address> "

- -Title " \<title name> "

- -UsageLocation " \<2-character country or region code> "

    这是 ISO 3166-1 alpha-2 (A2) 两个字母的国家/地区代码。

有关其他参数，请参阅 [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100))。

若要查看所有用户的用户主体名称，请运行以下命令：
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

此命令指示 PowerShell：
  
1. 获取 **Get-MsolUser** (用户帐户) 并将其发送到下一个 **|** () 。

1. 按字母顺序对 **UserPrincipalName** (用户主体名称列表进行排序) 并将其发送到下一个 **|** () 。

1. 只显示 Select **UserPrincipalName** (帐户的用户主体名称) 。

1. 一次显示一个屏幕 (**更多**) 。

若要根据帐户的用户名和姓氏显示名称 (用户主体名称) ，请运行以下命令。 填写 *$userName* 变量，然后删除 \< and > 字符。
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

本示例显示名为 Caleb Sills 的用户的用户主体名称：
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

通过使用 *$upn* 变量，可以基于单个帐户的用户帐户显示名称。 下面是一个示例，将 *Belinda Newman* 的使用位置设置为 *法国*，但指定她显示名称而不是用户主体名称：
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>更改所有用户帐户的属性

若要更改所有用户的属性，请使用 **Get-MsolUser** 和 **Set-MsolUser** cmdlet 的组合。 以下示例将所有用户的使用位置更改到 *法国*：
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

此命令指示 PowerShell：
  
1. 获取 **Get-MsolUser** (用户帐户) 并将其发送到下一个 **|** () 。

1. 将用户位置设置为法国 (**Set-MsolUser -UsageLocation "FR"**) 。

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>更改一组特定用户帐户的属性

若要更改一组特定用户帐户的属性，可以使用 **Get-MsolUser、Where** 和 **Set-MsolUser** cmdlet 的组合。  以下示例将 Accounting 部门所有用户的使用位置更改为 *法国*：
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

此命令指示 PowerShell：
  
1. 获取 **Get-MsolUser** (用户帐户) 并将其发送到下一个 **|** () 。

1. 在 Where {$_中查找其 *Department* 属性设置为"Accounting" (**用户帐户。Department -eq "Accounting"}**) ，并将生成的信息发送到下一个命令 **|** () 。

1. 将用户位置设置为法国 (**Set-MsolUser -UsageLocation "FR"**) 。

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
