---
title: 使用 PowerShell 查看 Microsoft 365 许可证和服务
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
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: 介绍如何使用 PowerShell 查看有关 Microsoft 365 组织中可用的许可计划、服务和许可证的信息。
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924632"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="fbddf-103">使用 PowerShell 查看 Microsoft 365 许可证和服务</span><span class="sxs-lookup"><span data-stu-id="fbddf-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="fbddf-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="fbddf-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fbddf-105">每个 Microsoft 365 订阅包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="fbddf-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="fbddf-106">**许可计划** 这些也称为许可证计划或 Microsoft 365 计划。</span><span class="sxs-lookup"><span data-stu-id="fbddf-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="fbddf-107">许可计划定义可供用户使用的 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="fbddf-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="fbddf-108">你的 Microsoft 365 订阅可能包含多个许可计划。</span><span class="sxs-lookup"><span data-stu-id="fbddf-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="fbddf-109">Microsoft 365 E3 就是一个许可计划示例。</span><span class="sxs-lookup"><span data-stu-id="fbddf-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="fbddf-110">**服务** 这些也称为服务计划。</span><span class="sxs-lookup"><span data-stu-id="fbddf-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="fbddf-111">服务是每个许可计划中提供的 Microsoft 365 产品、特性和功能，例如，Exchange Online 和 Microsoft 365 企业应用版 (以前称为 Office 365 专业增强版) 。</span><span class="sxs-lookup"><span data-stu-id="fbddf-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="fbddf-112">可以从授予不同服务访问权限的不同许可计划向用户分配多个许可证。</span><span class="sxs-lookup"><span data-stu-id="fbddf-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="fbddf-113">**许可证** 每个许可计划都包含你购买的许可证数量。</span><span class="sxs-lookup"><span data-stu-id="fbddf-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="fbddf-114">你可以向用户分配许可证，以便他们可以使用许可计划定义的 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="fbddf-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="fbddf-115">每个用户帐户至少需要一个许可计划中的一个许可证，以便他们可以登录到 Microsoft 365 并使用服务。</span><span class="sxs-lookup"><span data-stu-id="fbddf-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="fbddf-116">可以使用适用于 Microsoft 365 的 PowerShell 查看有关 Microsoft 365 组织中可用许可计划、许可证和服务的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fbddf-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="fbddf-117">有关不同 Office 365 订阅中提供的产品、功能和服务的详细信息，请参阅 [Office 365 计划选项](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)。</span><span class="sxs-lookup"><span data-stu-id="fbddf-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="fbddf-118">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbddf-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="fbddf-119">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="fbddf-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="fbddf-120">若要查看有关当前许可计划以及每个计划的可用许可证的摘要信息，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fbddf-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="fbddf-121">结果包含：</span><span class="sxs-lookup"><span data-stu-id="fbddf-121">The results contain:</span></span>
  
- <span data-ttu-id="fbddf-122">**SkuPartNumber：** 显示组织的可用许可计划。</span><span class="sxs-lookup"><span data-stu-id="fbddf-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="fbddf-123">例如， `ENTERPRISEPACK` 是 Office 365 企业版 E3 的许可证计划名称。</span><span class="sxs-lookup"><span data-stu-id="fbddf-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="fbddf-124">**已启用：** 你为特定许可计划购买的许可证数量。</span><span class="sxs-lookup"><span data-stu-id="fbddf-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="fbddf-125">**ConsumedUnits：** 从特定许可计划向用户分配的许可证数。</span><span class="sxs-lookup"><span data-stu-id="fbddf-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="fbddf-126">若要查看所有许可证计划中可用的 Microsoft 365 服务的详细信息，请首先显示许可证计划的列表。</span><span class="sxs-lookup"><span data-stu-id="fbddf-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="fbddf-127">接下来，将许可证计划信息存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="fbddf-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="fbddf-128">接下来，显示特定许可证计划中的服务。</span><span class="sxs-lookup"><span data-stu-id="fbddf-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="fbddf-129">\<index> 是一个整数，用于指定显示命令后许可证计划的行号，减 `Get-AzureADSubscribedSku | Select SkuPartNumber` 1。</span><span class="sxs-lookup"><span data-stu-id="fbddf-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="fbddf-130">例如，如果命令的显示 `Get-AzureADSubscribedSku | Select SkuPartNumber` 方式为：</span><span class="sxs-lookup"><span data-stu-id="fbddf-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="fbddf-131">然后，显示 ENTERPRISEPREMIUM 许可证计划的服务的命令为：</span><span class="sxs-lookup"><span data-stu-id="fbddf-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="fbddf-132">ENTERPRISEPREMIUM 是第三行。</span><span class="sxs-lookup"><span data-stu-id="fbddf-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="fbddf-133">因此，索引值是 (3 - 1) 2。</span><span class="sxs-lookup"><span data-stu-id="fbddf-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="fbddf-134">有关许可证计划的完整列表 (也称为产品名称) 、包含的服务计划及其对应的友好名称，请参阅许可的产品名称和服务计划 [标识符](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。</span><span class="sxs-lookup"><span data-stu-id="fbddf-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="fbddf-135">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="fbddf-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="fbddf-136">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="fbddf-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="fbddf-137">PowerShell 脚本可自动执行本主题中描述的过程。</span><span class="sxs-lookup"><span data-stu-id="fbddf-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="fbddf-138">具体而言，该脚本允许你查看和禁用 Microsoft 365 组织（包括 Sway）中的服务。</span><span class="sxs-lookup"><span data-stu-id="fbddf-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="fbddf-139">有关详细信息，请参阅使用 [PowerShell 禁用对 Sway 的访问](disable-access-to-sway-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="fbddf-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="fbddf-140">若要查看有关当前许可计划以及每个计划的可用许可证的摘要信息，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fbddf-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="fbddf-141">PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="fbddf-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="fbddf-142">若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。</span><span class="sxs-lookup"><span data-stu-id="fbddf-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="fbddf-143">结果包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="fbddf-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="fbddf-144">**AccountSkuId：** 使用 语法 显示组织的可用许可计划 `<CompanyName>:<LicensingPlan>` 。</span><span class="sxs-lookup"><span data-stu-id="fbddf-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="fbddf-145">_\<CompanyName>_ 是你在 Microsoft 365 中注册时提供的值，并且对于你的组织是唯一的。</span><span class="sxs-lookup"><span data-stu-id="fbddf-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="fbddf-146">_\<LicensingPlan>_ 该值对于每个人都是相同的。</span><span class="sxs-lookup"><span data-stu-id="fbddf-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="fbddf-147">例如，在值 中，公司名称是 ，许可计划名称 `litwareinc:ENTERPRISEPACK`  `litwareinc` 是  `ENTERPRISEPACK` Office 365 企业版 E3 的系统名称。</span><span class="sxs-lookup"><span data-stu-id="fbddf-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="fbddf-148">**ActiveUnits：** 你为特定许可计划购买的许可证数量。</span><span class="sxs-lookup"><span data-stu-id="fbddf-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="fbddf-149">**WarningUnits：** 未续订且将在 30 天宽限期后过期的许可计划中许可证数量。</span><span class="sxs-lookup"><span data-stu-id="fbddf-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="fbddf-150">**ConsumedUnits：** 从特定许可计划向用户分配的许可证数。</span><span class="sxs-lookup"><span data-stu-id="fbddf-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="fbddf-151">若要查看所有许可证计划中可用的 Microsoft 365 服务的详细信息，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fbddf-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="fbddf-152">下表显示了最常见服务的 Microsoft 365 服务计划及其友好名称。</span><span class="sxs-lookup"><span data-stu-id="fbddf-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="fbddf-153">服务计划列表可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="fbddf-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="fbddf-154">**服务计划**</span><span class="sxs-lookup"><span data-stu-id="fbddf-154">**Service plan**</span></span>|<span data-ttu-id="fbddf-155">**说明**</span><span class="sxs-lookup"><span data-stu-id="fbddf-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="fbddf-156">Sway</span><span class="sxs-lookup"><span data-stu-id="fbddf-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="fbddf-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fbddf-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="fbddf-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="fbddf-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="fbddf-159">Azure 权限管理 (RMS)</span><span class="sxs-lookup"><span data-stu-id="fbddf-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="fbddf-160">以前名为 Office 365 专业增强 (*Microsoft 365* 企业应用版) </span><span class="sxs-lookup"><span data-stu-id="fbddf-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="fbddf-161">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fbddf-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="fbddf-162">Office</span><span class="sxs-lookup"><span data-stu-id="fbddf-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="fbddf-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fbddf-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="fbddf-164">Exchange Online 计划 2</span><span class="sxs-lookup"><span data-stu-id="fbddf-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="fbddf-165">有关许可证计划的完整列表 (也称为产品名称) 、包含的服务计划及其对应的友好名称，请参阅许可的产品名称和服务计划 [标识符](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。</span><span class="sxs-lookup"><span data-stu-id="fbddf-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="fbddf-166">若要查看特定许可计划中提供的 Microsoft 365 服务的详细信息，请使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="fbddf-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="fbddf-167">此示例显示 office 365 企业版 E3 许可计划 (litwareinc：ENTERPRISEPACK) 服务。</span><span class="sxs-lookup"><span data-stu-id="fbddf-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="fbddf-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbddf-168">See also</span></span>

[<span data-ttu-id="fbddf-169">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="fbddf-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fbddf-170">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fbddf-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fbddf-171">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="fbddf-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)