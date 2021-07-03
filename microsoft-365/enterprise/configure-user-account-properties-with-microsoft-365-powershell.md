---
title: 使用 Microsoft 365 PowerShell 配置用户帐户属性
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
description: 使用 PowerShell for Microsoft 365配置租户中单个或多个用户帐户Microsoft 365属性。
ms.openlocfilehash: aeb9b586c42a0bdfb8d69b8d297998fedc1124e6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286005"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="6a1f8-103">使用 Microsoft 365 PowerShell 配置用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="6a1f8-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="6a1f8-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="6a1f8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6a1f8-105">可以使用 Microsoft 365 管理中心为租户的用户帐户配置Microsoft 365属性。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="6a1f8-106">在 PowerShell 中，还可以执行此操作，以及一些在管理中心中无法执行的其他操作。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6a1f8-107">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a1f8-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6a1f8-108">若要在 Azure Active Directory PowerShell for Graph 模块中配置用户帐户的属性，请使用 [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser) cmdlet 并指定要设置或更改的属性。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="6a1f8-109">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="6a1f8-110">更改特定用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="6a1f8-110">Change properties for a specific user account</span></span>

<span data-ttu-id="6a1f8-111">可以使用 *-ObjectID* 参数标识帐户，然后使用其他参数设置或更改特定属性。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="6a1f8-112">以下是最常见的参数列表：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="6a1f8-113">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-113">-Department "\<department name>"</span></span>

- <span data-ttu-id="6a1f8-114">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-114">-DisplayName "\<full user name>"</span></span>

- <span data-ttu-id="6a1f8-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>

- <span data-ttu-id="6a1f8-116">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-116">-GivenName "\<user first name>"</span></span>

- <span data-ttu-id="6a1f8-117">-Surname " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-117">-Surname "\<user last name>"</span></span>

- <span data-ttu-id="6a1f8-118">-Mobile " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-118">-Mobile "\<mobile phone number>"</span></span>

- <span data-ttu-id="6a1f8-119">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-119">-JobTitle "\<job title>"</span></span>

- <span data-ttu-id="6a1f8-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-120">-PreferredLanguage "\<language>"</span></span>

- <span data-ttu-id="6a1f8-121">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-121">-StreetAddress "\<street address>"</span></span>

- <span data-ttu-id="6a1f8-122">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-122">-City "\<city name>"</span></span>

- <span data-ttu-id="6a1f8-123">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-123">-State "\<state name>"</span></span>

- <span data-ttu-id="6a1f8-124">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-124">-PostalCode "\<postal code>"</span></span>

- <span data-ttu-id="6a1f8-125">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-125">-Country "\<country name>"</span></span>

- <span data-ttu-id="6a1f8-126">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-126">-TelephoneNumber "\<office phone number>"</span></span>

- <span data-ttu-id="6a1f8-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-127">-UsageLocation "\<2-character country or region code>"</span></span>

    <span data-ttu-id="6a1f8-128">这是 ISO 3166-1 alpha-2 (A2) 两个字母的国家/地区代码。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>

<span data-ttu-id="6a1f8-129">有关其他参数，请参阅 [Set-AzureADUser](/powershell/module/azuread/set-azureaduser)。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-129">For additional parameters, see [Set-AzureADUser](/powershell/module/azuread/set-azureaduser).</span></span>

> [!NOTE]
> <span data-ttu-id="6a1f8-130">必须先分配使用位置，然后才能将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>

<span data-ttu-id="6a1f8-131">若要显示用户帐户的用户主体名称，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="6a1f8-132">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6a1f8-133">获取 **Get-AzureADUser** (用户帐户) 并将其发送到下一个 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="6a1f8-134">按字母顺序对 **UserPrincipalName** (用户主体名称列表进行排序) 并将其发送到下一个命令 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="6a1f8-135">只显示每个帐户的"用户主体名称"属性 (**选择 UserPrincipalName**) 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="6a1f8-136">一次显示一个屏幕， (**更多**) 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-136">Display them one screen at a time (**More**).</span></span>

<span data-ttu-id="6a1f8-137">若要显示帐户的用户主体名称，显示名称 (和姓氏) ，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="6a1f8-138">填写 *$userName* 变量，然后删除 \< and > 字符：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6a1f8-139">本示例显示具有 *Caleb Sills 显示名称用户帐户的用户主体名称*。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6a1f8-140">通过使用 *$upn* 变量，您可以基于单个帐户的 显示名称。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="6a1f8-141">下面的示例将 *Belinda Newman* 的使用位置设置到法国。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="6a1f8-142">但它指定她的显示名称，而不是用户主体名称：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="6a1f8-143">更改所有用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="6a1f8-143">Change properties for all user accounts</span></span>

<span data-ttu-id="6a1f8-144">若要更改所有用户的属性，可以使用 **Get-AzureADUser** 和 **Set-AzureADUser** cmdlet 的组合。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="6a1f8-145">以下示例将所有用户的使用位置更改到 *法国*：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="6a1f8-146">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6a1f8-147">获取 **Get-AzureADUser** (用户帐户的所有信息) 并将其发送到下一个 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="6a1f8-148">将用户位置设置为法国 (**Set-AzureADUser -UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="6a1f8-149">更改一组特定用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="6a1f8-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="6a1f8-150">若要更改一组特定用户帐户的属性，可以使用 **Get-AzureADUser、Where** 和 **Set-AzureADUser** cmdlet 的组合。 </span><span class="sxs-lookup"><span data-stu-id="6a1f8-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="6a1f8-151">以下示例将会计部门所有用户的使用位置更改为 *法国*：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="6a1f8-152">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6a1f8-153">获取 **Get-AzureADUser** (用户帐户) ，并将其发送到下一个 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>

1.  <span data-ttu-id="6a1f8-154">在 Where {$_中查找其 *Department* 属性设置为"Accounting" (**用户帐户。Department -eq "Accounting"}**) ，并将生成的信息发送到下一个命令 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>

1. <span data-ttu-id="6a1f8-155">将用户位置设置为法国 (**Set-AzureADUser -UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6a1f8-156">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="6a1f8-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6a1f8-157">若要使用 Microsoft Azure Active Directory Module for Windows PowerShell 配置用户帐户的属性，请使用 **Set-MsolUser** cmdlet 并指定要设置或更改的属性。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="6a1f8-158">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a1f8-159">PowerShell Core 不支持用于 Windows PowerShell 和 cmdlet 的其名称中包含 *Msol* 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="6a1f8-160">从 Windows PowerShell 运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-160">Run these cmdlets from Windows PowerShell.</span></span>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="6a1f8-161">更改特定用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="6a1f8-161">Change properties for a specific user account</span></span>

<span data-ttu-id="6a1f8-162">若要配置特定用户帐户的属性，请使用 [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet 并指定要设置或更改的属性。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-162">To configure properties for a specific user account, use the [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="6a1f8-163">使用 *-UserPrincipalName* 参数标识帐户，然后使用其他参数设置或更改特定属性。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="6a1f8-164">下面是最常见的参数列表。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="6a1f8-165">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-165">-City "\<city name>"</span></span>

- <span data-ttu-id="6a1f8-166">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-166">-Country "\<country name>"</span></span>

- <span data-ttu-id="6a1f8-167">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-167">-Department "\<department name>"</span></span>

- <span data-ttu-id="6a1f8-168">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-168">-DisplayName "\<full user name>"</span></span>

- <span data-ttu-id="6a1f8-169">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-169">-Fax "\<fax number>"</span></span>

- <span data-ttu-id="6a1f8-170">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-170">-FirstName "\<user first name>"</span></span>

- <span data-ttu-id="6a1f8-171">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-171">-LastName "\<user last name>"</span></span>

- <span data-ttu-id="6a1f8-172">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-172">-MobilePhone "\<mobile phone number>"</span></span>

- <span data-ttu-id="6a1f8-173">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-173">-Office "\<office location>"</span></span>

- <span data-ttu-id="6a1f8-174">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-174">-PhoneNumber "\<office phone number>"</span></span>

- <span data-ttu-id="6a1f8-175">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-175">-PostalCode "\<postal code>"</span></span>

- <span data-ttu-id="6a1f8-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-176">-PreferredLanguage "\<language>"</span></span>

- <span data-ttu-id="6a1f8-177">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-177">-State "\<state name>"</span></span>

- <span data-ttu-id="6a1f8-178">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-178">-StreetAddress "\<street address>"</span></span>

- <span data-ttu-id="6a1f8-179">-Title " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-179">-Title "\<title name>"</span></span>

- <span data-ttu-id="6a1f8-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="6a1f8-180">-UsageLocation "\<2-character country or region code>"</span></span>

    <span data-ttu-id="6a1f8-181">这是 ISO 3166-1 alpha-2 (A2) 两个字母的国家/地区代码。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>

<span data-ttu-id="6a1f8-182">有关其他参数，请参阅 [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-182">For additional parameters, see [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="6a1f8-183">若要查看所有用户的用户主体名称，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="6a1f8-184">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6a1f8-185">获取 **Get-MsolUser** (用户帐户) 并将其发送到下一个 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="6a1f8-186">按字母顺序对 **UserPrincipalName** (用户主体名称列表进行排序) 并将其发送到下一个命令 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="6a1f8-187">只显示每个帐户的"用户主体名称"属性 (**选择 UserPrincipalName**) 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="6a1f8-188">一次显示一个屏幕， (**更多**) 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-188">Display them one screen at a time (**More**).</span></span>

<span data-ttu-id="6a1f8-189">若要显示帐户的用户主体名称，显示名称 (和姓氏) ，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="6a1f8-190">填写 *$userName* 变量，然后删除 \< and > 字符。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6a1f8-191">本示例显示名为 Caleb Sills 的用户的用户主体名称：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6a1f8-192">通过使用 *$upn* 变量，您可以基于单个帐户的 显示名称。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="6a1f8-193">下面是一个示例，将 *Belinda Newman* 的使用位置设置为 *法国*，但显示名称而不是用户主体名称：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="6a1f8-194">更改所有用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="6a1f8-194">Change properties for all user accounts</span></span>

<span data-ttu-id="6a1f8-195">若要更改所有用户的属性，请使用 **Get-MsolUser** 和 **Set-MsolUser** cmdlet 的组合。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="6a1f8-196">以下示例将所有用户的使用位置更改到 *法国*：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="6a1f8-197">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6a1f8-198">获取 **Get-MsolUser** (用户帐户) 并将其发送到下一个 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="6a1f8-199">将用户位置设置为法国 (**Set-MsolUser -UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="6a1f8-200">更改一组特定用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="6a1f8-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="6a1f8-201">若要更改一组特定用户帐户的属性，可以使用 **Get-MsolUser、Where** 和 **Set-MsolUser** cmdlet 的组合。 </span><span class="sxs-lookup"><span data-stu-id="6a1f8-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="6a1f8-202">以下示例将会计部门所有用户的使用位置更改为 *法国*：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="6a1f8-203">此命令指示 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="6a1f8-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="6a1f8-204">获取 **Get-MsolUser** (用户帐户) 并将其发送到下一个 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="6a1f8-205">在 Where {$_中查找其 *Department* 属性设置为"Accounting" (**用户帐户。Department -eq "Accounting"}**) 并将生成的信息发送到下一个命令 **|** () 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>

1. <span data-ttu-id="6a1f8-206">将用户位置设置为法国 (**Set-MsolUser -UsageLocation "FR"**) 。</span><span class="sxs-lookup"><span data-stu-id="6a1f8-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="6a1f8-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a1f8-207">See also</span></span>

[<span data-ttu-id="6a1f8-208">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="6a1f8-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6a1f8-209">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6a1f8-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6a1f8-210">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="6a1f8-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
