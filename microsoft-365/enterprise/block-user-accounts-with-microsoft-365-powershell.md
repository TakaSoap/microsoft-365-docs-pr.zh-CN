---
title: 使用 PowerShell Microsoft 365用户帐户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: 如何使用 PowerShell 阻止和取消阻止对帐户Microsoft 365访问。
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754676"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="cfb3d-103">使用 PowerShell Microsoft 365用户帐户</span><span class="sxs-lookup"><span data-stu-id="cfb3d-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="cfb3d-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="cfb3d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cfb3d-105">阻止访问 Microsoft 365 帐户时，可防止任何人使用该帐户登录并访问组织中Microsoft 365和数据。</span><span class="sxs-lookup"><span data-stu-id="cfb3d-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="cfb3d-106">可以使用 PowerShell 阻止对单个或多个用户帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="cfb3d-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="cfb3d-107">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfb3d-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="cfb3d-108">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="cfb3d-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="cfb3d-109">阻止对单个用户帐户的访问</span><span class="sxs-lookup"><span data-stu-id="cfb3d-109">Block access to individual user accounts</span></span>

<span data-ttu-id="cfb3d-110">使用以下语法阻止单个用户帐户：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="cfb3d-111">**Set-AzureAD** cmdlet 中的 *-ObjectID* 参数接受帐户登录名（也称为用户主体名称）或帐户的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="cfb3d-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="cfb3d-112">此示例阻止访问用户帐户 *fabricec@litwareinc.com。*</span><span class="sxs-lookup"><span data-stu-id="cfb3d-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="cfb3d-113">若要取消阻止此用户帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="cfb3d-114">若要根据用户的帐户显示用户帐户 UPN 显示名称，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="cfb3d-115">本示例显示用户  *Caleb Sills* 的用户帐户 UPN。</span><span class="sxs-lookup"><span data-stu-id="cfb3d-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="cfb3d-116">若要基于用户的用户帐户阻止显示名称，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="cfb3d-117">若要检查用户帐户的阻止状态，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="cfb3d-118">阻止多个用户帐户</span><span class="sxs-lookup"><span data-stu-id="cfb3d-118">Block multiple user accounts</span></span>

<span data-ttu-id="cfb3d-119">若要阻止访问多个用户帐户，请在每个行上创建一个包含一个帐户登录名的文本文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="cfb3d-120">在下列命令中，示例文本文件为 *C：\My Documents\Accounts.txt。*</span><span class="sxs-lookup"><span data-stu-id="cfb3d-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="cfb3d-121">将此文件名替换为文本文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="cfb3d-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="cfb3d-122">若要阻止访问该文本文件中列出的帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="cfb3d-123">若要取消阻止文本文件中列出的帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="cfb3d-124">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="cfb3d-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="cfb3d-125">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cfb3d-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="cfb3d-126">阻止单个用户帐户</span><span class="sxs-lookup"><span data-stu-id="cfb3d-126">Block individual user accounts</span></span>

<span data-ttu-id="cfb3d-127">使用以下语法阻止对单个用户帐户的访问：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="cfb3d-128">PowerShell Core 不支持模块Microsoft Azure Active Directory模块Windows PowerShell名称中具有 *Msol* 的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cfb3d-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="cfb3d-129">您必须从应用程序运行这些 cmdlet Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cfb3d-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="cfb3d-130">此示例阻止访问用户帐户 *fabricec litwareinc.com。 \@*</span><span class="sxs-lookup"><span data-stu-id="cfb3d-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="cfb3d-131">若要取消阻止该用户帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="cfb3d-132">若要检查用户帐户的阻止状态，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="cfb3d-133">阻止访问多个用户帐户</span><span class="sxs-lookup"><span data-stu-id="cfb3d-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="cfb3d-134">首先，在每个行上创建一个包含一个帐户的文本文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="cfb3d-135">在下列命令中，示例文本文件为 *C：\My Documents\Accounts.txt。*</span><span class="sxs-lookup"><span data-stu-id="cfb3d-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="cfb3d-136">将此文件名替换为文本文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="cfb3d-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="cfb3d-137">若要阻止对文本文件中列出的帐户的访问，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="cfb3d-138">若要解除阻止该文本文件中列出的帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cfb3d-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="cfb3d-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfb3d-139">See also</span></span>

[<span data-ttu-id="cfb3d-140">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="cfb3d-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="cfb3d-141">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cfb3d-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="cfb3d-142">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="cfb3d-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
