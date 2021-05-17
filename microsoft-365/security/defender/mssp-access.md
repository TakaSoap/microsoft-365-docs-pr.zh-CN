---
title: 提供托管安全服务提供程序 (MSSP) 访问
description: 了解从安全中心Microsoft Defender 安全中心安全Microsoft 365更改
keywords: 入门：Microsoft 365安全中心、适用于 Office 365 的 Microsoft Defender、适用于终结点的 Microsoft Defender、MDO、MDE、单窗格的门户、聚合门户、安全门户、Defender 安全门户
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 4b34d3ea20716fb2424d9317b8a51c088a5714a6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935349"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="8ec1a-104">提供托管安全服务提供程序 (MSSP) 访问</span><span class="sxs-lookup"><span data-stu-id="8ec1a-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="8ec1a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8ec1a-105">**Applies to:**</span></span>

- [<span data-ttu-id="8ec1a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ec1a-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="8ec1a-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8ec1a-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="8ec1a-108">若要实现多租户委派访问解决方案，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8ec1a-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="8ec1a-109">在[安全中心的](/windows/security/threat-protection/microsoft-defender-atp/rbac)Defender for Endpoint 中启用基于角色Microsoft 365，并与 Azure AD Azure Active Directory (组) 连接。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-109">Enable [role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="8ec1a-110">配置 [用于访问请求](/azure/active-directory/governance/identity-governance-overview) 和预配的治理访问包。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-110">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="8ec1a-111">在 [Microsoft Myaccess 中管理访问请求和审核](/azure/active-directory/governance/entitlement-management-request-approve)。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-111">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="8ec1a-112">在安全中心的 Microsoft Defender for Endpoint 中Microsoft 365基于角色的访问控制</span><span class="sxs-lookup"><span data-stu-id="8ec1a-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="8ec1a-113">**为客户 AAD 中的 MSSP 资源创建访问组：组**</span><span class="sxs-lookup"><span data-stu-id="8ec1a-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="8ec1a-114">这些组将链接到你在安全中心的 Defender for Endpoint Microsoft 365角色。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="8ec1a-115">为此，在客户 AD 租户中，创建三个组。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="8ec1a-116">在我们的示例方法中，我们将创建以下组：</span><span class="sxs-lookup"><span data-stu-id="8ec1a-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="8ec1a-117">第 1 层分析员</span><span class="sxs-lookup"><span data-stu-id="8ec1a-117">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="8ec1a-118">第 2 层分析员</span><span class="sxs-lookup"><span data-stu-id="8ec1a-118">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="8ec1a-119">MSSP 分析员审批者</span><span class="sxs-lookup"><span data-stu-id="8ec1a-119">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="8ec1a-120">在安全中心角色和组的 Customer Defender for Endpoint 中为Microsoft 365 Defender 终结点角色创建 Defender。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="8ec1a-121">若要在客户安全中心Microsoft 365 RBAC，请通过具有全局管理员>安全管理员权限的用户帐户&组>角色"访问"权限">终结点角色"。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![MSSP 访问的图像](../../media/mssp-access.png)

    <span data-ttu-id="8ec1a-123">然后，创建 RBAC 角色以满足 MSSP SOC 层需求。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="8ec1a-124">通过"分配的用户组"将这些角色链接到已创建的用户组。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="8ec1a-125">两个可能的角色：</span><span class="sxs-lookup"><span data-stu-id="8ec1a-125">Two possible roles:</span></span>

    - <span data-ttu-id="8ec1a-126">**第 1 层分析员**</span><span class="sxs-lookup"><span data-stu-id="8ec1a-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="8ec1a-127">执行除实时响应以外的所有操作并管理安全设置。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="8ec1a-128">**第 2 层分析员**</span><span class="sxs-lookup"><span data-stu-id="8ec1a-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="8ec1a-129">第 1 层功能以及实时 [响应](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="8ec1a-129">Tier 1 capabilities with the addition to [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="8ec1a-130">有关详细信息，请参阅使用 [基于角色的访问控制](/windows/security/threat-protection/microsoft-defender-atp/rbac)。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-130">For more information, see [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="8ec1a-131">配置治理访问包</span><span class="sxs-lookup"><span data-stu-id="8ec1a-131">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="8ec1a-132">**在客户 AAD 中添加 MSSP 作为连接组织：标识治理**</span><span class="sxs-lookup"><span data-stu-id="8ec1a-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="8ec1a-133">将 MSSP 添加为连接的组织将允许 MSSP 请求并设置访问权限。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="8ec1a-134">为此，在客户 AD 租户中，访问标识治理：已连接组织。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="8ec1a-135">添加新组织，然后通过租户 ID 或域搜索 MSSP 分析员租户。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="8ec1a-136">建议为 MSSP 分析员创建单独的 AD 租户。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="8ec1a-137">**在客户 AAD：标识治理中创建资源目录**</span><span class="sxs-lookup"><span data-stu-id="8ec1a-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="8ec1a-138">资源目录是在客户 AD 租户中创建的访问包的逻辑集合。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="8ec1a-139">为此，在客户 AD 租户中，访问 Identity Governance： Catalogs，并添加新 **目录**。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="8ec1a-140">在我们的示例中，我们将它称为 **MSSP Accesses**。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-140">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![新目录的图像](../../media/goverance-catalog.png)

    <span data-ttu-id="8ec1a-142">有关详细信息，请参阅创建 [资源目录](/azure/active-directory/governance/entitlement-management-catalog-create)。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-142">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="8ec1a-143">**为 MSSP 资源创建访问包客户 AAD：标识治理**</span><span class="sxs-lookup"><span data-stu-id="8ec1a-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="8ec1a-144">访问包是请求者在审批时将授予的权限和访问权限的集合。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="8ec1a-145">为此，在客户 AD 租户中，访问标识治理：访问程序包，并添加新 **的访问包**。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="8ec1a-146">为 MSSP 审批者以及每个分析员层创建一个访问包。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="8ec1a-147">例如，以下第 1 层分析员配置将创建一个访问包：</span><span class="sxs-lookup"><span data-stu-id="8ec1a-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="8ec1a-148">需要 AD 组 **MSSP 分析员审批者** 的成员来授权新请求</span><span class="sxs-lookup"><span data-stu-id="8ec1a-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="8ec1a-149">每年进行一次访问评审，SOC 分析师可在其中请求访问扩展</span><span class="sxs-lookup"><span data-stu-id="8ec1a-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="8ec1a-150">只能由 MSSP SOC 租户中的用户请求</span><span class="sxs-lookup"><span data-stu-id="8ec1a-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="8ec1a-151">Access 自动在 365 天后过期</span><span class="sxs-lookup"><span data-stu-id="8ec1a-151">Access auto expires after 365 days</span></span>

    ![新访问包的图像](../../media/new-access-package.png)

    <span data-ttu-id="8ec1a-153">有关详细信息，请参阅 [创建新的访问包](/azure/active-directory/governance/entitlement-management-access-package-create)。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-153">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="8ec1a-154">**从客户 AAD 提供 MSSP 资源的访问请求链接：标识治理**</span><span class="sxs-lookup"><span data-stu-id="8ec1a-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="8ec1a-155">MSSP SOC 分析员使用"我的访问门户"链接通过创建的访问包请求访问。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="8ec1a-156">该链接是持久链接，这意味着随着时间的推移，新分析师可能会使用相同的链接。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="8ec1a-157">分析员请求会进入一个队列，等待 **MSSP 分析员审批者审批**。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>


    ![访问属性的图像](../../media/access-properties.png)

    <span data-ttu-id="8ec1a-159">链接位于每个访问包的概述页面上。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="8ec1a-160">管理访问权限</span><span class="sxs-lookup"><span data-stu-id="8ec1a-160">Manage access</span></span> 

1. <span data-ttu-id="8ec1a-161">查看和授权客户和/或 MSSP myaccess 中的访问请求。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="8ec1a-162">访问请求在客户 My Access 中由 MSSP 分析员审批者组的成员进行管理。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="8ec1a-163">为此，请通过使用：访问客户的 myaccess。 `https://myaccess.microsoft.com/@<Customer Domain >`</span><span class="sxs-lookup"><span data-stu-id="8ec1a-163">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="8ec1a-164">示例： `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="8ec1a-164">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="8ec1a-165">在 UI 的" **审批"部分批准** 或拒绝请求。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="8ec1a-166">此时，已预配分析师访问权限，并且每个分析师都应能够访问客户的安全Microsoft 365中心：</span><span class="sxs-lookup"><span data-stu-id="8ec1a-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span> 

    <span data-ttu-id="8ec1a-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` 具有分配的权限和角色。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ec1a-168">安全中心内 Microsoft Defender for Endpoint Microsoft 365当前允许每个浏览器窗口访问单个租户。</span><span class="sxs-lookup"><span data-stu-id="8ec1a-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span>