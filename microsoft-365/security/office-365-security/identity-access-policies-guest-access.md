---
title: 用于允许来宾和外部用户 B2B 访问的标识和设备访问策略 - Microsoft 365 企业版|Microsoft Docs
description: 介绍用于保护来宾和外部用户访问的建议条件访问和相关策略。
ms.prod: m365-security
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 9d3a47752efc86c8ced32905bda851b7d8157f82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910650"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="e07c6-103">允许来宾访问和 B2B 外部用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="e07c6-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="e07c6-104">本文讨论调整推荐的设备和标识访问策略，以允许具有 Azure Active Directory (Azure AD) 企业到企业 (B2B) 帐户的来宾和外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="e07c6-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="e07c6-105">本指南基于通用[标识和设备访问策略。](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e07c6-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="e07c6-106">这些建议旨在应用于保护 **的基线** 层。</span><span class="sxs-lookup"><span data-stu-id="e07c6-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="e07c6-107">但是，也可以根据敏感和高度管控保护的特定需求 **调整建议**。 </span><span class="sxs-lookup"><span data-stu-id="e07c6-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="e07c6-108">为 B2B 帐户提供向 Azure AD 租户进行身份验证的路径不会向这些帐户授予访问整个环境的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e07c6-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="e07c6-109">B2B 用户及其帐户有权访问通过条件访问策略与它们共享的服务和资源（如文件）。</span><span class="sxs-lookup"><span data-stu-id="e07c6-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="e07c6-110">更新常用策略以允许和保护来宾和外部用户访问</span><span class="sxs-lookup"><span data-stu-id="e07c6-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="e07c6-111">此图显示了在 B2B 来宾和外部用户访问的常见标识和设备访问策略中添加或更新的策略。</span><span class="sxs-lookup"><span data-stu-id="e07c6-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="e07c6-112">[![用于保护来宾访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="e07c6-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

<span data-ttu-id="e07c6-113">下表列出了创建和更新所需的策略。</span><span class="sxs-lookup"><span data-stu-id="e07c6-113">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="e07c6-114">常见策略链接到常见标识和设备访问策略文章中的关联 [配置说明](identity-access-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="e07c6-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="e07c6-115">保护级别</span><span class="sxs-lookup"><span data-stu-id="e07c6-115">Protection level</span></span>|<span data-ttu-id="e07c6-116">策略</span><span class="sxs-lookup"><span data-stu-id="e07c6-116">Policies</span></span>|<span data-ttu-id="e07c6-117">更多信息</span><span class="sxs-lookup"><span data-stu-id="e07c6-117">More information</span></span>|
|---|---|---|
|<span data-ttu-id="e07c6-118">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="e07c6-118">**Baseline**</span></span>|[<span data-ttu-id="e07c6-119">始终要求来宾和外部用户使用 MFA</span><span class="sxs-lookup"><span data-stu-id="e07c6-119">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="e07c6-120">创建新策略并配置：</span><span class="sxs-lookup"><span data-stu-id="e07c6-120">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="e07c6-121">对于 **">包括** 的用户和组>，选择"**选择用户和** 组"，然后选择"所有 **来宾和外部用户"。**</span><span class="sxs-lookup"><span data-stu-id="e07c6-121">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="e07c6-122">对于 **">** 条件">"登录"，保留所有选项未选中状态，以始终在 MFA (多重) 。</span><span class="sxs-lookup"><span data-stu-id="e07c6-122">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="e07c6-123">当登录风险为中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="e07c6-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="e07c6-124">修改此策略以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="e07c6-124">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="e07c6-125">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="e07c6-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="e07c6-126">修改此策略以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="e07c6-126">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="e07c6-127">若要在条件访问策略中包括或排除来宾和外部用户，>用户和组>**包括** 或排除"，请检查"所有来宾和 **外部用户"。**</span><span class="sxs-lookup"><span data-stu-id="e07c6-127">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![用于排除来宾和外部用户的控件的屏幕捕获](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="e07c6-129">更多信息</span><span class="sxs-lookup"><span data-stu-id="e07c6-129">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="e07c6-130">使用 Microsoft Teams 的来宾和外部用户访问</span><span class="sxs-lookup"><span data-stu-id="e07c6-130">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="e07c6-131">Microsoft Teams 定义以下用户：</span><span class="sxs-lookup"><span data-stu-id="e07c6-131">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="e07c6-132">**来宾访问** 使用 Azure AD B2B 帐户，该帐户可添加为团队成员，并且有权访问团队的通信和资源。</span><span class="sxs-lookup"><span data-stu-id="e07c6-132">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="e07c6-133">**外部** 访问适用于没有 B2B 帐户的外部用户。</span><span class="sxs-lookup"><span data-stu-id="e07c6-133">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="e07c6-134">外部用户访问包括邀请、通话、聊天和会议，但不包括团队成员身份和团队资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e07c6-134">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="e07c6-135">有关详细信息，请参阅 teams [的来宾和外部用户访问之间的比较](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="e07c6-135">For more information, see the [comparison between guests and external user access for teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="e07c6-136">有关保护 Teams 的标识和设备访问策略的信息，请参阅用于保护 Teams 聊天、组和文件 [的策略建议](teams-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e07c6-136">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="e07c6-137">始终对来宾用户和外部用户要求 MFA</span><span class="sxs-lookup"><span data-stu-id="e07c6-137">Require MFA always for guest and external users</span></span>

<span data-ttu-id="e07c6-138">此策略会提示来宾在租户中注册 MFA，而不考虑来宾是否在主租户中注册了 MFA。</span><span class="sxs-lookup"><span data-stu-id="e07c6-138">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="e07c6-139">访问租户中的资源时，来宾和外部用户需要针对每个请求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="e07c6-139">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="e07c6-140">从基于风险的 MFA 中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="e07c6-140">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="e07c6-141">虽然组织可以使用 Azure AD Identity Protection 对 B2B 用户强制执行基于风险的策略，但由于 B2B 协作用户的身份已存储在其主目录中，因此，组织对资源目录中的 B2B 协作用户实施 Azure AD Identity Protection 存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="e07c6-141">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="e07c6-142">由于这些限制，Microsoft 建议你将来宾从基于风险的 MFA 策略中排除，并要求这些用户始终使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="e07c6-142">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="e07c6-143">有关详细信息，请参阅 [B2B 协作用户的身份保护限制](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="e07c6-143">For more information, see [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="e07c6-144">从设备管理中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="e07c6-144">Excluding guests and external users from device management</span></span>

<span data-ttu-id="e07c6-145">只有一个组织可以管理设备。</span><span class="sxs-lookup"><span data-stu-id="e07c6-145">Only one organization can manage a device.</span></span> <span data-ttu-id="e07c6-146">如果未将来宾和外部用户从要求设备符合性的策略中排除，这些策略将阻止这些用户。</span><span class="sxs-lookup"><span data-stu-id="e07c6-146">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="e07c6-147">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e07c6-147">Next step</span></span>

![步骤 4：Microsoft 365 云应用策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="e07c6-149">为：配置条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="e07c6-149">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="e07c6-150">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e07c6-150">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="e07c6-151">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e07c6-151">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="e07c6-152">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e07c6-152">SharePoint</span></span>](sharepoint-file-access-policies.md)