---
title: Contoso Corporation 的标识
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何利用标识即服务 (IDaaS)，并为其员工提供基于云的身份验证以及为其合作伙伴和客户提供联合身份验证。
ms.openlocfilehash: 795fb7dcb886c792c80d3bb251c9cb5774f1bf97
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686030"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="7c639-103">Contoso Corporation 的标识</span><span class="sxs-lookup"><span data-stu-id="7c639-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="7c639-104">Microsoft 通过 Azure Active Directory (Azure AD). 在其云产品中提供标识即服务 (IDaaS)。</span><span class="sxs-lookup"><span data-stu-id="7c639-104">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="7c639-105">若要采用 Microsoft 365 for enterprise，Contoso 的 IDaaS 解决方案必须利用其本地标识提供程序，并且仍包括与其现有的受信任的第三方标识提供程序的联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="7c639-105">To adopt Microsoft 365 for enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="7c639-106">Contoso 的 Active Directory 域服务林</span><span class="sxs-lookup"><span data-stu-id="7c639-106">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="7c639-107">Contoso 借助七个子域将单个 Active Directory 域服务 (AD DS) 林用于 contoso.com，每个域对应世界上的一个地区。</span><span class="sxs-lookup"><span data-stu-id="7c639-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="7c639-108">总部、区域中心办事处和分支办事处包含用于本地身份验证和授权的域控制器。</span><span class="sxs-lookup"><span data-stu-id="7c639-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="7c639-109">这是 Contoso 林和包含区域中心的全球各个区域的区域性域。</span><span class="sxs-lookup"><span data-stu-id="7c639-109">Here is the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![全球的 Contoso 林和域](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="7c639-111">Contoso 想要在 contoso.com 林中使用帐户和组来对其 Microsoft 365 工作负载和服务进行身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="7c639-111">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="7c639-112">Contoso 的联合身份验证基础结构</span><span class="sxs-lookup"><span data-stu-id="7c639-112">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="7c639-113">Contoso 允许：</span><span class="sxs-lookup"><span data-stu-id="7c639-113">Contoso allows:</span></span>

- <span data-ttu-id="7c639-114">客户使用 Microsoft、Facebook 或 Google Mail 帐户登录其公共网站。</span><span class="sxs-lookup"><span data-stu-id="7c639-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="7c639-115">供应商和合作伙伴使用他们的领英、Salesforce 或 Google Mail 帐户登录合作伙伴 Extranet。</span><span class="sxs-lookup"><span data-stu-id="7c639-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="7c639-116">这是包含一个公共网站、一个合作伙伴 Extranet 和一组 Active Directory 联合身份验证服务 (AD FS) 服务器的 Contoso DMZ。</span><span class="sxs-lookup"><span data-stu-id="7c639-116">Here is the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="7c639-117">DMZ 已连接至包含客户、合作伙伴和 Internet 服务的 Internet。</span><span class="sxs-lookup"><span data-stu-id="7c639-117">The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Contoso 对客户和合作伙伴的联合身份验证支持](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="7c639-119">DMZ 中的 AD FS 服务器可加快由标识提供程序对客户凭据进行身份验证以访问公共网站，并对合作伙伴凭据进行身份验证以访问合作伙伴 Extranet。</span><span class="sxs-lookup"><span data-stu-id="7c639-119">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="7c639-120">Contoso 决定保留此基础结构，并将其专用于客户和合作伙伴的身份验证。</span><span class="sxs-lookup"><span data-stu-id="7c639-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications.</span></span> <span data-ttu-id="7c639-121">Contoso 标识架构师正在研究如何将此基础结构转换为 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 和 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 解决方案。</span><span class="sxs-lookup"><span data-stu-id="7c639-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="7c639-122">通过混合标识和密码哈希同步实现基于云的身份验证</span><span class="sxs-lookup"><span data-stu-id="7c639-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="7c639-123">Contoso 想要利用其本地 AD DS 林来进行针对 Microsoft 365 云资源的身份验证。</span><span class="sxs-lookup"><span data-stu-id="7c639-123">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="7c639-124">它决定密码哈希同步 (PHS)。</span><span class="sxs-lookup"><span data-stu-id="7c639-124">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="7c639-125">PHS 将本地 AD DS 林与 Microsoft 365 for enterprise 订阅的 Azure AD 租户同步，复制用户和组帐户以及用户帐户密码的哈希版本。</span><span class="sxs-lookup"><span data-stu-id="7c639-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="7c639-126">为了执行持续目录同步，Contoso 在其巴黎数据中心的服务器上部署了 Azure AD Connect 工具。</span><span class="sxs-lookup"><span data-stu-id="7c639-126">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="7c639-127">这是运行 Azure AD Connect 的服务器，该服务器会轮询 Contoso AD DS 林来查找更改，然后将这些更改与 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="7c639-127">Here is the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso 的 PHS 目录同步基础结构](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="7c639-129">针对标识和设备访问的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="7c639-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="7c639-130">Contoso 为以下三种保护级别创建了一组 Azure AD 和 Intune [条件访问策略](identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="7c639-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="7c639-131">**基准**保护适用于所有用户帐户</span><span class="sxs-lookup"><span data-stu-id="7c639-131">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="7c639-132">**敏感**保护适用于高层领导和管理人员</span><span class="sxs-lookup"><span data-stu-id="7c639-132">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="7c639-133">**高度管控**保护适用于具有高度管控数据访问权限的财务、法务和研究部门的特定用户</span><span class="sxs-lookup"><span data-stu-id="7c639-133">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="7c639-134">这是 Contoso 最终得到的一组标识和设备条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="7c639-134">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Contoso 的标识和设备条件访问策略](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="7c639-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7c639-136">Next step</span></span>

<span data-ttu-id="7c639-137">[了解](contoso-win10.md) Contoso 如何利用其 Microsoft Endpoint Configuration Manager 基础结构在组织中部署 Windows 10 企业版并使之保持最新。</span><span class="sxs-lookup"><span data-stu-id="7c639-137">[Learn](contoso-win10.md) how Contoso is leveraging its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c639-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c639-138">See also</span></span>

[<span data-ttu-id="7c639-139">Microsoft 365 的身份路线图</span><span class="sxs-lookup"><span data-stu-id="7c639-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="7c639-140">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="7c639-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7c639-141">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="7c639-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
