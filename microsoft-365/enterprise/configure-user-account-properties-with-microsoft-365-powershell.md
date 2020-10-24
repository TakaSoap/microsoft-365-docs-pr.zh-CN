---
title: 使用 PowerShell 配置 Microsoft 365 用户帐户属性
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: 使用 PowerShell for Microsoft 365 在 Microsoft 365 租户中配置单个或多个用户帐户的属性。
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754324"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="6d94a-103">使用 PowerShell 配置 Microsoft 365 用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="6d94a-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="6d94a-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="6d94a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6d94a-105">可以使用 Microsoft 365 管理中心配置 Microsoft 365 租户的用户帐户的属性。</span><span class="sxs-lookup"><span data-stu-id="6d94a-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="6d94a-106">在 PowerShell 中，您还可以执行此操作，以及在管理中心中无法执行的一些其他操作。</span><span class="sxs-lookup"><span data-stu-id="6d94a-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6d94a-107">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d94a-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6d94a-108">若要在 Azure Active Directory PowerShell for Graph 模块中配置用户帐户的属性，请使用 [**AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet 并指定要设置或更改的属性。</span><span class="sxs-lookup"><span data-stu-id="6d94a-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="6d94a-109">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="6d94a-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="6d94a-110">更改特定用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="6d94a-110">Change properties for a specific user account</span></span>

<span data-ttu-id="6d94a-111">使用 *-ObjectID* 参数标识帐户，并使用其他参数设置或更改特定属性。</span><span class="sxs-lookup"><span data-stu-id="6d94a-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="6d94a-112">下面列出了最常见的参数：</span><span class="sxs-lookup"><span data-stu-id="6d94a-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="6d94a-113">-部门 " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="6d94a-114">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="6d94a-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="6d94a-116">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="6d94a-117">-姓 " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="6d94a-118">-移动 " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="6d94a-119">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="6d94a-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="6d94a-121">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="6d94a-122">-市/县 " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="6d94a-123">-状态 " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="6d94a-124">- \<postal code> 邮政编码 "</span><span class="sxs-lookup"><span data-stu-id="6d94a-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="6d94a-125">-国家/地区 " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="6d94a-126">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="6d94a-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="6d94a-128">这是 ISO 3166-1 alpha-2 (A2) 双字母国家或地区代码。</span><span class="sxs-lookup"><span data-stu-id="6d94a-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="6d94a-129">有关其他参数，请参阅 [AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="6d94a-130">在将许可证分配给用户帐户之前，必须分配使用位置。</span><span class="sxs-lookup"><span data-stu-id="6d94a-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="6d94a-131">若要显示用户帐户的用户主体名称，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="6d94a-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="6d94a-132">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6d94a-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6d94a-133">获取用户帐户 (**AzureADUser**) 的所有信息，并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="6d94a-134">按字母顺序对用户主体名称列表进行排序 (**对 UserPrincipalName 进行排序**) 并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="6d94a-135">仅显示每个帐户的 "用户主体名称" 属性 (**选择 "UserPrincipalName**) "。</span><span class="sxs-lookup"><span data-stu-id="6d94a-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="6d94a-136">每次显示一屏 (**更**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="6d94a-137">若要根据其显示名称显示帐户的用户主体名称 (名和姓) ，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="6d94a-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="6d94a-138">填写 *$userName* 变量，并删除 \< and > 以下字符：</span><span class="sxs-lookup"><span data-stu-id="6d94a-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6d94a-139">本示例显示具有显示名称 *Caleb Sills*的用户帐户的用户主体名称。</span><span class="sxs-lookup"><span data-stu-id="6d94a-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6d94a-140">通过使用 *$upn* 变量，可以根据各个帐户的显示名称对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="6d94a-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="6d94a-141">下面的示例将 *Belinda Newman*的使用位置设置为法国。</span><span class="sxs-lookup"><span data-stu-id="6d94a-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="6d94a-142">但它指定了她的显示名称而不是她的用户主体名称：</span><span class="sxs-lookup"><span data-stu-id="6d94a-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="6d94a-143">更改所有用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="6d94a-143">Change properties for all user accounts</span></span>

<span data-ttu-id="6d94a-144">若要更改所有用户的属性，您可以使用 **AzureADUser** 和 **AzureADUser** cmdlet 的组合。</span><span class="sxs-lookup"><span data-stu-id="6d94a-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="6d94a-145">下面的示例将所有用户的使用位置更改为 *法国*：</span><span class="sxs-lookup"><span data-stu-id="6d94a-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="6d94a-146">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6d94a-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6d94a-147">获取用户帐户上的所有信息 (**AzureADUser**) 并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="6d94a-148">将用户位置设置为 "法国 (**AzureADUser-UsageLocation" "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="6d94a-149">更改特定用户帐户集的属性</span><span class="sxs-lookup"><span data-stu-id="6d94a-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="6d94a-150">若要更改特定用户帐户集的属性，您可以使用 **AzureADUser**、 **Where**和 **AzureADUser** cmdlet 的组合。</span><span class="sxs-lookup"><span data-stu-id="6d94a-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="6d94a-151">下面的示例将记帐部门中所有用户的使用位置更改为 " *法国*"：</span><span class="sxs-lookup"><span data-stu-id="6d94a-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="6d94a-152">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6d94a-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6d94a-153">获取用户帐户 (**AzureADUser**) 的所有信息，并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="6d94a-154">查找其 " *部门* " 属性设置为 "记帐" (**其中 {$ _）的所有用户帐户。部门-eq "记帐"}**) ，并将生成的信息发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="6d94a-155">将用户位置设置为 "法国 (**AzureADUser-UsageLocation" "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6d94a-156">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="6d94a-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6d94a-157">若要使用适用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块配置用户帐户的属性，请使用 **get-msoluser** cmdlet 并指定要设置或更改的属性。</span><span class="sxs-lookup"><span data-stu-id="6d94a-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="6d94a-158">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6d94a-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="6d94a-159">PowerShell Core 不支持 Windows PowerShell 模块的 Microsoft Azure Active Directory 模块以及在其名称中带有 *Msol* 的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d94a-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="6d94a-160">从 Windows PowerShell 运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d94a-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="6d94a-161">更改特定用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="6d94a-161">Change properties for a specific user account</span></span>

<span data-ttu-id="6d94a-162">若要配置特定用户帐户的属性，请使用 [**get-msoluser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet 并指定要设置或更改的属性。</span><span class="sxs-lookup"><span data-stu-id="6d94a-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="6d94a-163">使用 *-UserPrincipalName* 参数标识帐户，并使用其他参数设置或更改特定属性。</span><span class="sxs-lookup"><span data-stu-id="6d94a-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="6d94a-164">下面列出了最常见的参数。</span><span class="sxs-lookup"><span data-stu-id="6d94a-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="6d94a-165">-市/县 " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="6d94a-166">-国家/地区 " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="6d94a-167">-部门 " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="6d94a-168">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="6d94a-169">-传真 " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="6d94a-170">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="6d94a-171">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="6d94a-172">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="6d94a-173">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="6d94a-174">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="6d94a-175">- \<postal code> 邮政编码 "</span><span class="sxs-lookup"><span data-stu-id="6d94a-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="6d94a-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="6d94a-177">-状态 " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="6d94a-178">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="6d94a-179">-标题 " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="6d94a-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="6d94a-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="6d94a-181">这是 ISO 3166-1 alpha-2 (A2) 双字母国家或地区代码。</span><span class="sxs-lookup"><span data-stu-id="6d94a-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="6d94a-182">有关其他参数，请参阅 [get-msoluser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="6d94a-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="6d94a-183">若要查看所有用户的用户主体名称，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6d94a-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="6d94a-184">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6d94a-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6d94a-185">获取用户帐户的所有信息 (**get-msoluser**) 并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="6d94a-186">按字母顺序对用户主体名称列表进行排序 (**对 UserPrincipalName 进行排序**) 并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="6d94a-187">仅显示每个帐户的 "用户主体名称" 属性 (**选择 "UserPrincipalName**) "。</span><span class="sxs-lookup"><span data-stu-id="6d94a-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="6d94a-188">每次显示一屏 (**更**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="6d94a-189">若要根据其显示名称显示帐户的用户主体名称 (名和姓) ，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="6d94a-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="6d94a-190">填写 *$userName* 变量，并删除这些 \< and > 字符。</span><span class="sxs-lookup"><span data-stu-id="6d94a-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6d94a-191">本示例显示名为 Caleb Sills 的用户的用户主体名称：</span><span class="sxs-lookup"><span data-stu-id="6d94a-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6d94a-192">通过使用 *$upn* 变量，可以根据各个帐户的显示名称对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="6d94a-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="6d94a-193">下面的示例将 *Belinda Newman*的使用位置设置为 *法国*，但指定了她的显示名称而不是她的用户主体名称：</span><span class="sxs-lookup"><span data-stu-id="6d94a-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="6d94a-194">更改所有用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="6d94a-194">Change properties for all user accounts</span></span>

<span data-ttu-id="6d94a-195">若要更改所有用户的属性，请使用 **get-msoluser** 和 **get-msoluser** cmdlet 的组合。</span><span class="sxs-lookup"><span data-stu-id="6d94a-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="6d94a-196">下面的示例将所有用户的使用位置更改为 *法国*：</span><span class="sxs-lookup"><span data-stu-id="6d94a-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="6d94a-197">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6d94a-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6d94a-198">获取用户帐户的所有信息 (**get-msoluser**) 并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="6d94a-199">将用户位置设置为 "法国 (**get-msoluser-UsageLocation" "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="6d94a-200">更改特定用户帐户集的属性</span><span class="sxs-lookup"><span data-stu-id="6d94a-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="6d94a-201">若要更改特定用户帐户集的属性，您可以使用 **get-msoluser**、 **Where**和 **get-msoluser** cmdlet 的组合。</span><span class="sxs-lookup"><span data-stu-id="6d94a-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="6d94a-202">下面的示例将记帐部门中所有用户的使用位置更改为 " *法国*"：</span><span class="sxs-lookup"><span data-stu-id="6d94a-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="6d94a-203">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6d94a-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6d94a-204">获取用户帐户的所有信息 (**get-msoluser**) 并将其发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="6d94a-205">查找其 " *部门* " 属性设置为 "记帐" (**其中 {$ _）的所有用户帐户。部门-eq "记帐"}**) 并将生成的信息发送到下一个命令 (**|**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="6d94a-206">将用户位置设置为 "法国 (**get-msoluser-UsageLocation" "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="6d94a-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="6d94a-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d94a-207">See also</span></span>

[<span data-ttu-id="6d94a-208">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="6d94a-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6d94a-209">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d94a-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6d94a-210">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="6d94a-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
