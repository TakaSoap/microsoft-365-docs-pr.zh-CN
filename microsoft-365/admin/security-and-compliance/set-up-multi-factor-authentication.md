---
title: 为用户设置多重身份验证
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
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
ms.openlocfilehash: 597d8383166e0ddae0984573d77ba75cf54dafdd
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146226"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="40cdc-103">设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="40cdc-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="40cdc-104">根据你对 [Microsoft 365 中的多重身份验证 (MFA) 及其支持的理解](multi-factor-authentication-microsoft-365.md)，可对其进行设置并推广到你的组织。</span><span class="sxs-lookup"><span data-stu-id="40cdc-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40cdc-105">如果你在 2019 年 10 月 21 日之后购买了订阅或试用版，并且你在登录时收到 MFA 的提示，则已经自动为你的订阅启用[安全性默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="40cdc-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="40cdc-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="40cdc-106">Before you begin</span></span>

- <span data-ttu-id="40cdc-107">只有全局管理员才能管理 MFA。</span><span class="sxs-lookup"><span data-stu-id="40cdc-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="40cdc-108">有关详细信息，请参阅[关于管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="40cdc-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="40cdc-109">如果你启用了旧版每人 MFA，[关闭旧版对每个人进行MFA](#turn-off-legacy-per-person-mfa)。 </span><span class="sxs-lookup"><span data-stu-id="40cdc-109">If you have legacy per person MFA turned on, [Turn off legacy per person MFA](#turn-off-legacy-per-person-mfa).</span></span>
- <span data-ttu-id="40cdc-110">如果你在 Windows 设备上有 Office 2013 客户端，[启用 Office 2013 客户端的新式验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。</span><span class="sxs-lookup"><span data-stu-id="40cdc-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>
- <span data-ttu-id="40cdc-111">高级：如果你有使用 Active Directory 联合身份验证服务（AD FS）的第三方目录服务，请设置 Azure MFA 服务器。</span><span class="sxs-lookup"><span data-stu-id="40cdc-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="40cdc-112">有关详细信息，请参阅[具有 Azure 多重身份验证的高级方案和第三方 VPN 解决方案](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。</span><span class="sxs-lookup"><span data-stu-id="40cdc-112">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="40cdc-113">打开或关闭安全性默认值</span><span class="sxs-lookup"><span data-stu-id="40cdc-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="40cdc-114">对于大多数组织来说，安全性默认值提供很好的额外登录安全性级别。</span><span class="sxs-lookup"><span data-stu-id="40cdc-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="40cdc-115">有关详细信息，请参阅[什么是安全性默认值？](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="40cdc-115">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="40cdc-116">如果你的订阅是新的，则可能已自动为你启用安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="40cdc-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="40cdc-117">可通过 Microsoft Azure 门户中 Azure Active Directory (Azure AD) 的“**属性**”窗格启用或禁用安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="40cdc-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="40cdc-118">使用全局管理员凭据登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="40cdc-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="40cdc-119">在左侧导航栏中，选择“**显示所有**”，然后在 **管理中心**下，选择 “**Azure Active Directory**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="40cdc-120">在 **Azure Active Directory 管理中心**里选择 “**Azure Active Directory** > **属性**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** > **Properties**.</span></span>
3.  <span data-ttu-id="40cdc-121">在页面底部，选择“**管理安全性默认值**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="40cdc-122">选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="40cdc-123">如果你已在使用 [基准条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，则会在你使用安全性默认值之前，提示你将其关闭。</span><span class="sxs-lookup"><span data-stu-id="40cdc-123">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1.  <span data-ttu-id="40cdc-124">转到[“条件访问 - 策略”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。</span><span class="sxs-lookup"><span data-stu-id="40cdc-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="40cdc-125">选择“**开**”的每个基准策略，然后将“**启用策略**”设置为“**关**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="40cdc-126">转到[“Azure Active Directory - 属性”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="40cdc-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="40cdc-127">在页面底部，选择“**管理安全性默认值**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="40cdc-128">选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="40cdc-129">使用条件访问策略</span><span class="sxs-lookup"><span data-stu-id="40cdc-129">Use Conditional Access policies</span></span>

<span data-ttu-id="40cdc-130">如果你的组织具有更精细的登录安全需求，条件访问策略可以为你提供更多控制。</span><span class="sxs-lookup"><span data-stu-id="40cdc-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="40cdc-131">"条件访问" 允许你在向用户授予对应用程序或服务的访问权限前，先创建和定义对登录事件作出反应并请求其他操作的策略。</span><span class="sxs-lookup"><span data-stu-id="40cdc-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40cdc-132">在你启用条件访问策略前，请关闭“每人 MFA” 和安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="40cdc-132">Turn off both per person MFA and Security defaults before you enable Conditional Access policies.</span></span> 

<span data-ttu-id="40cdc-133">"条件访问" 适用于购买了 Azure AD 高级版 P1 的客户，或购买了包含此项许可证的客户，比如 Microsoft 365 商业高级版和 Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="40cdc-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="40cdc-134">有关详细信息，请参阅 [创建条件访问策略](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa)。</span><span class="sxs-lookup"><span data-stu-id="40cdc-134">For more information, see [create a Conditional Access policy](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="40cdc-135">可通过 Azure AD 高级 P2 许可证，或包含此项的许可证，例如 Microsoft 365 E5 来获取基于风险的条件访问。</span><span class="sxs-lookup"><span data-stu-id="40cdc-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licences that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="40cdc-136">有关详细信息，请参阅[基于风险的条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk)。</span><span class="sxs-lookup"><span data-stu-id="40cdc-136">For more information, see [risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="40cdc-137">为你的组织启用新式验证</span><span class="sxs-lookup"><span data-stu-id="40cdc-137">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="40cdc-138">对于大多数订阅来说，新式验证将自动被启用，但如果你在很久前购买了订阅，则可能不会。</span><span class="sxs-lookup"><span data-stu-id="40cdc-138">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription a long time ago, it might not be.</span></span> <span data-ttu-id="40cdc-139">必须先启用该功能，然后 MFA 才能使用 Office 应用适当地工作。</span><span class="sxs-lookup"><span data-stu-id="40cdc-139">This has to be turned on before MFA works appropriately with Office apps.</span></span>

1. <span data-ttu-id="40cdc-140">在 Microsoft 365 管理中心里，在左侧导航栏中选择“**设置**” > “**组织设置**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-140">In the Microsoft 365 admin center, in the left nav choose **Settings** > **Org settings**.</span></span>
1. <span data-ttu-id="40cdc-141">在“**服务**”选项卡上，选择 “**新式身份验证**”，然后在"**新式身份验证**"窗格中，确保选择 “**启用新式验证**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-141">Under **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="40cdc-142">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-142">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-person-mfa"></a><span data-ttu-id="40cdc-143">关闭“旧版每人 MFA”</span><span class="sxs-lookup"><span data-stu-id="40cdc-143">Turn off legacy per person MFA</span></span>

<span data-ttu-id="40cdc-144">如果你以前已启用了“每人MFA”，则必须在启用安全性默认值之前将其关闭。</span><span class="sxs-lookup"><span data-stu-id="40cdc-144">If you have previously turned on per person MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="40cdc-145">在 Microsoft 365 管理中心里，在左侧导航栏中选择“**用户**” > “**活动用户**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-145">In the Microsoft 365 admin center, in the left nav choose **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="40cdc-146">在“**活动用户**”页面上，选择“**多重身份验证**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-146">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="40cdc-147">在“多重身份验证”页面上，选择每个用户并将其多重身份验证状态设置为“**禁用**”。</span><span class="sxs-lookup"><span data-stu-id="40cdc-147">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="40cdc-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="40cdc-148">Next steps</span></span>

- [<span data-ttu-id="40cdc-149">如何注册以获取更多验证方法</span><span class="sxs-lookup"><span data-stu-id="40cdc-149">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="40cdc-150">注册后如何登录</span><span class="sxs-lookup"><span data-stu-id="40cdc-150">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="40cdc-151">如何更改其他验证方法</span><span class="sxs-lookup"><span data-stu-id="40cdc-151">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="40cdc-152">如何处理新智能手机等情况</span><span class="sxs-lookup"><span data-stu-id="40cdc-152">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)
- [<span data-ttu-id="40cdc-153">MFA 登录疑难解答</span><span class="sxs-lookup"><span data-stu-id="40cdc-153">Troubleshoot MFA sign-ins</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)




