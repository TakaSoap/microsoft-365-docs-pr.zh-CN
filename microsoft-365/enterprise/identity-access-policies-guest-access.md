---
title: 允许来宾和外部 B2B 访问的标识和设备访问策略-Microsoft 365 for enterprise |Microsoft 文档
description: 描述建议的条件访问和用于保护来宾和外部用户访问的相关策略。
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: c61526139111885ec345bc4a4dd3cd6b147370e6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950804"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="45809-103">允许来宾和外部 B2B 访问的策略</span><span class="sxs-lookup"><span data-stu-id="45809-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="45809-104">本文介绍如何调整建议的公共标识和设备访问策略，以允许企业到企业 (B2B) 帐户访问 (来宾和外部用户) 。</span><span class="sxs-lookup"><span data-stu-id="45809-104">This article describes how to adjust the recommended common identity and device access policies to allow Business-to-Business (B2B) account access (guest and external users).</span></span> <span data-ttu-id="45809-105">本指南建立在 [通用标识和设备访问策略](identity-access-policies.md)之上。</span><span class="sxs-lookup"><span data-stu-id="45809-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="45809-106">这些建议旨在适用于保护的 **基准** 层。</span><span class="sxs-lookup"><span data-stu-id="45809-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="45809-107">不过，您还可以根据您对 **敏感** 和 **高度管控** 保护的需求的粒度来调整建议。</span><span class="sxs-lookup"><span data-stu-id="45809-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="45809-108">为 B2B 用户提供用于对 Azure Active Directory 进行身份验证的路径 (Azure AD) 租户不会为这些用户授予对您的整个环境的访问权限。</span><span class="sxs-lookup"><span data-stu-id="45809-108">Providing a path for B2B users to authenticate with your Azure Active Directory (Azure AD) tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="45809-109">B2B 用户只能访问与他们共享的资源 (例如，在条件访问策略中授予的服务中) 文件。</span><span class="sxs-lookup"><span data-stu-id="45809-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="45809-110">更新常见策略以允许和保护来宾和外部访问</span><span class="sxs-lookup"><span data-stu-id="45809-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="45809-111">若要保护来宾和外部访问，下图说明了要从通用标识和设备访问策略中添加或更新的策略。</span><span class="sxs-lookup"><span data-stu-id="45809-111">To protect guest and external access, the following diagram illustrates which policies to add or update from the the common identity and device access policies .</span></span> 

<span data-ttu-id="45809-112">[![保护来宾访问的策略更新摘要](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="45809-112">[![Summary of policy updates for protecting guest access](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="45809-113">查看此图像的更大版本</span><span class="sxs-lookup"><span data-stu-id="45809-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="45809-114">下表列出了您需要更新或创建新的策略。</span><span class="sxs-lookup"><span data-stu-id="45809-114">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="45809-115">常见策略链接到 [常见标识和设备访问策略](identity-access-policies.md) 文章中相关的配置说明。</span><span class="sxs-lookup"><span data-stu-id="45809-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="45809-116">保护级别</span><span class="sxs-lookup"><span data-stu-id="45809-116">Protection level</span></span>|<span data-ttu-id="45809-117">策略</span><span class="sxs-lookup"><span data-stu-id="45809-117">Policies</span></span>|<span data-ttu-id="45809-118">更多信息</span><span class="sxs-lookup"><span data-stu-id="45809-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="45809-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="45809-119">**Baseline**</span></span>|[<span data-ttu-id="45809-120">要求为来宾和外部用户始终进行 MFA</span><span class="sxs-lookup"><span data-stu-id="45809-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="45809-121">创建此新策略并仅将其应用于来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="45809-121">Create this new policy and apply it only to guests and external users.</span></span> <span data-ttu-id="45809-122">在 " **登录风险**" 下，将所有选项保留为未选中状态，以始终强制实施多重身份验证 (MFA) 。</span><span class="sxs-lookup"><span data-stu-id="45809-122">Under **Sign-in risk**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span>|
|        |[<span data-ttu-id="45809-123">当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="45809-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="45809-124">修改此策略以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="45809-124">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="45809-125">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="45809-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="45809-126">修改此策略以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="45809-126">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="45809-127">若要在条件访问策略中包括或排除来宾和外部用户，请单击 " **包含** " 或 " **排除** " 选项卡，并检查 **所有来宾和外部用户**。</span><span class="sxs-lookup"><span data-stu-id="45809-127">To include or exclude guests and external users in Conditional Access policies, click the **Include** or **Exclude** tab and check **All guests and external users**.</span></span>

![用于排除来宾的控件的屏幕捕获](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="45809-129">更多信息</span><span class="sxs-lookup"><span data-stu-id="45809-129">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="45809-130">来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="45809-130">Guests vs. external users</span></span>
<span data-ttu-id="45809-131">在 Azure AD 中，来宾和外部用户是相同的。</span><span class="sxs-lookup"><span data-stu-id="45809-131">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="45809-132">这两个用户的用户类型为 "来宾"。</span><span class="sxs-lookup"><span data-stu-id="45809-132">The user type for both of these is Guest.</span></span> <span data-ttu-id="45809-133">来宾用户是 B2B 用户。</span><span class="sxs-lookup"><span data-stu-id="45809-133">Guest users are B2B users.</span></span>

<span data-ttu-id="45809-134">Microsoft 团队在应用程序中区分来宾用户和外部用户。</span><span class="sxs-lookup"><span data-stu-id="45809-134">Microsoft Teams differentiates between guest users and external users within the app.</span></span> <span data-ttu-id="45809-135">来宾用户拥有 Azure AD B2B 帐户，并且可以添加到团队。</span><span class="sxs-lookup"><span data-stu-id="45809-135">Guest users have Azure AD B2B accounts and can be added to teams.</span></span> <span data-ttu-id="45809-136">外部用户只能参与呼叫、聊天和会议。</span><span class="sxs-lookup"><span data-stu-id="45809-136">External users can only participate in calls, chats, and meetings.</span></span> <span data-ttu-id="45809-137">有关详细信息，请参阅 [针对团队的来宾和外部用户之间的比较](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="45809-137">For more information, see [this comparison between guest and external users for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="45809-138">有关保护团队的身份和设备访问的详细信息，请参阅[保护团队聊天、组和文件的策略建议](teams-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="45809-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access for Teams</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="45809-139">要求为来宾和外部用户始终进行 MFA</span><span class="sxs-lookup"><span data-stu-id="45809-139">Require MFA always for guest and external users</span></span>
<span data-ttu-id="45809-140">此策略将提示来宾在你的租户中注册 MFA，而不考虑是否在其家乡租户中向 MFA 注册了这些。</span><span class="sxs-lookup"><span data-stu-id="45809-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="45809-141">在访问租户中的资源时，来宾和外部用户需要对每个请求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="45809-141">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="45809-142">从基于风险的 MFA 中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="45809-142">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="45809-143">虽然组织可以使用 Azure AD 标识保护为 B2B 用户强制实施基于风险的策略，但由于在其主目录中存在其标识，对资源目录中的 B2B 协作用户实施 Azure AD 标识保护有一些限制。</span><span class="sxs-lookup"><span data-stu-id="45809-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="45809-144">由于这些限制，Microsoft 建议您将来宾用户从基于风险的 MFA 策略中排除，并要求这些用户始终使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="45809-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="45809-145">有关详细信息，请参阅 [针对 B2B 协作用户的标识保护的限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="45809-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="45809-146">从设备管理中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="45809-146">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="45809-147">只有一个组织可以管理一个设备。</span><span class="sxs-lookup"><span data-stu-id="45809-147">Only one organization can manage a device.</span></span> <span data-ttu-id="45809-148">如果不从需要设备符合性的策略中排除来宾和外部用户，则这些策略将阻止这些用户。</span><span class="sxs-lookup"><span data-stu-id="45809-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="45809-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="45809-149">Next step</span></span>

![步骤4： Microsoft 365 云应用的策略](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="45809-151">为以下项配置条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="45809-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="45809-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45809-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="45809-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="45809-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="45809-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="45809-154">SharePoint</span></span>](secure-email-recommended-policies.md)

