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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: 了解如何使用 Windows PowerShell 将某些个人用户密码设置为永不过期。
ms.openlocfilehash: f85eb2d3aaf5b19779ea8f293e2cbdc28c1535aa
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804204"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>将个人用户密码设置为永不过期

## <a name="set-the-password-expiration-policy-for-your-organization"></a>为组织设置密码过期策略

1. 在 "管理中心" 中，转到 "**设置**" "设置" \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a>页。
2. 在 "设置" 页面顶部，选择 " **安全 & 隐私**"。
3. 选择“**密码过期策略**”。 
4. 如果密码设置为永不过期，请单击 " **将用户密码设置为在数天后过期**" 旁边的复选框。 您将获得用于指定密码过期前的天数的选项。

## <a name="set-the-password-expiration-policy-for-individual-users"></a>为单个用户设置密码过期策略

Microsoft 云服务的全局管理员可以使用 [Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) 将密码设置为不会对特定用户过期。 您还可以使用 [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlet 删除永不过期的配置，或查看设置为永不过期的用户密码。

本指南适用于其他提供商，如 Intune 和 Microsoft 365，后者还依赖 Azure AD 进行标识和目录服务。 密码过期是策略中唯一可以更改的部分。

有关用于图形的 Azure AD PowerShell 的详细信息，请参阅 [Azure Active Directory powershell For graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)。

> [!NOTE]
> 只能将未通过目录同步同步的用户帐户的密码配置为永不过期。 有关目录同步的详细信息，请参阅 [CONNECT ad With AZURE AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。

### <a name="how-to-check-the-expiration-policy-for-a-password"></a>如何检查密码的过期策略

有关 AzureAD 模块中的 AzureADUser 命令的详细信息，请参阅参考文章 [Get AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)。

运行下列命令之一：

- 若要查看是否将单个用户的密码设置为永不过期，请使用 UPN (运行以下 cmdlet （例如， *user@contoso.onmicrosoft.com*) 或要检查的用户的用户 ID）：

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

- 若要查看所有用户的 " **密码永不过期** " 设置，请运行以下 cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- 使用名为**ReportPasswordNeverExpires.html**的当前用户的桌面上的 Html 中的所有用户获取报告

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- 若要使用名称**ReportPasswordNeverExpires.csv**获取当前用户的在 CSV 中具有 PasswordNeverExpires 的所有用户的报告

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a>将密码设置为过期

运行下列命令之一：

- 若要设置一个用户的密码以使密码过期，请使用 UPN 或用户的用户 ID 运行以下 cmdlet：

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- 若要将组织中所有用户的密码设置为过期，请使用以下 cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a>将密码设置为永不过期

运行下列命令之一：

- 若要将一个用户的密码设置为永不过期，请使用 UPN 或用户的用户 ID 运行以下 cmdlet：

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- 若要将组织中所有用户的密码设置为永不过期，请运行以下 cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> 使用参数配置的用户帐户 `-PasswordPolicies DisablePasswordExpiration` 基于 `pwdLastSet` 用户帐户属性的期限。 例如，如果您将用户密码设置为永不过期，然后90或更多天，则密码仍将过期。 根据 `pwdLastSet` 用户帐户属性，对于使用参数配置的用户帐户 `-PasswordPolicies None` ，所有 `pwdLastSet` 早于90天的密码都要求用户在下次登录时更改这些密码。此更改可能会影响大量用户。
