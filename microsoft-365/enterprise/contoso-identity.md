---
title: Contoso Corporation 的标识
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何利用标识即服务 (IDaaS)，并为其员工提供基于云的身份验证以及为其合作伙伴和客户提供联合身份验证。
ms.openlocfilehash: a61ce89c3d0069edffccc12a6ed2a4c578e6968a
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370249"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="9a6cc-103">Contoso Corporation 的标识</span><span class="sxs-lookup"><span data-stu-id="9a6cc-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="9a6cc-104">**摘要：** Contoso 如何利用标识即服务 (IDaaS)，并为其员工提供基于云的身份验证以及为其合作伙伴和客户提供联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="9a6cc-105">Microsoft 通过 Azure Active Directory (Azure AD). 在其云产品中提供标识即服务 (IDaaS)。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-105">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="9a6cc-106">若要采用 Microsoft 365 企业版，Contoso 的 IDaaS 解决方案必须利用其本地标识提供程序，并且仍包括其现有受信任的第三方标识提供程序提供的联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-106">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="9a6cc-107">Contoso 的 Active Directory 域服务林</span><span class="sxs-lookup"><span data-stu-id="9a6cc-107">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="9a6cc-108">Contoso 借助七个子域将单个 Active Directory 域服务 (AD DS) 林用于 contoso.com，每个域对应世界上的一个地区。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-108">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="9a6cc-109">总部、区域中心办事处和分支办事处包含用于本地身份验证和授权的域控制器。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-109">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="9a6cc-110">这是 Contoso 林和包含区域中心的全球各个区域的区域性域。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![全球的 Contoso 林和域](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="9a6cc-112">Contoso 想要在 contoso.com 林中使用帐户和组来对其 Microsoft 365 工作负载和服务进行身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-112">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="9a6cc-113">Contoso 的联合身份验证基础结构</span><span class="sxs-lookup"><span data-stu-id="9a6cc-113">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="9a6cc-114">Contoso 允许：</span><span class="sxs-lookup"><span data-stu-id="9a6cc-114">Contoso allows:</span></span>

- <span data-ttu-id="9a6cc-115">客户使用 Microsoft、Facebook 或 Google Mail 帐户登录其公共网站。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-115">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="9a6cc-116">供应商和合作伙伴使用他们的领英、Salesforce 或 Google Mail 帐户登录合作伙伴 Extranet。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-116">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="9a6cc-117">这是包含一个公共网站、一个合作伙伴 Extranet 和一组 Active Directory 联合身份验证服务 (AD FS) 服务器的 Contoso DMZ。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-117">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span> <span data-ttu-id="9a6cc-118">DMZ 已连接至包含客户、合作伙伴和 Internet 服务的 Internet。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-118">The DMZ is connected to the Internet that contains customers and partners and Internet services.</span></span>

![Contoso 对客户和合作伙伴的联合身份验证支持](./media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="9a6cc-120">DMZ 中的 AD FS 服务器可加快由标识提供程序对客户凭据进行身份验证以访问公共网站，并对合作伙伴凭据进行身份验证以访问合作伙伴 Extranet。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-120">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="9a6cc-121">Contoso 决定保留此基础结构，并将其专用于客户和合作伙伴的身份验证。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-121">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications.</span></span> <span data-ttu-id="9a6cc-122">Contoso 标识架构师正在研究如何将此基础结构转换为 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 和 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 解决方案。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-122">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="9a6cc-123">通过混合标识和密码哈希同步实现基于云的身份验证</span><span class="sxs-lookup"><span data-stu-id="9a6cc-123">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="9a6cc-124">Contoso 想要利用其本地 AD DS 林来进行针对 Microsoft 365 云资源的身份验证。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-124">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="9a6cc-125">它决定密码哈希同步 (PHS)。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-125">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="9a6cc-126">PHS 将本地 AD DS 林与 Microsoft 365 企业版订阅的 Azure AD 租户同步，同时复制用户和组帐户以及哈希版用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-126">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="9a6cc-127">为了执行持续目录同步，Contoso 在其巴黎数据中心的服务器上部署了 Azure AD Connect 工具。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-127">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="9a6cc-128">这是运行 Azure AD Connect 的服务器，该服务器会轮询 Contoso AD DS 林来查找更改，然后将这些更改与 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-128">Figure 3 shows the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso 的 PHS 目录同步基础结构](./media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="9a6cc-130">针对标识和设备访问的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="9a6cc-130">Conditional access policies for identity and device access</span></span>

<span data-ttu-id="9a6cc-131">Contoso 为以下三种保护级别创建了一组 Azure AD 和 Intune [条件访问策略](identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="9a6cc-131">Contoso created a set of Azure AD and Intune [conditional access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="9a6cc-132">**基准**保护适用于所有用户帐户</span><span class="sxs-lookup"><span data-stu-id="9a6cc-132">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="9a6cc-133">**敏感**保护适用于高层领导和管理人员</span><span class="sxs-lookup"><span data-stu-id="9a6cc-133">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="9a6cc-134">**高度管控**保护适用于具有高度管控数据访问权限的财务、法务和研究部门的特定用户</span><span class="sxs-lookup"><span data-stu-id="9a6cc-134">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="9a6cc-135">这是 Contoso 最终得到的一组标识和设备条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-135">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Contoso 的标识和设备条件访问策略](./media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="9a6cc-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9a6cc-137">Next step</span></span>

<span data-ttu-id="9a6cc-138">[了解](contoso-win10.md) Contoso 如何利用其 System Center Configuration Manager 基础结构在组织中部署 Windows 10 企业版并使之保持最新。</span><span class="sxs-lookup"><span data-stu-id="9a6cc-138">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a6cc-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a6cc-139">See also</span></span>

[<span data-ttu-id="9a6cc-140">Microsoft 365 企业版的标识</span><span class="sxs-lookup"><span data-stu-id="9a6cc-140">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="9a6cc-141">部署指南</span><span class="sxs-lookup"><span data-stu-id="9a6cc-141">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9a6cc-142">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="9a6cc-142">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
