---
title: 适用于非企业组织的 Microsoft 365 企业版基础结构
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/22/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 逐步完成适用于非企业组织的 Microsoft 365 企业版基础结构的简化部署阶段。
ms.openlocfilehash: 64d911a9d59d5b9b1a450a9a122463699ec8eab8
ms.sourcegitcommit: 2cf0d57b1771b37db773c3eaabac8456a6fa9195
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "34419811"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-for-non-enterprises"></a><span data-ttu-id="7f135-103">适用于非企业组织的 Microsoft 365 企业版基础结构</span><span class="sxs-lookup"><span data-stu-id="7f135-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="7f135-104">非企业组织也可以部署 Microsoft 365 企业版，并实现集成式安全基础结构的业务价值，从而实现团队协作并激发创造力。</span><span class="sxs-lookup"><span data-stu-id="7f135-104">Non-enterprise organizations can also deploy Microsoft 365 Enterprise and realize the business value of an integrated and secure infrastructure that enables teamwork and unlocks creativity.</span></span> <span data-ttu-id="7f135-105">非企业组织通常具有：</span><span class="sxs-lookup"><span data-stu-id="7f135-105">A non-enterprise typically has:</span></span>

- <span data-ttu-id="7f135-106">少量的本地 IT 基础结构，例如电子邮件和文件服务器以及 Active Directory 域服务 (AD DS) 域，或者根本不存在。</span><span class="sxs-lookup"><span data-stu-id="7f135-106">A small amount of on-premises IT infrastructure, such as email and file servers and an Active Directory Domain Services (AD DS) domain, or none at all.</span></span>
- <span data-ttu-id="7f135-107">少量的 IT 人员，其中大多数是 IT 通才，而不是特定技术或工作负载（如网络或电子邮件）领域的专家。</span><span class="sxs-lookup"><span data-stu-id="7f135-107">A small IT staff, most of whom are IT generalists, rather than specialists in a specific technology or workload such as networking or email.</span></span>

<span data-ttu-id="7f135-108">Microsoft 为小型非企业组织提供了 [Microsoft 365 商业版](https://www.microsoft.com/microsoft-365/business)。</span><span class="sxs-lookup"><span data-stu-id="7f135-108">For your smaller, non-enterprise organization, Microsoft offers [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="7f135-109">但是，出于某些原因你可能需要使用 Microsoft 365 企业版，例如：</span><span class="sxs-lookup"><span data-stu-id="7f135-109">However, there are reasons why you might need Microsoft 365 Enterprise, such as:</span></span>

- <span data-ttu-id="7f135-110">你的组织需要超过 300 个 Microsoft 365 许可证，而 Microsoft 365 商业版的最大许可证数量为 300 个。</span><span class="sxs-lookup"><span data-stu-id="7f135-110">Your organization needs more or will need more than 300 Microsoft 365 licenses, which is the maximum for Microsoft 365 Business.</span></span>
- <span data-ttu-id="7f135-111">你的组织需要高级生产力、语音、安全性和分析功能，这些功能是 Microsoft 365 商业版所不具备的。</span><span class="sxs-lookup"><span data-stu-id="7f135-111">Your organization needs the advanced productivity, voice, security, and analytics that are not available with Microsoft 365 Business.</span></span>

<span data-ttu-id="7f135-112">本文将指导你完成适用于非企业组织的 Microsoft 365 企业版基础结构的简化部署。</span><span class="sxs-lookup"><span data-stu-id="7f135-112">This article steps you through a simplified deployment of the foundation infrastructure of Microsoft 365 Enterprise suitable for your non-enterprise.</span></span>

## <a name="first-set-up-your-subscription"></a><span data-ttu-id="7f135-113">首先，设置你的订阅</span><span class="sxs-lookup"><span data-stu-id="7f135-113">First, set up your subscription</span></span>

<span data-ttu-id="7f135-114">你必须为订阅设置域名系统 (DNS) 域。</span><span class="sxs-lookup"><span data-stu-id="7f135-114">You must set up the Domain Name System (DNS) domains for your subscription.</span></span> <span data-ttu-id="7f135-115">如果你已经拥有 Office 365 订阅，则应该已完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="7f135-115">If you already have an Office 365 subscription, this should have been done.</span></span> <span data-ttu-id="7f135-116">如果没有，请按照[将域添加到 Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide) 中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="7f135-116">If not, follow the instructions in [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span></span>

<span data-ttu-id="7f135-117">接下来，你需要为 Microsoft 365 配置其他安全性。</span><span class="sxs-lookup"><span data-stu-id="7f135-117">Next, you need to configure additional security for Microsoft 365.</span></span> <span data-ttu-id="7f135-118">请按照[配置增强的安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="7f135-118">Follow the instructions in [Configure increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

## <a name="phase-1-networking"></a><span data-ttu-id="7f135-119">阶段 1：网络</span><span class="sxs-lookup"><span data-stu-id="7f135-119">Phase 1: Networking</span></span>

<span data-ttu-id="7f135-120">非企业组织通常在每个办公室都建立了本地 Internet 连接，并且未使用代理服务器、防火墙或数据包检查设备。</span><span class="sxs-lookup"><span data-stu-id="7f135-120">Non-enterprise organizations typically have local Internet connections in each office and do not use proxy servers, firewalls, or packet inspection devices.</span></span> <span data-ttu-id="7f135-121">每个办公室的 Internet 服务提供商 (ISP) 都有一个区域性的本地 DNS 服务器，用于将流量定向到离你和本地用户最近的 Microsoft 365 云服务器。</span><span class="sxs-lookup"><span data-stu-id="7f135-121">The Internet service provider (ISP) at each office has a regionally local DNS server so that traffic is directed to the Microsoft 365 cloud servers that are closest to your offices and their on-premises users.</span></span>

<span data-ttu-id="7f135-122">因此，你只需要与 ISP 确认每个办公地点的连接：</span><span class="sxs-lookup"><span data-stu-id="7f135-122">Therefore, you only need to verify with your ISP that the connection at each of your office locations:</span></span>

- <span data-ttu-id="7f135-123">使用区域性的本地 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="7f135-123">Uses a regionally local DNS server.</span></span>
- <span data-ttu-id="7f135-124">随着用户开始使用更多的 Microsoft 365 云服务，足以满足当前和未来的需求。</span><span class="sxs-lookup"><span data-stu-id="7f135-124">Is adequate for current and future needs as your users begin using more Microsoft 365 cloud services.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="7f135-125">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="7f135-125">Your configuration so far</span></span>

<span data-ttu-id="7f135-126">以下是突出显示第 1 阶段元素的可视摘要。</span><span class="sxs-lookup"><span data-stu-id="7f135-126">Here is a visual summary with the Phase 1 element highlighted.</span></span> <span data-ttu-id="7f135-127">**你的组织**可能拥有多个办公室，每个办公室都与使用区域性本地 DNS 服务器的 ISP 建立了本地 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="7f135-127">**Your organization** can be multiple offices, each of which has a local Internet connection with an ISP that uses a regionally local DNS server.</span></span> <span data-ttu-id="7f135-128">通过 ISP，每个办公室的用户都可以访问最近的 Microsoft 网络位置和 Microsoft 365 订阅的资源。</span><span class="sxs-lookup"><span data-stu-id="7f135-128">Through the ISP, users in each office can reach the nearest Microsoft network location and the resources of your Microsoft 365 subscription.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a><span data-ttu-id="7f135-129">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="7f135-129">Phase 2: Identity</span></span>

<span data-ttu-id="7f135-130">组织内的每个员工都必须能够登录，这需要使用 Microsoft 365 企业版订阅的 Azure Active Directory (Azure AD) 租户中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7f135-130">Each of the employees of your organization must be able to sign in, which requires a user account in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="7f135-131">然后，组将用于包含用户帐户和其他组以进行通信或访问许可的资源，例如 SharePoint Online 网站或团队。</span><span class="sxs-lookup"><span data-stu-id="7f135-131">Groups are then used to contain user accounts and other groups to communicate or gain access to permissioned resources, such as a SharePoint Online site or a team.</span></span> 

### <a name="administrator-accounts"></a><span data-ttu-id="7f135-132">管理员帐户</span><span class="sxs-lookup"><span data-stu-id="7f135-132">Administrator accounts</span></span>

<span data-ttu-id="7f135-133">通过要求非常强的密码和多因素身份验证 (MFA) 来保护你的全局管理员用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7f135-133">Protect your global administrator user accounts by requiring very strong passwords and multi-factor authentication (MFA).</span></span> <span data-ttu-id="7f135-134">有关详细信息，请参阅[保护全局管理员帐户](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="7f135-134">See [Protect your Office 365 global administrator accounts](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts) for more information about configuration.</span></span>

<span data-ttu-id="7f135-135">如果贵组织需要高安全性并且你拥有 Microsoft 365 企业版 E5，请使用 Azure AD Privileged Identity Management 来启用实时管理员访问。</span><span class="sxs-lookup"><span data-stu-id="7f135-135">If your organization requires high security and you have Microsoft 365 Enterprise E5, use Azure AD Privileged Identity Management to enable just-in-time administrator access.</span></span> <span data-ttu-id="7f135-136">有关详细信息，请参阅[设置按需全局管理员](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators)。</span><span class="sxs-lookup"><span data-stu-id="7f135-136">See [Set up on-demand global administrators](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators) for more information.</span></span>

### <a name="recommendations-for-groups"></a><span data-ttu-id="7f135-137">有关组的建议</span><span class="sxs-lookup"><span data-stu-id="7f135-137">Recommendations for groups</span></span>

<span data-ttu-id="7f135-138">如果你具有本地 AD DS 域，请继续将 Microsoft 365 企业版中的这些组用作 Azure AD 中的组。</span><span class="sxs-lookup"><span data-stu-id="7f135-138">If you have an on-premises AD DS domain, continue to use those groups in Microsoft 365 Enterprise as groups in Azure AD.</span></span>

<span data-ttu-id="7f135-139">如果你没有本地 AD DS 域，请使用这些安全级别在 Azure AD 中创建安全组。</span><span class="sxs-lookup"><span data-stu-id="7f135-139">If you don’t have an on-premises AD DS domain, create security groups in Azure AD using these levels of security.</span></span>

| <span data-ttu-id="7f135-140">安全级别</span><span class="sxs-lookup"><span data-stu-id="7f135-140">Security level</span></span> | <span data-ttu-id="7f135-141">说明</span><span class="sxs-lookup"><span data-stu-id="7f135-141">Description</span></span> | <span data-ttu-id="7f135-142">示例</span><span class="sxs-lookup"><span data-stu-id="7f135-142">Examples</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="7f135-143">基线</span><span class="sxs-lookup"><span data-stu-id="7f135-143">Baseline</span></span> | <span data-ttu-id="7f135-144">这是保护数据以及访问数据的标识和设备的最低和默认标准。</span><span class="sxs-lookup"><span data-stu-id="7f135-144">This is a minimum and default  standard for protecting data and the identities and devices that access your data.</span></span> <BR><BR> <span data-ttu-id="7f135-145">这通常是大多数用户管理的大部分组织数据。</span><span class="sxs-lookup"><span data-stu-id="7f135-145">This is typically most of your organization’s data managed by most of your users.</span></span> | <span data-ttu-id="7f135-146">一线员工组，例如销售、营销、支持、管理和制造。</span><span class="sxs-lookup"><span data-stu-id="7f135-146">Groups for first line workers, such as sales, marketing, support, administration, and manufacturing.</span></span> |
| <span data-ttu-id="7f135-147">敏感</span><span class="sxs-lookup"><span data-stu-id="7f135-147">Sensitive</span></span> | <span data-ttu-id="7f135-148">这是对数据子集的额外保护，这种保护必须超出基线级别。</span><span class="sxs-lookup"><span data-stu-id="7f135-148">This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="7f135-149">这些组包含使用和创建敏感数据的用户，这些数据特定于相关部门以及不向所有人公开的项目。</span><span class="sxs-lookup"><span data-stu-id="7f135-149">These groups contain users that use and create sensitive data that is specific to departments and projects that are not meant to be available to everyone.</span></span> | <span data-ttu-id="7f135-150">负责开发未来产品的产品或营销团队</span><span class="sxs-lookup"><span data-stu-id="7f135-150">Product or marketing teams that are developing future products</span></span> |
| <span data-ttu-id="7f135-151">高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-151">Highly regulated</span></span> | <span data-ttu-id="7f135-152">这通常是对少量数据的最高级别的保护，这些数据是高度机密、视为知识产权或商业机密或必须遵守安全法规的数据。</span><span class="sxs-lookup"><span data-stu-id="7f135-152">Highly regulated: This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span> |  <span data-ttu-id="7f135-153">研究、法律和财务团队。</span><span class="sxs-lookup"><span data-stu-id="7f135-153">Research, legal, and financial teams.</span></span> <BR><BR> <span data-ttu-id="7f135-154">负责存储或使用客户或合作伙伴数据的团队。</span><span class="sxs-lookup"><span data-stu-id="7f135-154">Teams storing or using customer or partner data.</span></span> |

### <a name="hybrid-identity"></a><span data-ttu-id="7f135-155">混合标识</span><span class="sxs-lookup"><span data-stu-id="7f135-155">Hybrid identity</span></span>

<span data-ttu-id="7f135-156">如果你具有本地 AD DS 域，请在具有密码哈希同步 (PHS) 功能的服务器上配置 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="7f135-156">If you have an on-premises AD DS domain, configure Azure AD Connect on a server with password hash synchronization (PHS).</span></span> <span data-ttu-id="7f135-157">有关详细信息，请参阅[同步标识](identity-azure-ad-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="7f135-157">See [Synchronize identities](identity-azure-ad-connect.md) for more information.</span></span>

### <a name="more-secure-user-access-with-conditional-access-policies"></a><span data-ttu-id="7f135-158">通过条件访问策略实现更安全的用户访问</span><span class="sxs-lookup"><span data-stu-id="7f135-158">More secure user access with conditional access policies</span></span>

<span data-ttu-id="7f135-159">Azure AD 将会评估用户登录的条件，并且可以使用条件访问策略来授予或拒绝访问权限，并强制执行必须采取的进一步操作以完成登录。</span><span class="sxs-lookup"><span data-stu-id="7f135-159">Azure AD evaluates the conditions of user sign-ins and can use conditional access policies to grant or deny access and impose further actions that must be taken to complete the sign-in.</span></span> <span data-ttu-id="7f135-160">例如，如果 Azure AD 确定登录是在中或高风险条件下发生的，则可能要求用户执行 MFA 以完成登录。</span><span class="sxs-lookup"><span data-stu-id="7f135-160">For example, if Azure AD determines that the sign-in is happening under medium or high-risk conditions, it can require the user to perform MFA to complete the sign-in.</span></span>

<span data-ttu-id="7f135-161">你可以将条件访问策略应用于用户帐户或组。</span><span class="sxs-lookup"><span data-stu-id="7f135-161">You apply conditional access policies to user accounts or groups.</span></span> <span data-ttu-id="7f135-162">为了便于更轻松地分配条件访问策略，请在组织中创建以下 Azure AD 安全组：</span><span class="sxs-lookup"><span data-stu-id="7f135-162">To facilitate an easier assignment of conditional access policies, create these Azure AD security groups in your organization:</span></span>

- <span data-ttu-id="7f135-163">基线</span><span class="sxs-lookup"><span data-stu-id="7f135-163">Baseline</span></span>

  <span data-ttu-id="7f135-164">包含有权访问基线数据的用户的组或用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7f135-164">Contains the groups or user accounts for users with access to baseline data.</span></span>

- <span data-ttu-id="7f135-165">敏感</span><span class="sxs-lookup"><span data-stu-id="7f135-165">Sensitive</span></span>

  <span data-ttu-id="7f135-166">包含有权访问敏感数据的用户的组或用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7f135-166">Contains the groups or user accounts for users with access to sensitive data.</span></span>

- <span data-ttu-id="7f135-167">高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-167">HIGHLY-REGULATED</span></span>

  <span data-ttu-id="7f135-168">包含有权访问高度管控数据的用户的组或用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7f135-168">Contains the groups or user accounts for users with access to highly regulated data.</span></span>

- <span data-ttu-id="7f135-169">条件-访问-排除</span><span class="sxs-lookup"><span data-stu-id="7f135-169">COND-ACCESS-EXCLUDE</span></span>

  <span data-ttu-id="7f135-170">可用于临时从条件访问策略中排除用户的空组。</span><span class="sxs-lookup"><span data-stu-id="7f135-170">An empty group that you can use to temporarily exclude a user from conditional access policies.</span></span>

<span data-ttu-id="7f135-171">以下是要启用或创建的 Azure AD 条件访问策略的列表。</span><span class="sxs-lookup"><span data-stu-id="7f135-171">Here is the list of Azure AD conditional access policies to enable or create.</span></span>

| <span data-ttu-id="7f135-172">Azure AD 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="7f135-172">Azure AD conditional access policy</span></span> | <span data-ttu-id="7f135-173">应用到的组</span><span class="sxs-lookup"><span data-stu-id="7f135-173">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="7f135-174">基线策略：要求管理员执行 MFA</span><span class="sxs-lookup"><span data-stu-id="7f135-174">Baseline policy: Require MFA for admins</span></span> | <span data-ttu-id="7f135-175">此策略适用于管理员角色，因此不需要指定任何组。</span><span class="sxs-lookup"><span data-stu-id="7f135-175">This policy applies to admin roles, so no groups need to be specified.</span></span> <span data-ttu-id="7f135-176">只需要启用此策略。</span><span class="sxs-lookup"><span data-stu-id="7f135-176">This policy just needs to be enabled.</span></span> <span data-ttu-id="7f135-177">需要创建和启用所有后续策略。</span><span class="sxs-lookup"><span data-stu-id="7f135-177">All subsequent policies need to be created and enabled.</span></span> |
| <span data-ttu-id="7f135-178">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="7f135-178">Block clients that don't support modern authentication</span></span> | <span data-ttu-id="7f135-179">在策略设置中选择“所有用户”。</span><span class="sxs-lookup"><span data-stu-id="7f135-179">Select “All users” in the policy settings.</span></span> |
| <span data-ttu-id="7f135-180">当登录风险为中或高时需要执行 MFA（需要使用 Microsoft 365 企业版 E5）</span><span class="sxs-lookup"><span data-stu-id="7f135-180">Require MFA when sign-in risk is medium or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="7f135-181">基线</span><span class="sxs-lookup"><span data-stu-id="7f135-181">Baseline</span></span> |
| <span data-ttu-id="7f135-182">当登录风险为低、中或高时需要执行 MFA（需要使用 Microsoft 365 企业版 E5）</span><span class="sxs-lookup"><span data-stu-id="7f135-182">Require MFA when sign-in risk is low, medium, or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="7f135-183">敏感</span><span class="sxs-lookup"><span data-stu-id="7f135-183">Sensitive</span></span> |
| <span data-ttu-id="7f135-184">始终需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="7f135-184">Always require MFA</span></span> | <span data-ttu-id="7f135-185">高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-185">HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7f135-186">需要在 iOS 和 Android 设备上使用经过批准的应用</span><span class="sxs-lookup"><span data-stu-id="7f135-186">Require approved apps on iOS and Android devices</span></span> | <span data-ttu-id="7f135-187">基线、敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-187">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7f135-188">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="7f135-188">Require compliant PCs</span></span> | <span data-ttu-id="7f135-189">基线</span><span class="sxs-lookup"><span data-stu-id="7f135-189">Baseline</span></span> |
| <span data-ttu-id="7f135-190">需要兼容电脑以及 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="7f135-190">Require compliant PCs and iOS and Android devices</span></span> | <span data-ttu-id="7f135-191">敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-191">SENSITIVE, HIGHLY-REGULATED</span></span> |
|||

<span data-ttu-id="7f135-192">以下是要创建和启用的 Azure AD Identity Protection（需要使用 Microsoft 365 企业版 E5）用户风险策略。</span><span class="sxs-lookup"><span data-stu-id="7f135-192">Here is the Azure AD Identity Protection (requires Microsoft 365 Enterprise E5) user risk policy to create and enable.</span></span>

| <span data-ttu-id="7f135-193">Azure AD Identity Protection 用户风险策略</span><span class="sxs-lookup"><span data-stu-id="7f135-193">Azure AD Identity Protection user risk policy</span></span> | <span data-ttu-id="7f135-194">应用到的组</span><span class="sxs-lookup"><span data-stu-id="7f135-194">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="7f135-195">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="7f135-195">High risk users must change passwords</span></span> | <span data-ttu-id="7f135-196">在策略设置中选择“所有用户”。</span><span class="sxs-lookup"><span data-stu-id="7f135-196">Select “All users” in the policy settings.</span></span> |
|||

<span data-ttu-id="7f135-197">有关说明，请参阅[通用标识和设备访问策略](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7f135-197">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="groups-for-easier-management"></a><span data-ttu-id="7f135-198">通过组实现更轻松的管理</span><span class="sxs-lookup"><span data-stu-id="7f135-198">Groups for easier management</span></span>

<span data-ttu-id="7f135-199">以下是一些可以使你更轻松地进行组和许可管理的功能。</span><span class="sxs-lookup"><span data-stu-id="7f135-199">Here are some features that can make group and licensing management easier for you.</span></span>

| <span data-ttu-id="7f135-200">功能</span><span class="sxs-lookup"><span data-stu-id="7f135-200">Feature</span></span> | <span data-ttu-id="7f135-201">用途</span><span class="sxs-lookup"><span data-stu-id="7f135-201">Use</span></span> |
|:------|:-----|
| <span data-ttu-id="7f135-202">自助服务组管理</span><span class="sxs-lookup"><span data-stu-id="7f135-202">Self-service group management</span></span> | <span data-ttu-id="7f135-203">允许组所有者而不是 IT 人员管理 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="7f135-203">Allow management of Azure AD groups by group owners instead of IT staff.</span></span> <span data-ttu-id="7f135-204">有关详细信息，请参阅[自助服务组管理](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups)。</span><span class="sxs-lookup"><span data-stu-id="7f135-204">See [Self-service group management](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups) for more information.</span></span> |
| <span data-ttu-id="7f135-205">动态组成员身份</span><span class="sxs-lookup"><span data-stu-id="7f135-205">Dynamic group membership</span></span> | <span data-ttu-id="7f135-206">根据用户帐户属性（如“部门”或“国家/地区”）配置在 Azure AD 组中自动添加或删除用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7f135-206">Configure automatic addition or removal of user accounts from Azure AD groups based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="7f135-207">关详细信息，请参阅[动态组成员身份](identity-self-service-group-management.md#set-up-dynamic-group-membership)。</span><span class="sxs-lookup"><span data-stu-id="7f135-207">See [Dynamic group membership](identity-self-service-group-management.md#set-up-dynamic-group-membership) for more information.</span></span> |
| <span data-ttu-id="7f135-208">基于组的许可</span><span class="sxs-lookup"><span data-stu-id="7f135-208">Group-based licensing</span></span> | <span data-ttu-id="7f135-209">使用组成员身份自动为用户帐户分配或取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="7f135-209">Use group membership to automatically assign or unassign licenses to user accounts.</span></span> <span data-ttu-id="7f135-210">有关详细信息，请参阅[基于组的许可](identity-self-service-group-management.md#set-up-automatic-licensing)。</span><span class="sxs-lookup"><span data-stu-id="7f135-210">See [Group-based licensing](identity-self-service-group-management.md#set-up-automatic-licensing) for more information.</span></span> |
|  |  |

<span data-ttu-id="7f135-211">如果你使用的是基于组的许可，请创建一个名为“已许可”的组，以包含分配了 Microsoft 365 企业版许可证的用户帐户名。</span><span class="sxs-lookup"><span data-stu-id="7f135-211">If you are using group-based licensing, create a group named LICENSED to contain user account names that are assigned a Microsoft 365 Enterprise license.</span></span>

### <a name="monitor-user-access"></a><span data-ttu-id="7f135-212">监视用户访问</span><span class="sxs-lookup"><span data-stu-id="7f135-212">Monitor user access</span></span>

<span data-ttu-id="7f135-213">如果你具有 Microsoft 365 企业版 E5，则可以使用 Azure AD Identity Protection 来监视和分析用户登录是否存在凭据泄露。</span><span class="sxs-lookup"><span data-stu-id="7f135-213">If you have Microsoft 365 Enterprise E5, you can use Azure AD Identity Protection to monitor and analyze user sign-ins for credential compromise.</span></span> <span data-ttu-id="7f135-214">有关详细信息，请参阅[防范凭据泄露](identity-multi-factor-authentication.md#protect-against-credential-compromise)。</span><span class="sxs-lookup"><span data-stu-id="7f135-214">See [Protect against credential compromise](identity-multi-factor-authentication.md#protect-against-credential-compromise) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="7f135-215">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="7f135-215">Your configuration so far</span></span>

<span data-ttu-id="7f135-216">以下是混合标识的标识阶段的可视摘要，其中突出显示了新元素。</span><span class="sxs-lookup"><span data-stu-id="7f135-216">Here is a visual summary of the Identity phase for hybrid identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
<span data-ttu-id="7f135-217">新的和突出显示的标识元素包括：</span><span class="sxs-lookup"><span data-stu-id="7f135-217">The new and highlighted identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | <span data-ttu-id="7f135-218">具有用户帐户和组的本地 AD DS 域。</span><span class="sxs-lookup"><span data-stu-id="7f135-218">An on-premises AD DS domain with user accounts and groups.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | <span data-ttu-id="7f135-219">运行 Azure AD Connect 的基于 Windows 的服务器。</span><span class="sxs-lookup"><span data-stu-id="7f135-219">A Windows-based server running Azure AD Connect.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | <span data-ttu-id="7f135-220">Azure AD 中的 AD DS 帐户和组的同步集。</span><span class="sxs-lookup"><span data-stu-id="7f135-220">The synchronized set of AD DS accounts and groups in Azure AD.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="7f135-221">用于身份验证、保护全局帐户以及更轻松地管理组和许可证的 Azure AD 设置。</span><span class="sxs-lookup"><span data-stu-id="7f135-221">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="7f135-222">Azure AD 条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="7f135-222">Azure AD conditional access policies.</span></span> |
|||

## <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="7f135-223">阶段 3：Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="7f135-223">Phase 3: Windows 10 Enterprise</span></span>

<span data-ttu-id="7f135-224">为确保将 Windows 10 企业版设备集成到 Microsoft 365 的标识和安全基础结构中，可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="7f135-224">To ensure that your Windows 10 Enterprise devices are integrated into the identity and security infrastructure of Microsoft 365, here are your options:</span></span>

- <span data-ttu-id="7f135-225">仅限云（你没有本地 AD DS 域）</span><span class="sxs-lookup"><span data-stu-id="7f135-225">Cloud-only (you do not have on-premises AD DS domain)</span></span>

  <span data-ttu-id="7f135-226">将每台 Windows 10 企业版设备加入订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="7f135-226">Join each Windows 10 Enterprise device to the Azure AD tenant of your subscription.</span></span>

  <span data-ttu-id="7f135-227">有关详细信息，请参阅[将工作设备加入组织的网络](https://docs.microsoft.com/zh-CN/azure/active-directory/user-help/user-help-join-device-on-network)。</span><span class="sxs-lookup"><span data-stu-id="7f135-227">See [Join your work device to your organization's network](https://docs.microsoft.com/en-us/azure/active-directory/user-help/user-help-join-device-on-network) for more information.</span></span>

- <span data-ttu-id="7f135-228">混合（你具有本地 AD DS 域）</span><span class="sxs-lookup"><span data-stu-id="7f135-228">Hybrid (you have on-premises AD DS domain)</span></span>

  <span data-ttu-id="7f135-229">对于已加入 AD DS 域的每台现有的 Windows 10 企业版设备，请将它们加入 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="7f135-229">For each existing Windows 10 Enterprise device already joined to your AD DS domain, join them to the Azure AD tenant.</span></span> <span data-ttu-id="7f135-230">有关说明，请参阅[如何配置联接到混合 Azure Active Directory 的设备](https://go.microsoft.com/fwlink/p/?linkid=872870)。</span><span class="sxs-lookup"><span data-stu-id="7f135-230">See [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870) for the instructions.</span></span>

  <span data-ttu-id="7f135-231">对于每台新的 Windows 10 企业版设备，请将它们加入 AD DS 域，然后将它们加入 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="7f135-231">For each new Windows 10 Enterprise device, join them to your AD DS domain, and then join them to the Azure AD tenant.</span></span>

  <span data-ttu-id="7f135-232">对于每台 Windows 10 企业版设备，请注册它们以进行移动设备管理。</span><span class="sxs-lookup"><span data-stu-id="7f135-232">For each Windows 10 Enterprise device, enroll them for mobile device management.</span></span> <span data-ttu-id="7f135-233">有关说明，请参阅[使用组策略注册带有 Intune 的 Windows 10 设备](https://go.microsoft.com/fwlink/p/?linkid=872871)。</span><span class="sxs-lookup"><span data-stu-id="7f135-233">See [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for the instructions.</span></span>

<span data-ttu-id="7f135-234">安装并加入后，每台 Windows 10 企业版设备都会自动从 Windows Update for Business 云服务安装更新。</span><span class="sxs-lookup"><span data-stu-id="7f135-234">Once installed and joined, each Windows 10 Enterprise device automatically installs updates from the Windows Update for Business cloud service.</span></span> <span data-ttu-id="7f135-235">在非企业组织中，通常无需设置基础结构即可分发和安装更新。</span><span class="sxs-lookup"><span data-stu-id="7f135-235">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute and install updates.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="7f135-236">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="7f135-236">Your configuration so far</span></span>

<span data-ttu-id="7f135-237">以下是 Windows 10 企业版阶段的可视摘要，其中突出显示了新元素。</span><span class="sxs-lookup"><span data-stu-id="7f135-237">Here is a visual summary of the Windows 10 Enterprise phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
<span data-ttu-id="7f135-238">新的和突出显示的 Windows 10 企业版元素包括：</span><span class="sxs-lookup"><span data-stu-id="7f135-238">The new and highlighted Windows 10 Enterprise elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | <span data-ttu-id="7f135-239">Windows 设备上安装的 Windows 10 企业版，以本地笔记本电脑为例。</span><span class="sxs-lookup"><span data-stu-id="7f135-239">Windows 10 Enterprise installed on Windows devices, with the on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | <span data-ttu-id="7f135-240">批量许可服务中心（它为 Windows 10 企业版的新安装提供映像）和 Windows Update for Business 服务（它提供最新的更新）。</span><span class="sxs-lookup"><span data-stu-id="7f135-240">The Volume Licensing Service Center, which provides images for new installations of Windows 10 Enterprise, and the Windows Update for Business service, which provides the latest updates.</span></span> |
|||

## <a name="phase-4-office-365-proplus"></a><span data-ttu-id="7f135-241">阶段 4：Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="7f135-241">Phase 4: Office 365 ProPlus</span></span>

<span data-ttu-id="7f135-242">Microsoft 365 企业版包括 Office 365 专业增强版，即 Microsoft Office 的订阅版本。</span><span class="sxs-lookup"><span data-stu-id="7f135-242">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Microsoft Office.</span></span> <span data-ttu-id="7f135-243">与 Office 2016 或 Office 2019 一样，Office 365 专业增强版也直接安装在客户端设备上。</span><span class="sxs-lookup"><span data-stu-id="7f135-243">Like Office 2016 or Office 2019, Office 365 ProPlus is installed directly on your client devices.</span></span> <span data-ttu-id="7f135-244">但是，Office 365 专业增强版会定期接收新功能。</span><span class="sxs-lookup"><span data-stu-id="7f135-244">However, Office 365 ProPlus receives new features on a regular basis.</span></span> <span data-ttu-id="7f135-245">有关详细信息，请参阅[关于企业中的 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="7f135-245">See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

<span data-ttu-id="7f135-246">对于非企业组织，请在设备上手动安装 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="7f135-246">For your non-enterprise organization, manually install Office 365 ProPlus on devices.</span></span> <span data-ttu-id="7f135-247">这可以作为准备使用新设备的一部分来完成，也可以由用户在载入过程中完成。</span><span class="sxs-lookup"><span data-stu-id="7f135-247">This can be done as part of preparing a new device for use, or it can be done by the user as part of their onboarding process.</span></span>

<span data-ttu-id="7f135-248">在任何一种情况下，管理员或用户都需要登录 Office 365 门户：https://portal.office.com。</span><span class="sxs-lookup"><span data-stu-id="7f135-248">In either case, the administrator or the user signs in to the Office 365 portal at https://portal.office.com.</span></span> <span data-ttu-id="7f135-249">在“**Microsoft Office 家庭版**”选项卡上，单击“**安装 Office**”并逐步完成安装过程。</span><span class="sxs-lookup"><span data-stu-id="7f135-249">On the **Microsoft Office Home** tab, click **Install Office** and step through the installation process.</span></span>

<span data-ttu-id="7f135-250">安装它的每台计算机每月都会下载 Office 365 专业增强版的功能更新。</span><span class="sxs-lookup"><span data-stu-id="7f135-250">Feature updates to Office 365 ProPlus are downloaded monthly by each computer on which it is installed.</span></span> <span data-ttu-id="7f135-251">在非企业组织中，通常无需设置基础结构即可分发 Office 365 专业增强版更新。</span><span class="sxs-lookup"><span data-stu-id="7f135-251">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute Office 365 ProPlus updates.</span></span> 

### <a name="your-configuration-so-far"></a><span data-ttu-id="7f135-252">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="7f135-252">Your configuration so far</span></span>

<span data-ttu-id="7f135-253">以下是 Office 365 专业增强版阶段的可视摘要，其中突出显示了新元素。</span><span class="sxs-lookup"><span data-stu-id="7f135-253">Here is a visual summary of the Office 365 ProPlus phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
<span data-ttu-id="7f135-254">新的和突出显示的 Office 365 专业增强版元素包括：</span><span class="sxs-lookup"><span data-stu-id="7f135-254">The new and highlighted Office 365 ProPlus elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | <span data-ttu-id="7f135-255">设备上安装的 Office 365 专业增强版，以本地笔记本电脑为例。</span><span class="sxs-lookup"><span data-stu-id="7f135-255">Office 365 ProPlus installed on devices, with the on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | <span data-ttu-id="7f135-256">Office 365 专业增强版的 Office 内容交付网络 (CDN)，设备可以通过它访问 Office 365 专业增强版更新。</span><span class="sxs-lookup"><span data-stu-id="7f135-256">The Office Content Delivery Network (CDN) for Office 365 ProPlus, which devices access for Office 365 ProPlus updates.</span></span> |
|||

## <a name="phase-5-mobile-device-management"></a><span data-ttu-id="7f135-257">阶段 5：移动设备管理</span><span class="sxs-lookup"><span data-stu-id="7f135-257">Phase 5: Mobile device management</span></span>

<span data-ttu-id="7f135-258">Microsoft 365 企业版包含用于移动设备管理的 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="7f135-258">Microsoft 365 Enterprise includes Microsoft Intune for mobile device management.</span></span> <span data-ttu-id="7f135-259">使用 Intune，你可以管理 iOS、Android、macOS 和 Windows 设备，以保护对组织资源（包括数据）的访问。</span><span class="sxs-lookup"><span data-stu-id="7f135-259">With Intune, you can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="7f135-260">Intune 可与 Azure AD 的用户、组和计算机帐户集成。</span><span class="sxs-lookup"><span data-stu-id="7f135-260">Intune integrates with the users, groups, and computer accounts of Azure AD.</span></span>

<span data-ttu-id="7f135-261">Intune 提供了两种类型的移动设备管理：</span><span class="sxs-lookup"><span data-stu-id="7f135-261">Intune provides two types of mobile device management:</span></span>

- <span data-ttu-id="7f135-262">在 Intune 中注册设备后进行移动设备管理 (MDM)。</span><span class="sxs-lookup"><span data-stu-id="7f135-262">Mobile device management (MDM) is when devices get enrolled in Intune.</span></span> <span data-ttu-id="7f135-263">注册后，它们将成为受管理设备，可以接收组织使用的策略、规则和设置。</span><span class="sxs-lookup"><span data-stu-id="7f135-263">Once enrolled, they are managed devices and can receive the policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="7f135-264">这些类型的设备通常由贵组织拥有并分发给你的员工。</span><span class="sxs-lookup"><span data-stu-id="7f135-264">These types of devices are typically owned by your organization and issued to your employees.</span></span>

- <span data-ttu-id="7f135-265">拥有个人设备的用户可能不想注册他们的设备，也不希望由 Intune 使用你的策略和设置进行管理。</span><span class="sxs-lookup"><span data-stu-id="7f135-265">Users with their own personal devices may not want to enroll their devices or be managed by Intune with your policies and settings.</span></span> <span data-ttu-id="7f135-266">但是，你仍需要保护组织的资源和数据。</span><span class="sxs-lookup"><span data-stu-id="7f135-266">However, you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="7f135-267">在这种情况下，你可以使用移动应用程序管理 (MAM) 来保护你的应用。</span><span class="sxs-lookup"><span data-stu-id="7f135-267">For this scenario, you can protect your apps using mobile application management (MAM).</span></span> <span data-ttu-id="7f135-268">这些类型的设备称为自带设备 (BYOD)，通常由你的员工拥有。</span><span class="sxs-lookup"><span data-stu-id="7f135-268">These types of devices are referred to as bring your own devices (BYOD) and are typically owned by your employees.</span></span> 

<span data-ttu-id="7f135-269">Intune 策略可以强制执行设备合规性和应用保护。</span><span class="sxs-lookup"><span data-stu-id="7f135-269">Intune policies can enforce device compliance and app protection.</span></span> <span data-ttu-id="7f135-270">以下是要创建的 Intune 策略的列表。</span><span class="sxs-lookup"><span data-stu-id="7f135-270">Here is the list of Intune policies to create.</span></span>

| <span data-ttu-id="7f135-271">Intune 策略</span><span class="sxs-lookup"><span data-stu-id="7f135-271">Intune policies</span></span> | <span data-ttu-id="7f135-272">应用到的组</span><span class="sxs-lookup"><span data-stu-id="7f135-272">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="7f135-273">Windows 的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="7f135-273">Device compliance policy for Windows</span></span> | <span data-ttu-id="7f135-274">基线、敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-274">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7f135-275">iOS 的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="7f135-275">Device compliance policy for iOS</span></span> | <span data-ttu-id="7f135-276">敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-276">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7f135-277">macOS 的设备合规性</span><span class="sxs-lookup"><span data-stu-id="7f135-277">Device compliance for macOS</span></span> | <span data-ttu-id="7f135-278">敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-278">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7f135-279">Android 和 Android Enterprise 的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="7f135-279">Device compliance policy for Android and Android Enterprise</span></span> | <span data-ttu-id="7f135-280">敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-280">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7f135-281">iOS 的应用保护策略</span><span class="sxs-lookup"><span data-stu-id="7f135-281">App protection policy for iOS</span></span> | <span data-ttu-id="7f135-282">基线、敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-282">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7f135-283">macOS 的应用保护策略</span><span class="sxs-lookup"><span data-stu-id="7f135-283">App protection policy for macOS</span></span> | <span data-ttu-id="7f135-284">基线、敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-284">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="7f135-285">Android 和 Android Enterprise 的应用保护策略</span><span class="sxs-lookup"><span data-stu-id="7f135-285">App protection policy for Android and Android Enterprise</span></span> | <span data-ttu-id="7f135-286">基线、敏感、高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-286">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
|||
    
<span data-ttu-id="7f135-287">有关说明，请参阅[通用标识和设备访问策略](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7f135-287">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="7f135-288">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="7f135-288">Your configuration so far</span></span>

<span data-ttu-id="7f135-289">以下是移动设备管理阶段的可视摘要，其中突出显示了新元素。</span><span class="sxs-lookup"><span data-stu-id="7f135-289">Here is a visual summary of the Mobile Device Management phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
<span data-ttu-id="7f135-290">新的和突出显示的移动设备管理元素包括：</span><span class="sxs-lookup"><span data-stu-id="7f135-290">The new and highlighted mobile device management elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | <span data-ttu-id="7f135-291">在 Intune 中注册的设备，以运行 Windows 10 企业版的本地笔记本电脑为例。</span><span class="sxs-lookup"><span data-stu-id="7f135-291">Devices that are enrolled in Intune, showing the on-premises laptop running Windows 10 Enterprise as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | <span data-ttu-id="7f135-292">Intune 的设备合规性和应用保护策略。</span><span class="sxs-lookup"><span data-stu-id="7f135-292">Intune policies for device compliance and app protection.</span></span> |
|||

## <a name="phase-6-information-protection"></a><span data-ttu-id="7f135-293">阶段 6：信息保护</span><span class="sxs-lookup"><span data-stu-id="7f135-293">Phase 6: Information protection</span></span>

<span data-ttu-id="7f135-294">Microsoft 365 企业版具有许多信息保护功能，允许你通过应用不同级别的治理、安全性和保护来区别对待数据分类。</span><span class="sxs-lookup"><span data-stu-id="7f135-294">Microsoft 365 Enterprise has a host of information protection features that allow you treat classifications of data differently by applying different levels of governance, security, and protection.</span></span> 

<span data-ttu-id="7f135-295">例如，大多数员工与他们所处理的文档之间的正常对应关系都需要特定的基线保护级别。</span><span class="sxs-lookup"><span data-stu-id="7f135-295">For example, normal correspondence between most employees and the documents that they work on need a certain baseline level of protection.</span></span> <span data-ttu-id="7f135-296">财务记录、客户数据和你的知识产权需要更高级别的保护。</span><span class="sxs-lookup"><span data-stu-id="7f135-296">Financial records, customer data, and your intellectual property need a higher level of protection.</span></span>

<span data-ttu-id="7f135-297">信息保护策略的第一步是确定保护级别。</span><span class="sxs-lookup"><span data-stu-id="7f135-297">The first step to an information protection strategy is to determine the levels of protection.</span></span> <span data-ttu-id="7f135-298">许多组织都会使用已用于条件访问策略的保护级别：</span><span class="sxs-lookup"><span data-stu-id="7f135-298">Many organizations use these levels, which are already being used for conditional access policies:</span></span>

- <span data-ttu-id="7f135-299">基线</span><span class="sxs-lookup"><span data-stu-id="7f135-299">Baseline</span></span>

  <span data-ttu-id="7f135-300">示例包括正常的业务通信（电子邮件）和供管理、销售和支持工作人员使用的文件。</span><span class="sxs-lookup"><span data-stu-id="7f135-300">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span>

- <span data-ttu-id="7f135-301">敏感</span><span class="sxs-lookup"><span data-stu-id="7f135-301">Sensitive</span></span>

  <span data-ttu-id="7f135-302">示例包括财务和法律信息，以及新产品或服务的研发数据。</span><span class="sxs-lookup"><span data-stu-id="7f135-302">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span>

- <span data-ttu-id="7f135-303">高度管控</span><span class="sxs-lookup"><span data-stu-id="7f135-303">Highly regulated</span></span>

  <span data-ttu-id="7f135-304">示例包括客户和合作伙伴的个人身份信息以及组织的知识产权。</span><span class="sxs-lookup"><span data-stu-id="7f135-304">Examples include customer and partner personally identifiable information and your organization’s intellectual property.</span></span>

<span data-ttu-id="7f135-305">基于这些数据安全级别，下一步是确定并实施：</span><span class="sxs-lookup"><span data-stu-id="7f135-305">Based on these levels of data security, the next step is to identify and implement:</span></span>

- <span data-ttu-id="7f135-306">自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="7f135-306">Custom sensitive information types</span></span>

  <span data-ttu-id="7f135-307">Microsoft 365 提供了各种敏感信息类型，例如健康服务和信用卡号。</span><span class="sxs-lookup"><span data-stu-id="7f135-307">Microsoft 365 supplies a wide selection of sensitive information types, such as health service and credit card numbers.</span></span> <span data-ttu-id="7f135-308">如果你未在 Microsoft 365 提供的列表中找到所需的类型，则可以创建自己的信息类型。</span><span class="sxs-lookup"><span data-stu-id="7f135-308">If you do not find one that you need in the Microsoft 365-supplied list, you can create your own.</span></span>

- <span data-ttu-id="7f135-309">保留标签</span><span class="sxs-lookup"><span data-stu-id="7f135-309">Retention labels</span></span>

  <span data-ttu-id="7f135-310">为了遵守组织政策和区域法规，你可能必须指定特定类型的文档或含有特定内容的文档应保留多长时间。</span><span class="sxs-lookup"><span data-stu-id="7f135-310">To comply with organization policies and regional regulations, you might have to specify how long specific types of documents or documents with specific contents should be retained.</span></span> <span data-ttu-id="7f135-311">你可以使用保留标签为电子邮件和文档实施此策略。</span><span class="sxs-lookup"><span data-stu-id="7f135-311">You can implement this for email and document using retention labels.</span></span>

- <span data-ttu-id="7f135-312">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="7f135-312">Sensitivity labels</span></span>

  <span data-ttu-id="7f135-313">你可以使用指定的敏感度标签来标记电子邮件或文档，以便能够应用其他安全级别。</span><span class="sxs-lookup"><span data-stu-id="7f135-313">You can label email or documents with a named sensitivity label so that the additional levels of security can be applied.</span></span> <span data-ttu-id="7f135-314">示例包括水印、加密和权限，它们指定允许谁访问电子邮件或文档以及允许他们执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="7f135-314">Examples are watermarks, encryption, and permissions, which specify who is allowed to access the email or document and what they are allowed to do.</span></span>

<span data-ttu-id="7f135-315">有关详细信息，请参阅 [Microsoft 365 分类类型](infoprotect-configure-classification.md#microsoft-365-classification-types)。</span><span class="sxs-lookup"><span data-stu-id="7f135-315">See [Microsoft 365 classification types](infoprotect-configure-classification.md#microsoft-365-classification-types) for more information.</span></span>

<span data-ttu-id="7f135-316">如果你使用具有权限的敏感度标签，则可能必须创建其他 Azure AD 安全组，以定义允许谁对电子邮件和文档执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="7f135-316">If you use sensitivity labels with permissions, you might have to create additional Azure AD security groups to define who is allowed to do what with email and documents.</span></span> 

<span data-ttu-id="7f135-317">例如，你需要创建一个“研究”敏感性标签来保护研究团队的电子邮件和文档。</span><span class="sxs-lookup"><span data-stu-id="7f135-317">For example, you need to create a RESEARCH sensitivity label to protect the email and documents of your research team.</span></span> <span data-ttu-id="7f135-318">你确定某些研究人员必须能够更改标有“研究”敏感度标签的文档，而其他非研究员工只能查看标有“研究”敏感度标签的文档。</span><span class="sxs-lookup"><span data-stu-id="7f135-318">You determine that some researchers must have the ability to change documents marked with the RESEARCH sensitivity label and other non-research employees need have the ability to only view documents marked with the RESEARCH sensitivity label.</span></span> <span data-ttu-id="7f135-319">这意味着你需要创建和管理两个附加组：</span><span class="sxs-lookup"><span data-stu-id="7f135-319">This means you need to create and manage two additional groups:</span></span>

- <span data-ttu-id="7f135-320">研究-全部</span><span class="sxs-lookup"><span data-stu-id="7f135-320">RESEARCH-ALL</span></span>
- <span data-ttu-id="7f135-321">研究-查看</span><span class="sxs-lookup"><span data-stu-id="7f135-321">RESEARCH-VIEW</span></span>

<span data-ttu-id="7f135-322">这些组及其权限将成为“研究”敏感度标签配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="7f135-322">These groups and their permissions become part of the RESEARCH sensitivity label's configuration.</span></span>

<span data-ttu-id="7f135-323">对于已配置基于组的权限的敏感度标签，你必须管理这些组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="7f135-323">For sensitivity labels configured with group-based permissions, you must manage the membership of these groups.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="7f135-324">你的当前配置</span><span class="sxs-lookup"><span data-stu-id="7f135-324">Your configuration so far</span></span>

<span data-ttu-id="7f135-325">以下是信息保护阶段的可视摘要，其中突出显示了新元素。</span><span class="sxs-lookup"><span data-stu-id="7f135-325">Here is a visual summary of the Information Protection phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
<span data-ttu-id="7f135-326">新的和突出显示的信息保护元素包括：</span><span class="sxs-lookup"><span data-stu-id="7f135-326">The new and highlighted information protection elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | <span data-ttu-id="7f135-327">用户可以应用于文档的三个安全级别的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="7f135-327">Sensitivity labels for the three levels of security that users can apply to documents.</span></span> |
|||

<span data-ttu-id="7f135-328">未显示保留标签和自定义信息类型。</span><span class="sxs-lookup"><span data-stu-id="7f135-328">Retention labels and custom information types are not shown.</span></span>

## <a name="onboarding"></a><span data-ttu-id="7f135-329">载入</span><span class="sxs-lookup"><span data-stu-id="7f135-329">Onboarding</span></span>

<span data-ttu-id="7f135-330">使用此基础结构，你可以使用这些流程为 Microsoft 365 企业版载入员工。</span><span class="sxs-lookup"><span data-stu-id="7f135-330">With this infrastructure, you can onboard an employee for Microsoft 365 Enterprise with these processes.</span></span>

### <a name="a-new-windows-10-enterprise-device"></a><span data-ttu-id="7f135-331">新的 Windows 10 企业版设备</span><span class="sxs-lookup"><span data-stu-id="7f135-331">A new Windows 10 Enterprise device</span></span>

<span data-ttu-id="7f135-332">在为员工提供新的 Windows 10 企业版设备之前：</span><span class="sxs-lookup"><span data-stu-id="7f135-332">Before giving an employee a new Windows 10 Enterprise device:</span></span>

- <span data-ttu-id="7f135-333">对于仅限云标识</span><span class="sxs-lookup"><span data-stu-id="7f135-333">For cloud-only identity</span></span>

  <span data-ttu-id="7f135-334">将设备加入 Microsoft 365 企业版订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="7f135-334">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>

- <span data-ttu-id="7f135-335">对于混合标识</span><span class="sxs-lookup"><span data-stu-id="7f135-335">For hybrid identity</span></span>

  <span data-ttu-id="7f135-336">依次将设备加入 AD DS 和 Azure AD 租户，然后在 Intune 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="7f135-336">Join the device to your AD DS, join the device to your Azure AD tenant, and then enroll the device in Intune.</span></span>

### <a name="existing-employee-with-an-ad-ds-user-account"></a><span data-ttu-id="7f135-337">具有 AD DS 用户帐户的现有员工</span><span class="sxs-lookup"><span data-stu-id="7f135-337">Existing employee with an AD DS user account</span></span>

<span data-ttu-id="7f135-338">在使用混合标识时，作为组织的初始载入的一部分，请将 AD DS 用户帐户添加到这些 Azure AD 组：</span><span class="sxs-lookup"><span data-stu-id="7f135-338">As part of the initial onboarding for your organization when using hybrid identity, add the AD DS user account to these Azure AD groups:</span></span>

- <span data-ttu-id="7f135-339">已许可</span><span class="sxs-lookup"><span data-stu-id="7f135-339">Licensed</span></span>
- <span data-ttu-id="7f135-340">相应的 AD DS 或 Azure AD 安全组，它们是“基线”、“敏感”和“高度管控”Azure AD 组的成员</span><span class="sxs-lookup"><span data-stu-id="7f135-340">The appropriate AD DS or Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="7f135-341">敏感度标签组（根据需要）</span><span class="sxs-lookup"><span data-stu-id="7f135-341">Sensitivity label groups (as needed)</span></span>

<span data-ttu-id="7f135-342">现有员工应已添加到相应的工作组、部门和区域 AD DS 组。</span><span class="sxs-lookup"><span data-stu-id="7f135-342">The existing employee should already be added to the appropriate workgroup, departmental, and regional AD DS groups.</span></span>

### <a name="new-employee-with-cloud-only-user-account"></a><span data-ttu-id="7f135-343">使用仅限云用户帐户的新员工</span><span class="sxs-lookup"><span data-stu-id="7f135-343">New employee with cloud-only user account</span></span>

<span data-ttu-id="7f135-344">在使用仅限云标识时，作为组织的初始载入的一部分，请将新用户帐户添加到这些组：</span><span class="sxs-lookup"><span data-stu-id="7f135-344">As part of the initial onboarding for your organization when using cloud-only identity, add the new user account to these groups:</span></span>

- <span data-ttu-id="7f135-345">已许可</span><span class="sxs-lookup"><span data-stu-id="7f135-345">Licensed</span></span>
- <span data-ttu-id="7f135-346">相应的 Azure AD 安全组，它们是“基线”、“敏感”和“高度管控”Azure AD 组的成员</span><span class="sxs-lookup"><span data-stu-id="7f135-346">The appropriate Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="7f135-347">工作组、部门和区域组</span><span class="sxs-lookup"><span data-stu-id="7f135-347">Workgroup, departmental, and regional groups</span></span>
- <span data-ttu-id="7f135-348">敏感度标签组（根据需要）</span><span class="sxs-lookup"><span data-stu-id="7f135-348">Sensitivity label groups (as needed)</span></span>

### <a name="initial-sign-in-to-microsoft-365"></a><span data-ttu-id="7f135-349">初次登录 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f135-349">Initial sign-in to Microsoft 365</span></span>

<span data-ttu-id="7f135-350">当具有 AD DS 用户帐户的新员工或现有员工首次登录 Microsoft 365 时，请指示他们：</span><span class="sxs-lookup"><span data-stu-id="7f135-350">For the first time new employees or existing employees with an AD DS user account sign in to Microsoft 365, instruct them to:</span></span>

1. <span data-ttu-id="7f135-351">使用其用户帐户凭据登录其设备。</span><span class="sxs-lookup"><span data-stu-id="7f135-351">Sign into their devices with their user account credentials.</span></span>
2. <span data-ttu-id="7f135-352">使用浏览器登录 Office 365 门户：https://portal.office.com。</span><span class="sxs-lookup"><span data-stu-id="7f135-352">Using a browser on your local computer, sign in to the https://portal.office.com using your global administrator account.</span></span>
3. <span data-ttu-id="7f135-353">在“**Office 365 家庭版**”选项卡中，单击“**安装 Office**”以在设备上安装 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="7f135-353">From the **Office 365 Home** tab, click **Install Office** to install Office 365 ProPlus on their device.</span></span>

## <a name="end-results"></a><span data-ttu-id="7f135-354">结果</span><span class="sxs-lookup"><span data-stu-id="7f135-354">End results</span></span>

<span data-ttu-id="7f135-355">以下是为非企业组织配置 Microsoft 365 企业版基础结构的结果。</span><span class="sxs-lookup"><span data-stu-id="7f135-355">Here are the results of configuring the Microsoft 365 Enterprise foundation infrastructure for your non-enterprise organization.</span></span>

### <a name="infrastructure-results"></a><span data-ttu-id="7f135-356">基础结构结果</span><span class="sxs-lookup"><span data-stu-id="7f135-356">Infrastructure results</span></span>

<span data-ttu-id="7f135-357">在构建和配置 Microsoft 365 企业版基础结构之后，你应该：</span><span class="sxs-lookup"><span data-stu-id="7f135-357">After the build-out and configuration of your Microsoft 365 Enterprise infrastructure, you should have:</span></span>

- <span data-ttu-id="7f135-358">为每个办公室建立了本地 Internet 连接，其具有由使用区域性本地 DNS 服务器的 ISP 提供的足够带宽。</span><span class="sxs-lookup"><span data-stu-id="7f135-358">A local Internet connection for each of your offices with sufficient bandwidth supplied by an ISP that uses a regionally local DNS server.</span></span>
- <span data-ttu-id="7f135-359">对于混合标识，具有在服务器上运行的 Azure AD Connect，该服务器可将你的本地 AD DS 域与 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="7f135-359">For hybrid identity, Azure AD Connect running on a server that synchronizes your on-premises AD DS domain with your Azure AD tenant.</span></span>
- <span data-ttu-id="7f135-360">这些组：</span><span class="sxs-lookup"><span data-stu-id="7f135-360">These universal groups include:</span></span>
  - <span data-ttu-id="7f135-361">已许可</span><span class="sxs-lookup"><span data-stu-id="7f135-361">Licensed</span></span>
  - <span data-ttu-id="7f135-362">条件-访问-排除</span><span class="sxs-lookup"><span data-stu-id="7f135-362">COND-ACCESS-EXCLUDE</span></span>
  - <span data-ttu-id="7f135-363">相应的 AD DS 或 Azure AD 安全组，它们也是“基线”、“敏感”和“高度管控”Azure AD 组的成员</span><span class="sxs-lookup"><span data-stu-id="7f135-363">The appropriate AD DS or Azure AD security groups that are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span> 
  - <span data-ttu-id="7f135-364">工作组、部门和区域组</span><span class="sxs-lookup"><span data-stu-id="7f135-364">Workgroup, departmental, and regional groups</span></span>
  - <span data-ttu-id="7f135-365">敏感度标签组（根据需要）</span><span class="sxs-lookup"><span data-stu-id="7f135-365">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="7f135-366">Azure AD 登录条件访问策略，它们使用“基线”、“敏感”、“高度管控”和“条件-访问-排除”Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="7f135-366">Azure AD sign-in conditional access policies that use the BASELINE, SENSITIVE, and HIGHLY-REGULATED, and COND-ACCESS-EXCLUDE Azure AD groups.</span></span>
- <span data-ttu-id="7f135-367">Intune 应用程序和设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="7f135-367">Intune application and device compliance policies.</span></span>
- <span data-ttu-id="7f135-368">自定义敏感信息类型（根据需要）。</span><span class="sxs-lookup"><span data-stu-id="7f135-368">Custom sensitive information types (as needed).</span></span>
- <span data-ttu-id="7f135-369">保留标签（根据需要）。</span><span class="sxs-lookup"><span data-stu-id="7f135-369">Retention labels (as needed).</span></span>
- <span data-ttu-id="7f135-370">敏感度标签（根据需要）。</span><span class="sxs-lookup"><span data-stu-id="7f135-370">Sensitivity labels (as needed).</span></span>

<span data-ttu-id="7f135-371">以下是当组织使用混合标识时基础结构的可视摘要，它包含 AD DS 域、Azure AD Connect 服务器以及同步的 AD DS 用户和组。</span><span class="sxs-lookup"><span data-stu-id="7f135-371">Here is a visual summary of the infrastructure if your organization uses hybrid identity, which includes your AD DS domain, an Azure AD Connect server, and synchronized AD DS users and groups.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
<span data-ttu-id="7f135-372">以下是当组织使用仅限云标识时基础结构的可视摘要。</span><span class="sxs-lookup"><span data-stu-id="7f135-372">Here is a visual summary of the infrastructure if your organization uses cloud-only identity.</span></span>
 
![](./media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a><span data-ttu-id="7f135-373">员工结果</span><span class="sxs-lookup"><span data-stu-id="7f135-373">Employee results</span></span>

<span data-ttu-id="7f135-374">载入后，每位员工都应该具有：</span><span class="sxs-lookup"><span data-stu-id="7f135-374">After their onboarding, each employee should have:</span></span>

- <span data-ttu-id="7f135-375">从其设备到其区域内的 Microsoft 365 云服务的高性能本地网络路径。</span><span class="sxs-lookup"><span data-stu-id="7f135-375">A performant, on-premises network path from their device to the Microsoft 365 cloud services in their region.</span></span>
- <span data-ttu-id="7f135-376">包含这些组成员身份的用户帐户：</span><span class="sxs-lookup"><span data-stu-id="7f135-376">A user account with these group memberships:</span></span>
   - <span data-ttu-id="7f135-377">已许可</span><span class="sxs-lookup"><span data-stu-id="7f135-377">Licensed</span></span>
   - <span data-ttu-id="7f135-378">相应的 AD DS 或 Azure AD 安全组，它们也是“基线”、“敏感”和“高度管控”Azure AD 条件访问策略组的成员</span><span class="sxs-lookup"><span data-stu-id="7f135-378">The appropriate AD DS or Azure AD security groups, which are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups for conditional access policies</span></span> 
   - <span data-ttu-id="7f135-379">相应的工作组、部门和区域组</span><span class="sxs-lookup"><span data-stu-id="7f135-379">The appropriate workgroup, departmental, and regional groups</span></span>
   - <span data-ttu-id="7f135-380">敏感度标签组（根据需要）</span><span class="sxs-lookup"><span data-stu-id="7f135-380">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="7f135-381">Windows 10 企业版设备：</span><span class="sxs-lookup"><span data-stu-id="7f135-381">A Windows 10 Enterprise device that:</span></span>
   - <span data-ttu-id="7f135-382">已加入 Azure AD 租户（仅限云）或已同时加入 Azure AD 租户和 AD DS 域（混合）。</span><span class="sxs-lookup"><span data-stu-id="7f135-382">Is joined to the Azure AD tenant (cloud-only) or to both the Azure AD tenant and your AD DS domain (hybrid).</span></span>
   - <span data-ttu-id="7f135-383">使用最新的 Windows 10 企业版产品改进和安全增强功能进行自动更新。</span><span class="sxs-lookup"><span data-stu-id="7f135-383">Automatically updates itself with the latest Windows 10 Enterprise product improvements and security enhancements.</span></span>
   - <span data-ttu-id="7f135-384">已安装 Office 365 专业增强版，它使用最新的 Office 产品改进和安全增强功能进行自动更新。</span><span class="sxs-lookup"><span data-stu-id="7f135-384">Has Office 365 ProPlus installed, which automatically updates itself with the latest Office product improvements and security enhancements.</span></span>
   - <span data-ttu-id="7f135-385">已在 Intune 中注册并受 Intune 设备合规性策略和应用保护策略的制约。</span><span class="sxs-lookup"><span data-stu-id="7f135-385">Is enrolled in Intune and subject to Intune device compliance policies and app protection policies.</span></span>

## <a name="next-step"></a><span data-ttu-id="7f135-386">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7f135-386">Next step</span></span>

<span data-ttu-id="7f135-387">利用基础架构的功能和配置来部署[工作负载和方案](deploy-workloads.md)。</span><span class="sxs-lookup"><span data-stu-id="7f135-387">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
