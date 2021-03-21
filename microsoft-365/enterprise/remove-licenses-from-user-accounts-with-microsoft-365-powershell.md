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
description: 介绍如何使用 PowerShell 删除之前分配给用户的 Microsoft 365 许可证。
ms.openlocfilehash: 9944d1ab056d109b6bf71a44fe01acef78ce1f14
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920664"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a><span data-ttu-id="875a3-103">使用 PowerShell 从用户帐户中删除 Microsoft 365 许可证</span><span class="sxs-lookup"><span data-stu-id="875a3-103">Remove Microsoft 365 licenses from user accounts with PowerShell</span></span>

<span data-ttu-id="875a3-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="875a3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

>[!Note]
><span data-ttu-id="875a3-105">[了解如何使用](../admin/manage/remove-licenses-from-users.md) Microsoft 365 管理中心删除用户帐户的许可证。</span><span class="sxs-lookup"><span data-stu-id="875a3-105">[Learn how to remove licenses from user accounts](../admin/manage/remove-licenses-from-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="875a3-106">有关其他资源的列表，请参阅管理 [用户和组](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="875a3-106">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="875a3-107">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="875a3-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="875a3-108">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="875a3-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="875a3-109">接下来，使用此命令列出租户的许可证计划。</span><span class="sxs-lookup"><span data-stu-id="875a3-109">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="875a3-110">接下来，获取要删除其许可证的帐户的登录名，也称为 UPN (用户) 。</span><span class="sxs-lookup"><span data-stu-id="875a3-110">Next, get the sign-in name of the account for which you want remove a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="875a3-111">最后，指定用户登录和许可证计划名称，删除"<"和">"字符，然后运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="875a3-111">Finally, specify the user sign-in and license plan names, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

<span data-ttu-id="875a3-112">若要删除特定用户帐户的所有许可证，请指定用户登录名，删除"<"和">"字符，然后运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="875a3-112">To remove all of the licenses for a specific user account, specify the user sign-in name, remove the "<" and ">" characters, and run these commands.</span></span>

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

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="875a3-113">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="875a3-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="875a3-114">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="875a3-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
   
<span data-ttu-id="875a3-115">要查看组织中的许可计划 (**AccountSkuID**) 信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="875a3-115">To view the licensing plan (**AccountSkuID**) information in your organization, see the following topics:</span></span>
    
  - [<span data-ttu-id="875a3-116">使用 PowerShell 查看许可证和服务</span><span class="sxs-lookup"><span data-stu-id="875a3-116">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="875a3-117">使用 PowerShell 查看帐户许可证和服务详细信息</span><span class="sxs-lookup"><span data-stu-id="875a3-117">View account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
<span data-ttu-id="875a3-118">如果使用 **Get-MsolUser** cmdlet，而未使用 _-All_ 参数，只返回前 500 个帐户。</span><span class="sxs-lookup"><span data-stu-id="875a3-118">If you use the **Get-MsolUser** cmdlet without using the _-All_ parameter, only the first 500 accounts are returned.</span></span>
    
### <a name="removing-licenses-from-user-accounts"></a><span data-ttu-id="875a3-119">从用户帐户删除许可证</span><span class="sxs-lookup"><span data-stu-id="875a3-119">Removing licenses from user accounts</span></span>

<span data-ttu-id="875a3-120">要从现有的用户帐户中删除许可证，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="875a3-120">To remove licenses from an existing user account, use the following syntax:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
><span data-ttu-id="875a3-121">PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="875a3-121">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="875a3-122">若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。</span><span class="sxs-lookup"><span data-stu-id="875a3-122">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="875a3-123">此示例从用户帐户 **管理 (删除 litwareinc：ENTERPRISEPACK**) Office 365 企业版 E3 BelindaN@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="875a3-123">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
><span data-ttu-id="875a3-124">不能使用 `Set-MsolUserLicense` cmdlet 取消为用户分配 *已取消的许可证* 。</span><span class="sxs-lookup"><span data-stu-id="875a3-124">You cannot use the `Set-MsolUserLicense` cmdlet to unassign users from *canceled* licenses.</span></span> <span data-ttu-id="875a3-125">你必须为 Microsoft 365 管理中心的每个用户帐户分别执行这一操作。</span><span class="sxs-lookup"><span data-stu-id="875a3-125">You must do this individually for each user account in the Microsoft 365 admin center.</span></span>
>

<span data-ttu-id="875a3-126">若要删除一组现有许可用户的所有许可证，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="875a3-126">To remove all licenses from a group of existing licensed users, use either of the following methods:</span></span>
  
- <span data-ttu-id="875a3-127">**基于现有帐户属性筛选帐户** 为此，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="875a3-127">**Filter the accounts based on an existing account attribute** To do this, use the following syntax:</span></span>
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="875a3-128">本示例删除美国销售部门的所有用户帐户的所有许可证。</span><span class="sxs-lookup"><span data-stu-id="875a3-128">This example removes all licenses from all user accounts in the Sales department in the United States.</span></span>
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- <span data-ttu-id="875a3-129">**使用特定许可证的特定帐户列表** 为此，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="875a3-129">**Use a list of specific accounts for a specific license** To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="875a3-130">创建并保存一个文本文件，其中每一行都有一个帐户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="875a3-130">Create and save a text file that contains one account on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. <span data-ttu-id="875a3-131">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="875a3-131">Use the following syntax:</span></span>
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
<span data-ttu-id="875a3-132">此示例从文本文件 C：Documents\Accounts.txt\My (中定义的用户帐户中删除 **litwareinc：ENTERPRISEPACK** (Office 365 企业版 E3) 许可证。</span><span class="sxs-lookup"><span data-stu-id="875a3-132">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user accounts defined in the text file C:\My Documents\Accounts.txt.</span></span>
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

<span data-ttu-id="875a3-133">若要删除所有现有用户帐户的所有许可证，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="875a3-133">To remove all licenses from all existing user accounts, use the following syntax:</span></span>
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="875a3-134">释放许可证的另一种方法是删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="875a3-134">Another way to free up a license is by deleting the user account.</span></span> <span data-ttu-id="875a3-135">有关详细信息，请参阅使用 [PowerShell 删除和还原用户帐户](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="875a3-135">For more information, see [Delete and restore user accounts with PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="875a3-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="875a3-136">See also</span></span>

[<span data-ttu-id="875a3-137">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="875a3-137">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="875a3-138">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="875a3-138">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="875a3-139">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="875a3-139">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)