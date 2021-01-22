---
title: 推荐的 Teams 策略 - Microsoft 365 企业版|Microsoft Docs
description: 介绍了 Microsoft 有关如何保护 Teams 通信和文件访问的策略。
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 7724ef76d905cdbaf48f3122d0df7ef28d0b8385
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931622"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="0294d-103">用于保护 Teams 聊天、组和文件的策略建议</span><span class="sxs-lookup"><span data-stu-id="0294d-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="0294d-104">本文介绍如何实施推荐的标识和设备访问策略来保护 Microsoft Teams 聊天、组以及文件和日历等内容。</span><span class="sxs-lookup"><span data-stu-id="0294d-104">This article describes how to implement the recommended identity and device-access policies to protect Microsoft Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="0294d-105">本指南基于通用 [标识和设备访问策略](identity-access-policies.md)，以及特定于 Teams 的其他信息。</span><span class="sxs-lookup"><span data-stu-id="0294d-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="0294d-106">由于 Teams 与其他产品集成，因此还请参阅有关保护 [SharePoint](sharepoint-file-access-policies.md) 网站和文件的策略建议，以及用于保护电子邮件 [的策略建议](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0294d-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="0294d-107">这些建议基于针对 Teams 的三个不同安全和保护层，可基于你的需求粒度应用这些层：基线、敏感和高度管控。</span><span class="sxs-lookup"><span data-stu-id="0294d-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="0294d-108">可以在标识和设备访问配置中了解有关这些安全层以及这些建议所引用 [的建议策略的更多信息](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="0294d-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="0294d-109">本文包含特定于 Teams 部署的其他建议，以涵盖特定身份验证情况，包括针对组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="0294d-109">Additional recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="0294d-110">你将需要遵循本指南，获得完整的安全体验。</span><span class="sxs-lookup"><span data-stu-id="0294d-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="0294d-111">在其他相关服务之前开始使用 Teams</span><span class="sxs-lookup"><span data-stu-id="0294d-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="0294d-112">无需启用相关服务，就无需开始使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="0294d-112">You don't need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="0294d-113">这些都将"正常工作"。</span><span class="sxs-lookup"><span data-stu-id="0294d-113">These will all "just work."</span></span> <span data-ttu-id="0294d-114">但是，您需要准备好管理以下各项：</span><span class="sxs-lookup"><span data-stu-id="0294d-114">However, you do need to be prepared to manage the following:</span></span>

- <span data-ttu-id="0294d-115">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="0294d-115">Microsoft 365 groups</span></span>
- <span data-ttu-id="0294d-116">SharePoint 团队网站</span><span class="sxs-lookup"><span data-stu-id="0294d-116">SharePoint team sites</span></span>
- <span data-ttu-id="0294d-117">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="0294d-117">OneDrive for Business</span></span>
- <span data-ttu-id="0294d-118">Exchange 邮箱</span><span class="sxs-lookup"><span data-stu-id="0294d-118">Exchange mailboxes</span></span>
- <span data-ttu-id="0294d-119">如果启用了这些服务， (流视频和 Planner 计划) </span><span class="sxs-lookup"><span data-stu-id="0294d-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="0294d-120">更新常见策略以包含 Teams</span><span class="sxs-lookup"><span data-stu-id="0294d-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="0294d-121">为了保护 Teams 中的聊天、组和内容，下图说明了从通用标识和设备访问策略更新的策略。</span><span class="sxs-lookup"><span data-stu-id="0294d-121">To protect chat, groups and content in Teams, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span> <span data-ttu-id="0294d-122">对于要更新的每个策略，请确保 Teams 和依赖服务包含在云应用的分配中。</span><span class="sxs-lookup"><span data-stu-id="0294d-122">For each policy to update, make sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

<span data-ttu-id="0294d-123">[![用于保护对 Teams 及其从属服务的访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span><span class="sxs-lookup"><span data-stu-id="0294d-123">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span></span>

[<span data-ttu-id="0294d-124">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="0294d-124">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

<span data-ttu-id="0294d-125">这些是分配 Teams 云应用时要包括的依赖服务：</span><span class="sxs-lookup"><span data-stu-id="0294d-125">These are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="0294d-126">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0294d-126">Microsoft Teams</span></span>
- <span data-ttu-id="0294d-127">Sharepoint 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="0294d-127">SharePoint and OneDrive for Business</span></span>
- <span data-ttu-id="0294d-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0294d-128">Exchange Online</span></span>
- <span data-ttu-id="0294d-129">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0294d-129">Skype for Business Online</span></span>
- <span data-ttu-id="0294d-130">Microsoft Stream (会议录制) </span><span class="sxs-lookup"><span data-stu-id="0294d-130">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="0294d-131">Microsoft Planner (Planner 任务和规划) </span><span class="sxs-lookup"><span data-stu-id="0294d-131">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="0294d-132">此表列出了需要重新访问的策略以及指向通用标识和设备访问策略中每个策略的链接[](identity-access-policies.md)，这些策略具有针对所有 Office 应用程序的较宽策略集。</span><span class="sxs-lookup"><span data-stu-id="0294d-132">This table lists the policies that need to be revisited and links to each policy in the [common identity and device access policies](identity-access-policies.md), which has the wider policy set for all Office applications.</span></span>

|<span data-ttu-id="0294d-133">保护级别</span><span class="sxs-lookup"><span data-stu-id="0294d-133">Protection level</span></span>|<span data-ttu-id="0294d-134">策略</span><span class="sxs-lookup"><span data-stu-id="0294d-134">Policies</span></span>|<span data-ttu-id="0294d-135">有关 Teams 实施的进一步信息</span><span class="sxs-lookup"><span data-stu-id="0294d-135">Further information for Teams implementation</span></span>|
|---|---|---|
|<span data-ttu-id="0294d-136">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="0294d-136">**Baseline**</span></span>|[<span data-ttu-id="0294d-137">当登录风险为中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="0294d-137">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="0294d-138">请确保 Teams 和从属服务包含在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="0294d-138">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="0294d-139">Teams 还有要考虑的来宾访问和外部访问规则，你将在本文的稍后部分了解有关这些规则的更多内容。</span><span class="sxs-lookup"><span data-stu-id="0294d-139">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span>|
||[<span data-ttu-id="0294d-140">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="0294d-140">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="0294d-141">在分配云应用时包括 Teams 和从属服务。</span><span class="sxs-lookup"><span data-stu-id="0294d-141">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="0294d-142">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="0294d-142">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="0294d-143">如果检测到其帐户存在高风险活动，则强制 Teams 用户在登录时更改其密码。</span><span class="sxs-lookup"><span data-stu-id="0294d-143">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="0294d-144">请确保 Teams 和从属服务包含在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="0294d-144">Be sure Teams and dependent services are included in the list of apps.</span></span>|
||[<span data-ttu-id="0294d-145">应用 APP 数据保护策略</span><span class="sxs-lookup"><span data-stu-id="0294d-145">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="0294d-146">请确保 Teams 和从属服务包含在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="0294d-146">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="0294d-147">为 iOS、 (Android、Windows) 的每个平台更新) 。</span><span class="sxs-lookup"><span data-stu-id="0294d-147">Update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="0294d-148">定义设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="0294d-148">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="0294d-149">在此策略中包括 Teams 和依赖服务。</span><span class="sxs-lookup"><span data-stu-id="0294d-149">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="0294d-150">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="0294d-150">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="0294d-151">在此策略中包括 Teams 和从属服务。</span><span class="sxs-lookup"><span data-stu-id="0294d-151">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="0294d-152">**敏感**</span><span class="sxs-lookup"><span data-stu-id="0294d-152">**Sensitive**</span></span>|[<span data-ttu-id="0294d-153">当登录风险较低、中等或高时需要MFA </span><span class="sxs-lookup"><span data-stu-id="0294d-153">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="0294d-154">Teams 还有要考虑的来宾访问和外部访问规则，你将在本文的稍后部分了解有关这些规则的更多内容。</span><span class="sxs-lookup"><span data-stu-id="0294d-154">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span> <span data-ttu-id="0294d-155">在此策略中包括 Teams 和依赖服务。</span><span class="sxs-lookup"><span data-stu-id="0294d-155">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="0294d-156">要求 *兼容电脑和* 移动设备</span><span class="sxs-lookup"><span data-stu-id="0294d-156">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="0294d-157">在此策略中包括 Teams 和依赖服务。</span><span class="sxs-lookup"><span data-stu-id="0294d-157">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="0294d-158">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="0294d-158">**Highly regulated**</span></span>|[<span data-ttu-id="0294d-159">*始终* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="0294d-159">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="0294d-160">无论用户标识如何，组织都将使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="0294d-160">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="0294d-161">在此策略中包括 Teams 和从属服务。</span><span class="sxs-lookup"><span data-stu-id="0294d-161">Include Teams and dependent services in this policy.</span></span> |
|

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="0294d-162">与 Teams 相关的服务体系结构</span><span class="sxs-lookup"><span data-stu-id="0294d-162">Teams dependent services architecture</span></span>

<span data-ttu-id="0294d-163">为了参考，下图说明了 Teams 所依赖的服务。</span><span class="sxs-lookup"><span data-stu-id="0294d-163">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="0294d-164">有关详细信息和其他插图，请参阅适用于 IT 架构师的 [Microsoft 365 中的 Microsoft Teams 和相关生产力服务](../../solutions/productivity-illustrations.md)。</span><span class="sxs-lookup"><span data-stu-id="0294d-164">For more information and additional illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../../solutions/productivity-illustrations.md).</span></span>

<span data-ttu-id="0294d-165">[![显示 SharePoint、OneDrive for Business 和 Exchange 上的 Teams 依赖项的关系图](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span><span class="sxs-lookup"><span data-stu-id="0294d-165">[![Diagram showing Teams dependencies on SharePoint, OneDrive for Business, and Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span></span>

[<span data-ttu-id="0294d-166">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="0294d-166">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a><span data-ttu-id="0294d-167">Teams 的来宾和外部访问</span><span class="sxs-lookup"><span data-stu-id="0294d-167">Guest and external access for Teams</span></span>

<span data-ttu-id="0294d-168">Microsoft Teams 定义以下内容：</span><span class="sxs-lookup"><span data-stu-id="0294d-168">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="0294d-169">**来宾访问** 使用 Azure AD B2B 帐户作为来宾或外部用户，可添加为团队成员，并拥有访问团队通信和资源的所有权限。</span><span class="sxs-lookup"><span data-stu-id="0294d-169">**Guest access** uses an Azure AD B2B account for a guest or external user that can be added as a member of a team and have all permissioned access to the communication and resources of the team.</span></span>

- <span data-ttu-id="0294d-170">**外部访问** 适用于没有 Azure AD B2B 帐户的外部用户。</span><span class="sxs-lookup"><span data-stu-id="0294d-170">**External access** is for an external user that does not have an Azure AD B2B account.</span></span> <span data-ttu-id="0294d-171">外部访问可以包括邀请和参与通话、聊天和会议，但不包括团队成员身份和访问团队资源。</span><span class="sxs-lookup"><span data-stu-id="0294d-171">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="0294d-172">条件访问策略仅适用于 Teams 中的来宾访问，因为存在相应的 Azure AD B2B 帐户。</span><span class="sxs-lookup"><span data-stu-id="0294d-172">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

<span data-ttu-id="0294d-173">有关允许使用 Azure AD B2B 帐户的来宾和外部用户访问的建议策略，请参阅用于允许来宾和外部 [B2B 帐户访问的策略](identity-access-policies-guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="0294d-173">For recommended policies to allow access for guest and external users with an Azure AD B2B account, see [Policies for allowing guest and external B2B account access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="0294d-174">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="0294d-174">Guest access in Teams</span></span>

<span data-ttu-id="0294d-175">除了针对企业或组织内部用户的策略外，管理员还可能会启用来宾访问，以允许企业或组织外部的用户以用户为基础访问 Teams 资源，并与内部人员进行群组对话、聊天和会议等操作。</span><span class="sxs-lookup"><span data-stu-id="0294d-175">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span>

<span data-ttu-id="0294d-176">有关来宾访问以及如何实现它的信息，请参阅  [Teams 来宾访问](https://docs.microsoft.com/microsoftteams/guest-access)。</span><span class="sxs-lookup"><span data-stu-id="0294d-176">For more information about guest access and how to implement it, see  [Teams guest access](https://docs.microsoft.com/microsoftteams/guest-access).</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="0294d-177">Teams 中的外部访问</span><span class="sxs-lookup"><span data-stu-id="0294d-177">External access in Teams</span></span>

<span data-ttu-id="0294d-178">外部访问有时与来宾访问混淆，因此必须明确这两个非内部访问机制实际上截然不同。</span><span class="sxs-lookup"><span data-stu-id="0294d-178">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are actually quite different.</span></span>

<span data-ttu-id="0294d-179">外部访问是一种供整个外部域中的 Teams 用户在 Teams 中查找、呼叫、聊天和设置与用户的会议的方法。</span><span class="sxs-lookup"><span data-stu-id="0294d-179">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with your users in Teams.</span></span> <span data-ttu-id="0294d-180">Teams 管理员在组织级别配置外部访问。</span><span class="sxs-lookup"><span data-stu-id="0294d-180">Teams administrators configure external access at the organization level.</span></span> <span data-ttu-id="0294d-181">有关详细信息，请参阅"在[Microsoft Teams 中管理外部访问"。](https://docs.microsoft.com/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="0294d-181">For more information, see [Manage external access in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access).</span></span>

<span data-ttu-id="0294d-182">与通过来宾访问添加的用户相比，外部访问用户具有的访问和功能更少。</span><span class="sxs-lookup"><span data-stu-id="0294d-182">External access users have less access and functionality than an individual who's been added via guest access.</span></span> <span data-ttu-id="0294d-183">例如，外部访问用户可以使用 Teams 与内部用户聊天，但无法访问团队频道、文件或其他资源。</span><span class="sxs-lookup"><span data-stu-id="0294d-183">For example, external access users can chat with your internal users with Teams but cannot access team channels, files, or other resources.</span></span>

<span data-ttu-id="0294d-184">外部访问不使用 Azure AD B2B 用户帐户，因此不使用条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="0294d-184">External access does not use Azure AD B2B user accounts and therefore does not use Conditional Access policies.</span></span>

## <a name="teams-policies"></a><span data-ttu-id="0294d-185">Teams 策略</span><span class="sxs-lookup"><span data-stu-id="0294d-185">Teams policies</span></span>

<span data-ttu-id="0294d-186">除了上面列出的常见策略外，还可以且应该将 Teams 特定的策略配置为管理各种 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="0294d-186">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="0294d-187">Teams 和频道策略</span><span class="sxs-lookup"><span data-stu-id="0294d-187">Teams and channels policies</span></span>

<span data-ttu-id="0294d-188">Teams 和频道是 Microsoft Teams 中常用的两个元素，你可以制定一些策略来控制用户在使用团队和频道时可以和不能执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="0294d-188">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="0294d-189">虽然可以创建全局团队，但如果贵组织的用户数小于或小于 5000，则可能会发现在组织需求内，将较小的团队和频道用于特定用途会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="0294d-189">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="0294d-190">建议更改默认策略或创建自定义策略，你可以在此链接中了解有关管理策略的更多信息：在 Microsoft Teams 中 [管理团队策略](https://docs.microsoft.com/microsoftteams/teams-policies)。</span><span class="sxs-lookup"><span data-stu-id="0294d-190">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="0294d-191">邮件策略</span><span class="sxs-lookup"><span data-stu-id="0294d-191">Messaging policies</span></span>

<span data-ttu-id="0294d-192">消息或聊天也可通过默认全局策略或自定义策略进行管理，这可帮助用户以适合组织的方式相互通信。</span><span class="sxs-lookup"><span data-stu-id="0294d-192">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="0294d-193">可以在 Teams 中管理 [邮件策略中查看此信息](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="0294d-193">This information can be reviewed at [Managing messaging policies in Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="0294d-194">会议策略</span><span class="sxs-lookup"><span data-stu-id="0294d-194">Meeting policies</span></span>

<span data-ttu-id="0294d-195">如果不规划和实施有关 Teams 会议的策略，就无法完成有关 Teams 的讨论。</span><span class="sxs-lookup"><span data-stu-id="0294d-195">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="0294d-196">会议是 Teams 的一个基本组件，允许用户一次正式开会并呈现给许多用户，并共享与会议相关的内容。</span><span class="sxs-lookup"><span data-stu-id="0294d-196">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, as well as share content relevant to the meeting.</span></span> <span data-ttu-id="0294d-197">为组织围绕会议设置正确的策略至关重要。</span><span class="sxs-lookup"><span data-stu-id="0294d-197">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="0294d-198">有关详细信息， [请查看 Teams 中的](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) "管理会议策略"。</span><span class="sxs-lookup"><span data-stu-id="0294d-198">Please review [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) for more information.</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="0294d-199">应用权限策略</span><span class="sxs-lookup"><span data-stu-id="0294d-199">App permission policies</span></span>

<span data-ttu-id="0294d-200">Teams 还允许你在各种位置（如频道或个人聊天）使用应用。</span><span class="sxs-lookup"><span data-stu-id="0294d-200">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="0294d-201">制定有关可以添加和使用的应用的策略以及在何处，对于维护同样安全的丰富内容环境至关重要。</span><span class="sxs-lookup"><span data-stu-id="0294d-201">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="0294d-202">有关应用权限策略的更多阅读，请查看[Microsoft Teams 中的"管理应用权限策略"。](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)</span><span class="sxs-lookup"><span data-stu-id="0294d-202">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0294d-203">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0294d-203">Next steps</span></span>

![步骤 4：Microsoft 365 云应用的策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="0294d-205">为：</span><span class="sxs-lookup"><span data-stu-id="0294d-205">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="0294d-206">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0294d-206">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="0294d-207">SharePoint</span><span class="sxs-lookup"><span data-stu-id="0294d-207">SharePoint</span></span>](sharepoint-file-access-policies.md)
