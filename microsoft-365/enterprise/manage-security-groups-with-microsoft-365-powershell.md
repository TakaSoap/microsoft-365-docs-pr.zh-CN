---
title: 使用 PowerShell 管理安全组
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
description: 了解如何使用 PowerShell 管理安全组。
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073193"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="9d5be-103">使用 PowerShell 管理安全组</span><span class="sxs-lookup"><span data-stu-id="9d5be-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="9d5be-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="9d5be-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9d5be-105">您可以使用 PowerShell for Microsoft 365 作为 Microsoft 365 管理中心管理安全组的替代方法。</span><span class="sxs-lookup"><span data-stu-id="9d5be-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="9d5be-106">本文介绍了如何列出、创建、更改设置和删除安全组。</span><span class="sxs-lookup"><span data-stu-id="9d5be-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="9d5be-107">当本文中的命令块要求您指定变量值时，请按照这些步骤操作。</span><span class="sxs-lookup"><span data-stu-id="9d5be-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="9d5be-108">将命令块复制到剪贴板，并将其粘贴到记事本或 PowerShell 集成脚本环境中 (ISE) 。</span><span class="sxs-lookup"><span data-stu-id="9d5be-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="9d5be-109">填写变量值，并删除 "<" 和 ">" 字符。</span><span class="sxs-lookup"><span data-stu-id="9d5be-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="9d5be-110">在 PowerShell 窗口或 PowerShell ISE 中运行命令。</span><span class="sxs-lookup"><span data-stu-id="9d5be-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="9d5be-111">请参阅 [维护安全组成员身份](maintain-group-membership-with-microsoft-365-powershell.md) 以使用 PowerShell 管理组成员身份。</span><span class="sxs-lookup"><span data-stu-id="9d5be-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="9d5be-112">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d5be-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="9d5be-113">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="9d5be-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="9d5be-114">列出你的组</span><span class="sxs-lookup"><span data-stu-id="9d5be-114">List your groups</span></span>

<span data-ttu-id="9d5be-115">使用此命令可列出你的所有组。</span><span class="sxs-lookup"><span data-stu-id="9d5be-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="9d5be-116">使用这些命令显示特定组的显示名称的设置。</span><span class="sxs-lookup"><span data-stu-id="9d5be-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="9d5be-117">创建新组</span><span class="sxs-lookup"><span data-stu-id="9d5be-117">Create a new group</span></span>

<span data-ttu-id="9d5be-118">使用此命令创建新的安全组。</span><span class="sxs-lookup"><span data-stu-id="9d5be-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="9d5be-119">更改组上的设置</span><span class="sxs-lookup"><span data-stu-id="9d5be-119">Change the settings on a group</span></span>

<span data-ttu-id="9d5be-120">使用这些命令显示组的设置。</span><span class="sxs-lookup"><span data-stu-id="9d5be-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="9d5be-121">然后，使用 [AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) 文章来确定如何更改设置。</span><span class="sxs-lookup"><span data-stu-id="9d5be-121">Then, use the [Set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="9d5be-122">删除安全组</span><span class="sxs-lookup"><span data-stu-id="9d5be-122">Remove a security group</span></span>

<span data-ttu-id="9d5be-123">使用这些命令删除安全组。</span><span class="sxs-lookup"><span data-stu-id="9d5be-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="9d5be-124">管理安全组的所有者</span><span class="sxs-lookup"><span data-stu-id="9d5be-124">Manage the owners of a security group</span></span>

<span data-ttu-id="9d5be-125">使用这些命令显示安全组的当前所有者。</span><span class="sxs-lookup"><span data-stu-id="9d5be-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="9d5be-126">使用这些命令通过其用户主体名称将用户帐户添加 **(UPN)** 到安全组的当前所有者。</span><span class="sxs-lookup"><span data-stu-id="9d5be-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="9d5be-127">使用这些命令将用户帐户的 **显示名称** 添加到安全组的当前所有者。</span><span class="sxs-lookup"><span data-stu-id="9d5be-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="9d5be-128">使用这些命令可通过其 **UPN** 将用户帐户删除到安全组的当前所有者。</span><span class="sxs-lookup"><span data-stu-id="9d5be-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="9d5be-129">使用这些命令将用户帐户的 **显示名称** 删除到安全组的当前所有者。</span><span class="sxs-lookup"><span data-stu-id="9d5be-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="9d5be-130">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="9d5be-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="9d5be-131">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9d5be-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="9d5be-132">列出你的组</span><span class="sxs-lookup"><span data-stu-id="9d5be-132">List your groups</span></span>

<span data-ttu-id="9d5be-133">使用此命令可列出你的所有组。</span><span class="sxs-lookup"><span data-stu-id="9d5be-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="9d5be-134">使用这些命令显示特定组的显示名称的设置。</span><span class="sxs-lookup"><span data-stu-id="9d5be-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="9d5be-135">创建新组</span><span class="sxs-lookup"><span data-stu-id="9d5be-135">Create a new group</span></span>

<span data-ttu-id="9d5be-136">使用此命令创建新的安全组。</span><span class="sxs-lookup"><span data-stu-id="9d5be-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="9d5be-137">更改组上的设置</span><span class="sxs-lookup"><span data-stu-id="9d5be-137">Change the settings on a group</span></span>

<span data-ttu-id="9d5be-138">使用这些命令显示组的设置。</span><span class="sxs-lookup"><span data-stu-id="9d5be-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="9d5be-139">然后，使用 [MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) 文章来确定如何更改设置。</span><span class="sxs-lookup"><span data-stu-id="9d5be-139">Then, use the [Set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="9d5be-140">删除安全组</span><span class="sxs-lookup"><span data-stu-id="9d5be-140">Remove a security group</span></span>

<span data-ttu-id="9d5be-141">使用这些命令删除安全组。</span><span class="sxs-lookup"><span data-stu-id="9d5be-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="9d5be-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d5be-142">See also</span></span>

[<span data-ttu-id="9d5be-143">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="9d5be-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9d5be-144">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d5be-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9d5be-145">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="9d5be-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

