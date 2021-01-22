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
ms.openlocfilehash: 2ef494f8e383f50f16b1e64f6387b6e5d62459c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932606"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="a17d9-103">允许来宾访问和 B2B 外部用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="a17d9-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="a17d9-104">本文讨论调整推荐的设备和标识访问策略，以允许具有 Azure Active Directory (Azure AD) 企业到企业 (B2B) 帐户的来宾和外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="a17d9-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="a17d9-105">本指南基于通用 [标识和设备访问策略](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a17d9-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="a17d9-106">这些建议旨在应用于 **保护的基线** 层。</span><span class="sxs-lookup"><span data-stu-id="a17d9-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="a17d9-107">但您也可以根据敏感和高度管控保护的特定需求 **调整建议**。 </span><span class="sxs-lookup"><span data-stu-id="a17d9-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="a17d9-108">为 B2B 帐户提供向 Azure AD 租户进行身份验证的路径不会向这些帐户授予访问整个环境的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a17d9-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="a17d9-109">B2B 用户及其帐户有权访问由条件访问策略与它们共享的服务和资源（如文件）。</span><span class="sxs-lookup"><span data-stu-id="a17d9-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="a17d9-110">更新常见策略以允许和保护来宾和外部用户访问</span><span class="sxs-lookup"><span data-stu-id="a17d9-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="a17d9-111">此图显示了在通用标识和设备访问策略之间添加或更新哪些策略，用于 B2B 来宾和外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="a17d9-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="a17d9-112">[![用于保护来宾访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="a17d9-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="a17d9-113">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="a17d9-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="a17d9-114">下表列出了创建和更新所需的策略。</span><span class="sxs-lookup"><span data-stu-id="a17d9-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="a17d9-115">常见策略链接到通用标识和设备访问策略文章中的 [关联配置](identity-access-policies.md) 说明。</span><span class="sxs-lookup"><span data-stu-id="a17d9-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="a17d9-116">保护级别</span><span class="sxs-lookup"><span data-stu-id="a17d9-116">Protection level</span></span>|<span data-ttu-id="a17d9-117">策略</span><span class="sxs-lookup"><span data-stu-id="a17d9-117">Policies</span></span>|<span data-ttu-id="a17d9-118">更多信息</span><span class="sxs-lookup"><span data-stu-id="a17d9-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="a17d9-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="a17d9-119">**Baseline**</span></span>|[<span data-ttu-id="a17d9-120">始终要求来宾和外部用户使用 MFA</span><span class="sxs-lookup"><span data-stu-id="a17d9-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a17d9-121">创建此新策略并配置：</span><span class="sxs-lookup"><span data-stu-id="a17d9-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="a17d9-122">对于 **分配>包括** 的用户和组>，选择"选择用户 **和组**"，然后选择"所有 **来宾用户"和"外部用户"。**</span><span class="sxs-lookup"><span data-stu-id="a17d9-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="a17d9-123">对于 **>条件>，** 保留所有选项未选中状态，以始终在 MFA (多重) 。</span><span class="sxs-lookup"><span data-stu-id="a17d9-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="a17d9-124">当登录风险为中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="a17d9-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a17d9-125">修改此策略以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="a17d9-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="a17d9-126">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="a17d9-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="a17d9-127">修改此策略以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="a17d9-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="a17d9-128">若要在条件访问策略中包括或排除来宾和外部用户，>用户和组分配>**包含或** 排除，请检查所有 **来宾和外部用户**。 </span><span class="sxs-lookup"><span data-stu-id="a17d9-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![用于排除来宾和外部用户的控件的屏幕截图](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="a17d9-130">更多信息</span><span class="sxs-lookup"><span data-stu-id="a17d9-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="a17d9-131">使用 Microsoft Teams 的来宾和外部用户访问</span><span class="sxs-lookup"><span data-stu-id="a17d9-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="a17d9-132">Microsoft Teams 定义以下用户：</span><span class="sxs-lookup"><span data-stu-id="a17d9-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="a17d9-133">**来宾访问** 使用 Azure AD B2B 帐户，可添加为团队成员，并有权访问团队的通信和资源。</span><span class="sxs-lookup"><span data-stu-id="a17d9-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="a17d9-134">**外部** 访问适用于没有 B2B 帐户的外部用户。</span><span class="sxs-lookup"><span data-stu-id="a17d9-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="a17d9-135">外部用户访问包括邀请、通话、聊天和会议，但不包括团队成员身份和访问团队资源。</span><span class="sxs-lookup"><span data-stu-id="a17d9-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="a17d9-136">有关详细信息，请参阅来宾和团队 [的外部用户访问之间的比较](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="a17d9-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="a17d9-137">有关保护 Teams 的标识和设备访问策略详细信息，请参阅用于保护 Teams 聊天、组和文件的策略 [建议](teams-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a17d9-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="a17d9-138">始终要求来宾和外部用户使用 MFA</span><span class="sxs-lookup"><span data-stu-id="a17d9-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="a17d9-139">此策略会提示来宾在租户中注册 MFA，无论他们是否在家庭租户中注册了 MFA。</span><span class="sxs-lookup"><span data-stu-id="a17d9-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="a17d9-140">访问租户中的资源时，来宾和外部用户需要针对每个请求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="a17d9-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="a17d9-141">从基于风险的 MFA 中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="a17d9-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="a17d9-142">虽然组织可以使用 Azure AD Identity Protection 为 B2B 用户强制执行基于风险的策略，但由于 B2B 协作用户的身份已存储在其主目录中，因此在资源目录中实现 Azure AD Identity Protection 时存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="a17d9-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="a17d9-143">由于这些限制，Microsoft 建议从基于风险的 MFA 策略中排除来宾，并要求这些用户始终使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="a17d9-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="a17d9-144">有关详细信息，请参阅 [B2B 协作用户的身份保护限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="a17d9-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="a17d9-145">从设备管理中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="a17d9-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="a17d9-146">只有一个组织可以管理设备。</span><span class="sxs-lookup"><span data-stu-id="a17d9-146">Only one organization can manage a device.</span></span> <span data-ttu-id="a17d9-147">如果未将来宾和外部用户从要求设备符合性的策略中排除，这些策略将阻止这些用户。</span><span class="sxs-lookup"><span data-stu-id="a17d9-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="a17d9-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a17d9-148">Next step</span></span>

![步骤 4：Microsoft 365 云应用的策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="a17d9-150">为：</span><span class="sxs-lookup"><span data-stu-id="a17d9-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="a17d9-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a17d9-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="a17d9-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a17d9-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="a17d9-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="a17d9-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
