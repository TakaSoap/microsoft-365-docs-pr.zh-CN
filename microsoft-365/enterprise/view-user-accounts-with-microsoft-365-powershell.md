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
ms.openlocfilehash: 4dba05ce440ec0d395fda58a12df3e9f751bb469
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357894"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="e9954-103">使用 PowerShell 查看 Microsoft 365 用户帐户</span><span class="sxs-lookup"><span data-stu-id="e9954-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="e9954-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="e9954-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e9954-105">虽然您可以使用 Microsoft 365 管理中心来查看 Microsoft 365 租户的帐户，但您也可以使用 PowerShell for Microsoft 365 并执行管理中心无法执行的某些操作。</span><span class="sxs-lookup"><span data-stu-id="e9954-105">Although you can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant, you can also use PowerShell for Microsoft 365 and do some things that the admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e9954-106">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9954-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e9954-107">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="e9954-107">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="e9954-108">查看所有帐户</span><span class="sxs-lookup"><span data-stu-id="e9954-108">View all accounts</span></span>

<span data-ttu-id="e9954-109">若要显示用户帐户的完整列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9954-109">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="e9954-110">您应看到类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="e9954-110">You should see information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="e9954-111">查看特定帐户</span><span class="sxs-lookup"><span data-stu-id="e9954-111">View a specific account</span></span>

<span data-ttu-id="e9954-112">若要显示特定的用户帐户，请填写用户帐户的登录帐户名（也称为 "用户主体名称 (UPN) ），删除" < "和" > "字符，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9954-112">To display a specific user account, fill in the sign-in account name of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="e9954-113">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e9954-113">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="e9954-114">查看特定帐户的其他属性值</span><span class="sxs-lookup"><span data-stu-id="e9954-114">View additional property values for a specific account</span></span>

<span data-ttu-id="e9954-115">默认情况下， **AzureADUser** cmdlet 仅显示帐户的 ObjectID、DisplayName 和 UserPrincipalName 属性。</span><span class="sxs-lookup"><span data-stu-id="e9954-115">By default, the **Get-AzureADUser** cmdlet only displays the ObjectID, DisplayName, and UserPrincipalName properties of accounts.</span></span>

<span data-ttu-id="e9954-116">若要更好地选择要显示的属性列表，可以结合使用 **Select** Cmdlet 和 **AzureADUser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e9954-116">To be more selective about the list of properties to display, you can use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="e9954-117">若要组合这两个 cmdlet，我们使用 "管道" 字符 "|"，它通知 Azure Active Directory PowerShell 以获取一个命令的结果，并将其发送到下一个命令。</span><span class="sxs-lookup"><span data-stu-id="e9954-117">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="e9954-118">下面是一个显示每个用户帐户的 DisplayName、部门和 UsageLocation 的示例命令：</span><span class="sxs-lookup"><span data-stu-id="e9954-118">Here is an example command that displays the DisplayName, Department, and UsageLocation for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="e9954-119">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="e9954-119">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="e9954-120">获取用户帐户上的所有信息 ( **AzureADUser** ) 并将其发送到下一个命令 ( **|** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-120">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="e9954-121">仅显示用户帐户名称、部门和使用位置 ( **选择 "DisplayName"、"部门"、"UsageLocation"** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-121">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
  
<span data-ttu-id="e9954-122">若要查看用户帐户的所有属性，请使用 **Select** cmdlet 和通配符 ( \* ) 为特定用户帐户显示所有属性。</span><span class="sxs-lookup"><span data-stu-id="e9954-122">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="e9954-123">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e9954-123">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="e9954-124">作为另一个示例，您可以使用以下命令检查特定用户帐户的启用状态：</span><span class="sxs-lookup"><span data-stu-id="e9954-124">As another example, you can check the enabled status of a specific user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="e9954-125">查看帐户同步状态</span><span class="sxs-lookup"><span data-stu-id="e9954-125">View account synchronization status</span></span>

<span data-ttu-id="e9954-126">用户帐户有两个源;Windows Server Active Directory (AD) ，它们是从本地 AD 同步到云和 Azure AD 的帐户，后者是在云中直接创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="e9954-126">User accounts have two sources; Windows Server Active Directory (AD) which are accounts that sync from on-premises AD to the cloud and Azure AD which are accounts directly created in the cloud.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```
<span data-ttu-id="e9954-127">此命令指示 PowerShell 获取属性 **DirSyncEnabled** 设置为 True 的所有用户。</span><span class="sxs-lookup"><span data-stu-id="e9954-127">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to True.</span></span> <span data-ttu-id="e9954-128">它可用于提取从内部部署 AD 同步的帐户。</span><span class="sxs-lookup"><span data-stu-id="e9954-128">It can be used to pull up accounts synchronizing from on-premise AD.</span></span>


```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $true}
```
<span data-ttu-id="e9954-129">此命令指示 PowerShell 获取属性 **DirSyncEnabled** 设置为 False 的所有用户。</span><span class="sxs-lookup"><span data-stu-id="e9954-129">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to False.</span></span> <span data-ttu-id="e9954-130">它可用于提取仅限云帐户。</span><span class="sxs-lookup"><span data-stu-id="e9954-130">It can be used to pull up cloud-only accounts.</span></span>

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="e9954-131">根据通用属性查看一些帐户</span><span class="sxs-lookup"><span data-stu-id="e9954-131">View some accounts based on a common property</span></span>

<span data-ttu-id="e9954-132">若要更好地选择要显示的帐户列表，可以结合使用 **Where** Cmdlet 和 **AzureADUser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e9954-132">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="e9954-133">若要组合这两个 cmdlet，我们使用 "管道" 字符 "|"，它通知 Azure Active Directory PowerShell 以获取一个命令的结果，并将其发送到下一个命令。</span><span class="sxs-lookup"><span data-stu-id="e9954-133">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="e9954-134">下面是一个示例命令，它显示了未指定使用地点的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="e9954-134">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="e9954-135">此命令将 Azure Active Directory PowerShell for Graph 指示为：</span><span class="sxs-lookup"><span data-stu-id="e9954-135">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
- <span data-ttu-id="e9954-136">获取用户帐户上的所有信息 ( **AzureADUser** ) 并将其发送到下一个命令 ( **|** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-136">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="e9954-137">查找未指定使用位置的所有用户帐户 ( **其中 {$ \_ 。UsageLocation-eq $Null}** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-137">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="e9954-138">在大括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性 ( 的帐户集\*\* $ \_ 。\*\* 未 ( **-eq $Null** ) 指定 UsageLocation ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-138">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="e9954-139">**UsageLocation**属性只是与用户帐户关联的很多属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="e9954-139">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="e9954-140">若要查看用户帐户的所有属性，请使用 **Select** cmdlet 和通配符 ( \* ) 为特定用户帐户显示所有属性。</span><span class="sxs-lookup"><span data-stu-id="e9954-140">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="e9954-141">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e9954-141">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="e9954-142">例如，在此列表中， **City** 是用户帐户属性的名称。</span><span class="sxs-lookup"><span data-stu-id="e9954-142">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="e9954-143">这意味着您可以使用以下命令列出居住在伦敦的用户的所有用户帐户：</span><span class="sxs-lookup"><span data-stu-id="e9954-143">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="e9954-144">这些示例中所示的 **where** cmdlet 的语法为 **{$ \_ 。**</span><span class="sxs-lookup"><span data-stu-id="e9954-144">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="e9954-145">[用户帐户属性名称][比较运算符]增值 **}**. > [比较运算符] 为 **-eq** for equals， **-ne** 不等于， **-lt** 表示小于， **-gt** 表示大于，其他。</span><span class="sxs-lookup"><span data-stu-id="e9954-145">[user account property name] [comparison operator] [value] **}**.>  [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="e9954-146">[value] 通常是一个字符串， (字母、数字和其他字符的序列) 、数值或未指定> 的 **$Null** 。有关详细信息，请参阅 [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-146">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified>  See [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) for more information.</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e9954-147">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="e9954-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e9954-148">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e9954-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="e9954-149">查看所有帐户</span><span class="sxs-lookup"><span data-stu-id="e9954-149">View all accounts</span></span>

<span data-ttu-id="e9954-150">若要显示用户帐户的完整列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9954-150">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="e9954-151">PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="e9954-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="e9954-152">若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。</span><span class="sxs-lookup"><span data-stu-id="e9954-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="e9954-153">您应看到类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="e9954-153">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="e9954-154">**Get-MsolUser** cmdlet 也有一组参数可用于筛选显示的用户帐户组。</span><span class="sxs-lookup"><span data-stu-id="e9954-154">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="e9954-155">例如，对于已添加到 Microsoft 365 但尚未许可使用任何服务) 的用户，未授权用户的列表 (的用户运行此命令。</span><span class="sxs-lookup"><span data-stu-id="e9954-155">For example, for the list of unlicensed users (users who've been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command.</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="e9954-156">您应看到类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="e9954-156">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="e9954-157">有关筛选显示显示的用户帐户集的其他参数的详细信息，请参阅 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="e9954-157">For more information about additional parameters to filter the display the set of user accounts displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="e9954-158">查看特定帐户</span><span class="sxs-lookup"><span data-stu-id="e9954-158">View a specific account</span></span>

<span data-ttu-id="e9954-159">若要显示特定的用户帐户，请填写用户帐户的用户帐户的登录名（也称为 "用户主体名称 (UPN) ），删除" < "和" > "字符，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9954-159">To display a specific user account, fill in the sign-in name of the user account of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="e9954-160">根据通用属性查看一些帐户</span><span class="sxs-lookup"><span data-stu-id="e9954-160">View some accounts based on a common property</span></span>

<span data-ttu-id="e9954-161">若要更好地选择要显示的帐户列表，可以结合使用 **Where** Cmdlet 和 **get-msoluser** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e9954-161">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="e9954-162">若要组合这两个 cmdlet，我们使用 "管道" 字符 "|"，它将通知 PowerShell 获取一个命令的结果，并将其发送到下一个命令。</span><span class="sxs-lookup"><span data-stu-id="e9954-162">To combine the two cmdlets, we use the "pipe" character "|", which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="e9954-163">下面是一个示例命令，它显示了未指定使用地点的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="e9954-163">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="e9954-164">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="e9954-164">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="e9954-165">获取用户帐户上的所有信息 ( **get-msoluser** ) 并将其发送到下一个命令 ( **|** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-165">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="e9954-166">查找未指定使用位置的所有用户帐户 ( **其中 {$ \_ 。UsageLocation-eq $Null}** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-166">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="e9954-167">在大括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性 ( 的帐户集\*\* $ \_ 。\*\* 未 ( **-eq $Null** ) 指定 UsageLocation ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-167">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="e9954-168">您应看到类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="e9954-168">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="e9954-169">**UsageLocation**属性只是与用户帐户关联的很多属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="e9954-169">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="e9954-170">若要查看用户帐户的所有属性，请使用 **Select** cmdlet 和通配符 ( \* ) 为特定用户帐户显示所有属性。</span><span class="sxs-lookup"><span data-stu-id="e9954-170">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="e9954-171">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e9954-171">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="e9954-172">例如，在此列表中， **City** 是用户帐户属性的名称。</span><span class="sxs-lookup"><span data-stu-id="e9954-172">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="e9954-173">这意味着您可以使用以下命令列出居住在伦敦的用户的所有用户帐户：</span><span class="sxs-lookup"><span data-stu-id="e9954-173">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="e9954-174">这些示例中所示的 **where** cmdlet 的语法为 **{$ \_ 。**</span><span class="sxs-lookup"><span data-stu-id="e9954-174">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="e9954-175">[用户帐户属性名称][比较运算符]增值 **}**.</span><span class="sxs-lookup"><span data-stu-id="e9954-175">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="e9954-176">[比较运算符] 为 **-eq** ，等于， **-ne** 表示不等于， **-lt** 表示小于， **-gt** 表示大于，其他。</span><span class="sxs-lookup"><span data-stu-id="e9954-176">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="e9954-177">[value] 通常是一个字符串， (字母、数字和其他字符的序列) 、数字值或未指定的 **$Null** 。</span><span class="sxs-lookup"><span data-stu-id="e9954-177">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="e9954-178">有关详细信息，请参阅 [何处](https://technet.microsoft.com/library/hh849715.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-178">See [Where](https://technet.microsoft.com/library/hh849715.aspx) for more information.</span></span>
  
<span data-ttu-id="e9954-179">您可以使用以下命令检查用户帐户的阻止状态：</span><span class="sxs-lookup"><span data-stu-id="e9954-179">You can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="e9954-180">查看帐户的其他属性值</span><span class="sxs-lookup"><span data-stu-id="e9954-180">View additional property values for accounts</span></span>

<span data-ttu-id="e9954-181">默认情况下， **get-msoluser** cmdlet 显示用户帐户的三个属性：</span><span class="sxs-lookup"><span data-stu-id="e9954-181">The **Get-MsolUser** cmdlet by default displays three properties of user accounts:</span></span>
  
- <span data-ttu-id="e9954-182">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="e9954-182">UserPrincipalName</span></span>
    
- <span data-ttu-id="e9954-183">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e9954-183">DisplayName</span></span>
    
- <span data-ttu-id="e9954-184">isLicensed</span><span class="sxs-lookup"><span data-stu-id="e9954-184">isLicensed</span></span>
    
<span data-ttu-id="e9954-185">如果您需要其他属性（如用户所使用的部门和用户使用 Microsoft 365 服务的国家/地区），则可以同时运行 **get-msoluser** ，并使用 **Select** cmdlet 指定用户帐户属性列表。</span><span class="sxs-lookup"><span data-stu-id="e9954-185">If you need additional properties, such as the department the user works for and the country/region where the user uses Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="e9954-186">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e9954-186">Here is an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="e9954-187">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="e9954-187">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="e9954-188">获取用户帐户上的所有信息 ( **get-msoluser** ) 并将其发送到下一个命令 ( **|** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-188">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="e9954-189">仅显示用户帐户名称、部门和使用位置 ( **选择 "DisplayName"、"部门"、"UsageLocation"** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-189">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="e9954-190">您应看到类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="e9954-190">You should see information similar to this:</span></span>
  
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

<span data-ttu-id="e9954-191">使用 **Select** cmdlet，您可以选取要显示命令的属性并选择这些属性。</span><span class="sxs-lookup"><span data-stu-id="e9954-191">The **Select** cmdlet lets you pick and choose the properties you want a command to display.</span></span> <span data-ttu-id="e9954-192">若要查看用户帐户的所有属性，请使用通配符 ( \* ) 为特定用户帐户显示所有属性。</span><span class="sxs-lookup"><span data-stu-id="e9954-192">To see all of the properties for user accounts, use the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="e9954-193">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e9954-193">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="e9954-194">若要更好地选择要显示的帐户列表，您还可以使用 **Where** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e9954-194">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="e9954-195">下面是一个示例命令，它显示了未指定使用地点的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="e9954-195">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="e9954-196">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="e9954-196">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="e9954-197">获取用户帐户上的所有信息 ( **get-msoluser** ) 并将其发送到下一个命令 ( **|** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-197">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="e9954-198">查找未指定使用位置的所有用户帐户 ( **其中 {$ \_ 。UsageLocation-eq $Null}** ) 并将生成的信息发送到下一个命令 ( **|** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-198">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ) and send the resulting information to the next command ( **|** ).</span></span> <span data-ttu-id="e9954-199">在大括号内，该命令指示 PowerShell 仅查找 UsageLocation 用户帐户属性 ( 的帐户集\*\* $ \_ 。\*\* 未 ( **-eq $Null** ) 指定 UsageLocation ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-199">Inside the braces, the command is instructing PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
- <span data-ttu-id="e9954-200">仅显示用户帐户名称、部门和使用位置 ( **选择 "DisplayName"、"部门"、"UsageLocation"** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9954-200">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="e9954-201">您应看到类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="e9954-201">You should see information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="e9954-202">如果要使用目录同步来创建和管理 Microsoft 365 用户，则可以显示已投影 Microsoft 365 用户的本地帐户。</span><span class="sxs-lookup"><span data-stu-id="e9954-202">If you are using directory synchronization to create and manage your Microsoft 365 users, you can display which local account a Microsoft 365 user has been projected from.</span></span> <span data-ttu-id="e9954-203">以下示例假定已将 Azure AD Connect 配置为使用 ObjectGUID (的默认源锚点。有关配置源锚点的详细信息，请参阅 [AZURE Ad connect：设计概念](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) 并假定已安装用于 PowerShell 的 Active Directory 域服务模块 (参阅 [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)) ：</span><span class="sxs-lookup"><span data-stu-id="e9954-203">The following assumes that Azure AD Connect has been configured to use the default source anchor of ObjectGUID (for more on configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) and assumes that the Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="e9954-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9954-204">See also</span></span>

[<span data-ttu-id="e9954-205">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="e9954-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e9954-206">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e9954-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e9954-207">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="e9954-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
