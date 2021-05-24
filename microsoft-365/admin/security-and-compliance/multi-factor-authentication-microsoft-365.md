---
title: 适用于 Microsoft 365 的 Multi-Factor Authentication
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: MFA (多重身份验证) 密码（应该很强）和其他验证方法。
ms.openlocfilehash: 84d26d0a9908e51ce734e71961d4643a2df3471b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623685"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="8dbb1-103">适用于 Microsoft 365 的 Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="8dbb1-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="8dbb1-104">密码是验证计算机或联机服务的登录的最常见方法，但它们也是最易受攻击的。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="8dbb1-105">用户可以选择简单密码，并使用相同的密码进行不同计算机和服务的多个登录。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="8dbb1-106">若要为登录提供一个额外的安全级别，必须使用多重身份验证 (MFA) ，它同时使用应强的密码和基于：</span><span class="sxs-lookup"><span data-stu-id="8dbb1-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="8dbb1-107">你拥有且不易复制的项，例如智能手机。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="8dbb1-108">你唯一且明显拥有的属性，例如指纹、面部或其他生物识别属性。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="8dbb1-109">在验证用户密码之前，不会采用其他验证方法。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="8dbb1-110">使用 MFA，即使强用户密码受到威胁，攻击者也无需智能手机或指纹来完成登录。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="8dbb1-111">Microsoft 365 中的 MFA 支持</span><span class="sxs-lookup"><span data-stu-id="8dbb1-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="8dbb1-112">默认情况下，Microsoft 365和Office 365都支持用户帐户的 MFA，使用：</span><span class="sxs-lookup"><span data-stu-id="8dbb1-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="8dbb1-113">发送到电话的短信，要求用户键入验证码。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="8dbb1-114">电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-114">A phone call.</span></span>
- <span data-ttu-id="8dbb1-115">智能Microsoft Authenticator应用程序。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="8dbb1-116">在这两种情况下，MFA 登录都使用"你拥有且不可轻易复制的项"方法进行附加验证。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="8dbb1-117">可以通过多种方式为用户和用户启用 MFA Microsoft 365 Office 365：</span><span class="sxs-lookup"><span data-stu-id="8dbb1-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="8dbb1-118">使用安全默认值</span><span class="sxs-lookup"><span data-stu-id="8dbb1-118">With security defaults</span></span>
- <span data-ttu-id="8dbb1-119">使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="8dbb1-119">With Conditional Access policies</span></span>
- <span data-ttu-id="8dbb1-120">对于每个单独的用户帐户， (建议) </span><span class="sxs-lookup"><span data-stu-id="8dbb1-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="8dbb1-121">这些方法基于你的Microsoft 365计划。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="8dbb1-122">计划</span><span class="sxs-lookup"><span data-stu-id="8dbb1-122">Plan</span></span>|<span data-ttu-id="8dbb1-123">建议</span><span class="sxs-lookup"><span data-stu-id="8dbb1-123">Recommendation</span></span>|<span data-ttu-id="8dbb1-124">客户类型</span><span class="sxs-lookup"><span data-stu-id="8dbb1-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="8dbb1-125">所有Microsoft 365计划</span><span class="sxs-lookup"><span data-stu-id="8dbb1-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="8dbb1-126">使用安全默认值，这要求所有用户帐户使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="8dbb1-127">还可以对单个用户帐户配置每用户 MFA，但不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="8dbb1-128">小型企业</span><span class="sxs-lookup"><span data-stu-id="8dbb1-128">Small business</span></span>|
|<span data-ttu-id="8dbb1-129">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="8dbb1-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="8dbb1-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="8dbb1-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="8dbb1-131">Azure Active Directory (Azure AD) 高级版 P1 许可证</span><span class="sxs-lookup"><span data-stu-id="8dbb1-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="8dbb1-132">使用条件访问策略根据组成员身份、应用或其他条件要求用户帐户进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="8dbb1-133">小型企业到企业</span><span class="sxs-lookup"><span data-stu-id="8dbb1-133">Small business to enterprise</span></span>|
|<span data-ttu-id="8dbb1-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8dbb1-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="8dbb1-135">Azure AD 高级版 P2 许可证</span><span class="sxs-lookup"><span data-stu-id="8dbb1-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="8dbb1-136">使用 Azure AD Identity Protection 根据登录风险条件要求 MFA。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="8dbb1-137">企业版</span><span class="sxs-lookup"><span data-stu-id="8dbb1-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="8dbb1-138">安全性默认值</span><span class="sxs-lookup"><span data-stu-id="8dbb1-138">Security defaults</span></span>

<span data-ttu-id="8dbb1-139">安全性默认值是在 2019 年 10 月 21 日之后创建的 Microsoft 365 和 Office 365 付费或试用版订阅的一项新功能。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="8dbb1-140">这些订阅启用安全默认值，即：</span><span class="sxs-lookup"><span data-stu-id="8dbb1-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="8dbb1-141">要求所有用户将 MFA 用于 Microsoft Authenticator 应用。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="8dbb1-142">阻止旧式身份验证。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="8dbb1-143">用户有 14 天的时间从其智能手机中通过 Microsoft Authenticator 应用登录 MFA，自启用安全性默认值后首次登录起计。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="8dbb1-144">14 天后，除非 MFA 注册完成，否则用户将无法登录。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="8dbb1-145">安全性默认值可确保所有组织均对默认启用的用户登录具有基本的安全级别。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="8dbb1-146">可以禁用安全默认值，以使用条件访问策略支持 MFA。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="8dbb1-147">可以在 Azure 门户的 Azure  AD 的"属性"窗格中启用或禁用安全默认值。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![目录属性页的图片。](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="8dbb1-149">可以将安全默认值用于任何Microsoft 365计划中。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="8dbb1-150">有关详细信息，请参阅此[安全性默认值概述](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-150">For more information, see this [overview of security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="8dbb1-151">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="8dbb1-151">Conditional Access policies</span></span>

<span data-ttu-id="8dbb1-152">条件访问策略是一组规则，指定评估和允许登录的条件。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="8dbb1-153">例如，你可以创建一个条件访问策略，指明：</span><span class="sxs-lookup"><span data-stu-id="8dbb1-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="8dbb1-154">如果用户帐户名是分配了 Exchange、用户、密码、安全性、SharePoint 或全局管理员角色的用户组的成员，则需要先进行 MFA，然后才能允许访问。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="8dbb1-155">通过此策略，当为用户分配或取消分配了上述管理员角色时，你可以根据其组成员身份要求进行 MFA，而不是针对单个用户帐户进行 MFA 配置。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="8dbb1-156">还可以将条件访问策略用于更高级的功能，例如要求特定应用使用 MFA，或者从兼容设备（如运行 Windows 10）完成登录。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="8dbb1-157">在 Azure 门户的Azure AD 安全窗格中配置条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![条件访问的菜单选项的图片](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="8dbb1-159">可以将条件访问策略与：</span><span class="sxs-lookup"><span data-stu-id="8dbb1-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="8dbb1-160">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="8dbb1-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="8dbb1-161">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="8dbb1-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="8dbb1-162">Azure AD 高级版 P1 和 Azure AD 高级版 P2 许可证</span><span class="sxs-lookup"><span data-stu-id="8dbb1-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="8dbb1-163">对于具有 Microsoft 365 商业高级版 的小型企业，可以通过以下步骤轻松使用条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="8dbb1-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="8dbb1-164">创建一个组以包含需要 MFA 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="8dbb1-165">启用" **要求全局管理员使用 MFA"** 策略。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="8dbb1-166">使用这些设置创建基于组的条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="8dbb1-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="8dbb1-167">分配>用户和组：上面的步骤 1 中的组名称。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="8dbb1-168">分配>云应用或操作：所有云应用。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="8dbb1-169">访问控制>授予>授予>要求多重身份验证的权限。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="8dbb1-170">启用策略。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-170">Enable the policy.</span></span>
5. <span data-ttu-id="8dbb1-171">将用户帐户添加到上述步骤 1 中创建的组并进行测试。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="8dbb1-172">若要要求为其他用户帐户使用 MFA，请将其添加到步骤 1 中创建的组中。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="8dbb1-173">此条件访问策略允许你按自己的节奏向用户推出 MFA 要求。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="8dbb1-174">企业应该 [使用常见条件访问策略](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) 来配置以下策略：</span><span class="sxs-lookup"><span data-stu-id="8dbb1-174">Enterprises should use [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="8dbb1-175">要求对管理员执行 MFA</span><span class="sxs-lookup"><span data-stu-id="8dbb1-175">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="8dbb1-176">要求对所有用户执行 MFA</span><span class="sxs-lookup"><span data-stu-id="8dbb1-176">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="8dbb1-177">阻止旧身份验证</span><span class="sxs-lookup"><span data-stu-id="8dbb1-177">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="8dbb1-178">有关详细信息，请参阅此[条件访问概述](/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-178">For more information, see this [overview of Conditional Access](/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="8dbb1-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="8dbb1-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="8dbb1-180">借助 Azure AD Identity Protection，你可以创建其他条件访问策略，要求在登录风险中等或较高时[进行 MFA。](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="8dbb1-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="8dbb1-181">可以将 Azure AD Identity Protection 和基于风险的条件访问策略与：</span><span class="sxs-lookup"><span data-stu-id="8dbb1-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="8dbb1-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8dbb1-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="8dbb1-183">Azure AD 高级版 P2 许可证</span><span class="sxs-lookup"><span data-stu-id="8dbb1-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="8dbb1-184">有关详细信息，请参阅此 [Azure AD 标识保护概述](/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-184">For more information, see this [overview of Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="8dbb1-185">不建议使用旧版每 (MFA) </span><span class="sxs-lookup"><span data-stu-id="8dbb1-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="8dbb1-186">你应该使用安全默认值或条件访问策略来要求用户帐户登录使用 MFA。但是，如果无法使用其中任何一个，Microsoft 强烈建议为具有管理员角色的用户帐户（尤其是 全局管理员角色）执行 MFA。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="8dbb1-187">从管理中心的"活动用户"窗格中为单个用户帐户Microsoft 365 MFA。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

!["活动用户"页面上多重身份验证选项的图片](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="8dbb1-189">启用后，用户下次登录时，系统将提示他们注册 MFA，并选择并测试其他验证方法。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="8dbb1-190">结合使用这些方法</span><span class="sxs-lookup"><span data-stu-id="8dbb1-190">Using these methods together</span></span>

<span data-ttu-id="8dbb1-191">下表显示了通过安全性默认值、条件访问策略和每用户帐户设置启用 MFA 的结果。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

||<span data-ttu-id="8dbb1-192">已启用</span><span class="sxs-lookup"><span data-stu-id="8dbb1-192">Enabled</span></span>|<span data-ttu-id="8dbb1-193">Disabled</span><span class="sxs-lookup"><span data-stu-id="8dbb1-193">Disabled</span></span>|<span data-ttu-id="8dbb1-194">辅助身份验证方法</span><span class="sxs-lookup"><span data-stu-id="8dbb1-194">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="8dbb1-195">**安全性默认值**</span><span class="sxs-lookup"><span data-stu-id="8dbb1-195">**Security defaults**</span></span>|<span data-ttu-id="8dbb1-196">不使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="8dbb1-196">Can't use Conditional Access policies</span></span>|<span data-ttu-id="8dbb1-197">可以使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="8dbb1-197">Can use Conditional Access policies</span></span>|<span data-ttu-id="8dbb1-198">Microsoft Authenticator 应用</span><span class="sxs-lookup"><span data-stu-id="8dbb1-198">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="8dbb1-199">**条件访问策略**</span><span class="sxs-lookup"><span data-stu-id="8dbb1-199">**Conditional Access policies**</span></span>|<span data-ttu-id="8dbb1-200">如果启用了任何安全默认值，则不能启用安全默认值</span><span class="sxs-lookup"><span data-stu-id="8dbb1-200">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="8dbb1-201">如果已禁用所有条件访问策略，则可以启用安全性默认值</span><span class="sxs-lookup"><span data-stu-id="8dbb1-201">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="8dbb1-202">由用户在 MFA 注册期间指定</span><span class="sxs-lookup"><span data-stu-id="8dbb1-202">User-specified during MFA registration</span></span>|
|<span data-ttu-id="8dbb1-203">**不建议使用旧版每 (MFA)**</span><span class="sxs-lookup"><span data-stu-id="8dbb1-203">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="8dbb1-204">替代每次登录时要求 MFA 的安全默认值和条件访问策略</span><span class="sxs-lookup"><span data-stu-id="8dbb1-204">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="8dbb1-205">由安全默认值和条件访问策略替代</span><span class="sxs-lookup"><span data-stu-id="8dbb1-205">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="8dbb1-206">由用户在 MFA 注册期间指定</span><span class="sxs-lookup"><span data-stu-id="8dbb1-206">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="8dbb1-207">如果启用安全默认值，将提示所有新用户在下次登录时进行 MFA 注册Microsoft Authenticator使用应用。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-207">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="8dbb1-208">管理 MFA 设置的方法</span><span class="sxs-lookup"><span data-stu-id="8dbb1-208">Ways to manage MFA settings</span></span>

<span data-ttu-id="8dbb1-209">有两种方法可以管理 MFA 设置。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-209">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="8dbb1-210">在 Azure 门户中，你可以：</span><span class="sxs-lookup"><span data-stu-id="8dbb1-210">In the Azure portal, you can:</span></span>

- <span data-ttu-id="8dbb1-211">启用和禁用安全默认值</span><span class="sxs-lookup"><span data-stu-id="8dbb1-211">Enable and disable security defaults</span></span>
- <span data-ttu-id="8dbb1-212">配置条件访问策略</span><span class="sxs-lookup"><span data-stu-id="8dbb1-212">Configure Conditional Access policies</span></span>

<span data-ttu-id="8dbb1-213">在Microsoft 365管理中心，可以配置每用户和服务 MFA 设置。</span><span class="sxs-lookup"><span data-stu-id="8dbb1-213">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="8dbb1-214">下一步</span><span class="sxs-lookup"><span data-stu-id="8dbb1-214">Your next step</span></span>

[<span data-ttu-id="8dbb1-215">为组织设置 MFA Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8dbb1-215">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

## <a name="related-content"></a><span data-ttu-id="8dbb1-216">相关内容</span><span class="sxs-lookup"><span data-stu-id="8dbb1-216">Related content</span></span>

<span data-ttu-id="8dbb1-217">[打开多因素身份验证](../../business-video/turn-on-mfa.md) (视频) </span><span class="sxs-lookup"><span data-stu-id="8dbb1-217">[Turn on multi-factor authentication](../../business-video/turn-on-mfa.md) (video)</span></span>\
<span data-ttu-id="8dbb1-218">[打开手机的多重身份验证](../../business-video/set-up-mfa.md)（视频）</span><span class="sxs-lookup"><span data-stu-id="8dbb1-218">[Turn on multi-factor authentication for your phone](../../business-video/set-up-mfa.md) (video)</span></span>