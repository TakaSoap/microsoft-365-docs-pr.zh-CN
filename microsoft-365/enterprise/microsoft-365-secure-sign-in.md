---
title: 安全地让用户登录到 Microsoft 365 租户
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365initiative-coredeploy
ms.custom: ''
description: 要求用户通过多重身份验证（MFA）和其他功能安全地登录。
ms.openlocfilehash: 64b873a243d0ce86ee3700d5150076f88031a483
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399131"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a><span data-ttu-id="2784d-103">安全地让用户登录到 Microsoft 365 租户</span><span class="sxs-lookup"><span data-stu-id="2784d-103">Secure user sign-ins to your Microsoft 365 tenant</span></span>

<span data-ttu-id="2784d-104">若要增强用户登录的安全性，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2784d-104">To increase the security of user sign-ins:</span></span>

- <span data-ttu-id="2784d-105">使用 Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="2784d-105">Use Windows Hello for Business</span></span>
- <span data-ttu-id="2784d-106">使用 Azure Active Directory (Azure AD) 密码保护</span><span class="sxs-lookup"><span data-stu-id="2784d-106">Use Azure Active Directory (Azure AD) Password Protection</span></span>
- <span data-ttu-id="2784d-107">使用多重身份验证 (MFA)</span><span class="sxs-lookup"><span data-stu-id="2784d-107">Use multi-factor authentication (MFA)</span></span>
- <span data-ttu-id="2784d-108">部署标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="2784d-108">Deploy identity and device access configurations</span></span>
- <span data-ttu-id="2784d-109">通过 Azure AD 标识保护防止凭据泄露</span><span class="sxs-lookup"><span data-stu-id="2784d-109">Protect against credential compromise with Azure AD Identity Protection</span></span>

## <a name="windows-hello-for-business"></a><span data-ttu-id="2784d-110">Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="2784d-110">Windows Hello for Business</span></span>

<span data-ttu-id="2784d-111">Windows 10 企业版中的 Windows Hello 企业版在 Windows 设备上签名时，会将密码替换为强双因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="2784d-111">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="2784d-112">这两个因素是一种与设备和生物识别或 PIN 相关联的新型用户凭据。</span><span class="sxs-lookup"><span data-stu-id="2784d-112">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="2784d-113">有关详细信息，请参阅 [Windows Hello 企业版概述](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。</span><span class="sxs-lookup"><span data-stu-id="2784d-113">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


## <a name="azure-ad-password-protection"></a><span data-ttu-id="2784d-114">Azure AD 密码保护</span><span class="sxs-lookup"><span data-stu-id="2784d-114">Azure AD Password Protection</span></span>

<span data-ttu-id="2784d-115">Azure AD 密码保护会检测并阻止已知的弱密码及其变体，还会阻止特定于你组织的额外弱项。</span><span class="sxs-lookup"><span data-stu-id="2784d-115">Azure AD Password Protection detects and blocks known weak passwords and their variants and can also block additional weak terms that are specific to your organization.</span></span> <span data-ttu-id="2784d-116">默认全局禁止使用的密码列表将自动应用于 Azure AD 租户中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="2784d-116">Default global banned password lists are automatically applied to all users in an Azure AD tenant.</span></span> <span data-ttu-id="2784d-117">可在自定义禁止密码列表中定义额外条目。</span><span class="sxs-lookup"><span data-stu-id="2784d-117">You can define additional entries in a custom banned password list.</span></span> <span data-ttu-id="2784d-118">用户更改或重置其密码时，将检查这些禁止的密码列表，强制使用强密码。</span><span class="sxs-lookup"><span data-stu-id="2784d-118">When users change or reset their passwords, these banned password lists are checked to enforce the use of strong passwords.</span></span>

<span data-ttu-id="2784d-119">有关详细信息，请参阅“[配置 Azure AD 密码保护](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)”。</span><span class="sxs-lookup"><span data-stu-id="2784d-119">For more information, see [Configure Azure AD password protection](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).</span></span>

## <a name="mfa"></a><span data-ttu-id="2784d-120">MFA</span><span class="sxs-lookup"><span data-stu-id="2784d-120">MFA</span></span>

<span data-ttu-id="2784d-121">MFA 要求用户登录受用户帐户密码之外的其他验证约束。</span><span class="sxs-lookup"><span data-stu-id="2784d-121">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="2784d-122">即使恶意用户确定了用户帐户密码，还必须能够响应其他验证（如发送到智能手机的短信）才能获得访问权限。</span><span class="sxs-lookup"><span data-stu-id="2784d-122">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![正确的密码和其他验证会导致登录成功](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="2784d-124">使用 MFA 的第一步是***对所有管理员帐户要求使用 MFA***，这些帐户也被称为特权帐户。</span><span class="sxs-lookup"><span data-stu-id="2784d-124">Your first step in using MFA is to ***require it for all administrator accounts***, also known as privileged accounts.</span></span>

<span data-ttu-id="2784d-125">比第一步更好的是，Microsoft 建议对所有用户要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="2784d-125">Beyond this first step, Microsoft recommends MFA For all users.</span></span>

<span data-ttu-id="2784d-126">根据 Microsoft 365 套餐，可通过三种方式要求你的管理员或用户使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="2784d-126">There are three ways to require your administrators or users to use MFA based on your Microsoft 365 plan.</span></span>

| <span data-ttu-id="2784d-127">计划</span><span class="sxs-lookup"><span data-stu-id="2784d-127">Plan</span></span> | <span data-ttu-id="2784d-128">建议</span><span class="sxs-lookup"><span data-stu-id="2784d-128">Recommendation</span></span> |
|---------|---------|
|<span data-ttu-id="2784d-129">所有 Microsoft 365 套餐（无 Azure AD Premium P1 或 P2 许可证）</span><span class="sxs-lookup"><span data-stu-id="2784d-129">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="2784d-130">[在 Azure AD 中启用安全性默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="2784d-130">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="2784d-131">Azure AD 中的安全性默认值于用户和管理员的 MFA。</span><span class="sxs-lookup"><span data-stu-id="2784d-131">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="2784d-132">Microsoft 365 E3 （包括 Azure AD Premium P1 许可证）</span><span class="sxs-lookup"><span data-stu-id="2784d-132">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="2784d-133">使用[常用条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)配置以下策略：</span><span class="sxs-lookup"><span data-stu-id="2784d-133">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="2784d-134">- [要求对管理员执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="2784d-134">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="2784d-135">- [要求对所有用户执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="2784d-135">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="2784d-136">- [阻止传统身份验证](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="2784d-136">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="2784d-137">Microsoft 365 E5 （包括 Azure AD Premium P2 许可证）</span><span class="sxs-lookup"><span data-stu-id="2784d-137">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="2784d-138">利用 Azure AD 标识保护，通过创建以下两个策略开始实施 Microsoft [推荐的一组条件访问和相关策略](../security/office-365-security/identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="2784d-138">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of conditional access and related policies](../security/office-365-security/identity-access-policies.md) by creating these two policies:</span></span><br> <span data-ttu-id="2784d-139">- [要求在登录风险为“中等”或“高”时执行 MFA](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="2784d-139">- [Require MFA when sign-in risk is medium or high](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="2784d-140">- [高风险用户必须更改密码](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="2784d-140">- [High risk users must change password](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

### <a name="security-defaults"></a><span data-ttu-id="2784d-141">安全性默认值</span><span class="sxs-lookup"><span data-stu-id="2784d-141">Security defaults</span></span>

<span data-ttu-id="2784d-142">安全性默认值是在 2019 年 10 月 21 日之后创建的 Microsoft 365 和 Office 365 付费或试用版订阅的一项新功能。</span><span class="sxs-lookup"><span data-stu-id="2784d-142">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="2784d-143">这些订阅启用了安全性默认值，这***要求所有用户将 MFA 与 Microsoft Authenticator 应用配合使用***。</span><span class="sxs-lookup"><span data-stu-id="2784d-143">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="2784d-144">用户有 14 天的时间从其智能手机中通过 Microsoft Authenticator 应用登录 MFA，自启用安全性默认值后首次登录起计。</span><span class="sxs-lookup"><span data-stu-id="2784d-144">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="2784d-145">14 天后，除非 MFA 注册完成，否则用户将无法登录。</span><span class="sxs-lookup"><span data-stu-id="2784d-145">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="2784d-146">安全性默认值可确保所有组织均对默认启用的用户登录具有基本的安全级别。</span><span class="sxs-lookup"><span data-stu-id="2784d-146">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="2784d-147">可使用条件访问策略或针对个别帐户禁用安全性默认值，以支持 MFA。</span><span class="sxs-lookup"><span data-stu-id="2784d-147">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="2784d-148">有关详细信息，请参阅[安全性默认值概述](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="2784d-148">For more information, see the [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="2784d-149">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="2784d-149">Conditional Access policies</span></span>

<span data-ttu-id="2784d-150">条件访问策略是一组规则，指定评估登录和授予访问的条件。</span><span class="sxs-lookup"><span data-stu-id="2784d-150">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and access is granted.</span></span> <span data-ttu-id="2784d-151">例如，你可以创建一个条件访问策略，指明：</span><span class="sxs-lookup"><span data-stu-id="2784d-151">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="2784d-152">如果用户帐户名是分配了 Exchange、用户、密码、安全性、SharePoint 或全局管理员角色的用户组的成员，则需要先进行 MFA，然后才能允许访问。</span><span class="sxs-lookup"><span data-stu-id="2784d-152">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="2784d-153">通过此策略，当为用户分配或取消分配了上述管理员角色时，你可以根据其组成员身份要求进行 MFA，而不是针对单个用户帐户进行 MFA 配置。</span><span class="sxs-lookup"><span data-stu-id="2784d-153">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="2784d-154">你还可以使用条件访问策略来实现更高级的功能，例如，要求从合规设备（例如运行 Windows 10 的电脑）完成登录。</span><span class="sxs-lookup"><span data-stu-id="2784d-154">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="2784d-155">条件访问需要 Microsoft 365 E3 和 E5 随附的 Azure AD Premium P1 许可证。</span><span class="sxs-lookup"><span data-stu-id="2784d-155">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="2784d-156">有关详细信息，请参阅[条件访问概述](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="2784d-156">For more information, see the [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="2784d-157">结合使用这些方法</span><span class="sxs-lookup"><span data-stu-id="2784d-157">Using these methods together</span></span>

<span data-ttu-id="2784d-158">请注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="2784d-158">Keep the following in mind:</span></span>

- <span data-ttu-id="2784d-159">如果启用了任何条件访问策略，则无法启用安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="2784d-159">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="2784d-160">如果启用了安全性默认值，则无法启用任何条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="2784d-160">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="2784d-161">如果启用了安全性默认值，系统将提示所有新用户进行 MFA 注册并使用 Microsoft Authenticator 应用。</span><span class="sxs-lookup"><span data-stu-id="2784d-161">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="2784d-162">下表显示了通过安全性默认值和条件访问策略启用 MFA 的结果。</span><span class="sxs-lookup"><span data-stu-id="2784d-162">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="2784d-163">方法</span><span class="sxs-lookup"><span data-stu-id="2784d-163">Method</span></span> | <span data-ttu-id="2784d-164">已启用</span><span class="sxs-lookup"><span data-stu-id="2784d-164">Enabled</span></span> | <span data-ttu-id="2784d-165">禁用</span><span class="sxs-lookup"><span data-stu-id="2784d-165">Disabled</span></span> | <span data-ttu-id="2784d-166">其他身份验证方法</span><span class="sxs-lookup"><span data-stu-id="2784d-166">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="2784d-167">**安全性默认值**</span><span class="sxs-lookup"><span data-stu-id="2784d-167">**Security defaults**</span></span>  | <span data-ttu-id="2784d-168">无法使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="2784d-168">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="2784d-169">可以使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="2784d-169">Can use Conditional Access policies</span></span> | <span data-ttu-id="2784d-170">Microsoft Authenticator 应用</span><span class="sxs-lookup"><span data-stu-id="2784d-170">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="2784d-171">**条件访问策略**</span><span class="sxs-lookup"><span data-stu-id="2784d-171">**Conditional Access policies**</span></span> | <span data-ttu-id="2784d-172">如果已启用任何条件访问策略，则无法启用安全性默认值</span><span class="sxs-lookup"><span data-stu-id="2784d-172">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="2784d-173">如果已禁用所有条件访问策略，则可以启用安全性默认值</span><span class="sxs-lookup"><span data-stu-id="2784d-173">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="2784d-174">由用户在 MFA 注册期间指定</span><span class="sxs-lookup"><span data-stu-id="2784d-174">User specifies during MFA registration</span></span>  |
||||

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="2784d-175">标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="2784d-175">Identity and device access configurations</span></span>

<span data-ttu-id="2784d-176">标识和设备访问设置和策略是推荐的必备功能，而且它们的设置与用于确定是否应授予给定的访问请求，以及在何种情况下授予请求的“条件访问”、Intune 和 Azure AD 标识保护策略结合在了一起。</span><span class="sxs-lookup"><span data-stu-id="2784d-176">Identity and device access settings and policies are recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span> <span data-ttu-id="2784d-177">这种决定是基于登录的用户帐户、正在使用的设备、用户为获得访问权限而正在使用的应用程序、创建访问请求的位置，以及对请求风险的评估。</span><span class="sxs-lookup"><span data-stu-id="2784d-177">This determination is based on the user account of the sign-in, the device being used, the app the user is using for access, the location from which the access request is made, and an assessment of the risk of the request.</span></span> <span data-ttu-id="2784d-178">这个功能有助于确保只有经过批准的用户和设备才能访问关键的公司资源。</span><span class="sxs-lookup"><span data-stu-id="2784d-178">This capability helps ensure that only approved users and devices can access your critical resources.</span></span>

>[!Note]
><span data-ttu-id="2784d-179">Azure AD 标识保护需要 Microsoft 365 E5 随附的 Azure AD Premium P2 许可证。</span><span class="sxs-lookup"><span data-stu-id="2784d-179">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>
>

<span data-ttu-id="2784d-180">标识和设备访问策略被定义以用于三种层级：</span><span class="sxs-lookup"><span data-stu-id="2784d-180">Identity and device access policies are defined to be used in three tiers:</span></span> 

- <span data-ttu-id="2784d-181">对于访问应用和数据的身份和设备，基线保护是最低级别的安全性。</span><span class="sxs-lookup"><span data-stu-id="2784d-181">Baseline protection is a minimum level of security for your identities and devices that access your apps and data.</span></span>
- <span data-ttu-id="2784d-182">敏感保护提供针对特定数据的额外安全性。</span><span class="sxs-lookup"><span data-stu-id="2784d-182">Sensitive protection provides additional security for specific data.</span></span> <span data-ttu-id="2784d-183">标识和设备遵循更高级别的安全性和设备运行状况要求。</span><span class="sxs-lookup"><span data-stu-id="2784d-183">Identities and devices are subject to higher levels of security and device health requirements.</span></span>
- <span data-ttu-id="2784d-184">对具有高度管控或分类数据的环境的保护仅用于高度分类、包含商业机密或遵守数据法规的一般少量数据。</span><span class="sxs-lookup"><span data-stu-id="2784d-184">Protection for environments with highly regulated or classified data is for typically small amounts of data that are highly classified, contain trade secrets, or is subject to data regulations.</span></span> <span data-ttu-id="2784d-185">标识和设备遵循非常高级别的安全性和设备运行状况要求。</span><span class="sxs-lookup"><span data-stu-id="2784d-185">Identities and devices are subject to much higher levels of security and device health requirements.</span></span> 

<span data-ttu-id="2784d-186">这些层及其相应的配置会跨数据、标识和设备，提供一致级别的保护。</span><span class="sxs-lookup"><span data-stu-id="2784d-186">These tiers and their corresponding configurations provide consistent levels of protection across your data, identities, and devices.</span></span>

<span data-ttu-id="2784d-187">Microsoft 强烈建议在组织中配置和推出标识和设备访问策略，包括 Microsoft Teams、Exchange Online 和 SharePoint 的特定设置。</span><span class="sxs-lookup"><span data-stu-id="2784d-187">Microsoft highly recommends configuring and rolling out identity and device access policies in your organization, including specific settings for Microsoft Teams, Exchange Online, and SharePoint.</span></span> <span data-ttu-id="2784d-188">有关详细信息，请参阅“[标识和设备访问配置](../security/office-365-security/microsoft-365-policies-configurations.md)”。</span><span class="sxs-lookup"><span data-stu-id="2784d-188">For more information, see [Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md).</span></span>

## <a name="azure-ad-identity-protection"></a><span data-ttu-id="2784d-189">Azure AD 标识保护</span><span class="sxs-lookup"><span data-stu-id="2784d-189">Azure AD Identity Protection</span></span>

<span data-ttu-id="2784d-190">在此部分中，将了解如何配置策略，以防止凭据泄露（攻击者可以通过确定用户帐户名称和密码来获取访问组织的云服务和数据的权限）。</span><span class="sxs-lookup"><span data-stu-id="2784d-190">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="2784d-191">Azure AD Identity Protection 可提供多种方式来帮助阻止攻击者破坏用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="2784d-191">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="2784d-192">使用 Azure AD Identity Protection，可以：</span><span class="sxs-lookup"><span data-stu-id="2784d-192">With Azure AD Identity Protection, you can:</span></span>

|<span data-ttu-id="2784d-193">功能</span><span class="sxs-lookup"><span data-stu-id="2784d-193">Capability</span></span>|<span data-ttu-id="2784d-194">Description</span><span class="sxs-lookup"><span data-stu-id="2784d-194">Description</span></span>|
|:---------|:---------|
| <span data-ttu-id="2784d-195">确定并解决组织身份中的潜在漏洞</span><span class="sxs-lookup"><span data-stu-id="2784d-195">Determine and address potential vulnerabilities in your organization’s identities</span></span> | <span data-ttu-id="2784d-196">Azure AD 使用机器学习功能检测不正常和可疑活动，如登录和登录后活动。</span><span class="sxs-lookup"><span data-stu-id="2784d-196">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="2784d-197">通过使用此数据，Azure AD Identity Protection 会生成报告和警报，帮助你评估问题并执行操作。</span><span class="sxs-lookup"><span data-stu-id="2784d-197">Using this data, Azure AD Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="2784d-198">检测与组织身份相关的可疑操作并自动对其响应</span><span class="sxs-lookup"><span data-stu-id="2784d-198">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="2784d-199">可以配置基于风险的策略，该策略可在达到指定风险级别时自动响应检测到的问题。</span><span class="sxs-lookup"><span data-stu-id="2784d-199">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="2784d-200">除了 Azure AD 与 Microsoft Intune 提供的其他条件性访问控制以外，这些策略也可以自动阻止访问或采取纠正措施，包括密码重置和要求后续登录的 Azure 多因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="2784d-200">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span> |
| <span data-ttu-id="2784d-201">调查可疑事件并使用管理操作加以解决</span><span class="sxs-lookup"><span data-stu-id="2784d-201">Investigate suspicious incidents and resolve them with administrative actions</span></span> | <span data-ttu-id="2784d-p116">可以使用有关安全事件的信息来调查风险事件。提供的基本工作流可用于跟踪调查和启动修正操作（如密码重置）。</span><span class="sxs-lookup"><span data-stu-id="2784d-p116">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span> |
|||

<span data-ttu-id="2784d-204">请参阅[有关 Azure AD Identity Protection 的详细信息](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。</span><span class="sxs-lookup"><span data-stu-id="2784d-204">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="2784d-205">请参阅[启用 Azure AD Identity Protection 的步骤](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</span><span class="sxs-lookup"><span data-stu-id="2784d-205">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a><span data-ttu-id="2784d-206">用于 MFA 和身份验证的管理员技术资源</span><span class="sxs-lookup"><span data-stu-id="2784d-206">Admin technical resources for MFA and secure sign-ins</span></span>

- [<span data-ttu-id="2784d-207">适用于 Microsoft 365 的 MFA</span><span class="sxs-lookup"><span data-stu-id="2784d-207">MFA for Microsoft 365</span></span>](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [<span data-ttu-id="2784d-208">Microsoft 365 的识别指南</span><span class="sxs-lookup"><span data-stu-id="2784d-208">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="2784d-209">Azure Academy Azure AD 培训视频</span><span class="sxs-lookup"><span data-stu-id="2784d-209">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [<span data-ttu-id="2784d-210">配置多重身份验证注册策略</span><span class="sxs-lookup"><span data-stu-id="2784d-210">Configure the Azure Multi-Factor Authentication registration policy</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [<span data-ttu-id="2784d-211">标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="2784d-211">Identity and device access configurations</span></span>](../security/office-365-security/microsoft-365-policies-configurations.md)

## <a name="next-step"></a><span data-ttu-id="2784d-212">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2784d-212">Next step</span></span>

[<span data-ttu-id="2784d-213">管理用户帐户</span><span class="sxs-lookup"><span data-stu-id="2784d-213">Manage your user accounts</span></span>](manage-microsoft-365-accounts.md)