---
title: 使用 PowerShell 禁用对Microsoft 365服务的访问
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/27/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 本文介绍如何使用 PowerShell 为用户禁用对Microsoft 365服务的访问权限。
ms.openlocfilehash: e0fc42f0c68b02824513f382228378bfd4ee2a8e
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824851"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>使用 PowerShell 禁用对Microsoft 365服务的访问

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

向Microsoft 365帐户分配许可计划许可证时，Microsoft 365服务将从该许可证提供给用户。 但是，可以控制用户可以访问的Microsoft 365服务。 例如，即使许可证允许访问 SharePoint Online 服务，也可以禁用对它的访问权限。 可以使用 PowerShell 为以下特定许可计划禁用对任意数量的服务的访问：

- 单个帐户。
- 一组帐户。
- 组织中的所有帐户。

>[!Note]
>有Microsoft 365服务依赖项可阻止在其他服务依赖指定服务时禁用该服务。
>

## <a name="use-the-microsoft-graph-powershell-sdk"></a>使用 Microsoft Graph PowerShell SDK

首先，[连接到Microsoft 365租户](/graph/powershell/get-started#authentication)。

为用户分配和删除许可证需要 User.ReadWrite.All 权限范围或[“分配许可证”图形 API参考页](/graph/api/user-assignlicense)中列出的其他权限之一。

需要组织.Read.All 权限范围才能读取租户中可用的许可证。

```powershell
Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All
```

接下来，使用此命令查看可用的许可计划，也称为 SkuPartNumber：

```powershell
Get-MgSubscribedSku | Select SkuId, SkuPartNumber, ServicePlans | Sort SkuPartNumber
```

有关详细信息，请参阅 [PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)。

若要查看本主题中过程的前后结果，请参 [阅 PowerShell 查看帐户许可证和服务详细信息](view-account-license-and-service-details-with-microsoft-365-powershell.md)。

### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>针对特定许可计划禁用特定用户的特定Microsoft 365服务
  
若要为特定许可计划的用户禁用一组特定的Microsoft 365服务，请执行以下步骤：
  
#### <a name="step-1-identify-the-undesired-services-in-the-licensing-plan-by-using-the-following-syntax"></a>步骤 1：使用以下语法标识许可计划中不受欢迎的服务：

首先，使用以下命令列出租户中可用的许可计划。

```powershell
Get-MgSubscribedSku | Select SkuPartNumber

SkuPartNumber
-------------
EMSPREMIUM
SPE_E5
RIGHTSMANAGEMENT_ADHOC

$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesiredService1>", "<UndesiredService2>"...
```

接下来，使用上述命令中的 SkuPartNumber，列出可用于给定许可证计划的服务计划 (Sku) 。

以下示例列出了可用于 **SPE_E5 (Microsoft 365 E5)** 的所有服务计划。

```powershell
Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5' |  select -ExpandProperty ServicePlans
```

```text
AppliesTo ProvisioningStatus ServicePlanId                        ServicePlanName
--------- ------------------ -------------                        ---------------
User      Success            b21a6b06-1988-436e-a07b-51ec6d9f52ad PROJECT_O365_P3
User      Success            64bfac92-2b17-4482-b5e5-a0304429de3e MICROSOFTENDPOINTDLP
User      Success            199a5c09-e0ca-4e37-8f7c-b05d533e1ea2 MICROSOFTBOOKINGS
User      Success            6db1f1db-2b46-403f-be40-e39395f08dbb CUSTOMER_KEY
User      Success            4a51bca5-1eff-43f5-878c-177680f191af WHITEBOARD_PLAN3
User      Success            07699545-9485-468e-95b6-2fca3738be01 FLOW_O365_P3
User      Success            9c0dab89-a30c-4117-86e7-97bda240acd2 POWERAPPS_O365_P3
User      Success            e212cbc7-0961-4c40-9825-01117710dcb1 FORMS_PLAN_E5
User      Success            57ff2da0-773e-42df-b2af-ffb7a2317929 TEAMS1
User      Success            21b439ba-a0ca-424f-a6cc-52f954a5b111 WIN10_PRO_ENT_SUB
User      Success            eec0eb4f-6444-4f95-aba0-50c24d67f998 AAD_PREMIUM_P2
User      Success            c1ec4a95-1f05-45b3-a911-aa3fa01094f5 INTUNE_A
User      Success            7547a3fe-08ee-4ccb-b430-5077c5041653 YAMMER_ENTERPRISE
User      Success            a23b959c-7ce8-4e57-9140-b90eb88a9e97 SWAY
User      Success            e95bec33-7c88-4a70-8e19-b10bd9d0c014 SHAREPOINTWAC
User      Success            5dbe027f-2339-4123-9542-606e4d348a72 SHAREPOINTENTERPRISE
User      Success            b737dad2-2f6c-4c65-90e3-ca563267e8b9 PROJECTWORKMANAGEMENT
User      Success            43de0ff5-c92c-492b-9116-175376d08c38 OFFICESUBSCRIPTION
User      Success            0feaeb32-d00e-4d66-bd5a-43b5b83db82c MCOSTANDARD
User      Success            9f431833-0334-42de-a7dc-70aa40db46db LOCKBOX_ENTERPRISE
User      Success            efb87545-963c-4e0d-99df-69c6916d9eb0 EXCHANGE_S_ENTERPRISE
```

有关许可证计划的完整列表 (也称为产品名称) 、其包含的服务计划及其相应的友好名称，请参阅 [产品名称和服务计划标识符以获取许可](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。  (使用 ServicePlanId 搜索以查找服务计划的相应友好名称) 。

以下示例使用 **MICROSOFTBOOKINGS** **(Microsoft Bookings) 分配SPE_E5** (Microsoft 365 E5) ，LOCKBOX_ENTERPRISE **(** 客户密码箱) 服务关闭：
  
```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$disabledPlans = $e5Sku.ServicePlans | `
    Where ServicePlanName -in ("LOCKBOX_ENTERPRISE", "MICROSOFTBOOKINGS") | `
    Select -ExpandProperty ServicePlanId

$addLicenses = @(
    @{
        SkuId = $e5Sku.SkuId
        DisabledPlans = $disabledPlans
    }
)

Set-MgUserLicense -UserId "belinda@litwareinc.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

Set-MgUserLicense中 AddLicenses 参数的 DisabledPlans 属性将覆盖用户的现有 DisabledPlans 值。 若要保留现有服务计划的状态，必须将用户的当前服务计划状态与要禁用的新计划合并。

如果无法包括现有的 DisabledPlans，则会导致用户以前禁用的计划处于启用状态。

以下示例使用 **SPE_E5 (Microsoft 365 E5)** 更新用户，并关闭Sway和窗体服务计划，同时使用户现有的禁用计划处于当前状态：
  
```powershell
## Get the services that have already been disabled for the user.
$userLicense = Get-MgUserLicenseDetail -UserId "belinda@fdoau.onmicrosoft.com"
$userDisabledPlans = $userLicense.ServicePlans | `
    Where ProvisioningStatus -eq "Disabled" | `
    Select -ExpandProperty ServicePlanId

## Get the new service plans that are going to be disabled
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$newDisabledPlans = $e5Sku.ServicePlans | `
    Where ServicePlanName -in ("SWAY", "FORMS_PLAN_E5") | `
    Select -ExpandProperty ServicePlanId

## Merge the new plans that are to be disabled with the user's current state of disabled plans
$disabledPlans = ($userDisabledPlans + $newDisabledPlans) | Select -Unique

$addLicenses = @(
    @{
        SkuId = $e5Sku.SkuId
        DisabledPlans = $disabledPlans
    }
)
## Update user's license
Set-MgUserLicense -UserId "belinda@litwareinc.onmicrosoft.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

接下来，使用此命令查看可用的许可计划，也称为 AccountSkuId：

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。 若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。
>

有关详细信息，请参阅 [PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)。
    
若要查看本主题中过程的前后结果，请参 [阅 PowerShell 查看帐户许可证和服务详细信息](view-account-license-and-service-details-with-microsoft-365-powershell.md)。
    
PowerShell 脚本可自动执行本主题中描述的过程。 具体而言，该脚本允许你查看和禁用Microsoft 365组织中的服务，包括Sway。 有关详细信息，请参阅[使用 PowerShell 禁用对Sway的访问](disable-access-to-sway-with-microsoft-365-powershell.md)。
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>针对特定许可计划禁用特定用户的特定Microsoft 365服务
  
若要为特定许可计划的用户禁用一组特定的Microsoft 365服务，请执行以下步骤：
  
#### <a name="step-1-identify-the-undesired-services-in-the-licensing-plan-by-using-the-following-syntax"></a>步骤 1：使用以下语法标识许可计划中不受欢迎的服务：
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesiredService1>", "<UndesiredService2>"...
```

以下示例创建一个 **LicenseOptions** 对象，该对象在名为 `litwareinc:ENTERPRISEPACK` (Office 365 企业版 E3) 的许可计划中禁用Office和SharePoint Online 服务。
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>步骤 2：对一个或多个用户使用步骤 1 中的 **LicenseOptions** 对象。
    
若要创建一个已禁用服务的新帐户，请使用以下语法：
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

以下示例为 Allie Bellew 创建一个新帐户，该帐户分配许可证并禁用步骤 1 中所述的服务。
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

有关在 PowerShell 中为Microsoft 365创建用户帐户的详细信息，请参阅[使用 PowerShell 创建用户帐户](create-user-accounts-with-microsoft-365-powershell.md)。
    
若要禁用现有授权用户的服务，请使用下面的语法：
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

本示例对用户 BelindaN@litwareinc.com 禁用服务。
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

若要为所有现有许可用户禁用步骤 1 中所述的服务，请从 **Get-MsolAccountSku** cmdlet (（如 **litwareinc：ENTERPRISEPACK**) ）的显示中指定Microsoft 365计划的名称，然后运行以下命令：
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 如果使用 **Get-MsolUser** cmdlet 而不使用 _All_ 参数，则仅返回前 500 个用户帐户。

若要对一组现有用户禁用服务，请使用下列两种方法之一来确定用户：
    
**方法 1.根据现有帐户属性筛选帐户** 

为此，请使用以下语法：
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

以下示例禁用美国中销售部门中用户的服务。
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**方法 2：使用特定帐户的列表** 

若要完成此操作，请执行以下步骤：
    
1. 创建一个文本文件，在它的每一行上包含一个帐户，如下所示：
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   在此示例中，文本文件为 C：\\My Documents\\Accounts.txt。
    
2. 运行以下命令：
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

如果要为多个许可计划禁用对服务的访问，请对每个许可计划重复上述说明，确保：

- 已为用户帐户分配许可计划。
- 要禁用的服务在许可计划中可用。

若要在将用户分配到许可计划时禁用Microsoft 365服务，请参阅在[分配用户许可证时禁用对服务的访问权限](disable-access-to-services-while-assigning-user-licenses.md)。

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>将许可计划中的所有服务分配给用户帐户

对于已禁用服务的用户帐户，可以使用以下命令为特定许可计划启用所有服务：

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>相关主题

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
