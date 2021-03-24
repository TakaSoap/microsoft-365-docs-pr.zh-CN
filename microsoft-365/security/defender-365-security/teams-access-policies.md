---
title: 推荐的 Teams 策略 - Microsoft 365 企业版 |Microsoft Docs
description: 介绍了 Microsoft 建议中有关如何保护 Teams 通信和文件访问的策略。
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
ms.openlocfilehash: 51dec80c541cd77a1d4813505d82429487e8381c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055164"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="766fd-103">用于保护 Teams 聊天、组和文件的策略建议</span><span class="sxs-lookup"><span data-stu-id="766fd-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="766fd-104">本文介绍如何实施推荐的标识和设备访问策略来保护 Microsoft Teams 聊天、组以及文件和日历等内容。</span><span class="sxs-lookup"><span data-stu-id="766fd-104">This article describes how to implement the recommended identity and device-access policies to protect Microsoft Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="766fd-105">本指南基于 [通用标识和设备访问](identity-access-policies.md)策略，并包含特定于 Teams 的其他信息。</span><span class="sxs-lookup"><span data-stu-id="766fd-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="766fd-106">由于 Teams 与其他产品集成，因此另请参阅有关保护 [SharePoint](sharepoint-file-access-policies.md) 网站和文件的策略建议和用于保护电子邮件 [的策略建议](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="766fd-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="766fd-107">这些建议基于针对 Teams 的三种不同安全和保护层，可基于你的需求粒度应用这些层：基线、敏感和高度管控。</span><span class="sxs-lookup"><span data-stu-id="766fd-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="766fd-108">可以在标识和设备访问配置中了解有关这些安全层以及这些建议所引用 [的策略的更多信息](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="766fd-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="766fd-109">本文包含特定于 Teams 部署的更多建议，以涵盖特定身份验证情况，包括针对组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="766fd-109">More recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="766fd-110">你需要遵循本指南，获得完整的安全体验。</span><span class="sxs-lookup"><span data-stu-id="766fd-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="766fd-111">在其他相关服务之前开始使用 Teams</span><span class="sxs-lookup"><span data-stu-id="766fd-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="766fd-112">无需启用相关服务，就无需开始使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="766fd-112">You don't need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="766fd-113">这些服务将全部"正常工作"。</span><span class="sxs-lookup"><span data-stu-id="766fd-113">These services will all "just work."</span></span> <span data-ttu-id="766fd-114">但是，您需要准备好管理以下与服务相关的元素：</span><span class="sxs-lookup"><span data-stu-id="766fd-114">However, you do need to be prepared to manage the following service-related elements:</span></span>

- <span data-ttu-id="766fd-115">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="766fd-115">Microsoft 365 groups</span></span>
- <span data-ttu-id="766fd-116">SharePoint 团队网站</span><span class="sxs-lookup"><span data-stu-id="766fd-116">SharePoint team sites</span></span>
- <span data-ttu-id="766fd-117">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="766fd-117">OneDrive for Business</span></span>
- <span data-ttu-id="766fd-118">Exchange 邮箱</span><span class="sxs-lookup"><span data-stu-id="766fd-118">Exchange mailboxes</span></span>
- <span data-ttu-id="766fd-119">Stream videos and Planner plans (if these services are enabled) </span><span class="sxs-lookup"><span data-stu-id="766fd-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="766fd-120">更新常见策略以包括 Teams</span><span class="sxs-lookup"><span data-stu-id="766fd-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="766fd-121">为了在 Teams 中保护聊天、组和内容，下图说明了从通用标识和设备访问策略更新的策略。</span><span class="sxs-lookup"><span data-stu-id="766fd-121">To protect chat, groups and content in Teams, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span> <span data-ttu-id="766fd-122">对于要更新的每个策略，请确保 Teams 和依赖服务包含在云应用的分配中。</span><span class="sxs-lookup"><span data-stu-id="766fd-122">For each policy to update, make sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

<span data-ttu-id="766fd-123">[![用于保护对 Teams 及其从属服务的访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span><span class="sxs-lookup"><span data-stu-id="766fd-123">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span></span>

<span data-ttu-id="766fd-124">这些服务是分配 Teams 云应用时要包括的从属服务：</span><span class="sxs-lookup"><span data-stu-id="766fd-124">These services are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="766fd-125">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="766fd-125">Microsoft Teams</span></span>
- <span data-ttu-id="766fd-126">Sharepoint 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="766fd-126">SharePoint and OneDrive for Business</span></span>
- <span data-ttu-id="766fd-127">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="766fd-127">Exchange Online</span></span>
- <span data-ttu-id="766fd-128">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="766fd-128">Skype for Business Online</span></span>
- <span data-ttu-id="766fd-129">Microsoft Stream (会议录制) </span><span class="sxs-lookup"><span data-stu-id="766fd-129">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="766fd-130">Microsoft Planner (Planner 任务和规划数据) </span><span class="sxs-lookup"><span data-stu-id="766fd-130">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="766fd-131">此表列出了需要重新访问的策略以及指向通用标识和设备访问策略中每个策略的链接[](identity-access-policies.md)，这些策略具有针对所有 Office 应用程序的更大策略集。</span><span class="sxs-lookup"><span data-stu-id="766fd-131">This table lists the policies that need to be revisited and links to each policy in the [common identity and device access policies](identity-access-policies.md), which has the wider policy set for all Office applications.</span></span>

|<span data-ttu-id="766fd-132">保护级别</span><span class="sxs-lookup"><span data-stu-id="766fd-132">Protection level</span></span>|<span data-ttu-id="766fd-133">策略</span><span class="sxs-lookup"><span data-stu-id="766fd-133">Policies</span></span>|<span data-ttu-id="766fd-134">有关 Teams 实施的进一步信息</span><span class="sxs-lookup"><span data-stu-id="766fd-134">Further information for Teams implementation</span></span>|
|---|---|---|
|<span data-ttu-id="766fd-135">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="766fd-135">**Baseline**</span></span>|[<span data-ttu-id="766fd-136">当登录风险为中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="766fd-136">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="766fd-137">请确保 Teams 和从属服务包含在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="766fd-137">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="766fd-138">Teams 也有要考虑的来宾访问和外部访问规则，你将在本文的稍后部分了解有关这些规则的更多内容。</span><span class="sxs-lookup"><span data-stu-id="766fd-138">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span>|
||[<span data-ttu-id="766fd-139">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="766fd-139">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="766fd-140">分配云应用时包括 Teams 和从属服务。</span><span class="sxs-lookup"><span data-stu-id="766fd-140">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="766fd-141">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="766fd-141">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="766fd-142">如果为 Teams 用户的帐户检测到高风险活动，则强制 Teams 用户在登录时更改其密码。</span><span class="sxs-lookup"><span data-stu-id="766fd-142">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="766fd-143">请确保 Teams 和从属服务包含在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="766fd-143">Be sure Teams and dependent services are included in the list of apps.</span></span>|
||[<span data-ttu-id="766fd-144">应用 APP 数据保护策略</span><span class="sxs-lookup"><span data-stu-id="766fd-144">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="766fd-145">请确保 Teams 和从属服务包含在应用列表中。</span><span class="sxs-lookup"><span data-stu-id="766fd-145">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="766fd-146">针对 iOS、Android、Windows () 的每个平台更新) 。</span><span class="sxs-lookup"><span data-stu-id="766fd-146">Update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="766fd-147">定义设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="766fd-147">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="766fd-148">在此策略中包括 Teams 和从属服务。</span><span class="sxs-lookup"><span data-stu-id="766fd-148">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="766fd-149">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="766fd-149">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="766fd-150">在此策略中包括 Teams 和从属服务。</span><span class="sxs-lookup"><span data-stu-id="766fd-150">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="766fd-151">**敏感**</span><span class="sxs-lookup"><span data-stu-id="766fd-151">**Sensitive**</span></span>|[<span data-ttu-id="766fd-152">登录风险低、中或高 *时需要* MFA</span><span class="sxs-lookup"><span data-stu-id="766fd-152">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="766fd-153">Teams 也有要考虑的来宾访问和外部访问规则，你将在本文的稍后部分了解有关这些规则的更多内容。</span><span class="sxs-lookup"><span data-stu-id="766fd-153">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span> <span data-ttu-id="766fd-154">在此策略中包括 Teams 和从属服务。</span><span class="sxs-lookup"><span data-stu-id="766fd-154">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="766fd-155">要求兼容电脑 *和* 移动设备</span><span class="sxs-lookup"><span data-stu-id="766fd-155">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="766fd-156">在此策略中包括 Teams 和从属服务。</span><span class="sxs-lookup"><span data-stu-id="766fd-156">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="766fd-157">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="766fd-157">**Highly regulated**</span></span>|[<span data-ttu-id="766fd-158">*始终* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="766fd-158">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="766fd-159">无论用户身份如何，组织都将使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="766fd-159">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="766fd-160">在此策略中包括 Teams 和从属服务。</span><span class="sxs-lookup"><span data-stu-id="766fd-160">Include Teams and dependent services in this policy.</span></span> |
|

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="766fd-161">Teams 相关服务体系结构</span><span class="sxs-lookup"><span data-stu-id="766fd-161">Teams dependent services architecture</span></span>

<span data-ttu-id="766fd-162">为了参考，下图说明了 Teams 所依赖的服务。</span><span class="sxs-lookup"><span data-stu-id="766fd-162">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="766fd-163">有关详细信息和图示，请参阅适用于 IT 架构师的 Microsoft Teams 和 [Microsoft 365 中的相关生产力服务](../../solutions/productivity-illustrations.md)。</span><span class="sxs-lookup"><span data-stu-id="766fd-163">For more information and illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../../solutions/productivity-illustrations.md).</span></span>

<span data-ttu-id="766fd-164">[![显示 SharePoint、OneDrive for Business 和 Exchange 上的 Teams 依赖项的关系图](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span><span class="sxs-lookup"><span data-stu-id="766fd-164">[![Diagram showing Teams dependencies on SharePoint, OneDrive for Business, and Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span></span>

[<span data-ttu-id="766fd-165">查看此图像的较大版本</span><span class="sxs-lookup"><span data-stu-id="766fd-165">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a><span data-ttu-id="766fd-166">Teams 的来宾和外部访问</span><span class="sxs-lookup"><span data-stu-id="766fd-166">Guest and external access for Teams</span></span>

<span data-ttu-id="766fd-167">Microsoft Teams 定义以下访问类型：</span><span class="sxs-lookup"><span data-stu-id="766fd-167">Microsoft Teams defines the following access types:</span></span>

- <span data-ttu-id="766fd-168">**来宾访问** 使用 Azure AD B2B 帐户作为来宾或外部用户，可以添加为团队成员，并且具有访问团队通信和资源的所有权限。</span><span class="sxs-lookup"><span data-stu-id="766fd-168">**Guest access** uses an Azure AD B2B account for a guest or external user that can be added as a member of a team and have all permissioned access to the communication and resources of the team.</span></span>

- <span data-ttu-id="766fd-169">**外部访问** 适用于没有 Azure AD B2B 帐户的外部用户。</span><span class="sxs-lookup"><span data-stu-id="766fd-169">**External access** is for an external user that does not have an Azure AD B2B account.</span></span> <span data-ttu-id="766fd-170">外部访问可以包括邀请和参与通话、聊天和会议，但不包括团队成员身份和访问团队资源。</span><span class="sxs-lookup"><span data-stu-id="766fd-170">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="766fd-171">条件访问策略仅适用于 Teams 中的来宾访问，因为存在相应的 Azure AD B2B 帐户。</span><span class="sxs-lookup"><span data-stu-id="766fd-171">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

<span data-ttu-id="766fd-172">有关允许使用 Azure AD B2B 帐户的来宾和外部用户访问的建议策略，请参阅允许来宾和外部 [B2B 帐户访问的策略](identity-access-policies-guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="766fd-172">For recommended policies to allow access for guest and external users with an Azure AD B2B account, see [Policies for allowing guest and external B2B account access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="766fd-173">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="766fd-173">Guest access in Teams</span></span>

<span data-ttu-id="766fd-174">除了针对企业或组织内部用户的策略之外，管理员还允许来宾访问以用户为基础，允许企业或组织外部人员访问 Teams 资源，并与内部人员进行群组对话、聊天和会议等操作。</span><span class="sxs-lookup"><span data-stu-id="766fd-174">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span>

<span data-ttu-id="766fd-175">有关来宾访问以及如何实现它的信息，请参阅  [Teams 来宾访问](/microsoftteams/guest-access)。</span><span class="sxs-lookup"><span data-stu-id="766fd-175">For more information about guest access and how to implement it, see  [Teams guest access](/microsoftteams/guest-access).</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="766fd-176">Teams 中的外部访问</span><span class="sxs-lookup"><span data-stu-id="766fd-176">External access in Teams</span></span>

<span data-ttu-id="766fd-177">外部访问有时与来宾访问混淆，因此必须明确这两种非内部访问机制是不同类型的访问。</span><span class="sxs-lookup"><span data-stu-id="766fd-177">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are different types of access.</span></span>

<span data-ttu-id="766fd-178">外部访问是整个外部域中的 Teams 用户在 Teams 中查找、呼叫、聊天和设置与用户的会议的一种方式。</span><span class="sxs-lookup"><span data-stu-id="766fd-178">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with your users in Teams.</span></span> <span data-ttu-id="766fd-179">Teams 管理员在组织级别配置外部访问。</span><span class="sxs-lookup"><span data-stu-id="766fd-179">Teams administrators configure external access at the organization level.</span></span> <span data-ttu-id="766fd-180">有关详细信息，请参阅在 [Microsoft Teams 中管理外部访问](/microsoftteams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="766fd-180">For more information, see [Manage external access in Microsoft Teams](/microsoftteams/manage-external-access).</span></span>

<span data-ttu-id="766fd-181">与通过来宾访问添加的用户相比，外部访问用户具有的访问和功能更少。</span><span class="sxs-lookup"><span data-stu-id="766fd-181">External access users have less access and functionality than an individual who's been added via guest access.</span></span> <span data-ttu-id="766fd-182">例如，外部访问用户可以使用 Teams 与内部用户聊天，但不能访问团队频道、文件或其他资源。</span><span class="sxs-lookup"><span data-stu-id="766fd-182">For example, external access users can chat with your internal users with Teams but cannot access team channels, files, or other resources.</span></span>

<span data-ttu-id="766fd-183">外部访问不使用 Azure AD B2B 用户帐户，因此不使用条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="766fd-183">External access does not use Azure AD B2B user accounts and therefore does not use Conditional Access policies.</span></span>

## <a name="teams-policies"></a><span data-ttu-id="766fd-184">Teams 策略</span><span class="sxs-lookup"><span data-stu-id="766fd-184">Teams policies</span></span>

<span data-ttu-id="766fd-185">除了上面列出的常见策略之外，还可以且应该配置特定于 Teams 的策略来管理各种 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="766fd-185">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="766fd-186">Teams 和频道策略</span><span class="sxs-lookup"><span data-stu-id="766fd-186">Teams and channels policies</span></span>

<span data-ttu-id="766fd-187">Teams 和频道是 Microsoft Teams 中常用的两个元素，你可以制定一些策略来控制用户在使用团队和频道时可以执行和不能执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="766fd-187">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="766fd-188">虽然可以创建一个全局团队，但如果贵组织的用户数小于或小于 5000，则可能会发现，与组织需求一起，让较小的团队和频道用于特定用途可能会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="766fd-188">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="766fd-189">建议更改默认策略或创建自定义策略，你可以在此链接中了解有关管理策略的更多信息： [在 Microsoft Teams](/microsoftteams/teams-policies)中管理团队策略。</span><span class="sxs-lookup"><span data-stu-id="766fd-189">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="766fd-190">邮件策略</span><span class="sxs-lookup"><span data-stu-id="766fd-190">Messaging policies</span></span>

<span data-ttu-id="766fd-191">消息或聊天也可通过默认全局策略或自定义策略进行管理，这可帮助用户以适合贵组织的方式相互通信。</span><span class="sxs-lookup"><span data-stu-id="766fd-191">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="766fd-192">可以在管理 Teams 中的消息传递 [策略中查看此信息](/microsoftteams/messaging-policies-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="766fd-192">This information can be reviewed at [Managing messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="766fd-193">会议策略</span><span class="sxs-lookup"><span data-stu-id="766fd-193">Meeting policies</span></span>

<span data-ttu-id="766fd-194">如果不规划和实施有关 Teams 会议的策略，就无法完成有关 Teams 的讨论。</span><span class="sxs-lookup"><span data-stu-id="766fd-194">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="766fd-195">会议是 Teams 的一个基本组件，允许用户一次正式开会并呈现给许多用户，并共享与会议相关的内容。</span><span class="sxs-lookup"><span data-stu-id="766fd-195">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, and to share content relevant to the meeting.</span></span> <span data-ttu-id="766fd-196">为组织围绕会议设置正确的策略至关重要。</span><span class="sxs-lookup"><span data-stu-id="766fd-196">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="766fd-197">有关详细信息，请参阅在 [Teams 中管理会议策略](/microsoftteams/meeting-policies-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="766fd-197">For more information, review [Manage meeting policies in Teams](/microsoftteams/meeting-policies-in-teams).</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="766fd-198">应用程序权限策略</span><span class="sxs-lookup"><span data-stu-id="766fd-198">App permission policies</span></span>

<span data-ttu-id="766fd-199">Teams 还允许你在各种位置（如频道或个人聊天）使用应用。</span><span class="sxs-lookup"><span data-stu-id="766fd-199">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="766fd-200">对于维护同样安全的内容丰富的环境来说，制定有关可添加和使用的应用的策略以及在何处添加策略至关重要。</span><span class="sxs-lookup"><span data-stu-id="766fd-200">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="766fd-201">有关应用权限策略的更多阅读，请查看在 [Microsoft Teams 中管理应用权限策略](/microsoftteams/teams-app-permission-policies)。</span><span class="sxs-lookup"><span data-stu-id="766fd-201">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="766fd-202">后续步骤</span><span class="sxs-lookup"><span data-stu-id="766fd-202">Next steps</span></span>

![步骤 4：Microsoft 365 云应用策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="766fd-204">为：配置条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="766fd-204">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="766fd-205">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="766fd-205">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="766fd-206">SharePoint</span><span class="sxs-lookup"><span data-stu-id="766fd-206">SharePoint</span></span>](sharepoint-file-access-policies.md)