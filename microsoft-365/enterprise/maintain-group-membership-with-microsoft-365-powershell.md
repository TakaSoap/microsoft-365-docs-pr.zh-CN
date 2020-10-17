---
title: 使用 PowerShell 维护 Microsoft 365 组成员身份
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
description: 了解如何使用 PowerShell 维护 Microsoft 365 组中的成员身份。
ms.openlocfilehash: 7763f4275ff31f3dc26aa7fecba93e545f7c7644
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580970"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a><span data-ttu-id="1a140-103">使用 PowerShell 维护 Microsoft 365 组成员身份</span><span class="sxs-lookup"><span data-stu-id="1a140-103">Maintain Microsoft 365 group membership with PowerShell</span></span>

<span data-ttu-id="1a140-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="1a140-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1a140-105">您可以使用 PowerShell for Microsoft 365 作为 microsoft 365 管理中心的替代方法来维护 Microsoft 365 中的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="1a140-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="1a140-106">了解如何使用 Microsoft 365 管理中心[维护 microsoft 365 组成员身份](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)。</span><span class="sxs-lookup"><span data-stu-id="1a140-106">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="1a140-107">有关其他资源的列表，请参阅 [管理用户和组](https://docs.microsoft.com/microsoft-365/admin/add-users/)。</span><span class="sxs-lookup"><span data-stu-id="1a140-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1a140-108">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a140-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="1a140-109">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="1a140-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="1a140-110">将用户帐户添加或删除为组的成员</span><span class="sxs-lookup"><span data-stu-id="1a140-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="1a140-111">**若要通过其 UPN 添加用户帐户**，请填写用户帐户用户主体名称 (UPN)  (例如： belindan@contoso.com) 和组显示名称，删除 "<" 和 ">" 字符，并在 powershell 窗口或 Powershell 集成脚本环境 (ISE) 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1a140-112">**若要按照其显示名称添加用户帐户**，请填写用户帐户显示名称 (示例： Belinda Newman) 和组显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1a140-113">**若要通过其 UPN 删除用户帐户**，请填写用户帐户 upn (示例： belindan@contoso.com) 和组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1a140-114">**若要按其显示名称删除用户帐户**，请填写用户帐户显示名称 (示例： Belinda Newman) 和组显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="1a140-115">将组添加或删除为组的成员</span><span class="sxs-lookup"><span data-stu-id="1a140-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="1a140-116">安全组可以将其他组包含为成员。</span><span class="sxs-lookup"><span data-stu-id="1a140-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="1a140-117">但是，Microsoft 365 组无法这样做。</span><span class="sxs-lookup"><span data-stu-id="1a140-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="1a140-118">此部分包含 PowerShell 命令，仅用于为安全组添加或删除组。</span><span class="sxs-lookup"><span data-stu-id="1a140-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="1a140-119">**若要按照其显示名称添加组**，请填写要添加的组的显示名称和将包含该成员组的组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1a140-120">**若要按其显示名称删除组**，请填写要删除的组的显示名称和将包含该成员组的组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1a140-121">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="1a140-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1a140-122">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1a140-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="1a140-123">将用户帐户添加或删除为组的成员</span><span class="sxs-lookup"><span data-stu-id="1a140-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="1a140-124">**若要通过其 UPN 添加用户帐户**，请填写用户帐户用户主体名称 (UPN)  (例如： belindan@contoso.com) 和组显示名称，删除 "<" 和 ">" 字符，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1a140-125">**若要按照其显示名称添加用户帐户**，请填写用户帐户显示名称 (示例： Belinda Newman) 和组显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1a140-126">**若要通过其 UPN 删除用户帐户**，请填写用户帐户 upn (示例： belindan@contoso.com) 和组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="1a140-127">**若要按其显示名称删除用户帐户**，请填写用户帐户显示名称 (示例： Belinda Newman) 和组显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="1a140-128">将组添加或删除为组的成员</span><span class="sxs-lookup"><span data-stu-id="1a140-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="1a140-129">安全组可以将其他组包含为成员。</span><span class="sxs-lookup"><span data-stu-id="1a140-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="1a140-130">但是，Microsoft 365 组无法这样做。</span><span class="sxs-lookup"><span data-stu-id="1a140-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="1a140-131">此部分包含 PowerShell 命令，仅用于为安全组添加或删除组。</span><span class="sxs-lookup"><span data-stu-id="1a140-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="1a140-132">**若要按照其显示名称添加组**，请填写要添加的组的显示名称和将包含该成员组的组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="1a140-133">**若要按其显示名称删除组**，请填写要删除的组的显示名称和将包含该成员组的组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="1a140-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="1a140-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a140-134">See also</span></span>

[<span data-ttu-id="1a140-135">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="1a140-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1a140-136">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a140-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1a140-137">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="1a140-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

