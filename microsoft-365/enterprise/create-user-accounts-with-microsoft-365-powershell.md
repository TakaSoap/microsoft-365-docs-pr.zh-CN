---
title: 使用 PowerShell 创建 Microsoft 365 用户帐户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: 如何使用 PowerShell 创建单个或多个 Microsoft 365 用户帐户。
ms.openlocfilehash: c3676acdec3bbba328809ee1528206bbc44f94f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907560"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="29a58-103">使用 PowerShell 创建 Microsoft 365 用户帐户</span><span class="sxs-lookup"><span data-stu-id="29a58-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="29a58-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="29a58-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="29a58-105">可以使用适用于 Microsoft 365 的 PowerShell 高效创建用户帐户，包括多个帐户。</span><span class="sxs-lookup"><span data-stu-id="29a58-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, including multiple accounts.</span></span>

<span data-ttu-id="29a58-106">在 PowerShell 中创建用户帐户时，始终需要某些帐户属性。</span><span class="sxs-lookup"><span data-stu-id="29a58-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="29a58-107">其他属性不是必需的，但非常重要。</span><span class="sxs-lookup"><span data-stu-id="29a58-107">Other properties aren't required but are important.</span></span> <span data-ttu-id="29a58-108">请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="29a58-108">See the following table.</span></span>
  
|<span data-ttu-id="29a58-109">**属性名称**</span><span class="sxs-lookup"><span data-stu-id="29a58-109">**Property name**</span></span>|<span data-ttu-id="29a58-110">**是否必需？**</span><span class="sxs-lookup"><span data-stu-id="29a58-110">**Required?**</span></span>|<span data-ttu-id="29a58-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="29a58-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="29a58-112">**DisplayName**</span><span class="sxs-lookup"><span data-stu-id="29a58-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="29a58-113">是</span><span class="sxs-lookup"><span data-stu-id="29a58-113">Yes</span></span>  <br/> |<span data-ttu-id="29a58-114">这是显示名称 Microsoft 365 服务中使用的服务。</span><span class="sxs-lookup"><span data-stu-id="29a58-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="29a58-115">例如 *，Caleb Sills*。</span><span class="sxs-lookup"><span data-stu-id="29a58-115">For example, *Caleb Sills*.</span></span> <br/> |
|<span data-ttu-id="29a58-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="29a58-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="29a58-117">是</span><span class="sxs-lookup"><span data-stu-id="29a58-117">Yes</span></span>  <br/> |<span data-ttu-id="29a58-118">这是用于登录 Microsoft 365 服务的帐户名称。</span><span class="sxs-lookup"><span data-stu-id="29a58-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="29a58-119">例如 *，CalebS \@ contoso.onmicrosoft.com*。</span><span class="sxs-lookup"><span data-stu-id="29a58-119">For example, *CalebS\@contoso.onmicrosoft.com*.</span></span>  <br/> |
|<span data-ttu-id="29a58-120">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="29a58-120">**FirstName**</span></span> <br/> |<span data-ttu-id="29a58-121">否</span><span class="sxs-lookup"><span data-stu-id="29a58-121">No</span></span>  <br/> ||
|<span data-ttu-id="29a58-122">**LastName**</span><span class="sxs-lookup"><span data-stu-id="29a58-122">**LastName**</span></span> <br/> |<span data-ttu-id="29a58-123">否</span><span class="sxs-lookup"><span data-stu-id="29a58-123">No</span></span>  <br/> ||
|<span data-ttu-id="29a58-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="29a58-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="29a58-125">否</span><span class="sxs-lookup"><span data-stu-id="29a58-125">No</span></span>  <br/> |<span data-ttu-id="29a58-126">这是许可计划 (也称为许可证计划或 SKU) 从中向用户帐户分配可用许可证。</span><span class="sxs-lookup"><span data-stu-id="29a58-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="29a58-127">许可证定义可供帐户使用 Microsoft 365 服务。</span><span class="sxs-lookup"><span data-stu-id="29a58-127">The license defines the Microsoft 365 services that are available to the account.</span></span> <span data-ttu-id="29a58-128">创建帐户时，不必向用户分配许可证，但该帐户必须具有访问 Microsoft 365 服务的许可证。</span><span class="sxs-lookup"><span data-stu-id="29a58-128">You don't have to assign a license to a user when you create the account, but the account must have a license to access Microsoft 365 services.</span></span> <span data-ttu-id="29a58-129">创建用户帐户后，您有 30 天的时间可以对该用户帐户授权。</span><span class="sxs-lookup"><span data-stu-id="29a58-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="29a58-130">**密码**</span><span class="sxs-lookup"><span data-stu-id="29a58-130">**Password**</span></span> <br/> |<span data-ttu-id="29a58-131">否</span><span class="sxs-lookup"><span data-stu-id="29a58-131">No</span></span>  <br/> | <span data-ttu-id="29a58-132">如果您没有指定密码，将向用户帐户分配一个随机密码，且该密码将显示在命令结果中。</span><span class="sxs-lookup"><span data-stu-id="29a58-132">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command.</span></span> <span data-ttu-id="29a58-133">如果指定密码，则密码需要为 8 到 16 个以下类型的 ASCII 文本字符：小写字母、大写字母、数字和符号。</span><span class="sxs-lookup"><span data-stu-id="29a58-133">If you specify a password, it needs to be 8 to 16 ASCII text characters of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span><br/> |
|<span data-ttu-id="29a58-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="29a58-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="29a58-135">否</span><span class="sxs-lookup"><span data-stu-id="29a58-135">No</span></span>  <br/> |<span data-ttu-id="29a58-136">这是一个由两位字母组成的有效 ISO 3166-1 国家/地区代码。</span><span class="sxs-lookup"><span data-stu-id="29a58-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="29a58-137">例如 *，US* 代表美国 *，FR* 代表法国。</span><span class="sxs-lookup"><span data-stu-id="29a58-137">For example, *US* for the United States, and *FR* for France.</span></span> <span data-ttu-id="29a58-138">提供此值很重要，因为某些 Microsoft 365 服务在某些国家/地区不可用。</span><span class="sxs-lookup"><span data-stu-id="29a58-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="29a58-139">无法将许可证分配给用户帐户，除非该帐户已配置此值。</span><span class="sxs-lookup"><span data-stu-id="29a58-139">You can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="29a58-140">有关详细信息，请参阅[关于许可证限制](https://go.microsoft.com/fwlink/p/?LinkId=691730)。</span><span class="sxs-lookup"><span data-stu-id="29a58-140">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span><br/> |

>[!Note]
><span data-ttu-id="29a58-141">[了解如何使用](../admin/add-users/add-users.md) Microsoft 365 管理中心创建用户帐户。</span><span class="sxs-lookup"><span data-stu-id="29a58-141">[Learn how to create user accounts](../admin/add-users/add-users.md) by using the Microsoft 365 admin center.</span></span>
> 
> <span data-ttu-id="29a58-142">有关其他资源的列表，请参阅管理 [用户和组](../admin/add-users/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="29a58-142">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="29a58-143">使用用于图表模块的 Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="29a58-143">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="29a58-144">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="29a58-144">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="29a58-145">连接后，使用以下语法创建单个帐户：</span><span class="sxs-lookup"><span data-stu-id="29a58-145">After you connect, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="29a58-146">本示例为美国用户 *Caleb Sills 创建一个帐户*：</span><span class="sxs-lookup"><span data-stu-id="29a58-146">This example creates an account for the US user *Caleb Sills*:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="29a58-147">使用用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块</span><span class="sxs-lookup"><span data-stu-id="29a58-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="29a58-148">首先， [连接到 Microsoft 365 租户](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="29a58-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="29a58-149">创建单个用户帐户</span><span class="sxs-lookup"><span data-stu-id="29a58-149">Create an individual user account</span></span>

<span data-ttu-id="29a58-150">若要创建单个帐户，请使用下面的语法：</span><span class="sxs-lookup"><span data-stu-id="29a58-150">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="29a58-151">PowerShell Core 不支持 Microsoft Azure Active Directory 模块，Windows PowerShell名称中具有 *Msol* 的模块和 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="29a58-151">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="29a58-152">从 Windows PowerShell 运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="29a58-152">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="29a58-153">若要列出可用的许可计划名称，请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="29a58-153">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="29a58-154">本示例为美国用户 *Caleb Sills* 创建一个帐户，然后从 `contoso:ENTERPRISEPACK` (Office 365 企业版 E3) 许可证计划分配许可证。</span><span class="sxs-lookup"><span data-stu-id="29a58-154">This example creates an account for the US user *Caleb Sills*, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="29a58-155">创建多个用户帐户</span><span class="sxs-lookup"><span data-stu-id="29a58-155">Create multiple user accounts</span></span>

1. <span data-ttu-id="29a58-p108">创建包含所需用户帐户信息的逗号分隔值 (CSV) 文件。例如：</span><span class="sxs-lookup"><span data-stu-id="29a58-p108">Create a comma-separated value (CSV) file that contains the required user account information. For example:</span></span>

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   ><span data-ttu-id="29a58-158">列名及其在 CSV 文件第一行中的顺序是任意的。</span><span class="sxs-lookup"><span data-stu-id="29a58-158">The column names and their order in the first row of the CSV file are arbitrary.</span></span> <span data-ttu-id="29a58-159">但请确保文件其余部分的数据顺序与列名称的顺序相匹配。</span><span class="sxs-lookup"><span data-stu-id="29a58-159">But make sure the order of the data in the rest of the file matches the order of the column names.</span></span> <span data-ttu-id="29a58-160">并使用列名称作为 PowerShell for Microsoft 365 命令中的参数值。</span><span class="sxs-lookup"><span data-stu-id="29a58-160">And use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="29a58-161">使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="29a58-161">Use the following syntax:</span></span>
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   <span data-ttu-id="29a58-162">此示例从文件 *C：\My Documents\NewAccounts.csv* 创建用户帐户，并记录在名为 *C：\My Documents\NewAccountResults.csv的文件中*。</span><span class="sxs-lookup"><span data-stu-id="29a58-162">This example creates user accounts from the file *C:\My Documents\NewAccounts.csv* and logs the results in a file named *C:\My Documents\NewAccountResults.csv*.</span></span>
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. <span data-ttu-id="29a58-163">查看输出文件以查看结果。</span><span class="sxs-lookup"><span data-stu-id="29a58-163">Review the output file to see the results.</span></span> <span data-ttu-id="29a58-164">我们没有指定密码，因此 Microsoft 365 生成的随机密码在输出文件中可见。</span><span class="sxs-lookup"><span data-stu-id="29a58-164">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="29a58-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29a58-165">See also</span></span>

[<span data-ttu-id="29a58-166">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="29a58-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="29a58-167">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29a58-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="29a58-168">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="29a58-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)