---
title: 从使用 PowerShell 的用户帐户中删除 Microsoft 365 许可证
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
description: 说明如何使用 PowerShell 删除之前分配给用户的 Microsoft 365 许可证。
ms.openlocfilehash: 7651f300dbf7a57ce163096d500401365e624663
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235450"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a><span data-ttu-id="6be93-103">从使用 PowerShell 的用户帐户中删除 Microsoft 365 许可证</span><span class="sxs-lookup"><span data-stu-id="6be93-103">Remove Microsoft 365 licenses from user accounts with PowerShell</span></span>

<span data-ttu-id="6be93-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="6be93-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

>[!Note]
><span data-ttu-id="6be93-105">了解如何使用 Microsoft 365 管理中心[删除用户帐户的许可证](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)。</span><span class="sxs-lookup"><span data-stu-id="6be93-105">[Learn how to remove licenses from user accounts](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="6be93-106">有关其他资源的列表，请参阅 [管理用户和组](https://docs.microsoft.com/microsoft-365/admin/add-users/)。</span><span class="sxs-lookup"><span data-stu-id="6be93-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6be93-107">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="6be93-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6be93-108">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="6be93-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="6be93-109">接下来，使用此命令列出租户的许可证计划。</span><span class="sxs-lookup"><span data-stu-id="6be93-109">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="6be93-110">接下来，获取要删除其许可证（也称为用户主体名称 (UPN) ）的帐户的登录名。</span><span class="sxs-lookup"><span data-stu-id="6be93-110">Next, get the sign-in name of the account for which you want remove a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="6be93-111">最后，指定用户登录和许可证计划名称，删除 "<" 和 ">" 字符，然后运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="6be93-111">Finally, specify the user sign-in and license plan names, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

<span data-ttu-id="6be93-112">若要删除特定用户帐户的所有许可证，请指定用户登录名，删除 "<" 和 ">" 字符，然后运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="6be93-112">To remove all of the licenses for a specific user account, specify the user sign-in name, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
if($userList -is [array]) {
for ($i=0; $i -lt $userList.Count; $i++) {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList[$i].SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList[$i].SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}
} else {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList.SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList.SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6be93-113">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="6be93-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6be93-114">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6be93-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
   
<span data-ttu-id="6be93-115">要查看组织中的许可计划 (**AccountSkuID**) 信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="6be93-115">To view the licensing plan (**AccountSkuID**) information in your organization, see the following topics:</span></span>
    
  - [<span data-ttu-id="6be93-116">使用 PowerShell 查看许可证和服务</span><span class="sxs-lookup"><span data-stu-id="6be93-116">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="6be93-117">使用 PowerShell 查看帐户许可证和服务详细信息</span><span class="sxs-lookup"><span data-stu-id="6be93-117">View account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
<span data-ttu-id="6be93-118">如果使用 **Get-MsolUser** cmdlet，而未使用 _-All_ 参数，只返回前 500 个帐户。</span><span class="sxs-lookup"><span data-stu-id="6be93-118">If you use the **Get-MsolUser** cmdlet without using the _-All_ parameter, only the first 500 accounts are returned.</span></span>
    
### <a name="removing-licenses-from-user-accounts"></a><span data-ttu-id="6be93-119">从用户帐户中删除许可证</span><span class="sxs-lookup"><span data-stu-id="6be93-119">Removing licenses from user accounts</span></span>

<span data-ttu-id="6be93-120">要从现有的用户帐户中删除许可证，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6be93-120">To remove licenses from an existing user account, use the following syntax:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
><span data-ttu-id="6be93-121">PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="6be93-121">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="6be93-122">若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。</span><span class="sxs-lookup"><span data-stu-id="6be93-122">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="6be93-123">此示例从用户帐户 BelindaN@litwareinc.com 中删除 **litwareinc： ENTERPRISEPACK** (Office 365 Enterprise E3) 许可证。</span><span class="sxs-lookup"><span data-stu-id="6be93-123">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
><span data-ttu-id="6be93-124">无法使用 `Set-MsolUserLicense` cmdlet 从 *已取消* 的许可证中取消分配用户。</span><span class="sxs-lookup"><span data-stu-id="6be93-124">You cannot use the `Set-MsolUserLicense` cmdlet to unassign users from *canceled* licenses.</span></span> <span data-ttu-id="6be93-125">您必须为 Microsoft 365 管理中心中的每个用户帐户单独执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6be93-125">You must do this individually for each user account in the Microsoft 365 admin center.</span></span>
>

<span data-ttu-id="6be93-126">若要从一组现有许可用户中删除所有许可证，请使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="6be93-126">To remove all licenses from a group of existing licensed users, use either of the following methods:</span></span>
  
- <span data-ttu-id="6be93-127">**基于现有帐户属性筛选帐户** 为此，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6be93-127">**Filter the accounts based on an existing account attribute** To do this, use the following syntax:</span></span>
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="6be93-128">本示例将从美国的销售部的所有用户帐户中删除所有许可证。</span><span class="sxs-lookup"><span data-stu-id="6be93-128">This example removes all licenses from all user accounts in the Sales department in the United States.</span></span>
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- <span data-ttu-id="6be93-129">**对特定的许可证使用特定帐户的列表** 为此，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6be93-129">**Use a list of specific accounts for a specific license** To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="6be93-130">创建并保存一个文本文件，其中每一行都有一个帐户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6be93-130">Create and save a text file that contains one account on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. <span data-ttu-id="6be93-131">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6be93-131">Use the following syntax:</span></span>
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
<span data-ttu-id="6be93-132">本示例从文本文件 C:\My Documents\Accounts.txt 中定义的用户帐户中删除 **litwareinc： ENTERPRISEPACK** (Office 365 企业版 E3) 许可证。</span><span class="sxs-lookup"><span data-stu-id="6be93-132">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user accounts defined in the text file C:\My Documents\Accounts.txt.</span></span>
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

<span data-ttu-id="6be93-133">若要从所有现有用户帐户中删除所有许可证，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6be93-133">To remove all licenses from all existing user accounts, use the following syntax:</span></span>
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="6be93-134">释放许可证的另一种方法是删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6be93-134">Another way to free up a license is by deleting the user account.</span></span> <span data-ttu-id="6be93-135">有关详细信息，请参阅 [Delete and restore user accounts With PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="6be93-135">For more information, see [Delete and restore user accounts with PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6be93-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6be93-136">See also</span></span>

[<span data-ttu-id="6be93-137">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="6be93-137">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6be93-138">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6be93-138">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6be93-139">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="6be93-139">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

