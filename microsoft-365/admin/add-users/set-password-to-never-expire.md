---
title: 将个人用户密码设置为永不过期
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
ms.openlocfilehash: 9497dfb5793ddbfc3d6845ec1efba91ad972ea38
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646651"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>将个人用户密码设置为永不过期

本文介绍如何将单个用户的密码设置为永不过期。 您必须使用 PowerShell 完成这些步骤。

## <a name="before-you-begin"></a>准备工作

本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。 若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。 [什么是管理员帐户？](../admin-overview/admin-overview.md) 

您必须是 [全局管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。

Microsoft 云服务的全局管理员可以使用 [Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) 将密码设置为不会对特定用户过期。 您还可以使用 [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlet 删除永不过期的配置，或查看设置为永不过期的用户密码。

本指南适用于其他提供商，如 Intune 和 Microsoft 365，后者还依赖 Azure AD 进行标识和目录服务。 密码过期是策略中唯一可以更改的部分。

> [!NOTE]
> 只能将未通过目录同步同步的用户帐户的密码配置为永不过期。 有关目录同步的详细信息，请参阅 [CONNECT ad With AZURE AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>如何检查密码的过期策略

有关 AzureAD 模块中的 Get-AzureADUser 命令的详细信息，请参阅参考文章 [AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)。

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

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- 若要将组织中所有用户的密码设置为永不过期，请运行以下 cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
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

> [!WARNING]
> 使用参数配置的用户帐户 `-PasswordPolicies DisablePasswordExpiration` 基于 `pwdLastSet` 用户帐户属性的期限。 例如，如果您将用户密码设置为永不过期，然后90或更多天，则密码仍将过期。 根据 `pwdLastSet` 用户帐户属性，对于使用参数配置的用户帐户 `-PasswordPolicies None` ，所有 `pwdLastSet` 早于90天的密码都要求用户在下次登录时更改这些密码。此更改可能会影响大量用户。

## <a name="related-content"></a>相关内容

[允许用户重置自己的密码](../add-users/let-users-reset-passwords.md)

[重置密码](../add-users/reset-passwords.md)