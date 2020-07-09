---
title: 适用于 Microsoft 365 的 Multi-Factor Authentication
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Microsoft 365 中的多因素身份验证。
ms.openlocfilehash: 71a61c51d2813880cad782d132679fa413ada987
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083582"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="970a9-103">适用于 Microsoft 365 的 Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="970a9-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="970a9-104">密码是对计算机或联机服务进行身份验证的最常用方法，但它们也最容易受到攻击。</span><span class="sxs-lookup"><span data-stu-id="970a9-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="970a9-105">用户可以选择轻松使用密码，并将相同的密码用于多个登录到不同的计算机和服务。</span><span class="sxs-lookup"><span data-stu-id="970a9-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="970a9-106">若要为登录提供额外的安全级别，必须使用多重身份验证（MFA），该身份验证使用密码（应为 "强"）和其他验证方法（基于）：</span><span class="sxs-lookup"><span data-stu-id="970a9-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="970a9-107">您对其具有不容易复制的内容，例如智能手机。</span><span class="sxs-lookup"><span data-stu-id="970a9-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="970a9-108">您唯一且 biologically 的内容，如您的指纹、面孔或其他生物特征属性。</span><span class="sxs-lookup"><span data-stu-id="970a9-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="970a9-109">只有在验证了用户的密码之后，才会再采用其他验证方法。</span><span class="sxs-lookup"><span data-stu-id="970a9-109">The additional verification method is not employed until after the user’s password has been verified.</span></span> <span data-ttu-id="970a9-110">通过 MFA，即使安全性较强的用户密码，攻击者也没有您的智能手机或指纹即可完成登录。</span><span class="sxs-lookup"><span data-stu-id="970a9-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="970a9-111">Microsoft 365 中的 MFA 支持</span><span class="sxs-lookup"><span data-stu-id="970a9-111">MFA support in Microsoft 365</span></span>
<span data-ttu-id="970a9-112">默认情况下，Microsoft 365 和 Office 365 支持对用户帐户进行 MFA，使用：</span><span class="sxs-lookup"><span data-stu-id="970a9-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="970a9-113">发送到要求用户键入验证代码的电话的短信。</span><span class="sxs-lookup"><span data-stu-id="970a9-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="970a9-114">电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="970a9-114">A phone call.</span></span>
- <span data-ttu-id="970a9-115">Microsoft 身份验证器智能电话应用程序。</span><span class="sxs-lookup"><span data-stu-id="970a9-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="970a9-116">在这两种情况下，MFA 登录使用的是 "与你有的事情不容易复制" 方法进行其他验证。</span><span class="sxs-lookup"><span data-stu-id="970a9-116">In both cases, the MFA sign-in is using the “something you have with you that is not easily duplicated” method for the additional verification.</span></span>
<span data-ttu-id="970a9-117">可以通过多种方式为 Microsoft 365 和 Office 365 启用 MFA：</span><span class="sxs-lookup"><span data-stu-id="970a9-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="970a9-118">使用安全默认值</span><span class="sxs-lookup"><span data-stu-id="970a9-118">With security defaults</span></span>
- <span data-ttu-id="970a9-119">使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="970a9-119">With Conditional Access policies</span></span>
- <span data-ttu-id="970a9-120">对于每个单独的用户帐户（不推荐）</span><span class="sxs-lookup"><span data-stu-id="970a9-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="970a9-121">这些方法基于 Microsoft 365 计划。</span><span class="sxs-lookup"><span data-stu-id="970a9-121">These ways are based on your Microsoft 365 plan.</span></span>
    
|<span data-ttu-id="970a9-122">套餐</span><span class="sxs-lookup"><span data-stu-id="970a9-122">Plan</span></span>  |<span data-ttu-id="970a9-123">建议</span><span class="sxs-lookup"><span data-stu-id="970a9-123">Recommendation</span></span>  | <span data-ttu-id="970a9-124">客户类型</span><span class="sxs-lookup"><span data-stu-id="970a9-124">Type of customer</span></span> |
|---------|---------|----------|
| <span data-ttu-id="970a9-125">所有 Microsoft 365 计划</span><span class="sxs-lookup"><span data-stu-id="970a9-125">All Microsoft 365 plans</span></span> | <span data-ttu-id="970a9-126">使用安全默认设置，这需要对所有用户帐户进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="970a9-126">Use security defaults, which require MFA for all user accounts.</span></span> <br> <span data-ttu-id="970a9-127">您还可以基于每个用户的帐户要求进行 MFA，但不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="970a9-127">You can also require MFA on a per-user account basis, but this is not recommended.</span></span> | <span data-ttu-id="970a9-128">小型企业</span><span class="sxs-lookup"><span data-stu-id="970a9-128">Small business</span></span> |
| <span data-ttu-id="970a9-129">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="970a9-129">Microsoft 365 Business Premium</span></span> <br><br> <span data-ttu-id="970a9-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="970a9-130">Microsoft 365 E3</span></span> <br><br> <span data-ttu-id="970a9-131">Azure Active Directory （Azure AD）高级 P1 许可证</span><span class="sxs-lookup"><span data-stu-id="970a9-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span> | <span data-ttu-id="970a9-132">使用条件访问策略根据组成员身份、应用或其他条件要求对用户帐户进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="970a9-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span> | <span data-ttu-id="970a9-133">小型企业到企业</span><span class="sxs-lookup"><span data-stu-id="970a9-133">Small business to enterprise</span></span> |
| <span data-ttu-id="970a9-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="970a9-134">Microsoft 365 E5</span></span> <br><br> <span data-ttu-id="970a9-135">Azure AD 高级 P2 许可证</span><span class="sxs-lookup"><span data-stu-id="970a9-135">Azure AD Premium P2 licenses</span></span> | <span data-ttu-id="970a9-136">使用 Azure AD 标识保护根据登录风险条件要求进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="970a9-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span> |  <span data-ttu-id="970a9-137">企业版</span><span class="sxs-lookup"><span data-stu-id="970a9-137">Enterprise</span></span> |
||||

### <a name="security-defaults"></a><span data-ttu-id="970a9-138">安全性默认值</span><span class="sxs-lookup"><span data-stu-id="970a9-138">Security defaults</span></span>

<span data-ttu-id="970a9-139">安全性默认值是在 2019 年 10 月 21 日之后创建的 Microsoft 365 和 Office 365 付费或试用版订阅的一项新功能。</span><span class="sxs-lookup"><span data-stu-id="970a9-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="970a9-140">这些订阅启用了安全默认设置，其中：</span><span class="sxs-lookup"><span data-stu-id="970a9-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="970a9-141">要求所有用户都使用与 Microsoft 身份验证器应用的 MFA。</span><span class="sxs-lookup"><span data-stu-id="970a9-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="970a9-142">阻止旧版身份验证。</span><span class="sxs-lookup"><span data-stu-id="970a9-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="970a9-143">用户有 14 天的时间从其智能手机中通过 Microsoft Authenticator 应用登录 MFA，自启用安全性默认值后首次登录起计。</span><span class="sxs-lookup"><span data-stu-id="970a9-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="970a9-144">14 天后，除非 MFA 注册完成，否则用户将无法登录。</span><span class="sxs-lookup"><span data-stu-id="970a9-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="970a9-145">安全性默认值可确保所有组织均对默认启用的用户登录具有基本的安全级别。</span><span class="sxs-lookup"><span data-stu-id="970a9-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="970a9-146">您可以禁用安全默认设置，以支持使用条件访问策略的 MFA。</span><span class="sxs-lookup"><span data-stu-id="970a9-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="970a9-147">您可以在 Azure 门户中的 Azure AD 的**属性**窗格中启用或禁用安全默认设置。</span><span class="sxs-lookup"><span data-stu-id="970a9-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

!["目录属性" 页的图片。](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="970a9-149">您可以使用任何 Microsoft 365 计划的安全性默认设置。</span><span class="sxs-lookup"><span data-stu-id="970a9-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="970a9-150">有关详细信息，请参阅此[安全性默认值概述](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="970a9-150">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> 

### <a name="conditional-access-policies"></a><span data-ttu-id="970a9-151">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="970a9-151">Conditional Access policies</span></span>

<span data-ttu-id="970a9-152">条件访问策略是一组规则，指定评估和允许登录的条件。</span><span class="sxs-lookup"><span data-stu-id="970a9-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="970a9-153">例如，你可以创建一个条件访问策略，指明：</span><span class="sxs-lookup"><span data-stu-id="970a9-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="970a9-154">如果用户帐户名是分配了 Exchange、用户、密码、安全性、SharePoint 或全局管理员角色的用户组的成员，则需要先进行 MFA，然后才能允许访问。</span><span class="sxs-lookup"><span data-stu-id="970a9-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="970a9-155">通过此策略，当为用户分配或取消分配了上述管理员角色时，你可以根据其组成员身份要求进行 MFA，而不是针对单个用户帐户进行 MFA 配置。</span><span class="sxs-lookup"><span data-stu-id="970a9-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="970a9-156">您还可以使用条件访问策略进行更高级的功能，例如，要求对特定应用进行 MFA，或在兼容设备（如运行 Windows 10 的便携式计算机）上完成登录。</span><span class="sxs-lookup"><span data-stu-id="970a9-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="970a9-157">在 Azure 门户中，从 Azure AD 的 "**安全**" 窗格中配置条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="970a9-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Picure 条件访问的菜单选项](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="970a9-159">您可以通过以下方式使用条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="970a9-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="970a9-160">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="970a9-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="970a9-161">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="970a9-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="970a9-162">Azure AD 高级 P1 和 Azure AD 高级 P2 许可证</span><span class="sxs-lookup"><span data-stu-id="970a9-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span> 

<span data-ttu-id="970a9-163">对于具有 Microsoft 365 商业高级版的小型企业，可以通过以下步骤轻松使用条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="970a9-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="970a9-164">创建一个组，以包含需要进行 MFA 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="970a9-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="970a9-165">启用 "**要求对全局管理员进行 MFA** " 策略。</span><span class="sxs-lookup"><span data-stu-id="970a9-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="970a9-166">使用以下设置创建基于组的条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="970a9-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="970a9-167">> 用户和组的工作分配：上述步骤1中的组名称。</span><span class="sxs-lookup"><span data-stu-id="970a9-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="970a9-168">云应用或操作 > 的工作分配：所有云应用。</span><span class="sxs-lookup"><span data-stu-id="970a9-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="970a9-169">访问控制 > 授予 > 授予访问权限 > 需要多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="970a9-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="970a9-170">启用该策略。</span><span class="sxs-lookup"><span data-stu-id="970a9-170">Enable the policy.</span></span>
5. <span data-ttu-id="970a9-171">将用户帐户添加到在上面的步骤1中创建的组并进行测试。</span><span class="sxs-lookup"><span data-stu-id="970a9-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="970a9-172">若要对其他用户帐户要求进行 MFA，请将其添加到在步骤1中创建的组。</span><span class="sxs-lookup"><span data-stu-id="970a9-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="970a9-173">通过此条件访问策略，您可以按自己的步调向用户展示 MFA 要求。</span><span class="sxs-lookup"><span data-stu-id="970a9-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="970a9-174">企业应使用[常见的条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)来配置以下策略：</span><span class="sxs-lookup"><span data-stu-id="970a9-174">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="970a9-175">要求对管理员执行 MFA</span><span class="sxs-lookup"><span data-stu-id="970a9-175">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="970a9-176">要求对所有用户执行 MFA</span><span class="sxs-lookup"><span data-stu-id="970a9-176">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="970a9-177">阻止传统身份验证</span><span class="sxs-lookup"><span data-stu-id="970a9-177">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="970a9-178">有关详细信息，请参阅此[条件访问概述](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="970a9-178">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="970a9-179">Azure AD 标识保护</span><span class="sxs-lookup"><span data-stu-id="970a9-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="970a9-180">使用 Azure AD Identity Protection，可以创建额外的条件访问策略，以便[在登录风险为中或高时需要进行 MFA](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)。</span><span class="sxs-lookup"><span data-stu-id="970a9-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="970a9-181">您可以使用 Azure AD 标识保护和基于风险的条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="970a9-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="970a9-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="970a9-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="970a9-183">Azure AD 高级 P2 许可证</span><span class="sxs-lookup"><span data-stu-id="970a9-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="970a9-184">有关详细信息，请参阅此 [Azure AD 标识保护概述](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="970a9-184">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="mfa-for-an-individual-user-account-not-recommended"></a><span data-ttu-id="970a9-185">对单个用户帐户的 MFA （不推荐）</span><span class="sxs-lookup"><span data-stu-id="970a9-185">MFA for an individual user account (not recommended)</span></span>

<span data-ttu-id="970a9-186">应使用安全默认设置或条件访问策略来要求对用户帐户登录进行 MFA。但是，如果无法使用其中一种方法，Microsoft 强烈建议对具有管理员角色（尤其是全局管理员角色）的用户帐户进行 MFA，以进行任何大小订阅。</span><span class="sxs-lookup"><span data-stu-id="970a9-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span> 

<span data-ttu-id="970a9-187">您可以从 Microsoft 365 管理中心的 "**活动用户**" 窗格中为单个用户帐户启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="970a9-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

!["活动用户" 页面上的多因素身份验证选项的图片](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="970a9-189">启用后，下次用户登录时，系统将提示他们注册 MFA，并选择和测试其他验证方法。</span><span class="sxs-lookup"><span data-stu-id="970a9-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="970a9-190">结合使用这些方法</span><span class="sxs-lookup"><span data-stu-id="970a9-190">Using these methods together</span></span>

<span data-ttu-id="970a9-191">下表显示了通过安全性默认值、条件访问策略和每用户帐户设置启用 MFA 的结果。</span><span class="sxs-lookup"><span data-stu-id="970a9-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="970a9-192">已启用</span><span class="sxs-lookup"><span data-stu-id="970a9-192">Enabled</span></span> | <span data-ttu-id="970a9-193">Disabled</span><span class="sxs-lookup"><span data-stu-id="970a9-193">Disabled</span></span> | <span data-ttu-id="970a9-194">辅助身份验证方法</span><span class="sxs-lookup"><span data-stu-id="970a9-194">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="970a9-195">**安全性默认值**</span><span class="sxs-lookup"><span data-stu-id="970a9-195">**Security defaults**</span></span> | <span data-ttu-id="970a9-196">无法使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="970a9-196">Can’t use Conditional Access policies</span></span> |   <span data-ttu-id="970a9-197">可以使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="970a9-197">Can use Conditional Access policies</span></span> | <span data-ttu-id="970a9-198">Microsoft Authenticator 应用</span><span class="sxs-lookup"><span data-stu-id="970a9-198">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="970a9-199">**条件访问策略**</span><span class="sxs-lookup"><span data-stu-id="970a9-199">**Conditional Access policies**</span></span> |<span data-ttu-id="970a9-200">如果已启用任何条件访问策略，则无法启用安全性默认值</span><span class="sxs-lookup"><span data-stu-id="970a9-200">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="970a9-201">如果已禁用所有条件访问策略，则可以启用安全性默认值</span><span class="sxs-lookup"><span data-stu-id="970a9-201">If all are disabled, you can enable security defaults</span></span> | <span data-ttu-id="970a9-202">由用户在 MFA 注册期间指定</span><span class="sxs-lookup"><span data-stu-id="970a9-202">User-specified during MFA registration</span></span> |
| <span data-ttu-id="970a9-203">**每用户帐户设置（不推荐）**</span><span class="sxs-lookup"><span data-stu-id="970a9-203">**Per-user account setting (not recommended)**</span></span> | <span data-ttu-id="970a9-204">覆盖在每次登录时要求进行 MFA 的安全默认值和条件访问策略</span><span class="sxs-lookup"><span data-stu-id="970a9-204">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span> | <span data-ttu-id="970a9-205">由安全默认值和条件访问策略重写</span><span class="sxs-lookup"><span data-stu-id="970a9-205">Overridden by security defaults and Conditional Access policies</span></span> | <span data-ttu-id="970a9-206">由用户在 MFA 注册期间指定</span><span class="sxs-lookup"><span data-stu-id="970a9-206">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="970a9-207">如果启用了安全默认设置，则系统会提示用户在下一次登录时进行 MFA 注册和使用 Microsoft 身份验证器应用的所有新用户。</span><span class="sxs-lookup"><span data-stu-id="970a9-207">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="970a9-208">管理 MFA 设置的方法</span><span class="sxs-lookup"><span data-stu-id="970a9-208">Ways to manage MFA settings</span></span>

<span data-ttu-id="970a9-209">有两种管理 MFA 设置的方法。</span><span class="sxs-lookup"><span data-stu-id="970a9-209">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="970a9-210">在 Azure 门户中，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="970a9-210">In the Azure portal, you can:</span></span>

- <span data-ttu-id="970a9-211">启用和禁用安全默认设置</span><span class="sxs-lookup"><span data-stu-id="970a9-211">Enable and disable security defaults</span></span>
- <span data-ttu-id="970a9-212">配置条件访问策略</span><span class="sxs-lookup"><span data-stu-id="970a9-212">Configure Conditional Access policies</span></span>

<span data-ttu-id="970a9-213">在 Microsoft 365 管理中心，您可以配置每用户和服务 MFA 设置。</span><span class="sxs-lookup"><span data-stu-id="970a9-213">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="970a9-214">下一步</span><span class="sxs-lookup"><span data-stu-id="970a9-214">Your next step</span></span>

[<span data-ttu-id="970a9-215">为 Microsoft 365 设置 MFA</span><span class="sxs-lookup"><span data-stu-id="970a9-215">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

