---
title: 通过Microsoft 365 DAP 合作伙伴Windows PowerShell管理租户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f92d5116-5b66-4150-ad20-1452fc3dd712
description: 本文将了解如何使用 PowerShell for Microsoft 365管理客户租赁。
ms.openlocfilehash: 14290f04159e3ba0ce46971d204b71d3bb1600d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687715"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="c7a91-103">使用Microsoft 365 DAP Windows PowerShell的委派访问权限管理 (租户) 租户</span><span class="sxs-lookup"><span data-stu-id="c7a91-103">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="c7a91-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="c7a91-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c7a91-105">Windows PowerShell联合和云解决方案提供商 (CSP) 合作伙伴可以轻松地管理和报告在 Microsoft 365 管理中心中不可用的客户租赁设置。</span><span class="sxs-lookup"><span data-stu-id="c7a91-105">Windows PowerShell allows Syndication and Cloud Solution Provider (CSP) partners to easily administer and report on customer tenancy settings that are not available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c7a91-106">请注意，合作伙伴管理员帐户要连接到其客户租赁，需要代表以下方管理 (AOBO) 权限。</span><span class="sxs-lookup"><span data-stu-id="c7a91-106">Note that Administer on Behalf Of (AOBO) permissions are required for the partner administrator account to connect to its customer tenancies.</span></span>
  
<span data-ttu-id="c7a91-107">委派访问权限 (DAP) 合作伙伴是联合和云解决方案提供商 (CSP) 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="c7a91-107">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="c7a91-108">他们通常是面向其他公司的网络或电信提供商。</span><span class="sxs-lookup"><span data-stu-id="c7a91-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="c7a91-109">他们Microsoft 365订阅捆绑到他们的服务产品/服务中。</span><span class="sxs-lookup"><span data-stu-id="c7a91-109">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="c7a91-110">当他们销售 Microsoft 365 订阅时，将自动被授予代表 (AOBO) 管理客户租赁的权限，以便他们可以管理和报告客户租赁。</span><span class="sxs-lookup"><span data-stu-id="c7a91-110">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c7a91-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="c7a91-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="c7a91-112">本主题中的过程需要您连接到 连接[Microsoft 365 PowerShell 进行连接](connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="c7a91-112">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="c7a91-113">您也需要您的合作伙伴租户管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="c7a91-113">You also need your partner tenant administrator credentials.</span></span>
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="c7a91-114">要执行什么操作？</span><span class="sxs-lookup"><span data-stu-id="c7a91-114">What do you want to do?</span></span>

### <a name="list-all-tenant-ids"></a><span data-ttu-id="c7a91-115">列出所有租户 ID</span><span class="sxs-lookup"><span data-stu-id="c7a91-115">List all tenant IDs</span></span>

> [!NOTE]
> <span data-ttu-id="c7a91-p103">如果您有 500 多个租户，使用  _-All_ 或 _-MaxResultsParameter_ 确定 cmdlet 语法的范围。这适用于可以提供大型输出的其他 cmdlet，如 **Get-MsolUser** 。</span><span class="sxs-lookup"><span data-stu-id="c7a91-p103">If you have more than 500 tenants, scope the cmdlet syntax with either  _-All_ or _-MaxResultsParameter_. This applies to other cmdlets that can give a large output, such as **Get-MsolUser**.</span></span>
  
<span data-ttu-id="c7a91-118">若要列出您有权访问的所有客户租户 ID，请运行此命令。</span><span class="sxs-lookup"><span data-stu-id="c7a91-118">To list all customer tenant Ids that you have access to, run this command.</span></span>
  
```
Get-MsolPartnerContract -All | Select-Object TenantId
```

<span data-ttu-id="c7a91-119">这将按 **TenantId** 列出所有客户租户。</span><span class="sxs-lookup"><span data-stu-id="c7a91-119">This will display a listing of all your customer tenants by **TenantId**.</span></span>

>[!Note]
><span data-ttu-id="c7a91-120">PowerShell Core 不支持用于 Windows PowerShell 模块和 cmdlet 的其名称中包含 **Msol** 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="c7a91-120">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="c7a91-121">若要继续使用这些 cmdlet，必须从 Windows PowerShell 运行它们。</span><span class="sxs-lookup"><span data-stu-id="c7a91-121">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>
  
### <a name="get-a-tenant-id-by-using-the-domain-name"></a><span data-ttu-id="c7a91-122">使用域名获取租户 ID</span><span class="sxs-lookup"><span data-stu-id="c7a91-122">Get a tenant ID by using the domain name</span></span>

<span data-ttu-id="c7a91-p105">要按域名获取特定客户租户的 **TenantId** ，请运行此命令。将 _<domainname.onmicrosoft.com>_ 替换为您需要的客户租户的实际域名。</span><span class="sxs-lookup"><span data-stu-id="c7a91-p105">To get the **TenantId** for a specific customer tenant by domain name, run this command. Replace _<domainname.onmicrosoft.com>_ with the actual domain name of the customer tenant that you want.</span></span>
  
```
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a><span data-ttu-id="c7a91-125">列出租户的所有域</span><span class="sxs-lookup"><span data-stu-id="c7a91-125">List all domains for a tenant</span></span>

<span data-ttu-id="c7a91-p106">若要获取任一客户租户的所有域，请运行以下命令。将 _<customer TenantId value>_ 替换为实际值。</span><span class="sxs-lookup"><span data-stu-id="c7a91-p106">To get all domains for any one customer tenant, run this command. Replace  _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolDomain -TenantId <customer TenantId value>
```

<span data-ttu-id="c7a91-128">如果您已注册其他域，这将返回与客户 **TenantId** 关联的所有域。</span><span class="sxs-lookup"><span data-stu-id="c7a91-128">If you have registered additional domains, this will return all domains associated with the customer **TenantId**.</span></span>
  
### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a><span data-ttu-id="c7a91-129">获取所有租户和已注册的域的映射</span><span class="sxs-lookup"><span data-stu-id="c7a91-129">Get a mapping of all tenants and registered domains</span></span>

<span data-ttu-id="c7a91-130">前面的 PowerShell for Microsoft 365 命令展示了如何检索租户 ID 或域，但不能同时检索两者，并且它们之间没有明确映射。</span><span class="sxs-lookup"><span data-stu-id="c7a91-130">The previous PowerShell for Microsoft 365 commands showed you how to retrieve either tenant IDs or domains but not both at the same time, and with no clear mapping between them all.</span></span> <span data-ttu-id="c7a91-131">此命令会生成您的所有客户租户 ID 及其域的列表。</span><span class="sxs-lookup"><span data-stu-id="c7a91-131">This command generates a listing of all your customer tenant IDs and their domains.</span></span>
  
```
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a><span data-ttu-id="c7a91-132">获取租户的所有用户</span><span class="sxs-lookup"><span data-stu-id="c7a91-132">Get all users for a tenant</span></span>

<span data-ttu-id="c7a91-p108">这会显示特定租户的所有用户的 **UserPrincipalName**、**DisplayName** 和 **isLicensed** 状态。将 _<customer TenantId value>_ 替换为实际值。</span><span class="sxs-lookup"><span data-stu-id="c7a91-p108">This will display the **UserPrincipalName**, the **DisplayName**, and the **isLicensed** status for all users for a particular tenant. Replace _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a><span data-ttu-id="c7a91-135">获取有关用户的所有详细信息</span><span class="sxs-lookup"><span data-stu-id="c7a91-135">Get all details about a user</span></span>

<span data-ttu-id="c7a91-p109">若要查看特定用户的所有属性，请运行此命令。将 _<customer TenantId value>_ 和 _<user principal name value>_ 替换为实际值。</span><span class="sxs-lookup"><span data-stu-id="c7a91-p109">If you want to see all the properties of a particular user, run this command. Replace  _<customer TenantId value>_ and _<user principal name value>_ with the actual values.</span></span>
  
```
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a><span data-ttu-id="c7a91-138">添加用户、设置选项并分配许可证</span><span class="sxs-lookup"><span data-stu-id="c7a91-138">Add users, set options, and assign licenses</span></span>

<span data-ttu-id="c7a91-139">通过使用 PowerShell for Microsoft 365用户批量创建、配置和Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c7a91-139">The bulk creation, configuration, and licensing of Microsoft 365 users is particularly efficient by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="c7a91-140">在此两步过程中，首先为要添加到逗号分隔值 (CSV) 文件的所有用户创建条目，然后使用 PowerShell for Microsoft 365 导入该文件。</span><span class="sxs-lookup"><span data-stu-id="c7a91-140">In this two-step process, you first create entries for all the users you want to add in a comma-separated value (CSV) file and then import that file by using PowerShell for Microsoft 365.</span></span> 
  
#### <a name="create-a-csv-file"></a><span data-ttu-id="c7a91-141">创建 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="c7a91-141">Create a CSV file</span></span>

<span data-ttu-id="c7a91-142">使用此格式创建 CSV 文件：</span><span class="sxs-lookup"><span data-stu-id="c7a91-142">Create a CSV file by using this format:</span></span>
  
-  `UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`
    
<span data-ttu-id="c7a91-143">其中：</span><span class="sxs-lookup"><span data-stu-id="c7a91-143">where:</span></span>
  
- <span data-ttu-id="c7a91-p111">**UsageLocation** ：此值是用户的两个字母的 ISO 国家/地区代码。国家/地区代码可以在 [ISO 联机浏览平台](https://go.microsoft.com/fwlink/p/?LinkId=532703)中查找。例如，美国的代码为 US，巴西的代码为 BR。</span><span class="sxs-lookup"><span data-stu-id="c7a91-p111">**UsageLocation**: The value for this is the two-letter ISO country/region code of the user. The country/region codes can be looked up at the[ISO Online Browsing Platform](https://go.microsoft.com/fwlink/p/?LinkId=532703). For example, the code for the United States is US, and the code for Brazil is BR.</span></span> 
    
- <span data-ttu-id="c7a91-p112">**LicenseAssignment** ：此值使用以下格式： `syndication-account:<PROVISIONING_ID>`。例如，如果您要向客户租户用户分配 O365_Business_Premium 许可证， **LicenseAssignment** 值将如下所示： **syndication-account:O365_Business_Premium** 。您将在您有权作为联合或 CSP 合作伙伴访问的联合合作伙伴门户中找到 PROVISIONING_ID。</span><span class="sxs-lookup"><span data-stu-id="c7a91-p112">**LicenseAssignment**: The value for this uses this format: `syndication-account:<PROVISIONING_ID>`. For example, if you are assigning customer tenant users O365_Business_Premium licenses, the **LicenseAssignment** value looks like this: **syndication-account:O365_Business_Premium**. You will find the PROVISIONING_IDs in the Syndication Partner Portal that you have access to as a Syndication or CSP partner.</span></span>
    
#### <a name="import-the-csv-file-and-create-the-users"></a><span data-ttu-id="c7a91-150">导入 CSV 文件并创建用户</span><span class="sxs-lookup"><span data-stu-id="c7a91-150">Import the CSV file and create the users</span></span>

<span data-ttu-id="c7a91-p113">创建您的 CSV 文件后，运行此命令，使用不会过期的密码创建用户帐户。此密码分配您指定的许可证，用户必须在第一次登录时进行更改。请确保替换为正确的 CSV 文件名。</span><span class="sxs-lookup"><span data-stu-id="c7a91-p113">After you have your CSV file created, run this command to create user accounts with non-expiring passwords that the user must change at first sign-in and that assigns the license you specify. Be sure to substitute the correct CSV file name.</span></span>
  
```
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a><span data-ttu-id="c7a91-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7a91-153">See also</span></span>

#### 

[<span data-ttu-id="c7a91-154">适用于合作伙伴的帮助</span><span class="sxs-lookup"><span data-stu-id="c7a91-154">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=533477)

