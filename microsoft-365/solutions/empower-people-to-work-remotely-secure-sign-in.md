---
title: 步骤 1. 通过 MFA 提高远程工作者的登录安全性
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 要求远程工作者通过多重身份验证 (MFA) 登录。
ms.openlocfilehash: aa9b122ca18c4d8a8123914ee2d29d41c9ec789e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681452"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a><span data-ttu-id="ff173-104">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="ff173-104">Step 1.</span></span> <span data-ttu-id="ff173-105">通过 MFA 提高远程工作者的登录安全性</span><span class="sxs-lookup"><span data-stu-id="ff173-105">Increase sign-in security for remote workers with MFA</span></span>

<span data-ttu-id="ff173-106">要提高远程工作者的登录安全性，请使用多重身份验证 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="ff173-106">To increase the security of sign-ins of your remote workers, use multi-factor authentication (MFA).</span></span> <span data-ttu-id="ff173-107">MFA 要求用户登录受用户帐户密码之外的其他验证约束。</span><span class="sxs-lookup"><span data-stu-id="ff173-107">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="ff173-108">即使恶意用户确定了用户帐户密码，还必须能够响应其他验证（如发送到智能手机的短信）才能获得访问权限。</span><span class="sxs-lookup"><span data-stu-id="ff173-108">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![正确的密码和其他验证会导致登录成功](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="ff173-110">对于所有用户（包括远程工作者，特别是管理员），Microsoft 强烈建议实施 MFA。</span><span class="sxs-lookup"><span data-stu-id="ff173-110">For all users, including remote workers and especially admins, Microsoft strongly recommends MFA.</span></span>

<span data-ttu-id="ff173-111">根据 Microsoft 365 套餐，可通过三种方式要求你的用户使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="ff173-111">There are three ways to require your users to use MFA based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="ff173-112">套餐</span><span class="sxs-lookup"><span data-stu-id="ff173-112">Plan</span></span>  |<span data-ttu-id="ff173-113">建议</span><span class="sxs-lookup"><span data-stu-id="ff173-113">Recommendation</span></span>  |
|---------|---------|
|<span data-ttu-id="ff173-114">所有 Microsoft 365 套餐（无 Azure AD Premium P1 或 P2 许可证）</span><span class="sxs-lookup"><span data-stu-id="ff173-114">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="ff173-115">[在 Azure AD 中启用安全性默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="ff173-115">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="ff173-116">Azure AD 中的安全性默认值于用户和管理员的 MFA。</span><span class="sxs-lookup"><span data-stu-id="ff173-116">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="ff173-117">Microsoft 365 E3 （包括 Azure AD Premium P1 许可证）</span><span class="sxs-lookup"><span data-stu-id="ff173-117">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="ff173-118">使用[常用条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)配置以下策略：</span><span class="sxs-lookup"><span data-stu-id="ff173-118">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="ff173-119">- [要求对管理员执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="ff173-119">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="ff173-120">- [要求对所有用户执行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="ff173-120">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="ff173-121">- [阻止传统身份验证](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="ff173-121">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="ff173-122">Microsoft 365 E5 （包括 Azure AD Premium P2 许可证）</span><span class="sxs-lookup"><span data-stu-id="ff173-122">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="ff173-123">借助 Azure AD 标识保护，创建以下策略来开始实施 Microsoft [推荐的一组条件访问和相关策略](../security/office-365-security/identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="ff173-123">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of Conditional Access and related policies](../security/office-365-security/identity-access-policies.md) by creating these policies:</span></span><br> <span data-ttu-id="ff173-124">- [要求在登录风险为“中等”或“高”时执行 MFA](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="ff173-124">- [Require MFA when sign-in risk is medium or high](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="ff173-125">- [阻止不支持新式身份验证的客户端](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)</span><span class="sxs-lookup"><span data-stu-id="ff173-125">- [Block clients that don't support modern authentication](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)</span></span><br><span data-ttu-id="ff173-126">- [高风险用户必须更改密码](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="ff173-126">- [High risk users must change password](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

## <a name="security-defaults"></a><span data-ttu-id="ff173-127">安全性默认值</span><span class="sxs-lookup"><span data-stu-id="ff173-127">Security defaults</span></span>

<span data-ttu-id="ff173-128">安全性默认值是在 2019 年 10 月 21 日之后创建的 Microsoft 365 和 Office 365 付费或试用版订阅的一项新功能。</span><span class="sxs-lookup"><span data-stu-id="ff173-128">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="ff173-129">这些订阅启用了安全性默认值，这\***要求所有用户将 MFA 与 Microsoft Authenticator 应用配合使用**。</span><span class="sxs-lookup"><span data-stu-id="ff173-129">These subscriptions have security defaults turned on, which \***requires all of your users to use MFA with the Microsoft Authenticator app**_.</span></span>
 
<span data-ttu-id="ff173-130">用户有 14 天的时间从其智能手机中通过 Microsoft Authenticator 应用登录 MFA，自启用安全性默认值后首次登录起计。</span><span class="sxs-lookup"><span data-stu-id="ff173-130">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="ff173-131">14 天后，除非 MFA 注册完成，否则用户将无法登录。</span><span class="sxs-lookup"><span data-stu-id="ff173-131">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="ff173-132">安全性默认值可确保所有组织均对默认启用的用户登录具有基本的安全级别。</span><span class="sxs-lookup"><span data-stu-id="ff173-132">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="ff173-133">可使用条件访问策略或针对个别帐户禁用安全性默认值，以支持 MFA。</span><span class="sxs-lookup"><span data-stu-id="ff173-133">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="ff173-134">有关详细信息，请参阅此[安全性默认值概述](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="ff173-134">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

## <a name="conditional-access-policies"></a><span data-ttu-id="ff173-135">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="ff173-135">Conditional Access policies</span></span>

<span data-ttu-id="ff173-136">条件访问策略是一组规则，指定评估和允许登录的条件。</span><span class="sxs-lookup"><span data-stu-id="ff173-136">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="ff173-137">例如，你可以创建一个条件访问策略，指明：</span><span class="sxs-lookup"><span data-stu-id="ff173-137">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="ff173-138">如果用户帐户名是分配了 Exchange、用户、密码、安全性、SharePoint 或全局管理员角色的用户组的成员，则需要先进行 MFA，然后才能允许访问。</span><span class="sxs-lookup"><span data-stu-id="ff173-138">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="ff173-139">通过此策略，当为用户分配或取消分配了上述管理员角色时，你可以根据其组成员身份要求进行 MFA，而不是针对单个用户帐户进行 MFA 配置。</span><span class="sxs-lookup"><span data-stu-id="ff173-139">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="ff173-140">你还可以使用条件访问策略来实现更高级的功能，例如，要求从合规设备（例如运行 Windows 10 的电脑）完成登录。</span><span class="sxs-lookup"><span data-stu-id="ff173-140">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="ff173-141">条件访问需要 Microsoft 365 E3 和 E5 随附的 Azure AD Premium P1 许可证。</span><span class="sxs-lookup"><span data-stu-id="ff173-141">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="ff173-142">有关详细信息，请参阅此[条件访问概述](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="ff173-142">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

## <a name="azure-ad-identity-protection-support"></a><span data-ttu-id="ff173-143">Azure AD 标识保护支持</span><span class="sxs-lookup"><span data-stu-id="ff173-143">Azure AD Identity Protection support</span></span>

<span data-ttu-id="ff173-144">借助 Azure AD 标识保护，你可以创建其他条件访问策略，该策略规定：</span><span class="sxs-lookup"><span data-stu-id="ff173-144">With Azure AD Identity Protection, you can create an additional Conditional Access policy that states:</span></span>

- <span data-ttu-id="ff173-145">如果登录风险确定为中等或高风险，则必须进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="ff173-145">If the risk of the sign-in is determined to be medium or high, require MFA.</span></span>

<span data-ttu-id="ff173-146">Azure AD 标识保护需要 Microsoft 365 E5 随附的 Azure AD Premium P2 许可证。</span><span class="sxs-lookup"><span data-stu-id="ff173-146">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>

<span data-ttu-id="ff173-147">有关详细信息，请参阅[基于风险的条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users)。</span><span class="sxs-lookup"><span data-stu-id="ff173-147">For more information, see [Risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users).</span></span>

<span data-ttu-id="ff173-148">借助 Azure AD 标识保护，你还可创建一个策略来要求用户注册 MFA。</span><span class="sxs-lookup"><span data-stu-id="ff173-148">With Azure AD Identity Protection, you can also create a policy to require your users to register for MFA.</span></span> <span data-ttu-id="ff173-149">有关详细信息，请参阅[配置 Azure 多重身份验证注册策略](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)</span><span class="sxs-lookup"><span data-stu-id="ff173-149">For more information, see [Configure the Azure Multi-Factor Authentication registration policy](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)</span></span>


## <a name="using-these-methods-together"></a><span data-ttu-id="ff173-150">结合使用这些方法</span><span class="sxs-lookup"><span data-stu-id="ff173-150">Using these methods together</span></span>

<span data-ttu-id="ff173-151">请注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="ff173-151">Keep the following in mind:</span></span>

- <span data-ttu-id="ff173-152">如果启用了任何条件访问策略，则无法启用安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="ff173-152">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="ff173-153">如果启用了安全性默认值，则无法启用任何条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="ff173-153">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="ff173-154">如果启用了安全性默认值，系统将提示所有新用户进行 MFA 注册并使用 Microsoft Authenticator 应用。</span><span class="sxs-lookup"><span data-stu-id="ff173-154">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="ff173-155">下表显示了通过安全性默认值和条件访问策略启用 MFA 的结果。</span><span class="sxs-lookup"><span data-stu-id="ff173-155">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="ff173-156">方法</span><span class="sxs-lookup"><span data-stu-id="ff173-156">Method</span></span> | <span data-ttu-id="ff173-157">已启用</span><span class="sxs-lookup"><span data-stu-id="ff173-157">Enabled</span></span> | <span data-ttu-id="ff173-158">禁用</span><span class="sxs-lookup"><span data-stu-id="ff173-158">Disabled</span></span> | <span data-ttu-id="ff173-159">其他身份验证方法</span><span class="sxs-lookup"><span data-stu-id="ff173-159">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="ff173-160">_*安全性默认值*\*</span><span class="sxs-lookup"><span data-stu-id="ff173-160">_*Security defaults*\*</span></span>  | <span data-ttu-id="ff173-161">无法使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="ff173-161">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="ff173-162">可以使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="ff173-162">Can use Conditional Access policies</span></span> | <span data-ttu-id="ff173-163">Microsoft Authenticator 应用</span><span class="sxs-lookup"><span data-stu-id="ff173-163">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="ff173-164">**条件访问策略**</span><span class="sxs-lookup"><span data-stu-id="ff173-164">**Conditional Access policies**</span></span> | <span data-ttu-id="ff173-165">如果已启用任何条件访问策略，则无法启用安全性默认值</span><span class="sxs-lookup"><span data-stu-id="ff173-165">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="ff173-166">如果已禁用所有条件访问策略，则可以启用安全性默认值</span><span class="sxs-lookup"><span data-stu-id="ff173-166">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="ff173-167">由用户在 MFA 注册期间指定</span><span class="sxs-lookup"><span data-stu-id="ff173-167">User specifies during MFA registration</span></span>  |
||||

## <a name="let-your-users-reset-their-own-passwords"></a><span data-ttu-id="ff173-168">允许用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="ff173-168">Let your users reset their own passwords</span></span>

<span data-ttu-id="ff173-169">自助密码重置 (SSPR) 使用户可以重置自己的密码，而不会影响 IT 人员。</span><span class="sxs-lookup"><span data-stu-id="ff173-169">Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff.</span></span> <span data-ttu-id="ff173-170">用户可随时随地快速重置其密码。</span><span class="sxs-lookup"><span data-stu-id="ff173-170">Users can quickly reset their passwords at any time and from any place.</span></span> <span data-ttu-id="ff173-171">有关详细信息，请查阅[计划 Azure AD 自助服务密码重置部署](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。</span><span class="sxs-lookup"><span data-stu-id="ff173-171">For more information, see [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

## <a name="sign-in-to-saas-apps-with-azure-ad"></a><span data-ttu-id="ff173-172">使用 Azure AD 登录 SaaS 应用</span><span class="sxs-lookup"><span data-stu-id="ff173-172">Sign in to SaaS apps with Azure AD</span></span>

<span data-ttu-id="ff173-173">除了为用户提供云身份验证之外，Azure AD 还可以是保护所有应用（无论是本地、Microsoft 云中还是其他云中的应用）的主要方法。</span><span class="sxs-lookup"><span data-stu-id="ff173-173">In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud.</span></span> <span data-ttu-id="ff173-174">通过[将应用集成到 Azure AD 中](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration)，你可以轻松地帮助远程工作者发现他们所需的应用程序并进行安全登录。</span><span class="sxs-lookup"><span data-stu-id="ff173-174">By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for remote workers to discover the applications they need and sign into them securely.</span></span>

## <a name="admin-technical-resources-for-mfa-and-identity"></a><span data-ttu-id="ff173-175">用于 MFA 和身份验证的管理员技术资源</span><span class="sxs-lookup"><span data-stu-id="ff173-175">Admin technical resources for MFA and identity</span></span>

- [<span data-ttu-id="ff173-176">Azure AD 帮助你实现远程工作的 5 大方法</span><span class="sxs-lookup"><span data-stu-id="ff173-176">Top 5 ways your Azure AD can help you enable remote work</span></span>](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [<span data-ttu-id="ff173-177">Microsoft 365 的识别指南</span><span class="sxs-lookup"><span data-stu-id="ff173-177">Identity roadmap for Microsoft 365</span></span>](../enterprise/identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="ff173-178">Azure Academy Azure AD 培训视频</span><span class="sxs-lookup"><span data-stu-id="ff173-178">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## <a name="results-of-step-1"></a><span data-ttu-id="ff173-179">步骤 1 的结果</span><span class="sxs-lookup"><span data-stu-id="ff173-179">Results of Step 1</span></span>

<span data-ttu-id="ff173-180">部署 MFA 之后，用户：</span><span class="sxs-lookup"><span data-stu-id="ff173-180">After deployment of MFA, your users:</span></span>

- <span data-ttu-id="ff173-181">需要使用 MFA 进行登录。</span><span class="sxs-lookup"><span data-stu-id="ff173-181">Are required to use MFA for sign-ins.</span></span>
- <span data-ttu-id="ff173-182">已完成 MFA 注册流程，并将使用 MFA 进行所有登录。</span><span class="sxs-lookup"><span data-stu-id="ff173-182">Have completed the MFA registration process and are using MFA for all sign-ins.</span></span>
- <span data-ttu-id="ff173-183">可以使用 SSPR 重置他们自己的密码。</span><span class="sxs-lookup"><span data-stu-id="ff173-183">Can use SSPR to reset their own passwords.</span></span>

## <a name="next-step"></a><span data-ttu-id="ff173-184">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ff173-184">Next step</span></span>

<span data-ttu-id="ff173-185">[![步骤 2：提供对本地应用和服务的远程访问权限](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)</span><span class="sxs-lookup"><span data-stu-id="ff173-185">[![Step 2: Provide remote access to on-premises apps and services](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)</span></span>

<span data-ttu-id="ff173-186">继续执行[步骤 2](empower-people-to-work-remotely-remote-access.md)，提供对本地应用和服务的远程访问权限。</span><span class="sxs-lookup"><span data-stu-id="ff173-186">Continue with [Step 2](empower-people-to-work-remotely-remote-access.md) to provide remote access to on-premises apps and services.</span></span>
