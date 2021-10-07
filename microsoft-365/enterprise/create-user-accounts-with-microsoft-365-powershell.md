---
title: 使用 PowerShell Microsoft 365用户帐户
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: 如何使用 PowerShell 创建单个或多个Microsoft 365用户帐户。
ms.openlocfilehash: 7396e98e597491910b639e5a0d0c57b8f685bc02
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171995"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>使用 PowerShell Microsoft 365用户帐户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

可以使用 PowerShell for Microsoft 365创建用户帐户，包括多个帐户。

在 PowerShell 中创建用户帐户时，始终需要某些帐户属性。 其他属性不是必需的，但非常重要。 请参阅下表。
  
|**属性名称**|**是否必需？**|**说明**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |是  <br/> |这是显示名称服务中使用的Microsoft 365。 例如 *，Caleb Sills*。 <br/> |
|**UserPrincipalName** <br/> |是  <br/> |这是用于登录到服务Microsoft 365名称。 例如 *，CalebS \@ contoso.onmicrosoft.com*。  <br/> |
|**FirstName** <br/> |否  <br/> ||
|**LastName** <br/> |否  <br/> ||
|**LicenseAssignment** <br/> |否  <br/> |这是许可计划 (也称为许可证计划或 SKU) ，从其中向用户帐户分配可用许可证。 许可证定义Microsoft 365帐户可用的服务。 创建帐户时，不必向用户分配许可证，但该帐户必须具有许可证才能访问Microsoft 365服务。 创建用户帐户后，您有 30 天的时间可以对该用户帐户授权。 |
|**密码** <br/> |否  <br/> | 如果您没有指定密码，将向用户帐户分配一个随机密码，且该密码将显示在命令结果中。 如果指定密码，则密码需要为 8 到 16 个以下类型的 ASCII 文本字符：小写字母、大写字母、数字和符号。<br/> |
|**UsageLocation** <br/> |否  <br/> |这是一个由两位字母组成的有效 ISO 3166-1 国家/地区代码。 例如 *，US* 代表美国 *，FR* 代表法国。 提供此值很重要，因为某些 Microsoft 365服务在某些国家/地区不可用。 无法将许可证分配给用户帐户，除非该帐户已配置此值。 有关详细信息，请参阅[关于许可证限制](https://go.microsoft.com/fwlink/p/?LinkId=691730)。<br/> |

>[!Note]
>[了解如何使用 Microsoft 365 管理中心。](../admin/add-users/add-users.md)
> 
> 有关其他资源的列表，请参阅管理 [用户和组](/admin)。
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

连接后，使用以下语法创建单个帐户：
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

本示例为美国用户 *Caleb Sills 创建一个帐户*：
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="create-an-individual-user-account"></a>创建单个用户帐户

若要创建单个帐户，请使用下面的语法：
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core 不支持 Microsoft Azure Active Directory 模块Windows PowerShell名称中具有 *Msol* 的 cmdlet。 从 Windows PowerShell 运行这些 cmdlet。
>

若要列出可用的许可计划名称，请使用此命令：

````powershell
Get-MsolAccountSku
````

本示例为美国用户 *Caleb Sills* 创建一个帐户，并分配来自 E3 (Office 365 企业版许可证) `contoso:ENTERPRISEPACK` 许可证。
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>创建多个用户帐户

1. 创建包含所需用户帐户信息的逗号分隔值 (CSV) 文件。例如：

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   >列名及其在 CSV 文件第一行中的顺序是任意的。 但请确保文件其余部分的数据顺序与列名称的顺序相匹配。 并使用 PowerShell for Microsoft 365 命令中的参数值列名称。
    
2. 使用以下语法：
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   此示例从文件 *C：\My Documents\NewAccounts.csv* 创建用户帐户，并记录在名为 *C：\My Documents\NewAccountResults.csv的文件中*。
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. 查看输出文件以查看结果。 我们没有指定密码，因此生成的随机密码Microsoft 365输出文件中可见。
    
## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)