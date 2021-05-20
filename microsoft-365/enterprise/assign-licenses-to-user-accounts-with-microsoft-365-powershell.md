---
title: 使用 PowerShell Microsoft 365用户帐户分配许可证
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: 本文将了解如何使用 PowerShell 向未授权Microsoft 365许可证。
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572617"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="80d6c-103">使用 PowerShell Microsoft 365用户帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="80d6c-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="80d6c-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="80d6c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="80d6c-105">在从许可计划为其帐户Microsoft 365许可证之前，用户才能使用任何服务。</span><span class="sxs-lookup"><span data-stu-id="80d6c-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="80d6c-106">可以使用 PowerShell 将许可证快速分配给未授权的帐户。</span><span class="sxs-lookup"><span data-stu-id="80d6c-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="80d6c-107">必须先为用户帐户分配位置。</span><span class="sxs-lookup"><span data-stu-id="80d6c-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="80d6c-108">指定位置是在管理中心中创建新用户帐户的必需Microsoft 365[部分](../admin/add-users/add-users.md)。</span><span class="sxs-lookup"><span data-stu-id="80d6c-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="80d6c-109">默认情况下，从本地 Active Directory 域服务同步的帐户没有指定位置。</span><span class="sxs-lookup"><span data-stu-id="80d6c-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="80d6c-110">你可以从以下位置为这些帐户配置位置：</span><span class="sxs-lookup"><span data-stu-id="80d6c-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="80d6c-111">Microsoft 365 管理员中心</span><span class="sxs-lookup"><span data-stu-id="80d6c-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="80d6c-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="80d6c-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="80d6c-113">Azure [门户 (](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) Active **Directory** 用户>  >  配置文件>  >  **联系人信息**"  >  **的** 用户帐户) 。</span><span class="sxs-lookup"><span data-stu-id="80d6c-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="80d6c-114">[了解如何使用管理中心向用户帐户](../admin/manage/assign-licenses-to-users.md)Microsoft 365许可证。</span><span class="sxs-lookup"><span data-stu-id="80d6c-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="80d6c-115">有关其他资源的列表，请参阅管理 [用户和组](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="80d6c-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="80d6c-116">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="80d6c-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="80d6c-117">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="80d6c-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="80d6c-118">接下来，使用此命令列出租户的许可证计划。</span><span class="sxs-lookup"><span data-stu-id="80d6c-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="80d6c-119">接下来，获取要添加许可证的帐户的登录名，也称为 UPN (用户) 。</span><span class="sxs-lookup"><span data-stu-id="80d6c-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="80d6c-120">接下来，确保用户帐户分配了使用位置。</span><span class="sxs-lookup"><span data-stu-id="80d6c-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="80d6c-121">如果没有分配使用位置，可以使用以下命令分配一个：</span><span class="sxs-lookup"><span data-stu-id="80d6c-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="80d6c-122">最后，指定用户登录名称和许可证计划名称并运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="80d6c-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="80d6c-123">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="80d6c-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="80d6c-124">请注意，当此模块的功能在较新的[PowerShell](/powershell/azuread/v2/azureactivedirectory) for Azure Active Directory 模块中可用时，我们将开始Graph模块。</span><span class="sxs-lookup"><span data-stu-id="80d6c-124">Please note that we will begin to deprecate this module when the functionality of this module is available in the newer [Azure Active Directory PowerShell for Graph](/powershell/azuread/v2/azureactivedirectory) module.</span></span> <span data-ttu-id="80d6c-125">我们建议创建新 PowerShell 脚本的客户使用较新的模块而不是此模块。</span><span class="sxs-lookup"><span data-stu-id="80d6c-125">We advise customers who are creating new PowerShell scripts to use the newer module instead of this module.</span></span>

<span data-ttu-id="80d6c-126">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="80d6c-126">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="80d6c-127">运行 `Get-MsolAccountSku` 命令以查看组织中可用的许可计划以及每个计划的可用许可证数量。</span><span class="sxs-lookup"><span data-stu-id="80d6c-127">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="80d6c-128">每个计划中可用的许可证数量为 **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**。</span><span class="sxs-lookup"><span data-stu-id="80d6c-128">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="80d6c-129">有关许可计划、许可证和服务的信息，请参阅 [使用 PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="80d6c-129">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="80d6c-130">PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="80d6c-130">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="80d6c-131">若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。</span><span class="sxs-lookup"><span data-stu-id="80d6c-131">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="80d6c-132">若要查找组织中未授权的帐户，请运行此命令。</span><span class="sxs-lookup"><span data-stu-id="80d6c-132">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="80d6c-133">只能将许可证分配给 **UsageLocation** 属性设置为有效的 ISO 3166-1 alpha-2 国家/地区代码的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="80d6c-133">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="80d6c-134">例如，US 代表美国，FR 代表法国。</span><span class="sxs-lookup"><span data-stu-id="80d6c-134">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="80d6c-135">某些Microsoft 365服务在某些国家/地区不可用。</span><span class="sxs-lookup"><span data-stu-id="80d6c-135">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="80d6c-136">有关详细信息，请参阅[关于许可证限制](https://go.microsoft.com/fwlink/p/?LinkId=691730)。</span><span class="sxs-lookup"><span data-stu-id="80d6c-136">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="80d6c-137">若要查找没有 **UsageLocation** 值的帐户，请运行此命令。</span><span class="sxs-lookup"><span data-stu-id="80d6c-137">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="80d6c-138">若要在 **帐户上设置 UsageLocation** 值，请运行此命令。</span><span class="sxs-lookup"><span data-stu-id="80d6c-138">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="80d6c-139">例如：</span><span class="sxs-lookup"><span data-stu-id="80d6c-139">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="80d6c-140">如果使用 **Get-MsolUser** cmdlet，而未使用 **-All** 参数，只返回前 500 个帐户。</span><span class="sxs-lookup"><span data-stu-id="80d6c-140">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="80d6c-141">向用户帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="80d6c-141">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="80d6c-142">若要向用户分配许可证，请使用 PowerShell 中的以下命令。</span><span class="sxs-lookup"><span data-stu-id="80d6c-142">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="80d6c-143">此示例将 **litwareinc：ENTERPRISEPACK** (Office 365 企业版 E3) 许可计划中的许可证分配给未授权用户 **belindan \@** litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="80d6c-143">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="80d6c-144">若要将许可证分配给所有未授权的用户，请运行此命令。</span><span class="sxs-lookup"><span data-stu-id="80d6c-144">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="80d6c-145">您无法使用相同的许可计划为用户分配多个许可证。</span><span class="sxs-lookup"><span data-stu-id="80d6c-145">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="80d6c-146">如果没有足够可用的许可证，将按照 **Get-MsolUser** cmdlet 返回的顺序为用户分配许可证，直到可用许可证用尽。</span><span class="sxs-lookup"><span data-stu-id="80d6c-146">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="80d6c-147">此示例将 **litwareinc：ENTERPRISEPACK** (Office 365 企业版 E3) 许可证计划中的许可证分配给所有未授权用户：</span><span class="sxs-lookup"><span data-stu-id="80d6c-147">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="80d6c-148">本示例将相同的许可证分配给美国销售部门的未授权用户：</span><span class="sxs-lookup"><span data-stu-id="80d6c-148">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="80d6c-149">使用 PowerShell for (模块将) 移动到其他订阅Azure Active Directory许可证Graph计划</span><span class="sxs-lookup"><span data-stu-id="80d6c-149">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="80d6c-150">首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="80d6c-150">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="80d6c-151">接下来，获取要切换订阅的用户帐户的登录名，也称为 UPN (用户) 。</span><span class="sxs-lookup"><span data-stu-id="80d6c-151">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="80d6c-152">接下来，使用此命令 (租户) 许可证计划的订阅。</span><span class="sxs-lookup"><span data-stu-id="80d6c-152">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="80d6c-153">接下来，使用这些命令列出用户帐户当前具有的订阅。</span><span class="sxs-lookup"><span data-stu-id="80d6c-153">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="80d6c-154">确定用户当前 (FROM 订阅订阅) 以及用户将订阅移动到的订阅 (TO) 。</span><span class="sxs-lookup"><span data-stu-id="80d6c-154">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="80d6c-155">最后，使用 SKU (指定 TO 和 FROM) 并运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="80d6c-155">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

<span data-ttu-id="80d6c-156">可以使用这些命令验证用户帐户的订阅更改。</span><span class="sxs-lookup"><span data-stu-id="80d6c-156">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="80d6c-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80d6c-157">See also</span></span>

[<span data-ttu-id="80d6c-158">使用 PowerShell 管理用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="80d6c-158">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="80d6c-159">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="80d6c-159">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="80d6c-160">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="80d6c-160">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
