---
title: 在分配用户Microsoft 365禁用对服务的访问权限
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: 了解如何使用 PowerShell for Microsoft 365 同时向用户帐户分配许可证和禁用特定服务Microsoft 365。
ms.openlocfilehash: 5b7130930097970f5cfabc9a7599c211393b7c7a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189161"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>在分配用户Microsoft 365禁用对服务的访问权限

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

Microsoft 365订阅随单个服务的服务计划一起提供。 Microsoft 365向用户分配许可证时，管理员通常需要禁用某些计划。 按照本文中的说明，您可以分配一个Microsoft 365许可证，同时使用 PowerShell 为单个用户帐户或多个用户帐户禁用特定服务计划。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。


接下来，使用此命令列出租户的许可证计划。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下来，获取要添加许可证的帐户的登录名，也称为 UPN (用户) 。

接下来，编译要启用的服务列表。 有关许可证计划的完整列表 (产品名称) 包括的服务计划及其对应的友好名称，请参阅许可的产品名称和服务计划 [标识符](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

对于下面的命令块，填写用户帐户的用户主体名称、SKU 部件号以及启用和删除说明性文本和字符的服务计划 \< and > 列表。 然后，在 PowerShell 命令提示符下运行生成的命令。

```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

首先，[连接到你的Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

接下来，运行此命令以查看当前订阅：

```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。 若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。
>

在命令的  `Get-MsolAccountSku` 显示中：

- **AccountSkuId** 是组织采用 ： \<OrganizationName> 格式 \<Subscription> 的订阅。 \<OrganizationName>是当你在组织中注册时提供Microsoft 365，并且对于你的组织是唯一的。 \<Subscription>该值用于特定订阅。 例如，对于 litwareinc：ENTERPRISEPACK，组织名称为 litwareinc，订阅名称为 ENTERPRISEPACK (Office 365 企业版 E3) 。

- **ActiveUnits** 是已购买订阅的许可证数。

- **WarningUnits** 是订阅中尚未续订且将在 30 天宽限期后过期的许可证数量。

- **ConsumedUnits** 是已分配给订阅用户的许可证数。

请注意包含要许可的用户Microsoft 365订阅的 AccountSkuId。 此外，还要确保有足够的许可证来从 **ActiveUnits** (**分配 ConsumedUnits**) 。

接下来，运行此命令以查看有关所有Microsoft 365中可用的服务计划的详细信息：

```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

从此命令的显示中，确定在向用户分配许可证时要禁用的服务计划。

以下是服务计划及其相应服务Microsoft 365列表。

下表显示了最常见的Microsoft 365服务计划及其友好名称。 服务计划列表可能会有所不同。

|**服务计划**|**说明**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure 权限管理 (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |*Microsoft 365 企业应用版 (之前名为 Office 365 专业增强版)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online 计划 2  <br/> |

有关许可证计划的完整列表 (产品名称) 包括的服务计划及其对应的友好名称，请参阅许可的产品名称和服务计划 [标识符](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

现在，您具有要禁用的 AccountSkuId 和服务计划，您可以为单个用户或多个用户分配许可证。

### <a name="for-a-single-user"></a>对于单个用户

对于单个用户，请填写用户帐户的用户主体名称、AccountSkuId 以及禁用和删除说明文本和字符的服务 \< and > 计划列表。 然后，在 PowerShell 命令提示符下运行生成的命令。

```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

下面是针对 contoso：ENTERPRISEPACK 许可证的名为 belindan@contoso.com 的帐户的示例命令块，要禁用的服务计划包括 RMS_S_ENTERPRISE、SWAY、INTUNE_O365 和 YAMMER_ENTERPRISE：

```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a>对于多个用户

若要为多个用户执行此管理任务，请为包含 UserPrincipalName 和 UsageLocation (CSV) 创建一个逗号分隔值。 下面是一个示例：

```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

接下来，填写输入和输出 CSV 文件的位置、帐户 SKU ID 和要禁用的服务计划列表，然后在 PowerShell 命令提示符处运行生成的命令。

```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

此 PowerShell 命令块：

- 显示每个用户的用户主体名称。

- 向每个用户分配自定义许可证。

- 创建包含已处理的所有用户的 CSV 文件，并显示其许可证状态。

## <a name="see-also"></a>另请参阅

[使用 PowerShell Microsoft 365访问服务](disable-access-to-services-with-microsoft-365-powershell.md)

[使用 PowerShell 禁用对 Sway 的访问](disable-access-to-sway-with-microsoft-365-powershell.md)

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)