---
title: Microsoft 365客户端和服务应用支持
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 本文查找有关客户端Microsoft 365服务应用支持的详细信息。
ms.openlocfilehash: e380efffc1bf29cbd4d3a77d32e4d1f8b2994da3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905004"
---
# <a name="microsoft-365-client-and-services-app-support"></a><span data-ttu-id="80cde-103">Microsoft 365客户端和服务应用支持</span><span class="sxs-lookup"><span data-stu-id="80cde-103">Microsoft 365 client and services app support</span></span>

<span data-ttu-id="80cde-104">Microsoft 支持多种安全、身份验证和合规性功能，以确保客户数据安全，并允许 IT 管理员在 Microsoft 365 管理中心中为用户自定义策略。</span><span class="sxs-lookup"><span data-stu-id="80cde-104">Microsoft supports a wide range of security, authentication, and compliance features to keep customer data safe and allows IT administrators to customize policies within the Microsoft 365 admin center for their users.</span></span> <span data-ttu-id="80cde-105">以下功能只是许多企业功能的子集，您可以根据你的订阅Microsoft 365这些功能。</span><span class="sxs-lookup"><span data-stu-id="80cde-105">The following features are just a subset of the many enterprise features that you can configure depending on your Microsoft 365 subscription.</span></span>

## <a name="client-and-service-support"></a><span data-ttu-id="80cde-106">客户端和服务支持</span><span class="sxs-lookup"><span data-stu-id="80cde-106">Client and service support</span></span>

### <a name="continuous-access-evaluation-preview"></a><span data-ttu-id="80cde-107">连续访问评估 (预览) </span><span class="sxs-lookup"><span data-stu-id="80cde-107">Continuous access evaluation (preview)</span></span>

<span data-ttu-id="80cde-108">连续访问评估通过启用服务（如 Exchange Online、SharePoint Online 和 Teams）订阅 Azure Active Directory 中的关键事件来实施，以便几乎可以实时评估和强制执行这些事件。</span><span class="sxs-lookup"><span data-stu-id="80cde-108">Continuous access evaluation is implemented by enabling services, like Exchange Online, SharePoint Online, and Teams, to subscribe to critical events in Azure Active Directory so that those events can be evaluated and enforced near real time.</span></span> <span data-ttu-id="80cde-109">关键事件评估不依赖于条件访问策略，因此可在任何租户中使用。</span><span class="sxs-lookup"><span data-stu-id="80cde-109">Critical event evaluation does not rely on Conditional Access policies so is available in any tenant.</span></span>

<span data-ttu-id="80cde-110">当前评估以下事件：</span><span class="sxs-lookup"><span data-stu-id="80cde-110">The following events are currently evaluated:</span></span>

- <span data-ttu-id="80cde-111">删除或禁用用户帐户</span><span class="sxs-lookup"><span data-stu-id="80cde-111">A user account is deleted or disabled</span></span>
- <span data-ttu-id="80cde-112">更改或重置用户的密码</span><span class="sxs-lookup"><span data-stu-id="80cde-112">The password for a user is changed or reset</span></span>
- <span data-ttu-id="80cde-113">为用户启用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="80cde-113">Multi-factor authentication is enabled for the user</span></span>
- <span data-ttu-id="80cde-114">管理员显式撤消用户的所有刷新令牌</span><span class="sxs-lookup"><span data-stu-id="80cde-114">Administrator explicitly revokes all refresh tokens for a user</span></span>
- <span data-ttu-id="80cde-115">Azure AD Identity Protection 检测到的提升的用户风险</span><span class="sxs-lookup"><span data-stu-id="80cde-115">Elevated user risk detected by Azure AD Identity Protection</span></span>

<span data-ttu-id="80cde-116">有关客户端和服务应用支持的连续访问评估的详细信息，请参阅连续访问评估 ([预览) 。 ](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)</span><span class="sxs-lookup"><span data-stu-id="80cde-116">For more information about continuous access evaluation for client and services app support, see [Continuous access evaluation (preview)](/azure/active-directory/conditional-access/concept-continuous-access-evaluation).</span></span>

## <a name="client-support"></a><span data-ttu-id="80cde-117">客户端支持</span><span class="sxs-lookup"><span data-stu-id="80cde-117">Client support</span></span>

### <a name="certificate-based-authentication"></a><span data-ttu-id="80cde-118">基于证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="80cde-118">Certificate-based authentication</span></span>

<span data-ttu-id="80cde-119">CBA (基于证书) 是使用数字证书在授予对资源、网络、应用程序或服务的访问权限之前标识用户、计算机或设备。</span><span class="sxs-lookup"><span data-stu-id="80cde-119">Certificate-based authentication (CBA) is the use of a digital certificate to identify a user, machine, or device before granting access to a resource, network, application, or service.</span></span> <span data-ttu-id="80cde-120">在用户身份验证中，它通常与用户名和密码等传统方法协调部署。</span><span class="sxs-lookup"><span data-stu-id="80cde-120">In user authentication, it is often deployed in coordination with traditional methods such as usernames and passwords.</span></span>

<span data-ttu-id="80cde-121">某些传统解决方案仅适用于用户，例如生物识别以及 OTP (一) 。</span><span class="sxs-lookup"><span data-stu-id="80cde-121">Some traditional solutions only work for users, such as biometrics and one-time passwords (OTP).</span></span> <span data-ttu-id="80cde-122">使用基于证书的身份验证，可针对所有终结点使用相同的解决方案;用户、设备和不断增多的物联网 (IoT) 。</span><span class="sxs-lookup"><span data-stu-id="80cde-122">With certificate-based authentication, the same solution can be used for all endpoints; users, devices, and the growing Internet of Things (IoT).</span></span>

<span data-ttu-id="80cde-123">有关客户端和服务应用支持的基于证书的身份验证Microsoft 365请参阅客户端[应用支持：基于证书的身份验证](microsoft-365-client-support-certificate-based-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="80cde-123">For more information about certificate-based authentication for client and services app support, see [Microsoft 365 Client App Support: Certificate-based Authentication](microsoft-365-client-support-certificate-based-authentication.md).</span></span>

### <a name="conditional-access"></a><span data-ttu-id="80cde-124">条件访问</span><span class="sxs-lookup"><span data-stu-id="80cde-124">Conditional Access</span></span>

<span data-ttu-id="80cde-125">条件访问是一种工具，Azure Active Directory将信号汇集在一起、做出决策以及强制执行组织访问策略。</span><span class="sxs-lookup"><span data-stu-id="80cde-125">Conditional Access is the tool used by Azure Active Directory to bring signals together, to make decisions, and enforce organizational access policies.</span></span> <span data-ttu-id="80cde-126">条件访问是新的标识驱动控件模型的核心。</span><span class="sxs-lookup"><span data-stu-id="80cde-126">Conditional Access is at the heart of the new identity-driven control model.</span></span>

<span data-ttu-id="80cde-127">条件访问策略是 if-then 语句，用于授予对资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="80cde-127">Conditional Access policies are if-then statements for granting access to resources.</span></span> <span data-ttu-id="80cde-128">如果用户希望访问资源，则用户必须完成一个操作。</span><span class="sxs-lookup"><span data-stu-id="80cde-128">If a user wants to access a resource, then the user must complete an action.</span></span> <span data-ttu-id="80cde-129">条件访问在做出策略访问决策时可以使用的常见信号包括：</span><span class="sxs-lookup"><span data-stu-id="80cde-129">Common signals that Conditional Access can use when making a policy access decision include:</span></span>

- <span data-ttu-id="80cde-130">用户或组成员身份</span><span class="sxs-lookup"><span data-stu-id="80cde-130">User or group membership</span></span>
- <span data-ttu-id="80cde-131">IP 位置信息</span><span class="sxs-lookup"><span data-stu-id="80cde-131">IP location information</span></span>
- <span data-ttu-id="80cde-132">设备信息</span><span class="sxs-lookup"><span data-stu-id="80cde-132">Device information</span></span>
- <span data-ttu-id="80cde-133">应用程序信息</span><span class="sxs-lookup"><span data-stu-id="80cde-133">Application information</span></span>
- <span data-ttu-id="80cde-134">实时和计算的风险检测</span><span class="sxs-lookup"><span data-stu-id="80cde-134">Real-time and calculated risk detection</span></span>
- <span data-ttu-id="80cde-135">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="80cde-135">Microsoft Cloud App Security (MCAS)</span></span>

<span data-ttu-id="80cde-136">做出这些访问决策时，策略可以采取不同的操作：</span><span class="sxs-lookup"><span data-stu-id="80cde-136">When making these access decisions, the policies can take different actions:</span></span>

- <span data-ttu-id="80cde-137">策略可以阻止访问：此配置是最严格的操作，可阻止用户访问资源。</span><span class="sxs-lookup"><span data-stu-id="80cde-137">The policy can block access: This configuration is the most restrictive action and prevents the user from accessing the resource.</span></span>
- <span data-ttu-id="80cde-138">策略可以授予访问权限：此配置是限制较少的决策，可能仍然需要以下一个或多个选项：</span><span class="sxs-lookup"><span data-stu-id="80cde-138">The policy can grant access: This configuration is a less restrictive decision and may still require one or more of the following options:</span></span>

    - <span data-ttu-id="80cde-139">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="80cde-139">Multi-factor authentication</span></span>
    - <span data-ttu-id="80cde-140">要标记为合规的设备</span><span class="sxs-lookup"><span data-stu-id="80cde-140">The device to be marked as compliant</span></span>
    - <span data-ttu-id="80cde-141">设备已加入混合 Azure AD</span><span class="sxs-lookup"><span data-stu-id="80cde-141">The device is hybrid Azure AD joined</span></span>
    - <span data-ttu-id="80cde-142">已批准的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="80cde-142">An approved client app</span></span>
    - <span data-ttu-id="80cde-143">配置了应用保护策略 (预览) </span><span class="sxs-lookup"><span data-stu-id="80cde-143">App protection policy configured (preview)</span></span>

<span data-ttu-id="80cde-144">有关客户端和服务应用支持的条件访问详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="80cde-144">For more information about Conditional Access for client and services app support, see:</span></span>

- [<span data-ttu-id="80cde-145">Microsoft 365客户端应用支持：基于设备的条件访问</span><span class="sxs-lookup"><span data-stu-id="80cde-145">Microsoft 365 Client App Support: Device-based Conditional Access</span></span>](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a><span data-ttu-id="80cde-146">移动应用管理</span><span class="sxs-lookup"><span data-stu-id="80cde-146">Mobile application management</span></span>

<span data-ttu-id="80cde-147">用户通常从同一移动设备访问组织和个人文档、电子邮件和数据。</span><span class="sxs-lookup"><span data-stu-id="80cde-147">Users often access both organization and personal documents, email, and data from the same mobile device.</span></span> <span data-ttu-id="80cde-148">这些设备通常是个人拥有的，应配置为保护组织数据和用户的个人隐私。</span><span class="sxs-lookup"><span data-stu-id="80cde-148">Those devices are often personally owned and should be configured to protect both organization data and the user's personal privacy.</span></span>

<span data-ttu-id="80cde-149">用户访问组织数据时，组织必须确保应用组织策略（如配置策略和保护策略）以帮助保护设备中的组织数据。</span><span class="sxs-lookup"><span data-stu-id="80cde-149">When a user accesses organization data, the organization must be confident that organization policies, such as configuration policies and protection policies, are applied to help protect organization data on the device.</span></span> <span data-ttu-id="80cde-150">此外，用户设备上的个人内容应保持在组织控制之外。</span><span class="sxs-lookup"><span data-stu-id="80cde-150">Additionally, the user's personal content on the device should remain outside of the organization's control.</span></span>

<span data-ttu-id="80cde-151">对于组织管理的内容，您可以应用应用程序管理策略，以控制如何使用 Microsoft Intune 访问、共享和使用Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="80cde-151">For organization-managed content, you can apply application management policies to control how data is accessed, shared, and used by using Microsoft Intune.</span></span> <span data-ttu-id="80cde-152">例如，支持以下操作：</span><span class="sxs-lookup"><span data-stu-id="80cde-152">For example, the following actions are supported:</span></span>

- <span data-ttu-id="80cde-153">远程擦除托管组织内容 (也称为组织数据) </span><span class="sxs-lookup"><span data-stu-id="80cde-153">Remote wipe the managed organization content (also referred to org data)</span></span>
- <span data-ttu-id="80cde-154">防止将组织内容粘贴到非组织位置</span><span class="sxs-lookup"><span data-stu-id="80cde-154">Prevent pasting organization content into non-organization locations</span></span>
- <span data-ttu-id="80cde-155">需要 PIN 来访问组织内容</span><span class="sxs-lookup"><span data-stu-id="80cde-155">Require a PIN to access organization content</span></span>
- <span data-ttu-id="80cde-156">阻止托管应用在已越狱或获得 root 权限的设备上运行</span><span class="sxs-lookup"><span data-stu-id="80cde-156">Prevent managed apps from running on jailbroken or rooted devices</span></span>
- <span data-ttu-id="80cde-157">阻止将组织内容保存到未经批准的云存储提供程序</span><span class="sxs-lookup"><span data-stu-id="80cde-157">Prevent organization content from being saved to unapproved cloud storage providers</span></span>
- <span data-ttu-id="80cde-158">阻止将未经批准的内容传输到托管应用程序中</span><span class="sxs-lookup"><span data-stu-id="80cde-158">Prevent unapproved content from being transferred into managed applications</span></span>
- <span data-ttu-id="80cde-159">仅在应用了策略后，才允许访问组织内容</span><span class="sxs-lookup"><span data-stu-id="80cde-159">Allow access to organization content only after policies have been applied</span></span>
- <span data-ttu-id="80cde-160">提供应用程序配置以管理应用程序的行为和设置</span><span class="sxs-lookup"><span data-stu-id="80cde-160">Deliver application configuration to manage the application's behavior and settings</span></span>
- <span data-ttu-id="80cde-161">通过禁用多标识功能或个人用法，将托管应用程序限制为定义的标识</span><span class="sxs-lookup"><span data-stu-id="80cde-161">Restrict the managed application to a defined identity by disabling multi-identity capabilities or personal usage</span></span>

<span data-ttu-id="80cde-162">有关使用应用程序管理移动应用程序Microsoft Intune，请参阅什么是Microsoft Intune[应用程序管理？](/mem/intune/apps/app-management)</span><span class="sxs-lookup"><span data-stu-id="80cde-162">For more information about mobile application management with Microsoft Intune, see [What is Microsoft Intune app management?](/mem/intune/apps/app-management)</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="80cde-163">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="80cde-163">Multi-factor authentication</span></span>

<span data-ttu-id="80cde-164">[MFA (多重身份验证) 是一种计算机访问控制方法，在该方法中，只有在向身份验证机制成功呈现多个单独证据后，用户才被授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="80cde-164">[Multi-factor authentication (MFA) is a method of computer access control in which a user is granted access only after successfully presenting several separate pieces of evidence to an authentication mechanism.</span></span> <span data-ttu-id="80cde-165">此方法通常至少使用下列两种类别：</span><span class="sxs-lookup"><span data-stu-id="80cde-165">This method typically uses at least two of the following categories:</span></span>

- <span data-ttu-id="80cde-166">知识 (他们了解) </span><span class="sxs-lookup"><span data-stu-id="80cde-166">Knowledge (something they know)</span></span>
- <span data-ttu-id="80cde-167">拥有 (他们拥有) </span><span class="sxs-lookup"><span data-stu-id="80cde-167">Possession (something they have)</span></span>
- <span data-ttu-id="80cde-168">不一 (它们) </span><span class="sxs-lookup"><span data-stu-id="80cde-168">Inherence (something they are)</span></span>

<span data-ttu-id="80cde-169">有关客户端和服务应用支持的多重身份验证详细信息，请参阅Microsoft 365[客户端应用支持：多重身份验证](microsoft-365-client-support-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="80cde-169">For more information about multi-factor authentication for client and services app support, see [Microsoft 365 Client App Support: Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md).</span></span>

### <a name="single-sign-on"></a><span data-ttu-id="80cde-170">单一登录</span><span class="sxs-lookup"><span data-stu-id="80cde-170">Single sign-on</span></span>

<span data-ttu-id="80cde-171">SSO (单一登录) 当用户登录到 SSO 中的应用程序时，可添加安全性和Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="80cde-171">Single sign-on (SSO) adds security and convenience when your users sign-on to applications in Azure Active Directory.</span></span> <span data-ttu-id="80cde-172">借助单一登录，用户可以使用一个帐户登录一次，以访问本地 Active Directory 域服务 (AD DS) 已加入域的设备、软件即服务 (SaaS) 应用程序和您组织的 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="80cde-172">With single sign-on, users sign in once with one account to access on-premises Active Directory Domain Services (AD DS) domain-joined devices, software as a service (SaaS) applications, and web applications in your organization.</span></span>

<span data-ttu-id="80cde-173">有关客户端和服务应用支持的单一登录Microsoft 365，请参阅客户端应用支持：[单一登录](microsoft-365-client-support-single-sign-on.md)。</span><span class="sxs-lookup"><span data-stu-id="80cde-173">For more information about single sign-on for client and services app support, see [Microsoft 365 Client App Support: Single sign-on](microsoft-365-client-support-single-sign-on.md).</span></span>

## <a name="services-support"></a><span data-ttu-id="80cde-174">服务支持</span><span class="sxs-lookup"><span data-stu-id="80cde-174">Services support</span></span>

### <a name="modern-authentication"></a><span data-ttu-id="80cde-175">新式验证</span><span class="sxs-lookup"><span data-stu-id="80cde-175">Modern authentication</span></span>

<span data-ttu-id="80cde-176">新式身份验证使客户能够针对 Office 365 进行身份验证的新方案，以及租户管理员在整个租户Office 365特定的身份验证要求，例如：</span><span class="sxs-lookup"><span data-stu-id="80cde-176">Modern authentication enables new scenarios for customers to authenticate against Office 365 and for tenant admins to enforce specific authentication requirements across the Office 365 tenancy, such as:</span></span>

- <span data-ttu-id="80cde-177">对与租赁和服务的管理交互以及最终用户与应用程序及其数据的交互的多重身份验证支持</span><span class="sxs-lookup"><span data-stu-id="80cde-177">Multi-factor authentication support for administrative interaction with the tenancy and services, and end-user interaction with applications and their data</span></span>
- <span data-ttu-id="80cde-178">条件访问</span><span class="sxs-lookup"><span data-stu-id="80cde-178">Conditional access</span></span>
- <span data-ttu-id="80cde-179">基于 SAML 的第三方标识提供程序登录</span><span class="sxs-lookup"><span data-stu-id="80cde-179">SAML-based third-party identity provider sign-in</span></span>
- <span data-ttu-id="80cde-180">个人计算机上的智能卡日志</span><span class="sxs-lookup"><span data-stu-id="80cde-180">Smartcard log on personal computers</span></span>
- <span data-ttu-id="80cde-181">移动设备上基于证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="80cde-181">Certificate-based authentication on mobile devices</span></span>
- <span data-ttu-id="80cde-182">不再需要通过基本身份验证传输凭据。</span><span class="sxs-lookup"><span data-stu-id="80cde-182">No longer require the transmission of credentials over basic authentication.</span></span>

<span data-ttu-id="80cde-183">有关新式身份验证服务支持的信息，请参阅身份验证 [与授权](/azure/active-directory/develop/authentication-vs-authorization)。</span><span class="sxs-lookup"><span data-stu-id="80cde-183">For more information about modern authentication services support, see [Authentication vs. authorization](/azure/active-directory/develop/authentication-vs-authorization).</span></span>

### <a name="azure-active-directory-conditional-access"></a><span data-ttu-id="80cde-184">Azure Active Directory 条件访问</span><span class="sxs-lookup"><span data-stu-id="80cde-184">Azure Active Directory Conditional Access</span></span>

<span data-ttu-id="80cde-185">Azure Active Directory (Azure AD) 条件访问规则允许客户根据设备合规性或网络位置等属性控制对联机服务的访问。</span><span class="sxs-lookup"><span data-stu-id="80cde-185">Azure Active Directory (Azure AD) Conditional Access rules allow customers to control access to online services, based on attributes such as device compliance or network location.</span></span> <span data-ttu-id="80cde-186">可能会使用下列解决方案：</span><span class="sxs-lookup"><span data-stu-id="80cde-186">The following solutions may be used:</span></span>

- <span data-ttu-id="80cde-187">基于 Azure AD 多重身份验证的条件访问</span><span class="sxs-lookup"><span data-stu-id="80cde-187">Azure AD multi-factor authentication-based Conditional Access</span></span>
- <span data-ttu-id="80cde-188">基于 Azure AD 位置的条件访问</span><span class="sxs-lookup"><span data-stu-id="80cde-188">Azure AD location-based Conditional Access</span></span>
- <span data-ttu-id="80cde-189">基于 Azure AD 设备的条件访问</span><span class="sxs-lookup"><span data-stu-id="80cde-189">Azure AD device-based Conditional Access</span></span>

<span data-ttu-id="80cde-190">Azure AD 条件访问规则适用于每个应用程序，客户可以使用这些规则根据不同的条件控制访问。</span><span class="sxs-lookup"><span data-stu-id="80cde-190">Azure AD Conditional access rules are applied per-application and are available for customers to control access based on different conditions.</span></span> <span data-ttu-id="80cde-191">使用[移动设备管理 (MDM) 或 Intune，](/mem/intune/fundamentals/what-is-device-management)客户必须能够将 Microsoft 365 的访问权限限制为仅针对使用组织设备或已注册其个人设备进行管理的用户。</span><span class="sxs-lookup"><span data-stu-id="80cde-191">Using [Mobile Device Management (MDM) or Intune](/mem/intune/fundamentals/what-is-device-management), customers must be able to restrict access to Microsoft 365 to only those users who are using an organization device or who have enrolled their personal device for management.</span></span> <span data-ttu-id="80cde-192">例如，客户可以配置条件访问规则以强制执行如下控件：</span><span class="sxs-lookup"><span data-stu-id="80cde-192">For example, customers may configure Conditional Access rules to enforce controls such as:</span></span>

- <span data-ttu-id="80cde-193">仅允许从已加入域或符合域的设备访问</span><span class="sxs-lookup"><span data-stu-id="80cde-193">Only allow access from devices that are domain joined or domain compliant</span></span>
- <span data-ttu-id="80cde-194">强制对服务的所有访问进行多重Exchange Online身份验证</span><span class="sxs-lookup"><span data-stu-id="80cde-194">Enforce multi-factor authentication for all access to Exchange Online services</span></span>

<span data-ttu-id="80cde-195">有关条件访问Azure Active Directory，请参阅[什么是条件访问？](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="80cde-195">For more information about Azure Active Directory Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span>

### <a name="tls-12-support"></a><span data-ttu-id="80cde-196">TLS 1.2 支持</span><span class="sxs-lookup"><span data-stu-id="80cde-196">TLS 1.2 support</span></span>

<span data-ttu-id="80cde-197">为了为客户提供一流的加密，Microsoft 计划停止支持 Office 365 和 Office 365 GCC 中的传输层安全性 (TLS) 版本 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="80cde-197">To provide the best-in-class encryption to our customers, Microsoft plans to discontinue support for Transport Layer Security (TLS) versions 1.0 and 1.1 in Office 365 and Office 365 GCC.</span></span>

<span data-ttu-id="80cde-198">我们知道您的数据的安全性非常重要，并且我们承诺对可能影响使用 TLS 服务的更改保持透明公开。</span><span class="sxs-lookup"><span data-stu-id="80cde-198">We understand that the security of your data is important, and we're committed to transparency about changes that may affect your use of the TLS service.</span></span> <span data-ttu-id="80cde-199">我们建议所有客户端-服务器和浏览器-服务器组合使用 TLS 1.2 (或更高版本) 来维护与 Office 365 服务的连接。</span><span class="sxs-lookup"><span data-stu-id="80cde-199">We recommend that all client-server and browser-server combinations use TLS 1.2 (or a later version) to maintain connection to Office 365 services.</span></span> <span data-ttu-id="80cde-200">你可能必须更新某些客户端-服务器和浏览器-服务器组合。</span><span class="sxs-lookup"><span data-stu-id="80cde-200">You might have to update certain client-server and browser-server combinations.</span></span>

<span data-ttu-id="80cde-201">有关 TLS 1.2 支持和服务支持的信息，请参阅 Office 365 和 Office 365 GCC 中的准备[TLS 1.2。](../compliance/prepare-tls-1.2-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="80cde-201">For more information about TLS 1.2 support and services support, see [Preparing for TLS 1.2 in Office 365 and Office 365 GCC](../compliance/prepare-tls-1.2-in-office-365.md).</span></span>