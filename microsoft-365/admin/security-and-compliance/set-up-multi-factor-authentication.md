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
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083534"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="46896-103">设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="46896-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="46896-104">根据你对 [Microsoft 365 中的多重身份验证 (MFA) 及其支持的理解](multi-factor-authentication-microsoft-365.md)，可对其进行设置并推广到你的组织。</span><span class="sxs-lookup"><span data-stu-id="46896-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="46896-105">开始之前，请确定这些特殊条件是否适用于你并采取相应的行动：</span><span class="sxs-lookup"><span data-stu-id="46896-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="46896-106">如果 Windows 设备上有 Office 2013 客户端，则[启用新式验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。</span><span class="sxs-lookup"><span data-stu-id="46896-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="46896-107">如果具有带 Active Directory 联合身份验证服务 (AD FS) 的第三方目录服务，请设置 Azure MFA 服务器。</span><span class="sxs-lookup"><span data-stu-id="46896-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="46896-108">有关详细信息，请参阅[具有 Azure 多重身份验证的高级方案和第三方 VPN 解决方案](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。</span><span class="sxs-lookup"><span data-stu-id="46896-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

<span data-ttu-id="46896-109">必要时，系统将要求其他所有用户执行额外的身份验证。</span><span class="sxs-lookup"><span data-stu-id="46896-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="46896-110">有关详细信息，请访问[双因素验证方法和设置](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device)。</span><span class="sxs-lookup"><span data-stu-id="46896-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="46896-111">步骤 1：确定要求用户使用 MFA 的方法</span><span class="sxs-lookup"><span data-stu-id="46896-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="46896-112">你必须是全局管理员才能设置或修改 MFA。</span><span class="sxs-lookup"><span data-stu-id="46896-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="46896-113">可通过三种方式要求用户使用 MFA 进行登录。有关详细信息，请参阅 [Microsoft 365 中的 MFA 支持](multi-factor-authentication-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="46896-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="46896-114">安全性默认值（对于小型企业推荐）</span><span class="sxs-lookup"><span data-stu-id="46896-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="46896-115">如果你在 2019 年 10 月 21 日之后购买了订阅或试用版，并且系统意外提示你进行 MFA，则将自动为你的订阅启用[安全性默认值](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="46896-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="46896-116">每个新的 Microsoft 365 订阅都将自动启用安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="46896-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="46896-117">这意味着每位用户都必须在其移动设备上设置 MFA 并安装 Microsoft Authenticator 应用。</span><span class="sxs-lookup"><span data-stu-id="46896-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="46896-118">所有用户都必须使用 Microsoft Authenticator 应用作为其额外验证方法，而旧式身份验证会被阻止。</span><span class="sxs-lookup"><span data-stu-id="46896-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="46896-119">条件访问策略（推荐用于企业）</span><span class="sxs-lookup"><span data-stu-id="46896-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="46896-120">在 MFA 注册期间，用户可选择其他验证方法。</span><span class="sxs-lookup"><span data-stu-id="46896-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="46896-121">每用户帐户（不推荐）</span><span class="sxs-lookup"><span data-stu-id="46896-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="46896-122">在 MFA 注册期间，用户可选择其他验证方法。</span><span class="sxs-lookup"><span data-stu-id="46896-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="46896-123">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="46896-123">Step 2.</span></span> <span data-ttu-id="46896-124">对引导用户测试 MFA</span><span class="sxs-lookup"><span data-stu-id="46896-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="46896-125">如果你使用的是条件访问策略或每用户 MFA（不推荐），请在你的企业或组织中选择引导用户以测试 MFA 注册和登录。例如：</span><span class="sxs-lookup"><span data-stu-id="46896-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="46896-126">对于条件访问策略，请创建一个引导用户组和要求对组成员和所有应用进行 MFA 的策略。</span><span class="sxs-lookup"><span data-stu-id="46896-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="46896-127">然后，将引导用户的帐户添加到组中。</span><span class="sxs-lookup"><span data-stu-id="46896-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="46896-128">对于每用户 MFA，每次对引导用户的用户帐户启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="46896-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="46896-129">与引导用户协作解决难题和问题，以便你的组织做好平稳推广准备。</span><span class="sxs-lookup"><span data-stu-id="46896-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="46896-130">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="46896-130">Step 3.</span></span> <span data-ttu-id="46896-131">告知你的组织即将进行 MFA</span><span class="sxs-lookup"><span data-stu-id="46896-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="46896-132">使用电子邮件通知、走廊海报、团队会议或正式培训来确保员工理解：</span><span class="sxs-lookup"><span data-stu-id="46896-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="46896-133">为什么需要 MFA 才能登录</span><span class="sxs-lookup"><span data-stu-id="46896-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="46896-134">如何注册以获取更多验证方法</span><span class="sxs-lookup"><span data-stu-id="46896-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="46896-135">注册后如何登录</span><span class="sxs-lookup"><span data-stu-id="46896-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="46896-136">如何更改其他验证方法</span><span class="sxs-lookup"><span data-stu-id="46896-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="46896-137">如何处理新智能手机等情况</span><span class="sxs-lookup"><span data-stu-id="46896-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="46896-138">最重要的是，请确保员工了解***何时将要实施 MFA 要求***，以免让他们感到惊讶。</span><span class="sxs-lookup"><span data-stu-id="46896-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="46896-139">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="46896-139">Step 4.</span></span> <span data-ttu-id="46896-140">向你的组织或用户推出 MFA 要求</span><span class="sxs-lookup"><span data-stu-id="46896-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="46896-141">根据所选的 MFA 要求方法，向试点测试人员以外的员工推广 MFA 身份验证。</span><span class="sxs-lookup"><span data-stu-id="46896-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="46896-142">安全性默认值</span><span class="sxs-lookup"><span data-stu-id="46896-142">Security defaults</span></span>

<span data-ttu-id="46896-143">可通过 Microsoft Azure 门户中 Azure Active Directory (Azure AD) 的“**属性**”窗格启用或禁用安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="46896-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="46896-144">使用全局管理员凭据登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="46896-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="46896-145">转到[“Azure Active Directory - 属性”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="46896-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="46896-146">在页面底部，选择“**管理安全性默认值**”。</span><span class="sxs-lookup"><span data-stu-id="46896-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="46896-147">选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="46896-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="46896-148">如果已在使用[基准条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，下面是转为使用安全性默认值的方式。</span><span class="sxs-lookup"><span data-stu-id="46896-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="46896-149">转到[“条件访问 - 策略”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。</span><span class="sxs-lookup"><span data-stu-id="46896-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="46896-150">选择“**开**”的每个基准策略，然后将“**启用策略**”设置为“**关**”。</span><span class="sxs-lookup"><span data-stu-id="46896-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="46896-151">转到[“Azure Active Directory - 属性”页面](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="46896-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="46896-152">在页面底部，选择“**管理安全性默认值**”。</span><span class="sxs-lookup"><span data-stu-id="46896-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="46896-153">选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="46896-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="46896-154">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="46896-154">Conditional Access policies</span></span>

<span data-ttu-id="46896-155">创建、配置和启用相应的策略，其中包括需要使用 MFA 进行登录的用户组。</span><span class="sxs-lookup"><span data-stu-id="46896-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="46896-156">每用户 MFA（不推荐）</span><span class="sxs-lookup"><span data-stu-id="46896-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="46896-157">针对你的推广为用户帐户启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="46896-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="46896-158">为员工提供支持</span><span class="sxs-lookup"><span data-stu-id="46896-158">Supporting your employees</span></span>

<span data-ttu-id="46896-159">随着你的员工注册并开始使用 MFA 进行登录，请确保你的 IT 专家、IT 部门或支持人员能够快速回答问题并解决问题。</span><span class="sxs-lookup"><span data-stu-id="46896-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="46896-160">请参阅本文以获取[有关 MFA 登录疑难解答的信息](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)。</span><span class="sxs-lookup"><span data-stu-id="46896-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


