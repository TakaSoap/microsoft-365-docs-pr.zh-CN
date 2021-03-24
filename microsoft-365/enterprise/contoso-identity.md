---
title: Contoso Corporation 的标识
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何利用标识即服务 (IDaaS)，并为其员工提供基于云的身份验证以及为其合作伙伴和客户提供联合身份验证。
ms.openlocfilehash: f3c8746345683652ce601400ae7297e96fff2ee3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051516"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="f6efc-103">Contoso Corporation 的标识</span><span class="sxs-lookup"><span data-stu-id="f6efc-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="f6efc-104">Microsoft 通过 Azure Active Directory (Azure AD) 在其云产品/服务中提供标识即服务 (IDaaS) 。</span><span class="sxs-lookup"><span data-stu-id="f6efc-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="f6efc-105">若要采用 Microsoft 365 企业版，Contoso IDaaS 解决方案必须使用其本地标识提供程序，并包括具有其现有受信任的第三方标识提供程序的联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="f6efc-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="f6efc-106">Contoso Active Directory 域服务林</span><span class="sxs-lookup"><span data-stu-id="f6efc-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="f6efc-107">Contoso 将单个 Active Directory 域服务 (AD DS) 林用于具有七个子域的 contoso com，每个子域分别用于世界上的一 \. 个子域。</span><span class="sxs-lookup"><span data-stu-id="f6efc-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="f6efc-108">总部、区域中心办事处和分支办事处包含用于本地身份验证和授权的域控制器。</span><span class="sxs-lookup"><span data-stu-id="f6efc-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="f6efc-109">下面是 Contoso 林，其中包含包含区域中心的世界不同区域的区域域。</span><span class="sxs-lookup"><span data-stu-id="f6efc-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![全球的 Contoso 林和域](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="f6efc-111">Contoso 决定使用 contoso com 林中的帐户和组来验证和授权 \. 其 Microsoft 365 工作负载和服务。</span><span class="sxs-lookup"><span data-stu-id="f6efc-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="f6efc-112">Contoso 联合身份验证基础结构</span><span class="sxs-lookup"><span data-stu-id="f6efc-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="f6efc-113">Contoso 允许：</span><span class="sxs-lookup"><span data-stu-id="f6efc-113">Contoso allows:</span></span>

- <span data-ttu-id="f6efc-114">客户使用其 Microsoft、Facebook 或 Google Mail 帐户登录到公司的公共网站。</span><span class="sxs-lookup"><span data-stu-id="f6efc-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="f6efc-115">供应商和合作伙伴使用其 LinkedIn、Salesforce 或 Google Mail 帐户登录到公司的合作伙伴 Extranet。</span><span class="sxs-lookup"><span data-stu-id="f6efc-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="f6efc-116">下面是 Contoso DMZ，其中包含公共网站、合作伙伴 Extranet 和一组 Active Directory 联合身份验证服务 (AD FS) 服务器。</span><span class="sxs-lookup"><span data-stu-id="f6efc-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="f6efc-117">DMZ 连接到包含客户、合作伙伴和 Internet 服务的 Internet。</span><span class="sxs-lookup"><span data-stu-id="f6efc-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![针对客户和合作伙伴的联合身份验证的 Contoso 支持](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="f6efc-119">DMZ 中的 AD FS 服务器便于其标识提供程序验证客户凭据，以便访问公共网站，使用合作伙伴凭据访问合作伙伴 Extranet。</span><span class="sxs-lookup"><span data-stu-id="f6efc-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="f6efc-120">Contoso 决定保留此基础结构，并专用于客户和合作伙伴身份验证。</span><span class="sxs-lookup"><span data-stu-id="f6efc-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="f6efc-121">Contoso 标识架构师正在研究如何将此基础结构转换为 Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) 和 [B2C](/azure/active-directory-b2c/solution-articles) 解决方案。</span><span class="sxs-lookup"><span data-stu-id="f6efc-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) and [B2C](/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="f6efc-122">通过混合标识和密码哈希同步实现基于云的身份验证</span><span class="sxs-lookup"><span data-stu-id="f6efc-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="f6efc-123">Contoso 想要使用其本地 AD DS 林对 Microsoft 365 云资源进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f6efc-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="f6efc-124">它决定在 PHS (密码哈希) 。</span><span class="sxs-lookup"><span data-stu-id="f6efc-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="f6efc-125">PHS 将本地 AD DS 林与 Microsoft 365 企业版订阅的 Azure AD 租户同步，复制用户和组帐户以及哈希版本的用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="f6efc-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="f6efc-126">为执行目录同步，Contoso 在其巴黎数据中心的服务器上部署了 Azure AD Connect 工具。</span><span class="sxs-lookup"><span data-stu-id="f6efc-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="f6efc-127">下面是运行 Azure AD Connect 的服务器，该服务器轮询 Contoso AD DS 林中的更改，然后将这些更改与 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="f6efc-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso PHS 目录同步基础结构](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="f6efc-129">针对标识和设备访问的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="f6efc-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="f6efc-130">Contoso 为以下三种保护级别创建了一组 Azure AD 和 Intune [条件访问策略](../security/defender-365-security/identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="f6efc-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](../security/defender-365-security/identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="f6efc-131">*基线* 保护适用于所有用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f6efc-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="f6efc-132">*敏感* 保护适用于高层领导和管理人员。</span><span class="sxs-lookup"><span data-stu-id="f6efc-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="f6efc-133">*高度管控* 保护适用于金融、法律和研究部门中有权访问高度管控数据的特定用户。</span><span class="sxs-lookup"><span data-stu-id="f6efc-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="f6efc-134">下面是生成的 Contoso 标识和设备条件访问策略集。</span><span class="sxs-lookup"><span data-stu-id="f6efc-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Contoso 的标识和设备条件访问策略](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="f6efc-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f6efc-136">Next step</span></span>

<span data-ttu-id="f6efc-137">了解 Contoso 如何使用其 Microsoft Endpoint Configuration Manager 基础结构在整个组织中部署和保持最新的 [Windows 10](contoso-win10.md) 企业版。</span><span class="sxs-lookup"><span data-stu-id="f6efc-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6efc-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6efc-138">See also</span></span>

[<span data-ttu-id="f6efc-139">Microsoft 365 的识别指南</span><span class="sxs-lookup"><span data-stu-id="f6efc-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="f6efc-140">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="f6efc-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f6efc-141">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="f6efc-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)