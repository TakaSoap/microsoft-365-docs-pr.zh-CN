---
title: 推荐的团队策略-适用于企业的 Microsoft 365 |Microsoft 文档
description: 介绍有关如何保护团队通信和文件访问的 Microsoft 建议的策略。
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/18/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 570ef098a3989bf42d641b78e325414350b8e5a5
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132108"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="57318-103">保护团队聊天、组和文件的策略建议</span><span class="sxs-lookup"><span data-stu-id="57318-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="57318-104">本文介绍如何实现建议的标识和设备访问策略，以保护 Microsoft 团队聊天、组和内容（如文件和日历）。</span><span class="sxs-lookup"><span data-stu-id="57318-104">This article describes how to implement the recommended identity and device-access policies to protect Microsoft Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="57318-105">本指南基于 [通用标识和设备访问策略](identity-access-policies.md)构建，其中包含特定于团队的其他信息。</span><span class="sxs-lookup"><span data-stu-id="57318-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="57318-106">由于团队与我们的其他产品集成，因此请参阅 [保护 SharePoint 网站和文件](sharepoint-file-access-policies.md) 以及 [保护电子邮件的策略建议](secure-email-recommended-policies.md)的策略建议。</span><span class="sxs-lookup"><span data-stu-id="57318-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="57318-107">这些建议基于三种不同的安全层级保护和针对团队的保护，这些团队可根据您需求的粒度进行应用：比较基准、敏感和高度管控。</span><span class="sxs-lookup"><span data-stu-id="57318-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="57318-108">您可以在 [标识和设备访问配置](microsoft-365-policies-configurations.md)中了解有关这些安全层以及这些建议所引用的建议策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="57318-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="57318-109">本文中包含特定于团队部署的其他建议，以涵盖特定身份验证环境，包括组织外部的用户。</span><span class="sxs-lookup"><span data-stu-id="57318-109">Additional recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="57318-110">您需要遵循本指南，以获得完整的安全体验。</span><span class="sxs-lookup"><span data-stu-id="57318-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="57318-111">其他相关服务之前的团队入门</span><span class="sxs-lookup"><span data-stu-id="57318-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="57318-112">您无需启用相关服务即可开始使用 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="57318-112">You don't need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="57318-113">这些都是 "只是工作"。</span><span class="sxs-lookup"><span data-stu-id="57318-113">These will all "just work."</span></span> <span data-ttu-id="57318-114">但是，您确实需要准备好管理以下内容：</span><span class="sxs-lookup"><span data-stu-id="57318-114">However, you do need to be prepared to manage the following:</span></span>

- <span data-ttu-id="57318-115">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="57318-115">Microsoft 365 groups</span></span>
- <span data-ttu-id="57318-116">SharePoint 团队网站</span><span class="sxs-lookup"><span data-stu-id="57318-116">SharePoint team sites</span></span>
- <span data-ttu-id="57318-117">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="57318-117">OneDrive for Business</span></span>
- <span data-ttu-id="57318-118">Exchange 邮箱</span><span class="sxs-lookup"><span data-stu-id="57318-118">Exchange mailboxes</span></span>
- <span data-ttu-id="57318-119">如果启用这些服务，则 Stream 视频和 Planner 计划 () </span><span class="sxs-lookup"><span data-stu-id="57318-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="57318-120">更新常见策略以包括团队</span><span class="sxs-lookup"><span data-stu-id="57318-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="57318-121">若要保护团队中的聊天、组和内容，下图说明了要从公共标识和设备访问策略中更新的策略。</span><span class="sxs-lookup"><span data-stu-id="57318-121">To protect chat, groups and content in Teams, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span> <span data-ttu-id="57318-122">对于要更新的每个策略，请确保在云应用的分配中包含团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="57318-122">For each policy to update, make sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

<span data-ttu-id="57318-123">[![用于保护对团队及其依赖服务的访问权限的策略更新的摘要](../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span><span class="sxs-lookup"><span data-stu-id="57318-123">[![Summary of policy updates for protecting access to Teams and its dependent services](../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span></span>

[<span data-ttu-id="57318-124">查看此图像的更大版本</span><span class="sxs-lookup"><span data-stu-id="57318-124">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

<span data-ttu-id="57318-125">以下是要在团队的云应用程序分配中包括的相关服务：</span><span class="sxs-lookup"><span data-stu-id="57318-125">These are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="57318-126">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57318-126">Microsoft Teams</span></span>
- <span data-ttu-id="57318-127">Sharepoint 和 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="57318-127">SharePoint and OneDrive for Business</span></span>
- <span data-ttu-id="57318-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="57318-128">Exchange Online</span></span>
- <span data-ttu-id="57318-129">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="57318-129">Skype for Business Online</span></span>
- <span data-ttu-id="57318-130">Microsoft Stream (会议录制) </span><span class="sxs-lookup"><span data-stu-id="57318-130">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="57318-131">Microsoft Planner (Planner 任务和规划数据) </span><span class="sxs-lookup"><span data-stu-id="57318-131">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="57318-132">此表列出了需要对其进行访问的策略，以及在 [常见标识和设备访问策略](identity-access-policies.md)中的每个策略的链接，这些策略为所有 Office 应用程序设置了更宽的策略。</span><span class="sxs-lookup"><span data-stu-id="57318-132">This table lists the policies that need to be revisited and links to each policy in the [common identity and device access policies](identity-access-policies.md), which has the wider policy set for all Office applications.</span></span>

|<span data-ttu-id="57318-133">保护级别</span><span class="sxs-lookup"><span data-stu-id="57318-133">Protection level</span></span>|<span data-ttu-id="57318-134">策略</span><span class="sxs-lookup"><span data-stu-id="57318-134">Policies</span></span>|<span data-ttu-id="57318-135">有关团队实施的详细信息</span><span class="sxs-lookup"><span data-stu-id="57318-135">Further information for Teams implementation</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="57318-136">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="57318-136">**Baseline**</span></span>|[<span data-ttu-id="57318-137">当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="57318-137">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="57318-138">确保团队和相关服务包含在应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="57318-138">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="57318-139">团队还提供了来宾访问和外部访问规则，您将在本文后面的部分中了解有关这些规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="57318-139">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span>|
|        |[<span data-ttu-id="57318-140">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="57318-140">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="57318-141">在云应用的分配中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="57318-141">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
|        |[<span data-ttu-id="57318-142">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="57318-142">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="57318-143">强制团队用户在登录时更改其密码（如果为其帐户检测到高风险活动）。</span><span class="sxs-lookup"><span data-stu-id="57318-143">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="57318-144">确保团队和相关服务包含在应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="57318-144">Be sure Teams and dependent services are included in the list of apps.</span></span>|
|        |[<span data-ttu-id="57318-145">应用应用数据保护策略</span><span class="sxs-lookup"><span data-stu-id="57318-145">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="57318-146">确保团队和相关服务包含在应用程序列表中。</span><span class="sxs-lookup"><span data-stu-id="57318-146">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="57318-147">为每个平台 (iOS、Android、Windows) 更新策略。</span><span class="sxs-lookup"><span data-stu-id="57318-147">Update the policy for each platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="57318-148">需要经批准的应用和应用保护</span><span class="sxs-lookup"><span data-stu-id="57318-148">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="57318-149">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="57318-149">Include Teams and dependent services in this policy.</span></span>|
|        |[<span data-ttu-id="57318-150">定义设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="57318-150">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="57318-151">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="57318-151">Include Teams and dependent services in this policy.</span></span>|
|        |[<span data-ttu-id="57318-152">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="57318-152">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="57318-153">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="57318-153">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="57318-154">**敏感**</span><span class="sxs-lookup"><span data-stu-id="57318-154">**Sensitive**</span></span>|[<span data-ttu-id="57318-155">当登录风险为*低*、*中*或*高*时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="57318-155">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="57318-156">团队还提供了来宾访问和外部访问规则，您将在本文后面的部分中了解有关这些规则的详细信息。</span><span class="sxs-lookup"><span data-stu-id="57318-156">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span> <span data-ttu-id="57318-157">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="57318-157">Include Teams and dependent services in this policy.</span></span>|
|         |[<span data-ttu-id="57318-158">需要符合要求 *的 pc 和* 移动设备</span><span class="sxs-lookup"><span data-stu-id="57318-158">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="57318-159">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="57318-159">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="57318-160">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="57318-160">**Highly regulated**</span></span>|[<span data-ttu-id="57318-161">*始终* 要求进行 MFA</span><span class="sxs-lookup"><span data-stu-id="57318-161">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="57318-162">无论用户标识如何，你的组织都将使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="57318-162">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="57318-163">在此策略中包括团队和相关服务。</span><span class="sxs-lookup"><span data-stu-id="57318-163">Include Teams and dependent services in this policy.</span></span> |
| | |

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="57318-164">团队相关服务体系结构</span><span class="sxs-lookup"><span data-stu-id="57318-164">Teams dependent services architecture</span></span>

<span data-ttu-id="57318-165">为了供参考，下图演示了服务团队所依赖的。</span><span class="sxs-lookup"><span data-stu-id="57318-165">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="57318-166">有关详细信息和其他说明，请参阅 microsoft [团队和 microsoft 365 中相关的工作效率服务（针对 IT 架构师](../solutions/productivity-illustrations.md)）。</span><span class="sxs-lookup"><span data-stu-id="57318-166">For more information and additional illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../solutions/productivity-illustrations.md).</span></span>

<span data-ttu-id="57318-167">[![显示 SharePoint、OneDrive for Business 和 Exchange 上的团队相关性的图表](../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span><span class="sxs-lookup"><span data-stu-id="57318-167">[![Diagram showing Teams dependencies on SharePoint, OneDrive for Business, and Exchange](../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span></span>

[<span data-ttu-id="57318-168">查看此图像的更大版本</span><span class="sxs-lookup"><span data-stu-id="57318-168">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a><span data-ttu-id="57318-169">团队的来宾访问和外部访问</span><span class="sxs-lookup"><span data-stu-id="57318-169">Guest and external access for Teams</span></span>

<span data-ttu-id="57318-170">Microsoft 团队定义了以下内容：</span><span class="sxs-lookup"><span data-stu-id="57318-170">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="57318-171">**来宾访问** 使用可作为团队成员添加的来宾或外部用户的 AZURE AD B2B 帐户，并拥有对团队的通信和资源的所有具有独特权限访问权限。</span><span class="sxs-lookup"><span data-stu-id="57318-171">**Guest access** uses an Azure AD B2B account for a guest or external user that can be added as a member of a team and have all permissioned access to the communication and resources of the team.</span></span>

- <span data-ttu-id="57318-172">**外部访问** 适用于没有 AZURE AD B2B 帐户的外部用户。</span><span class="sxs-lookup"><span data-stu-id="57318-172">**External access** is for an external user that does not have an Azure AD B2B account.</span></span> <span data-ttu-id="57318-173">外部访问可以包括邀请和参与呼叫、聊天和会议，但不包括团队成员资格和对团队资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="57318-173">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="57318-174">条件访问策略仅适用于团队中的来宾访问，因为存在相应的 Azure AD B2B 帐户。</span><span class="sxs-lookup"><span data-stu-id="57318-174">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both. 

--> 

<span data-ttu-id="57318-175">有关使用 Azure AD B2B 帐户为来宾和外部用户授予访问权限的建议策略，请参阅 [允许来宾和外部 B2B 帐户访问的策略](identity-access-policies-guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="57318-175">For recommended policies to allow access for guest and external users with an Azure AD B2B account, see [Policies for allowing guest and external B2B account access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="57318-176">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="57318-176">Guest access in Teams</span></span>

<span data-ttu-id="57318-177">除了企业或组织内部用户的策略之外，管理员还可以启用来宾访问以允许在用户的用户的基础上访问团队资源并与内部人员进行交互（如组对话、聊天和会议），从而获得人员。</span><span class="sxs-lookup"><span data-stu-id="57318-177">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span> 

<span data-ttu-id="57318-178">有关来宾访问和如何实施来宾的详细信息，请参阅  [团队来宾访问](https://docs.microsoft.com/microsoftteams/guest-access)。</span><span class="sxs-lookup"><span data-stu-id="57318-178">For more information about guest access and how to implement it, see  [Teams guest access](https://docs.microsoft.com/microsoftteams/guest-access).</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="57318-179">团队中的外部访问</span><span class="sxs-lookup"><span data-stu-id="57318-179">External access in Teams</span></span>

<span data-ttu-id="57318-180">外部访问有时会与来宾访问相混淆，因此请务必清楚，这两种非内部访问机制的实际差别很大。</span><span class="sxs-lookup"><span data-stu-id="57318-180">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are actually quite different.</span></span> 

<span data-ttu-id="57318-181">通过外部访问，团队用户可以从整个外部域中查找、呼叫、聊天和设置与团队用户的会议。</span><span class="sxs-lookup"><span data-stu-id="57318-181">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with your users in Teams.</span></span> <span data-ttu-id="57318-182">团队管理员在组织级别配置外部访问。</span><span class="sxs-lookup"><span data-stu-id="57318-182">Teams administrators configure external access at the organization level.</span></span> <span data-ttu-id="57318-183">有关详细信息，请参阅 [在 Microsoft 团队中管理外部访问](https://docs.microsoft.com/microsoftteams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="57318-183">For more information, see [Manage external access in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access).</span></span>

<span data-ttu-id="57318-184">外部访问用户的访问权限和功能比通过来宾访问添加的个人更少。</span><span class="sxs-lookup"><span data-stu-id="57318-184">External access users have less access and functionality than an individual who's been added via guest access.</span></span> <span data-ttu-id="57318-185">例如，外部访问用户可以与具有团队的内部用户聊天，但无法访问团队频道、文件或其他资源。</span><span class="sxs-lookup"><span data-stu-id="57318-185">For example, external access users can chat with your internal users with Teams but cannot access team channels, files, or other resources.</span></span>

<span data-ttu-id="57318-186">外部访问不使用 Azure AD B2B 用户帐户，因此不使用条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="57318-186">External access does not use Azure AD B2B user accounts and therefore does not use Conditional Access policies.</span></span> 

## <a name="teams-policies"></a><span data-ttu-id="57318-187">团队策略</span><span class="sxs-lookup"><span data-stu-id="57318-187">Teams policies</span></span>

<span data-ttu-id="57318-188">在上面列出的常见策略之外，有一些团队特定的策略可以和应配置为管理各种团队功能。</span><span class="sxs-lookup"><span data-stu-id="57318-188">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="57318-189">团队和频道策略</span><span class="sxs-lookup"><span data-stu-id="57318-189">Teams and channels policies</span></span>

<span data-ttu-id="57318-190">团队和频道是 Microsoft 团队中的两个常用元素，有一些策略可用于控制用户在使用团队和频道时可以执行和不能执行的操作。</span><span class="sxs-lookup"><span data-stu-id="57318-190">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="57318-191">虽然您可以创建一个全局团队，但如果您的组织具有5000用户或更低的用户，那么您很可能会发现，具有更小的团队和渠道来实现特定目的，从而满足您的组织需求。</span><span class="sxs-lookup"><span data-stu-id="57318-191">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="57318-192">建议您更改默认策略或创建自定义策略，您可以通过以下链接了解有关管理策略的详细信息： [管理 Microsoft 团队中的团队策略](https://docs.microsoft.com/microsoftteams/teams-policies)。</span><span class="sxs-lookup"><span data-stu-id="57318-192">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="57318-193">邮件策略</span><span class="sxs-lookup"><span data-stu-id="57318-193">Messaging policies</span></span>

<span data-ttu-id="57318-194">消息传递或聊天也可以通过默认全局策略或通过自定义策略进行管理，这可以帮助您的用户以适合您组织的方式与其他人进行通信。</span><span class="sxs-lookup"><span data-stu-id="57318-194">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="57318-195">可以在 [团队中管理邮件策略](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)时查看此信息。</span><span class="sxs-lookup"><span data-stu-id="57318-195">This information can be reviewed at [Managing messaging policies in Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="57318-196">会议策略</span><span class="sxs-lookup"><span data-stu-id="57318-196">Meeting policies</span></span>

<span data-ttu-id="57318-197">无需在团队会议周围规划和实施策略，即可完成团队的讨论。</span><span class="sxs-lookup"><span data-stu-id="57318-197">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="57318-198">会议是团队的基本组件，使用户可以一次正式地开会并演示给多个用户，以及共享与会议相关的内容。</span><span class="sxs-lookup"><span data-stu-id="57318-198">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, as well as share content relevant to the meeting.</span></span> <span data-ttu-id="57318-199">在会议周围为组织设置适当的策略是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="57318-199">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="57318-200">有关详细信息，请参阅 [管理团队中的会议策略](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) 。</span><span class="sxs-lookup"><span data-stu-id="57318-200">Please review [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) for more information.</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="57318-201">应用权限策略</span><span class="sxs-lookup"><span data-stu-id="57318-201">App permission policies</span></span>

<span data-ttu-id="57318-202">团队还允许您在不同位置使用应用程序，例如频道或个人聊天。</span><span class="sxs-lookup"><span data-stu-id="57318-202">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="57318-203">围绕可添加和使用哪些应用程序以及在何处维护内容丰富的环境（也是安全的）有必要的策略。</span><span class="sxs-lookup"><span data-stu-id="57318-203">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="57318-204">有关应用程序权限策略的详细信息，请参阅 [管理 Microsoft 团队中的应用程序权限策略](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)。</span><span class="sxs-lookup"><span data-stu-id="57318-204">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="57318-205">后续步骤</span><span class="sxs-lookup"><span data-stu-id="57318-205">Next steps</span></span>

![步骤4： Microsoft 365 云应用的策略](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="57318-207">为以下项配置条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="57318-207">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="57318-208">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="57318-208">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="57318-209">SharePoint</span><span class="sxs-lookup"><span data-stu-id="57318-209">SharePoint</span></span>](secure-email-recommended-policies.md)

