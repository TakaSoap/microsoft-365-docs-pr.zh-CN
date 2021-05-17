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
description: 了解如何使用密码设置一些个人用户密码永不Windows PowerShell。
ms.openlocfilehash: c70fce1c3ea9cb1dea66982a27ddb24e2b2de255
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222059"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="ed1d9-103">设置单个用户的密码永不过期</span><span class="sxs-lookup"><span data-stu-id="ed1d9-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="ed1d9-104">本文介绍如何为单个用户设置密码，使密码永不过期。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="ed1d9-105">您必须使用 PowerShell 完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ed1d9-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="ed1d9-106">Before you begin</span></span>

<span data-ttu-id="ed1d9-107">本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="ed1d9-108">若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="ed1d9-109">[什么是管理员帐户？](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)</span><span class="sxs-lookup"><span data-stu-id="ed1d9-109">[What's an admin account?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).</span></span> 

<span data-ttu-id="ed1d9-110">您必须是全局 [管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="ed1d9-111">Microsoft 云服务的全局管理员可以使用 Azure Active Directory [PowerShell Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)设置特定用户的密码永不过期。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="ed1d9-112">您还可以使用 [AzureAD](/powershell/module/Azuread) cmdlet 删除永不过期的配置或查看将哪些用户密码设置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="ed1d9-113">本指南适用于其他提供程序，如 Intune 和 Microsoft 365，这些提供程序还依赖 Azure AD 提供标识和目录服务。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="ed1d9-114">密码过期是策略中唯一可以更改的部分。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="ed1d9-115">只能将未通过目录同步同步的用户帐户的密码配置为永不过期。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="ed1d9-116">有关目录同步详细信息，请参阅 连接[AD with Azure AD。](/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="ed1d9-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="ed1d9-117">如何检查密码的过期策略</span><span class="sxs-lookup"><span data-stu-id="ed1d9-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="ed1d9-118">有关 AzureAD 模块中的 Get-AzureADUser 命令，请参阅参考文章 [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="ed1d9-119">运行下列命令之一：</span><span class="sxs-lookup"><span data-stu-id="ed1d9-119">Run one of the following commands:</span></span>

- <span data-ttu-id="ed1d9-120">若要了解单个用户的密码是否设置为永不过期，请通过使用 UPN (例如 *user@contoso.onmicrosoft.com*) 或要检查的用户 ID 运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ed1d9-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="ed1d9-121">示例：</span><span class="sxs-lookup"><span data-stu-id="ed1d9-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="ed1d9-122">若要查看 **所有用户的"密码永不** 过期"设置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ed1d9-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="ed1d9-123">获取当前用户的桌面上具有 Html 格式 PasswordNeverExpires 的所有用户的报告，其名称ReportPasswordNeverExpires.htm **l**</span><span class="sxs-lookup"><span data-stu-id="ed1d9-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="ed1d9-124">获取当前用户桌面上 CSV 中 PasswordNeverExpires 的所有用户的报告，并ReportPasswordNeverExpires.csv</span><span class="sxs-lookup"><span data-stu-id="ed1d9-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="ed1d9-125">若要将组织中所有用户的密码设置为永不过期，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ed1d9-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="ed1d9-126">使用 参数配置的 `-PasswordPolicies DisablePasswordExpiration` 用户帐户仍然基于 属性使用 `pwdLastSet` 年龄。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="ed1d9-127">根据 属性，如果将过期更改为 ，则 pwdLastSet 超过 90 天的所有密码都需要用户在下次登录时 `pwdLastSet` `-PasswordPolicies None` 更改密码。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="ed1d9-128">此更改可能会影响大量用户。</span><span class="sxs-lookup"><span data-stu-id="ed1d9-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="ed1d9-129">设置密码以过期</span><span class="sxs-lookup"><span data-stu-id="ed1d9-129">Set a password to expire</span></span>

<span data-ttu-id="ed1d9-130">运行下列命令之一：</span><span class="sxs-lookup"><span data-stu-id="ed1d9-130">Run one of the following commands:</span></span>

- <span data-ttu-id="ed1d9-131">若要设置一个用户的密码以便密码过期，请通过使用 UPN 或用户的用户 ID 运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ed1d9-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="ed1d9-132">若要设置组织中所有用户的密码以便其过期，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ed1d9-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="ed1d9-133">相关内容</span><span class="sxs-lookup"><span data-stu-id="ed1d9-133">Related content</span></span>

[<span data-ttu-id="ed1d9-134">允许用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="ed1d9-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="ed1d9-135">重置密码</span><span class="sxs-lookup"><span data-stu-id="ed1d9-135">Reset passwords</span></span>](../add-users/reset-passwords.md)