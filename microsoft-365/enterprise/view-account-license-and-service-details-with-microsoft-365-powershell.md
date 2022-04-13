---
title: 使用 PowerShell 查看Microsoft 365帐户许可证和服务详细信息
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
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
- PowerShell
- Ent_Office_Other
- LIL_Placement
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: 说明如何使用 PowerShell 确定已分配给用户的Microsoft 365服务。
ms.openlocfilehash: 2789026e2e22bbae3e84e91ada7ad21af2252f03
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823951"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a>使用 PowerShell 查看Microsoft 365帐户许可证和服务详细信息

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

在Microsoft 365中，许可计划 (的许可证也称为 SKU 或Microsoft 365计划，) 使用户能够访问为这些计划定义的Microsoft 365服务。 但是，用户可能无法访问当前分配给他们的许可证中提供的所有服务。 可以使用 PowerShell Microsoft 365查看用户帐户上的服务状态。

有关许可计划、许可证和服务的详细信息，请参 [阅 PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)。

## <a name="use-the-microsoft-graph-powershell-sdk"></a>使用 Microsoft Graph PowerShell SDK

首先，[连接到Microsoft 365租户](/graph/powershell/get-started#authentication)。

读取用户属性（包括许可证详细信息）需要 User.Read.All 权限范围或[“获取用户”图形 API参考页](/graph/api/user-get)中列出的其他权限之一。

```powershell
Connect-Graph -Scopes User.Read.All
```

接下来，使用此命令列出租户的许可证计划。

```powershell
Get-MgSubscribedSku
```

使用这些命令列出每个许可计划中可用的服务。

```powershell

$allSKUs = Get-MgSubscribedSku -Property SkuPartNumber, ServicePlans 
$allSKUs | ForEach-Object {
    Write-Host "Service Plan:" $_.SkuPartNumber
    $_.ServicePlans | ForEach-Object {$_}
}

```

使用这些命令列出分配给用户帐户的许可证。

```powershell
Get-MgUserLicenseDetail -UserId "<user sign-in name (UPN)>"
```

例如：

```powershell
Get-MgUserLicenseDetail -UserId "belindan@litwareinc.com"
```

### <a name="to-view-services-for-a-user-account"></a>查看用户帐户的服务

若要查看用户有权访问的所有Microsoft 365服务，请使用以下语法：
  
```powershell
(Get-MgUserLicenseDetail -UserId <user account UPN> -Property ServicePlans)[<LicenseIndexNumber>].ServicePlans
```

此示例演示用户 BelindaN@litwareinc.com 有权访问的服务。 这会显示与分配到其帐户的所有许可证关联的服务。
  
```powershell
(Get-MgUserLicenseDetail -UserId belindan@litwareinc.com -Property ServicePlans).ServicePlans
```

此示例显示用户 BelindaN@litwareinc.com 有权从分配到其帐户的第一个许可证中访问的服务， (索引号为 0) 。
  
```powershell
(Get-MgUserLicenseDetail -UserId belindan@litwareinc.com -Property ServicePlans)[0].ServicePlans
```

若要查看已分配 *多个许可证* 的用户的所有服务，请使用以下语法：

```powershell
$userUPN="<user account UPN>"
$allLicenses = Get-MgUserLicenseDetail -UserId $userUPN -Property SkuPartNumber, ServicePlans
$allLicenses | ForEach-Object {
    Write-Host "License:" $_.SkuPartNumber
    $_.ServicePlans | ForEach-Object {$_}
}

```

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
接下来，使用此命令列出租户的许可证计划。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

使用这些命令列出每个许可计划中可用的服务。

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

使用这些命令列出分配给用户帐户的许可证。

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

接下来，运行此命令，列出组织中可用的许可计划。 

```powershell
Get-MsolAccountSku
```
>[!Note]
>PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。 若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。
>

接下来，运行此命令，列出每个许可计划中可用的服务，以及它们 (索引号) 列出的顺序。

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
使用此命令列出分配给用户的许可证，以及其列出顺序 (索引号) 。

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a>查看用户帐户的服务

若要查看用户有权访问的所有Microsoft 365服务，请使用以下语法：
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

此示例演示用户 BelindaN@litwareinc.com 有权访问的服务。 这会显示与分配到其帐户的所有许可证关联的服务。
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

此示例显示用户 BelindaN@litwareinc.com 有权从分配到其帐户的第一个许可证中访问的服务， (索引号为 0) 。
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

若要查看已分配 *多个许可证* 的用户的所有服务，请使用以下语法：

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
