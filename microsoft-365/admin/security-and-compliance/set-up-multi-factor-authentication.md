---
title: 为用户设置多重身份验证
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 了解如何为你的组织设置多重身份验证。
monikerRange: o365-worldwide
ms.openlocfilehash: 5ea367e64108e80ee7429ec700cf2ac0551aeab2
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105147"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="19291-103">设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="19291-103">Set up multi-factor authentication</span></span>

<span data-ttu-id="19291-104">根据你对 [Microsoft 365 中的多重身份验证 (MFA) 及其支持的理解](multi-factor-authentication-microsoft-365.md)，可对其进行设置并推广到你的组织。</span><span class="sxs-lookup"><span data-stu-id="19291-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it's time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19291-105">如果你在 2019 年 10 月 21 日之后购买了订阅或试用版，并且你在登录时收到 MFA 的提示，则已经自动为你的订阅启用[安全性默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="19291-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="19291-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="19291-106">Before you begin</span></span>

- <span data-ttu-id="19291-107">只有全局管理员才能管理 MFA。</span><span class="sxs-lookup"><span data-stu-id="19291-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="19291-108">有关详细信息，请参阅[关于管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="19291-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="19291-109">如果你启用了旧版每用户 MFA，请[关闭旧版每用户 MFA](#turn-off-legacy-per-user-mfa)。</span><span class="sxs-lookup"><span data-stu-id="19291-109">If you have legacy per-user MFA turned on, [Turn off legacy per-user MFA](#turn-off-legacy-per-user-mfa).</span></span>
- <span data-ttu-id="19291-110">如果你在 Windows 设备上有 Office 2013 客户端，[启用 Office 2013 客户端的新式验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。</span><span class="sxs-lookup"><span data-stu-id="19291-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>
- <span data-ttu-id="19291-111">高级：如果你有使用 Active Directory 联合身份验证服务（AD FS）的第三方目录服务，请设置 Azure MFA 服务器。</span><span class="sxs-lookup"><span data-stu-id="19291-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="19291-112">有关详细信息，请参阅[具有 Azure Active Directory 多重身份验证的高级方案和第三方 VPN 解决方案](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。</span><span class="sxs-lookup"><span data-stu-id="19291-112">See [advanced scenarios with Azure AD Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="19291-113">打开或关闭安全性默认值</span><span class="sxs-lookup"><span data-stu-id="19291-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="19291-114">对于大多数组织来说，安全性默认值提供很好的额外登录安全性级别。</span><span class="sxs-lookup"><span data-stu-id="19291-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="19291-115">有关详细信息，请参阅[什么是安全性默认值？](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="19291-115">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="19291-116">如果你的订阅是新的，则可能已自动为你启用安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="19291-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="19291-117">可通过 Microsoft Azure 门户中 Azure Active Directory (Azure AD) 的“**属性**”窗格启用或禁用安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="19291-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="19291-118">使用全局管理员凭据登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="19291-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="19291-119">在左侧导航栏中，选择“**全部显示**”，然后在 **管理中心** 下，选择“**Azure Active Directory**”。</span><span class="sxs-lookup"><span data-stu-id="19291-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="19291-120">在 **Azure Active Directory 管理中心** 中选择“**Azure Active Directory**”\>“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="19291-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** \> **Properties**.</span></span>
4. <span data-ttu-id="19291-121">在页面底部，选择“**管理安全性默认值**”。</span><span class="sxs-lookup"><span data-stu-id="19291-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="19291-122">选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="19291-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="19291-123">如果你已在使用 [基准条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，则会在你使用安全性默认值之前，提示你将其关闭。</span><span class="sxs-lookup"><span data-stu-id="19291-123">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1. <span data-ttu-id="19291-124">转到[“条件访问 - 策略”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。</span><span class="sxs-lookup"><span data-stu-id="19291-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="19291-125">选择“**开**”的每个基准策略，然后将“**启用策略**”设置为“**关**”。</span><span class="sxs-lookup"><span data-stu-id="19291-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="19291-126">转到[“Azure Active Directory - 属性”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="19291-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="19291-127">在页面底部，选择“**管理安全性默认值**”。</span><span class="sxs-lookup"><span data-stu-id="19291-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="19291-128">选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="19291-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="19291-129">使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="19291-129">Use Conditional Access policies</span></span>

<span data-ttu-id="19291-130">如果你的组织具有更精细的登录安全需求，条件访问策略可以为你提供更多控制。</span><span class="sxs-lookup"><span data-stu-id="19291-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="19291-131">“条件访问”允许你在向用户授予对应用程序或服务的访问权限前，先创建和定义对登录事件作出反应并请求其他操作的策略。</span><span class="sxs-lookup"><span data-stu-id="19291-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19291-132">在你启用条件访问策略前，请关闭每用户 MFA 和安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="19291-132">Turn off both per-user MFA and Security defaults before you enable Conditional Access policies.</span></span>

<span data-ttu-id="19291-133">“条件访问”适用于购买了 Azure AD 高级版 P1 的客户，或购买了包含此项许可证的客户，比如 Microsoft 365 商业高级版和 Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="19291-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="19291-134">有关详细信息，请参阅 [创建条件访问策略](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa)。</span><span class="sxs-lookup"><span data-stu-id="19291-134">For more information, see [create a Conditional Access policy](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="19291-135">可通过 Azure AD 高级 P2 许可证或包含此项的许可证（例如 Microsoft 365 E5）来获得基于风险的条件访问。</span><span class="sxs-lookup"><span data-stu-id="19291-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licenses that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="19291-136">有关详细信息，请参阅[基于风险的条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk)。</span><span class="sxs-lookup"><span data-stu-id="19291-136">For more information, see [risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="19291-137">有关 Azure AD P1 和 P2 的详细信息，请参阅 [Azure Active Directory 定价](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="19291-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="19291-138">为你的组织启用新式验证</span><span class="sxs-lookup"><span data-stu-id="19291-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="19291-139">对于大多数订阅来说，新式验证将自动被启用，但如果你在很久前购买了订阅，则可能不会。</span><span class="sxs-lookup"><span data-stu-id="19291-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription a long time ago, it might not be.</span></span> <span data-ttu-id="19291-140">必须先启用该功能，然后 MFA 才能使用 Office 应用适当地工作。</span><span class="sxs-lookup"><span data-stu-id="19291-140">This has to be turned on before MFA works appropriately with Office apps.</span></span>

1. <span data-ttu-id="19291-141">在 Microsoft 365 管理中心中，在左侧导航栏中选择“**设置**”\>“**组织设置**”。</span><span class="sxs-lookup"><span data-stu-id="19291-141">In the Microsoft 365 admin center, in the left nav choose **Settings** \> **Org settings**.</span></span>
1. <span data-ttu-id="19291-142">在“**服务**”选项卡上，选择“**新式身份验证**”，然后在“**新式身份验证**"窗格中，确保选择“**启用新式验证**”。</span><span class="sxs-lookup"><span data-stu-id="19291-142">Under **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="19291-143">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="19291-143">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-user-mfa"></a><span data-ttu-id="19291-144">关闭旧版每用户 MFA</span><span class="sxs-lookup"><span data-stu-id="19291-144">Turn off legacy per-user MFA</span></span>

<span data-ttu-id="19291-145">如果你以前已启用了每用户 MFA，则必须在启用安全性默认值之前将其关闭。</span><span class="sxs-lookup"><span data-stu-id="19291-145">If you have previously turned on per-user MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="19291-146">在 Microsoft 365 管理中心中，在左侧导航栏中选择“**用户**”\>“**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="19291-146">In the Microsoft 365 admin center, in the left nav choose **Users** \> **Active users**.</span></span>
1. <span data-ttu-id="19291-147">在“**活动用户**”页面上，选择“**多重身份验证**”。</span><span class="sxs-lookup"><span data-stu-id="19291-147">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="19291-148">在“多重身份验证”页面上，选择每个用户并将其多重身份验证状态设置为“**禁用**”。</span><span class="sxs-lookup"><span data-stu-id="19291-148">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="19291-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="19291-149">Next steps</span></span>

- [<span data-ttu-id="19291-150">如何注册以获取更多验证方法</span><span class="sxs-lookup"><span data-stu-id="19291-150">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="19291-151">何为：多重身份验证</span><span class="sxs-lookup"><span data-stu-id="19291-151">What is: Multifactor Authentication</span></span>](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [<span data-ttu-id="19291-152">注册后如何登录</span><span class="sxs-lookup"><span data-stu-id="19291-152">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="19291-153">如何更改其他验证方法</span><span class="sxs-lookup"><span data-stu-id="19291-153">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-topics"></a><span data-ttu-id="19291-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="19291-154">Related topics</span></span>

[<span data-ttu-id="19291-155">i视频：开启多重身份验证</span><span class="sxs-lookup"><span data-stu-id="19291-155">Video: Turn on multi-factor authentication</span></span>](https://docs.microsoft.com/microsoft-365/business-video/turn-on-mfa)

[<span data-ttu-id="19291-156">i视频：为手机开启多重身份验证</span><span class="sxs-lookup"><span data-stu-id="19291-156">Video: Turn on multi-factor authentication for your phone</span></span>](https://docs.microsoft.com/microsoft-365/business-video/set-up-mfa)