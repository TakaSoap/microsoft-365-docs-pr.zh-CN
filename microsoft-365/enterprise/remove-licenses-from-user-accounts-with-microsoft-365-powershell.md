---
title: 使用 PowerShell 从用户帐户中删除 Microsoft 365 许可证
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- PowerShell
- Ent_Office_Other
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: 介绍如何使用 PowerShell 删除以前分配给用户的 Microsoft 365 许可证。
ms.openlocfilehash: 8ae7ca1013e26a60f16177f2dab7ced4cc8b97a8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289589"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>使用 PowerShell 从用户帐户中删除 Microsoft 365 许可证

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

>[!Note]
>[了解如何使用](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) Microsoft 365 管理中心从用户帐户中删除许可证。 有关其他资源的列表，请参阅["管理用户和组"。](https://docs.microsoft.com/microsoft-365/admin/add-users/)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>使用用于图表模块的 Azure Active Directory PowerShell

首先 [，连接到你的 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

接下来，使用此命令列出租户的许可证计划。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

接下来，获取要删除其许可证的帐户的登录名，也称为 UPN (用户) 。

最后，指定用户登录和许可证计划名称，删除"<"和">"字符，然后运行这些命令。

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

若要删除特定用户帐户的所有许可证，请指定用户登录名，删除"<"和">"字符，然后运行这些命令。

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

首先 [，连接到你的 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
   
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

此示例从用户帐户中删除 **litwareinc：ENTERPRISEPACK** (Office 365 企业版 E3) 许可证BelindaN@litwareinc.com。
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>不能使用 `Set-MsolUserLicense` cmdlet 取消分配用户取消 *许可证* 。 你必须为 Microsoft 365 管理中心的每个用户帐户单独执行此操作。
>

若要从一组现有许可用户中删除所有许可证，请使用以下任一方法：
  
- **基于现有帐户属性筛选帐户** 为此，请使用以下语法：
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

本示例删除美国销售部门的所有用户帐户的所有许可证。
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **使用特定许可证的特定帐户列表** 为此，请执行以下步骤：
    
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
此示例从文本文件 C：\My (中定义的用户帐户中删除 **litwareinc：ENTERPRISEPACK**)  (Office 365 企业版 E3 Documents\Accounts.txt。
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

若要删除所有现有用户帐户的所有许可证，请使用以下语法：
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

释放许可证的另一种方法是删除用户帐户。 有关详细信息，请参阅使用 [PowerShell 删除和还原用户帐户](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)。
  
## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)

