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
ms.openlocfilehash: a88fc5f46a6dafda72a24ba5e80587b24a216955
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546464"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="2b4c1-103">允许来宾和外部 B2B 访问的策略</span><span class="sxs-lookup"><span data-stu-id="2b4c1-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="2b4c1-104">本文介绍如何调整建议的公共标识和设备访问策略，以允许企业到企业 (B2B) 帐户访问 (来宾和外部用户) 。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-104">This article describes how to adjust the recommended common identity and device access policies to allow Business-to-Business (B2B) account access (guest and external users).</span></span> <span data-ttu-id="2b4c1-105">本指南建立在 [通用标识和设备访问策略](identity-access-policies.md)之上。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="2b4c1-106">这些建议旨在适用于保护的 **基准** 层。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="2b4c1-107">不过，您还可以根据您对 **敏感** 和 **高度管控** 保护的需求的粒度来调整建议。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="2b4c1-108">为 B2B 用户提供用于对 Azure Active Directory 进行身份验证的路径 (Azure AD) 租户不会为这些用户授予对您的整个环境的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-108">Providing a path for B2B users to authenticate with your Azure Active Directory (Azure AD) tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="2b4c1-109">B2B 用户只能访问与他们共享的资源 (例如，在条件访问策略中授予的服务中) 文件。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="2b4c1-110">更新常见策略以允许和保护来宾和外部访问</span><span class="sxs-lookup"><span data-stu-id="2b4c1-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="2b4c1-111">若要保护来宾和外部访问，下图说明了要从通用标识和设备访问策略中添加或更新的策略。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-111">To protect guest and external access, the following diagram illustrates which policies to add or update from the the common identity and device access policies .</span></span> 

<span data-ttu-id="2b4c1-112">[![保护来宾访问的策略更新摘要](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="2b4c1-112">[![Summary of policy updates for protecting guest access](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="2b4c1-113">查看此图像的更大版本</span><span class="sxs-lookup"><span data-stu-id="2b4c1-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="2b4c1-114">下表列出了您需要更新或创建新的策略。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-114">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="2b4c1-115">常见策略链接到 [常见标识和设备访问策略](identity-access-policies.md) 文章中相关的配置说明。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="2b4c1-116">保护级别</span><span class="sxs-lookup"><span data-stu-id="2b4c1-116">Protection level</span></span>|<span data-ttu-id="2b4c1-117">策略</span><span class="sxs-lookup"><span data-stu-id="2b4c1-117">Policies</span></span>|<span data-ttu-id="2b4c1-118">更多信息</span><span class="sxs-lookup"><span data-stu-id="2b4c1-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="2b4c1-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="2b4c1-119">**Baseline**</span></span>|[<span data-ttu-id="2b4c1-120">要求为来宾和外部用户始终进行 MFA</span><span class="sxs-lookup"><span data-stu-id="2b4c1-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2b4c1-121">创建此新策略并仅将其应用于来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-121">Create this new policy and apply it only to guests and external users.</span></span> <span data-ttu-id="2b4c1-122">在 " **登录风险**" 下，将所有选项保留为未选中状态，以始终强制实施多重身份验证 (MFA) 。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-122">Under **Sign-in risk**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span>|
|        |[<span data-ttu-id="2b4c1-123">当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="2b4c1-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="2b4c1-124">修改此策略以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-124">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="2b4c1-125">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="2b4c1-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="2b4c1-126">修改此策略以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-126">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="2b4c1-127">若要在条件访问策略中包括或排除来宾和外部用户，请单击 " **包含** " 或 " **排除** " 选项卡，并检查 **所有来宾和外部用户**。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-127">To include or exclude guests and external users in Conditional Access policies, click the **Include** or **Exclude** tab and check **All guests and external users**.</span></span>

![用于排除来宾的控件的屏幕捕获](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="2b4c1-129">更多信息</span><span class="sxs-lookup"><span data-stu-id="2b4c1-129">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="2b4c1-130">来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="2b4c1-130">Guests vs. external users</span></span>
<span data-ttu-id="2b4c1-131">在 Azure AD 中，来宾和外部用户是相同的。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-131">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="2b4c1-132">这两个用户的用户类型为 "来宾"。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-132">The user type for both of these is Guest.</span></span> <span data-ttu-id="2b4c1-133">来宾用户是 B2B 用户。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-133">Guest users are B2B users.</span></span>

<span data-ttu-id="2b4c1-134">Microsoft 团队在应用程序中区分来宾用户和外部用户，但在进行身份验证时，这两个用户都是 B2B 用户。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-134">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="2b4c1-135">有关团队来宾和外部用户的详细信息，请参阅 [为团队启用来宾和外部访问](teams-access-policies.md#enabling-guest-and-external-access-for-teams)。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-135">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="2b4c1-136">要求为来宾和外部用户始终进行 MFA</span><span class="sxs-lookup"><span data-stu-id="2b4c1-136">Require MFA always for guest and external users</span></span>
<span data-ttu-id="2b4c1-137">此策略将提示来宾在你的租户中注册 MFA，而不考虑是否在其家乡租户中向 MFA 注册了这些。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-137">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="2b4c1-138">在访问租户中的资源时，来宾和外部用户需要对每个请求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-138">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="2b4c1-139">从基于风险的 MFA 中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="2b4c1-139">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="2b4c1-140">虽然组织可以使用 Azure AD 标识保护为 B2B 用户强制实施基于风险的策略，但由于在其主目录中存在其标识，对资源目录中的 B2B 协作用户实施 Azure AD 标识保护有一些限制。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-140">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="2b4c1-141">由于这些限制，Microsoft 建议您将来宾用户从基于风险的 MFA 策略中排除，并要求这些用户始终使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-141">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="2b4c1-142">有关详细信息，请参阅 [针对 B2B 协作用户的标识保护的限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-142">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="2b4c1-143">从设备管理中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="2b4c1-143">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="2b4c1-144">只有一个组织可以管理一个设备。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-144">Only one organization can manage a device.</span></span> <span data-ttu-id="2b4c1-145">如果不从需要设备符合性的策略中排除来宾和外部用户，则这些策略将阻止这些用户。</span><span class="sxs-lookup"><span data-stu-id="2b4c1-145">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="2b4c1-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2b4c1-146">Next step</span></span>

![步骤4： Microsoft 365 云应用的策略](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="2b4c1-148">为以下项配置条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="2b4c1-148">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="2b4c1-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b4c1-149">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="2b4c1-150">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2b4c1-150">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="2b4c1-151">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2b4c1-151">SharePoint</span></span>](secure-email-recommended-policies.md)

