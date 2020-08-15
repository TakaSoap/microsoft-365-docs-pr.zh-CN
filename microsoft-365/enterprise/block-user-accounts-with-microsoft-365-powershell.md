---
title: 使用 PowerShell 阻止 Microsoft 365 用户帐户
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
description: 本文介绍如何使用 PowerShell 阻止和取消阻止对 Microsoft 365 帐户的访问。
ms.openlocfilehash: a9ade2f41fb601da00ca1c2d1905ca0cb003dcb3
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687829"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="564d5-103">使用 PowerShell 阻止 Microsoft 365 用户帐户</span><span class="sxs-lookup"><span data-stu-id="564d5-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="564d5-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="564d5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="564d5-105">阻止访问 Microsoft 365 帐户将阻止任何人使用该帐户登录并访问 Microsoft 365 组织中的服务和数据。</span><span class="sxs-lookup"><span data-stu-id="564d5-105">Blocking access to a Microsoft 365 account prevents anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="564d5-106">您可以使用 PowerShell 阻止对单个和多个用户帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="564d5-106">You can use PowerShell to block access to individual and multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="564d5-107">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="564d5-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="564d5-108">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="564d5-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="564d5-109">阻止对单个用户帐户的访问</span><span class="sxs-lookup"><span data-stu-id="564d5-109">Block access to individual user accounts</span></span>

<span data-ttu-id="564d5-110">使用以下语法来阻止单个用户帐户：</span><span class="sxs-lookup"><span data-stu-id="564d5-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="564d5-111">AzureAD cmdlet 中的-ObjectID 参数可接受帐户登录名（也称为 "用户主体名称"）或帐户的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="564d5-111">The -ObjectID parameter in the Set-AzureAD cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span> 
  
<span data-ttu-id="564d5-112">此示例阻止访问用户帐户 fabricec@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="564d5-112">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="564d5-113">若要取消阻止此用户帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="564d5-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="564d5-114">若要根据用户的显示名称显示用户帐户 UPN，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="564d5-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="564d5-115">本示例显示名为 Caleb Sills 的用户的用户帐户 UPN。</span><span class="sxs-lookup"><span data-stu-id="564d5-115">This example displays the user account UPN for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="564d5-116">若要基于用户的显示名称阻止某个帐户，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="564d5-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="564d5-117">在任何时候，都可以使用以下命令检查用户帐户的阻止状态：</span><span class="sxs-lookup"><span data-stu-id="564d5-117">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="564d5-118">阻止对多个用户帐户的访问</span><span class="sxs-lookup"><span data-stu-id="564d5-118">Block access to multiple user accounts</span></span>

<span data-ttu-id="564d5-119">若要阻止对多个用户帐户的访问，请创建一个文本文件，其中每行包含一个帐户登录名，如下所示：</span><span class="sxs-lookup"><span data-stu-id="564d5-119">To block access to multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="564d5-120">在以下命令中，示例文本文件为 C:\My Documents\Accounts.txt。</span><span class="sxs-lookup"><span data-stu-id="564d5-120">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="564d5-121">将此替换为您的文本文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="564d5-121">Replace this with the path and file name of your text file.</span></span>
  
<span data-ttu-id="564d5-122">若要阻止访问该文本文件中列出的帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="564d5-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="564d5-123">若要解除阻止该文本文件中列出的帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="564d5-123">To unblock the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="564d5-124">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="564d5-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="564d5-125">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="564d5-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="564d5-126">阻止对单个用户帐户的访问</span><span class="sxs-lookup"><span data-stu-id="564d5-126">Block access to individual user accounts</span></span>

<span data-ttu-id="564d5-127">使用以下语法来阻止对单个用户帐户的访问：</span><span class="sxs-lookup"><span data-stu-id="564d5-127">Use the following syntax to block access to an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="564d5-128">PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="564d5-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="564d5-129">若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。</span><span class="sxs-lookup"><span data-stu-id="564d5-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="564d5-130">此示例阻止访问用户帐户 fabricec@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="564d5-130">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="564d5-131">若要取消阻止该用户帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="564d5-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="564d5-132">在任何时候，都可以使用以下命令检查用户帐户的阻止状态：</span><span class="sxs-lookup"><span data-stu-id="564d5-132">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="564d5-133">阻止对多个用户帐户的访问</span><span class="sxs-lookup"><span data-stu-id="564d5-133">Block access to multiple user accounts</span></span>

<span data-ttu-id="564d5-134">首先，创建一个文本文件，其中每行包含一个帐户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="564d5-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="564d5-135">在以下命令中，示例文本文件为 C:\My Documents\Accounts.txt。</span><span class="sxs-lookup"><span data-stu-id="564d5-135">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="564d5-136">将此替换为您的文本文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="564d5-136">Replace this with the path and file name of your text file.</span></span>
    
<span data-ttu-id="564d5-137">若要阻止访问该文本文件中列出的帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="564d5-137">To block access to the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="564d5-138">若要解除阻止该文本文件中列出的帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="564d5-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="564d5-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="564d5-139">See also</span></span>

[<span data-ttu-id="564d5-140">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="564d5-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="564d5-141">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="564d5-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="564d5-142">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="564d5-142">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
