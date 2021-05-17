---
title: 使用 PowerShell 管理密码
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: 了解如何使用 PowerShell 管理密码。
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073188"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="e1ea9-103">使用 PowerShell 管理密码</span><span class="sxs-lookup"><span data-stu-id="e1ea9-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="e1ea9-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="e1ea9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e1ea9-105">可以使用 PowerShell for Microsoft 365作为管理中心Microsoft 365管理密码的Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="e1ea9-106">当本文中的命令块要求您指定变量值时，请使用这些步骤。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="e1ea9-107">将命令块复制到剪贴板并将其粘贴到 isE 记事本 或 PowerShell 集成脚本 (中) 。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="e1ea9-108">填写变量值并删除"<"和">"字符。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="e1ea9-109">在 PowerShell 窗口或 PowerShell ISE 中运行命令。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e1ea9-110">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1ea9-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e1ea9-111">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="e1ea9-112">设置密码</span><span class="sxs-lookup"><span data-stu-id="e1ea9-112">Set a password</span></span>

<span data-ttu-id="e1ea9-113">使用这些命令指定用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="e1ea9-114">强制用户更改其密码</span><span class="sxs-lookup"><span data-stu-id="e1ea9-114">Force a user to change their password</span></span>

<span data-ttu-id="e1ea9-115">使用这些命令设置密码并强制用户更改其新密码。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="e1ea9-116">使用这些命令设置密码，并强制用户在下次登录时更改其新密码。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e1ea9-117">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="e1ea9-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e1ea9-118">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="e1ea9-119">设置密码</span><span class="sxs-lookup"><span data-stu-id="e1ea9-119">Set a password</span></span>

<span data-ttu-id="e1ea9-120">使用这些命令指定用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="e1ea9-121">强制用户更改其密码</span><span class="sxs-lookup"><span data-stu-id="e1ea9-121">Force a user to change their password</span></span>

<span data-ttu-id="e1ea9-122">使用这些命令强制用户更改其密码。</span><span class="sxs-lookup"><span data-stu-id="e1ea9-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="e1ea9-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1ea9-123">See also</span></span>

[<span data-ttu-id="e1ea9-124">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="e1ea9-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e1ea9-125">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e1ea9-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e1ea9-126">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="e1ea9-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

