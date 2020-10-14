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
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 4a0eb530df2709294bf1c9aa0cf285e59c9fd1f8
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464200"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="7188f-103">允许来宾和外部 B2B 访问的策略</span><span class="sxs-lookup"><span data-stu-id="7188f-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="7188f-104">本文介绍如何调整建议的公共标识和设备访问策略，以允许来宾和具有 Azure Active Directory (Azure AD) 企业到企业 (B2B) 帐户的外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="7188f-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="7188f-105">本指南建立在 [通用标识和设备访问策略](identity-access-policies.md)之上。</span><span class="sxs-lookup"><span data-stu-id="7188f-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="7188f-106">这些建议旨在适用于保护的 **基准** 层。</span><span class="sxs-lookup"><span data-stu-id="7188f-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="7188f-107">不过，您还可以根据您对 **敏感** 和 **高度管控** 保护的需求的粒度来调整建议。</span><span class="sxs-lookup"><span data-stu-id="7188f-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="7188f-108">为 B2B 帐户提供用于对 Azure AD 租户进行身份验证的路径不会为这些帐户授予对你的整个环境的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7188f-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="7188f-109">B2B 用户及其帐户只能访问与他们共享的资源 (如在条件访问策略中授予的服务中) 的文件。</span><span class="sxs-lookup"><span data-stu-id="7188f-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="7188f-110">更新常见策略以允许和保护来宾和外部访问</span><span class="sxs-lookup"><span data-stu-id="7188f-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="7188f-111">若要使用 Azure AD B2B 帐户保护来宾和外部访问，下图说明了要从通用标识和设备访问策略中添加或更新的策略。</span><span class="sxs-lookup"><span data-stu-id="7188f-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span> 

<span data-ttu-id="7188f-112">[![保护来宾访问的策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="7188f-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="7188f-113">查看此图像的更大版本</span><span class="sxs-lookup"><span data-stu-id="7188f-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="7188f-114">下表列出了您需要创建和更新的策略。</span><span class="sxs-lookup"><span data-stu-id="7188f-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="7188f-115">常见策略链接到 [常见标识和设备访问策略](identity-access-policies.md) 文章中相关的配置说明。</span><span class="sxs-lookup"><span data-stu-id="7188f-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="7188f-116">保护级别</span><span class="sxs-lookup"><span data-stu-id="7188f-116">Protection level</span></span>|<span data-ttu-id="7188f-117">策略</span><span class="sxs-lookup"><span data-stu-id="7188f-117">Policies</span></span>|<span data-ttu-id="7188f-118">更多信息</span><span class="sxs-lookup"><span data-stu-id="7188f-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="7188f-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="7188f-119">**Baseline**</span></span>|[<span data-ttu-id="7188f-120">要求为来宾和外部用户始终进行 MFA</span><span class="sxs-lookup"><span data-stu-id="7188f-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7188f-121">创建此新策略并配置：</span><span class="sxs-lookup"><span data-stu-id="7188f-121">Create this new policy and configure:</span></span> <ul><li> <span data-ttu-id="7188f-122">对于 **> 包括的用户和组 > 的工作分配**，请选择 " **选择用户和组**"，然后选择 " **所有来宾和外部用户**"。</span><span class="sxs-lookup"><span data-stu-id="7188f-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span> </li><li> <span data-ttu-id="7188f-123">对于 **工作分配 > 条件 > 登录**，请将所有选项保留为选中状态，以始终强制实施多重身份验证 (MFA) 。</span><span class="sxs-lookup"><span data-stu-id="7188f-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li>|
|        |[<span data-ttu-id="7188f-124">当登录风险为 "*中*" 或 "*高*" 时，需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="7188f-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7188f-125">修改此策略以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="7188f-125">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="7188f-126">需要兼容电脑</span><span class="sxs-lookup"><span data-stu-id="7188f-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="7188f-127">修改此策略以排除来宾和外部用户。</span><span class="sxs-lookup"><span data-stu-id="7188f-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="7188f-128">若要在条件访问策略中包括或排除来宾和外部用户，对于 > 包含或**排除**的**用户和组 > 的工作分配**，请检查**所有来宾和外部用户**。</span><span class="sxs-lookup"><span data-stu-id="7188f-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![用于排除来宾和外部用户的控件的屏幕捕获](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="7188f-130">更多信息</span><span class="sxs-lookup"><span data-stu-id="7188f-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="7188f-131">Microsoft 团队的来宾和外部访问</span><span class="sxs-lookup"><span data-stu-id="7188f-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="7188f-132">Microsoft 团队定义了以下内容：</span><span class="sxs-lookup"><span data-stu-id="7188f-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="7188f-133">**来宾访问** 使用可添加为团队成员的 AZURE AD B2B 帐户，并拥有对团队的通信和资源的所有具有独特权限访问权限。</span><span class="sxs-lookup"><span data-stu-id="7188f-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="7188f-134">**外部访问** 适用于没有 B2B 帐户的外部用户。</span><span class="sxs-lookup"><span data-stu-id="7188f-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="7188f-135">外部访问可以包括邀请和参与呼叫、聊天和会议，但不包括团队成员资格和对团队资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7188f-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="7188f-136">有关详细信息，请参阅 [针对团队的来宾和外部访问之间的比较](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="7188f-136">For more information, see the [comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="7188f-137">条件访问策略仅适用于团队中的来宾访问，因为存在相应的 Azure AD B2B 帐户。</span><span class="sxs-lookup"><span data-stu-id="7188f-137">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<span data-ttu-id="7188f-138">有关保护团队的标识和设备访问策略的详细信息，请参阅 [保护团队聊天、组和文件的策略建议](teams-access-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="7188f-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="7188f-139">要求为来宾和外部用户始终进行 MFA</span><span class="sxs-lookup"><span data-stu-id="7188f-139">Require MFA always for guest and external users</span></span>
<span data-ttu-id="7188f-140">此策略将提示来宾在你的租户中注册 MFA，而不考虑是否在其家乡租户中向 MFA 注册了这些。</span><span class="sxs-lookup"><span data-stu-id="7188f-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="7188f-141">在访问租户中的资源时，来宾和外部用户需要对每个请求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="7188f-141">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="7188f-142">从基于风险的 MFA 中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="7188f-142">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="7188f-143">虽然组织可以使用 Azure AD 标识保护为 B2B 用户强制实施基于风险的策略，但由于在其主目录中存在其标识，对资源目录中的 B2B 协作用户实施 Azure AD 标识保护有一些限制。</span><span class="sxs-lookup"><span data-stu-id="7188f-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="7188f-144">由于这些限制，Microsoft 建议您将来宾用户从基于风险的 MFA 策略中排除，并要求这些用户始终使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="7188f-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="7188f-145">有关详细信息，请参阅 [针对 B2B 协作用户的标识保护的限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="7188f-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="7188f-146">从设备管理中排除来宾和外部用户</span><span class="sxs-lookup"><span data-stu-id="7188f-146">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="7188f-147">只有一个组织可以管理一个设备。</span><span class="sxs-lookup"><span data-stu-id="7188f-147">Only one organization can manage a device.</span></span> <span data-ttu-id="7188f-148">如果不从需要设备符合性的策略中排除来宾和外部用户，则这些策略将阻止这些用户。</span><span class="sxs-lookup"><span data-stu-id="7188f-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="7188f-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7188f-149">Next step</span></span>

![步骤4： Microsoft 365 云应用的策略](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="7188f-151">为以下项配置条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="7188f-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="7188f-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7188f-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="7188f-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7188f-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="7188f-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7188f-154">SharePoint</span></span>](sharepoint-file-access-policies.md)

