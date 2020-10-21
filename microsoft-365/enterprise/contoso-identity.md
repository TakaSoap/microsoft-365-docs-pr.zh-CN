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
ms.openlocfilehash: 10db0a35024595c4dba9a33ad83ae75bcad3870c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637243"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="c2c30-103">Contoso Corporation 的标识</span><span class="sxs-lookup"><span data-stu-id="c2c30-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="c2c30-104">Microsoft 通过 Azure Active Directory (Azure AD) 将标识作为服务 (IDaaS) 通过其云产品提供。</span><span class="sxs-lookup"><span data-stu-id="c2c30-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="c2c30-105">若要采用 Microsoft 365 for enterprise，Contoso IDaaS 解决方案必须使用其内部部署标识提供程序，并将联合身份验证包括在其现有的受信任的第三方标识提供程序中。</span><span class="sxs-lookup"><span data-stu-id="c2c30-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="c2c30-106">Contoso Active Directory 域服务林</span><span class="sxs-lookup"><span data-stu-id="c2c30-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="c2c30-107">Contoso 使用单个 Active Directory 域服务 (AD DS) 林，为 contoso \. com 提供七个子域，每个区域适用于世界的每个区域一个。</span><span class="sxs-lookup"><span data-stu-id="c2c30-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="c2c30-108">总部、区域中心办事处和分支办事处包含用于本地身份验证和授权的域控制器。</span><span class="sxs-lookup"><span data-stu-id="c2c30-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="c2c30-109">以下是包含区域中心的全球不同部分的带有地区性域的 Contoso 林。</span><span class="sxs-lookup"><span data-stu-id="c2c30-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![全球的 Contoso 林和域](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="c2c30-111">Contoso 决定使用 contoso com 林中的帐户和组 \. 进行身份验证，并授权其 Microsoft 365 工作负载和服务。</span><span class="sxs-lookup"><span data-stu-id="c2c30-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="c2c30-112">Contoso 联合身份验证基础结构</span><span class="sxs-lookup"><span data-stu-id="c2c30-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="c2c30-113">Contoso 允许：</span><span class="sxs-lookup"><span data-stu-id="c2c30-113">Contoso allows:</span></span>

- <span data-ttu-id="c2c30-114">客户使用其 Microsoft、Facebook 或 Google 邮件帐户登录到公司的公共网站。</span><span class="sxs-lookup"><span data-stu-id="c2c30-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="c2c30-115">供应商和合作伙伴使用其 LinkedIn、Salesforce 或 Google Mail 帐户登录到公司的合作伙伴 extranet。</span><span class="sxs-lookup"><span data-stu-id="c2c30-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="c2c30-116">以下是包含公共网站、合作伙伴 extranet 和一组 AD FS 服务器的 Contoso DMZ。</span><span class="sxs-lookup"><span data-stu-id="c2c30-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of AD FS servers.</span></span> <span data-ttu-id="c2c30-117">DMZ 连接到包含客户、合作伙伴和 internet 服务的 internet。</span><span class="sxs-lookup"><span data-stu-id="c2c30-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Contoso 支持客户和合作伙伴的联合身份验证](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="c2c30-119">DMZ 中的 AD FS 服务器通过其标识提供商访问公用网站的身份验证和合作伙伴凭据，从而简化了客户凭据的身份验证，以访问合作伙伴 extranet。</span><span class="sxs-lookup"><span data-stu-id="c2c30-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="c2c30-120">Contoso 决定保留此基础结构并将其专用于客户和合作伙伴身份验证。</span><span class="sxs-lookup"><span data-stu-id="c2c30-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="c2c30-121">Contoso 标识架构师正在研究如何将此基础结构转换为 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 和 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 解决方案。</span><span class="sxs-lookup"><span data-stu-id="c2c30-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="c2c30-122">通过混合标识和密码哈希同步实现基于云的身份验证</span><span class="sxs-lookup"><span data-stu-id="c2c30-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="c2c30-123">Contoso 想要使用其内部部署 AD DS 林进行身份验证，以进行 Microsoft 365 云资源的身份验证。</span><span class="sxs-lookup"><span data-stu-id="c2c30-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="c2c30-124">它决定使用密码哈希同步 (PHS) 。</span><span class="sxs-lookup"><span data-stu-id="c2c30-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="c2c30-125">PHS 将本地 AD DS 林与 Microsoft 365 for enterprise 订阅的 Azure AD 租户同步，复制用户和组帐户以及用户帐户密码的哈希版本。</span><span class="sxs-lookup"><span data-stu-id="c2c30-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="c2c30-126">为了执行目录同步，Contoso 在巴黎 datacenter 中的服务器上部署了 Azure AD Connect 工具。</span><span class="sxs-lookup"><span data-stu-id="c2c30-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="c2c30-127">以下是运行 Azure AD 的服务器连接轮询 Contoso AD DS 林以进行更改，然后将这些更改与 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="c2c30-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Contoso PHS 目录同步基础结构](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="c2c30-129">针对标识和设备访问的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="c2c30-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="c2c30-130">Contoso 为以下三种保护级别创建了一组 Azure AD 和 Intune [条件访问策略](identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="c2c30-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="c2c30-131">*基准* 保护适用于所有用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c2c30-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="c2c30-132">*敏感* 保护适用于高级领导和执行人员。</span><span class="sxs-lookup"><span data-stu-id="c2c30-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="c2c30-133">*高度管控* 保护适用于财务、法律和研究部门中有权访问高度管控数据的特定用户。</span><span class="sxs-lookup"><span data-stu-id="c2c30-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="c2c30-134">以下是 Contoso identity and device 条件访问策略的结果集。</span><span class="sxs-lookup"><span data-stu-id="c2c30-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Contoso 的标识和设备条件访问策略](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="c2c30-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c2c30-136">Next step</span></span>

<span data-ttu-id="c2c30-137">[了解](contoso-win10.md) Contoso 如何使用其 Microsoft 终结点配置管理器基础结构在其整个组织中部署和保留当前的 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="c2c30-137">[Learn](contoso-win10.md) how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2c30-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2c30-138">See also</span></span>

[<span data-ttu-id="c2c30-139">Microsoft 365 的识别指南</span><span class="sxs-lookup"><span data-stu-id="c2c30-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="c2c30-140">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="c2c30-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c2c30-141">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="c2c30-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
