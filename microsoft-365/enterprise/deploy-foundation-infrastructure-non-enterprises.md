---
title: 适用于非企业组织的 Microsoft 365 企业版基础结构
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 逐步完成适用于非企业组织的 Microsoft 365 企业版基础结构的简化部署阶段。
ms.openlocfilehash: 4006980de5341c53d9c6a2d827613015c000fab0
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369573"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-for-non-enterprises"></a><span data-ttu-id="a69e1-103">适用于非企业组织的 Microsoft 365 企业版基础结构</span><span class="sxs-lookup"><span data-stu-id="a69e1-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="a69e1-104">非企业组织也可以部署 Microsoft 365 企业版，并实现集成式安全基础结构的业务价值，从而实现团队协作并激发创造力。</span><span class="sxs-lookup"><span data-stu-id="a69e1-104">Non-enterprise organizations can also deploy Microsoft 365 Enterprise and realize the business value of an integrated and secure infrastructure that enables teamwork and unlocks creativity.</span></span> <span data-ttu-id="a69e1-105">非企业组织通常具有：</span><span class="sxs-lookup"><span data-stu-id="a69e1-105">A non-enterprise typically has:</span></span>

- <span data-ttu-id="a69e1-106">少量的本地 IT 基础结构，例如电子邮件和文件服务器以及 Active Directory 域服务 (AD DS) 域，或者根本不存在。</span><span class="sxs-lookup"><span data-stu-id="a69e1-106">A small amount of on-premises IT infrastructure, such as email and file servers and an Active Directory Domain Services (AD DS) domain, or none at all.</span></span>
- <span data-ttu-id="a69e1-107">少量的 IT 人员，其中大多数是 IT 通才，而不是特定技术或工作负载（如网络或电子邮件）领域的专家。</span><span class="sxs-lookup"><span data-stu-id="a69e1-107">A small IT staff, most of whom are IT generalists, rather than specialists in a specific technology or workload such as networking or email.</span></span>

<span data-ttu-id="a69e1-108">Microsoft 为小型非企业组织提供了 [Microsoft 365 商业版](https://www.microsoft.com/microsoft-365/business)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-108">For smaller, non-enterprise organizations, Microsoft offers [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="a69e1-109">但是，出于某些原因你可能需要使用 Microsoft 365 企业版，例如：</span><span class="sxs-lookup"><span data-stu-id="a69e1-109">However, there are reasons why you might need Microsoft 365 Enterprise, such as:</span></span>

- <span data-ttu-id="a69e1-110">你的组织需要超过 300 个 Microsoft 365 许可证，而 Microsoft 365 商业版的最大许可证数量为 300 个。</span><span class="sxs-lookup"><span data-stu-id="a69e1-110">Your organization needs more or will need more than 300 Microsoft 365 licenses, which is the maximum for Microsoft 365 Business.</span></span>
- <span data-ttu-id="a69e1-111">你的组织需要高级生产力、语音、安全性和分析功能，这些功能是 Microsoft 365 商业版所不具备的。</span><span class="sxs-lookup"><span data-stu-id="a69e1-111">Your organization needs the advanced productivity, voice, security, and analytics capabilities that are not available with Microsoft 365 Business.</span></span>

<span data-ttu-id="a69e1-112">本文将指导你完成适用于非企业组织的 Microsoft 365 企业版基础结构的简化部署。</span><span class="sxs-lookup"><span data-stu-id="a69e1-112">This article steps you through a simplified deployment of the foundation infrastructure of Microsoft 365 Enterprise suitable for your non-enterprise.</span></span>

## <a name="first-set-up-your-subscription"></a><span data-ttu-id="a69e1-113">首先，设置你的订阅</span><span class="sxs-lookup"><span data-stu-id="a69e1-113">First, set up your subscription</span></span>

<span data-ttu-id="a69e1-114">你必须为订阅设置域名系统 (DNS) 域。</span><span class="sxs-lookup"><span data-stu-id="a69e1-114">You must set up the Domain Name System (DNS) domains for your subscription.</span></span> <span data-ttu-id="a69e1-115">如果你已经拥有 Office 365 订阅，则应该已完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="a69e1-115">If you already have an Office 365 subscription, this should have been done.</span></span> <span data-ttu-id="a69e1-116">如果没有，请按照[将域添加到 Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide) 中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="a69e1-116">If not, follow the instructions in [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span></span>

<span data-ttu-id="a69e1-117">接下来，你需要为 Microsoft 365 配置其他安全性。</span><span class="sxs-lookup"><span data-stu-id="a69e1-117">Next, you need to configure additional security for Microsoft 365.</span></span> <span data-ttu-id="a69e1-118">请按照[配置增强的安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="a69e1-118">Follow the instructions in [Configure increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

## <a name="phase-1-networking"></a><span data-ttu-id="a69e1-119">阶段 1：网络</span><span class="sxs-lookup"><span data-stu-id="a69e1-119">Phase 1: Networking</span></span>

<span data-ttu-id="a69e1-120">非企业组织通常在每个办公室都建立了本地 Internet 连接，并且未使用代理服务器、防火墙或数据包检查设备。</span><span class="sxs-lookup"><span data-stu-id="a69e1-120">Non-enterprise organizations typically have local Internet connections in each office and do not use proxy servers, firewalls, or packet inspection devices.</span></span> <span data-ttu-id="a69e1-121">为每个办公室服务的 Internet 服务提供商 (ISP) 都有一个区域性的本地 DNS 服务器，用于将流量定向到离你的办公室和本地用户最近的 Microsoft 365 网络位置。</span><span class="sxs-lookup"><span data-stu-id="a69e1-121">The Internet service provider (ISP) serving each office has a regionally local DNS server so that traffic is directed to the Microsoft 365 network location that is closest to your offices and their on-premises users.</span></span> <span data-ttu-id="a69e1-122">有关详细信息，请参阅[配置每个办公室的本地 Internet 连接](networking-dns-resolution-same-location.md)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-122">For more information, see [Configure local Internet connections for each office](networking-dns-resolution-same-location.md).</span></span>

<span data-ttu-id="a69e1-123">因此，你只需要与 ISP 确认每个办公地点的连接：</span><span class="sxs-lookup"><span data-stu-id="a69e1-123">Therefore, you only need to verify with your ISP that the connection at each of your office locations:</span></span>

- <span data-ttu-id="a69e1-124">使用区域性的本地 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="a69e1-124">Uses a regionally local DNS server.</span></span>
- <span data-ttu-id="a69e1-125">随着用户开始使用更多的 Microsoft 365 云服务，足以满足当前和未来的需求。</span><span class="sxs-lookup"><span data-stu-id="a69e1-125">Is adequate for current and future needs as your users begin using more Microsoft 365 cloud services.</span></span>

<span data-ttu-id="a69e1-126">如果你使用的是代理服务器、防火墙或数据包检查设备，请参阅[配置流量旁路](networking-configure-proxies-firewalls.md)，以获取有关如何优化 Microsoft 365 服务性能的信息。</span><span class="sxs-lookup"><span data-stu-id="a69e1-126">If you do use proxy servers, firewalls, or packet inspection devices, see [Configure traffic bypass](networking-configure-proxies-firewalls.md) for information on how to optimize performance to Microsoft 365 services.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="a69e1-127">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="a69e1-127">Your configuration so far</span></span>

<span data-ttu-id="a69e1-128">以下是突出显示第 1 阶段元素的可视化摘要。</span><span class="sxs-lookup"><span data-stu-id="a69e1-128">Here is a visual summary with the Phase 1 element highlighted.</span></span> <span data-ttu-id="a69e1-129">**你的组织**可能拥有多个办公室，每个办公室都与使用区域性本地 DNS 服务器的 ISP 建立了本地 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="a69e1-129">**Your organization** can be multiple offices, each of which has a local Internet connection with an ISP that uses a regionally local DNS server.</span></span> <span data-ttu-id="a69e1-130">通过 ISP，每个办公室的用户都可以访问最近的 Microsoft 365 网络位置和 Microsoft 365 订阅的资源。</span><span class="sxs-lookup"><span data-stu-id="a69e1-130">Through the ISP, users in each office can reach the nearest Microsoft 365 network location and the resources of your Microsoft 365 subscription.</span></span>

![“网络”阶段之后的组织](./media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a><span data-ttu-id="a69e1-132">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="a69e1-132">Phase 2: Identity</span></span>

<span data-ttu-id="a69e1-133">组织内的每个员工都必须能够登录，这需要使用 Microsoft 365 企业版订阅的 Azure Active Directory (Azure AD) 租户中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-133">Each employee of your organization must be able to sign in, which requires a user account in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="a69e1-134">然后，组将用于包含用户帐户和其他组以进行通信或访问许可的资源，例如 SharePoint Online 网站或团队。</span><span class="sxs-lookup"><span data-stu-id="a69e1-134">Groups are then used to contain user accounts and other groups to communicate or gain access to permissioned resources, such as a SharePoint Online site or a team.</span></span> 

### <a name="administrator-accounts"></a><span data-ttu-id="a69e1-135">管理员帐户</span><span class="sxs-lookup"><span data-stu-id="a69e1-135">Administrator accounts</span></span>

<span data-ttu-id="a69e1-136">通过要求强密码和多因素身份验证 (MFA) 来保护你的全局管理员用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-136">Protect your global administrator user accounts by requiring strong passwords and multi-factor authentication (MFA).</span></span> <span data-ttu-id="a69e1-137">有关详细信息，请参阅[保护全局管理员帐户](identity-create-protect-global-admins.md#protect-global-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-137">See [Protect your Office 365 global administrator accounts](identity-create-protect-global-admins.md#protect-global-administrator-accounts) for more information about configuration.</span></span>

<span data-ttu-id="a69e1-138">如果贵组织需要高安全性并且你拥有 Microsoft 365 企业版 E5，请使用 Azure AD Privileged Identity Management 来启用实时管理员访问。</span><span class="sxs-lookup"><span data-stu-id="a69e1-138">If your organization requires high security and you have Microsoft 365 Enterprise E5, use Azure AD Privileged Identity Management to enable just-in-time administrator access.</span></span> <span data-ttu-id="a69e1-139">有关详细信息，请参阅[设置按需全局管理员](identity-create-protect-global-admins.md#identity-pim)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-139">See [Set up on-demand global administrators](identity-create-protect-global-admins.md#identity-pim) for more information.</span></span>

### <a name="recommendations-for-groups"></a><span data-ttu-id="a69e1-140">有关组的建议</span><span class="sxs-lookup"><span data-stu-id="a69e1-140">Recommendations for groups</span></span>

<span data-ttu-id="a69e1-141">如果你具有本地 AD DS 域，请继续将 Microsoft 365 企业版中的这些组用作 Azure AD 中的组。</span><span class="sxs-lookup"><span data-stu-id="a69e1-141">If you have an on-premises AD DS domain, continue to use those groups in Microsoft 365 Enterprise as groups in Azure AD.</span></span>

<span data-ttu-id="a69e1-142">如果你没有本地 AD DS 域，请使用这些安全级别在 Azure AD 中创建安全组。</span><span class="sxs-lookup"><span data-stu-id="a69e1-142">If you don’t have an on-premises AD DS domain, create security groups in Azure AD using these levels of security.</span></span>

| <span data-ttu-id="a69e1-143">安全级别</span><span class="sxs-lookup"><span data-stu-id="a69e1-143">Security level</span></span> | <span data-ttu-id="a69e1-144">说明</span><span class="sxs-lookup"><span data-stu-id="a69e1-144">Description</span></span> | <span data-ttu-id="a69e1-145">示例</span><span class="sxs-lookup"><span data-stu-id="a69e1-145">Examples</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="a69e1-146">基线</span><span class="sxs-lookup"><span data-stu-id="a69e1-146">Baseline</span></span> | <span data-ttu-id="a69e1-147">这是保护数据以及访问数据的标识和设备的最低和默认标准。</span><span class="sxs-lookup"><span data-stu-id="a69e1-147">This is a minimum and default  standard for protecting data and the identities and devices that access your data.</span></span> <BR><BR> <span data-ttu-id="a69e1-148">这通常是大多数用户管理的大部分组织数据。</span><span class="sxs-lookup"><span data-stu-id="a69e1-148">This is typically most of your organization’s data managed by most of your users.</span></span> | <span data-ttu-id="a69e1-149">一线员工组，例如销售、营销、支持、管理和制造。</span><span class="sxs-lookup"><span data-stu-id="a69e1-149">Groups for first line workers, such as sales, marketing, support, administration, and manufacturing.</span></span> |
| <span data-ttu-id="a69e1-150">敏感</span><span class="sxs-lookup"><span data-stu-id="a69e1-150">Sensitive</span></span> | <span data-ttu-id="a69e1-151">这是对数据子集的额外保护，这种保护必须超出基线级别。</span><span class="sxs-lookup"><span data-stu-id="a69e1-151">This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="a69e1-152">这些组包含使用和创建敏感数据的用户，这些数据特定于相关部门以及不向所有人公开的项目。</span><span class="sxs-lookup"><span data-stu-id="a69e1-152">These groups contain users that use and create sensitive data that is specific to departments and projects that are not meant to be available to everyone.</span></span> | <span data-ttu-id="a69e1-153">负责开发未来产品的产品或营销团队</span><span class="sxs-lookup"><span data-stu-id="a69e1-153">Product or marketing teams that are developing future products</span></span> |
| <span data-ttu-id="a69e1-154">高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-154">Highly regulated</span></span> | <span data-ttu-id="a69e1-155">这通常是对少量数据的最高级别的保护，这些数据是高度机密、视为知识产权或商业机密或必须遵守安全法规的数据。</span><span class="sxs-lookup"><span data-stu-id="a69e1-155">Highly regulated: This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span> |  <span data-ttu-id="a69e1-156">研发、法律和财务团队，或者负责存储或使用客户或合作伙伴数据的团队。</span><span class="sxs-lookup"><span data-stu-id="a69e1-156">Research, legal, and financial teams, or teams storing or using customer or partner data.</span></span> |
||||

### <a name="hybrid-identity"></a><span data-ttu-id="a69e1-157">混合标识</span><span class="sxs-lookup"><span data-stu-id="a69e1-157">Hybrid identity</span></span>

<span data-ttu-id="a69e1-158">如果你有本地 AD DS 域，则需要将该域的一组用户帐户、组和联系人与 Microsoft 365 企业版订阅的 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="a69e1-158">If you have an on-premises AD DS domain, you need to synchronize the set of user accounts, groups, and contacts of your domain with the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="a69e1-159">对于非企业组织，请在使用密码哈希同步 (PHS) 功能的服务器上配置 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="a69e1-159">For your non-enterprise, you configure Azure AD Connect on a server with password hash synchronization (PHS).</span></span> <span data-ttu-id="a69e1-160">有关详细信息，请参阅[同步标识](identity-add-user-accounts.md#synchronize-identities-for-hybrid-identity)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-160">See [Synchronize identities](identity-add-user-accounts.md#synchronize-identities-for-hybrid-identity) for more information.</span></span>

### <a name="more-secure-user-access-with-conditional-access-policies"></a><span data-ttu-id="a69e1-161">通过条件访问策略实现更安全的用户访问</span><span class="sxs-lookup"><span data-stu-id="a69e1-161">More secure user access with Conditional Access policies</span></span>

<span data-ttu-id="a69e1-162">Azure AD 将会评估用户登录的条件，并且可以使用条件访问策略来授予或拒绝访问权限，并强制执行必须采取的进一步操作以完成登录。</span><span class="sxs-lookup"><span data-stu-id="a69e1-162">Azure AD evaluates the conditions of user sign-ins and can use Conditional Access policies to grant or deny access and impose further actions that must be taken to complete the sign-in.</span></span> <span data-ttu-id="a69e1-163">例如，如果 Azure AD 确定登录是在中或高风险条件下发生的，则可能要求用户执行 MFA 以完成登录。</span><span class="sxs-lookup"><span data-stu-id="a69e1-163">For example, if Azure AD determines that the sign-in is happening under medium or high-risk conditions, it can require the user to perform MFA to complete the sign-in.</span></span>

<span data-ttu-id="a69e1-164">你可以将条件访问策略应用于用户帐户或组。</span><span class="sxs-lookup"><span data-stu-id="a69e1-164">You apply Conditional Access policies to user accounts or groups.</span></span> <span data-ttu-id="a69e1-165">为了便于更轻松地分配条件访问策略，请在组织中创建以下 Azure AD 安全组：</span><span class="sxs-lookup"><span data-stu-id="a69e1-165">To facilitate an easier assignment of Conditional Access policies, create these Azure AD security groups in your organization:</span></span>

- <span data-ttu-id="a69e1-166">基线</span><span class="sxs-lookup"><span data-stu-id="a69e1-166">Baseline</span></span>

  <span data-ttu-id="a69e1-167">包含有权访问基线数据的用户的组或用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-167">Contains the groups or user accounts for users with access to baseline data.</span></span>

- <span data-ttu-id="a69e1-168">敏感</span><span class="sxs-lookup"><span data-stu-id="a69e1-168">Sensitive</span></span>

  <span data-ttu-id="a69e1-169">包含有权访问敏感数据的用户的组或用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-169">Contains the groups or user accounts for users with access to sensitive data.</span></span>

- <span data-ttu-id="a69e1-170">高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-170">HIGHLY-REGULATED</span></span>

  <span data-ttu-id="a69e1-171">包含有权访问高度管控数据的用户的组或用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-171">Contains the groups or user accounts for users with access to highly regulated data.</span></span>

- <span data-ttu-id="a69e1-172">条件-访问-排除</span><span class="sxs-lookup"><span data-stu-id="a69e1-172">COND-ACCESS-EXCLUDE</span></span>

  <span data-ttu-id="a69e1-173">可用于临时从条件访问策略中排除用户的空组。</span><span class="sxs-lookup"><span data-stu-id="a69e1-173">An empty group that you can use to temporarily exclude a user from Conditional Access policies.</span></span>

<span data-ttu-id="a69e1-174">以下是要启用或创建的 Azure AD 条件访问策略的列表。</span><span class="sxs-lookup"><span data-stu-id="a69e1-174">Here is the list of Azure AD Conditional Access policies to enable or create.</span></span>

| <span data-ttu-id="a69e1-175">Azure AD 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="a69e1-175">Azure AD Conditional Access policy</span></span> | <span data-ttu-id="a69e1-176">应用到的组</span><span class="sxs-lookup"><span data-stu-id="a69e1-176">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="a69e1-177">基线策略：要求管理员执行 MFA</span><span class="sxs-lookup"><span data-stu-id="a69e1-177">Baseline policy: Require MFA for admins</span></span> | <span data-ttu-id="a69e1-178">此策略适用于管理员角色，因此不需要指定任何组。</span><span class="sxs-lookup"><span data-stu-id="a69e1-178">This policy applies to admin roles, so no groups need to be specified.</span></span> <span data-ttu-id="a69e1-179">只需要启用此策略。</span><span class="sxs-lookup"><span data-stu-id="a69e1-179">This policy just needs to be enabled.</span></span> <span data-ttu-id="a69e1-180">需要创建和启用所有后续策略。</span><span class="sxs-lookup"><span data-stu-id="a69e1-180">All subsequent policies need to be created and enabled.</span></span> |
| <span data-ttu-id="a69e1-181">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="a69e1-181">Block clients that don't support modern authentication</span></span> | <span data-ttu-id="a69e1-182">在策略设置中选择“所有用户”。</span><span class="sxs-lookup"><span data-stu-id="a69e1-182">Select “All users” in the policy settings.</span></span> |
| <span data-ttu-id="a69e1-183">当登录风险为中或高时需要执行 MFA（需要使用 Microsoft 365 企业版 E5）</span><span class="sxs-lookup"><span data-stu-id="a69e1-183">Require MFA when sign-in risk is medium or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="a69e1-184">基线</span><span class="sxs-lookup"><span data-stu-id="a69e1-184">Baseline</span></span> |
| <span data-ttu-id="a69e1-185">当登录风险为低、中或高时需要执行 MFA（需要使用 Microsoft 365 企业版 E5）</span><span class="sxs-lookup"><span data-stu-id="a69e1-185">Require MFA when sign-in risk is low, medium, or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="a69e1-186">敏感</span><span class="sxs-lookup"><span data-stu-id="a69e1-186">Sensitive</span></span> |
| <span data-ttu-id="a69e1-187">始终需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="a69e1-187">Always require MFA</span></span> | <span data-ttu-id="a69e1-188">高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-188">HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="a69e1-189">需要在 iOS 和 Android 设备上使用经过批准的应用</span><span class="sxs-lookup"><span data-stu-id="a69e1-189">Require approved apps on iOS and Android devices</span></span> | <span data-ttu-id="a69e1-190">基线、敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-190">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="a69e1-191">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="a69e1-191">Require compliant PCs</span></span> | <span data-ttu-id="a69e1-192">基线</span><span class="sxs-lookup"><span data-stu-id="a69e1-192">Baseline</span></span> |
| <span data-ttu-id="a69e1-193">需要兼容电脑以及 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="a69e1-193">Require compliant PCs and iOS and Android devices</span></span> | <span data-ttu-id="a69e1-194">敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-194">SENSITIVE, HIGHLY-REGULATED</span></span> |
|||

<span data-ttu-id="a69e1-195">以下是要创建和启用的 Azure AD Identity Protection（需要使用 Microsoft 365 企业版 E5）用户风险策略。</span><span class="sxs-lookup"><span data-stu-id="a69e1-195">Here is the Azure AD Identity Protection (requires Microsoft 365 Enterprise E5) user risk policy to create and enable.</span></span>

| <span data-ttu-id="a69e1-196">Azure AD Identity Protection 用户风险策略</span><span class="sxs-lookup"><span data-stu-id="a69e1-196">Azure AD Identity Protection user risk policy</span></span> | <span data-ttu-id="a69e1-197">应用到的组</span><span class="sxs-lookup"><span data-stu-id="a69e1-197">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="a69e1-198">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="a69e1-198">High risk users must change passwords</span></span> | <span data-ttu-id="a69e1-199">在策略设置中选择“所有用户”。</span><span class="sxs-lookup"><span data-stu-id="a69e1-199">Select “All users” in the policy settings.</span></span> |
|||

<span data-ttu-id="a69e1-200">有关说明，请参阅[通用标识和设备访问策略](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-200">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="groups-for-easier-management"></a><span data-ttu-id="a69e1-201">通过组实现更轻松的管理</span><span class="sxs-lookup"><span data-stu-id="a69e1-201">Groups for easier management</span></span>

<span data-ttu-id="a69e1-202">以下是一些可以使你更轻松地进行组和许可管理的功能。</span><span class="sxs-lookup"><span data-stu-id="a69e1-202">Here are some features that can make group and licensing management easier for you.</span></span>

| <span data-ttu-id="a69e1-203">功能</span><span class="sxs-lookup"><span data-stu-id="a69e1-203">Feature</span></span> | <span data-ttu-id="a69e1-204">用途</span><span class="sxs-lookup"><span data-stu-id="a69e1-204">Use</span></span> |
|:------|:-----|
| <span data-ttu-id="a69e1-205">自助服务组管理</span><span class="sxs-lookup"><span data-stu-id="a69e1-205">Self-service group management</span></span> | <span data-ttu-id="a69e1-206">允许组所有者而不是 IT 人员管理 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a69e1-206">Allow management of Azure AD groups by group owners instead of IT staff.</span></span> <span data-ttu-id="a69e1-207">有关详细信息，请参阅[自助服务组管理](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-207">See [Self-service group management](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups) for more information.</span></span> |
| <span data-ttu-id="a69e1-208">动态组成员身份</span><span class="sxs-lookup"><span data-stu-id="a69e1-208">Dynamic group membership</span></span> | <span data-ttu-id="a69e1-209">根据用户帐户属性（如“部门”或“国家/地区”）配置在 Azure AD 组中自动添加或删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-209">Configure automatic addition or removal of user accounts from Azure AD groups based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="a69e1-210">关详细信息，请参阅[动态组成员身份](identity-use-group-management.md#set-up-dynamic-group-membership)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-210">See [Dynamic group membership](identity-use-group-management.md#set-up-dynamic-group-membership) for more information.</span></span> |
| <span data-ttu-id="a69e1-211">基于组的许可</span><span class="sxs-lookup"><span data-stu-id="a69e1-211">Group-based licensing</span></span> | <span data-ttu-id="a69e1-212">使用组成员身份自动为用户帐户分配或取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="a69e1-212">Use group membership to automatically assign or unassign licenses to user accounts.</span></span> <span data-ttu-id="a69e1-213">有关详细信息，请参阅[基于组的许可](identity-use-group-management.md#set-up-automatic-licensing)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-213">See [Group-based licensing](identity-use-group-management.md#set-up-automatic-licensing) for more information.</span></span> |
|  |  |

<span data-ttu-id="a69e1-214">如果你使用的是基于组的许可，请创建一个名为“已许可”的组，以包含分配了 Microsoft 365 企业版许可证的用户帐户名。</span><span class="sxs-lookup"><span data-stu-id="a69e1-214">If you are using group-based licensing, create a group named LICENSED to contain user account names that are assigned a Microsoft 365 Enterprise license.</span></span>

### <a name="monitor-user-access"></a><span data-ttu-id="a69e1-215">监视用户访问</span><span class="sxs-lookup"><span data-stu-id="a69e1-215">Monitor user access</span></span>

<span data-ttu-id="a69e1-216">如果你具有 Microsoft 365 企业版 E5，则可以使用 Azure AD Identity Protection 来监视和分析用户登录是否存在凭据泄露。</span><span class="sxs-lookup"><span data-stu-id="a69e1-216">If you have Microsoft 365 Enterprise E5, you can use Azure AD Identity Protection to monitor and analyze user sign-ins for credential compromise.</span></span> <span data-ttu-id="a69e1-217">有关详细信息，请参阅[防范凭据泄露](identity-secure-user-sign-ins.md#protect-against-credential-compromise)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-217">See [Protect against credential compromise](identity-secure-user-sign-ins.md#protect-against-credential-compromise) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="a69e1-218">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="a69e1-218">Your configuration so far</span></span>

<span data-ttu-id="a69e1-219">以下是混合标识的标识阶段的可视化摘要，其中突出显示了现有元素和新元素。</span><span class="sxs-lookup"><span data-stu-id="a69e1-219">Here is a visual summary of the Identity phase for hybrid identity, with existing and new elements highlighted.</span></span>

![混合标识的“标识”阶段之后的组织](./media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
<span data-ttu-id="a69e1-221">新的和突出显示的混合标识元素包括：</span><span class="sxs-lookup"><span data-stu-id="a69e1-221">The new and highlighted hybrid identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![具有用户帐户和组的本地 AD DS 域](./media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | <span data-ttu-id="a69e1-223">具有用户帐户和组的本地 AD DS 域。</span><span class="sxs-lookup"><span data-stu-id="a69e1-223">An on-premises AD DS domain with user accounts and groups.</span></span> |
| ![运行 Azure AD Connect 的基于 Windows 的服务器](./media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | <span data-ttu-id="a69e1-225">运行 Azure AD Connect 的基于 Windows 的服务器。</span><span class="sxs-lookup"><span data-stu-id="a69e1-225">A Windows-based server running Azure AD Connect.</span></span> |
| ![Azure AD 中的 AD DS 用户帐户和组的同步集](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | <span data-ttu-id="a69e1-227">Azure AD 中的 AD DS 用户帐户和组的同步集。</span><span class="sxs-lookup"><span data-stu-id="a69e1-227">The synchronized set of AD DS user accounts and groups in Azure AD.</span></span> |
| ![用于身份验证、保护全局帐户以及更轻松地管理组和许可证的 Azure AD 设置](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="a69e1-229">用于身份验证、保护全局帐户以及更轻松地管理组和许可证的 Azure AD 设置。</span><span class="sxs-lookup"><span data-stu-id="a69e1-229">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![Azure AD 条件访问策略](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="a69e1-231">Azure AD 条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="a69e1-231">Azure AD Conditional Access policies.</span></span> |
|||

<span data-ttu-id="a69e1-232">以下是仅限云标识的标识阶段的可视化摘要，其中突出显示了新元素。</span><span class="sxs-lookup"><span data-stu-id="a69e1-232">Here is a visual summary of the Identity phase for cloud-only identity, with the new elements highlighted.</span></span>

![仅限云的“标识”阶段之后的组织](./media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
<span data-ttu-id="a69e1-234">新的和突出显示的仅限云标识元素包括：</span><span class="sxs-lookup"><span data-stu-id="a69e1-234">The new and highlighted cloud-only identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![Azure AD 中的用户帐户和组](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts-cloud-only.png) | <span data-ttu-id="a69e1-236">Azure AD 中的用户帐户和组。</span><span class="sxs-lookup"><span data-stu-id="a69e1-236">The user accounts and groups in Azure AD.</span></span> |
| ![用于身份验证、保护全局帐户以及更轻松地管理组和许可证的 Azure AD 设置](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="a69e1-238">用于身份验证、保护全局帐户以及更轻松地管理组和许可证的 Azure AD 设置。</span><span class="sxs-lookup"><span data-stu-id="a69e1-238">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![Azure AD 条件访问策略](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="a69e1-240">Azure AD 条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="a69e1-240">Azure AD Conditional Access policies.</span></span> |
|||

## <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="a69e1-241">阶段 3：Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="a69e1-241">Phase 3: Windows 10 Enterprise</span></span>

<span data-ttu-id="a69e1-242">为确保将 Windows 10 企业版设备集成到 Microsoft 365 企业版的标识和安全基础结构中，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="a69e1-242">To ensure that your Windows 10 Enterprise devices are integrated into the identity and security infrastructure of Microsoft 365 Enterprise, here are your options:</span></span>

- <span data-ttu-id="a69e1-243">混合（你具有本地 AD DS 域）</span><span class="sxs-lookup"><span data-stu-id="a69e1-243">Hybrid (you have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="a69e1-244">对于已加入 AD DS 域的每台现有的 Windows 10 企业版设备，请将它们加入 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-244">For each existing Windows 10 Enterprise device already joined to your AD DS domain, join them to the Azure AD tenant.</span></span> <span data-ttu-id="a69e1-245">有关说明，请参阅[如何配置联接到混合 Azure Active Directory 的设备](https://go.microsoft.com/fwlink/p/?linkid=872870)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-245">See [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870) for the instructions.</span></span>

  <span data-ttu-id="a69e1-246">对于每台新的 Windows 10 企业版设备，请将它们加入 AD DS 域，然后将它们加入 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-246">For each new Windows 10 Enterprise device, join them to your AD DS domain, and then join them to the Azure AD tenant.</span></span>

  <span data-ttu-id="a69e1-247">对于每台 Windows 10 企业版设备，请注册它们以进行移动设备管理。</span><span class="sxs-lookup"><span data-stu-id="a69e1-247">For each Windows 10 Enterprise device, enroll them for mobile device management.</span></span> <span data-ttu-id="a69e1-248">有关说明，请参阅[使用组策略注册带有 Intune 的 Windows 10 设备](https://go.microsoft.com/fwlink/p/?linkid=872871)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-248">See [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for the instructions.</span></span>

- <span data-ttu-id="a69e1-249">仅限云（如果你没有本地 AD DS 域）</span><span class="sxs-lookup"><span data-stu-id="a69e1-249">Cloud-only (you do not have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="a69e1-250">将每台 Windows 10 企业版设备加入订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-250">Join each Windows 10 Enterprise device to the Azure AD tenant of your subscription.</span></span>

  <span data-ttu-id="a69e1-251">有关详细信息，请参阅[将工作设备加入组织的网络](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-251">See [Join your work device to your organization's network](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) for more information.</span></span>


<span data-ttu-id="a69e1-252">安装并加入后，每台 Windows 10 企业版设备都会自动从 Windows Update for Business 云服务安装更新。</span><span class="sxs-lookup"><span data-stu-id="a69e1-252">Once installed and joined, each Windows 10 Enterprise device automatically installs updates from the Windows Update for Business cloud service.</span></span> <span data-ttu-id="a69e1-253">在非企业组织中，通常无需设置基础结构即可分发和安装 Windows 10 更新。</span><span class="sxs-lookup"><span data-stu-id="a69e1-253">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute and install Windows 10 updates.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="a69e1-254">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="a69e1-254">Your configuration so far</span></span>

<span data-ttu-id="a69e1-255">以下是 Windows 10 企业版阶段的可视化摘要，其中突出显示了新元素。</span><span class="sxs-lookup"><span data-stu-id="a69e1-255">Here is a visual summary of the Windows 10 Enterprise phase with the new elements highlighted.</span></span>

![“Windows 10 企业版”阶段之后的组织](./media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
<span data-ttu-id="a69e1-257">新的和突出显示的 Windows 10 企业版元素包括：</span><span class="sxs-lookup"><span data-stu-id="a69e1-257">The new and highlighted Windows 10 Enterprise elements include:</span></span>

|||
|:------:|:-----|
| ![Windows 设备上安装的 Windows 10 企业版](./media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | <span data-ttu-id="a69e1-259">Windows 设备上安装的 Windows 10 企业版，以本地笔记本电脑为例。</span><span class="sxs-lookup"><span data-stu-id="a69e1-259">Windows 10 Enterprise installed on Windows devices, with an on-premises laptop as an example.</span></span> |
| ![批量许可服务中心](./media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | <span data-ttu-id="a69e1-261">批量许可服务中心（它为新安装的 Windows 10 企业版提供映像）和 Windows Update for Business 服务（它提供最新的更新）。</span><span class="sxs-lookup"><span data-stu-id="a69e1-261">The Volume Licensing Service Center, which provides images for new installations of Windows 10 Enterprise, and the Windows Update for Business service, which provides the latest updates.</span></span> |
|||

## <a name="phase-4-office-365-proplus"></a><span data-ttu-id="a69e1-262">阶段 4：Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="a69e1-262">Phase 4: Office 365 ProPlus</span></span>

<span data-ttu-id="a69e1-263">Microsoft 365 企业版包括 Office 365 专业增强版，即 Microsoft Office 的订阅版本。</span><span class="sxs-lookup"><span data-stu-id="a69e1-263">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Microsoft Office.</span></span> <span data-ttu-id="a69e1-264">与 Office 2016 或 Office 2019 一样，Office 365 专业增强版也直接安装在客户端设备上。</span><span class="sxs-lookup"><span data-stu-id="a69e1-264">Like Office 2016 or Office 2019, Office 365 ProPlus is installed directly on your client devices.</span></span> <span data-ttu-id="a69e1-265">但是，Office 365 专业增强版会定期接收包含新功能的更新。</span><span class="sxs-lookup"><span data-stu-id="a69e1-265">However, Office 365 ProPlus receives updates that include new features on a regular basis.</span></span> <span data-ttu-id="a69e1-266">有关详细信息，请参阅[关于企业中的 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-266">See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

<span data-ttu-id="a69e1-267">对于非企业组织，请在设备（包括 Windows、iOS 和 Android 设备）上手动安装 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="a69e1-267">For your non-enterprise organization, you manually install Office 365 ProPlus on devices, which can include Windows, iOS, and Android devices.</span></span> <span data-ttu-id="a69e1-268">这可以作为准备使用新设备的一部分来完成，也可以由用户在载入过程中完成。</span><span class="sxs-lookup"><span data-stu-id="a69e1-268">This can be done as part of preparing a new device for use, or by the user as part of their onboarding process.</span></span>

<span data-ttu-id="a69e1-269">在任何一种情况下，管理员或用户都需要登录 Office 365 门户：https://portal.office.com。</span><span class="sxs-lookup"><span data-stu-id="a69e1-269">In either case, the administrator or the user signs in to the Office 365 portal at https://portal.office.com.</span></span> <span data-ttu-id="a69e1-270">在“**Microsoft Office 家庭版**”选项卡上，单击“**安装 Office**”并逐步完成安装过程。</span><span class="sxs-lookup"><span data-stu-id="a69e1-270">On the **Microsoft Office Home** tab, click **Install Office** and step through the installation process.</span></span>

<span data-ttu-id="a69e1-271">安装它的每台计算机每月都会下载 Office 365 专业增强版的功能更新。</span><span class="sxs-lookup"><span data-stu-id="a69e1-271">Feature updates to Office 365 ProPlus are downloaded monthly by each computer on which it is installed.</span></span> <span data-ttu-id="a69e1-272">在非企业组织中，通常无需设置基础结构即可分发 Office 365 专业增强版更新。</span><span class="sxs-lookup"><span data-stu-id="a69e1-272">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute Office 365 ProPlus updates.</span></span> 

### <a name="your-configuration-so-far"></a><span data-ttu-id="a69e1-273">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="a69e1-273">Your configuration so far</span></span>

<span data-ttu-id="a69e1-274">以下是 Office 365 专业增强版阶段的可视化摘要，其中突出显示了新元素。</span><span class="sxs-lookup"><span data-stu-id="a69e1-274">Here is a visual summary of the Office 365 ProPlus phase with the new elements highlighted.</span></span>

![“Office 365 专业增强版”阶段之后的组织](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
<span data-ttu-id="a69e1-276">新的和突出显示的 Office 365 专业增强版元素包括：</span><span class="sxs-lookup"><span data-stu-id="a69e1-276">The new and highlighted Office 365 ProPlus elements include:</span></span>
 
|||
|:------:|:-----|
| ![设备上安装的 Office 365 专业增强版](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | <span data-ttu-id="a69e1-278">设备上安装的 Office 365 专业增强版，以本地笔记本电脑为例。</span><span class="sxs-lookup"><span data-stu-id="a69e1-278">Office 365 ProPlus installed on devices, with an on-premises laptop as an example.</span></span> |
| ![Office 365 专业增强版的 Office 内容交付网络 (CDN)](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | <span data-ttu-id="a69e1-280">Office 365 专业增强版的 Office 内容交付网络 (CDN)，设备可以通过它访问 Office 365 专业增强版更新。</span><span class="sxs-lookup"><span data-stu-id="a69e1-280">The Office Content Delivery Network (CDN) for Office 365 ProPlus, which devices access for Office 365 ProPlus updates.</span></span> |
|||

## <a name="phase-5-mobile-device-management"></a><span data-ttu-id="a69e1-281">阶段 5：移动设备管理</span><span class="sxs-lookup"><span data-stu-id="a69e1-281">Phase 5: Mobile device management</span></span>

<span data-ttu-id="a69e1-282">Microsoft 365 企业版包含用于移动设备管理的 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="a69e1-282">Microsoft 365 Enterprise includes Microsoft Intune for mobile device management.</span></span> <span data-ttu-id="a69e1-283">使用 Intune，你可以管理 Windows、iOS、Android 和 macOS，以保护对组织资源（包括数据）的访问。</span><span class="sxs-lookup"><span data-stu-id="a69e1-283">With Intune, you can manage Windows, iOS, Android, and macOS devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="a69e1-284">Intune 使用 Azure AD 的用户、组和计算机帐户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-284">Intune uses the user, group, and computer accounts of Azure AD.</span></span>

<span data-ttu-id="a69e1-285">Intune 提供了两种类型的移动设备管理：</span><span class="sxs-lookup"><span data-stu-id="a69e1-285">Intune provides two types of mobile device management:</span></span>

- <span data-ttu-id="a69e1-286">在 Intune 中注册设备后进行移动设备管理 (MDM)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-286">Mobile device management (MDM) is when devices get enrolled in Intune.</span></span> <span data-ttu-id="a69e1-287">注册后，它们将成为受管理设备，可以接收组织使用的策略、规则和设置。</span><span class="sxs-lookup"><span data-stu-id="a69e1-287">Once enrolled, they are managed devices and can receive the policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="a69e1-288">这些类型的设备通常由贵组织拥有并分发给你的员工。</span><span class="sxs-lookup"><span data-stu-id="a69e1-288">These types of devices are typically owned by your organization and issued to your employees.</span></span>

- <span data-ttu-id="a69e1-289">拥有个人设备的用户可能不想注册他们的设备，也不希望由 Intune 使用你的策略和设置进行管理。</span><span class="sxs-lookup"><span data-stu-id="a69e1-289">Users with their own personal devices may not want to enroll their devices or be managed by Intune with your policies and settings.</span></span> <span data-ttu-id="a69e1-290">但是，你仍需要保护组织的资源和数据。</span><span class="sxs-lookup"><span data-stu-id="a69e1-290">However, you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="a69e1-291">在这种情况下，你可以使用移动应用程序管理 (MAM) 来保护你的应用。</span><span class="sxs-lookup"><span data-stu-id="a69e1-291">For this scenario, you can protect your apps with mobile application management (MAM).</span></span>  

<span data-ttu-id="a69e1-292">Intune 策略可以强制执行设备合规性和应用保护。</span><span class="sxs-lookup"><span data-stu-id="a69e1-292">Intune policies can enforce device compliance and app protection.</span></span> <span data-ttu-id="a69e1-293">以下是要创建的 Intune 策略的列表。</span><span class="sxs-lookup"><span data-stu-id="a69e1-293">Here is the list of Intune policies to create.</span></span>

| <span data-ttu-id="a69e1-294">Intune 策略</span><span class="sxs-lookup"><span data-stu-id="a69e1-294">Intune policies</span></span> | <span data-ttu-id="a69e1-295">应用到的组</span><span class="sxs-lookup"><span data-stu-id="a69e1-295">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="a69e1-296">Windows 的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="a69e1-296">Device compliance policy for Windows</span></span> | <span data-ttu-id="a69e1-297">基线、敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-297">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="a69e1-298">iOS 的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="a69e1-298">Device compliance policy for iOS</span></span> | <span data-ttu-id="a69e1-299">敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-299">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="a69e1-300">macOS 的设备合规性</span><span class="sxs-lookup"><span data-stu-id="a69e1-300">Device compliance for macOS</span></span> | <span data-ttu-id="a69e1-301">敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-301">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="a69e1-302">Android 和 Android Enterprise 的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="a69e1-302">Device compliance policy for Android and Android Enterprise</span></span> | <span data-ttu-id="a69e1-303">敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-303">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="a69e1-304">iOS 的应用保护策略</span><span class="sxs-lookup"><span data-stu-id="a69e1-304">App protection policy for iOS</span></span> | <span data-ttu-id="a69e1-305">基线、敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-305">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="a69e1-306">macOS 的应用保护策略</span><span class="sxs-lookup"><span data-stu-id="a69e1-306">App protection policy for macOS</span></span> | <span data-ttu-id="a69e1-307">基线、敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-307">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="a69e1-308">Android 和 Android Enterprise 的应用保护策略</span><span class="sxs-lookup"><span data-stu-id="a69e1-308">App protection policy for Android and Android Enterprise</span></span> | <span data-ttu-id="a69e1-309">基线、敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-309">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
|||
    
<span data-ttu-id="a69e1-310">有关说明，请参阅[通用标识和设备访问策略](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-310">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="a69e1-311">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="a69e1-311">Your configuration so far</span></span>

<span data-ttu-id="a69e1-312">以下是移动设备管理阶段的可视化摘要，其中突出显示了新元素。</span><span class="sxs-lookup"><span data-stu-id="a69e1-312">Here is a visual summary of the Mobile Device Management phase with the new elements highlighted.</span></span>

![“移动设备管理”阶段之后的组织](./media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
<span data-ttu-id="a69e1-314">新的和突出显示的移动设备管理元素包括：</span><span class="sxs-lookup"><span data-stu-id="a69e1-314">The new and highlighted mobile device management elements include:</span></span>

|||
|:------:|:-----|
| ![在 Intune 中注册的设备](./media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | <span data-ttu-id="a69e1-316">在 Intune 中注册的设备，显示正运行 Windows 10 企业版的本地笔记本电脑为例。</span><span class="sxs-lookup"><span data-stu-id="a69e1-316">Devices that are enrolled in Intune, showing an on-premises laptop running Windows 10 Enterprise as an example.</span></span> |
| ![Intune 的设备合规性和应用保护策略](./media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | <span data-ttu-id="a69e1-318">Intune 的设备合规性和应用保护策略。</span><span class="sxs-lookup"><span data-stu-id="a69e1-318">Intune policies for device compliance and app protection.</span></span> |
|||

## <a name="phase-6-information-protection"></a><span data-ttu-id="a69e1-319">阶段 6：信息保护</span><span class="sxs-lookup"><span data-stu-id="a69e1-319">Phase 6: Information protection</span></span>

<span data-ttu-id="a69e1-320">Microsoft 365 企业版具有许多信息保护功能，允许你通过应用不同级别的管理、安全性和保护来区别对待数据分类。</span><span class="sxs-lookup"><span data-stu-id="a69e1-320">Microsoft 365 Enterprise has a host of information protection features that allow you to treat classifications of data differently by applying different levels of governance, security, and protection.</span></span> 

<span data-ttu-id="a69e1-321">例如，通常大多数员工与他们所处理文档之间的对应关系都需要特定的基线保护级别。</span><span class="sxs-lookup"><span data-stu-id="a69e1-321">For example, normal correspondence between most employees and the documents on which they work need a certain baseline level of protection.</span></span> <span data-ttu-id="a69e1-322">财务记录、客户数据和你的知识产权需要更高级别的保护。</span><span class="sxs-lookup"><span data-stu-id="a69e1-322">Financial records, customer data, and your intellectual property need a higher level of protection.</span></span>

<span data-ttu-id="a69e1-323">信息保护策略的第一步是确定保护级别。</span><span class="sxs-lookup"><span data-stu-id="a69e1-323">The first step to an information protection strategy is to determine the levels of protection.</span></span> <span data-ttu-id="a69e1-324">许多组织都会使用已用于条件访问策略的保护级别：</span><span class="sxs-lookup"><span data-stu-id="a69e1-324">Many organizations use these levels, which are already being used for Conditional Access policies:</span></span>

- <span data-ttu-id="a69e1-325">基线</span><span class="sxs-lookup"><span data-stu-id="a69e1-325">Baseline</span></span>

  <span data-ttu-id="a69e1-326">示例包括正常的业务通信（电子邮件）和供管理、销售和支持工作人员使用的文件。</span><span class="sxs-lookup"><span data-stu-id="a69e1-326">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span>

- <span data-ttu-id="a69e1-327">敏感</span><span class="sxs-lookup"><span data-stu-id="a69e1-327">Sensitive</span></span>

  <span data-ttu-id="a69e1-328">示例包括财务和法律信息，以及新产品或服务的研发数据。</span><span class="sxs-lookup"><span data-stu-id="a69e1-328">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span>

- <span data-ttu-id="a69e1-329">高度管控</span><span class="sxs-lookup"><span data-stu-id="a69e1-329">Highly regulated</span></span>

  <span data-ttu-id="a69e1-330">示例包括客户和合作伙伴的个人身份信息以及组织的战略计划或知识产权。</span><span class="sxs-lookup"><span data-stu-id="a69e1-330">Examples include customer and partner personally identifiable information and your organization’s strategic plans or intellectual property.</span></span>

<span data-ttu-id="a69e1-331">基于这些数据安全级别，下一步是确定并实施：</span><span class="sxs-lookup"><span data-stu-id="a69e1-331">Based on these levels of data security, the next step is to identify and implement:</span></span>

- <span data-ttu-id="a69e1-332">自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a69e1-332">Custom sensitive information types</span></span>

  <span data-ttu-id="a69e1-333">Microsoft 365 提供了各种敏感信息类型，例如健康服务和信用卡号。</span><span class="sxs-lookup"><span data-stu-id="a69e1-333">Microsoft 365 supplies a wide selection of sensitive information types, such as health service and credit card numbers.</span></span> <span data-ttu-id="a69e1-334">如果你未在提供的列表中找到所需的类型，则可以创建自己的信息类型。</span><span class="sxs-lookup"><span data-stu-id="a69e1-334">If you do not find one that you need in the supplied list, you can create your own.</span></span>

- <span data-ttu-id="a69e1-335">保留标签</span><span class="sxs-lookup"><span data-stu-id="a69e1-335">Retention labels</span></span>

  <span data-ttu-id="a69e1-336">为了遵守组织政策和区域法规，你可能必须指定特定类型的文档或含有特定内容的文档应保留多长时间。</span><span class="sxs-lookup"><span data-stu-id="a69e1-336">To comply with organization policies and regional regulations, you might have to specify how long specific types of documents or documents with specific contents should be retained.</span></span> <span data-ttu-id="a69e1-337">你可以使用保留标签为电子邮件和文档实施此策略。</span><span class="sxs-lookup"><span data-stu-id="a69e1-337">You can implement this for email and documents using retention labels.</span></span> <span data-ttu-id="a69e1-338">保留标签还可以与数据丢失防护 (DLP) 策略结合使用，该策略可以限制在组织外部共享文件或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a69e1-338">Retention labels can also be used in conjunction with Data Loss Prevention (DLP) policies that can restrict the sharing of files or email outside your organization.</span></span>

- <span data-ttu-id="a69e1-339">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="a69e1-339">Sensitivity labels</span></span>

  <span data-ttu-id="a69e1-340">你可以使用指定的敏感度标签来标记电子邮件或文档，以便能够应用其他安全级别。</span><span class="sxs-lookup"><span data-stu-id="a69e1-340">You can label email or documents with a named sensitivity label so that additional levels of security can be applied.</span></span> <span data-ttu-id="a69e1-341">示例包括水印、加密和权限，这些将指定允许谁访问电子邮件或文档以及允许他们执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="a69e1-341">Examples are watermarks, encryption, and permissions, which specify who is allowed to access the email or document and what they are allowed to do.</span></span>

<span data-ttu-id="a69e1-342">有关详细信息，请参阅 [Microsoft 365 分类类型](infoprotect-configure-classification.md#microsoft-365-classification-types)。</span><span class="sxs-lookup"><span data-stu-id="a69e1-342">See [Microsoft 365 classification types](infoprotect-configure-classification.md#microsoft-365-classification-types) for more information.</span></span>

<span data-ttu-id="a69e1-343">如果你使用具有权限的敏感度标签，则可能必须创建其他 Azure AD 安全组，以定义允许谁对已应用敏感度标签的电子邮件和文档执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="a69e1-343">If you use sensitivity labels with permissions, you might have to create additional Azure AD security groups to define who is allowed to do what with email and documents that have the sensitivity label applied.</span></span> 

<span data-ttu-id="a69e1-344">例如，你需要创建一个“研发”敏感度标签来保护研发团队的电子邮件和文档。</span><span class="sxs-lookup"><span data-stu-id="a69e1-344">For example, you need to create a RESEARCH sensitivity label to protect the email and documents of your research team.</span></span> <span data-ttu-id="a69e1-345">你确定：</span><span class="sxs-lookup"><span data-stu-id="a69e1-345">You determine that:</span></span>

- <span data-ttu-id="a69e1-346">研发人员必须具有更改带“研发”敏感度标签文档的权限。</span><span class="sxs-lookup"><span data-stu-id="a69e1-346">Researchers must have the ability to change documents marked with the RESEARCH sensitivity label.</span></span>
- <span data-ttu-id="a69e1-347">非研发员工只需具有查看带“研发”敏感度标签文档的权限。</span><span class="sxs-lookup"><span data-stu-id="a69e1-347">Non-research employees only need to have the ability to view documents marked with the RESEARCH sensitivity label.</span></span> 

<span data-ttu-id="a69e1-348">这意味着你需要创建和管理两个附加组：</span><span class="sxs-lookup"><span data-stu-id="a69e1-348">This means you need to create and manage two additional groups:</span></span>

- <span data-ttu-id="a69e1-349">研发-全部</span><span class="sxs-lookup"><span data-stu-id="a69e1-349">RESEARCH-ALL</span></span>
- <span data-ttu-id="a69e1-350">研发-查看</span><span class="sxs-lookup"><span data-stu-id="a69e1-350">RESEARCH-VIEW</span></span>

<span data-ttu-id="a69e1-351">这些组及其权限将成为“研发”敏感度标签配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="a69e1-351">These groups and their permissions become part of the RESEARCH sensitivity label's configuration.</span></span>

<span data-ttu-id="a69e1-352">对于已配置基于组的权限的敏感度标签，你必须管理这些组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="a69e1-352">For sensitivity labels configured with group-based permissions, you must manage the membership of these groups.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="a69e1-353">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="a69e1-353">Your configuration so far</span></span>

<span data-ttu-id="a69e1-354">以下是信息保护阶段的可视化摘要，其中突出显示了新元素。</span><span class="sxs-lookup"><span data-stu-id="a69e1-354">Here is a visual summary of the Information Protection phase with the new elements highlighted.</span></span>

![“信息保护”阶段之后的组织](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
<span data-ttu-id="a69e1-356">新的和突出显示的信息保护元素包括：</span><span class="sxs-lookup"><span data-stu-id="a69e1-356">The new and highlighted information protection elements include:</span></span>
 
|||
|:------:|:-----|
| ![三个安全级别的敏感度标签](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | <span data-ttu-id="a69e1-358">用户可以应用于文档和电子邮件的三个安全级别的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="a69e1-358">Sensitivity labels for the three levels of security that users can apply to documents and email.</span></span> |
|||

<span data-ttu-id="a69e1-359">未显示客户信息类型和保留标签。</span><span class="sxs-lookup"><span data-stu-id="a69e1-359">Custom information types and retention labels are not shown.</span></span>

## <a name="onboarding"></a><span data-ttu-id="a69e1-360">载入</span><span class="sxs-lookup"><span data-stu-id="a69e1-360">Onboarding</span></span>

<span data-ttu-id="a69e1-361">有了 Microsoft 365 企业版基础结构，你可以轻松载入员工。</span><span class="sxs-lookup"><span data-stu-id="a69e1-361">With your Microsoft 365 Enterprise infrastructure in place, you can easily onboard your employees.</span></span>

### <a name="a-new-windows-10-enterprise-device"></a><span data-ttu-id="a69e1-362">新的 Windows 10 企业版设备</span><span class="sxs-lookup"><span data-stu-id="a69e1-362">A new Windows 10 Enterprise device</span></span>

<span data-ttu-id="a69e1-363">在为员工提供新的 Windows 10 企业版设备之前：</span><span class="sxs-lookup"><span data-stu-id="a69e1-363">Before giving an employee a new Windows 10 Enterprise device:</span></span>

- <span data-ttu-id="a69e1-364">对于混合标识</span><span class="sxs-lookup"><span data-stu-id="a69e1-364">For hybrid identity</span></span>

  <span data-ttu-id="a69e1-365">依次将设备加入 AD DS 域和 Azure AD 租户，然后在 Intune 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="a69e1-365">Join the device to your AD DS domain, join the device to your Azure AD tenant, and then enroll the device in Intune.</span></span>

- <span data-ttu-id="a69e1-366">对于仅限云标识</span><span class="sxs-lookup"><span data-stu-id="a69e1-366">For cloud-only identity</span></span>

  <span data-ttu-id="a69e1-367">将设备加入 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-367">Join the device to your Azure AD tenant.</span></span>

### <a name="existing-employee-with-an-ad-ds-user-account"></a><span data-ttu-id="a69e1-368">具有 AD DS 用户帐户的现有员工</span><span class="sxs-lookup"><span data-stu-id="a69e1-368">Existing employee with an AD DS user account</span></span>

<span data-ttu-id="a69e1-369">在使用混合标识时，作为组织的初始载入的一部分，请将 AD DS 用户帐户添加到这些 Azure AD 组：</span><span class="sxs-lookup"><span data-stu-id="a69e1-369">As part of the initial onboarding for your organization when using hybrid identity, add the AD DS user account to these Azure AD groups:</span></span>

- <span data-ttu-id="a69e1-370">已许可</span><span class="sxs-lookup"><span data-stu-id="a69e1-370">Licensed</span></span>
- <span data-ttu-id="a69e1-371">相应的 AD DS 或 Azure AD 安全组，它们是“基线”、“敏感”和“高度管控”Azure AD 组的成员</span><span class="sxs-lookup"><span data-stu-id="a69e1-371">The appropriate AD DS or Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="a69e1-372">敏感度标签组（根据需要）</span><span class="sxs-lookup"><span data-stu-id="a69e1-372">Sensitivity label groups (as needed)</span></span>

<span data-ttu-id="a69e1-373">现有员工应已添加到相应的工作组、部门和区域 AD DS 组。</span><span class="sxs-lookup"><span data-stu-id="a69e1-373">The existing employee should already be added to the appropriate workgroup, departmental, and regional AD DS groups.</span></span>

<span data-ttu-id="a69e1-374">可向 Microsoft 365 管理中心内的多个 Azure AD 组添加用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a69e1-374">You can add a user account to multiple Azure AD groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a69e1-375">从用户帐户的属性中，单击“**管理组” > “添加成员身份**”。</span><span class="sxs-lookup"><span data-stu-id="a69e1-375">From the properties of the user account, click **Manage groups > Add memberships**.</span></span>

<span data-ttu-id="a69e1-376">如果要使用 PowerShell，请参阅[可下载的 Excel 工作簿](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true)，它基于指定的用户帐户和选定的组名称生成 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="a69e1-376">If you want to use PowerShell, see this [downloadable Excel workbook](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true), which generates the PowerShell commands based on a specified user account and selected group names.</span></span>

### <a name="new-employee-with-a-cloud-only-user-account"></a><span data-ttu-id="a69e1-377">使用仅限云用户帐户的新员工</span><span class="sxs-lookup"><span data-stu-id="a69e1-377">New employee with a cloud-only user account</span></span>

<span data-ttu-id="a69e1-378">在使用仅限云标识时，作为组织的初始载入的一部分，请将新用户帐户添加到这些组：</span><span class="sxs-lookup"><span data-stu-id="a69e1-378">As part of the initial onboarding for your organization when using cloud-only identity, add the new user account to these groups:</span></span>

- <span data-ttu-id="a69e1-379">已许可</span><span class="sxs-lookup"><span data-stu-id="a69e1-379">Licensed</span></span>
- <span data-ttu-id="a69e1-380">相应的 Azure AD 安全组，它们是“基线”、“敏感”和“高度管控”Azure AD 组的成员</span><span class="sxs-lookup"><span data-stu-id="a69e1-380">The appropriate Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="a69e1-381">工作组、部门和区域组</span><span class="sxs-lookup"><span data-stu-id="a69e1-381">Workgroup, departmental, and regional groups</span></span>
- <span data-ttu-id="a69e1-382">敏感度标签组（根据需要）</span><span class="sxs-lookup"><span data-stu-id="a69e1-382">Sensitivity label groups (as needed)</span></span>

### <a name="initial-sign-in-to-microsoft-365"></a><span data-ttu-id="a69e1-383">初次登录 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a69e1-383">Initial sign-in to Microsoft 365</span></span>

<span data-ttu-id="a69e1-384">当员工首次登录 Microsoft 365 时，请指示他们：</span><span class="sxs-lookup"><span data-stu-id="a69e1-384">For the first time employees sign in to Microsoft 365, instruct them to:</span></span>

1. <span data-ttu-id="a69e1-385">使用其用户帐户凭据登录其设备。</span><span class="sxs-lookup"><span data-stu-id="a69e1-385">Sign into their devices with their user account credentials.</span></span>
2. <span data-ttu-id="a69e1-386">使用浏览器登录 Office 365 门户：https://portal.office.com。</span><span class="sxs-lookup"><span data-stu-id="a69e1-386">Using a browser on your local computer, sign in to the https://portal.office.com using your global administrator account.</span></span>
3. <span data-ttu-id="a69e1-387">在“**Office 365 家庭版**”选项卡中，单击“**安装 Office**”以在设备上安装 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="a69e1-387">From the **Office 365 Home** tab, click **Install Office** to install Office 365 ProPlus on their device.</span></span>

## <a name="end-results"></a><span data-ttu-id="a69e1-388">结果</span><span class="sxs-lookup"><span data-stu-id="a69e1-388">End results</span></span>

<span data-ttu-id="a69e1-389">以下是为非企业组织配置 Microsoft 365 企业版基础结构的结果。</span><span class="sxs-lookup"><span data-stu-id="a69e1-389">Here are the results of configuring the Microsoft 365 Enterprise foundation infrastructure for your non-enterprise organization.</span></span>

### <a name="infrastructure-results"></a><span data-ttu-id="a69e1-390">基础结构结果</span><span class="sxs-lookup"><span data-stu-id="a69e1-390">Infrastructure results</span></span>

<span data-ttu-id="a69e1-391">在构建和配置 Microsoft 365 企业版基础结构之后，你应该：</span><span class="sxs-lookup"><span data-stu-id="a69e1-391">After the build-out and configuration of your Microsoft 365 Enterprise infrastructure, you should have:</span></span>

- <span data-ttu-id="a69e1-392">为每个办公室建立了本地 Internet 连接，其具有由使用区域性本地 DNS 服务器的 ISP 提供的足够带宽。</span><span class="sxs-lookup"><span data-stu-id="a69e1-392">A local Internet connection for each of your offices with sufficient bandwidth supplied by an ISP that uses a regionally local DNS server.</span></span>
- <span data-ttu-id="a69e1-393">对于混合标识，具有在服务器上运行的 Azure AD Connect，该服务器可将你的本地 AD DS 域与 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="a69e1-393">For hybrid identity, Azure AD Connect running on a server that synchronizes your on-premises AD DS domain with your Azure AD tenant.</span></span>
- <span data-ttu-id="a69e1-394">这些组：</span><span class="sxs-lookup"><span data-stu-id="a69e1-394">These universal groups include:</span></span>
  - <span data-ttu-id="a69e1-395">已许可</span><span class="sxs-lookup"><span data-stu-id="a69e1-395">Licensed</span></span>
  - <span data-ttu-id="a69e1-396">条件-访问-排除</span><span class="sxs-lookup"><span data-stu-id="a69e1-396">COND-ACCESS-EXCLUDE</span></span>
  - <span data-ttu-id="a69e1-397">相应的 AD DS 或 Azure AD 安全组，它们也是“基线”、“敏感”和“高度管控”Azure AD 组的成员</span><span class="sxs-lookup"><span data-stu-id="a69e1-397">The appropriate AD DS or Azure AD security groups that are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span> 
  - <span data-ttu-id="a69e1-398">工作组、部门和区域组</span><span class="sxs-lookup"><span data-stu-id="a69e1-398">Workgroup, departmental, and regional groups</span></span>
  - <span data-ttu-id="a69e1-399">敏感度标签组（根据需要）</span><span class="sxs-lookup"><span data-stu-id="a69e1-399">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="a69e1-400">Azure AD 登录条件访问策略，它们使用“基线”、“敏感”、“高度管控”和“条件-访问-排除”Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a69e1-400">Azure AD sign-in Conditional Access policies that use the BASELINE, SENSITIVE, and HIGHLY-REGULATED, and COND-ACCESS-EXCLUDE Azure AD groups.</span></span>
- <span data-ttu-id="a69e1-401">Intune 应用程序和设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="a69e1-401">Intune application and device compliance policies.</span></span>
- <span data-ttu-id="a69e1-402">自定义敏感信息类型（根据需要）。</span><span class="sxs-lookup"><span data-stu-id="a69e1-402">Custom sensitive information types (as needed).</span></span>
- <span data-ttu-id="a69e1-403">保留标签（根据需要）。</span><span class="sxs-lookup"><span data-stu-id="a69e1-403">Retention labels (as needed).</span></span>
- <span data-ttu-id="a69e1-404">敏感度标签（根据需要）。</span><span class="sxs-lookup"><span data-stu-id="a69e1-404">Sensitivity labels (as needed).</span></span>

<span data-ttu-id="a69e1-405">以下是当组织使用混合标识时基础结构的可视化摘要，它包含 AD DS 域、Azure AD Connect 服务器以及同步的 AD DS 用户和组。</span><span class="sxs-lookup"><span data-stu-id="a69e1-405">Here is a visual summary of the infrastructure if your organization uses hybrid identity, which includes your AD DS domain, an Azure AD Connect server, and synchronized AD DS users and groups.</span></span>

![当组织使用混合标识时基础结构的摘要](./media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
<span data-ttu-id="a69e1-407">以下是当组织使用仅限云标识时基础结构的可视化摘要。</span><span class="sxs-lookup"><span data-stu-id="a69e1-407">Here is a visual summary of the infrastructure if your organization uses cloud-only identity.</span></span>
 
![当组织使用仅限云标识时基础结构的摘要](./media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a><span data-ttu-id="a69e1-409">员工结果</span><span class="sxs-lookup"><span data-stu-id="a69e1-409">Employee results</span></span>

<span data-ttu-id="a69e1-410">载入后，每位员工都应该具有：</span><span class="sxs-lookup"><span data-stu-id="a69e1-410">After their onboarding, each employee should have:</span></span>

- <span data-ttu-id="a69e1-411">从其设备到其区域内的 Microsoft 365 云服务的高性能本地网络路径。</span><span class="sxs-lookup"><span data-stu-id="a69e1-411">A performant, on-premises network path from their device to the Microsoft 365 cloud services in their region.</span></span>
- <span data-ttu-id="a69e1-412">包含这些组成员身份的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="a69e1-412">A user account with these group memberships:</span></span>
   - <span data-ttu-id="a69e1-413">已许可</span><span class="sxs-lookup"><span data-stu-id="a69e1-413">Licensed</span></span>
   - <span data-ttu-id="a69e1-414">相应的 AD DS 或 Azure AD 安全组，它们也是“基线”、“敏感”和“高度管控”Azure AD 条件访问策略组的成员</span><span class="sxs-lookup"><span data-stu-id="a69e1-414">The appropriate AD DS or Azure AD security groups, which are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups for Conditional Access policies</span></span> 
   - <span data-ttu-id="a69e1-415">相应的工作组、部门和区域组</span><span class="sxs-lookup"><span data-stu-id="a69e1-415">The appropriate workgroup, departmental, and regional groups</span></span>
   - <span data-ttu-id="a69e1-416">敏感度标签组（根据需要）</span><span class="sxs-lookup"><span data-stu-id="a69e1-416">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="a69e1-417">Windows 10 企业版设备：</span><span class="sxs-lookup"><span data-stu-id="a69e1-417">A Windows 10 Enterprise device that:</span></span>
   - <span data-ttu-id="a69e1-418">已加入 Azure AD 租户（仅限云）或已同时加入 Azure AD 租户和 AD DS 域（混合）。</span><span class="sxs-lookup"><span data-stu-id="a69e1-418">Is joined to the Azure AD tenant (cloud-only) or to both the Azure AD tenant and your AD DS domain (hybrid).</span></span>
   - <span data-ttu-id="a69e1-419">使用最新的 Windows 10 企业版产品改进和安全增强功能进行自动更新。</span><span class="sxs-lookup"><span data-stu-id="a69e1-419">Automatically updates itself with the latest Windows 10 Enterprise product improvements and security enhancements.</span></span>
   - <span data-ttu-id="a69e1-420">已安装 Office 365 专业增强版，它使用最新的 Office 产品改进和安全增强功能进行自动更新。</span><span class="sxs-lookup"><span data-stu-id="a69e1-420">Has Office 365 ProPlus installed, which automatically updates itself with the latest Office product improvements and security enhancements.</span></span>
   - <span data-ttu-id="a69e1-421">已在 Intune 中注册并受 Intune 设备合规性策略和应用保护策略的制约。</span><span class="sxs-lookup"><span data-stu-id="a69e1-421">Is enrolled in Intune and subject to Intune device compliance policies and app protection policies.</span></span>

## <a name="next-step"></a><span data-ttu-id="a69e1-422">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a69e1-422">Next step</span></span>

<span data-ttu-id="a69e1-423">部署[工作负载和方案](deploy-workloads.md)以利用 Microsoft 365 企业版基础结构的功能和配置。</span><span class="sxs-lookup"><span data-stu-id="a69e1-423">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
