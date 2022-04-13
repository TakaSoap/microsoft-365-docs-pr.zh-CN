---
title: 使用 PowerShell 从用户帐户中删除Microsoft 365许可证
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/23/2020
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
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: 介绍如何使用 PowerShell 删除以前分配给用户的Microsoft 365许可证。
ms.openlocfilehash: c3317c651c561da4c8650e45ba3b64a135a1f6ce
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823137"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>使用 PowerShell 从用户帐户中删除Microsoft 365许可证

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

>[!Note]
>[了解如何使用Microsoft 365 管理中心从用户帐户中删除许可证](../admin/manage/remove-licenses-from-users.md)。 有关其他资源的列表，请参阅 [“管理用户和组](/admin)”。
>

## <a name="use-the-microsoft-graph-powershell-sdk"></a>使用 Microsoft Graph PowerShell SDK

首先，[连接到Microsoft 365租户](/graph/powershell/get-started#authentication)。

为用户分配和删除许可证需要 User.ReadWrite.All 权限范围或[“分配许可证”图形 API参考页](/graph/api/user-assignlicense)中列出的其他权限之一。

需要组织.Read.All 权限范围才能读取租户中可用的许可证。

```powershell
Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All
```

若要查看组织中的许可计划信息，请参阅以下主题：

- [使用 PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)

- [使用 PowerShell 查看帐户许可证和服务详细信息](view-account-license-and-service-details-with-microsoft-365-powershell.md)

### <a name="removing-licenses-from-user-accounts"></a>从用户帐户中删除许可证

要从现有的用户帐户中删除许可证，请使用以下语法：
  
```powershell
Set-MgUserLicense -UserId "<Account>" -RemoveLicenses @("<AccountSkuId1>") -AddLicenses @{}
```

本示例从用户 **BelindaN@litwareinc.com** 中删除SPE_E5 **(Microsoft 365 E5)** 许可计划：

```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
Set-MgUserLicense -UserId "belindan@litwareinc.com" -RemoveLicenses @($e5Sku.SkuId) -AddLicenses @{}
```

若要从一组现有许可用户中删除所有许可证，请使用以下语法：

```powershell
$licensedUsers = Get-MgUser -Filter 'assignedLicenses/$count ne 0' `
    -ConsistencyLevel eventual -CountVariable licensedUserCount -All `
    -Select UserPrincipalName,DisplayName,AssignedLicenses

foreach($user in $licensedUsers)
{
    $licencesToRemove = $user.AssignedLicenses | Select -ExpandProperty SkuId
    $user = Set-MgUserLicense -UserId $user.UserPrincipalName -RemoveLicenses $licencesToRemove -AddLicenses @{} 
}
```

释放许可证的另一种方法是删除用户帐户。 有关详细信息，请参阅 [使用 PowerShell 删除和还原用户帐户](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

>Set-AzureADUserLicense cmdlet 计划停用。 请将脚本迁移到 Microsoft Graph SDK 的 Set-MgUserLicense cmdlet，如上所述。 有关详细信息，请参阅[迁移应用以从 Microsoft Graph 访问许可证管理 API](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366)。
>

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

接下来，使用此命令列出租户的许可证计划。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下来，获取要为其删除许可证的帐户的登录名称，也称为 UPN)  (用户主体名称。

最后，指定用户登录和许可证计划名称，删除“<”和“>”字符，并运行这些命令。

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

若要删除特定用户帐户的所有许可证，请指定用户登录名称，删除“<”和“>”字符，并运行这些命令。

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $Licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块

>[!Note]
>Set-MsolUserLicense和New-MsolUser (-LicenseAssignment) cmdlet 计划停用。 请将脚本迁移到 Microsoft Graph SDK 的 Set-MgUserLicense cmdlet，如上所述。 有关详细信息，请参阅[迁移应用以从 Microsoft Graph 访问许可证管理 API](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/migrate-your-apps-to-access-the-license-managements-apis-from/ba-p/2464366)。
>

首先，[连接到Microsoft 365租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
   
要查看组织中的许可计划 (**AccountSkuID**) 信息，请参阅下列主题：
    
  - [使用 PowerShell 查看许可证和服务](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [使用 PowerShell 查看帐户许可证和服务详细信息](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
如果使用 **Get-MsolUser** cmdlet，而未使用 _-All_ 参数，只返回前 500 个帐户。
    
### <a name="removing-licenses-from-user-accounts"></a>从用户帐户中删除许可证

要从现有的用户帐户中删除许可证，请使用以下语法：
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。 若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。
>

本示例从用户帐户 BelindaN@litwareinc.com 中删除 **litwareinc：ENTERPRISEPACK** (Office 365 企业版 E3) 许可证。
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>不能使用 `Set-MsolUserLicense` 该 cmdlet 从 *已取消* 的许可证中取消分配用户。 必须针对Microsoft 365 管理中心中的每个用户帐户单独执行此操作。
>

若要从一组现有许可用户中删除所有许可证，请使用以下任一方法：
  
- **根据现有帐户属性筛选帐户** 为此，请使用以下语法：
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

本示例从美国中销售部门的所有用户帐户中删除所有许可证。
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **对特定许可证使用特定帐户的列表** 为此，请执行以下步骤：
    
1. 创建并保存一个文本文件，其中每一行都有一个帐户，如下所示：
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. 使用以下语法：
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
本示例从文本文件 C：\My Documents\Accounts.txt 中定义的用户帐户中删除 **litwareinc：ENTERPRISEPACK** (Office 365 企业版 E3) 许可证。
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

若要从所有现有用户帐户中删除所有许可证，请使用以下语法：
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

释放许可证的另一种方法是删除用户帐户。 有关详细信息，请参阅 [使用 PowerShell 删除和还原用户帐户](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)。
  
## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
