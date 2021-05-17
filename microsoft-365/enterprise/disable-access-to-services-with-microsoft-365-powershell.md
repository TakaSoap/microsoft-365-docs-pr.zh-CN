---
title: 使用 PowerShell Microsoft 365访问服务
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: 本文将了解如何使用 PowerShell 为用户禁用对 Microsoft 365 服务的访问权限。
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687810"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a><span data-ttu-id="bf309-103">使用 PowerShell Microsoft 365访问服务</span><span class="sxs-lookup"><span data-stu-id="bf309-103">Disable access to Microsoft 365 services with PowerShell</span></span>

<span data-ttu-id="bf309-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="bf309-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bf309-105">当Microsoft 365从许可计划分配许可证时，Microsoft 365该许可证为用户提供了服务。</span><span class="sxs-lookup"><span data-stu-id="bf309-105">When a Microsoft 365 account is assigned a license from a licensing plan, Microsoft 365 services are made available to the user from that license.</span></span> <span data-ttu-id="bf309-106">但是，您可以控制Microsoft 365访问的服务。</span><span class="sxs-lookup"><span data-stu-id="bf309-106">However, you can control the Microsoft 365 services that the user can access.</span></span> <span data-ttu-id="bf309-107">例如，即使许可证允许访问 SharePoint Online 服务，也可以禁用对它的访问。</span><span class="sxs-lookup"><span data-stu-id="bf309-107">For example, even though the license allows access to the SharePoint Online service, you can disable access to it.</span></span> <span data-ttu-id="bf309-108">可以使用 PowerShell 为特定许可计划禁用对任意数目的服务的访问：</span><span class="sxs-lookup"><span data-stu-id="bf309-108">You can use PowerShell to disable access to any number of services for a specific licensing plan for:</span></span>

- <span data-ttu-id="bf309-109">单个帐户。</span><span class="sxs-lookup"><span data-stu-id="bf309-109">An individual account.</span></span>
- <span data-ttu-id="bf309-110">一组帐户。</span><span class="sxs-lookup"><span data-stu-id="bf309-110">A group of accounts.</span></span>
- <span data-ttu-id="bf309-111">组织中的所有帐户。</span><span class="sxs-lookup"><span data-stu-id="bf309-111">All accounts in your organization.</span></span>

>[!Note]
><span data-ttu-id="bf309-112">存在Microsoft 365服务依赖项，当其他服务依赖它时，可能会阻止你禁用指定服务。</span><span class="sxs-lookup"><span data-stu-id="bf309-112">There are Microsoft 365 service dependencies that can prevent you from disabling a specified service when other services depend on it.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="bf309-113">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="bf309-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="bf309-114">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="bf309-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="bf309-115">接下来，使用此命令查看可用的许可计划（也称为 AccountSkuIds）：</span><span class="sxs-lookup"><span data-stu-id="bf309-115">Next, use this command to view your available licensing plans, also known as AccountSkuIds:</span></span>

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
><span data-ttu-id="bf309-116">PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="bf309-116">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="bf309-117">若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。</span><span class="sxs-lookup"><span data-stu-id="bf309-117">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="bf309-118">有关详细信息，请参阅使用 [PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bf309-118">For more information, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="bf309-119">若要查看本主题中过程之前和之后的结果，请参阅使用 PowerShell 查看帐户 [许可证和服务详细信息](view-account-license-and-service-details-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bf309-119">To see the before and after results of the procedures in this topic, see [View account license and service details with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="bf309-120">PowerShell 脚本可自动执行本主题中描述的过程。</span><span class="sxs-lookup"><span data-stu-id="bf309-120">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="bf309-121">具体而言，该脚本允许你查看和禁用 Microsoft 365 中的服务，包括 Sway。</span><span class="sxs-lookup"><span data-stu-id="bf309-121">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="bf309-122">有关详细信息，请参阅使用 [PowerShell 禁用对 Sway 的访问](disable-access-to-sway-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bf309-122">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a><span data-ttu-id="bf309-123">为特定Microsoft 365计划禁用特定用户的特定服务</span><span class="sxs-lookup"><span data-stu-id="bf309-123">Disable specific Microsoft 365 services for specific users for a specific licensing plan</span></span>
  
<span data-ttu-id="bf309-124">若要为特定许可Microsoft 365禁用一组特定的服务，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="bf309-124">To disable a specific set of Microsoft 365 services for users for a specific licensing plan, perform the following steps:</span></span>
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a><span data-ttu-id="bf309-125">步骤 1：使用下面的语法标识许可计划中不需要的服务：</span><span class="sxs-lookup"><span data-stu-id="bf309-125">Step 1: Identify the undesirable services in the licensing plan by using the following syntax:</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

<span data-ttu-id="bf309-126">下面的示例创建一个 **LicenseOptions** 对象，该对象在名为 Office E3) 的许可计划中禁用 Office SharePoint 和 `litwareinc:ENTERPRISEPACK` (Office 365 企业版 Online) 。</span><span class="sxs-lookup"><span data-stu-id="bf309-126">The following example creates a **LicenseOptions** object that disables the Office and SharePoint Online services in the licensing plan named `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a><span data-ttu-id="bf309-127">步骤 2：对一个或多个用户使用步骤 1 中的 **LicenseOptions** 对象。</span><span class="sxs-lookup"><span data-stu-id="bf309-127">Step 2: Use the **LicenseOptions** object from Step 1 on one or more users.</span></span>
    
<span data-ttu-id="bf309-128">若要创建一个已禁用服务的新帐户，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bf309-128">To create a new account that has the services disabled, use the following syntax:</span></span>
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

<span data-ttu-id="bf309-129">以下示例为 Allie Bellew 创建一个新帐户，该帐户分配许可证并禁用步骤 1 中所述的服务。</span><span class="sxs-lookup"><span data-stu-id="bf309-129">The following example creates a new account for Allie Bellew that assigns the license and disables the services described in Step 1.</span></span>
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

<span data-ttu-id="bf309-130">有关在 PowerShell 中为用户创建用户帐户Microsoft 365，请参阅使用[PowerShell 创建用户帐户](create-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bf309-130">For more information about creating user accounts in PowerShell for Microsoft 365, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="bf309-131">若要禁用现有授权用户的服务，请使用下面的语法：</span><span class="sxs-lookup"><span data-stu-id="bf309-131">To disable the services for an existing licensed user, use the following syntax:</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

<span data-ttu-id="bf309-132">本示例对用户 BelindaN@litwareinc.com 禁用服务。</span><span class="sxs-lookup"><span data-stu-id="bf309-132">This example disables the services for the user BelindaN@litwareinc.com.</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

<span data-ttu-id="bf309-133">若要针对所有现有许可用户禁用步骤 1 中所述的服务，请从 **Get-MsolAccountSku** cmdlet (（如 **litwareinc：ENTERPRISEPACK**) ）的显示中指定 Microsoft 365 计划的名称，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bf309-133">To disable the services described in Step 1 for all existing licensed users, specify the name of your Microsoft 365 plan from the display of the **Get-MsolAccountSku** cmdlet (such as **litwareinc:ENTERPRISEPACK**), and then run the following commands:</span></span>
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 <span data-ttu-id="bf309-134">如果使用 **Get-MsolUser** cmdlet 而不使用 _All_ 参数，则仅返回前 500 个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bf309-134">If you use the **Get-MsolUser** cmdlet without using the _All_ parameter, only the first 500 user accounts are returned.</span></span>

<span data-ttu-id="bf309-135">若要对一组现有用户禁用服务，请使用下列两种方法之一来确定用户：</span><span class="sxs-lookup"><span data-stu-id="bf309-135">To disable the services for a group of existing users, use either of the following methods to identify the users:</span></span>
    
<span data-ttu-id="bf309-136">**方法 1。基于现有帐户属性筛选帐户**</span><span class="sxs-lookup"><span data-stu-id="bf309-136">**Method 1. Filter the accounts based on an existing account attribute**</span></span> 

<span data-ttu-id="bf309-137">为此，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bf309-137">To do this, use the following syntax:</span></span>
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="bf309-138">下面的示例禁用美国销售部门中的用户的服务。</span><span class="sxs-lookup"><span data-stu-id="bf309-138">The following example disables the services for users in the Sales department in the United States.</span></span>
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="bf309-139">**方法 2：使用特定帐户的列表**</span><span class="sxs-lookup"><span data-stu-id="bf309-139">**Method 2: Use a list of specific accounts**</span></span> 

<span data-ttu-id="bf309-140">若要完成此操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="bf309-140">To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="bf309-141">创建一个文本文件，在它的每一行上包含一个帐户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bf309-141">Create a text file that contains one account on each line like this:</span></span>
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   <span data-ttu-id="bf309-142">本示例中，文本文件为 C：My \\ Documents \\Accounts.txt。</span><span class="sxs-lookup"><span data-stu-id="bf309-142">In this example, the text file is C:\\My Documents\\Accounts.txt.</span></span>
    
2. <span data-ttu-id="bf309-143">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bf309-143">Run the following command:</span></span>
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

<span data-ttu-id="bf309-144">如果要禁用对多个许可计划的服务的访问，请对每个许可计划重复上述说明，确保：</span><span class="sxs-lookup"><span data-stu-id="bf309-144">If you want to disable access to services for multiple licensing plans, repeat the above instructions for each licensing plan, ensuring that:</span></span>

- <span data-ttu-id="bf309-145">用户帐户已分配许可计划。</span><span class="sxs-lookup"><span data-stu-id="bf309-145">The user accounts have been assigned the licensing plan.</span></span>
- <span data-ttu-id="bf309-146">许可计划中提供了要禁用的服务。</span><span class="sxs-lookup"><span data-stu-id="bf309-146">The services to disable are available in the licensing plan.</span></span>

<span data-ttu-id="bf309-147">若要在Microsoft 365用户许可证时禁用服务，请参阅在分配用户许可证时禁用[对服务的访问权限](disable-access-to-services-while-assigning-user-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="bf309-147">To disable Microsoft 365 services for users while you are assigning them to a licensing plan, see [Disable access to services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</span></span>

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a><span data-ttu-id="bf309-148">将许可计划中的所有服务分配给用户帐户</span><span class="sxs-lookup"><span data-stu-id="bf309-148">Assign all services in a licensing plan to a user account</span></span>

<span data-ttu-id="bf309-149">对于禁用了服务的用户帐户，可以使用以下命令为特定许可计划启用所有服务：</span><span class="sxs-lookup"><span data-stu-id="bf309-149">For user accounts that have had services disabled, you can enable all services for a specific licensing plan with these commands:</span></span>

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a><span data-ttu-id="bf309-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="bf309-150">Related topic</span></span>

[<span data-ttu-id="bf309-151">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="bf309-151">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="bf309-152">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf309-152">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="bf309-153">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="bf309-153">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
