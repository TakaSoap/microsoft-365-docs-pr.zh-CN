---
title: 将个人用户密码设置为永不过期
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: 了解如何使用 Windows PowerShell 将某些个人用户密码设置为永不过期。
ms.openlocfilehash: 2645e6d5f307a5e5ce8fab5f3a848bf4a539b031
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "43540887"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>将个人用户密码设置为永不过期

## <a name="set-the-password-expiration-policy-for-your-organization"></a>为组织设置密码过期策略

1. 在 "管理中心" 中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全 & 隐私</a>" 页。
2. 选择 "**密码策略**" 旁边的 "**编辑**"。 
3. 如果密码设置为永不过期，请将切换设置为 "**关闭**"。 您将获得用于指定密码过期前的天数的选项。

## <a name="set-the-password-expiration-policy-for-individual-users"></a>为单个用户设置密码过期策略

Microsoft 云服务的全局管理员可以使用[Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)将密码设置为不会对特定用户过期。 您还可以使用[AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlet 删除永不过期的配置，或查看设置为永不过期的用户密码。

本指南适用于其他提供商，如 Intune 和 Office 365，后者还依赖 Azure AD 进行标识和目录服务。 密码过期是策略中唯一可以更改的部分。

有关用于图形的 Azure AD PowerShell 的详细信息，请参阅[Azure Active Directory powershell For graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)。

> [!NOTE]
> 只能将未通过目录同步同步的用户帐户的密码配置为永不过期。 有关目录同步的详细信息，请参阅[CONNECT ad With AZURE AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。

### <a name="how-to-check-the-expiration-policy-for-a-password"></a>如何检查密码的过期策略

有关 AzureAD 模块中的 AzureADUser 命令的详细信息，请参阅参考文章[Get AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)。

运行以下命令之一：

- 若要查看是否将单个用户的密码设置为永不过期，请使用 UPN （例如， *user@contoso.onmicrosoft.com*）或要检查的用户的用户 ID 运行以下 cmdlet：

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    示例：

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- 若要查看所有用户的 "**密码永不过期**" 设置，请运行以下 cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- 若要使用名为**ReportPasswordNeverExpires**的当前用户的桌面上的 Html 中的所有用户获取报告，PasswordNeverExpires

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- 使用名为**ReportPasswordNeverExpires**的当前用户的桌面上的 PasswordNeverExpires 中的所有用户获取报告

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a>将密码设置为过期

运行以下命令之一：

- 若要设置一个用户的密码以使密码过期，请使用 UPN 或用户的用户 ID 运行以下 cmdlet：

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- 若要将组织中所有用户的密码设置为过期，请使用以下 cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a>将密码设置为永不过期

运行以下命令之一：

- 若要将一个用户的密码设置为永不过期，请使用 UPN 或用户的用户 ID 运行以下 cmdlet：

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- 若要将组织中所有用户的密码设置为永不过期，请运行以下 cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> 密码根据属性`-PasswordPolicies DisablePasswordExpiration`设置为 "仍存在`pwdLastSet`年龄"。 如果将用户密码设置为永不过期，然后设置为 90 + 天，则密码将过期。 根据`pwdLastSet`属性，如果将过期时间更改为`-PasswordPolicies None`，则所有`pwdLastSet`早于90天的密码都需要用户在下次登录时更改。 此更改可能会影响大量用户。
