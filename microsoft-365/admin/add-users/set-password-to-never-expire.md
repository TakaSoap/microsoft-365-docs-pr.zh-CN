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
ms.openlocfilehash: 01817aba0de1f5ca5f0b9bdf7feb1d03d72f6a24
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361745"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="f7f8a-103">将个人用户密码设置为永不过期</span><span class="sxs-lookup"><span data-stu-id="f7f8a-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="f7f8a-104">本文介绍如何将单个用户的密码设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="f7f8a-105">您必须使用 PowerShell 完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f7f8a-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="f7f8a-106">Before you begin</span></span>

<span data-ttu-id="f7f8a-107">本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="f7f8a-108">若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="f7f8a-109">[什么是管理员帐户？](../admin-overview/admin-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> 

<span data-ttu-id="f7f8a-110">您必须是 [全局管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="f7f8a-111">Microsoft 云服务的全局管理员可以使用 [Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) 将密码设置为不会对特定用户过期。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="f7f8a-112">您还可以使用 [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlet 删除永不过期的配置，或查看设置为永不过期的用户密码。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="f7f8a-113">本指南适用于其他提供商，如 Intune 和 Microsoft 365，后者还依赖 Azure AD 进行标识和目录服务。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="f7f8a-114">密码过期是策略中唯一可以更改的部分。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="f7f8a-115">只能将未通过目录同步同步的用户帐户的密码配置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="f7f8a-116">有关目录同步的详细信息，请参阅 [CONNECT ad With AZURE AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="f7f8a-117">如何检查密码的过期策略</span><span class="sxs-lookup"><span data-stu-id="f7f8a-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="f7f8a-118">有关 AzureAD 模块中的 AzureADUser 命令的详细信息，请参阅参考文章 [Get AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="f7f8a-119">运行下列命令之一：</span><span class="sxs-lookup"><span data-stu-id="f7f8a-119">Run one of the following commands:</span></span>

- <span data-ttu-id="f7f8a-120">若要查看是否将单个用户的密码设置为永不过期，请使用 UPN (运行以下 cmdlet （例如， *user@contoso.onmicrosoft.com*) 或要检查的用户的用户 ID）：</span><span class="sxs-lookup"><span data-stu-id="f7f8a-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="f7f8a-121">示例：</span><span class="sxs-lookup"><span data-stu-id="f7f8a-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="f7f8a-122">若要查看所有用户的 " **密码永不过期** " 设置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f7f8a-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="f7f8a-123">使用名为**ReportPasswordNeverExpires.html**的当前用户的桌面上的 Html 中的所有用户获取报告</span><span class="sxs-lookup"><span data-stu-id="f7f8a-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="f7f8a-124">若要使用名称**ReportPasswordNeverExpires.csv**获取当前用户的在 CSV 中具有 PasswordNeverExpires 的所有用户的报告</span><span class="sxs-lookup"><span data-stu-id="f7f8a-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="f7f8a-125">若要将组织中所有用户的密码设置为永不过期，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f7f8a-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="f7f8a-126">将密码设置为过期</span><span class="sxs-lookup"><span data-stu-id="f7f8a-126">Set a password to expire</span></span>

<span data-ttu-id="f7f8a-127">运行下列命令之一：</span><span class="sxs-lookup"><span data-stu-id="f7f8a-127">Run one of the following commands:</span></span>

- <span data-ttu-id="f7f8a-128">若要设置一个用户的密码以使密码过期，请使用 UPN 或用户的用户 ID 运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f7f8a-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="f7f8a-129">若要将组织中所有用户的密码设置为过期，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f7f8a-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> <span data-ttu-id="f7f8a-130">使用参数配置的用户帐户 `-PasswordPolicies DisablePasswordExpiration` 基于 `pwdLastSet` 用户帐户属性的期限。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-130">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="f7f8a-131">例如，如果您将用户密码设置为永不过期，然后90或更多天，则密码仍将过期。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-131">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="f7f8a-132">根据 `pwdLastSet` 用户帐户属性，对于使用参数配置的用户帐户 `-PasswordPolicies None` ，所有 `pwdLastSet` 早于90天的密码都要求用户在下次登录时更改这些密码。此更改可能会影响大量用户。</span><span class="sxs-lookup"><span data-stu-id="f7f8a-132">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>

## <a name="related-content"></a><span data-ttu-id="f7f8a-133">相关内容</span><span class="sxs-lookup"><span data-stu-id="f7f8a-133">Related content</span></span>

[<span data-ttu-id="f7f8a-134">允许用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="f7f8a-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="f7f8a-135">重置密码</span><span class="sxs-lookup"><span data-stu-id="f7f8a-135">Reset passwords</span></span>](../add-users/reset-passwords.md)