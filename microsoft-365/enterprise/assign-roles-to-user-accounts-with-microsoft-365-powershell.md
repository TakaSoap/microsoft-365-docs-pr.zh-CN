---
title: 使用 PowerShell 向 Microsoft 365 用户帐户分配角色
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
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: 本文将了解如何快速轻松地使用适用于 Microsoft 365 的 PowerShell 将管理员角色分配给用户帐户。
ms.openlocfilehash: 84e785052c970ca15487540c3904eacdd0e9ca28
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905376"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="315d1-103">使用 PowerShell 将管理员角色分配给 Microsoft 365 用户帐户</span><span class="sxs-lookup"><span data-stu-id="315d1-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="315d1-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="315d1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="315d1-105">通过使用适用于 Microsoft 365 的 PowerShell，可以轻松地将角色分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="315d1-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="315d1-106">了解如何  [使用](../admin/add-users/assign-admin-roles.md) Microsoft 365 管理中心向用户帐户分配管理员角色。</span><span class="sxs-lookup"><span data-stu-id="315d1-106">Learn how to  [assign admin roles](../admin/add-users/assign-admin-roles.md) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="315d1-107">有关其他资源的列表，请参阅管理 [用户和组](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="315d1-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="315d1-108">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="315d1-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="315d1-109">首先，使用全局管理员帐户连接到 [Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="315d1-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="315d1-110">接下来，确定要添加到角色角色中的用户帐户的登录名 (示例：fredsm \@ contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="315d1-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="315d1-111">这也称为 UPN (用户主体) 。</span><span class="sxs-lookup"><span data-stu-id="315d1-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="315d1-112">接下来，确定角色的名称。</span><span class="sxs-lookup"><span data-stu-id="315d1-112">Next, determine the name of the role.</span></span> <span data-ttu-id="315d1-113">请参阅 [Azure Active Directory 中的管理员角色权限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="315d1-113">See [administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="315d1-114">请注意本文中的说明。</span><span class="sxs-lookup"><span data-stu-id="315d1-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="315d1-115">某些角色名称对于 Azure Active Directory (Azure AD) PowerShell 有所不同。</span><span class="sxs-lookup"><span data-stu-id="315d1-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="315d1-116">例如，Microsoft 365 管理中心中的 *SharePoint* 管理员角色是 Azure AD PowerShell 中的 *SharePoint* 服务管理员。</span><span class="sxs-lookup"><span data-stu-id="315d1-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="315d1-117">接下来，填写登录名和角色名称并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="315d1-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="315d1-118">下面是一个完成的命令集示例，该命令集将 SharePoint 服务管理员角色分配给 *belindan \@ contoso.com* 帐户：</span><span class="sxs-lookup"><span data-stu-id="315d1-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="315d1-119">若要显示特定管理员角色的用户名列表，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="315d1-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="315d1-120">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="315d1-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="315d1-121">首先，使用全局管理员帐户连接到 [Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="315d1-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="315d1-122">对于单个角色更改</span><span class="sxs-lookup"><span data-stu-id="315d1-122">For a single role change</span></span>

<span data-ttu-id="315d1-123">指定用户帐户的最常见方法就是使用其 显示名称 或电子邮件名称（也称为登录名或用户主体名称 (UPN) ）。</span><span class="sxs-lookup"><span data-stu-id="315d1-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="315d1-124">显示用户帐户的名称</span><span class="sxs-lookup"><span data-stu-id="315d1-124">Display names of user accounts</span></span>

<span data-ttu-id="315d1-125">如果您习惯使用用户帐户的显示名称，请确定以下信息：</span><span class="sxs-lookup"><span data-stu-id="315d1-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="315d1-126">要配置的用户帐户</span><span class="sxs-lookup"><span data-stu-id="315d1-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="315d1-127">若要指定用户帐户，您必须确定其显示名称。</span><span class="sxs-lookup"><span data-stu-id="315d1-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="315d1-128">若要获取帐户的完整列表，请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="315d1-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="315d1-129">此命令列出用户帐户的显示名称，按显示名称排序，一次显示一个屏幕。</span><span class="sxs-lookup"><span data-stu-id="315d1-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="315d1-130">可以使用 Where cmdlet 将列表筛选为较小的集合。</span><span class="sxs-lookup"><span data-stu-id="315d1-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="315d1-131">请参阅以下示例。</span><span class="sxs-lookup"><span data-stu-id="315d1-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="315d1-132">PowerShell Core 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="315d1-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="315d1-133">从 Windows PowerShell 运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="315d1-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="315d1-134">此命令仅列出显示名称以"John"开头的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="315d1-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="315d1-135">要分配的角色</span><span class="sxs-lookup"><span data-stu-id="315d1-135">The role you want to assign</span></span>
    
    <span data-ttu-id="315d1-136">若要显示可分配给用户帐户的可用管理员角色列表，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="315d1-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="315d1-137">确定帐户的显示名称和角色名称后，请使用以下命令将角色分配给该帐户：</span><span class="sxs-lookup"><span data-stu-id="315d1-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="315d1-138">将命令粘贴到记事本中。</span><span class="sxs-lookup"><span data-stu-id="315d1-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="315d1-139">对于 *$dispName* 和 *$roleName，* 请将说明文本替换为其值。</span><span class="sxs-lookup"><span data-stu-id="315d1-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="315d1-140">删除 \< and > 字符，但保留引号。</span><span class="sxs-lookup"><span data-stu-id="315d1-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="315d1-141">将修改的行粘贴到 Microsoft Azure Active Directory 模块中，Windows PowerShell运行这些行。</span><span class="sxs-lookup"><span data-stu-id="315d1-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="315d1-142">或者，您可以使用 ISE Windows PowerShell集成脚本 (脚本) 。</span><span class="sxs-lookup"><span data-stu-id="315d1-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="315d1-143">下面是已完成的命令集的示例：</span><span class="sxs-lookup"><span data-stu-id="315d1-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="315d1-144">用户帐户的登录名</span><span class="sxs-lookup"><span data-stu-id="315d1-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="315d1-145">如果您习惯使用用户帐户的登录名或 UPN，请确定以下信息：</span><span class="sxs-lookup"><span data-stu-id="315d1-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="315d1-146">用户帐户的 UPN</span><span class="sxs-lookup"><span data-stu-id="315d1-146">The user account's UPN</span></span>
    
    <span data-ttu-id="315d1-147">如果您不知道 UPN，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="315d1-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="315d1-148">此命令将列出用户帐户的 UPN，按 UPN 排序，一次列出一个屏幕。</span><span class="sxs-lookup"><span data-stu-id="315d1-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="315d1-149">可以使用 Where **cmdlet** 筛选列表。</span><span class="sxs-lookup"><span data-stu-id="315d1-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="315d1-150">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="315d1-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="315d1-151">此命令仅列出显示名称以"John"开头的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="315d1-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="315d1-152">要分配的角色</span><span class="sxs-lookup"><span data-stu-id="315d1-152">The role you want to assign</span></span>
    
    <span data-ttu-id="315d1-153">若要显示可分配给用户帐户的可用角色列表，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="315d1-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="315d1-154">拥有帐户的 UPN 和角色名称后，请使用以下命令将角色分配给帐户：</span><span class="sxs-lookup"><span data-stu-id="315d1-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="315d1-155">复制命令并将其粘贴到记事本中。</span><span class="sxs-lookup"><span data-stu-id="315d1-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="315d1-156">对于 **$upnName** 和 **$roleName** 变量。</span><span class="sxs-lookup"><span data-stu-id="315d1-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="315d1-157">将说明文本替换为其值。</span><span class="sxs-lookup"><span data-stu-id="315d1-157">Replace the description text with their values.</span></span> <span data-ttu-id="315d1-158">删除 \< and > 字符，但保留引号。</span><span class="sxs-lookup"><span data-stu-id="315d1-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="315d1-159">将修改的行粘贴到 Microsoft Azure Active Directory 模块Windows PowerShell窗口运行它们。</span><span class="sxs-lookup"><span data-stu-id="315d1-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="315d1-160">或者，可以使用 ISE Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="315d1-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="315d1-161">下面是已完成的命令集的示例：</span><span class="sxs-lookup"><span data-stu-id="315d1-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="315d1-162">多个角色更改</span><span class="sxs-lookup"><span data-stu-id="315d1-162">Multiple role changes</span></span>

<span data-ttu-id="315d1-163">对于多个角色更改，请确定以下信息：</span><span class="sxs-lookup"><span data-stu-id="315d1-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="315d1-164">要配置哪些用户帐户。</span><span class="sxs-lookup"><span data-stu-id="315d1-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="315d1-165">可以使用上一节中的方法收集一组显示名称或 UPN。</span><span class="sxs-lookup"><span data-stu-id="315d1-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="315d1-166">要分配给每个用户帐户的角色。</span><span class="sxs-lookup"><span data-stu-id="315d1-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="315d1-167">若要显示可分配给用户帐户的可用角色列表，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="315d1-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="315d1-168">接下来，使用 CSV (或) 名称字段的 CSV 显示名称创建一个逗号分隔值。</span><span class="sxs-lookup"><span data-stu-id="315d1-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="315d1-169">可以在 Microsoft Excel 中轻松完成此操作。</span><span class="sxs-lookup"><span data-stu-id="315d1-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="315d1-170">下面是显示名称的示例：</span><span class="sxs-lookup"><span data-stu-id="315d1-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="315d1-171">接下来，填写 CSV 文件的位置，在 PowerShell 命令提示符处运行生成的命令。</span><span class="sxs-lookup"><span data-stu-id="315d1-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="315d1-172">下面是 UPN 的示例：</span><span class="sxs-lookup"><span data-stu-id="315d1-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="315d1-173">接下来，填写 CSV 文件的位置，在 PowerShell 命令提示符处运行生成的命令。</span><span class="sxs-lookup"><span data-stu-id="315d1-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="315d1-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="315d1-174">See also</span></span>

- [<span data-ttu-id="315d1-175">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="315d1-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="315d1-176">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="315d1-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="315d1-177">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="315d1-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)