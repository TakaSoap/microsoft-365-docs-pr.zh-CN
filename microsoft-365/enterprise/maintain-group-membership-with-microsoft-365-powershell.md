---
title: 使用 PowerShell 维护安全组成员身份
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: 了解如何使用 PowerShell 维护组Microsoft 365成员身份。
ms.openlocfilehash: 3637fb7d2e68091c43e624e9b6780d032c1930bc
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208789"
---
# <a name="maintain-security-group-membership-with-powershell"></a>使用 PowerShell 维护安全组成员身份

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

可以使用 PowerShell for Microsoft 365作为安全组Microsoft 365 管理中心，以维护安全组Microsoft 365。 

>[!Note]
>[了解如何使用Microsoft 365维护组](../admin/create-groups/add-or-remove-members-from-groups.md)Microsoft 365 管理中心。 有关其他资源的列表，请参阅管理 [用户和组](/admin)。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell
首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>添加或删除用户帐户作为组的成员

若要按用户帐户 **的 UPN** 添加用户帐户，请填写用户帐户用户主体名称 (UPN)  (示例：belindan@contoso.com) 和安全组 显示名称，删除"<"和">"字符，在 PowerShell 窗口或 PowerShell 集成脚本环境 (ISE) 中运行这些命令。

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

若要按用户帐户的 **显示名称** 添加用户帐户，请填写用户帐户 显示名称 (示例：Belinda Newman) 和组 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

若要通过 UPN 删除用户帐户，请填写用户帐户 **UPN** (示例：belindan@contoso.com) 和组 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

若要通过用户帐户的 **显示名称** 删除用户帐户，请填写用户帐户 显示名称 (示例：Belinda Newman) 和组 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>添加或删除组作为组的成员

安全组可以包含其他组作为成员。 Microsoft 365组，但不能。 本节包含 PowerShell 命令，用于仅为安全组添加或删除组。

若要按组的 **显示名称** 添加组，请填写要添加的组的 显示名称 以及将包含成员组的组的 显示名称，然后使用 PowerShell 窗口或 PowerShell ISE 运行这些命令。

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

若要按组 **显示名称** 删除组，请填写要删除的组的 显示名称 和将包含成员组的组的 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>添加或删除用户帐户作为组的成员

若要按用户帐户 **的 UPN** 添加用户帐户，请填写用户帐户用户主体名称 (UPN)  (示例：belindan@contoso.com) 和组 显示名称，删除"<"和">"字符，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

若要按用户帐户的 **显示名称** 添加用户帐户，请填写用户帐户 显示名称 (示例：Belinda Newman) 和组 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

若要通过 UPN 删除用户帐户，请填写用户帐户 **UPN** (示例：belindan@contoso.com) 和组 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

若要通过用户帐户的 **显示名称** 删除用户帐户，请填写用户帐户 显示名称 (示例：Belinda Newman) 和组 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>添加或删除组作为组的成员

安全组可以包含其他组作为成员。 Microsoft 365组，但不能。 本节包含 PowerShell 命令，用于仅为安全组添加或删除组。

若要按组的 **显示名称** 添加组，请填写要添加的组的 显示名称 以及将包含成员组的组的 显示名称，然后使用 PowerShell 窗口或 PowerShell ISE 运行这些命令。

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

若要按组 **显示名称** 删除组，请填写要删除的组的 显示名称 和将包含成员组的组的 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)