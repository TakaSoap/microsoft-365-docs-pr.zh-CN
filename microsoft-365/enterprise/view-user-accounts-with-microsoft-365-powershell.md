---
title: 使用 PowerShell 查看 Microsoft 365 用户帐户
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
description: 了解如何使用 PowerShell 以不同方式查看、列出或显示 Microsoft 365 用户帐户。
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754068"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="fca65-103">使用 PowerShell 查看 Microsoft 365 用户帐户</span><span class="sxs-lookup"><span data-stu-id="fca65-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="fca65-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="fca65-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fca65-105">您可以使用 Microsoft 365 管理中心来查看您的 Microsoft 365 租户的帐户。</span><span class="sxs-lookup"><span data-stu-id="fca65-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="fca65-106">PowerShell for Microsoft 365 启用此功能，但还提供其他功能。</span><span class="sxs-lookup"><span data-stu-id="fca65-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="fca65-107">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="fca65-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="fca65-108">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="fca65-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="fca65-109">查看所有帐户</span><span class="sxs-lookup"><span data-stu-id="fca65-109">View all accounts</span></span>

<span data-ttu-id="fca65-110">若要显示用户帐户的完整列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fca65-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="fca65-111">应获取与以下内容类似的信息：</span><span class="sxs-lookup"><span data-stu-id="fca65-111">You should get information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="fca65-112">查看特定帐户</span><span class="sxs-lookup"><span data-stu-id="fca65-112">View a specific account</span></span>

<span data-ttu-id="fca65-113">若要显示特定的用户帐户，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="fca65-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="fca65-114">填写用户帐户的登录帐户名，该帐户也称为用户主体名称 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="fca65-115">删除 "<" 和 ">" 字符。</span><span class="sxs-lookup"><span data-stu-id="fca65-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="fca65-116">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="fca65-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="fca65-117">查看特定帐户的其他属性值</span><span class="sxs-lookup"><span data-stu-id="fca65-117">View additional property values for a specific account</span></span>

<span data-ttu-id="fca65-118">默认情况下， **AzureADUser** cmdlet 仅显示帐户的 *ObjectID*、 *DisplayName*和 *UserPrincipalName* 属性。</span><span class="sxs-lookup"><span data-stu-id="fca65-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="fca65-119">若要更好地选择要显示的属性，请结合使用 **Select** Cmdlet 和 **AzureADUser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fca65-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="fca65-120">若要组合这两个 cmdlet，请使用 "管道" 字符 ( "|") ，它指示 Azure Active Directory PowerShell for Graph 获取一个命令的结果，并将其发送到下一个命令。</span><span class="sxs-lookup"><span data-stu-id="fca65-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="fca65-121">下面的命令示例显示了每个用户帐户的 *DisplayName*、 *部门*和 *UsageLocation* ：</span><span class="sxs-lookup"><span data-stu-id="fca65-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="fca65-122">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="fca65-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="fca65-123">获取用户帐户 (**AzureADUser**) 的所有信息，并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="fca65-124">仅显示用户帐户名称、部门和使用位置 (**选择 "DisplayName"、"部门"、"UsageLocation"**) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="fca65-125">若要查看特定用户帐户的所有属性，请使用 **Select** cmdlet 和通配符 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="fca65-126">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="fca65-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="fca65-127">作为另一个示例，请运行以下命令以检查特定用户帐户的启用状态：</span><span class="sxs-lookup"><span data-stu-id="fca65-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="fca65-128">查看帐户同步状态</span><span class="sxs-lookup"><span data-stu-id="fca65-128">View account synchronization status</span></span>

<span data-ttu-id="fca65-129">用户帐户有两个源：</span><span class="sxs-lookup"><span data-stu-id="fca65-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="fca65-130">Windows Server Active Directory (AD) ，它是从本地 AD 同步到云的帐户。</span><span class="sxs-lookup"><span data-stu-id="fca65-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="fca65-131">Azure Active Directory (Azure AD) AD 帐户，这些帐户是直接在云中创建的。</span><span class="sxs-lookup"><span data-stu-id="fca65-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="fca65-132">以下命令指示 PowerShell 获取属性 *DirSyncEnabled* 设置为 *True*的所有用户。</span><span class="sxs-lookup"><span data-stu-id="fca65-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="fca65-133">您可以使用它来查找与内部部署 AD 同步的帐户。</span><span class="sxs-lookup"><span data-stu-id="fca65-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="fca65-134">以下命令指示 PowerShell 获取属性 *DirSyncEnabled* 设置为 *False*的所有用户。</span><span class="sxs-lookup"><span data-stu-id="fca65-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="fca65-135">您可以使用它查找仅云帐户。</span><span class="sxs-lookup"><span data-stu-id="fca65-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="fca65-136">基于通用属性查看帐户</span><span class="sxs-lookup"><span data-stu-id="fca65-136">View accounts based on a common property</span></span>

<span data-ttu-id="fca65-137">若要更好地选择要显示的帐户列表，可以结合使用 **Where** Cmdlet 和 **AzureADUser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fca65-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="fca65-138">若要组合这两个 cmdlet，请使用 "管道" 字符 ( "|") ，它指示 Azure Active Directory PowerShell for Graph 获取一个命令的结果，并将其发送到下一个命令。</span><span class="sxs-lookup"><span data-stu-id="fca65-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="fca65-139">下面的示例命令仅显示具有未指定的使用位置的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="fca65-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="fca65-140">此命令将 Azure Active Directory PowerShell for Graph 指示为：</span><span class="sxs-lookup"><span data-stu-id="fca65-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="fca65-141">获取用户帐户 (**AzureADUser**) 的所有信息，并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fca65-142">查找未指定使用位置 (的所有用户帐户 **{$ \_ 。UsageLocation-eq $Null}**) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="fca65-143">在大括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性 (的帐户集\*\* $ \_ 。\*\* 未 (**-eq $Null**) 指定 UsageLocation) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="fca65-144">**UsageLocation**属性只是与用户帐户关联的很多属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="fca65-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="fca65-145">若要显示特定用户帐户的所有属性，请使用 **Select** cmdlet 和通配符 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="fca65-146">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="fca65-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="fca65-147">例如， **City** 是用户帐户属性的名称。</span><span class="sxs-lookup"><span data-stu-id="fca65-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="fca65-148">您可以使用以下命令列出居住在伦敦的用户的所有帐户：</span><span class="sxs-lookup"><span data-stu-id="fca65-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="fca65-149">在这些示例中， **where** cmdlet 的语法为 **{$ \_ 。**</span><span class="sxs-lookup"><span data-stu-id="fca65-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="fca65-150">[用户帐户属性名称][比较运算符]增值 **}**. > [比较运算符] 为 **-eq** for equals， **-ne** 不等于， **-lt** 表示小于， **-gt** 表示大于，其他。</span><span class="sxs-lookup"><span data-stu-id="fca65-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="fca65-151">[value] 通常是一个字符串， (字母、数字和其他字符的序列) 、数字值或未指定的 **$Null** 。</span><span class="sxs-lookup"><span data-stu-id="fca65-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="fca65-152">有关详细信息，请参阅 [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="fca65-152">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="fca65-153">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="fca65-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="fca65-154">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="fca65-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="fca65-155">查看所有帐户</span><span class="sxs-lookup"><span data-stu-id="fca65-155">View all accounts</span></span>

<span data-ttu-id="fca65-156">若要显示用户帐户的完整列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fca65-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="fca65-157">PowerShell Core 不支持 Windows PowerShell 模块的 Microsoft Azure Active Directory 模块以及在其名称中带有 *Msol* 的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fca65-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="fca65-158">从 Windows PowerShell 运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fca65-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="fca65-159">应获取与以下内容类似的信息：</span><span class="sxs-lookup"><span data-stu-id="fca65-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="fca65-160">**Get-MsolUser** cmdlet 也有一组参数可用于筛选显示的用户帐户组。</span><span class="sxs-lookup"><span data-stu-id="fca65-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="fca65-161">例如，对于已添加到 Microsoft 365 但尚未许可使用任何服务) 的用户，未授权用户的列表 (，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fca65-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="fca65-162">应获取与以下内容类似的信息：</span><span class="sxs-lookup"><span data-stu-id="fca65-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="fca65-163">有关用于筛选所显示的用户帐户集的其他参数的信息，请参阅 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="fca65-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="fca65-164">查看特定帐户</span><span class="sxs-lookup"><span data-stu-id="fca65-164">View a specific account</span></span>

<span data-ttu-id="fca65-165">若要显示特定的用户帐户，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="fca65-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="fca65-166">填写用户帐户的登录名，该帐户也称为用户主体名称 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="fca65-167">删除 "<" 和 ">" 字符。</span><span class="sxs-lookup"><span data-stu-id="fca65-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="fca65-168">基于通用属性查看帐户</span><span class="sxs-lookup"><span data-stu-id="fca65-168">View accounts based on a common property</span></span>

<span data-ttu-id="fca65-169">若要更好地选择要显示的帐户列表，可以结合使用 **Where** Cmdlet 和 **get-msoluser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fca65-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="fca65-170">若要组合这两个 cmdlet，请使用 "管道" 字符 ( "|") ，它指示 PowerShell 获取一个命令的结果，并将其发送到下一个命令。</span><span class="sxs-lookup"><span data-stu-id="fca65-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="fca65-171">下面的示例展示了仅显示具有未指定的使用位置的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="fca65-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="fca65-172">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="fca65-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="fca65-173">获取用户帐户 (**get-msoluser**) 的所有信息，并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fca65-174">查找未指定使用位置的所有用户帐户 (**其中 {$ \_ 。UsageLocation-eq $Null}**) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="fca65-175">在大括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性 (的帐户集\*\* $ \_ 。\*\* 未 (**-eq $Null**) 指定 UsageLocation) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="fca65-176">应获取与以下内容类似的信息：</span><span class="sxs-lookup"><span data-stu-id="fca65-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="fca65-177">*UsageLocation*属性只是与用户帐户关联的很多属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="fca65-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="fca65-178">若要查看用户帐户的所有属性，请使用 **Select** cmdlet 和通配符 ( \* ) 为特定用户帐户显示所有属性。</span><span class="sxs-lookup"><span data-stu-id="fca65-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="fca65-179">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="fca65-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="fca65-180">例如， *City* 是用户帐户属性的名称。</span><span class="sxs-lookup"><span data-stu-id="fca65-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="fca65-181">您可以使用以下命令为居住在伦敦的用户列出所有用户帐户：</span><span class="sxs-lookup"><span data-stu-id="fca65-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="fca65-182">在这些示例中， **where** cmdlet 的语法为 **{$ \_ 。**</span><span class="sxs-lookup"><span data-stu-id="fca65-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="fca65-183">[用户帐户属性名称][比较运算符]增值 **}**.</span><span class="sxs-lookup"><span data-stu-id="fca65-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="fca65-184">[比较运算符] 为 **-eq** ，等于， **-ne** 表示不等于， **-lt** 表示小于， **-gt** 表示大于，其他。</span><span class="sxs-lookup"><span data-stu-id="fca65-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="fca65-185">[value] 通常是一个字符串， (字母、数字和其他字符的序列) 、数字值或未指定的 **$Null** 。</span><span class="sxs-lookup"><span data-stu-id="fca65-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="fca65-186">有关详细信息，请参阅 [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="fca65-186">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="fca65-187">若要检查用户帐户的阻止状态，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="fca65-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="fca65-188">查看帐户的其他属性值</span><span class="sxs-lookup"><span data-stu-id="fca65-188">View additional property values for accounts</span></span>

<span data-ttu-id="fca65-189">默认情况下， **get-msoluser** cmdlet 显示用户帐户的以下三个属性：</span><span class="sxs-lookup"><span data-stu-id="fca65-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="fca65-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="fca65-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="fca65-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fca65-191">DisplayName</span></span>
    
- <span data-ttu-id="fca65-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="fca65-192">isLicensed</span></span>
    
<span data-ttu-id="fca65-193">如果您需要其他属性（例如，用户所在的部门以及使用 Microsoft 365 服务的国家/地区），则可以同时运行 **get-msoluser** ，并使用 **Select** cmdlet 指定用户帐户属性列表。</span><span class="sxs-lookup"><span data-stu-id="fca65-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="fca65-194">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="fca65-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="fca65-195">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="fca65-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="fca65-196">获取有关用户帐户的所有信息 (**get-msoluser**) 并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fca65-197">仅显示用户帐户名称、部门和使用位置 (**选择 "DisplayName"、"部门"、"UsageLocation"**) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="fca65-198">应获取与以下内容类似的信息：</span><span class="sxs-lookup"><span data-stu-id="fca65-198">You should get information similar to this:</span></span>
  
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

<span data-ttu-id="fca65-199">**选择**cmdlet 允许您选择要显示的属性。</span><span class="sxs-lookup"><span data-stu-id="fca65-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="fca65-200">若要显示特定用户帐户的所有属性，请使用通配符 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="fca65-201">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="fca65-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="fca65-202">若要更好地选择要显示的帐户列表，您还可以使用 **Where** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fca65-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="fca65-203">下面的示例命令仅显示具有未指定的使用位置的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="fca65-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="fca65-204">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="fca65-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="fca65-205">获取有关用户帐户的所有信息 (**get-msoluser**) 并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fca65-206">查找未指定使用位置的所有用户帐户 (**其中 {$ \_ 。UsageLocation-eq $Null}**) ，并将生成的信息发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="fca65-207">在大括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性 (的帐户集\*\* $ \_ 。\*\* 未 (**-eq $Null**) 指定 UsageLocation) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="fca65-208">仅显示用户帐户名称、部门和使用位置 (**选择 "DisplayName"、"部门"、"UsageLocation"**) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="fca65-209">应获取与以下内容类似的信息：</span><span class="sxs-lookup"><span data-stu-id="fca65-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="fca65-210">如果要使用目录同步来创建和管理 Microsoft 365 用户，则可以显示已投影 Microsoft 365 用户的本地帐户。</span><span class="sxs-lookup"><span data-stu-id="fca65-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="fca65-211">下面的示例假定：</span><span class="sxs-lookup"><span data-stu-id="fca65-211">The following example assumes that:</span></span>

- <span data-ttu-id="fca65-212">Azure AD Connect 配置为使用 ObjectGUID 的默认源定位点。</span><span class="sxs-lookup"><span data-stu-id="fca65-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="fca65-213"> (有关配置源锚点的详细信息，请参阅 [AZURE AD Connect：设计概念](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="fca65-214">已安装 PowerShell 的 Active Directory 域服务模块 (请参阅 [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)) 。</span><span class="sxs-lookup"><span data-stu-id="fca65-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="fca65-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fca65-215">See also</span></span>

[<span data-ttu-id="fca65-216">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="fca65-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fca65-217">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fca65-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fca65-218">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="fca65-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
