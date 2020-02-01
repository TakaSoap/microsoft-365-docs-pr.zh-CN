---
title: 推荐的团队策略-Microsoft 365 企业版 |Microsoft 文档
description: 介绍有关如何保护团队通信和文件访问的 Microsoft 建议的策略。
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 10/31/2019
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 258e116e2d51a5fde9f6e9c3273824994b9dcfa6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596659"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="c4cd9-103">保护团队聊天、组和文件的策略建议</span><span class="sxs-lookup"><span data-stu-id="c4cd9-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="c4cd9-104">本文介绍如何实施建议的标识和设备访问策略来保护团队聊天、组和内容（如文件和日历）。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-104">This article describes how to implement the recommended identity and device-access policies to protect Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="c4cd9-105">本指南基于[通用标识和设备访问策略](identity-access-policies.md)构建，其中包含特定于团队的其他信息。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="c4cd9-106">由于团队与我们的其他产品集成，因此请参阅[保护 SharePoint 网站和文件](sharepoint-file-access-policies.md)以及[保护电子邮件的策略建议](secure-email-recommended-policies.md)的策略建议。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="c4cd9-107">这些建议基于三种不同的安全层级保护和针对团队的保护，这些团队可根据您需求的粒度进行应用：比较基准、敏感和高度管控。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="c4cd9-108">您可以在[标识和设备访问配置](microsoft-365-policies-configurations.md)中了解有关这些安全层以及这些建议所引用的建议策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="c4cd9-109">本文中包含特定于团队部署的其他建议，以涵盖特定身份验证环境，包括组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-109">Additional recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="c4cd9-110">您需要遵循本指南，以获得完整的安全体验。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="c4cd9-111">其他相关服务之前的团队入门</span><span class="sxs-lookup"><span data-stu-id="c4cd9-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="c4cd9-112">您无需启用相关服务即可开始使用 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-112">You don’t need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="c4cd9-113">这些都是正常工作的。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-113">These will all ‘just work.’</span></span> <span data-ttu-id="c4cd9-114">但是，您确实需要准备好管理以下内容：</span><span class="sxs-lookup"><span data-stu-id="c4cd9-114">However, you do need to be prepared to manage the following:</span></span>

- <span data-ttu-id="c4cd9-115">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="c4cd9-115">Office 365 groups</span></span>
- <span data-ttu-id="c4cd9-116">SharePoint 团队网站</span><span class="sxs-lookup"><span data-stu-id="c4cd9-116">SharePoint team sites</span></span>
- <span data-ttu-id="c4cd9-117">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="c4cd9-117">OneDrive for Business</span></span>
- <span data-ttu-id="c4cd9-118">邮箱</span><span class="sxs-lookup"><span data-stu-id="c4cd9-118">Mailboxes</span></span>
- <span data-ttu-id="c4cd9-119">流式传输视频和 Planner 计划（如果已启用这些服务）</span><span class="sxs-lookup"><span data-stu-id="c4cd9-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="c4cd9-120">更新常见策略以包括团队</span><span class="sxs-lookup"><span data-stu-id="c4cd9-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="c4cd9-121">下图说明了用于保护团队中的聊天、组和内容的建议策略集。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-121">The following diagram illustrates the set of recommended policies for protecting chat, groups and content in Teams.</span></span> <span data-ttu-id="c4cd9-122">铅笔图标指示需要重设的策略，以确保在分配云应用程序中包含团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-122">The pencil icon indicates which policies need to be revisited to be sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

![演示如何在各种设备上使用 Microsoft 团队的图表。](../images/identity-access-ruleset-teams.png)

<span data-ttu-id="c4cd9-124">以下是要在团队的云应用程序分配中包括的相关服务：</span><span class="sxs-lookup"><span data-stu-id="c4cd9-124">These are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="c4cd9-125">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4cd9-125">Microsoft Teams</span></span>
- <span data-ttu-id="c4cd9-126">SharePoint Online 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="c4cd9-126">SharePoint Online and OneDrive for Business</span></span>
- <span data-ttu-id="c4cd9-127">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c4cd9-127">Exchange Online</span></span>
- <span data-ttu-id="c4cd9-128">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c4cd9-128">Skype for Business Online</span></span>
- <span data-ttu-id="c4cd9-129">Microsoft Stream （会议录制）</span><span class="sxs-lookup"><span data-stu-id="c4cd9-129">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="c4cd9-130">Microsoft Planner （Planner 任务和规划数据）</span><span class="sxs-lookup"><span data-stu-id="c4cd9-130">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="c4cd9-131">此表列出了需要对其进行访问的策略，并链接到[常见标识和设备访问策略](identity-access-policies.md)中的每个策略，这些策略为所有 Office 应用程序提供了更宽的规则集。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-131">This table lists the policies that need to be revisited and links to each policy in [Common identity and device access policies](identity-access-policies.md), which has the wider rule-set for all Office applications.</span></span>

|<span data-ttu-id="c4cd9-132">保护级别</span><span class="sxs-lookup"><span data-stu-id="c4cd9-132">Protection level</span></span>|<span data-ttu-id="c4cd9-133">策略</span><span class="sxs-lookup"><span data-stu-id="c4cd9-133">Policies</span></span>|<span data-ttu-id="c4cd9-134">有关团队实施的详细信息</span><span class="sxs-lookup"><span data-stu-id="c4cd9-134">Further information for Teams implementation</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="c4cd9-135">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="c4cd9-135">**Baseline**</span></span>|[<span data-ttu-id="c4cd9-136">当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="c4cd9-136">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="c4cd9-137">确保团队和相关服务包含在应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-137">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="c4cd9-138">团队还提供了来宾访问和外部访问规则，您将在本文后面的部分中了解有关这些规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-138">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span>|
|        |[<span data-ttu-id="c4cd9-139">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="c4cd9-139">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="c4cd9-140">在云应用的分配中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-140">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
|        |[<span data-ttu-id="c4cd9-141">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="c4cd9-141">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="c4cd9-142">强制团队用户在登录时更改其密码（如果为其帐户检测到高风险活动）。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-142">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="c4cd9-143">确保团队和相关服务包含在应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-143">Be sure Teams and dependent services are included in the list of apps.</span></span>|
|        |[<span data-ttu-id="c4cd9-144">定义应用保护策略</span><span class="sxs-lookup"><span data-stu-id="c4cd9-144">Define app protection policies</span></span>](identity-access-policies.md#define-app-protection-policies)|<span data-ttu-id="c4cd9-145">确保团队和相关服务包含在应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-145">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="c4cd9-146">更新每个平台（iOS、Android、Windows）的策略。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-146">Update the policy for each platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="c4cd9-147">需要批准的应用程序</span><span class="sxs-lookup"><span data-stu-id="c4cd9-147">Require approved apps</span></span>](identity-access-policies.md#require-approved-apps)|<span data-ttu-id="c4cd9-148">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-148">Include Teams and dependent services in this policy.</span></span>|
|        |[<span data-ttu-id="c4cd9-149">定义设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="c4cd9-149">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="c4cd9-150">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-150">Include Teams and dependent services in this policy.</span></span>|
|        |[<span data-ttu-id="c4cd9-151">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="c4cd9-151">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="c4cd9-152">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-152">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="c4cd9-153">**敏感**</span><span class="sxs-lookup"><span data-stu-id="c4cd9-153">**Sensitive**</span></span>|[<span data-ttu-id="c4cd9-154">当登录风险为*低*、*中*或*高*时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="c4cd9-154">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="c4cd9-155">团队还提供了来宾访问和外部访问规则，您将在本文后面的部分中了解有关这些规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-155">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span> <span data-ttu-id="c4cd9-156">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-156">Include Teams and dependent services in this policy.</span></span>|
|         |[<span data-ttu-id="c4cd9-157">需要符合要求*的 pc 和*移动设备</span><span class="sxs-lookup"><span data-stu-id="c4cd9-157">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="c4cd9-158">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-158">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="c4cd9-159">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="c4cd9-159">**Highly regulated**</span></span>|[<span data-ttu-id="c4cd9-160">*始终*要求进行 MFA</span><span class="sxs-lookup"><span data-stu-id="c4cd9-160">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="c4cd9-161">无论用户标识如何，你的组织都将使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-161">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="c4cd9-162">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-162">Include Teams and dependent services in this policy.</span></span>
| | |

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="c4cd9-163">团队相关服务体系结构</span><span class="sxs-lookup"><span data-stu-id="c4cd9-163">Teams dependent services architecture</span></span>

<span data-ttu-id="c4cd9-164">为了供参考，下图演示了服务团队所依赖的。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-164">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="c4cd9-165">有关详细信息和其他说明，请参阅 microsoft[团队和 microsoft 365 中相关的工作效率服务（针对 IT 架构师](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects)）。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-165">For more information and additional illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects).</span></span>

![该图显示了 SharePoint Online、OneDrive for Business 和 Exchange 上的团队相关性。](../images/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a><span data-ttu-id="c4cd9-167">为团队启用来宾和外部访问</span><span class="sxs-lookup"><span data-stu-id="c4cd9-167">Enabling guest and external access for Teams</span></span>

<span data-ttu-id="c4cd9-168">在 Azure AD 中，来宾和外部用户是相同的。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-168">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="c4cd9-169">这两个用户的用户类型为 "来宾"。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-169">The user type for both of these is Guest.</span></span> <span data-ttu-id="c4cd9-170">来宾用户是 B2B 用户。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-170">Guest users are B2B users.</span></span> <span data-ttu-id="c4cd9-171">Microsoft 团队在应用程序中区分来宾用户和外部用户。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-171">Microsoft Teams differentiates between guest users and external users in the app.</span></span> <span data-ttu-id="c4cd9-172">虽然了解每个用户在团队中的处理方式非常重要，但这两种类型的用户在 Azure AD 中都是 B2B 用户，而 B2B 用户的建议策略适用于这两种用户。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-172">While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.</span></span> <span data-ttu-id="c4cd9-173">有关允许来宾访问的推荐策略，请参阅[允许来宾和外部 B2B 访问的策略](identity-access-policies-guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-173">For recommended policies to allow guest access, see [Policies for allowing guest and external B2B access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="c4cd9-174">团队中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="c4cd9-174">Guest Access in Teams</span></span>

<span data-ttu-id="c4cd9-175">除了企业或组织内部的用户的策略外，管理员还可以允许来宾访问允许在用户的用户的基础上为您的企业或组织外部的人员访问团队资源并与之交互内部人员，如组对话、聊天和会议等。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-175">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span> <span data-ttu-id="c4cd9-176">您可以通过以下链接了解有关来宾访问的详细信息：[团队来宾访问](https://docs.microsoft.com/microsoftteams/guest-access)</span><span class="sxs-lookup"><span data-stu-id="c4cd9-176">You can learn more about Guest Access at the following link: [Teams guest access](https://docs.microsoft.com/microsoftteams/guest-access)</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="c4cd9-177">团队中的外部访问</span><span class="sxs-lookup"><span data-stu-id="c4cd9-177">External Access in Teams</span></span>

<span data-ttu-id="c4cd9-178">外部访问有时会与来宾访问相混淆，因此请务必清楚，这两种非内部访问机制的实际差别很大。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-178">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are actually quite different.</span></span> <span data-ttu-id="c4cd9-179">虽然来宾访问是针对每个用户进行的（一次添加一个用户），当管理员启用外部访问时，您可以同时将外部域的所有用户添加到团队中。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-179">While guest access occurs on a per-user basis (you add one user at a time), when an administrator enables external access it allows you to add all the users of an external domain at the same time to Teams.</span></span> <span data-ttu-id="c4cd9-180">但是，这些外部用户的访问和功能比通过来宾访问添加的个人更少。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-180">However those external users have less access and functionality than an individual who's been added via guest access would have.</span></span> <span data-ttu-id="c4cd9-181">外部访问用户可以通过团队与您的内部用户聊天。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-181">External access users can chat with your internal users via Teams.</span></span>

<span data-ttu-id="c4cd9-182">有关外部访问的详细信息以及如何根据需要实现它，请参阅[管理 Microsoft 团队中的外部访问](https://docs.microsoft.com/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="c4cd9-182">For more reading about external access, and how to implement it if you need to, please review [Manage external access in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access)</span></span>

## <a name="teams-policies"></a><span data-ttu-id="c4cd9-183">团队策略</span><span class="sxs-lookup"><span data-stu-id="c4cd9-183">Teams Policies</span></span>

<span data-ttu-id="c4cd9-184">在上面列出的常见策略之外，有一些团队特定的策略可以和应配置为管理各种团队功能。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-184">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="c4cd9-185">团队和频道策略</span><span class="sxs-lookup"><span data-stu-id="c4cd9-185">Teams and Channels Policies</span></span>

<span data-ttu-id="c4cd9-186">团队和频道是 Microsoft 团队中的两个常用元素，有一些策略可用于控制用户在使用团队和频道时可以执行和不能执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-186">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="c4cd9-187">虽然您可以创建一个全局团队，但如果您的组织具有5000用户或更低的用户，那么您很可能会发现，具有更小的团队和渠道来实现特定目的，从而满足您的组织需求。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-187">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="c4cd9-188">建议您更改默认策略或创建自定义策略，您可以通过以下链接了解有关管理策略的详细信息：[管理 Microsoft 团队中的团队策略](https://docs.microsoft.com/microsoftteams/teams-policies)。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-188">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="c4cd9-189">邮件策略</span><span class="sxs-lookup"><span data-stu-id="c4cd9-189">Messaging Policies</span></span>

<span data-ttu-id="c4cd9-190">消息传递或聊天也可以通过默认全局策略或通过自定义策略进行管理，这可以帮助您的用户以适合您组织的方式与其他人进行通信。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-190">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="c4cd9-191">可以在[团队中管理邮件策略](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)时查看此信息。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-191">This information can be reviewed at [Managing messaging policies in Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="c4cd9-192">会议策略</span><span class="sxs-lookup"><span data-stu-id="c4cd9-192">Meeting Policies</span></span>

<span data-ttu-id="c4cd9-193">无需在团队会议周围规划和实施策略，即可完成团队的讨论。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-193">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="c4cd9-194">会议是团队的基本组件，使用户可以一次正式地开会并演示给多个用户，以及共享与会议相关的内容。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-194">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, as well as share content relevant to the meeting.</span></span> <span data-ttu-id="c4cd9-195">在会议周围为组织设置适当的策略是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-195">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="c4cd9-196">有关详细信息，请参阅[管理团队中的会议策略](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-196">Please review [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) for more information.</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="c4cd9-197">应用权限策略</span><span class="sxs-lookup"><span data-stu-id="c4cd9-197">App Permission Policies</span></span>

<span data-ttu-id="c4cd9-198">团队还允许您在不同位置使用应用程序，例如频道或个人聊天。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-198">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="c4cd9-199">围绕可添加和使用哪些应用程序以及在何处维护内容丰富的环境（也是安全的）有必要的策略。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-199">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="c4cd9-200">有关应用程序权限策略的详细信息，请参阅[管理 Microsoft 团队中的应用程序权限策略](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)。</span><span class="sxs-lookup"><span data-stu-id="c4cd9-200">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c4cd9-201">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c4cd9-201">Next steps</span></span>

[<span data-ttu-id="c4cd9-202">了解如何为 Exchange Online 启用条件访问</span><span class="sxs-lookup"><span data-stu-id="c4cd9-202">Learn how to enable conditional access for Exchange Online</span></span>](secure-email-recommended-policies.md)


