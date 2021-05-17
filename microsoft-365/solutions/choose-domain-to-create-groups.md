---
title: 选择在创建组时Microsoft 365域
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 了解如何使用 PowerShell 配置电子邮件地址策略，选择Microsoft 365组时使用的域。
ms.openlocfilehash: 4908d5bd58ca6d0fbb50151983ddb459f0732284
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904680"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="1c09f-103">选择在创建组时Microsoft 365域</span><span class="sxs-lookup"><span data-stu-id="1c09f-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="1c09f-104">一些组织使用单独的电子邮件域，以区分不同的业务部分。</span><span class="sxs-lookup"><span data-stu-id="1c09f-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="1c09f-105">可以指定在用户创建组时应该Microsoft 365域。</span><span class="sxs-lookup"><span data-stu-id="1c09f-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="1c09f-106">如果你的组织需要用户在企业的默认接受域外的其他域中创建其组，则可以通过使用 PowerShell 为 EAP (电子邮件地址策略) 允许此操作。</span><span class="sxs-lookup"><span data-stu-id="1c09f-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="1c09f-107">在运行 PowerShell cmdlet 之前，请下载并安装一个模块，该模块可让你与组织交谈。</span><span class="sxs-lookup"><span data-stu-id="1c09f-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="1c09f-108">请查看连接[powerShell Exchange Online进行远程访问](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1c09f-108">Check out [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="1c09f-109">示例场景</span><span class="sxs-lookup"><span data-stu-id="1c09f-109">Example scenarios</span></span>

<span data-ttu-id="1c09f-110">假设你的企业的主域是 Contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1c09f-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="1c09f-111">但是，组织的默认接受域 service.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1c09f-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="1c09f-112">这意味着将在例如，service.contoso.com (中创建 jimsteam@service.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="1c09f-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="1c09f-113">假设你还在组织中配置了子域。</span><span class="sxs-lookup"><span data-stu-id="1c09f-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="1c09f-114">您也希望在这些域中创建组：</span><span class="sxs-lookup"><span data-stu-id="1c09f-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="1c09f-115">students.contoso.com 学生</span><span class="sxs-lookup"><span data-stu-id="1c09f-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="1c09f-116">faculty.contoso.com 教职员工</span><span class="sxs-lookup"><span data-stu-id="1c09f-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="1c09f-117">以下两种方案说明了如何完成此操作。</span><span class="sxs-lookup"><span data-stu-id="1c09f-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="1c09f-118">当你拥有多个 EAP 时，将按优先级顺序评估它们。</span><span class="sxs-lookup"><span data-stu-id="1c09f-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="1c09f-119">值 1 表示最高优先级。</span><span class="sxs-lookup"><span data-stu-id="1c09f-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="1c09f-120">EAP 匹配后，不会进一步计算 EAP，并且按匹配的 EAP 在组上标记的地址。</span><span class="sxs-lookup"><span data-stu-id="1c09f-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="1c09f-121">> 如果没有符合指定条件的 EAP，则组将设置在组织的默认接受域中。</span><span class="sxs-lookup"><span data-stu-id="1c09f-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="1c09f-122">请参阅管理[域中的接受Exchange Online，](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)详细了解如何添加接受域。</span><span class="sxs-lookup"><span data-stu-id="1c09f-122">Check out [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="1c09f-123">方案 1</span><span class="sxs-lookup"><span data-stu-id="1c09f-123">Scenario 1</span></span>

<span data-ttu-id="1c09f-124">以下示例演示如何在 groups.contoso.com 域中设置组织Microsoft 365组。</span><span class="sxs-lookup"><span data-stu-id="1c09f-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="1c09f-125">方案 2</span><span class="sxs-lookup"><span data-stu-id="1c09f-125">Scenario 2</span></span>

<span data-ttu-id="1c09f-126">假设你想要控制在哪些子域中Microsoft 365创建组。</span><span class="sxs-lookup"><span data-stu-id="1c09f-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="1c09f-127">你想要：</span><span class="sxs-lookup"><span data-stu-id="1c09f-127">You want:</span></span>
  
- <span data-ttu-id="1c09f-128">学生创建的组 (部门设置为"学生") 域中students.groups.contoso.com组。</span><span class="sxs-lookup"><span data-stu-id="1c09f-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="1c09f-129">请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="1c09f-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="1c09f-130">教职员工创建的组 (部门设置为 **"** 教职员工"或电子邮件地址的用户 faculty.contoso.com) ) 域中 faculty.groups.contoso.com 组。</span><span class="sxs-lookup"><span data-stu-id="1c09f-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="1c09f-131">请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="1c09f-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="1c09f-132">由任何其他用户创建的组在 groups.contoso.com 域中创建。</span><span class="sxs-lookup"><span data-stu-id="1c09f-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="1c09f-133">请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="1c09f-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="1c09f-134">更改电子邮件地址策略</span><span class="sxs-lookup"><span data-stu-id="1c09f-134">Change email address policies</span></span>

<span data-ttu-id="1c09f-135">若要更改现有 EAP 的优先级或电子邮件地址模板，请使用 Set-EmailAddressPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1c09f-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="1c09f-136">更改 EAP 不会影响已预配的组。</span><span class="sxs-lookup"><span data-stu-id="1c09f-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="1c09f-137">删除电子邮件地址策略</span><span class="sxs-lookup"><span data-stu-id="1c09f-137">Delete email address policies</span></span>

<span data-ttu-id="1c09f-138">若要删除 EAP，请使用 Remove-EmailAddressPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1c09f-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="1c09f-139">更改 EAP 不会影响已预配的组。</span><span class="sxs-lookup"><span data-stu-id="1c09f-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="1c09f-140">混合要求</span><span class="sxs-lookup"><span data-stu-id="1c09f-140">Hybrid requirements</span></span>

<span data-ttu-id="1c09f-141">如果您的组织在混合方案中配置，请查看使用本地 Exchange 混合配置[Microsoft 365](/exchange/hybrid-deployment/set-up-microsoft-365-groups)组，以确保组织满足创建 Microsoft 365 组的要求。</span><span class="sxs-lookup"><span data-stu-id="1c09f-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="1c09f-142">有关使用电子邮件地址策略组的其他信息：</span><span class="sxs-lookup"><span data-stu-id="1c09f-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="1c09f-143">还有一些需要了解的方面：</span><span class="sxs-lookup"><span data-stu-id="1c09f-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="1c09f-144">组的创建速度取决于组织中配置的 EAP 数。</span><span class="sxs-lookup"><span data-stu-id="1c09f-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="1c09f-145">管理员和用户还可以在创建组时修改域。</span><span class="sxs-lookup"><span data-stu-id="1c09f-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="1c09f-146">用户组是使用标准查询来确定 (用户) 可用属性。</span><span class="sxs-lookup"><span data-stu-id="1c09f-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="1c09f-147">查看 [-RecipientFilter](/powershell/exchange/recipientfilter-properties) 参数的可筛选属性，了解受支持的可筛选属性。</span><span class="sxs-lookup"><span data-stu-id="1c09f-147">Check out [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="1c09f-148">如果未为组配置任何 EAP，则选择默认接受域以创建组。</span><span class="sxs-lookup"><span data-stu-id="1c09f-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="1c09f-149">如果删除接受域，应首先更新 EAPs，否则，组预配将受到影响。</span><span class="sxs-lookup"><span data-stu-id="1c09f-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="1c09f-150">最多可为组织配置 100 个电子邮件地址策略。</span><span class="sxs-lookup"><span data-stu-id="1c09f-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="1c09f-151">相关文章</span><span class="sxs-lookup"><span data-stu-id="1c09f-151">Related articles</span></span>

[<span data-ttu-id="1c09f-152">协作治理规划分步规划</span><span class="sxs-lookup"><span data-stu-id="1c09f-152">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="1c09f-153">创建协作管理计划</span><span class="sxs-lookup"><span data-stu-id="1c09f-153">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="1c09f-154">在管理Microsoft 365创建一个组</span><span class="sxs-lookup"><span data-stu-id="1c09f-154">Create an Microsoft 365 group in the admin center</span></span>](../admin/create-groups/create-groups.md)