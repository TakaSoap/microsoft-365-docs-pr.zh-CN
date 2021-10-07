---
title: 使用 PowerShell Microsoft 365用户帐户分配许可证
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
description: 本文将了解如何使用 PowerShell 向未授权Microsoft 365分配许可证。
ms.openlocfilehash: b9f076e4856820d9f10e4cf92718dd6ddd3971c5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60186773"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>使用 PowerShell Microsoft 365用户帐户分配许可证

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

在从许可计划为其帐户Microsoft 365许可证之前，用户才能使用任何服务。 可以使用 PowerShell 将许可证快速分配给未授权的帐户。 

必须先为用户帐户分配位置。 指定位置是创建新用户帐户的必需[Microsoft 365 管理中心。](../admin/add-users/add-users.md) 

默认情况下，从本地 Active Directory 域服务同步的帐户没有指定位置。 你可以从以下位置为这些帐户配置位置：

- Microsoft 365 管理员中心
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - Azure [门户 (](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) Active **Directory**>  >  用户帐户>**配置文件** 联系人  >  **信息**  >  **""国家/地区") 。**

>[!Note]
>[了解如何使用用户帐户分配许可证Microsoft 365 管理中心。](../admin/manage/assign-licenses-to-users.md) 有关其他资源的列表，请参阅管理 [用户和组](/admin)。
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  

接下来，使用此命令列出租户的许可证计划。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下来，获取要添加许可证的帐户的登录名，也称为 UPN (用户) 。

接下来，确保用户帐户分配了使用位置。

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

如果没有分配使用位置，可以使用以下命令分配一个：

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

请注意，当此模块的功能在适用于 Graph 模块的更高版本[的 PowerShell](/powershell/azuread/v2/azureactivedirectory)中可用时，我们将开始Azure Active Directory弃用此模块。 我们建议创建新 PowerShell 脚本的客户使用较新的模块而不是此模块。

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

运行 `Get-MsolAccountSku` 命令以查看组织中可用的许可计划以及每个计划的可用许可证数量。 每个计划中可用的许可证数量为 **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**。 有关许可计划、许可证和服务的信息，请参阅 [使用 PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)。

>[!Note]
>PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。 若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。
>

若要查找组织中未授权的帐户，请运行此命令。

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

只能将许可证分配给 **UsageLocation** 属性设置为有效的 ISO 3166-1 alpha-2 国家/地区代码的用户帐户。 例如，US 代表美国，FR 代表法国。 某些Microsoft 365服务在某些国家/地区不可用。 有关详细信息，请参阅[关于许可证限制](https://go.microsoft.com/fwlink/p/?LinkId=691730)。
    
若要查找没有 **UsageLocation** 值的帐户，请运行此命令。

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

若要在 **帐户上设置 UsageLocation** 值，请运行此命令。

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

例如：

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
如果使用 **Get-MsolUser** cmdlet，而未使用 **-All** 参数，只返回前 500 个帐户。

### <a name="assigning-licenses-to-user-accounts"></a>向用户帐户分配许可证
    
若要向用户分配许可证，请使用 PowerShell 中的以下命令。
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

此示例将 **litwareinc：ENTERPRISEPACK** (Office 365 企业版 E3 许可) 许可证计划中的许可证分配给未授权用户 **belindan \@** litwareinc.com：
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

若要将许可证分配给所有未授权的用户，请运行此命令。
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>您无法使用相同的许可计划为用户分配多个许可证。 如果没有足够可用的许可证，将按照 **Get-MsolUser** cmdlet 返回的顺序为用户分配许可证，直到可用许可证用尽。
>

此示例将 **litwareinc：ENTERPRISEPACK** (Office 365 企业版 E3) 许可证计划中的许可证分配给所有未授权用户：
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

本示例将相同的许可证分配给美国销售部门的未授权用户：
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>使用 PowerShell for (模块将) 移动到其他订阅Azure Active Directory许可证Graph计划

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
接下来，获取要切换订阅的用户帐户的登录名，也称为 UPN (用户) 。

接下来，使用此命令 (租户) 许可证计划的订阅。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下来，使用这些命令列出用户帐户当前具有的订阅。

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

确定用户当前 (FROM) 订阅订阅的订阅，以及用户 (TO 订阅) 。

最后，使用 SKU (指定 TO 和 FROM) 并运行这些命令。

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
