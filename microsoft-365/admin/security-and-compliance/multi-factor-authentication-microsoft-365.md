---
title: Microsoft 365 的多重身份验证
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 了解 Microsoft 365 中的多因素身份验证。
ms.openlocfilehash: 128296b7dbc37ba5ebffb25a87bce589f8e5a904
ms.sourcegitcommit: 185d62f41f6b173894ba6e3e87b11b2b5d02db58
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "44340819"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="17b74-103">Microsoft 365 的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="17b74-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="17b74-104">密码是对计算机或联机服务进行身份验证的最常用方法，但它们也最容易受到攻击。</span><span class="sxs-lookup"><span data-stu-id="17b74-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="17b74-105">用户可以选择轻松使用密码，并将相同的密码用于多个登录到不同的计算机和服务。</span><span class="sxs-lookup"><span data-stu-id="17b74-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="17b74-106">若要为登录提供额外的安全级别，必须使用多重身份验证（MFA），该身份验证使用密码（应为 "强"）和其他验证方法（基于）：</span><span class="sxs-lookup"><span data-stu-id="17b74-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="17b74-107">您对其具有不容易复制的内容，例如智能手机。</span><span class="sxs-lookup"><span data-stu-id="17b74-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="17b74-108">您唯一且 biologically 的内容，如您的指纹、面孔或其他生物特征属性。</span><span class="sxs-lookup"><span data-stu-id="17b74-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="17b74-109">只有在验证了用户的密码之后，才会再采用其他验证方法。</span><span class="sxs-lookup"><span data-stu-id="17b74-109">The additional verification method is not employed until after the user’s password has been verified.</span></span> <span data-ttu-id="17b74-110">通过 MFA，即使安全性较强的用户密码，攻击者也没有您的智能手机或指纹即可完成登录。</span><span class="sxs-lookup"><span data-stu-id="17b74-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="17b74-111">Microsoft 365 中的 MFA 支持</span><span class="sxs-lookup"><span data-stu-id="17b74-111">MFA support in Microsoft 365</span></span>
<span data-ttu-id="17b74-112">默认情况下，Microsoft 365 和 Office 365 支持对用户帐户进行 MFA，使用：</span><span class="sxs-lookup"><span data-stu-id="17b74-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="17b74-113">发送到要求用户键入验证代码的电话的短信。</span><span class="sxs-lookup"><span data-stu-id="17b74-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="17b74-114">电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="17b74-114">A phone call.</span></span>
- <span data-ttu-id="17b74-115">Microsoft 身份验证器智能电话应用程序。</span><span class="sxs-lookup"><span data-stu-id="17b74-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="17b74-116">在这两种情况下，MFA 登录使用的是 "与你有的事情不容易复制" 方法进行其他验证。</span><span class="sxs-lookup"><span data-stu-id="17b74-116">In both cases, the MFA sign-in is using the “something you have with you that is not easily duplicated” method for the additional verification.</span></span>
<span data-ttu-id="17b74-117">可以通过多种方式为 Microsoft 365 和 Office 365 启用 MFA：</span><span class="sxs-lookup"><span data-stu-id="17b74-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="17b74-118">使用安全默认值</span><span class="sxs-lookup"><span data-stu-id="17b74-118">With security defaults</span></span>
- <span data-ttu-id="17b74-119">使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="17b74-119">With Conditional Access policies</span></span>
- <span data-ttu-id="17b74-120">对于每个单独的用户帐户（不推荐）</span><span class="sxs-lookup"><span data-stu-id="17b74-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="17b74-121">这些方法基于 Microsoft 365 计划。</span><span class="sxs-lookup"><span data-stu-id="17b74-121">These ways are based on your Microsoft 365 plan.</span></span>
    
|<span data-ttu-id="17b74-122">套餐</span><span class="sxs-lookup"><span data-stu-id="17b74-122">Plan</span></span>  |<span data-ttu-id="17b74-123">建议</span><span class="sxs-lookup"><span data-stu-id="17b74-123">Recommendation</span></span>  | <span data-ttu-id="17b74-124">客户类型</span><span class="sxs-lookup"><span data-stu-id="17b74-124">Type of customer</span></span> |
|---------|---------|----------|
| <span data-ttu-id="17b74-125">所有 Microsoft 365 计划</span><span class="sxs-lookup"><span data-stu-id="17b74-125">All Microsoft 365 plans</span></span> | <span data-ttu-id="17b74-126">使用安全默认设置，这需要对所有用户帐户进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="17b74-126">Use security defaults, which require MFA for all user accounts.</span></span> <br> <span data-ttu-id="17b74-127">您还可以基于每个用户的帐户要求进行 MFA，但不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="17b74-127">You can also require MFA on a per-user account basis, but this is not recommended.</span></span> | <span data-ttu-id="17b74-128">小型企业</span><span class="sxs-lookup"><span data-stu-id="17b74-128">Small business</span></span> |
| <span data-ttu-id="17b74-129">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="17b74-129">Microsoft 365 Business Premium</span></span> <br><br> <span data-ttu-id="17b74-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="17b74-130">Microsoft 365 E3</span></span> <br><br> <span data-ttu-id="17b74-131">Azure Active Directory （Azure AD）高级 P1 许可证</span><span class="sxs-lookup"><span data-stu-id="17b74-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span> | <span data-ttu-id="17b74-132">使用条件访问策略根据组成员身份、应用或其他条件要求对用户帐户进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="17b74-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span> | <span data-ttu-id="17b74-133">小型企业到企业</span><span class="sxs-lookup"><span data-stu-id="17b74-133">Small business to enterprise</span></span> |
| <span data-ttu-id="17b74-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="17b74-134">Microsoft 365 E5</span></span> <br><br> <span data-ttu-id="17b74-135">Azure AD 高级 P2 许可证</span><span class="sxs-lookup"><span data-stu-id="17b74-135">Azure AD Premium P2 licenses</span></span> | <span data-ttu-id="17b74-136">使用 Azure AD 标识保护根据登录风险条件要求进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="17b74-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span> |  <span data-ttu-id="17b74-137">企业版</span><span class="sxs-lookup"><span data-stu-id="17b74-137">Enterprise</span></span> |
||||

### <a name="security-defaults"></a><span data-ttu-id="17b74-138">安全性默认值</span><span class="sxs-lookup"><span data-stu-id="17b74-138">Security defaults</span></span>

<span data-ttu-id="17b74-139">安全性默认值是在 2019 年 10 月 21 日之后创建的 Microsoft 365 和 Office 365 付费或试用版订阅的一项新功能。</span><span class="sxs-lookup"><span data-stu-id="17b74-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="17b74-140">这些订阅启用了安全默认设置，其中：</span><span class="sxs-lookup"><span data-stu-id="17b74-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="17b74-141">要求所有用户都使用与 Microsoft 身份验证器应用的 MFA。</span><span class="sxs-lookup"><span data-stu-id="17b74-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="17b74-142">阻止旧版身份验证。</span><span class="sxs-lookup"><span data-stu-id="17b74-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="17b74-143">用户有 14 天的时间从其智能手机中通过 Microsoft Authenticator 应用登录 MFA，自启用安全性默认值后首次登录起计。</span><span class="sxs-lookup"><span data-stu-id="17b74-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="17b74-144">14 天后，除非 MFA 注册完成，否则用户将无法登录。</span><span class="sxs-lookup"><span data-stu-id="17b74-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="17b74-145">安全性默认值可确保所有组织均对默认启用的用户登录具有基本的安全级别。</span><span class="sxs-lookup"><span data-stu-id="17b74-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="17b74-146">您可以禁用安全默认设置，以支持使用条件访问策略的 MFA。</span><span class="sxs-lookup"><span data-stu-id="17b74-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="17b74-147">您可以在 Azure 门户中的 Azure AD 的**属性**窗格中启用或禁用安全默认设置。</span><span class="sxs-lookup"><span data-stu-id="17b74-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="17b74-148">您可以使用任何 Microsoft 365 计划的安全性默认设置。</span><span class="sxs-lookup"><span data-stu-id="17b74-148">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="17b74-149">有关详细信息，请参阅此[安全性默认值概述](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="17b74-149">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> 

### <a name="conditional-access-policies"></a><span data-ttu-id="17b74-150">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="17b74-150">Conditional Access policies</span></span>

<span data-ttu-id="17b74-151">条件访问策略是一组规则，指定评估和允许登录的条件。</span><span class="sxs-lookup"><span data-stu-id="17b74-151">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="17b74-152">例如，你可以创建一个条件访问策略，指明：</span><span class="sxs-lookup"><span data-stu-id="17b74-152">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="17b74-153">如果用户帐户名是分配了 Exchange、用户、密码、安全性、SharePoint 或全局管理员角色的用户组的成员，则需要先进行 MFA，然后才能允许访问。</span><span class="sxs-lookup"><span data-stu-id="17b74-153">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="17b74-154">通过此策略，当为用户分配或取消分配了上述管理员角色时，你可以根据其组成员身份要求进行 MFA，而不是针对单个用户帐户进行 MFA 配置。</span><span class="sxs-lookup"><span data-stu-id="17b74-154">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="17b74-155">您还可以使用条件访问策略进行更高级的功能，例如，要求对特定应用进行 MFA，或在兼容设备（如运行 Windows 10 的便携式计算机）上完成登录。</span><span class="sxs-lookup"><span data-stu-id="17b74-155">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="17b74-156">在 Azure 门户中，从 Azure AD 的 "**安全**" 窗格中配置条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="17b74-156">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="17b74-157">您可以通过以下方式使用条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="17b74-157">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="17b74-158">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="17b74-158">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="17b74-159">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="17b74-159">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="17b74-160">Azure AD 高级 P1 和 Azure AD 高级 P2 许可证</span><span class="sxs-lookup"><span data-stu-id="17b74-160">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span> 

<span data-ttu-id="17b74-161">对于具有 Microsoft 365 商业高级版的小型企业，可以通过以下步骤轻松使用条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="17b74-161">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="17b74-162">创建一个组，以包含需要进行 MFA 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="17b74-162">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="17b74-163">启用 "**要求对全局管理员进行 MFA** " 策略。</span><span class="sxs-lookup"><span data-stu-id="17b74-163">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="17b74-164">使用以下设置创建基于组的条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="17b74-164">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="17b74-165">> 用户和组的工作分配：上述步骤1中的组名称。</span><span class="sxs-lookup"><span data-stu-id="17b74-165">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="17b74-166">云应用或操作 > 的工作分配：所有云应用。</span><span class="sxs-lookup"><span data-stu-id="17b74-166">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="17b74-167">访问控制 > 授予 > 授予访问权限 > 需要多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="17b74-167">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="17b74-168">启用该策略。</span><span class="sxs-lookup"><span data-stu-id="17b74-168">Enable the policy.</span></span>
5. <span data-ttu-id="17b74-169">将用户帐户添加到在上面的步骤1中创建的组并进行测试。</span><span class="sxs-lookup"><span data-stu-id="17b74-169">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="17b74-170">若要对其他用户帐户要求进行 MFA，请将其添加到在步骤1中创建的组。</span><span class="sxs-lookup"><span data-stu-id="17b74-170">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="17b74-171">通过此条件访问策略，您可以按自己的步调向用户展示 MFA 要求。</span><span class="sxs-lookup"><span data-stu-id="17b74-171">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="17b74-172">企业应使用[常见的条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)来配置以下策略：</span><span class="sxs-lookup"><span data-stu-id="17b74-172">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="17b74-173">要求对管理员执行 MFA</span><span class="sxs-lookup"><span data-stu-id="17b74-173">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="17b74-174">要求对所有用户执行 MFA</span><span class="sxs-lookup"><span data-stu-id="17b74-174">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="17b74-175">阻止传统身份验证</span><span class="sxs-lookup"><span data-stu-id="17b74-175">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="17b74-176">有关详细信息，请参阅此[条件访问概述](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="17b74-176">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="17b74-177">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="17b74-177">Azure AD Identity Protection</span></span>

<span data-ttu-id="17b74-178">使用 Azure AD Identity Protection，可以创建额外的条件访问策略，以便[在登录风险为中或高时需要进行 MFA](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)。</span><span class="sxs-lookup"><span data-stu-id="17b74-178">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="17b74-179">您可以使用 Azure AD 标识保护和基于风险的条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="17b74-179">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="17b74-180">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="17b74-180">Microsoft 365 E5</span></span>
- <span data-ttu-id="17b74-181">Azure AD 高级 P2 许可证</span><span class="sxs-lookup"><span data-stu-id="17b74-181">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="17b74-182">有关详细信息，请参阅此 [Azure AD 标识保护概述](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="17b74-182">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="mfa-for-an-individual-user-account-not-recommended"></a><span data-ttu-id="17b74-183">对单个用户帐户的 MFA （不推荐）</span><span class="sxs-lookup"><span data-stu-id="17b74-183">MFA for an individual user account (not recommended)</span></span>

<span data-ttu-id="17b74-184">应使用安全默认设置或条件访问策略来要求对用户帐户登录进行 MFA。但是，如果无法使用其中一种方法，Microsoft 强烈建议对具有管理员角色（尤其是全局管理员角色）的用户帐户进行 MFA，以进行任何大小订阅。</span><span class="sxs-lookup"><span data-stu-id="17b74-184">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span> 

<span data-ttu-id="17b74-185">您可以从 Microsoft 365 管理中心的 "**活动用户**" 窗格中为单个用户帐户启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="17b74-185">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="17b74-186">启用后，下次用户登录时，系统将提示他们注册 MFA，并选择和测试其他验证方法。</span><span class="sxs-lookup"><span data-stu-id="17b74-186">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="17b74-187">结合使用这些方法</span><span class="sxs-lookup"><span data-stu-id="17b74-187">Using these methods together</span></span>

<span data-ttu-id="17b74-188">下表显示了通过安全性默认值、条件访问策略和每用户帐户设置启用 MFA 的结果。</span><span class="sxs-lookup"><span data-stu-id="17b74-188">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="17b74-189">已启用</span><span class="sxs-lookup"><span data-stu-id="17b74-189">Enabled</span></span> | <span data-ttu-id="17b74-190">Disabled</span><span class="sxs-lookup"><span data-stu-id="17b74-190">Disabled</span></span> | <span data-ttu-id="17b74-191">辅助身份验证方法</span><span class="sxs-lookup"><span data-stu-id="17b74-191">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="17b74-192">**安全性默认值**</span><span class="sxs-lookup"><span data-stu-id="17b74-192">**Security defaults**</span></span> | <span data-ttu-id="17b74-193">无法使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="17b74-193">Can’t use Conditional Access policies</span></span> |   <span data-ttu-id="17b74-194">可以使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="17b74-194">Can use Conditional Access policies</span></span> | <span data-ttu-id="17b74-195">Microsoft Authenticator 应用</span><span class="sxs-lookup"><span data-stu-id="17b74-195">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="17b74-196">**条件访问策略**</span><span class="sxs-lookup"><span data-stu-id="17b74-196">**Conditional Access policies**</span></span> |<span data-ttu-id="17b74-197">如果已启用任何条件访问策略，则无法启用安全性默认值</span><span class="sxs-lookup"><span data-stu-id="17b74-197">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="17b74-198">如果已禁用所有条件访问策略，则可以启用安全性默认值</span><span class="sxs-lookup"><span data-stu-id="17b74-198">If all are disabled, you can enable security defaults</span></span> | <span data-ttu-id="17b74-199">由用户在 MFA 注册期间指定</span><span class="sxs-lookup"><span data-stu-id="17b74-199">User-specified during MFA registration</span></span> |
| <span data-ttu-id="17b74-200">**每用户帐户设置（不推荐）**</span><span class="sxs-lookup"><span data-stu-id="17b74-200">**Per-user account setting (not recommended)**</span></span> | <span data-ttu-id="17b74-201">由需要 MFA 的安全默认值和条件访问策略重写</span><span class="sxs-lookup"><span data-stu-id="17b74-201">Overridden by security defaults and Conditional Access policies requiring MFA</span></span> | <span data-ttu-id="17b74-202">由安全默认值和条件访问策略重写</span><span class="sxs-lookup"><span data-stu-id="17b74-202">Overridden by security defaults and Conditional Access policies</span></span> | <span data-ttu-id="17b74-203">由用户在 MFA 注册期间指定</span><span class="sxs-lookup"><span data-stu-id="17b74-203">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="17b74-204">如果启用了安全默认设置，则系统会提示用户在下一次登录时进行 MFA 注册和使用 Microsoft 身份验证器应用的所有新用户。</span><span class="sxs-lookup"><span data-stu-id="17b74-204">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

<span data-ttu-id="17b74-205">但是，如果用户具有可接收短信但无法运行 Microsoft 验证程序应用程序的较旧的电话，则可以对该特定用户帐户启用 MFA，并让它们使用文本代码其他验证方法注册这些步骤：</span><span class="sxs-lookup"><span data-stu-id="17b74-205">However, if a user has an older phone that can receive text messages but cannot run the Microsoft Authenticator app, you can enable MFA on that specific user account and have them register using the text code additional verification method with these steps:</span></span>

1. <span data-ttu-id="17b74-206">禁用 Azure 门户中的安全默认设置。</span><span class="sxs-lookup"><span data-stu-id="17b74-206">Disable security defaults in the Azure portal.</span></span>
2. <span data-ttu-id="17b74-207">为 Microsoft 365 管理中心中的用户帐户启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="17b74-207">Enable MFA for the user account in the Microsoft 365 admin center.</span></span>
3. <span data-ttu-id="17b74-208">让用户登录并注册 MFA 和文本代码身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="17b74-208">Have the user sign in and register for MFA and the text code authentication method.</span></span>
4. <span data-ttu-id="17b74-209">完成后，在 Azure 门户中启用安全默认设置</span><span class="sxs-lookup"><span data-stu-id="17b74-209">When complete, enable security defaults in the Azure portal</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="17b74-210">管理 MFA 设置的方法</span><span class="sxs-lookup"><span data-stu-id="17b74-210">Ways to manage MFA settings</span></span>

<span data-ttu-id="17b74-211">有两种管理 MFA 设置的方法。</span><span class="sxs-lookup"><span data-stu-id="17b74-211">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="17b74-212">在 Azure 门户中，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="17b74-212">In the Azure portal, you can:</span></span>

- <span data-ttu-id="17b74-213">启用和禁用安全默认设置</span><span class="sxs-lookup"><span data-stu-id="17b74-213">Enable and disable security defaults</span></span>
- <span data-ttu-id="17b74-214">配置条件访问策略</span><span class="sxs-lookup"><span data-stu-id="17b74-214">Configure Conditional Access policies</span></span>

<span data-ttu-id="17b74-215">在 Microsoft 365 管理中心，您可以配置每用户和服务 MFA 设置。</span><span class="sxs-lookup"><span data-stu-id="17b74-215">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="17b74-216">下一步</span><span class="sxs-lookup"><span data-stu-id="17b74-216">Your next step</span></span>

[<span data-ttu-id="17b74-217">为 Microsoft 365 设置 MFA</span><span class="sxs-lookup"><span data-stu-id="17b74-217">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

