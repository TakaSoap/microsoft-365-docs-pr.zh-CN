---
title: 允许来宾和外部 B2B 访问的标识和设备访问策略-Microsoft 365 企业版 |Microsoft 文档
description: 描述建议的条件访问和用于保护来宾和外部用户访问的相关策略。
author: BrendaCarter
manager: johmar
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 8276dcf85f6c5fd61e01e67deee4fea35c1a15c4
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067443"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="0bc01-103">允许来宾和外部 B2B 访问的策略</span><span class="sxs-lookup"><span data-stu-id="0bc01-103">Policies for allowing guest and external B2B access</span></span>
<span data-ttu-id="0bc01-104">本文介绍如何调整建议的公共标识和设备访问策略，以允许 B2B 帐户访问（来宾和外部用户）。</span><span class="sxs-lookup"><span data-stu-id="0bc01-104">This article describes how to adjust the recommended common identity and device access policies to allow B2B account access (guest and external users).</span></span> <span data-ttu-id="0bc01-105">本指南建立在[通用标识和设备访问策略](identity-access-policies.md)之上。</span><span class="sxs-lookup"><span data-stu-id="0bc01-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="0bc01-106">这些建议旨在适用于保护的**基准**层。</span><span class="sxs-lookup"><span data-stu-id="0bc01-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="0bc01-107">但是，您可以根据您对**敏感**和**高度管控**保护的需求的粒度来调整建议。</span><span class="sxs-lookup"><span data-stu-id="0bc01-107">However, you can adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="0bc01-108">为 B2B 用户提供用于对你的 Azure AD 租户进行身份验证的路径不会为这些用户授予对你的整个环境的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0bc01-108">Providing a path for B2B users to authenticate with your Azure AD tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="0bc01-109">B2B 用户只能访问在条件访问策略中授予的服务内与他们共享的资源（如文件）。</span><span class="sxs-lookup"><span data-stu-id="0bc01-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the conditional access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="0bc01-110">更新常见策略以允许和保护来宾和外部访问</span><span class="sxs-lookup"><span data-stu-id="0bc01-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="0bc01-111">下图说明了常见标识和设备访问策略，并指示（带有铅笔图标）要添加或更新的策略来保护来宾和外部访问。</span><span class="sxs-lookup"><span data-stu-id="0bc01-111">The following diagram illustrates the common identity and device access policies and indicates (with a pencil icon) which policies to add or update to protect guest and external access.</span></span> 

![保护来宾访问的策略更新摘要](../media/identity-access-ruleset-guest.png)

<span data-ttu-id="0bc01-113">下表列出了您需要更新或创建新的策略。</span><span class="sxs-lookup"><span data-stu-id="0bc01-113">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="0bc01-114">常见策略链接到[常见标识和设备访问策略](identity-access-policies.md)文章中相关的配置说明。</span><span class="sxs-lookup"><span data-stu-id="0bc01-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="0bc01-115">保护级别</span><span class="sxs-lookup"><span data-stu-id="0bc01-115">Protection level</span></span>|<span data-ttu-id="0bc01-116">策略</span><span class="sxs-lookup"><span data-stu-id="0bc01-116">Policies</span></span>|<span data-ttu-id="0bc01-117">更多信息</span><span class="sxs-lookup"><span data-stu-id="0bc01-117">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="0bc01-118">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="0bc01-118">**Baseline**</span></span>|[<span data-ttu-id="0bc01-119">要求为来宾和外部用户始终进行 MFA</span><span class="sxs-lookup"><span data-stu-id="0bc01-119">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="0bc01-120">创建此新规则并仅将其应用于来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="0bc01-120">Create this new rule and apply it only to guests and external users.</span></span> <span data-ttu-id="0bc01-121">在 "登录风险" 下，将所有选项保留为未选中状态，以始终强制执行 MFA。</span><span class="sxs-lookup"><span data-stu-id="0bc01-121">Under sign-in risk, leave all options unchecked to always enforce MFA.</span></span>|
|        |[<span data-ttu-id="0bc01-122">当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="0bc01-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="0bc01-123">修改此规则以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="0bc01-123">Modify this rule to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="0bc01-124">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="0bc01-124">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="0bc01-125">修改此规则以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="0bc01-125">Modify this rule to exclude guest and external users.</span></span>|

<span data-ttu-id="0bc01-126">若要在条件访问规则中包括或排除来宾和外部用户，请单击 "包含" 或 "排除" 选项卡，并检查**所有来宾和外部用户**。</span><span class="sxs-lookup"><span data-stu-id="0bc01-126">To include or exclude guests and external users in conditional access rules, click the include or exclude tab and check **All guests and external users**.</span></span>

![用于排除来宾的控件的屏幕捕获](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="0bc01-128">更多信息</span><span class="sxs-lookup"><span data-stu-id="0bc01-128">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="0bc01-129">来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="0bc01-129">Guests vs. external users</span></span>
<span data-ttu-id="0bc01-130">在 Azure AD 中，来宾和外部用户是相同的。</span><span class="sxs-lookup"><span data-stu-id="0bc01-130">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="0bc01-131">这两个用户的用户类型为 "来宾"。</span><span class="sxs-lookup"><span data-stu-id="0bc01-131">The user type for both of these is Guest.</span></span> <span data-ttu-id="0bc01-132">来宾用户是 B2B 用户。</span><span class="sxs-lookup"><span data-stu-id="0bc01-132">Guest users are B2B users.</span></span>

<span data-ttu-id="0bc01-133">Microsoft 团队在应用程序中区分来宾用户和外部用户，但在进行身份验证时，这两个用户都是 B2B 用户。</span><span class="sxs-lookup"><span data-stu-id="0bc01-133">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="0bc01-134">有关团队来宾和外部用户的详细信息，请参阅[为团队启用来宾和外部访问](teams-access-policies.md#enabling-guest-and-external-access-for-teams)。</span><span class="sxs-lookup"><span data-stu-id="0bc01-134">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="0bc01-135">要求为来宾和外部用户始终进行 MFA</span><span class="sxs-lookup"><span data-stu-id="0bc01-135">Require MFA always for guest and external users</span></span>
<span data-ttu-id="0bc01-136">此规则将提示来宾在你的租户中注册 MFA，而不考虑是否在其家乡租户中为 MFA 注册了这些规则。</span><span class="sxs-lookup"><span data-stu-id="0bc01-136">This rule prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="0bc01-137">在访问租户中的资源时，来宾和外部用户需要对每个请求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="0bc01-137">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="0bc01-138">从基于风险的 MFA 中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="0bc01-138">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="0bc01-139">虽然组织可以使用身份保护为 B2B 用户强制实施基于风险的策略，但由于在家庭中现有的用户标识，资源目录中的 B2B 协作用户在实施身份保护方面存在一些限制文件夹.</span><span class="sxs-lookup"><span data-stu-id="0bc01-139">While organizations can enforce risk-based policies for B2B users using Identity Protection, there are limitations in the implementation of Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="0bc01-140">由于这些限制，Microsoft 建议您将来宾用户从基于风险的 MFA 策略中排除，并要求这些用户始终使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="0bc01-140">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="0bc01-141">有关详细信息，请参阅[针对 B2B 协作用户的标识保护的限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="0bc01-141">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="0bc01-142">从设备管理中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="0bc01-142">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="0bc01-143">只有一个组织可以管理一个设备。</span><span class="sxs-lookup"><span data-stu-id="0bc01-143">Only one organization can manage a device.</span></span> <span data-ttu-id="0bc01-144">如果不从需要设备符合性的策略中排除来宾和外部用户，则这些策略将阻止这些用户。</span><span class="sxs-lookup"><span data-stu-id="0bc01-144">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="0bc01-145">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0bc01-145">Next steps</span></span>

[<span data-ttu-id="0bc01-146">了解如何启用团队条件访问</span><span class="sxs-lookup"><span data-stu-id="0bc01-146">Learn how to enable Teams conditional access</span></span>](teams-access-policies.md)

