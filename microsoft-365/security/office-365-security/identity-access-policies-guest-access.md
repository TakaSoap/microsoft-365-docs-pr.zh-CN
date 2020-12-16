---
title: 用于允许来宾和外部 B2B 访问的标识和设备访问策略 - Microsoft 365 企业版 |Microsoft Docs
description: 介绍用于保护来宾和外部用户访问的建议条件访问和相关策略。
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
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 376845d8e3657b91b9efe0357e94f4bec3a84078
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688274"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="df8fe-103">允许来宾和外部 B2B 访问的策略</span><span class="sxs-lookup"><span data-stu-id="df8fe-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="df8fe-104">本文介绍如何调整推荐的常见标识和设备访问策略，以允许具有 Azure Active Directory (Azure AD) 企业到企业 (B2B) 帐户的来宾和外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="df8fe-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="df8fe-105">本指南基于通用 [标识和设备访问策略](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="df8fe-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="df8fe-106">这些建议旨在应用于 **保护的基线** 层。</span><span class="sxs-lookup"><span data-stu-id="df8fe-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="df8fe-107">但是，您还可以根据敏感和高度管控保护需求的粒度 **调整建议**。 </span><span class="sxs-lookup"><span data-stu-id="df8fe-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="df8fe-108">为 B2B 帐户提供向 Azure AD 租户进行身份验证的路径不会向这些帐户授予访问整个环境的访问权限。</span><span class="sxs-lookup"><span data-stu-id="df8fe-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="df8fe-109">B2B 用户及其帐户只能访问与它们共享的资源 (例如，) 条件访问策略中授予的服务中的文件。</span><span class="sxs-lookup"><span data-stu-id="df8fe-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="df8fe-110">更新常见策略以允许和保护来宾和外部访问</span><span class="sxs-lookup"><span data-stu-id="df8fe-110">Updating the common policies to allow and protect guest and external access</span></span>

<span data-ttu-id="df8fe-111">若要使用 Azure AD B2B 帐户保护来宾和外部访问，下图说明了从通用标识和设备访问策略添加或更新的策略。</span><span class="sxs-lookup"><span data-stu-id="df8fe-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span>

<span data-ttu-id="df8fe-112">[![用于保护来宾访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="df8fe-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="df8fe-113">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="df8fe-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="df8fe-114">下表列出了创建和更新所需的策略。</span><span class="sxs-lookup"><span data-stu-id="df8fe-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="df8fe-115">常见策略链接到通用标识和设备访问策略文章中的 [关联配置](identity-access-policies.md) 说明。</span><span class="sxs-lookup"><span data-stu-id="df8fe-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="df8fe-116">保护级别</span><span class="sxs-lookup"><span data-stu-id="df8fe-116">Protection level</span></span>|<span data-ttu-id="df8fe-117">策略</span><span class="sxs-lookup"><span data-stu-id="df8fe-117">Policies</span></span>|<span data-ttu-id="df8fe-118">更多信息</span><span class="sxs-lookup"><span data-stu-id="df8fe-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="df8fe-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="df8fe-119">**Baseline**</span></span>|[<span data-ttu-id="df8fe-120">始终要求来宾用户和外部用户使用 MFA</span><span class="sxs-lookup"><span data-stu-id="df8fe-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="df8fe-121">创建此新策略并配置：</span><span class="sxs-lookup"><span data-stu-id="df8fe-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="df8fe-122">对于 **分配>包括** 的用户和组>，选择"选择用户 **和组**"，然后选择"所有 **来宾用户"和"外部用户"。**</span><span class="sxs-lookup"><span data-stu-id="df8fe-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="df8fe-123">对于 **>条件>，** 保留所有选项未选中状态，以始终在 MFA (多重) 。</span><span class="sxs-lookup"><span data-stu-id="df8fe-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="df8fe-124">当登录风险为中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="df8fe-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="df8fe-125">修改此策略以排除来宾用户和外部用户。</span><span class="sxs-lookup"><span data-stu-id="df8fe-125">Modify this policy to exclude guest and external users.</span></span>|
||[<span data-ttu-id="df8fe-126">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="df8fe-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="df8fe-127">修改此策略以排除来宾用户和外部用户。</span><span class="sxs-lookup"><span data-stu-id="df8fe-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="df8fe-128">若要在条件访问策略中包括或排除来宾用户和外部用户，>用户和组>**包含或** 排除，请检查所有来宾用户和 **外部用户**。</span><span class="sxs-lookup"><span data-stu-id="df8fe-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![用于排除来宾和外部用户的控件的屏幕截图](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="df8fe-130">更多信息</span><span class="sxs-lookup"><span data-stu-id="df8fe-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="df8fe-131">使用 Microsoft Teams 的来宾访问和外部访问</span><span class="sxs-lookup"><span data-stu-id="df8fe-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="df8fe-132">Microsoft Teams 定义以下内容：</span><span class="sxs-lookup"><span data-stu-id="df8fe-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="df8fe-133">**来宾访问** 使用 Azure AD B2B 帐户，该帐户可添加为团队成员，并拥有访问团队通信和资源的所有权限。</span><span class="sxs-lookup"><span data-stu-id="df8fe-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="df8fe-134">**外部访问** 适用于没有 B2B 帐户的外部用户。</span><span class="sxs-lookup"><span data-stu-id="df8fe-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="df8fe-135">外部访问可以包括邀请和参与通话、聊天和会议，但不包括团队成员身份和访问团队资源。</span><span class="sxs-lookup"><span data-stu-id="df8fe-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="df8fe-136">有关详细信息，请参阅团队 [的来宾访问和外部访问之间的比较](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="df8fe-136">For more information, see the [comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="df8fe-137">有关 [保护 Teams 的](teams-access-policies.md) 标识和设备访问策略详细信息，请参阅有关保护 Teams 聊天、组和文件的策略建议。</span><span class="sxs-lookup"><span data-stu-id="df8fe-137">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="df8fe-138">始终要求来宾用户和外部用户使用 MFA</span><span class="sxs-lookup"><span data-stu-id="df8fe-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="df8fe-139">此策略会提示来宾在租户中注册 MFA，无论他们是否在家庭租户中注册了 MFA。</span><span class="sxs-lookup"><span data-stu-id="df8fe-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="df8fe-140">访问租户中的资源时，来宾和外部用户需要针对每个请求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="df8fe-140">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="df8fe-141">从基于风险的 MFA 中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="df8fe-141">Excluding guest and external users from risk-based MFA</span></span>

<span data-ttu-id="df8fe-142">虽然组织可以使用 Azure AD Identity Protection 为 B2B 用户强制执行基于风险的策略，但由于 B2B 协作用户的身份已存储在其主目录中，因此在资源目录中实现 Azure AD Identity Protection 时存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="df8fe-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="df8fe-143">由于这些限制，Microsoft 建议从基于风险的 MFA 策略中排除来宾用户，并要求这些用户始终使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="df8fe-143">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="df8fe-144">有关详细信息，请参阅 [B2B 协作用户的身份保护限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="df8fe-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="df8fe-145">从设备管理中排除来宾用户和外部用户</span><span class="sxs-lookup"><span data-stu-id="df8fe-145">Excluding guest and external users from device management</span></span>

<span data-ttu-id="df8fe-146">只有一个组织可以管理设备。</span><span class="sxs-lookup"><span data-stu-id="df8fe-146">Only one organization can manage a device.</span></span> <span data-ttu-id="df8fe-147">如果未从要求设备符合性的策略中排除来宾用户和外部用户，则这些策略将阻止这些用户。</span><span class="sxs-lookup"><span data-stu-id="df8fe-147">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="df8fe-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="df8fe-148">Next step</span></span>

![步骤 4：Microsoft 365 云应用的策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="df8fe-150">为：</span><span class="sxs-lookup"><span data-stu-id="df8fe-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="df8fe-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df8fe-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="df8fe-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="df8fe-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="df8fe-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="df8fe-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
