---
title: '向 MSSP 应用程序授予对托管 (提供程序) '
description: 执行必要步骤以配置 MSSP 与 Microsoft Defender ATP 的集成
keywords: 托管安全服务提供程序， mssp， 配置， 集成
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1bb7bc3565bbb7c05f165c5649f3672ff33bb18b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165449"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a><span data-ttu-id="d05a6-104">向 MSSP (托管安全) 访问 (预览) </span><span class="sxs-lookup"><span data-stu-id="d05a6-104">Grant managed security service provider (MSSP) access (preview)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d05a6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d05a6-105">**Applies to:**</span></span>
- [<span data-ttu-id="d05a6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d05a6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d05a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d05a6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="d05a6-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="d05a6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d05a6-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="d05a6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
><span data-ttu-id="d05a6-110">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="d05a6-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d05a6-111">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="d05a6-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d05a6-112">若要实现多租户委派访问解决方案，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d05a6-112">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="d05a6-113">在 [Defender for](rbac.md) Endpoint 中启用基于角色的访问控制，并与 Active Directory (AD) 连接。</span><span class="sxs-lookup"><span data-stu-id="d05a6-113">Enable [role-based access control](rbac.md) in Defender for Endpoint and connect with Active Directory (AD) groups.</span></span>

2. <span data-ttu-id="d05a6-114">配置 [用于访问请求](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) 和预配的治理访问包。</span><span class="sxs-lookup"><span data-stu-id="d05a6-114">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="d05a6-115">在 [Microsoft Myaccess 中管理访问请求和审核](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)。</span><span class="sxs-lookup"><span data-stu-id="d05a6-115">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="d05a6-116">在 Microsoft Defender for Endpoint 中启用基于角色的访问控制</span><span class="sxs-lookup"><span data-stu-id="d05a6-116">Enable role-based access controls in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="d05a6-117">**为客户 AAD 中的 MSSP 资源创建访问组：组**</span><span class="sxs-lookup"><span data-stu-id="d05a6-117">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="d05a6-118">这些组将链接到你在 Defender for Endpoint 中创建的角色。</span><span class="sxs-lookup"><span data-stu-id="d05a6-118">These groups will be linked to the Roles you create in Defender for Endpoint.</span></span> <span data-ttu-id="d05a6-119">为此，在客户 AD 租户中，创建三个组。</span><span class="sxs-lookup"><span data-stu-id="d05a6-119">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="d05a6-120">在我们的示例方法中，我们将创建以下组：</span><span class="sxs-lookup"><span data-stu-id="d05a6-120">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="d05a6-121">第 1 层分析员</span><span class="sxs-lookup"><span data-stu-id="d05a6-121">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="d05a6-122">第 2 层分析员</span><span class="sxs-lookup"><span data-stu-id="d05a6-122">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="d05a6-123">MSSP 分析员审批者</span><span class="sxs-lookup"><span data-stu-id="d05a6-123">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="d05a6-124">在 Customer Defender for Endpoint 中为相应的访问级别创建适用于终结点的 Defender 角色。</span><span class="sxs-lookup"><span data-stu-id="d05a6-124">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint.</span></span>

    <span data-ttu-id="d05a6-125">若要在客户 Microsoft Defender 安全中心中启用RBAC，请从具有全局管理员或安全管理员权限的用户帐户访问"设置>权限>角色"和"启用角色"。</span><span class="sxs-lookup"><span data-stu-id="d05a6-125">To enable RBAC in the customer Microsoft Defender Security Center, access **Settings > Permissions > Roles** and "Turn on roles", from a user account with Global Administrator or Security Administrator rights.</span></span>

    ![MSSP 访问的图像](images/mssp-access.png)

    <span data-ttu-id="d05a6-127">然后，创建 RBAC 角色以满足 MSSP SOC 层需求。</span><span class="sxs-lookup"><span data-stu-id="d05a6-127">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="d05a6-128">通过"分配的用户组"将这些角色链接到已创建的用户组。</span><span class="sxs-lookup"><span data-stu-id="d05a6-128">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="d05a6-129">两个可能的角色：</span><span class="sxs-lookup"><span data-stu-id="d05a6-129">Two possible roles:</span></span>

    - <span data-ttu-id="d05a6-130">**第 1 层分析员**</span><span class="sxs-lookup"><span data-stu-id="d05a6-130">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="d05a6-131">执行除实时响应以外的所有操作并管理安全设置。</span><span class="sxs-lookup"><span data-stu-id="d05a6-131">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="d05a6-132">**第 2 层分析员**</span><span class="sxs-lookup"><span data-stu-id="d05a6-132">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="d05a6-133">第 1 层功能以及实时 [响应](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="d05a6-133">Tier 1 capabilities with the addition to [live response](live-response.md)</span></span>

    <span data-ttu-id="d05a6-134">有关详细信息，请参阅使用 [基于角色的访问控制](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="d05a6-134">For more information, see [Use role-based access control](rbac.md).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="d05a6-135">配置治理访问包</span><span class="sxs-lookup"><span data-stu-id="d05a6-135">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="d05a6-136">**在客户 AAD 中添加 MSSP 作为连接组织：标识治理**</span><span class="sxs-lookup"><span data-stu-id="d05a6-136">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="d05a6-137">将 MSSP 添加为连接的组织将允许 MSSP 请求并设置访问权限。</span><span class="sxs-lookup"><span data-stu-id="d05a6-137">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="d05a6-138">为此，在客户 AD 租户中，访问标识治理：已连接组织。</span><span class="sxs-lookup"><span data-stu-id="d05a6-138">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="d05a6-139">添加新组织，然后通过租户 ID 或域搜索 MSSP 分析员租户。</span><span class="sxs-lookup"><span data-stu-id="d05a6-139">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="d05a6-140">建议为 MSSP 分析员创建单独的 AD 租户。</span><span class="sxs-lookup"><span data-stu-id="d05a6-140">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="d05a6-141">**在客户 AAD：标识治理中创建资源目录**</span><span class="sxs-lookup"><span data-stu-id="d05a6-141">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="d05a6-142">资源目录是在客户 AD 租户中创建的访问包的逻辑集合。</span><span class="sxs-lookup"><span data-stu-id="d05a6-142">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="d05a6-143">为此，在客户 AD 租户中，访问 Identity Governance： Catalogs，并添加新 **目录**。</span><span class="sxs-lookup"><span data-stu-id="d05a6-143">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="d05a6-144">在我们的示例中，我们将它称为 **MSSP Accesses**。</span><span class="sxs-lookup"><span data-stu-id="d05a6-144">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![新目录的图像](images/goverance-catalog.png)

    <span data-ttu-id="d05a6-146">有关详细信息，请参阅创建 [资源目录](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)。</span><span class="sxs-lookup"><span data-stu-id="d05a6-146">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="d05a6-147">**为 MSSP 资源创建访问包客户 AAD：标识治理**</span><span class="sxs-lookup"><span data-stu-id="d05a6-147">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="d05a6-148">访问包是请求者在审批时将授予的权限和访问权限的集合。</span><span class="sxs-lookup"><span data-stu-id="d05a6-148">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="d05a6-149">为此，在客户 AD 租户中，访问标识治理：访问程序包，并添加新 **的访问包**。</span><span class="sxs-lookup"><span data-stu-id="d05a6-149">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="d05a6-150">为 MSSP 审批者以及每个分析员层创建一个访问包。</span><span class="sxs-lookup"><span data-stu-id="d05a6-150">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="d05a6-151">例如，以下第 1 层分析员配置将创建一个访问包：</span><span class="sxs-lookup"><span data-stu-id="d05a6-151">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="d05a6-152">需要 AD 组 **MSSP 分析员审批者** 的成员来授权新请求</span><span class="sxs-lookup"><span data-stu-id="d05a6-152">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="d05a6-153">每年进行一次访问评审，SOC 分析师可在其中请求访问扩展</span><span class="sxs-lookup"><span data-stu-id="d05a6-153">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="d05a6-154">只能由 MSSP SOC 租户中的用户请求</span><span class="sxs-lookup"><span data-stu-id="d05a6-154">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="d05a6-155">Access 自动在 365 天后过期</span><span class="sxs-lookup"><span data-stu-id="d05a6-155">Access auto expires after 365 days</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d05a6-156">![新访问包的图像](images/new-access-package.png)</span><span class="sxs-lookup"><span data-stu-id="d05a6-156">![Image of new access package](images/new-access-package.png)</span></span>

    <span data-ttu-id="d05a6-157">有关详细信息，请参阅 [创建新的访问包](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)。</span><span class="sxs-lookup"><span data-stu-id="d05a6-157">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="d05a6-158">**从客户 AAD 提供 MSSP 资源的访问请求链接：标识治理**</span><span class="sxs-lookup"><span data-stu-id="d05a6-158">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="d05a6-159">MSSP SOC 分析员使用"我的访问门户"链接通过创建的访问包请求访问。</span><span class="sxs-lookup"><span data-stu-id="d05a6-159">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="d05a6-160">该链接是持久链接，这意味着随着时间的推移，新分析师可能会使用相同的链接。</span><span class="sxs-lookup"><span data-stu-id="d05a6-160">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="d05a6-161">分析员请求会进入一个队列，等待 **MSSP 分析员审批者审批**。</span><span class="sxs-lookup"><span data-stu-id="d05a6-161">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d05a6-162">![访问属性的图像](images/access-properties.png)</span><span class="sxs-lookup"><span data-stu-id="d05a6-162">![Image of access properties](images/access-properties.png)</span></span>

    <span data-ttu-id="d05a6-163">链接位于每个访问包的概述页面上。</span><span class="sxs-lookup"><span data-stu-id="d05a6-163">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="d05a6-164">管理访问权限</span><span class="sxs-lookup"><span data-stu-id="d05a6-164">Manage access</span></span> 

1. <span data-ttu-id="d05a6-165">查看和授权客户和/或 MSSP myaccess 中的访问请求。</span><span class="sxs-lookup"><span data-stu-id="d05a6-165">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="d05a6-166">访问请求在客户 My Access 中由 MSSP 分析员审批者组的成员进行管理。</span><span class="sxs-lookup"><span data-stu-id="d05a6-166">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="d05a6-167">为此，请通过使用：访问客户的 myaccess。 `https://myaccess.microsoft.com/@<Customer Domain >`</span><span class="sxs-lookup"><span data-stu-id="d05a6-167">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="d05a6-168">示例： `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="d05a6-168">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="d05a6-169">在 UI 的" **审批"部分批准** 或拒绝请求。</span><span class="sxs-lookup"><span data-stu-id="d05a6-169">Approve or deny requests in the **Approvals** section of the UI.</span></span>

    <span data-ttu-id="d05a6-170">此时，已预配分析师访问权限，并且每个分析师应能够访问客户的 Microsoft Defender 安全中心： `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span><span class="sxs-lookup"><span data-stu-id="d05a6-170">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft Defender Security Center: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="d05a6-171">相关主题</span><span class="sxs-lookup"><span data-stu-id="d05a6-171">Related topics</span></span>
- [<span data-ttu-id="d05a6-172">访问 MSSP 客户门户</span><span class="sxs-lookup"><span data-stu-id="d05a6-172">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="d05a6-173">配置警报通知</span><span class="sxs-lookup"><span data-stu-id="d05a6-173">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="d05a6-174">从客户租户提取警报</span><span class="sxs-lookup"><span data-stu-id="d05a6-174">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)



 

