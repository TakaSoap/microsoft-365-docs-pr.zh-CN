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
ms.openlocfilehash: 64a02a1472fdeb0d61cfb4f380cbe61dd7b557b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909498"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="090bf-103">使用 PowerShell 管理安全组</span><span class="sxs-lookup"><span data-stu-id="090bf-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="090bf-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="090bf-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="090bf-105">可以使用 PowerShell for Microsoft 365作为管理中心管理Microsoft 365安全组的替代方法。</span><span class="sxs-lookup"><span data-stu-id="090bf-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="090bf-106">本文介绍列出、创建、更改设置和删除安全组。</span><span class="sxs-lookup"><span data-stu-id="090bf-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="090bf-107">当本文中的命令块要求您指定变量值时，请使用这些步骤。</span><span class="sxs-lookup"><span data-stu-id="090bf-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="090bf-108">将命令块复制到剪贴板并将其粘贴到 isE 记事本 或 PowerShell 集成脚本 (中) 。</span><span class="sxs-lookup"><span data-stu-id="090bf-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="090bf-109">填写变量值并删除"<"和">"字符。</span><span class="sxs-lookup"><span data-stu-id="090bf-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="090bf-110">在 PowerShell 窗口或 PowerShell ISE 中运行命令。</span><span class="sxs-lookup"><span data-stu-id="090bf-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="090bf-111">请参阅 [维护安全组成员身份](maintain-group-membership-with-microsoft-365-powershell.md) 以使用 PowerShell 管理组成员身份。</span><span class="sxs-lookup"><span data-stu-id="090bf-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="090bf-112">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="090bf-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="090bf-113">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="090bf-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="090bf-114">列出你的组</span><span class="sxs-lookup"><span data-stu-id="090bf-114">List your groups</span></span>

<span data-ttu-id="090bf-115">使用此命令列出所有组。</span><span class="sxs-lookup"><span data-stu-id="090bf-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="090bf-116">使用这些命令按特定组的组名称显示显示名称。</span><span class="sxs-lookup"><span data-stu-id="090bf-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="090bf-117">创建新组</span><span class="sxs-lookup"><span data-stu-id="090bf-117">Create a new group</span></span>

<span data-ttu-id="090bf-118">使用此命令可创建新的安全组。</span><span class="sxs-lookup"><span data-stu-id="090bf-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="090bf-119">更改组上的设置</span><span class="sxs-lookup"><span data-stu-id="090bf-119">Change the settings on a group</span></span>

<span data-ttu-id="090bf-120">使用这些命令显示组的设置。</span><span class="sxs-lookup"><span data-stu-id="090bf-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="090bf-121">然后，使用 [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) 文章确定如何更改设置。</span><span class="sxs-lookup"><span data-stu-id="090bf-121">Then, use the [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="090bf-122">删除安全组</span><span class="sxs-lookup"><span data-stu-id="090bf-122">Remove a security group</span></span>

<span data-ttu-id="090bf-123">使用这些命令删除安全组。</span><span class="sxs-lookup"><span data-stu-id="090bf-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="090bf-124">管理安全组的所有者</span><span class="sxs-lookup"><span data-stu-id="090bf-124">Manage the owners of a security group</span></span>

<span data-ttu-id="090bf-125">使用这些命令显示安全组的当前所有者。</span><span class="sxs-lookup"><span data-stu-id="090bf-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="090bf-126">使用这些命令按用户帐户的用户主体 (名称将 **UPN**) 添加到安全组的当前所有者。</span><span class="sxs-lookup"><span data-stu-id="090bf-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="090bf-127">使用这些命令按用户帐户的当前所有者显示名称用户帐户。 </span><span class="sxs-lookup"><span data-stu-id="090bf-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="090bf-128">使用这些命令，通过 **UPN** 将用户帐户删除给安全组的当前所有者。</span><span class="sxs-lookup"><span data-stu-id="090bf-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="090bf-129">使用这些命令通过向安全组的当前显示名称用户帐户删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="090bf-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="090bf-130">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="090bf-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="090bf-131">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="090bf-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="090bf-132">列出你的组</span><span class="sxs-lookup"><span data-stu-id="090bf-132">List your groups</span></span>

<span data-ttu-id="090bf-133">使用此命令列出所有组。</span><span class="sxs-lookup"><span data-stu-id="090bf-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="090bf-134">使用这些命令按特定组的组名称显示显示名称。</span><span class="sxs-lookup"><span data-stu-id="090bf-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="090bf-135">创建新组</span><span class="sxs-lookup"><span data-stu-id="090bf-135">Create a new group</span></span>

<span data-ttu-id="090bf-136">使用此命令可创建新的安全组。</span><span class="sxs-lookup"><span data-stu-id="090bf-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="090bf-137">更改组上的设置</span><span class="sxs-lookup"><span data-stu-id="090bf-137">Change the settings on a group</span></span>

<span data-ttu-id="090bf-138">使用这些命令显示组的设置。</span><span class="sxs-lookup"><span data-stu-id="090bf-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="090bf-139">然后，使用 [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) 文章确定如何更改设置。</span><span class="sxs-lookup"><span data-stu-id="090bf-139">Then, use the [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="090bf-140">删除安全组</span><span class="sxs-lookup"><span data-stu-id="090bf-140">Remove a security group</span></span>

<span data-ttu-id="090bf-141">使用这些命令删除安全组。</span><span class="sxs-lookup"><span data-stu-id="090bf-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="090bf-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="090bf-142">See also</span></span>

[<span data-ttu-id="090bf-143">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="090bf-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="090bf-144">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="090bf-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="090bf-145">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="090bf-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)