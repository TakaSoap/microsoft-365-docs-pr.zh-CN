---
title: 使用 PowerShell 维护 Microsoft 365 组成员身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.openlocfilehash: 61bdcb96433f4f384033768debf416900a305624
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688080"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a><span data-ttu-id="a5ac2-103">使用 PowerShell 维护 Microsoft 365 组成员身份</span><span class="sxs-lookup"><span data-stu-id="a5ac2-103">Maintain Microsoft 365 group membership with PowerShell</span></span>

<span data-ttu-id="a5ac2-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="a5ac2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a5ac2-105">您可以使用 PowerShell for Microsoft 365 作为 microsoft 365 管理中心的替代方法来维护 Microsoft 365 中的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain group membership in Microsoft 365.</span></span> 

> [!TIP]
> <span data-ttu-id="a5ac2-106">若要通过指定用户帐户和组名称生成现成的 PowerShell 命令，请使用此 [组维护 Microsoft Excel 工作簿](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-106">To generate ready-to-run PowerShell commands by specifying user account and group names, use this [group maintenance Microsoft Excel workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx).</span></span> 

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="a5ac2-107">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5ac2-107">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="a5ac2-108">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="a5ac2-109">将用户帐户添加或删除为组的成员</span><span class="sxs-lookup"><span data-stu-id="a5ac2-109">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="a5ac2-110">**若要通过其 UPN 添加用户帐户**，请填写用户帐户用户主体名称 (UPN)  (例如： belindan@contoso.com) 和组显示名称，删除 "<" 和 ">" 字符，并在 powershell 窗口或 Powershell 集成脚本环境 (ISE) 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-110">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a5ac2-111">**若要按照其显示名称添加用户帐户**，请填写用户帐户显示名称 (示例： Belinda Newman) 和组显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-111">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a5ac2-112">**若要通过其 UPN 删除用户帐户**，请填写用户帐户 upn (示例： belindan@contoso.com) 和组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-112">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a5ac2-113">**若要按其显示名称删除用户帐户**，请填写用户帐户显示名称 (示例： Belinda Newman) 和组显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-113">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="a5ac2-114">将组添加或删除为组的成员</span><span class="sxs-lookup"><span data-stu-id="a5ac2-114">Add or remove groups as members of a group</span></span>

<span data-ttu-id="a5ac2-115">安全组可以将其他组包含为成员。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-115">Security groups can contain other groups as members.</span></span> <span data-ttu-id="a5ac2-116">但是，Microsoft 365 组无法这样做。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-116">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="a5ac2-117">此部分包含 PowerShell 命令，仅用于为安全组添加或删除组。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-117">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="a5ac2-118">**若要按照其显示名称添加组**，请填写要添加的组的显示名称和将包含该成员组的组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-118">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a5ac2-119">**若要按其显示名称删除组**，请填写要删除的组的显示名称和将包含该成员组的组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-119">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a5ac2-120">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="a5ac2-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a5ac2-121">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-121">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="a5ac2-122">将用户帐户添加或删除为组的成员</span><span class="sxs-lookup"><span data-stu-id="a5ac2-122">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="a5ac2-123">**若要通过其 UPN 添加用户帐户**，请填写用户帐户用户主体名称 (UPN)  (例如： belindan@contoso.com) 和组显示名称，删除 "<" 和 ">" 字符，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-123">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a5ac2-124">**若要按照其显示名称添加用户帐户**，请填写用户帐户显示名称 (示例： Belinda Newman) 和组显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-124">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a5ac2-125">**若要通过其 UPN 删除用户帐户**，请填写用户帐户 upn (示例： belindan@contoso.com) 和组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-125">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="a5ac2-126">**若要按其显示名称删除用户帐户**，请填写用户帐户显示名称 (示例： Belinda Newman) 和组显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-126">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="a5ac2-127">将组添加或删除为组的成员</span><span class="sxs-lookup"><span data-stu-id="a5ac2-127">Add or remove groups as members of a group</span></span>

<span data-ttu-id="a5ac2-128">安全组可以将其他组包含为成员。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-128">Security groups can contain other groups as members.</span></span> <span data-ttu-id="a5ac2-129">但是，Microsoft 365 组无法这样做。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-129">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="a5ac2-130">此部分包含 PowerShell 命令，仅用于为安全组添加或删除组。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-130">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="a5ac2-131">**若要按照其显示名称添加组**，请填写要添加的组的显示名称和将包含该成员组的组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-131">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="a5ac2-132">**若要按其显示名称删除组**，请填写要删除的组的显示名称和将包含该成员组的组的显示名称，并在 powershell 窗口或 powershell ISE 中运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a5ac2-132">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="a5ac2-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5ac2-133">See also</span></span>

[<span data-ttu-id="a5ac2-134">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="a5ac2-134">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a5ac2-135">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5ac2-135">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a5ac2-136">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="a5ac2-136">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

