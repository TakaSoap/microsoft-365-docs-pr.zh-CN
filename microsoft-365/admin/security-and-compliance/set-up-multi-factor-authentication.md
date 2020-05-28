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
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 了解如何为你的组织设置多重身份验证。
monikerRange: o365-worldwide
ms.openlocfilehash: 2b4ac2b5950d2641254742e03f054f3e4c886833
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399118"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="3ec77-103">设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="3ec77-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="3ec77-104">根据您对[Microsoft 365 中的多重身份验证（MFA）和支持](multi-factor-authentication-microsoft-365.md)的理解，可以将其设置并将其部署到您的组织中。</span><span class="sxs-lookup"><span data-stu-id="3ec77-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="3ec77-105">在开始之前，请先确定这些特殊条件是否适用于您，并采取适当的措施：</span><span class="sxs-lookup"><span data-stu-id="3ec77-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="3ec77-106">如果你的 Windows 设备上有 Office 2013 客户端，请[启用新式验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)。</span><span class="sxs-lookup"><span data-stu-id="3ec77-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="3ec77-107">如果您具有具有 Active Directory 联合身份验证服务（AD FS）的第三方目录服务，请设置 Azure MFA 服务器。</span><span class="sxs-lookup"><span data-stu-id="3ec77-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="3ec77-108">有关详细信息，请参阅[使用 Azure 多重身份验证和第三方 VPN 解决方案的高级方案](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)。</span><span class="sxs-lookup"><span data-stu-id="3ec77-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="3ec77-109">步骤1：决定要求用户使用 MFA 的方法</span><span class="sxs-lookup"><span data-stu-id="3ec77-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

<span data-ttu-id="3ec77-110">有三种方法可以要求用户使用 MFA 进行登录。有关详细信息，请参阅[Microsoft 365 中的 MFA 支持](multi-factor-authentication-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec77-110">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="3ec77-111">安全性默认值（针对小型企业版推荐）</span><span class="sxs-lookup"><span data-stu-id="3ec77-111">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="3ec77-112">如果你在2019年10月21日之后购买了订阅或试用，并且意外提示您进行 MFA，则已为你的订阅自动启用[安全默认设置](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="3ec77-112">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="3ec77-113">每个新 Microsoft 365 订阅将自动启用安全默认设置。</span><span class="sxs-lookup"><span data-stu-id="3ec77-113">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="3ec77-114">这意味着，每个用户都必须设置 MFA 并在其移动设备上安装 Microsoft 身份验证器应用。</span><span class="sxs-lookup"><span data-stu-id="3ec77-114">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="3ec77-115">所有用户都必须使用 Microsoft 身份验证器应用作为其附加验证方法，并阻止旧版身份验证。</span><span class="sxs-lookup"><span data-stu-id="3ec77-115">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="3ec77-116">条件访问策略（针对企业推荐）</span><span class="sxs-lookup"><span data-stu-id="3ec77-116">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="3ec77-117">用户在 MFA 注册过程中选择其他验证方法。</span><span class="sxs-lookup"><span data-stu-id="3ec77-117">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="3ec77-118">每用户帐户（不推荐）</span><span class="sxs-lookup"><span data-stu-id="3ec77-118">Per-user account (not recommended)</span></span>

  <span data-ttu-id="3ec77-119">用户在 MFA 注册过程中选择其他验证方法。</span><span class="sxs-lookup"><span data-stu-id="3ec77-119">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="3ec77-120">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="3ec77-120">Step 2.</span></span> <span data-ttu-id="3ec77-121">在试点用户上测试 MFA</span><span class="sxs-lookup"><span data-stu-id="3ec77-121">Test MFA on your pilot users</span></span>

<span data-ttu-id="3ec77-122">如果您使用的是条件访问策略或每用户 MFA （不推荐），请选择您的企业或组织中的 "试点用户" 以测试 MFA 注册和登录。例如：</span><span class="sxs-lookup"><span data-stu-id="3ec77-122">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="3ec77-123">对于条件访问策略，创建试点用户组和要求对组成员和所有应用进行 MFA 的策略。</span><span class="sxs-lookup"><span data-stu-id="3ec77-123">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="3ec77-124">然后，将您的试点用户的帐户添加到组中。</span><span class="sxs-lookup"><span data-stu-id="3ec77-124">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="3ec77-125">对于每用户 MFA，请一次为你的试点用户的用户帐户启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="3ec77-125">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="3ec77-126">与您的试点用户合作，以解决为您的组织准备平稳推出的问题和问题。</span><span class="sxs-lookup"><span data-stu-id="3ec77-126">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="3ec77-127">第 3 步。</span><span class="sxs-lookup"><span data-stu-id="3ec77-127">Step 3.</span></span> <span data-ttu-id="3ec77-128">通知贵组织即将推出 MFA</span><span class="sxs-lookup"><span data-stu-id="3ec77-128">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="3ec77-129">使用电子邮件通知、hallway 海报、团队会议或正式培训以确保员工了解：</span><span class="sxs-lookup"><span data-stu-id="3ec77-129">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="3ec77-130">为什么登录需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="3ec77-130">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="3ec77-131">如何注册以获取其附加验证方法</span><span class="sxs-lookup"><span data-stu-id="3ec77-131">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="3ec77-132">注册后如何登录</span><span class="sxs-lookup"><span data-stu-id="3ec77-132">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="3ec77-133">如何更改其其他验证方法</span><span class="sxs-lookup"><span data-stu-id="3ec77-133">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="3ec77-134">如何处理像新的智能手机这样的情况</span><span class="sxs-lookup"><span data-stu-id="3ec77-134">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="3ec77-135">最重要的是，请确保你***的员工了解何时强制实施 MFA 要求***，以使其不会令他们感到吃惊。</span><span class="sxs-lookup"><span data-stu-id="3ec77-135">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="3ec77-136">第 4 步。</span><span class="sxs-lookup"><span data-stu-id="3ec77-136">Step 4.</span></span> <span data-ttu-id="3ec77-137">向你的组织或用户推出 MFA 要求</span><span class="sxs-lookup"><span data-stu-id="3ec77-137">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="3ec77-138">根据所选的 MFA 要求方法，将 MFA 身份验证部署到您的试点测试人员之外的员工。</span><span class="sxs-lookup"><span data-stu-id="3ec77-138">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="3ec77-139">安全性默认值</span><span class="sxs-lookup"><span data-stu-id="3ec77-139">Security defaults</span></span>

<span data-ttu-id="3ec77-140">您可以在 Azure 门户的 Azure Active Directory （Azure AD）的**属性**窗格中启用或禁用安全默认设置。</span><span class="sxs-lookup"><span data-stu-id="3ec77-140">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="3ec77-141">使用全局管理员凭据登录到[Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="3ec77-141">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="3ec77-142">转到 " [Azure Active Directory-属性" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="3ec77-142">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="3ec77-143">在页面底部，选择“**管理安全性默认值**”。</span><span class="sxs-lookup"><span data-stu-id="3ec77-143">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="3ec77-144">选择 **"是"** 启用安全默认设置，单击 "**否**" 禁用安全默认设置，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="3ec77-144">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="3ec77-145">如果您使用的是[基准条件访问策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)，下面介绍如何移动到使用安全默认设置。</span><span class="sxs-lookup"><span data-stu-id="3ec77-145">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="3ec77-146">转到 "[条件访问策略" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。</span><span class="sxs-lookup"><span data-stu-id="3ec77-146">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="3ec77-147">选择启用的每个基准策略，并将 "**启用策略**" 设置为 "**关闭** **"** 。</span><span class="sxs-lookup"><span data-stu-id="3ec77-147">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="3ec77-148">转到 " [Azure Active Directory-属性" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="3ec77-148">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="3ec77-149">在页面底部，选择“**管理安全性默认值**”。</span><span class="sxs-lookup"><span data-stu-id="3ec77-149">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="3ec77-150">选择 **"是"** 启用安全默认设置，单击 "**否**" 禁用安全默认设置，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="3ec77-150">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="3ec77-151">条件访问策略</span><span class="sxs-lookup"><span data-stu-id="3ec77-151">Conditional Access policies</span></span>

<span data-ttu-id="3ec77-152">创建、配置和启用相应的策略，其中包括需要进行 MFA 登录的用户组。</span><span class="sxs-lookup"><span data-stu-id="3ec77-152">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="3ec77-153">每用户 MFA （不推荐）</span><span class="sxs-lookup"><span data-stu-id="3ec77-153">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="3ec77-154">为对应于你的部署的 MFA 启用用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3ec77-154">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="3ec77-155">为你的员工提供支持</span><span class="sxs-lookup"><span data-stu-id="3ec77-155">Supporting your employees</span></span>

<span data-ttu-id="3ec77-156">在你的员工注册并开始使用 MFA 登录时，请确保你的 IT 专家、IT 部门或技术支持人员能够快速回答问题并解决问题。</span><span class="sxs-lookup"><span data-stu-id="3ec77-156">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="3ec77-157">有关对[MFA 登录进行疑难解答的信息](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)，请参阅本文。</span><span class="sxs-lookup"><span data-stu-id="3ec77-157">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


