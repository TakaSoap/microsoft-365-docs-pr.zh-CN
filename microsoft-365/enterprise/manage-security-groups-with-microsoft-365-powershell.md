---
title: 使用 PowerShell 管理安全组
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
description: 了解如何使用 PowerShell 管理安全组。
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073193"
---
# <a name="manage-security-groups-with-powershell"></a>使用 PowerShell 管理安全组

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

您可以使用 PowerShell for Microsoft 365 作为 Microsoft 365 管理中心管理安全组的替代方法。 

本文介绍了如何列出、创建、更改设置和删除安全组。 

当本文中的命令块要求您指定变量值时，请按照这些步骤操作。

1. 将命令块复制到剪贴板，并将其粘贴到记事本或 PowerShell 集成脚本环境中 (ISE) 。
2. 填写变量值，并删除 "<" 和 ">" 字符。
3. 在 PowerShell 窗口或 PowerShell ISE 中运行命令。

请参阅 [维护安全组成员身份](maintain-group-membership-with-microsoft-365-powershell.md) 以使用 PowerShell 管理组成员身份。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="list-your-groups"></a>列出你的组

使用此命令可列出你的所有组。

```powershell
Get-AzureADGroup
```
使用这些命令显示特定组的显示名称的设置。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>创建新组

使用此命令创建新的安全组。

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>更改组上的设置

使用这些命令显示组的设置。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

然后，使用 [AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) 文章来确定如何更改设置。

### <a name="remove-a-security-group"></a>删除安全组

使用这些命令删除安全组。

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>管理安全组的所有者

使用这些命令显示安全组的当前所有者。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
使用这些命令通过其用户主体名称将用户帐户添加 **(UPN)** 到安全组的当前所有者。

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
使用这些命令将用户帐户的 **显示名称** 添加到安全组的当前所有者。

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
使用这些命令可通过其 **UPN** 将用户帐户删除到安全组的当前所有者。

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

使用这些命令将用户帐户的 **显示名称** 删除到安全组的当前所有者。

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="list-your-groups"></a>列出你的组

使用此命令可列出你的所有组。

```powershell
Get-MsolGroup
```
使用这些命令显示特定组的显示名称的设置。

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>创建新组

使用此命令创建新的安全组。

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>更改组上的设置

使用这些命令显示组的设置。

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

然后，使用 [MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) 文章来确定如何更改设置。

### <a name="remove-a-security-group"></a>删除安全组

使用这些命令删除安全组。

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)

