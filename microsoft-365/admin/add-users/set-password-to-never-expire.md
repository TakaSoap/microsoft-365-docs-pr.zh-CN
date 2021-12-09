---
title: 设置单个用户的密码永不过期
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: 登录你的 Microsoft 365 管理员帐户，使用密码将一些个人用户密码设置为永不Windows PowerShell。
ms.openlocfilehash: ff2fa9b6dd4e63a1dcdee8280dfdaddc70388ae8
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370232"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>设置单个用户的密码永不过期

本文介绍如何为单个用户设置密码，使密码永不过期。 您必须使用 PowerShell 完成这些步骤。

## <a name="before-you-begin"></a>准备工作

本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。 若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。 [什么是管理员帐户？] ([概述 Microsoft 365 管理中心](../admin-overview/admin-center-overview.md)。

您必须是全局 [管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。

Microsoft 云服务的全局管理员可以使用 Azure Active Directory [PowerShell Graph](/powershell/azure/active-directory/install-adv2)设置特定用户的密码永不过期。 您还可以使用 [AzureAD](/powershell/module/Azuread) cmdlet 删除永不过期的配置或查看将哪些用户密码设置为永不过期。

本指南适用于其他提供程序，如 Intune 和 Microsoft 365，这些提供程序还依赖于Azure AD和目录服务。 密码过期是策略中唯一可以更改的部分。


## <a name="how-to-check-the-expiration-policy-for-a-password"></a>如何检查密码的过期策略

有关 AzureAD 模块中的 Get-AzureADUser 命令，请参阅参考文章 [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser)。

运行下列命令之一：

- 若要了解单个用户的密码是否设置为永不过期，请通过使用 UPN (例如 *，user@contoso.onmicrosoft.com*) 或要检查的用户 ID 运行以下 cmdlet：

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

- 若要查看 **所有用户的"密码永不** 过期"设置，请运行以下 cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- 获取当前用户的桌面上具有 Html 格式 PasswordNeverExpires 的所有用户的报告，并ReportPasswordNeverExpires.html

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- 获取当前用户桌面上 CSV 中 PasswordNeverExpires 的所有用户的报告，并ReportPasswordNeverExpires.csv

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

> [!WARNING]
> 使用 参数配置的 `-PasswordPolicies DisablePasswordExpiration` 用户帐户仍然基于 属性使用 `pwdLastSet` 年龄。 根据 属性，如果将过期更改为 ，则 pwdLastSet 超过 90 天的所有密码都需要用户在下次登录时 `pwdLastSet` `-PasswordPolicies None` 更改密码。 此更改可能会影响大量用户。

### <a name="set-a-password-to-expire"></a>设置密码以过期

运行下列命令之一：

- 若要设置一个用户的密码以便密码过期，请通过使用 UPN 或用户的用户 ID 运行以下 cmdlet：

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- 若要设置组织中所有用户的密码以便其过期，请使用以下 cmdlet：

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>相关内容

[允许用户重置自己的密码](../add-users/let-users-reset-passwords.md)（文章）
[重置密码](../add-users/reset-passwords.md)（文章）\
[为组织设置密码过期策略 (](../manage/set-password-expiration-policy.md) 文章) 
