---
title: 使用 PowerShell 维护安全组成员身份
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: 了解如何使用 PowerShell 维护组Microsoft 365成员身份。
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909570"
---
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="f1f47-103">使用 PowerShell 维护安全组成员身份</span><span class="sxs-lookup"><span data-stu-id="f1f47-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="f1f47-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="f1f47-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f1f47-105">可以使用 PowerShell for Microsoft 365作为管理中心Microsoft 365维护安全组成员身份的Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="f1f47-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="f1f47-106">[了解如何使用Microsoft 365中心维护](../admin/create-groups/add-or-remove-members-from-groups.md)Microsoft 365成员身份。</span><span class="sxs-lookup"><span data-stu-id="f1f47-106">[Learn how to maintain Microsoft 365 group membership](../admin/create-groups/add-or-remove-members-from-groups.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="f1f47-107">有关其他资源的列表，请参阅管理 [用户和组](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="f1f47-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f1f47-108">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1f47-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="f1f47-109">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="f1f47-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="f1f47-110">添加或删除用户帐户作为组的成员</span><span class="sxs-lookup"><span data-stu-id="f1f47-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="f1f47-111">若要按用户帐户 **的 UPN** 添加用户帐户，请填写用户帐户用户主体名称 (UPN)  (示例：belindan@contoso.com) 和安全组 显示名称，删除"<"和">"字符，在 PowerShell 窗口或 PowerShell 集成脚本环境 (ISE) 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="f1f47-112">若要按用户帐户的 **显示名称** 添加用户帐户，请填写用户帐户 显示名称 (示例：Belinda Newman) 和组 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="f1f47-113">若要通过 UPN 删除用户帐户，请填写用户帐户 **UPN** (示例：belindan@contoso.com) 和组 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="f1f47-114">若要通过用户帐户的 **显示名称** 删除用户帐户，请填写用户帐户 显示名称 (示例：Belinda Newman) 和组 显示名称在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="f1f47-115">添加或删除组作为组的成员</span><span class="sxs-lookup"><span data-stu-id="f1f47-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="f1f47-116">安全组可以包含其他组作为成员。</span><span class="sxs-lookup"><span data-stu-id="f1f47-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="f1f47-117">Microsoft 365组，但不能。</span><span class="sxs-lookup"><span data-stu-id="f1f47-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="f1f47-118">本节包含 PowerShell 命令，用于仅为安全组添加或删除组。</span><span class="sxs-lookup"><span data-stu-id="f1f47-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="f1f47-119">若要按组的 **显示名称** 添加组，请填写要添加的组的 显示名称 和将包含成员组的组的 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="f1f47-120">若要通过 显示名称 删除组，请填写要删除的组的 显示名称 以及将包含成员组的组的 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f1f47-121">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="f1f47-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f1f47-122">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f1f47-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="f1f47-123">添加或删除用户帐户作为组的成员</span><span class="sxs-lookup"><span data-stu-id="f1f47-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="f1f47-124">若要按用户帐户 **的 UPN** 添加用户帐户，请填写用户帐户用户主体名称 (UPN)  (示例：belindan@contoso.com) 和组 显示名称，删除"<"和">"字符，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="f1f47-125">若要按用户帐户的 **显示名称** 添加用户帐户，请填写用户帐户 显示名称 (示例：Belinda Newman) 和组 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="f1f47-126">若要通过 UPN 删除用户帐户，请填写用户帐户 **UPN** (示例：belindan@contoso.com) 和组 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="f1f47-127">若要通过用户帐户的 **显示名称** 删除用户帐户，请填写用户帐户 显示名称 (示例：Belinda Newman) 和组 显示名称在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="f1f47-128">添加或删除组作为组的成员</span><span class="sxs-lookup"><span data-stu-id="f1f47-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="f1f47-129">安全组可以包含其他组作为成员。</span><span class="sxs-lookup"><span data-stu-id="f1f47-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="f1f47-130">Microsoft 365组，但不能。</span><span class="sxs-lookup"><span data-stu-id="f1f47-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="f1f47-131">本节包含 PowerShell 命令，用于仅为安全组添加或删除组。</span><span class="sxs-lookup"><span data-stu-id="f1f47-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="f1f47-132">若要按组的 **显示名称** 添加组，请填写要添加的组的 显示名称 和将包含成员组的组的 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="f1f47-133">若要通过 显示名称 删除组，请填写要删除的组的 显示名称 以及将包含成员组的组的 显示名称，在 PowerShell 窗口或 PowerShell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="f1f47-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="f1f47-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1f47-134">See also</span></span>

[<span data-ttu-id="f1f47-135">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="f1f47-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f1f47-136">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1f47-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f1f47-137">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="f1f47-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)