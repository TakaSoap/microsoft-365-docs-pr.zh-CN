---
title: 使用 PowerShell 管理密码
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: 了解如何使用 PowerShell 管理密码。
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073188"
---
# <a name="manage-passwords-with-powershell"></a>使用 PowerShell 管理密码

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

您可以使用 PowerShell for Microsoft 365 作为 microsoft 365 管理中心的替代方法来管理 Microsoft 365 中的密码。 

当本文中的命令块要求您指定变量值时，请按照这些步骤操作。

1. 将命令块复制到剪贴板，并将其粘贴到记事本或 PowerShell 集成脚本环境中 (ISE) 。
2. 填写变量值，并删除 "<" 和 ">" 字符。
3. 在 PowerShell 窗口或 PowerShell ISE 中运行命令。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="set-a-password"></a>设置密码

使用这些命令指定用户帐户的密码。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a>强制用户更改其密码

使用这些命令设置密码，并强制用户更改其新密码。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

使用这些命令设置密码，并强制用户在下次登录时更改其新密码。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="set-a-password"></a>设置密码

使用这些命令指定用户帐户的密码。

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a>强制用户更改其密码

使用这些命令强制用户更改其密码。

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)

