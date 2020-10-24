---
title: 使用 PowerShell 删除 Microsoft 365 用户帐户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: 了解如何使用 PowerShell 中的不同模块删除 Microsoft 365 用户帐户。
ms.openlocfilehash: 39bf57fe7e7aad1bdc9915e503107ad799515030
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754536"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="43567-103">使用 PowerShell 删除 Microsoft 365 用户帐户</span><span class="sxs-lookup"><span data-stu-id="43567-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="43567-104">可以使用适用于 Microsoft 365 的 PowerShell 删除和还原用户帐户。</span><span class="sxs-lookup"><span data-stu-id="43567-104">You can use PowerShell for Microsoft 365 to delete and restore user accounts.</span></span>

>[!Note]
><span data-ttu-id="43567-105">了解如何使用 Microsoft 365 管理中心 [还原用户帐户](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) 。</span><span class="sxs-lookup"><span data-stu-id="43567-105">Learn how to [restore a user account](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) by using the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="43567-106">有关其他资源的列表，请参阅 [管理用户和组](https://docs.microsoft.com/microsoft-365/admin/add-users/)。</span><span class="sxs-lookup"><span data-stu-id="43567-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="43567-107">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="43567-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="43567-108">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="43567-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="43567-109">连接后，请使用以下语法删除单个用户帐户：</span><span class="sxs-lookup"><span data-stu-id="43567-109">After you connect, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="43567-110">本示例将删除用户帐户 *fabricec \@ litwareinc.com*。</span><span class="sxs-lookup"><span data-stu-id="43567-110">This example removes the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="43567-111">**AzureADUser** cmdlet 中的 *-ObjectID*参数可接受帐户的登录名，也称为用户主体名称或帐户的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="43567-111">The *-ObjectID* parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name or the account's object ID.</span></span>
  
<span data-ttu-id="43567-112">若要显示基于用户名的帐户名称，请使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="43567-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="43567-113">本示例显示用户 *Caleb Sills*的帐户名称。</span><span class="sxs-lookup"><span data-stu-id="43567-113">This example displays the account name for the user *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="43567-114">若要删除基于用户显示名称的帐户，请使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="43567-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="43567-115">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="43567-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="43567-116">当您通过 Windows PowerShell 的 Microsoft Azure Active Directory 模块删除用户帐户时，该帐户不会被永久删除。</span><span class="sxs-lookup"><span data-stu-id="43567-116">When you delete a user account through the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="43567-117">您可以在 30 天内还原已删除的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="43567-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="43567-118">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="43567-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="43567-119">若要删除一个用户帐户，请使用下面的语法：</span><span class="sxs-lookup"><span data-stu-id="43567-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="43567-120">PowerShell Core 不支持 Windows PowerShell 模块的 Microsoft Azure Active Directory 模块以及在其名称中带有 *Msol* 的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="43567-120">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="43567-121">从 Windows PowerShell 运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="43567-121">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="43567-122">本示例删除用户帐户 *BelindaN@litwareinc.com*。</span><span class="sxs-lookup"><span data-stu-id="43567-122">This example deletes the user account *BelindaN@litwareinc.com*.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="43567-123">若要在 30 天的宽限期内还原已删除的用户帐户，请使用下面的语法：</span><span class="sxs-lookup"><span data-stu-id="43567-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="43567-124">本示例将恢复已删除的帐户 *BelindaN \@ litwareinc.com*。</span><span class="sxs-lookup"><span data-stu-id="43567-124">This example restores the deleted account *BelindaN\@litwareinc.com*.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> <span data-ttu-id="43567-125">若要查看可以还原的已删除用户的列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="43567-125">To see the list of deleted users that can be restored, run the following command:</span></span>
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> <span data-ttu-id="43567-126">如果用户帐户的初始用户主体名称已被另一个帐户使用，那么在还原用户帐户时，请使用 _NewUserPrincipalName_ 参数而不是 _UserPrincipalName_ 来指定一个不同的用户主体名称。</span><span class="sxs-lookup"><span data-stu-id="43567-126">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="43567-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43567-127">See also</span></span>

[<span data-ttu-id="43567-128">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="43567-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="43567-129">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="43567-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="43567-130">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="43567-130">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
