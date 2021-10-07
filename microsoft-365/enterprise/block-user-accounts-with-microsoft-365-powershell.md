---
title: 使用 powerShell Microsoft 365用户帐户
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: 如何使用 PowerShell 阻止和取消阻止对帐户Microsoft 365访问。
ms.openlocfilehash: 0ecfdfb8f99175ce5312769593c7637a7d1ae25b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189185"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>使用 powerShell Microsoft 365用户帐户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

阻止访问 Microsoft 365 帐户时，可防止任何人使用该帐户登录并访问组织中Microsoft 365和数据。 可以使用 PowerShell 阻止对单个或多个用户帐户的访问。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="block-access-to-individual-user-accounts"></a>阻止对单个用户帐户的访问

使用以下语法阻止单个用户帐户：

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> **Set-AzureAD** cmdlet 中的 *-ObjectID* 参数接受帐户登录名（也称为用户主体名称）或帐户的对象 ID。

此示例阻止访问用户帐户 *fabricec@litwareinc.com。*

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

若要取消阻止此用户帐户，请运行以下命令：

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

若要根据用户的帐户显示用户帐户 UPN 显示名称，请使用以下命令：

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

本示例显示用户  *Caleb Sills* 的用户帐户 UPN。

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

若要基于用户的用户帐户阻止显示名称，请使用以下命令：

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

若要检查用户帐户的阻止状态，请使用以下命令：

```powershell
Get-AzureADUser  -ObjectID <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>阻止多个用户帐户

若要阻止访问多个用户帐户，请在每个行上创建一个包含一个帐户登录名的文本文件，如下所示：

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

在下列命令中，示例文本文件为 *C：\My Documents\Accounts.txt。* 将此文件名替换为文本文件的路径和文件名。

若要阻止访问该文本文件中列出的帐户，请运行以下命令：

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

若要取消阻止文本文件中列出的帐户，请运行以下命令：

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="block-individual-user-accounts"></a>阻止单个用户帐户

使用以下语法阻止对单个用户帐户的访问：

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core 不支持 Microsoft Azure Active Directory 模块Windows PowerShell名称中具有 *Msol* 的 cmdlet。 您必须从应用程序运行这些 cmdlet Windows PowerShell。

此示例阻止对用户帐户 *fabricec litwareinc.com。 \@*

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

若要取消阻止该用户帐户，请运行以下命令：

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

若要检查用户帐户的阻止状态，请运行以下命令：

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>阻止访问多个用户帐户

首先，在每个行上创建一个包含一个帐户的文本文件，如下所示：

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

在下列命令中，示例文本文件为 *C：\My Documents\Accounts.txt。* 将此文件名替换为文本文件的路径和文件名。

若要阻止对文本文件中列出的帐户的访问，请运行以下命令：

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
若要解除阻止该文本文件中列出的帐户，请运行以下命令：

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)

[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
