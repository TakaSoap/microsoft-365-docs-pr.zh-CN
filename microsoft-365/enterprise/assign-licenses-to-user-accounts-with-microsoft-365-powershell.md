---
title: 使用 PowerShell 将Microsoft 365许可证分配给用户帐户
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 本文介绍如何使用 PowerShell 向未经许可的用户分配Microsoft 365许可证。
ms.openlocfilehash: 72ad30cb3c8a36a78b3f95699c775b96d959b542
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823027"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>使用 PowerShell 将Microsoft 365许可证分配给用户帐户

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

用户无法使用任何Microsoft 365服务，除非其帐户已从许可计划中分配许可证。 可以使用 PowerShell 将许可证快速分配到未经许可的帐户。 

必须首先为用户帐户分配一个位置。 指定位置是Microsoft 365 管理中心中创建新用户帐户的必需[部分。](../admin/add-users/add-users.md) 

默认情况下，从本地 Active Directory域服务同步的帐户没有指定位置。 可以从以下位置配置这些帐户的位置：

- Microsoft 365 管理员中心
- [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
- [Azure 门户](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active DirectoryUsers** >  > **ProfileContact infoCountry** >  **或区域**) > > 用户帐户。

>[!Note]
>[了解如何使用Microsoft 365 管理中心向用户帐户分配许可证](../admin/manage/assign-licenses-to-users.md)。 有关其他资源的列表，请参阅 [“管理用户和组](/admin)”。
>

## <a name="use-the-microsoft-graph-powershell-sdk"></a>使用 Microsoft Graph PowerShell SDK

首先，[连接到Microsoft 365租户](/graph/powershell/get-started#authentication)。

为用户分配和删除许可证需要 User.ReadWrite.All 权限范围或[“分配许可证”图形 API参考页](/graph/api/user-assignlicense)中列出的其他权限之一。

需要组织.Read.All 权限范围才能读取租户中可用的许可证。

```powershell
Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All
```

运行该 `Get-MgSubscribedSku` 命令以查看组织中每个计划的可用许可计划和可用许可证数。 每个计划中的可用许可证数是 ActiveUnitsWarningUnitsConsumedUnits -  - 。 有关许可计划、许可证和服务的详细信息，请参 [阅 PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)。

若要在组织中查找未经许可的帐户，请运行此命令。

```powershell
Get-MgUser -Filter 'assignedLicenses/$count eq 0' -ConsistencyLevel eventual -CountVariable unlicensedUserCount -All
```

只能将许可证分配给将 **UsageLocation** 属性设置为有效 ISO 3166-1 alpha-2 国家/地区代码的用户帐户。 例如，US 代表美国，FR 代表法国。 某些Microsoft 365服务在某些国家/地区不可用。 有关详细信息，请参阅[关于许可证限制](https://go.microsoft.com/fwlink/p/?LinkId=691730)。

若要查找没有 **UsageLocation 值的** 帐户，请运行此命令。

```powershell
Get-MgUser -Select Id,DisplayName,Mail,UserPrincipalName,UsageLocation,UserType | where { $_.UsageLocation -eq $null -and $_.UserType -eq 'Member' }
```

若要在帐户上设置 **UsageLocation** 值，请运行此命令。

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"

Update-MgUser -UserId $userUPN -UsageLocation $userLoc
```

例如：

```powershell
Update-MgUser -UserId "belindan@litwareinc.com" -UsageLocation US
```

如果使用 **Get-MgUser** cmdlet 而不使用 **-All** 参数，则仅返回前 100 个帐户。

### <a name="assigning-licenses-to-user-accounts"></a>将许可证分配给用户帐户

若要向用户分配许可证，请在 PowerShell 中使用以下命令。
  
```powershell
Set-MgUserLicense -UserId $userUPN -AddLicenses @{SkuId = "<SkuId>"} -RemoveLicenses @()
```

本示例将 **SPE_E5 (Microsoft 365 E5)** 许可计划中的许可证分配给未经许可的用户 **belindan\@ litwareinc.com**：
  
```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
Set-MgUserLicense -UserId "belindan@litwareinc.com" -AddLicenses @{SkuId = $e5Sku.SkuId} -RemoveLicenses @()
```

本示例将 **SPE_E5 (Microsoft 365 E5)** 和 **EMSPREMIUM** (ENTERPRISE MOBILITY + SECURITY E5) 分配给用户 **belindan\@ litwareinc.com**：
  
```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$e5EmsSku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'EMSPREMIUM'
$addLicenses = @(
    @{SkuId = $e5Sku.SkuId},
    @{SkuId = $e5EmsSku.SkuId}
)

Set-MgUserLicense -UserId "belinda@litwareinc.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

本示例使用 **MICROSOFTBOOKINGS** **(Microsoft Bookings) 分配SPE_E5****(Microsoft 365 E5) ，LOCKBOX_ENTERPRISE** (客户 LockBox) 服务关闭：
  
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

本示例使用 **SPE_E5 (Microsoft 365 E5)** 更新用户，并关闭Sway和窗体服务计划，同时使用户现有的禁用计划处于当前状态：
  
```powershell
$userLicense = Get-MgUserLicenseDetail -UserId "belinda@fdoau.onmicrosoft.com"
$userDisabledPlans = $userLicense.ServicePlans | `
    Where ProvisioningStatus -eq "Disabled" | `
    Select -ExpandProperty ServicePlanId

$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$newDisabledPlans = $e5Sku.ServicePlans | `
    Where ServicePlanName -in ("SWAY", "FORMS_PLAN_E5") | `
    Select -ExpandProperty ServicePlanId

$disabledPlans = ($userDisabledPlans + $newDisabledPlans) | Select -Unique

$addLicenses = @(
    @{
        SkuId = $e5Sku.SkuId
        DisabledPlans = $disabledPlans
    }
)

Set-MgUserLicense -UserId "belinda@litwareinc.onmicrosoft.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

### <a name="assign-licenses-to-a-user-by-copying-the-license-assignment-from-another-user"></a>通过从其他用户复制许可证分配向用户分配许可证

本示例使用应用于 **belindan\@** 的相同许可计划分配 **jamesp\@ litwareinc.com** litwareinc.com：

```powershell
$mgUser = Get-MgUser -UserId "belindan@litwareinc.com"
Set-MgUserLicense -UserId "jamesp@litwareinc.com" -AddLicenses $mgUser.AssignedLicenses -RemoveLicenses @()
```

### <a name="move-a-user-to-a-different-subscription-license-plan"></a>将用户移动到其他订阅 (许可证计划) 

本示例将用户从 **SPE_E3** (Microsoft 365 E3) 许可计划升级到 **SPE_E5** (Microsoft 365 E5) 许可计划：

```powershell
$e3Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E3'
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'

# Unassign E3
Set-MgUserLicense -UserId "belindan@litwareinc.com" -AddLicenses @{} -RemoveLicenses @($e3Sku.SkuId)
# Assign E5
Set-MgUserLicense -UserId "belindan@litwareinc.com" -AddLicenses @{SkuId = $e5Sku.SkuId} -RemoveLicenses @()
```

可以使用此命令验证用户帐户的订阅更改。

```powershell
Get-MgUserLicenseDetail -UserId "belindan@litwareinc.com"
```

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

>[!Note]
>Set-AzureADUserLicense cmdlet 计划停用。 请将脚本迁移到 Microsoft Graph SDK 的 Set-MgUserLicense cmdlet，如上所述。 有关详细信息，请参阅[迁移应用以从 Microsoft Graph 访问许可证管理 API](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366)。
>

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  

接下来，使用此命令列出租户的许可证计划。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下来，获取要向其添加许可证的帐户的登录名称，也称为 UPN)  (用户主体名称。

接下来，确保用户帐户已分配使用位置。

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

如果没有分配使用位置，可以使用以下命令分配一个使用位置：

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

最后，指定用户登录名称和许可证计划名称并运行这些命令。

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

>[!Note]
>Set-MsolUserLicense和New-MsolUser (-LicenseAssignment) cmdlet 计划停用。 请将脚本迁移到 Microsoft Graph SDK 的 Set-MgUserLicense cmdlet，如上所述。 有关详细信息，请参阅[迁移应用以从 Microsoft Graph 访问许可证管理 API](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366)。
>

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

运行该 `Get-MsolAccountSku` 命令以查看组织中每个计划的可用许可计划和可用许可证数。 每个计划中的可用许可证数是 ActiveUnitsWarningUnitsConsumedUnits -  - 。 有关许可计划、许可证和服务的详细信息，请参 [阅 PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)。

>[!Note]
>PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。 若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。
>

若要在组织中查找未经许可的帐户，请运行此命令。

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

只能将许可证分配给将 **UsageLocation** 属性设置为有效 ISO 3166-1 alpha-2 国家/地区代码的用户帐户。 例如，US 代表美国，FR 代表法国。 某些Microsoft 365服务在某些国家/地区不可用。 有关详细信息，请参阅[关于许可证限制](https://go.microsoft.com/fwlink/p/?LinkId=691730)。
    
若要查找没有 **UsageLocation 值的** 帐户，请运行此命令。

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

若要在帐户上设置 **UsageLocation** 值，请运行此命令。

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

例如：

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
如果使用 **Get-MsolUser** cmdlet，而未使用 **-All** 参数，只返回前 500 个帐户。

### <a name="assigning-licenses-to-user-accounts"></a>将许可证分配给用户帐户
    
若要向用户分配许可证，请在 PowerShell 中使用以下命令。
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

本示例将 **litwareinc：ENTERPRISEPACK** (Office 365 企业版 E3) 许可计划的许可证分配给未经许可的用户 **belindan\@ litwareinc.com**：
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

若要向所有未授权用户分配许可证，请运行此命令。
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>您无法使用相同的许可计划为用户分配多个许可证。 如果没有足够可用的许可证，将按照 **Get-MsolUser** cmdlet 返回的顺序为用户分配许可证，直到可用许可证用尽。
>

本示例将 **litwareinc：ENTERPRISEPACK** (Office 365 企业版 E3) 许可计划的许可证分配给所有未经许可的用户：
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

本示例在美国中将这些相同的许可证分配给销售部门中的未授权用户：
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>使用 Azure Active Directory PowerShell for Graph 模块) 将用户移动到其他订阅 (许可证计划

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
接下来，获取要为其切换订阅的用户帐户的登录名称，也称为 UPN)  (用户主体名称。

接下来，使用此命令列出租户的订阅 (许可证计划) 。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下来，列出用户帐户当前具有这些命令的订阅。

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

确定用户当前 (FROM 订阅) 以及用户 (TO 订阅) 移动到的订阅。

最后，指定 TO 和 FROM 订阅名称 (SKU 部件号) 并运行这些命令。

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

可以使用这些命令验证用户帐户的订阅更改。

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
