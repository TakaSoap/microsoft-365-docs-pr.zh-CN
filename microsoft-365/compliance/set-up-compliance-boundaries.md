---
title: 设置电子数据展示调查的合规性边界
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 了解如何使用合规性边界创建逻辑边界，以控制电子数据展示管理员可在 Microsoft 365 中搜索的用户内容位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 23ff50b9cd0ab0178962f7be9f1cedfbd6a7a1f7
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022338"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a><span data-ttu-id="a4347-103">设置电子数据展示调查的合规性边界</span><span class="sxs-lookup"><span data-stu-id="a4347-103">Set up compliance boundaries for eDiscovery investigations</span></span>

<span data-ttu-id="a4347-104">使用核心电子数据展示或电子数据展示来管理调查时，Advanced eDiscovery本文中的指南。</span><span class="sxs-lookup"><span data-stu-id="a4347-104">The guidance in this article can be applied when using either Core eDiscovery or Advanced eDiscovery to manage investigations.</span></span>

<span data-ttu-id="a4347-105">合规性边界在组织中创建逻辑边界 (如电子数据展示管理员可搜索的邮箱、OneDrive 帐户和 SharePoint 网站) 用户内容位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-105">Compliance boundaries create logical boundaries within an organization that control the user content locations (such as mailboxes, OneDrive accounts, and SharePoint sites) that eDiscovery managers can search.</span></span> <span data-ttu-id="a4347-106">此外，合规性边界还控制谁可以访问用于管理组织中法律、人力资源或其他调查电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="a4347-106">Also, compliance boundaries control who can access eDiscovery cases used to manage the legal, human resources, or other investigations within your organization.</span></span> <span data-ttu-id="a4347-107">对于必须尊重地理机构和法规的跨国公司以及政府（通常分为不同的机构）来说，通常需要合规性边界。</span><span class="sxs-lookup"><span data-stu-id="a4347-107">The need for compliance boundaries is often necessary for multi-national corporations that have to respect geographical boarders and regulations and for governments, which are often divided into different agencies.</span></span> <span data-ttu-id="a4347-108">在Microsoft 365中，合规性边界可帮助您在使用电子数据展示事例执行内容搜索和管理调查时满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="a4347-108">In Microsoft 365, compliance boundaries help you meet these requirements when performing content searches and managing investigations with eDiscovery cases.</span></span>
  
<span data-ttu-id="a4347-109">我们使用下图中的示例说明合规性边界如何工作。</span><span class="sxs-lookup"><span data-stu-id="a4347-109">We use the example in the following illustration to explain how compliance boundaries work.</span></span>
  
![合规性边界由搜索权限筛选器组成，用于控制对控制电子数据展示事例访问权限的机构和管理角色组的访问权限](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
<span data-ttu-id="a4347-111">在此例中，Contoso LTD 是由 Fourth Coffee 和 Coho Winery 这两个子公司组成的组织。</span><span class="sxs-lookup"><span data-stu-id="a4347-111">In this example, Contoso LTD is an organization that consists of two subsidiaries, Fourth Coffee and Coho Winery.</span></span> <span data-ttu-id="a4347-112">业务要求电子数据展示的经理和调查人员只能搜索其Exchange邮箱、OneDrive帐户SharePoint网站。</span><span class="sxs-lookup"><span data-stu-id="a4347-112">The business requires that eDiscovery mangers and investigators can only search the Exchange mailboxes, OneDrive accounts, and SharePoint sites in their agency.</span></span> <span data-ttu-id="a4347-113">此外，电子数据展示管理员和调查人员只能查看其机构中的电子数据展示事例，并且只能访问他们作为成员的情况。</span><span class="sxs-lookup"><span data-stu-id="a4347-113">Also, eDiscovery managers and investigators can only see eDiscovery cases in their agency, and they can only access the cases that they're a member of.</span></span> <span data-ttu-id="a4347-114">此外，在此方案中，调查人员无法将内容位置保留或导出案例的内容。</span><span class="sxs-lookup"><span data-stu-id="a4347-114">Additionally in this scenario, investigators cannot place content locations on hold or export content from a case.</span></span> <span data-ttu-id="a4347-115">下面将说明合规性边界如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="a4347-115">Here's how compliance boundaries meet these requirements.</span></span>
  
- <span data-ttu-id="a4347-116">内容搜索中的搜索权限筛选功能控制电子数据展示管理员和研究人员可以搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-116">The search permissions filtering functionality in Content search controls the content locations that eDiscovery managers and investigators can search.</span></span> <span data-ttu-id="a4347-117">这意味着 Fourth Coffee 公司中的电子数据展示管理者和员工只能搜索 Fourth Coffee 子公司中的内容位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-117">This means eDiscovery managers and investigators in the Fourth Coffee agency can only search content locations in the Fourth Coffee subsidiary.</span></span> <span data-ttu-id="a4347-118">共同的限制适用于 Coho Winery 子公司。</span><span class="sxs-lookup"><span data-stu-id="a4347-118">The same restriction applies to the Coho Winery subsidiary.</span></span>

- <span data-ttu-id="a4347-119">[角色组](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) 为合规性边界提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="a4347-119">[Role groups](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) provide the following functions for compliance boundaries:</span></span>

  - <span data-ttu-id="a4347-120">控制哪些人可以看到电子数据展示事例Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="a4347-120">Control who can see the eDiscovery cases in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a4347-121">这意味着电子数据展示管理者和管理员只能看到其机构中的电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="a4347-121">This means that eDiscovery managers and investigators can only see the eDiscovery cases in their agency.</span></span>

  - <span data-ttu-id="a4347-122">控制谁可以将成员分配给电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="a4347-122">Control who can assign members to an eDiscovery case.</span></span> <span data-ttu-id="a4347-123">这意味着电子数据展示管理者和管理员只能向自己作为成员的事例分配成员。</span><span class="sxs-lookup"><span data-stu-id="a4347-123">This means eDiscovery managers and investigators can only assign members to cases that they themselves are a member of.</span></span>

  - <span data-ttu-id="a4347-124">通过添加或删除分配特定权限的角色，控制成员可以执行与电子数据展示相关的任务。</span><span class="sxs-lookup"><span data-stu-id="a4347-124">Control the eDiscovery-related tasks that members can perform by adding or removing roles that assign specific permissions.</span></span>

<span data-ttu-id="a4347-125">以下是设置合规性边界的过程：</span><span class="sxs-lookup"><span data-stu-id="a4347-125">Here's the process for setting up compliance boundaries:</span></span>
  
[<span data-ttu-id="a4347-126">步骤 1：标识要定义机构的用户属性</span><span class="sxs-lookup"><span data-stu-id="a4347-126">Step 1: Identify a user attribute to define your agencies</span></span>](#step-1-identify-a-user-attribute-to-define-your-agencies)

[<span data-ttu-id="a4347-127">步骤 2：为每个机构创建角色组</span><span class="sxs-lookup"><span data-stu-id="a4347-127">Step 2: Create a role group for each agency</span></span>](#step-2-create-a-role-group-for-each-agency)

[<span data-ttu-id="a4347-128">步骤 3：创建搜索权限筛选器以强制实施合规性边界</span><span class="sxs-lookup"><span data-stu-id="a4347-128">Step 3: Create a search permissions filter to enforce the compliance boundary</span></span>](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[<span data-ttu-id="a4347-129">步骤 4：为机构内调查创建电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="a4347-129">Step 4: Create an eDiscovery case for an intra-agency investigations</span></span>](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a><span data-ttu-id="a4347-130">设置合规性边界之前</span><span class="sxs-lookup"><span data-stu-id="a4347-130">Before you set up compliance boundaries</span></span>

- <span data-ttu-id="a4347-131">必须为用户分配Exchange Online许可证。</span><span class="sxs-lookup"><span data-stu-id="a4347-131">Users must be assigned an Exchange Online license.</span></span> <span data-ttu-id="a4347-132">若要验证这一点，请使用 Exchange Online PowerShell 中的[Get-User](/powershell/module/exchange/get-user) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a4347-132">To verify this, use the [Get-User](/powershell/module/exchange/get-user) cmdlet in Exchange Online PowerShell.</span></span>

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a><span data-ttu-id="a4347-133">步骤 1：标识要定义机构的用户属性</span><span class="sxs-lookup"><span data-stu-id="a4347-133">Step 1: Identify a user attribute to define your agencies</span></span>

<span data-ttu-id="a4347-134">第一步是选择要用于定义机构的属性。</span><span class="sxs-lookup"><span data-stu-id="a4347-134">The first step is to choose an attribute to use that will define your agencies.</span></span> <span data-ttu-id="a4347-135">此属性用于创建搜索权限筛选器，该筛选器限制电子数据展示管理员仅搜索分配了此属性的特定值的用户的内容位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-135">This attribute is used to create the search permissions filter that limits an eDiscovery manager to search only the content locations of users who are assigned a specific value for this attribute.</span></span> <span data-ttu-id="a4347-136">例如，假设 Contoso 决定使用 **Department** 属性。</span><span class="sxs-lookup"><span data-stu-id="a4347-136">For example, let's say Contoso decides to use the **Department** attribute.</span></span> <span data-ttu-id="a4347-137">Fourth Coffee 子公司中用户的此属性的值为  `FourthCoffee`  ，Coho Winery 子公司的用户的值为 `CohoWinery` 。</span><span class="sxs-lookup"><span data-stu-id="a4347-137">The value for this attribute for users in the Fourth Coffee subsidiary would be  `FourthCoffee`  and the value for users in Coho Winery subsidiary would be `CohoWinery`.</span></span> <span data-ttu-id="a4347-138">在步骤 3 中，使用此对 ( `attribute:value`  例如 *Department：FourthCoffee*) 来限制电子数据展示管理员可以搜索的用户内容位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-138">In Step 3, you use this  `attribute:value`  pair (for example, *Department:FourthCoffee*) to limit the user content locations that eDiscovery managers can search.</span></span> 
  
<span data-ttu-id="a4347-139">下面是可用于合规性边界的用户属性的一些示例：</span><span class="sxs-lookup"><span data-stu-id="a4347-139">Here are some examples of user attributes that you can use for compliance boundaries:</span></span>
  
- <span data-ttu-id="a4347-140">公司</span><span class="sxs-lookup"><span data-stu-id="a4347-140">Company</span></span>

- <span data-ttu-id="a4347-141">CustomAttribute1 - CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="a4347-141">CustomAttribute1 - CustomAttribute15</span></span>

- <span data-ttu-id="a4347-142">部门</span><span class="sxs-lookup"><span data-stu-id="a4347-142">Department</span></span>

- <span data-ttu-id="a4347-143">办公室</span><span class="sxs-lookup"><span data-stu-id="a4347-143">Office</span></span>

- <span data-ttu-id="a4347-144">CountryOrRegion (两个字母的国家/地区代码) </span><span class="sxs-lookup"><span data-stu-id="a4347-144">CountryOrRegion (Two-letter country code)</span></span>

<span data-ttu-id="a4347-145">有关完整列表，请参阅受支持的邮箱筛选器 [的完整列表](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)。</span><span class="sxs-lookup"><span data-stu-id="a4347-145">For a complete list, see the full list of supported [mailbox filters](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties).</span></span>

## <a name="step-2-create-a-role-group-for-each-agency"></a><span data-ttu-id="a4347-146">步骤 2：为每个机构创建角色组</span><span class="sxs-lookup"><span data-stu-id="a4347-146">Step 2: Create a role group for each agency</span></span>

<span data-ttu-id="a4347-147">下一步是在安全与合规中心&与机构一致的角色组。</span><span class="sxs-lookup"><span data-stu-id="a4347-147">The next step is to create the role groups in the Security & Compliance Center that will align with your agencies.</span></span> <span data-ttu-id="a4347-148">建议创建角色组，复制内置电子数据展示管理者组，添加适当的成员，并删除可能不适合你的角色。</span><span class="sxs-lookup"><span data-stu-id="a4347-148">We recommend that you create a role group by copying the built-in eDiscovery Managers group, adding the appropriate members, and removing roles that may not be applicable to your needs.</span></span> <span data-ttu-id="a4347-149">有关与电子数据展示相关的角色详细信息，请参阅分配 [电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="a4347-149">For more information about eDiscovery-related roles, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="a4347-150">若要创建角色组，请转到 安全与合规中心 中的 **权限** 页面，并为每个将使用合规性边界电子数据展示事例管理调查的团队创建角色组。</span><span class="sxs-lookup"><span data-stu-id="a4347-150">To create the role groups, go to the **Permissions** page in the Security & Compliance Center and create a role group for each team in each agency that will use compliance boundaries and eDiscovery cases to manage investigations.</span></span>
  
<span data-ttu-id="a4347-151">使用 Contoso 合规性边界方案，需要创建四个角色组，并添加每个角色组的适当成员。</span><span class="sxs-lookup"><span data-stu-id="a4347-151">Using the Contoso compliance boundaries scenario, four role groups need to be created and the appropriate members added to each one.</span></span>
  
- <span data-ttu-id="a4347-152">Fourth Coffee 电子数据展示管理者</span><span class="sxs-lookup"><span data-stu-id="a4347-152">Fourth Coffee eDiscovery Managers</span></span>

- <span data-ttu-id="a4347-153">Fourth Coffee 调查员</span><span class="sxs-lookup"><span data-stu-id="a4347-153">Fourth Coffee Investigators</span></span>

- <span data-ttu-id="a4347-154">Coho Winery 电子数据展示经理</span><span class="sxs-lookup"><span data-stu-id="a4347-154">Coho Winery eDiscovery Managers</span></span>

- <span data-ttu-id="a4347-155">Coho Winery Wines</span><span class="sxs-lookup"><span data-stu-id="a4347-155">Coho Winery Investigators</span></span>
  
<span data-ttu-id="a4347-156">为满足 Contoso 合规性边界方案的要求，还将从调查人员角色组中删除保留和导出角色，以防止调查人员对内容位置进行保留并从案例导出内容。</span><span class="sxs-lookup"><span data-stu-id="a4347-156">To meet the requirements of the Contoso compliance boundaries scenario, you would also remove the **Hold** and **Export** roles from the investigators role groups to prevent investigators from placing holds on content locations and exporting content from a case.</span></span>

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a><span data-ttu-id="a4347-157">步骤 3：创建搜索权限筛选器以强制实施合规性边界</span><span class="sxs-lookup"><span data-stu-id="a4347-157">Step 3: Create a search permissions filter to enforce the compliance boundary</span></span>

<span data-ttu-id="a4347-158">为每个机构创建角色组后，下一步是创建搜索权限筛选器，将每个角色组关联到其特定机构并定义合规性边界本身。</span><span class="sxs-lookup"><span data-stu-id="a4347-158">After you've created role groups for each agency, the next step is to create the search permissions filters that associate each role group to its specific agency and defines the compliance boundary itself.</span></span> <span data-ttu-id="a4347-159">你需要为每个机构创建一个搜索权限筛选器。</span><span class="sxs-lookup"><span data-stu-id="a4347-159">You need to create one search permissions filter for each agency.</span></span> <span data-ttu-id="a4347-160">有关创建安全权限筛选器的信息，请参阅配置内容 [搜索的权限筛选](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="a4347-160">For more information about creating security permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
  
<span data-ttu-id="a4347-161">下面是用于创建用于合规性边界的搜索权限筛选器的语法。</span><span class="sxs-lookup"><span data-stu-id="a4347-161">Here's the syntax that's used to create a search permissions filter used for compliance boundaries.</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'" -Action <Action>
```

<span data-ttu-id="a4347-162">下面是命令中每个参数的说明：</span><span class="sxs-lookup"><span data-stu-id="a4347-162">Here's a description of each parameter in the command:</span></span>
  
- <span data-ttu-id="a4347-163">`FilterName`：指定筛选器的名称。</span><span class="sxs-lookup"><span data-stu-id="a4347-163">`FilterName`: Specifies the name of the filter.</span></span> <span data-ttu-id="a4347-164">使用描述或标识筛选器所使用的机构的名称。</span><span class="sxs-lookup"><span data-stu-id="a4347-164">Use a name that describes or identifies the agency that the filter is used in.</span></span>

- <span data-ttu-id="a4347-165">`Users`：指定应用此筛选器的用户或组，这些用户或组将执行搜索操作。</span><span class="sxs-lookup"><span data-stu-id="a4347-165">`Users`: Specifies the users or groups who get this filter applied to the search actions they perform.</span></span> <span data-ttu-id="a4347-166">对于合规性边界，此参数 (在步骤 3) 中创建筛选器的代理中创建的角色组。</span><span class="sxs-lookup"><span data-stu-id="a4347-166">For compliance boundaries, this parameter specifies the role groups (that you created in Step 3) in the agency that you're creating the filter for.</span></span> <span data-ttu-id="a4347-167">请注意，这是一个多值参数，因此可以包含一个或多个角色组，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="a4347-167">Note this is a multi-value parameter so you can include one or more role groups, separated by commas.</span></span>

- <span data-ttu-id="a4347-168">`Filters`：指定筛选器的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="a4347-168">`Filters`: Specifies the search criteria for the filter.</span></span> <span data-ttu-id="a4347-169">对于合规性边界，定义以下筛选器。</span><span class="sxs-lookup"><span data-stu-id="a4347-169">For the compliance boundaries, you define the following filters.</span></span> <span data-ttu-id="a4347-170">每一个都适用于一个内容位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-170">Each one applies to a content location.</span></span>

    - <span data-ttu-id="a4347-171">`Mailbox`：指定在参数中OneDrive角色组可以搜索的邮箱 `Users` 或邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="a4347-171">`Mailbox`: Specifies the mailboxes or OneDrive accounts that the role groups defined in the `Users` parameter can search.</span></span> <span data-ttu-id="a4347-172">此筛选器允许角色组的成员仅搜索邮箱或OneDrive机构中的帐户;例如， `"Mailbox_Department -eq 'FourthCoffee'"` 。</span><span class="sxs-lookup"><span data-stu-id="a4347-172">This filter allows members of the role group to search only the mailboxes or OneDrive accounts in a specific agency; for example, `"Mailbox_Department -eq 'FourthCoffee'"`.</span></span>

    - <span data-ttu-id="a4347-173">`Site_Path`：指定SharePoint中定义的角色组可以搜索的网站 `Users` 。</span><span class="sxs-lookup"><span data-stu-id="a4347-173">`Site_Path`: Specifies the SharePoint sites that the role groups defined in the  `Users` parameter can search.</span></span> <span data-ttu-id="a4347-174">*SharePointURL* 指定角色组的成员可以搜索的代理中的网站。</span><span class="sxs-lookup"><span data-stu-id="a4347-174">The  *SharePointURL*  specifies the sites in the agency that members of the role group can search.</span></span> <span data-ttu-id="a4347-175">例如，`"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。</span><span class="sxs-lookup"><span data-stu-id="a4347-175">For example,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`.</span></span> <span data-ttu-id="a4347-176">请注意， `Site` `Site_Path` 和 筛选器由 **-or 运算符** 连接。</span><span class="sxs-lookup"><span data-stu-id="a4347-176">Notice the `Site` and `Site_Path` filters are connected by an **-or** operator.</span></span>

     > [!NOTE]
     > <span data-ttu-id="a4347-177">参数的语法 `Filters` 包括筛选器 *列表*。</span><span class="sxs-lookup"><span data-stu-id="a4347-177">The syntax for the `Filters` parameter includes a *filters list*.</span></span> <span data-ttu-id="a4347-178">筛选器列表是包含邮箱筛选器和网站路径筛选器（用逗号分隔）的筛选器。</span><span class="sxs-lookup"><span data-stu-id="a4347-178">A filters list is a filter that includes a mailbox filter and a site path filter separated by a comma.</span></span> <span data-ttu-id="a4347-179">在上一个示例中，请注意逗号分隔 **Mailbox_MailboxPropertyName和\*\*\*\*Site_Path：** `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"` 。</span><span class="sxs-lookup"><span data-stu-id="a4347-179">In the previous example, notice that a comma separates **Mailbox_MailboxPropertyName** and **Site_Path**: `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"`.</span></span> <span data-ttu-id="a4347-180">在运行内容搜索期间处理此筛选器时，会从筛选器列表中创建两个搜索权限筛选器：一个邮箱筛选器和一个SharePoint筛选器。</span><span class="sxs-lookup"><span data-stu-id="a4347-180">When this filter is processed during the running of a content search, two search permissions filters are created from the filters list: one mailbox filter and one SharePoint filter.</span></span> <span data-ttu-id="a4347-181">使用筛选器列表的替代方法是为每个机构创建两个单独的搜索权限筛选器：一个搜索权限筛选器用于邮箱属性，一个筛选器用于SharePoint网站属性。</span><span class="sxs-lookup"><span data-stu-id="a4347-181">An alternative to using a filters list would be to create two separate search permissions filters for each agency: one search permissions filter for the mailbox attribute and one filter for the SharePoint site attributes.</span></span> <span data-ttu-id="a4347-182">在任一情况下，结果都相同。</span><span class="sxs-lookup"><span data-stu-id="a4347-182">In either case, the results will be the same.</span></span> <span data-ttu-id="a4347-183">优先使用筛选器列表或创建单独的搜索权限筛选器。</span><span class="sxs-lookup"><span data-stu-id="a4347-183">Using a filters list or creating separate search permissions filters is a matter of preference.</span></span>

- <span data-ttu-id="a4347-184">`Action`：指定应用筛选器的搜索操作的类型。</span><span class="sxs-lookup"><span data-stu-id="a4347-184">`Action`: Specifies the type of search action the filter is applied to.</span></span> <span data-ttu-id="a4347-185">例如，仅在参数中定义的角色组的成员运行搜索  `-Action Search` 时 `Users` 应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="a4347-185">For example,  `-Action Search` would only apply the filter when members of the role group defined in the `Users` parameter run a search.</span></span> <span data-ttu-id="a4347-186">在这种情况下，导出搜索结果时不会应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="a4347-186">In this case, the filter wouldn't be applied when exporting search results.</span></span> <span data-ttu-id="a4347-187">对于合规性边界，请使用  `-Action All` ，以便筛选器适用于所有搜索操作。</span><span class="sxs-lookup"><span data-stu-id="a4347-187">For compliance boundaries, use  `-Action All` so the filter applies to all search actions.</span></span> 

    <span data-ttu-id="a4347-188">有关搜索操作的列表，请参阅配置内容搜索的权限筛选中的"New-ComplianceSecurityFilter" [部分](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)。</span><span class="sxs-lookup"><span data-stu-id="a4347-188">For a list of the search actions, see the "New-ComplianceSecurityFilter" section in [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).</span></span>

<span data-ttu-id="a4347-189">下面是为支持 Contoso 合规性边界方案而创建的两个搜索权限筛选器的示例。</span><span class="sxs-lookup"><span data-stu-id="a4347-189">Here are examples of the two search permissions filters that would be created to support the Contoso compliance boundaries scenario.</span></span> <span data-ttu-id="a4347-190">这两个示例包括逗号分隔的筛选器列表，列表中包括邮箱和网站筛选器在同一搜索权限筛选器中，并用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="a4347-190">Both of these examples include a comma-separated filters list, in which the mailbox and site filters are included in the same search permissions filter and are separated by a comma.</span></span>
  
### <a name="fourth-coffee"></a><span data-ttu-id="a4347-191">Fourth Coffee</span><span class="sxs-lookup"><span data-stu-id="a4347-191">Fourth Coffee</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a><span data-ttu-id="a4347-192">Coho Winery</span><span class="sxs-lookup"><span data-stu-id="a4347-192">Coho Winery</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a><span data-ttu-id="a4347-193">步骤 4：为机构内调查创建电子数据展示案例</span><span class="sxs-lookup"><span data-stu-id="a4347-193">Step 4: Create an eDiscovery case for intra-agency investigations</span></span>

<span data-ttu-id="a4347-194">最后一步是在 Microsoft 365 合规中心 中创建核心电子数据展示案例或 Advanced eDiscovery 案例，然后将在步骤 2 中创建的角色组添加为该案例的成员。</span><span class="sxs-lookup"><span data-stu-id="a4347-194">The final step is to create a Core eDiscovery case or Advanced eDiscovery case in the Microsoft 365 compliance center and then add the role group that you created in Step 2 as a member of the case.</span></span> <span data-ttu-id="a4347-195">这导致使用合规性边界有两个重要特征：</span><span class="sxs-lookup"><span data-stu-id="a4347-195">This results in two important characteristics of using compliance boundaries:</span></span>
  
- <span data-ttu-id="a4347-196">只有添加到案例的角色组的成员才能在安全与合规中心内查看&案例。</span><span class="sxs-lookup"><span data-stu-id="a4347-196">Only members of the role group added to the case will be able to see and access the case in the Security & Compliance Center.</span></span> <span data-ttu-id="a4347-197">例如，如果 Fourth Coffee 检查人员角色组是案例的唯一成员，则 Fourth Coffee 电子数据展示管理员角色组 (的成员或任何其他角色组) 的成员将不能查看或访问该案例。</span><span class="sxs-lookup"><span data-stu-id="a4347-197">For example, if the Fourth Coffee Investigators role group is the only member of a case, then members of the Fourth Coffee eDiscovery Managers role group (or members of any other role group) won't be able to see or access the case.</span></span>

- <span data-ttu-id="a4347-198">当分配给案例的角色组的成员运行与案例关联的搜索时，他们只能搜索其机构 (该位置由你在步骤 3.) 中创建的搜索权限筛选器定义。</span><span class="sxs-lookup"><span data-stu-id="a4347-198">When a member of the role group assigned to a case runs a search associated with the case, they will only be able to search the content locations within their agency (which is defined by the search permissions filter that you created in Step 3.)</span></span>

<span data-ttu-id="a4347-199">若要创建案例并分配成员：</span><span class="sxs-lookup"><span data-stu-id="a4347-199">To create a case and assign members:</span></span>

1. <span data-ttu-id="a4347-200">转到"**核心电子数据\*\*\*\*展示或** Advanced eDiscovery"页面中Microsoft 365 合规中心创建一个案例。</span><span class="sxs-lookup"><span data-stu-id="a4347-200">Go to the **Core eDiscovery** or **Advanced eDiscovery** page in the Microsoft 365 compliance center and create a case.</span></span>

2. <span data-ttu-id="a4347-201">在事例列表中，单击您创建的事例的名称。</span><span class="sxs-lookup"><span data-stu-id="a4347-201">In the list of cases, click the name of the case you created.</span></span>

3. <span data-ttu-id="a4347-202">将角色组作为成员添加到案例。</span><span class="sxs-lookup"><span data-stu-id="a4347-202">Add role groups as members to the case.</span></span> <span data-ttu-id="a4347-203">有关说明，请参阅以下文章之一：</span><span class="sxs-lookup"><span data-stu-id="a4347-203">For instructions, see the one of the following articles:</span></span>

   - [<span data-ttu-id="a4347-204">向核心电子数据展示案例添加成员</span><span class="sxs-lookup"><span data-stu-id="a4347-204">Add members to a Core eDiscovery case</span></span>](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [<span data-ttu-id="a4347-205">将成员添加到Advanced eDiscovery案例</span><span class="sxs-lookup"><span data-stu-id="a4347-205">Add members to an Advanced eDiscovery case</span></span>](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> <span data-ttu-id="a4347-206">向案例添加角色组时，只能添加作为成员的角色组。</span><span class="sxs-lookup"><span data-stu-id="a4347-206">When adding a role group to a case, you can only add the role groups that you are a member of.</span></span>

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a><span data-ttu-id="a4347-207">在多地理位置环境中搜索和导出内容</span><span class="sxs-lookup"><span data-stu-id="a4347-207">Searching and exporting content in Multi-Geo environments</span></span>

<span data-ttu-id="a4347-208">通过搜索权限筛选器，还可以控制内容在导出的路由位置，以及搜索内容位置时可以搜索的数据中心SharePoint Multi-Geo[位置](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a4347-208">Search permissions filters also let you control where content is routed for export and which datacenter can be searched when searching content locations in a [SharePoint Multi-Geo environment](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md).</span></span>
  
- <span data-ttu-id="a4347-209">**导出搜索结果：** 可以从特定数据中心导出Exchange邮箱、SharePoint网站OneDrive帐户。</span><span class="sxs-lookup"><span data-stu-id="a4347-209">**Export search results:** You can export the search results from Exchange mailboxes, SharePoint sites, and OneDrive accounts from a specific datacenter.</span></span> <span data-ttu-id="a4347-210">这意味着您可以指定搜索结果将导出到的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-210">This means that you can specify the datacenter location that search results will be exported from.</span></span>

    <span data-ttu-id="a4347-211">使用 **New-ComplianceSecurityFilter** 或 **Set-ComplianceSecurityFilter** cmdlet 的 **Region** 参数创建或更改导出将通过哪个数据中心。</span><span class="sxs-lookup"><span data-stu-id="a4347-211">Use the **Region** parameter for **New-ComplianceSecurityFilter** or **Set-ComplianceSecurityFilter** cmdlets to create or change which datacenter the export will be routed through.</span></span>
  
    |<span data-ttu-id="a4347-212">**参数值**</span><span class="sxs-lookup"><span data-stu-id="a4347-212">**Parameter value**</span></span>|<span data-ttu-id="a4347-213">**数据中心位置**</span><span class="sxs-lookup"><span data-stu-id="a4347-213">**Datacenter location**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a4347-214">NAM</span><span class="sxs-lookup"><span data-stu-id="a4347-214">NAM</span></span>  <br/> |<span data-ttu-id="a4347-215">北美 (数据中心位于美国) </span><span class="sxs-lookup"><span data-stu-id="a4347-215">North American (datacenters are in the US)</span></span>  <br/> |
    |<span data-ttu-id="a4347-216">EUR</span><span class="sxs-lookup"><span data-stu-id="a4347-216">EUR</span></span>  <br/> |<span data-ttu-id="a4347-217">欧洲</span><span class="sxs-lookup"><span data-stu-id="a4347-217">Europe</span></span>  <br/> |
    |<span data-ttu-id="a4347-218">APC</span><span class="sxs-lookup"><span data-stu-id="a4347-218">APC</span></span>  <br/> |<span data-ttu-id="a4347-219">亚太地区</span><span class="sxs-lookup"><span data-stu-id="a4347-219">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="a4347-220">CAN</span><span class="sxs-lookup"><span data-stu-id="a4347-220">CAN</span></span> <br/> |<span data-ttu-id="a4347-221">加拿大</span><span class="sxs-lookup"><span data-stu-id="a4347-221">Canada</span></span>|
    |||

- <span data-ttu-id="a4347-222">**路由内容搜索：** 你可以将网站和SharePoint的内容OneDrive路由到附属数据中心。</span><span class="sxs-lookup"><span data-stu-id="a4347-222">**Route content searches:** You can route the content searches of SharePoint sites and OneDrive accounts to a satellite datacenter.</span></span> <span data-ttu-id="a4347-223">这意味着您可以指定将运行搜索的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-223">This means you can specify the datacenter location where searches will be run.</span></span>

    <span data-ttu-id="a4347-224">使用 **Region** 参数的下列值之一来控制搜索将在其中运行的数据中心位置，该位置SharePoint网站和OneDrive帐户。</span><span class="sxs-lookup"><span data-stu-id="a4347-224">Use one of the following values for the **Region** parameter to control the datacenter location that searches will run in when searching SharePoint sites and OneDrive accounts.</span></span> 
  
    |<span data-ttu-id="a4347-225">**参数值**</span><span class="sxs-lookup"><span data-stu-id="a4347-225">**Parameter value**</span></span>|<span data-ttu-id="a4347-226">**数据中心路由位置SharePoint**</span><span class="sxs-lookup"><span data-stu-id="a4347-226">**Datacenter routing locations for SharePoint**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="a4347-227">NAM</span><span class="sxs-lookup"><span data-stu-id="a4347-227">NAM</span></span>  <br/> |<span data-ttu-id="a4347-228">美国</span><span class="sxs-lookup"><span data-stu-id="a4347-228">US</span></span>  <br/> |
    |<span data-ttu-id="a4347-229">EUR</span><span class="sxs-lookup"><span data-stu-id="a4347-229">EUR</span></span>  <br/> |<span data-ttu-id="a4347-230">欧洲</span><span class="sxs-lookup"><span data-stu-id="a4347-230">Europe</span></span>  <br/> |
    |<span data-ttu-id="a4347-231">APC</span><span class="sxs-lookup"><span data-stu-id="a4347-231">APC</span></span>  <br/> |<span data-ttu-id="a4347-232">亚太地区</span><span class="sxs-lookup"><span data-stu-id="a4347-232">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="a4347-233">CAN</span><span class="sxs-lookup"><span data-stu-id="a4347-233">CAN</span></span>  <br/> |<span data-ttu-id="a4347-234">美国</span><span class="sxs-lookup"><span data-stu-id="a4347-234">US</span></span>  <br/> |
    |<span data-ttu-id="a4347-235">AUS</span><span class="sxs-lookup"><span data-stu-id="a4347-235">AUS</span></span>  <br/> |<span data-ttu-id="a4347-236">亚太地区</span><span class="sxs-lookup"><span data-stu-id="a4347-236">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="a4347-237">KOR</span><span class="sxs-lookup"><span data-stu-id="a4347-237">KOR</span></span>  <br/> |<span data-ttu-id="a4347-238">组织的默认数据中心</span><span class="sxs-lookup"><span data-stu-id="a4347-238">The organization's default datacenter</span></span>  <br/> |
    |<span data-ttu-id="a4347-239">GBR</span><span class="sxs-lookup"><span data-stu-id="a4347-239">GBR</span></span>  <br/> |<span data-ttu-id="a4347-240">欧洲</span><span class="sxs-lookup"><span data-stu-id="a4347-240">Europe</span></span>  <br/> |
    |<span data-ttu-id="a4347-241">JPN</span><span class="sxs-lookup"><span data-stu-id="a4347-241">JPN</span></span>  <br/> |<span data-ttu-id="a4347-242">亚太地区</span><span class="sxs-lookup"><span data-stu-id="a4347-242">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="a4347-243">IND</span><span class="sxs-lookup"><span data-stu-id="a4347-243">IND</span></span>  <br/> |<span data-ttu-id="a4347-244">亚太地区</span><span class="sxs-lookup"><span data-stu-id="a4347-244">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="a4347-245">一百万</span><span class="sxs-lookup"><span data-stu-id="a4347-245">LAM</span></span>  <br/> |<span data-ttu-id="a4347-246">美国</span><span class="sxs-lookup"><span data-stu-id="a4347-246">US</span></span>  <br/> |
    |<span data-ttu-id="a4347-247">NOR</span><span class="sxs-lookup"><span data-stu-id="a4347-247">NOR</span></span>  <br/> |<span data-ttu-id="a4347-248">欧洲</span><span class="sxs-lookup"><span data-stu-id="a4347-248">Europe</span></span> |
    |<span data-ttu-id="a4347-249">BRA</span><span class="sxs-lookup"><span data-stu-id="a4347-249">BRA</span></span>  <br/> |<span data-ttu-id="a4347-250">北美数据中心</span><span class="sxs-lookup"><span data-stu-id="a4347-250">North American datacenters</span></span> |
    |||

   <span data-ttu-id="a4347-251">如果不为搜索权限筛选器指定 **Region** 参数，将搜索组织SharePoint区域。</span><span class="sxs-lookup"><span data-stu-id="a4347-251">If you don't specify the **Region** parameter for a search permissions filter, the organization's primary SharePoint region will be searched.</span></span> <span data-ttu-id="a4347-252">搜索结果将导出到最近的数据中心。</span><span class="sxs-lookup"><span data-stu-id="a4347-252">Search results are exported to the closest datacenter.</span></span>

   <span data-ttu-id="a4347-253">为了简化概念 **，Region** 参数控制用于搜索 SharePoint 和 OneDrive 中的内容的数据中心。</span><span class="sxs-lookup"><span data-stu-id="a4347-253">To simplify the concept, the **Region** parameter controls the datacenter that is used to search for content in SharePoint and OneDrive.</span></span> <span data-ttu-id="a4347-254">这不适用于搜索网站中的内容Exchange Exchange内容搜索不受数据中心的地理位置限制。</span><span class="sxs-lookup"><span data-stu-id="a4347-254">This doesn't apply to searching for content in Exchange because Exchange content searches aren't bound by the geographic location of datacenters.</span></span> <span data-ttu-id="a4347-255">此外，相同的 **Region** 参数值可能还指示通过导出的数据中心。</span><span class="sxs-lookup"><span data-stu-id="a4347-255">Also, the same **Region** parameter value may also dictate the datacenter that exports are routed through.</span></span> <span data-ttu-id="a4347-256">这通常是控制跨地理平台移动数据所必需的。</span><span class="sxs-lookup"><span data-stu-id="a4347-256">This is often necessary to control the movement of data across geographic boarders.</span></span>

> [!NOTE]
> <span data-ttu-id="a4347-257">如果您使用的是 Advanced eDiscovery，**则 Region** 参数不控制导出数据的区域。</span><span class="sxs-lookup"><span data-stu-id="a4347-257">If you're using Advanced eDiscovery, the **Region** parameter doesn't control the region that data is exported from.</span></span> <span data-ttu-id="a4347-258">数据从组织的主数据中心导出。</span><span class="sxs-lookup"><span data-stu-id="a4347-258">Data is exported from the organization's primary datacenter.</span></span> <span data-ttu-id="a4347-259">此外，搜索 SharePoint 和 OneDrive 中的内容不受数据中心的地理位置限制。</span><span class="sxs-lookup"><span data-stu-id="a4347-259">Also, searching for content in SharePoint and OneDrive isn't bound by the geographic location of datacenters.</span></span> <span data-ttu-id="a4347-260">搜索所有数据中心。</span><span class="sxs-lookup"><span data-stu-id="a4347-260">All datacenters are searched.</span></span> <span data-ttu-id="a4347-261">有关解决方案Advanced eDiscovery，请参阅 Advanced eDiscovery[中的](overview-ediscovery-20.md)Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a4347-261">For more information about Advanced eDiscovery, see [Overview of the Advanced eDiscovery solution in Microsoft 365](overview-ediscovery-20.md).</span></span>

<span data-ttu-id="a4347-262">下面是为合规性边界创建搜索权限筛选器时使用 **Region** 参数的示例。</span><span class="sxs-lookup"><span data-stu-id="a4347-262">Here are examples of using the **Region** parameter when creating search permission filters for compliance boundaries.</span></span> <span data-ttu-id="a4347-263">这假定 Fourth Coffee 子公司位于北美，Coho Winery 位于欧洲。</span><span class="sxs-lookup"><span data-stu-id="a4347-263">This assumes that the Fourth Coffee subsidiary is located in North America and that Coho Winery is in Europe.</span></span> 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

<span data-ttu-id="a4347-264">在多地理位置环境中搜索和导出内容时，请记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="a4347-264">Keep the following things in mind when searching and exporting content in multi-geo environments.</span></span>
  
- <span data-ttu-id="a4347-265">**Region** 参数不控制 Exchange 邮箱的搜索。</span><span class="sxs-lookup"><span data-stu-id="a4347-265">The **Region** parameter doesn't control searches of Exchange mailboxes.</span></span> <span data-ttu-id="a4347-266">搜索邮箱时，将搜索所有数据中心。</span><span class="sxs-lookup"><span data-stu-id="a4347-266">All datacenters will be searched when you search mailboxes.</span></span> <span data-ttu-id="a4347-267">若要限制搜索Exchange的范围，在创建或更改搜索权限筛选器时，请使用 **Filters** 参数。</span><span class="sxs-lookup"><span data-stu-id="a4347-267">To limit the scope of which Exchange mailboxes are searched, use the **Filters** parameter when creating or changing a search permissions filter.</span></span>

- <span data-ttu-id="a4347-268">如果电子数据展示管理员需要跨多个 SharePoint 区域进行搜索，则需要为电子数据展示管理员创建一个不同的用户帐户，以在搜索权限筛选器中用于指定 SharePoint 站点或 OneDrive 帐户所在的区域。</span><span class="sxs-lookup"><span data-stu-id="a4347-268">If it's necessary for an eDiscovery Manager to search across multiple SharePoint regions, you need to create a different user account for that eDiscovery manager to use in the search permissions filter to specify the region where the SharePoint sites or OneDrive accounts are located.</span></span> <span data-ttu-id="a4347-269">有关设置此设置的信息，请参阅内容搜索中的"在SharePoint Multi-Geo环境中[搜索内容"部分](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment)。</span><span class="sxs-lookup"><span data-stu-id="a4347-269">For more information about setting this up, see the "Searching for content in a SharePoint Multi-Geo environment" section in [Content Search](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment).</span></span>

- <span data-ttu-id="a4347-270">在搜索 SharePoint 和 OneDrive 中的内容时 **，Region** 参数将搜索引导到电子数据展示管理员将在其中执行电子数据展示调查的主位置或附属位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-270">When searching for content in SharePoint and OneDrive, the **Region** parameter directs searches to either the primary or satellite location where the eDiscovery manager will conduct eDiscovery investigations.</span></span> <span data-ttu-id="a4347-271">如果电子数据展示SharePoint搜索OneDrive搜索权限筛选器中指定的区域之外的所有网站，则不返回任何搜索结果。</span><span class="sxs-lookup"><span data-stu-id="a4347-271">If an eDiscovery manager searches SharePoint and OneDrive sites outside of the region that's specified in the search permissions filter, no search results are returned.</span></span>

- <span data-ttu-id="a4347-272">导出搜索结果时，所有内容位置 (包括 Exchange、Skype for Business、SharePoint、OneDrive 以及可以使用内容搜索工具) 搜索的其他服务中的内容将上载到数据中心中由 **Region** 参数指定的 Azure 存储空间 位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-272">When exporting search results, content from all content locations (including Exchange, Skype for Business, SharePoint, OneDrive, and other services that you can search by using the Content Search tool) are uploaded to the Azure Storage location in the datacenter that's specified by the **Region** parameter.</span></span> <span data-ttu-id="a4347-273">这可帮助组织通过不允许跨受控边界导出内容来保持合规性。</span><span class="sxs-lookup"><span data-stu-id="a4347-273">This helps organizations stay within compliance by not allowing content to be exported across controlled borders.</span></span> <span data-ttu-id="a4347-274">如果在搜索权限筛选器中未指定任何区域，内容将上载到组织的主数据中心。</span><span class="sxs-lookup"><span data-stu-id="a4347-274">If no region is specified in the search permissions filter, content is uploaded to the organization's primary datacenter.</span></span>

- <span data-ttu-id="a4347-275">您可以编辑现有的搜索权限筛选器，以通过运行以下命令添加或更改区域：</span><span class="sxs-lookup"><span data-stu-id="a4347-275">You can edit an existing search permissions filter to add or change the region by running the following command:</span></span>

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a><span data-ttu-id="a4347-276">使用中心网站的合规性SharePoint边界</span><span class="sxs-lookup"><span data-stu-id="a4347-276">Using compliance boundaries for SharePoint hub sites</span></span>

<span data-ttu-id="a4347-277">[SharePoint中心网站](/sharepoint/dev/features/hub-site/hub-site-overview)通常与电子数据展示合规性边界遵循的相同地理或机构边界保持一致。</span><span class="sxs-lookup"><span data-stu-id="a4347-277">[SharePoint hub sites](/sharepoint/dev/features/hub-site/hub-site-overview) often align with the same geographical or agency boundaries that eDiscovery compliance boundaries follow.</span></span> <span data-ttu-id="a4347-278">这意味着您可以使用中心网站的站点 ID 属性创建合规性边界。</span><span class="sxs-lookup"><span data-stu-id="a4347-278">That means you can use the site ID property of the hub site to create a compliance boundary.</span></span> <span data-ttu-id="a4347-279">为此，请使用 SharePoint Online PowerShell 中的[Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) cmdlet 获取中心网站的 SiteId，然后使用部门 ID 属性的此值创建搜索权限筛选器。</span><span class="sxs-lookup"><span data-stu-id="a4347-279">To do this, use the [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) cmdlet in SharePoint Online PowerShell to obtain the SiteId for the hub site and then use this value for the department ID property to create a search permissions filter.</span></span>

<span data-ttu-id="a4347-280">使用以下语法为中心网站创建SharePoint筛选器：</span><span class="sxs-lookup"><span data-stu-id="a4347-280">Use the following syntax to create a search permissions filter for a SharePoint hub site:</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

<span data-ttu-id="a4347-281">下面是为 Coho Winery 代理中心网站创建搜索权限筛选器的示例：</span><span class="sxs-lookup"><span data-stu-id="a4347-281">Here's an example of creating a search permissions filter for a hub site for the Coho Winery agency:</span></span>

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a><span data-ttu-id="a4347-282">合规性边界限制</span><span class="sxs-lookup"><span data-stu-id="a4347-282">Compliance boundary limitations</span></span>

<span data-ttu-id="a4347-283">管理电子数据展示事例和使用合规性边界的调查时，请记住以下限制。</span><span class="sxs-lookup"><span data-stu-id="a4347-283">Keep the following limitations in mind when managing eDiscovery cases and investigations that use of compliance boundaries.</span></span>
  
- <span data-ttu-id="a4347-284">创建和运行搜索时，可选择公司外部的内容位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-284">When creating and running a search, you can select content locations that are outside of your agency.</span></span> <span data-ttu-id="a4347-285">但是由于搜索权限筛选器，因此这些位置的内容不包含在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="a4347-285">However, because of the search permissions filter, content from those locations isn't included in the search results.</span></span>

- <span data-ttu-id="a4347-286">合规性边界不适用于电子数据展示事例中的保留。</span><span class="sxs-lookup"><span data-stu-id="a4347-286">Compliance boundaries don't apply to holds in eDiscovery cases.</span></span> <span data-ttu-id="a4347-287">这意味着一个公司中的电子数据展示管理者可以将用户放在不同的公司中保留。</span><span class="sxs-lookup"><span data-stu-id="a4347-287">That means an eDiscovery manager in one agency can place a user in a different agency on hold.</span></span> <span data-ttu-id="a4347-288">但是，如果电子数据展示管理器搜索已保留用户的内容位置，将实施合规性边界。</span><span class="sxs-lookup"><span data-stu-id="a4347-288">However, the compliance boundary will be enforced if the eDiscovery manager searches the content locations of the user who was placed on hold.</span></span> <span data-ttu-id="a4347-289">这意味着电子数据展示管理器无法搜索用户的内容位置，即使他们能够保留用户。</span><span class="sxs-lookup"><span data-stu-id="a4347-289">That means the eDiscovery manager won't be able search the user's content locations, even though they were able to place the user on hold.</span></span>

    <span data-ttu-id="a4347-290">此外，保留统计信息仅适用于公司中的内容位置。</span><span class="sxs-lookup"><span data-stu-id="a4347-290">Also, hold statistics will only apply to content locations in the agency.</span></span>

- <span data-ttu-id="a4347-291">如果您分配了搜索权限筛选器 (邮箱或网站筛选器) 并且您尝试导出包含组织中所有 SharePoint 网站的搜索的未索引项目，您将收到以下错误消息： `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` 。</span><span class="sxs-lookup"><span data-stu-id="a4347-291">If you're assigned a search permissions filter (either a mailbox or a site filter) and you try to export unindexed items for a search that includes all SharePoint sites in your organization, you'll receive the following error message: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied`.</span></span> <span data-ttu-id="a4347-292">如果分配了搜索权限筛选器，并且希望从 SharePoint 导出未索引的项目，您必须重新运行搜索并包括要搜索的特定 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="a4347-292">If you're assigned a search permissions filter and you want to export unindexed items from SharePoint, you'll have to rerun the search and include specific SharePoint sites to search.</span></span> <span data-ttu-id="a4347-293">否则，只能从包含所有网站索引项的搜索中导出SharePoint项。</span><span class="sxs-lookup"><span data-stu-id="a4347-293">Otherwise, you'll only be able to export indexed items from a search that includes all SharePoint sites.</span></span> <span data-ttu-id="a4347-294">有关导出搜索结果时的选项的详细信息，请参阅导出 [内容搜索结果](export-search-results.md#step-1-prepare-search-results-for-export)。</span><span class="sxs-lookup"><span data-stu-id="a4347-294">For more information about the options when you export search results, see [Export Content search results](export-search-results.md#step-1-prepare-search-results-for-export).</span></span>

- <span data-ttu-id="a4347-295">搜索权限筛选器未应用于 Exchange 公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="a4347-295">Search permissions filters aren't applied to Exchange public folders.</span></span>

## <a name="more-information"></a><span data-ttu-id="a4347-296">更多信息</span><span class="sxs-lookup"><span data-stu-id="a4347-296">More information</span></span>

- <span data-ttu-id="a4347-297">如果邮箱已取消许可或软删除，则不再在合规性边界内考虑用户。</span><span class="sxs-lookup"><span data-stu-id="a4347-297">If a mailbox is de-licensed or soft-deleted, the user will no longer be considered within the compliance boundary.</span></span> <span data-ttu-id="a4347-298">如果在删除邮箱时将其置于保留状态，则保留在邮箱中的内容仍受合规性边界或搜索权限筛选器限制。</span><span class="sxs-lookup"><span data-stu-id="a4347-298">If a hold was placed on the mailbox when it was deleted, the content preserved in the mailbox is still subject to a compliance boundary or search permissions filter.</span></span>

- <span data-ttu-id="a4347-299">如果为用户实现了合规性边界和搜索权限筛选器，则建议您不要删除用户的邮箱，而不要删除其OneDrive帐户。</span><span class="sxs-lookup"><span data-stu-id="a4347-299">If compliance boundaries and search permissions filters are implemented for a user, then we recommend that you don't delete a user's mailbox and not their OneDrive account.</span></span> <span data-ttu-id="a4347-300">换句话说，如果您删除用户的邮箱，则还应删除用户的 OneDrive 帐户，因为 mailbox_RecipientFilter 用于强制执行 OneDrive 的搜索权限筛选器。</span><span class="sxs-lookup"><span data-stu-id="a4347-300">In other words, if you delete a user's mailbox, you should also remove the user's OneDrive account since mailbox_RecipientFilter is used to enforce search permission filter for OneDrive.</span></span>

- <span data-ttu-id="a4347-301">合规性边界和搜索权限筛选器取决于在 Exchange、OneDrive 和 SharePoint 中的内容上标记的属性，以及此标记内容的后续索引。</span><span class="sxs-lookup"><span data-stu-id="a4347-301">Compliance boundaries and search permissions filters depend on attributes being stamped on content in Exchange, OneDrive, and SharePoint and the subsequent indexing of this stamped content.</span></span>

- <span data-ttu-id="a4347-302">建议不要将排除筛选器 (例如，在基于内容的合规性) 搜索 `-not()` 权限筛选器中使用。</span><span class="sxs-lookup"><span data-stu-id="a4347-302">We don't recommend using exclusion filters (such as using `-not()` in a search permissions filter) for a content-based compliance boundary.</span></span> <span data-ttu-id="a4347-303">如果未对具有最近更新的属性的内容编制索引，则使用排除筛选器可能会获得意外结果。</span><span class="sxs-lookup"><span data-stu-id="a4347-303">Using an exclusion filter can have unexpected results if content with recently updated attributes hasn't been indexed.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a4347-304">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="a4347-304">Frequently asked questions</span></span>

<span data-ttu-id="a4347-305">**谁可以使用 (cmdlet 和 New-ComplianceSecurityFilter cmdlet Set-ComplianceSecurityFilter和管理) ？**</span><span class="sxs-lookup"><span data-stu-id="a4347-305">**Who can create and manage search permissions filters (using New-ComplianceSecurityFilter and Set-ComplianceSecurityFilter cmdlets)?**</span></span>
  
<span data-ttu-id="a4347-306">若要创建、查看和修改搜索权限筛选器，您必须是 Microsoft 365 合规中心中组织管理角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="a4347-306">To create, view, and modify search permissions filters, you have to be a member of the Organization Management role group in the Microsoft 365 compliance center.</span></span>
  
<span data-ttu-id="a4347-307">**如果将电子数据展示管理员分配给跨多个机构的多个角色组，如何搜索一个机构或另一个机构中的内容？**</span><span class="sxs-lookup"><span data-stu-id="a4347-307">**If an eDiscovery manager is assigned to more than one role group that spans multiple agencies, how do they search for content in one agency or the other?**</span></span>
  
<span data-ttu-id="a4347-308">电子数据展示管理员可以将参数添加到其搜索查询中，以将搜索限制到特定机构。</span><span class="sxs-lookup"><span data-stu-id="a4347-308">The eDiscovery manager can add parameters to their search query that restrict the search to a specific agency.</span></span> <span data-ttu-id="a4347-309">例如，如果组织已指定 **CustomAttribute10** 属性来区分机构，他们可以将以下内容追加到搜索查询中，以搜索特定机构中的邮箱和 OneDrive 帐户  `CustomAttribute10:<value>` ：。</span><span class="sxs-lookup"><span data-stu-id="a4347-309">For example, if an organization has specified the **CustomAttribute10** property to differentiate agencies, they can append the following to their search query to search mailboxes and OneDrive accounts in a specific agency:  `CustomAttribute10:<value>`.</span></span>
  
<span data-ttu-id="a4347-310">**如果用作搜索权限筛选器中的合规性属性的值发生更改，会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="a4347-310">**What happens if the value of the attribute that's used as the compliance attribute in a search permissions filter is changed?**</span></span>
  
<span data-ttu-id="a4347-311">如果更改了筛选器中使用的属性的值，则搜索权限筛选器最多需要三天才能强制实施合规性边界。</span><span class="sxs-lookup"><span data-stu-id="a4347-311">It takes up to three days for a search permissions filter to enforce the compliance boundary if the value of the attribute that's used in the filter is changed.</span></span> <span data-ttu-id="a4347-312">例如，在 Contoso 方案中，假设 Fourth Coffee 机构中的用户被转移到 Coho Winery 代理。</span><span class="sxs-lookup"><span data-stu-id="a4347-312">For example, in the Contoso scenario let's say that a user in the Fourth Coffee agency is transferred to the Coho Winery agency.</span></span> <span data-ttu-id="a4347-313">因此，用户对象上的 **Department** 属性的值从 *FourthCoffee* 更改为 *CohoWinery*。</span><span class="sxs-lookup"><span data-stu-id="a4347-313">As a result, the value of the **Department** attribute on the user object is changed from *FourthCoffee* to *CohoWinery*.</span></span> <span data-ttu-id="a4347-314">在这种情况下，Fourth Coffee 电子数据展示和电子商务将在属性更改后的最多三天内获取该用户的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="a4347-314">In this situation, Fourth Coffee eDiscovery and investors will get search results for that user for up three days after the attribute is changed.</span></span> <span data-ttu-id="a4347-315">同样，Coho Winery 电子数据展示管理员和调查人员最多需要三天的时间才能获取用户的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="a4347-315">Similarly, it takes up to three days before Coho Winery eDiscovery managers and investigators get search results for the user.</span></span>
  
<span data-ttu-id="a4347-316">**电子数据展示管理员能否从两个单独的合规性边界查看内容？**</span><span class="sxs-lookup"><span data-stu-id="a4347-316">**Can an eDiscovery manager see content from two separate compliance boundaries?**</span></span>
  
<span data-ttu-id="a4347-317">可以，在搜索 Exchange 邮箱时，可以通过将电子数据展示管理员添加到对两个机构都可见的角色组来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="a4347-317">Yes, this can be done when searching Exchange mailboxes by adding the eDiscovery manager to role groups that have visibility to both agencies.</span></span> <span data-ttu-id="a4347-318">但是，在搜索 SharePoint 网站和 OneDrive 帐户时，只有在机构位于同一区域或地理位置时，电子数据展示管理员才能搜索不同合规性边界内的内容。</span><span class="sxs-lookup"><span data-stu-id="a4347-318">However when searching SharePoint sites and OneDrive accounts, an eDiscovery manager can search for content in different compliance boundaries only if the agencies are in the same region or geo location.</span></span> <span data-ttu-id="a4347-319">**注意：** 此网站限制不适用于高级电子数据展示，因为搜索 SharePoint 和 OneDrive 中的内容不受地理位置限制。</span><span class="sxs-lookup"><span data-stu-id="a4347-319">**Note:** This limitation for sites doesn't apply in Advanced eDiscovery because searching for content in SharePoint and OneDrive isn't bound by geographic location.</span></span>
  
<span data-ttu-id="a4347-320">**搜索权限筛选器是否适用于电子数据展示案例保留、Microsoft 365 保留策略或 DLP？**</span><span class="sxs-lookup"><span data-stu-id="a4347-320">**Do search permissions filters work for eDiscovery case holds, Microsoft 365 retention policies, or DLP?**</span></span>
  
<span data-ttu-id="a4347-321">否，此时不会。</span><span class="sxs-lookup"><span data-stu-id="a4347-321">No, not at this time.</span></span>
  
<span data-ttu-id="a4347-322">**如果指定一个控制内容导出位置的区域，但该区域中没有 SharePoint 组织，我能否仍搜索 SharePoint？**</span><span class="sxs-lookup"><span data-stu-id="a4347-322">**If I specify a region to control where content is exported, but I don't have a SharePoint organization in that region, can I still search SharePoint?**</span></span>
  
<span data-ttu-id="a4347-323">如果搜索权限筛选器中指定的区域在你的组织中不存在，将搜索默认区域。</span><span class="sxs-lookup"><span data-stu-id="a4347-323">If the region specified in the search permissions filter doesn't exist in your organization, the default region will be searched.</span></span>
  
<span data-ttu-id="a4347-324">**可以在组织中创建的搜索权限筛选器的最大数量是什么？**</span><span class="sxs-lookup"><span data-stu-id="a4347-324">**What is the maximum number of search permissions filters that can be created in an organization?**</span></span>
  
<span data-ttu-id="a4347-325">对可以在组织中创建的搜索权限筛选器的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="a4347-325">There is no limit to the number of search permissions filters that can be created in an organization.</span></span> <span data-ttu-id="a4347-326">但是，当搜索权限筛选器超过 100 个时，搜索性能将受到影响。</span><span class="sxs-lookup"><span data-stu-id="a4347-326">However, search performance will be impacted when there are more than 100 search permissions filters.</span></span> <span data-ttu-id="a4347-327">若要尽可能减少组织中搜索权限筛选器的数量，请创建尽可能将 Exchange、SharePoint 和 OneDrive 的规则合并到单个搜索权限筛选器中的筛选器。</span><span class="sxs-lookup"><span data-stu-id="a4347-327">To keep the number of search permissions filters in your organization as small as possible, create filters that combine rules for Exchange, SharePoint, and OneDrive into a single search permissions filter whenever possible.</span></span>
