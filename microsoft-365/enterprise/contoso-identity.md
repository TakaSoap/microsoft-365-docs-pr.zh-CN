---
title: Contoso Corporation 的标识
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何利用标识即服务 (IDaaS)，并为其员工提供基于云的身份验证以及为其合作伙伴和客户提供联合身份验证。
ms.openlocfilehash: 7571aa455cac4da9e56d7d2001ae4421c3769c94
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865868"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="10c87-103">Contoso Corporation 的标识</span><span class="sxs-lookup"><span data-stu-id="10c87-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="10c87-104">**摘要：** Contoso 如何利用标识即服务 (IDaaS)，并为其员工提供基于云的身份验证以及为其合作伙伴和客户提供联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="10c87-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="10c87-p101">Microsoft 在其云产品中通过 Azure Active Directory (AD) 提供标识即服务 (IDaaS)。为了采用 Microsoft 365 企业版，Contoso 的 IDaaS 解决方案必须利用其本地标识提供程序，并仍然包括其现有受信任的第三方标识提供程序提供的联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="10c87-p101">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (AD). To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-windows-server-ad-forest"></a><span data-ttu-id="10c87-107">Contoso 的 Windows Server AD 林</span><span class="sxs-lookup"><span data-stu-id="10c87-107">Contoso's Windows Server AD forest</span></span>

<span data-ttu-id="10c87-p102">Contoso 将单个 Windows Server Active Directory (AD) 林用于具有七个子域的 contoso.com，每个子域代表全球的一个区域。总部、区域中心办事处和分支办事处包含用于本地身份验证和授权的域控制器。</span><span class="sxs-lookup"><span data-stu-id="10c87-p102">Contoso uses a single Windows Server Active Directory (AD) forest for contoso.com with seven sub-domains, one for each region of the world. The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="10c87-110">图 1 显示 Contoso 林和包含区域中心的全球各个区域的区域性域。</span><span class="sxs-lookup"><span data-stu-id="10c87-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="10c87-111">**图 1：全球的 Contoso 林和域**</span><span class="sxs-lookup"><span data-stu-id="10c87-111">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="10c87-112">Contoso 想要在 contoso.com 林中使用帐户和组来对其基于云的应用和工作负载进行身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="10c87-112">Contoso wants to use the accounts and groups in the contoso.com forest for authentication and authorization for its cloud-based apps and workloads.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="10c87-113">Contoso 的联合身份验证基础结构</span><span class="sxs-lookup"><span data-stu-id="10c87-113">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="10c87-114">Contoso 允许：</span><span class="sxs-lookup"><span data-stu-id="10c87-114">Contoso allows:</span></span>

- <span data-ttu-id="10c87-115">客户使用 Microsoft、Facebook 或 Google Mail 帐户登录其公共网站。</span><span class="sxs-lookup"><span data-stu-id="10c87-115">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="10c87-116">供应商和合作伙伴使用他们的领英、Salesforce 或 Google Mail 帐户登录合作伙伴 Extranet。</span><span class="sxs-lookup"><span data-stu-id="10c87-116">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="10c87-p103">图 2 显示包含一个公共网站、一个合作伙伴 Extranet 和一组 Active Directory 联合身份验证服务 (AD FS) 服务器的 Contoso DMZ。DMZ 已连接至包含客户、合作伙伴和 Internet 服务的 Internet。</span><span class="sxs-lookup"><span data-stu-id="10c87-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="10c87-119">**图 2：Contoso 对客户和合作伙伴的联合身份验证支持**</span><span class="sxs-lookup"><span data-stu-id="10c87-119">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="10c87-120">DMZ 中的 AD FS 服务器会对用以访问公共网站的客户凭据进行身份验证，并对用以访问合作伙伴 Extranet 的合作伙伴凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="10c87-120">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="10c87-p104">Contoso 决定保留此基础结构，并将其用于客户和合作伙伴身份验证。Contoso 标识工程师正在调查如何将此基础结构转换为 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 和 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 解决方案。</span><span class="sxs-lookup"><span data-stu-id="10c87-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-pass-through-authentication-for-cloud-based-authentication"></a><span data-ttu-id="10c87-123">通过混合标识和传递身份验证实现基于云的身份验证</span><span class="sxs-lookup"><span data-stu-id="10c87-123">Hybrid identity with pass-through authentication for cloud-based authentication</span></span>

<span data-ttu-id="10c87-p105">Contoso 想要利用其本地 Windows Server AD 林来进行针对 Microsoft 365 云资源的身份验证。它决定采用具有密码哈希同步 (PHS) 的传递身份验证 (PTA)。</span><span class="sxs-lookup"><span data-stu-id="10c87-p105">Contoso wanted to leverage its on-premises Windows Server AD forest for authentication to Microsoft 365 cloud resources. It decided on pass-through authentication (PTA) with password hash synchronization (PHS).</span></span>

### <a name="pta-authentication"></a><span data-ttu-id="10c87-126">PTA 身份验证</span><span class="sxs-lookup"><span data-stu-id="10c87-126">PTA authentication</span></span>

<span data-ttu-id="10c87-p106">Contoso 将使用 PTA 来对用户凭据进行身份验证。当 Contoso 用户访问基于云的资源时，Azure AD 会将他们发送的凭据传递到 Contoso 总部数据中心中运行身份验证代理的服务器上。其中一个身份验证代理服务器会代表 Azure AD 验证用户凭据。</span><span class="sxs-lookup"><span data-stu-id="10c87-p106">For authentication of user credentials, Contoso is using PTA. When a Contoso user accesses a cloud-based resources, the credentials it sends are passed by Azure AD to a server running an Authentication Agent in the Contoso headquarters datacenter. One of these Authentication Agent servers validates the user credentials on behalf of Azure AD.</span></span>

<span data-ttu-id="10c87-130">图 3 显示 Contoso 总部中一组运行身份验证代理的服务器，这些服务器会处理 Azure AD 传递给它们的身份验证请求。</span><span class="sxs-lookup"><span data-stu-id="10c87-130">Figure 3 shows a set of servers in the Contoso headquarters running the Authentication Agent, which process authentication requests passed to it from Azure AD.</span></span> 

![](./media/contoso-identity/contoso-identity-fig3.png)
 
<span data-ttu-id="10c87-131">**图 3：Contoso 的传递身份验证基础结构**</span><span class="sxs-lookup"><span data-stu-id="10c87-131">**Figure 3: Contoso's pass-through authentication infrastructure**</span></span>

<span data-ttu-id="10c87-132">Contoso 选择使用 PTA 来满足其安全要求，即在评估任何身份验证尝试后迅速改变用户帐户状态、密码策略和在本地 Windows Server AD 林上的登录时间。</span><span class="sxs-lookup"><span data-stu-id="10c87-132">Contoso chose PTA to fulfill its security requirement that all authentication attempts be evaluated for immediate changes to user account states, password policies, and sign-in hours made to the on-premises Windows Server AD forest.</span></span>

### <a name="phs"></a><span data-ttu-id="10c87-133">PHS</span><span class="sxs-lookup"><span data-stu-id="10c87-133">PHS</span></span>

<span data-ttu-id="10c87-p107">PHS 将本地 Windows Server AD 林与 Microsoft 365 企业版订阅的 Azure AD 租户同步，同时复制用户和组帐户以及哈希版用户帐户密码。Contoso 已决定采用 PHS，从而在 PTA 不可用时提供直接向 Azure AD 租户验证的替代身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="10c87-p107">PHS synchronizes the on-premises Windows Server AD forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords. Contoso decided on PHS to provide an alternate method of authentication directly with the Azure AD tenant in the event that PTA is not available.</span></span>

<span data-ttu-id="10c87-p108">为了执行持续目录同步，Contoso 在其巴黎数据中心的服务器上部署了 Azure AD Connect 工具。图 4 显示运行 Azure AD Connect 的服务器，该服务器会轮询 Contoso Windows Server AD 林来查找更改，然后将这些更改与 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="10c87-p108">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="10c87-138">**图 4：Contoso 的 PHS 目录同步基础结构**</span><span class="sxs-lookup"><span data-stu-id="10c87-138">**Figure 4: Contoso's PHS directory synchronization infrastructure**</span></span>

## <a name="conditional-access-policies-for-identity"></a><span data-ttu-id="10c87-139">针对标识的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="10c87-139">Conditional access policies for identity</span></span>

<span data-ttu-id="10c87-140">Contoso 创建了一组 Azure AD [条件访问策略](identity-access-policies.md)，以确保在 Azure AD 确定某个身份验证请求存在登录风险时强制实施多重身份验证和密码更改。</span><span class="sxs-lookup"><span data-stu-id="10c87-140">Contoso created a set of Azure AD [conditional access policies](identity-access-policies.md) to ensure that multi-factor authentication and password changes are enforced when Azure AD determines there is sign-in risk for an authentication request.</span></span>

<span data-ttu-id="10c87-141">图 5 显示他们最终得到的一组针对标识的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="10c87-141">Figure 5 shows their resulting set of conditional access policies for identity.</span></span>

![](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="10c87-142">**图 5：Contoso 的基于标识的条件访问策略**</span><span class="sxs-lookup"><span data-stu-id="10c87-142">**Figure 5: Contoso’s identity-based conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="10c87-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="10c87-143">Next step</span></span>

<span data-ttu-id="10c87-144">[了解](contoso-win10.md) Contoso 如何利用其 System Center Configuration Manager 基础结构在组织中部署 Windows 10 企业版并使之保持最新。</span><span class="sxs-lookup"><span data-stu-id="10c87-144">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="10c87-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10c87-145">See also</span></span>

[<span data-ttu-id="10c87-146">Microsoft 365 企业版的标识</span><span class="sxs-lookup"><span data-stu-id="10c87-146">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="10c87-147">部署指南</span><span class="sxs-lookup"><span data-stu-id="10c87-147">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="10c87-148">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="10c87-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
