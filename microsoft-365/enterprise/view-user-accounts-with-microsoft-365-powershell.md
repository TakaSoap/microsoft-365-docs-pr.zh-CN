---
title: 使用 PowerShell Microsoft 365用户帐户
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: 了解如何使用 PowerShell 以不同方式查看、Microsoft 365或显示用户帐户。
ms.openlocfilehash: de91195afeb8480bf231d9536e4b3a94502a6da1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924644"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="89cb4-103">使用 PowerShell Microsoft 365用户帐户</span><span class="sxs-lookup"><span data-stu-id="89cb4-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="89cb4-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="89cb4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="89cb4-105">可以使用管理Microsoft 365查看你的租户Microsoft 365帐户。</span><span class="sxs-lookup"><span data-stu-id="89cb4-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="89cb4-106">PowerShell for Microsoft 365可实现此功能，但也提供了其他功能。</span><span class="sxs-lookup"><span data-stu-id="89cb4-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="89cb4-107">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="89cb4-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="89cb4-108">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="89cb4-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="89cb4-109">查看所有帐户</span><span class="sxs-lookup"><span data-stu-id="89cb4-109">View all accounts</span></span>

<span data-ttu-id="89cb4-110">若要显示用户帐户的完整列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89cb4-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="89cb4-111">应获取与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="89cb4-111">You should get information similar to this:</span></span>
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a><span data-ttu-id="89cb4-112">查看特定帐户</span><span class="sxs-lookup"><span data-stu-id="89cb4-112">View a specific account</span></span>

<span data-ttu-id="89cb4-113">若要显示特定用户帐户，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="89cb4-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="89cb4-114">填写用户帐户的登录帐户名称，也称为 UPN (用户) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="89cb4-115">删除"<"和">"字符。</span><span class="sxs-lookup"><span data-stu-id="89cb4-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="89cb4-116">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="89cb4-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="89cb4-117">查看特定帐户的其他属性值</span><span class="sxs-lookup"><span data-stu-id="89cb4-117">View additional property values for a specific account</span></span>

<span data-ttu-id="89cb4-118">默认情况下 **，Get-AzureADUser** cmdlet 仅显示帐户的 *ObjectID、DisplayName* 和 *UserPrincipalName* 属性。 </span><span class="sxs-lookup"><span data-stu-id="89cb4-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="89cb4-119">若要对要显示的属性更具选择性，请结合使用 **Select** cmdlet 和 **Get-AzureADUser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="89cb4-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="89cb4-120">若要组合这两个 cmdlet，请使用"pipe"字符 ("|") ，指示 Azure Active Directory PowerShell Graph接受一个命令的结果并将其发送到下一个命令。</span><span class="sxs-lookup"><span data-stu-id="89cb4-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="89cb4-121">下面是显示每个用户帐户的 *DisplayName、Department* 和 *UsageLocation* 的示例命令：</span><span class="sxs-lookup"><span data-stu-id="89cb4-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="89cb4-122">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="89cb4-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="89cb4-123">获取 **Get-AzureADUser** (用户帐户) 并将其发送到下一个 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="89cb4-124">仅显示用户帐户名、部门以及使用情况位置 (**选择 DisplayName、Department、UsageLocation**) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="89cb4-125">To see all the properties for a specific user account， use the **Select** cmdlet and the wildcard character (\*) .</span><span class="sxs-lookup"><span data-stu-id="89cb4-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="89cb4-126">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="89cb4-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="89cb4-127">再如，运行以下命令以检查特定用户帐户的启用状态：</span><span class="sxs-lookup"><span data-stu-id="89cb4-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="89cb4-128">查看帐户同步状态</span><span class="sxs-lookup"><span data-stu-id="89cb4-128">View account synchronization status</span></span>

<span data-ttu-id="89cb4-129">用户帐户有两个来源：</span><span class="sxs-lookup"><span data-stu-id="89cb4-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="89cb4-130">Windows服务器 Active Directory (AD) ，即从本地 AD 同步到云的帐户。</span><span class="sxs-lookup"><span data-stu-id="89cb4-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="89cb4-131">Azure Active Directory (Azure AD) AD 帐户，这些帐户直接在云中创建。</span><span class="sxs-lookup"><span data-stu-id="89cb4-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="89cb4-132">以下命令指示 PowerShell 获取属性 *DirSyncEnabled* 设置为 True 的 *所有用户*。</span><span class="sxs-lookup"><span data-stu-id="89cb4-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="89cb4-133">可以使用它查找正在从本地 AD 同步的帐户。</span><span class="sxs-lookup"><span data-stu-id="89cb4-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="89cb4-134">以下命令指示 PowerShell 获取属性 *DirSyncEnabled* 设置为 False 的 *所有用户*。</span><span class="sxs-lookup"><span data-stu-id="89cb4-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="89cb4-135">可以使用它查找仅云帐户。</span><span class="sxs-lookup"><span data-stu-id="89cb4-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="89cb4-136">查看基于通用属性的帐户</span><span class="sxs-lookup"><span data-stu-id="89cb4-136">View accounts based on a common property</span></span>

<span data-ttu-id="89cb4-137">若要对要显示的帐户列表更具选择性，可以将 **Where** cmdlet 与 **Get-AzureADUser** cmdlet 结合使用。</span><span class="sxs-lookup"><span data-stu-id="89cb4-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="89cb4-138">若要组合这两个 cmdlet，请使用"pipe"字符 ("|") ，指示 Azure Active Directory PowerShell Graph接受一个命令的结果并将其发送到下一个命令。</span><span class="sxs-lookup"><span data-stu-id="89cb4-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="89cb4-139">下面是一个示例命令，该命令仅显示未指定使用位置的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="89cb4-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="89cb4-140">此命令指示Azure Active Directory PowerShell Graph：</span><span class="sxs-lookup"><span data-stu-id="89cb4-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="89cb4-141">获取 **Get-AzureADUser** (用户帐户) 并将其发送到下一个 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="89cb4-142">在 Where {$ 中查找未指定使用位置 (**用户帐户 \_ 。UsageLocation -eq $Null}**) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="89cb4-143">在大括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性所针对的帐户 **$ \_ (。UsageLocation**) 未指定 -eq (**-eq** $Null) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="89cb4-144">**UsageLocation** 属性只是与用户帐户关联的众多属性之一。</span><span class="sxs-lookup"><span data-stu-id="89cb4-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="89cb4-145">若要显示特定用户帐户的所有属性，请使用 **Select** cmdlet 和通配符 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="89cb4-146">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="89cb4-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="89cb4-147">例如 **，City** 是用户帐户属性的名称。</span><span class="sxs-lookup"><span data-stu-id="89cb4-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="89cb4-148">可以使用以下命令列出居住在伦敦的用户的所有帐户：</span><span class="sxs-lookup"><span data-stu-id="89cb4-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="89cb4-149">这些示例中 **Where** cmdlet 的语法为 **Where {$ \_ 。**</span><span class="sxs-lookup"><span data-stu-id="89cb4-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="89cb4-150">[用户帐户属性名称][比较运算符][value] **}**.> [comparison operator] is **-eq** for equals， **-ne** for not equals， **-lt** for less than， **-gt** for greater than， and others.</span><span class="sxs-lookup"><span data-stu-id="89cb4-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="89cb4-151">[value] 通常是一个字符串， (字母、数字和其他字符序列、) 、数字值 **$Null未指定。**</span><span class="sxs-lookup"><span data-stu-id="89cb4-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="89cb4-152">有关详细信息，请参阅 [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="89cb4-152">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="89cb4-153">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="89cb4-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="89cb4-154">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="89cb4-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="89cb4-155">查看所有帐户</span><span class="sxs-lookup"><span data-stu-id="89cb4-155">View all accounts</span></span>

<span data-ttu-id="89cb4-156">若要显示用户帐户的完整列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89cb4-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="89cb4-157">PowerShell Core 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="89cb4-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="89cb4-158">从 Windows PowerShell 运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="89cb4-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="89cb4-159">应获取与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="89cb4-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="89cb4-160">**Get-MsolUser** cmdlet 也有一组参数可用于筛选显示的用户帐户组。</span><span class="sxs-lookup"><span data-stu-id="89cb4-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="89cb4-161">例如，对于未授权用户列表 (已添加到 Microsoft 365但尚未获得使用任一服务许可证) ，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89cb4-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="89cb4-162">应获取与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="89cb4-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="89cb4-163">有关用于筛选显示的用户帐户集的其他参数的信息，请参阅 [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="89cb4-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="89cb4-164">查看特定帐户</span><span class="sxs-lookup"><span data-stu-id="89cb4-164">View a specific account</span></span>

<span data-ttu-id="89cb4-165">若要显示特定用户帐户，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="89cb4-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="89cb4-166">填写用户帐户的登录名，也称为 UPN (用户) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="89cb4-167">删除"<"和">"字符。</span><span class="sxs-lookup"><span data-stu-id="89cb4-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="89cb4-168">查看基于通用属性的帐户</span><span class="sxs-lookup"><span data-stu-id="89cb4-168">View accounts based on a common property</span></span>

<span data-ttu-id="89cb4-169">若要对要显示的帐户列表更具选择性，可以将 **Where** cmdlet 与 **Get-MsolUser** cmdlet 结合使用。</span><span class="sxs-lookup"><span data-stu-id="89cb4-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="89cb4-170">若要组合这两个 cmdlet，请使用"pipe"字符 ("|") ，指示 PowerShell 接受一个命令的结果并将其发送到下一个命令。</span><span class="sxs-lookup"><span data-stu-id="89cb4-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="89cb4-171">下面的示例仅显示未指定使用位置的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="89cb4-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="89cb4-172">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="89cb4-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="89cb4-173">获取 **Get-MsolUser** (用户帐户) 并将其发送到下一个 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="89cb4-174">在 Where {$ 中查找未指定使用位置 (**用户帐户 \_ 。UsageLocation -eq $Null}**) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="89cb4-175">在括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性所针对的帐户 **$ \_ (。UsageLocation**) 未指定 -eq (**-eq** $Null) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="89cb4-176">应获取与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="89cb4-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="89cb4-177">*UsageLocation* 属性只是与用户帐户关联的众多属性之一。</span><span class="sxs-lookup"><span data-stu-id="89cb4-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="89cb4-178">To see all the properties for user accounts， use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span><span class="sxs-lookup"><span data-stu-id="89cb4-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="89cb4-179">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="89cb4-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="89cb4-180">例如 *，City* 是用户帐户属性的名称。</span><span class="sxs-lookup"><span data-stu-id="89cb4-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="89cb4-181">可以使用以下命令列出居住在伦敦的用户的所有用户帐户：</span><span class="sxs-lookup"><span data-stu-id="89cb4-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="89cb4-182">这些示例中 **Where** cmdlet 的语法为 **Where {$ \_ 。**</span><span class="sxs-lookup"><span data-stu-id="89cb4-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="89cb4-183">[用户帐户属性名称][比较运算符][value] **}**.</span><span class="sxs-lookup"><span data-stu-id="89cb4-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="89cb4-184">[comparison operator] is **-eq** for equals， **-ne** for not equals， **-lt** for less than， **-gt** for greater than， and others.</span><span class="sxs-lookup"><span data-stu-id="89cb4-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="89cb4-185">[value] 通常是一个字符串， (字母、数字和其他字符序列、) 、数字值 **$Null未指定。**</span><span class="sxs-lookup"><span data-stu-id="89cb4-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="89cb4-186">有关详细信息，请参阅 [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="89cb4-186">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="89cb4-187">若要检查用户帐户的阻止状态，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="89cb4-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="89cb4-188">查看帐户的其他属性值</span><span class="sxs-lookup"><span data-stu-id="89cb4-188">View additional property values for accounts</span></span>

<span data-ttu-id="89cb4-189">默认情况下 **，Get-MsolUser** cmdlet 显示用户帐户的以下三个属性：</span><span class="sxs-lookup"><span data-stu-id="89cb4-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="89cb4-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="89cb4-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="89cb4-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="89cb4-191">DisplayName</span></span>
    
- <span data-ttu-id="89cb4-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="89cb4-192">isLicensed</span></span>
    
<span data-ttu-id="89cb4-193">如果您需要其他属性（如用户工作部门以及他们使用 Microsoft 365 服务的国家/地区），您可以结合 **Select** cmdlet 运行 **Get-MsolUser** 以指定用户帐户属性列表。</span><span class="sxs-lookup"><span data-stu-id="89cb4-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="89cb4-194">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="89cb4-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="89cb4-195">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="89cb4-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="89cb4-196">获取 **Get-MsolUser** (用户帐户的所有信息) 并将其发送到下一个 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="89cb4-197">仅显示用户帐户名、部门以及使用情况位置 (**选择 DisplayName、Department、UsageLocation**) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="89cb4-198">应获取与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="89cb4-198">You should get information similar to this:</span></span>
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

<span data-ttu-id="89cb4-199">Select  cmdlet 允许您选择要显示的属性。</span><span class="sxs-lookup"><span data-stu-id="89cb4-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="89cb4-200">若要显示特定用户帐户的所有属性，请使用通配符 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="89cb4-201">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="89cb4-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="89cb4-202">若要对要显示的帐户列表进行更多选择，您还可以使用 **Where** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="89cb4-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="89cb4-203">下面是一个示例命令，该命令仅显示未指定使用位置的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="89cb4-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="89cb4-204">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="89cb4-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="89cb4-205">获取 **Get-MsolUser** (用户帐户的所有信息) 并将其发送到下一个 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="89cb4-206">在 Where {$ 中查找未指定使用位置 (**用户帐户 \_ 。UsageLocation -eq $Null}**) ，并将结果信息发送到下一个命令 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="89cb4-207">在大括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性所针对的帐户 **$ \_ (。UsageLocation**) 未指定 -eq (**-eq** $Null) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="89cb4-208">仅显示用户帐户名、部门以及使用情况位置 (**选择 DisplayName、Department、UsageLocation**) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="89cb4-209">应获取与以下类似的信息：</span><span class="sxs-lookup"><span data-stu-id="89cb4-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="89cb4-210">如果要使用目录同步创建和管理 Microsoft 365 用户，可以显示已从其中Microsoft 365用户的本地帐户。</span><span class="sxs-lookup"><span data-stu-id="89cb4-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="89cb4-211">以下示例假定：</span><span class="sxs-lookup"><span data-stu-id="89cb4-211">The following example assumes that:</span></span>

- <span data-ttu-id="89cb4-212">Azure AD 连接配置为使用 ObjectGUID 的默认源定位标记。</span><span class="sxs-lookup"><span data-stu-id="89cb4-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="89cb4-213"> (有关配置源定位标记的信息，请参阅[Azure AD 连接：设计概](/azure/active-directory/hybrid/plan-connect-design-concepts)念) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="89cb4-214">已安装用于 PowerShell 的 Active Directory 域服务模块 ([RSAT 工具](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)) 。</span><span class="sxs-lookup"><span data-stu-id="89cb4-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="89cb4-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89cb4-215">See also</span></span>

[<span data-ttu-id="89cb4-216">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="89cb4-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="89cb4-217">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89cb4-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="89cb4-218">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="89cb4-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)