---
title: 常见标识和设备访问策略-Microsoft 365 企业版 |Microsoft 文档
description: 介绍针对有关如何应用标识和设备访问策略以及配置的 Microsoft 建议的策略。
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 322da1ccfbd0cf8b5070894580b06fb5b0283f40
ms.sourcegitcommit: 1d5fc181036b673c4f0b9e161e19395dbfe5a304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2019
ms.locfileid: "35411646"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="a74f6-103">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="a74f6-103">Common identity and device access policies</span></span>
<span data-ttu-id="a74f6-104">本文介绍了用于保护云服务访问的常见建议策略, 其中包括使用 Azure AD 应用程序代理发布的本地应用程序。</span><span class="sxs-lookup"><span data-stu-id="a74f6-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="a74f6-105">本指南讨论如何在新预配的环境中部署建议的策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-105">This guidance discusses how to deploy the recommended policies in a newly-provisioned environment.</span></span> <span data-ttu-id="a74f6-106">在单独的实验室环境中设置这些策略, 可以在将首展转移到预生产和生产环境之前, 了解和评估建议的策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-106">Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your preproduction and production environments.</span></span> <span data-ttu-id="a74f6-107">您的新设置的环境可能是仅云或混合的。</span><span class="sxs-lookup"><span data-stu-id="a74f6-107">Your newly provisioned environment may be cloud-only or hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="a74f6-108">策略集</span><span class="sxs-lookup"><span data-stu-id="a74f6-108">Policy set</span></span> 

<span data-ttu-id="a74f6-109">下图说明了建议的一组策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-109">The following diagram illustrates the recommended set of policies.</span></span> <span data-ttu-id="a74f6-110">它显示了每个策略应用于哪一层的保护, 以及这些策略是应用于 Pc、电话和平板电脑, 还是适用于这两种类别的设备。</span><span class="sxs-lookup"><span data-stu-id="a74f6-110">It shows which tier of protections each policy applies to and whether the policies apply to PCs or phones and tablets, or both categories of devices.</span></span> <span data-ttu-id="a74f6-111">它还指示这些策略的配置位置。</span><span class="sxs-lookup"><span data-stu-id="a74f6-111">It also indicates where these policies are configured.</span></span>

![用于配置标识和设备访问的常见策略](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="a74f6-113">本文的其余部分介绍了如何配置这些策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="a74f6-114">建议在将设备注册到 Intune 中之前使用多重身份验证, 以确保设备已占有目标用户。</span><span class="sxs-lookup"><span data-stu-id="a74f6-114">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> <span data-ttu-id="a74f6-115">在强制实施设备合规性策略之前, 还必须将设备注册到 Intune。</span><span class="sxs-lookup"><span data-stu-id="a74f6-115">You must also enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="a74f6-116">为了让你有时间完成这些任务, 我们建议你按照此表中所列的顺序实施基准策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-116">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table.</span></span> <span data-ttu-id="a74f6-117">但是, 敏感和高度管控保护的 MFA 策略可在任何时候实施。</span><span class="sxs-lookup"><span data-stu-id="a74f6-117">However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="a74f6-118">保护级别</span><span class="sxs-lookup"><span data-stu-id="a74f6-118">Protection level</span></span>|<span data-ttu-id="a74f6-119">策略</span><span class="sxs-lookup"><span data-stu-id="a74f6-119">Policies</span></span>|<span data-ttu-id="a74f6-120">更多信息</span><span class="sxs-lookup"><span data-stu-id="a74f6-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="a74f6-121">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="a74f6-121">**Baseline**</span></span>|[<span data-ttu-id="a74f6-122">当登录风险为 "*中*" 或 "*高*" 时, 需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="a74f6-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="a74f6-123">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="a74f6-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="a74f6-124">不使用新式身份验证的客户端可以绕过条件访问规则, 因此, 请务必阻止这些</span><span class="sxs-lookup"><span data-stu-id="a74f6-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these</span></span>|
|        |[<span data-ttu-id="a74f6-125">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="a74f6-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="a74f6-126">如果为帐户检测到高风险活动, 则强制用户在登录时更改其密码</span><span class="sxs-lookup"><span data-stu-id="a74f6-126">Forces users to change their password when signing in if high-risk activity is detected for their account</span></span>|
|        |[<span data-ttu-id="a74f6-127">定义应用保护策略</span><span class="sxs-lookup"><span data-stu-id="a74f6-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="a74f6-128">每个平台 (iOS、Android、Windows) 一个策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="a74f6-129">需要批准的应用程序</span><span class="sxs-lookup"><span data-stu-id="a74f6-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="a74f6-130">为电话和平板电脑强制实施移动应用保护</span><span class="sxs-lookup"><span data-stu-id="a74f6-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="a74f6-131">定义设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="a74f6-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="a74f6-132">每个平台一个策略</span><span class="sxs-lookup"><span data-stu-id="a74f6-132">One policy for each platform</span></span>|
|        |[<span data-ttu-id="a74f6-133">需要符合要求的电脑</span><span class="sxs-lookup"><span data-stu-id="a74f6-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="a74f6-134">强制对电脑进行 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="a74f6-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="a74f6-135">**敏感**</span><span class="sxs-lookup"><span data-stu-id="a74f6-135">**Sensitive**</span></span>|[<span data-ttu-id="a74f6-136">当登录风险为*低*、*中*或*高*时, 需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="a74f6-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="a74f6-137">需要符合要求*的 pc 和*移动设备</span><span class="sxs-lookup"><span data-stu-id="a74f6-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="a74f6-138">对电脑和电话/平板电脑强制 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="a74f6-138">Enforces Intune management for PCs and phone/tablets</span></span>|
|<span data-ttu-id="a74f6-139">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="a74f6-139">**Highly regulated**</span></span>|[<span data-ttu-id="a74f6-140">*始终*要求进行 MFA</span><span class="sxs-lookup"><span data-stu-id="a74f6-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="a74f6-141">向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="a74f6-141">Assigning policies to users</span></span>
<span data-ttu-id="a74f6-142">在配置策略之前, 请确定您对每个保护层使用的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a74f6-142">Before configuring policies, identify the Azure AD groups you are using for each tier of protection.</span></span> <span data-ttu-id="a74f6-143">通常情况下, 基准保护适用于组织中的每个人。</span><span class="sxs-lookup"><span data-stu-id="a74f6-143">Typically, baseline protection applies to everybody in the organization.</span></span> <span data-ttu-id="a74f6-144">同时包含在基线和敏感保护中的用户将应用所有基准策略加上敏感策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-144">A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies.</span></span> <span data-ttu-id="a74f6-145">保护是累积的, 并且强制实施最严格的策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-145">Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="a74f6-146">建议的做法是为条件访问排除创建 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="a74f6-146">A recommended practice is to create an Azure AD group for conditional access exclusion.</span></span> <span data-ttu-id="a74f6-147">将此组添加到 "Exclude" 下的所有条件访问规则。</span><span class="sxs-lookup"><span data-stu-id="a74f6-147">Add this group to all of your conditional access rules under "Exclude".</span></span> <span data-ttu-id="a74f6-148">这为您提供了在对访问问题进行故障排除时提供对用户的访问权限的方法。</span><span class="sxs-lookup"><span data-stu-id="a74f6-148">This gives you a method to provide access to a user while you troubleshoot access issues.</span></span> <span data-ttu-id="a74f6-149">建议仅将其作为临时解决方案。</span><span class="sxs-lookup"><span data-stu-id="a74f6-149">This is recommended as a temporary solution only.</span></span> <span data-ttu-id="a74f6-150">监视此组的更改, 并确保仅按预期使用排除组。</span><span class="sxs-lookup"><span data-stu-id="a74f6-150">Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="a74f6-151">下图提供了用户分配和排除的示例。</span><span class="sxs-lookup"><span data-stu-id="a74f6-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![用于 MFA 规则的用户分配和排除示例](../images/identity-access-policies-assignment.png)

<span data-ttu-id="a74f6-153">在图中, "Top secret project X team" 分配了一个需要*始终*进行 MFA 的条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-153">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*.</span></span> <span data-ttu-id="a74f6-154">对用户应用更高级别的保护时要合理。</span><span class="sxs-lookup"><span data-stu-id="a74f6-154">Be judicious when applying higher levels of protection to users.</span></span> <span data-ttu-id="a74f6-155">此项目团队的成员将需要在每次登录时提供两种形式的身份验证, 即使他们没有查看高度管控的内容也是如此。</span><span class="sxs-lookup"><span data-stu-id="a74f6-155">Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly-regulated content.</span></span>  

<span data-ttu-id="a74f6-156">作为这些建议的一部分创建的所有 Azure AD 组都必须创建为 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="a74f6-156">All Azure AD groups created as part of these recommendations must be created as Office 365 groups.</span></span> <span data-ttu-id="a74f6-157">在 SharePoint Online 中保护文档时，这一点对于部署 Azure 信息保护 (AIP) 尤为重要。</span><span class="sxs-lookup"><span data-stu-id="a74f6-157">This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![用于创建 Office 365 组的屏幕捕获](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="a74f6-159">需要基于登录风险进行 MFA</span><span class="sxs-lookup"><span data-stu-id="a74f6-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="a74f6-160">在要求进行 MFA 之前, 首先使用标识保护 MFA 注册策略为用户注册 MFA。</span><span class="sxs-lookup"><span data-stu-id="a74f6-160">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA.</span></span> <span data-ttu-id="a74f6-161">注册用户后, 可以强制进行 MFA 以进行登录。</span><span class="sxs-lookup"><span data-stu-id="a74f6-161">After users are registered you can enforce MFA for sign-in.</span></span> <span data-ttu-id="a74f6-162">[先决条件工作](identity-access-prerequisites.md)包括向具有 MFA 的所有用户注册。</span><span class="sxs-lookup"><span data-stu-id="a74f6-162">The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="a74f6-163">创建新的条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="a74f6-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="a74f6-164">转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="a74f6-164">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="a74f6-165">成功登录后, 您将看到 "Azure 仪表板"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-165">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="a74f6-166">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="a74f6-167">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="a74f6-168">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-168">Choose **New policy**.</span></span>

![基线 CA 策略](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="a74f6-170">下表介绍了要为此策略实现的条件访问策略设置。</span><span class="sxs-lookup"><span data-stu-id="a74f6-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="a74f6-171">**作业**</span><span class="sxs-lookup"><span data-stu-id="a74f6-171">**Assignments**</span></span>

|<span data-ttu-id="a74f6-172">类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-172">Type</span></span>|<span data-ttu-id="a74f6-173">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-173">Properties</span></span>|<span data-ttu-id="a74f6-174">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-174">Values</span></span>|<span data-ttu-id="a74f6-175">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a74f6-176">用户和组</span><span class="sxs-lookup"><span data-stu-id="a74f6-176">Users and groups</span></span>|<span data-ttu-id="a74f6-177">包括</span><span class="sxs-lookup"><span data-stu-id="a74f6-177">Include</span></span>|<span data-ttu-id="a74f6-178">选择用户和组 - 选择包含目标用户的特定安全组</span><span class="sxs-lookup"><span data-stu-id="a74f6-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="a74f6-179">从包含试点用户的安全组开始</span><span class="sxs-lookup"><span data-stu-id="a74f6-179">Start with security group including pilot users</span></span>|
||<span data-ttu-id="a74f6-180">排除</span><span class="sxs-lookup"><span data-stu-id="a74f6-180">Exclude</span></span>|<span data-ttu-id="a74f6-181">例外安全组；服务帐户(应用标识)</span><span class="sxs-lookup"><span data-stu-id="a74f6-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="a74f6-182">根据需要在临时基础上修改的成员身份</span><span class="sxs-lookup"><span data-stu-id="a74f6-182">Membership modified on an as-needed temporary basis</span></span>|
|<span data-ttu-id="a74f6-183">云应用</span><span class="sxs-lookup"><span data-stu-id="a74f6-183">Cloud apps</span></span>|<span data-ttu-id="a74f6-184">包括</span><span class="sxs-lookup"><span data-stu-id="a74f6-184">Include</span></span>|<span data-ttu-id="a74f6-185">选择要应用此规则的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a74f6-185">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="a74f6-186">例如, 选择 "Office 365 Exchange Online"</span><span class="sxs-lookup"><span data-stu-id="a74f6-186">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="a74f6-187">条件</span><span class="sxs-lookup"><span data-stu-id="a74f6-187">Conditions</span></span>|<span data-ttu-id="a74f6-188">已配置</span><span class="sxs-lookup"><span data-stu-id="a74f6-188">Configured</span></span>|<span data-ttu-id="a74f6-189">是</span><span class="sxs-lookup"><span data-stu-id="a74f6-189">Yes</span></span>|<span data-ttu-id="a74f6-190">根据自身环境和需求进行配置</span><span class="sxs-lookup"><span data-stu-id="a74f6-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="a74f6-191">登录风险</span><span class="sxs-lookup"><span data-stu-id="a74f6-191">Sign-in risk</span></span>|<span data-ttu-id="a74f6-192">风险级别</span><span class="sxs-lookup"><span data-stu-id="a74f6-192">Risk level</span></span>||<span data-ttu-id="a74f6-193">请参阅下表中的指南</span><span class="sxs-lookup"><span data-stu-id="a74f6-193">See the guidance in the following table</span></span>|

<span data-ttu-id="a74f6-194">**登录风险**</span><span class="sxs-lookup"><span data-stu-id="a74f6-194">**Sign-in risk**</span></span>

<span data-ttu-id="a74f6-195">根据目标的保护级别应用设置。</span><span class="sxs-lookup"><span data-stu-id="a74f6-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="a74f6-196">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-196">Property</span></span>|<span data-ttu-id="a74f6-197">保护级别</span><span class="sxs-lookup"><span data-stu-id="a74f6-197">Level of protection</span></span>|<span data-ttu-id="a74f6-198">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-198">Values</span></span>|<span data-ttu-id="a74f6-199">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a74f6-200">风险级别</span><span class="sxs-lookup"><span data-stu-id="a74f6-200">Risk level</span></span>|<span data-ttu-id="a74f6-201">基线</span><span class="sxs-lookup"><span data-stu-id="a74f6-201">Baseline</span></span>|<span data-ttu-id="a74f6-202">高、中</span><span class="sxs-lookup"><span data-stu-id="a74f6-202">High, medium</span></span>|<span data-ttu-id="a74f6-203">两项全选</span><span class="sxs-lookup"><span data-stu-id="a74f6-203">Check both</span></span>|
| |<span data-ttu-id="a74f6-204">敏感</span><span class="sxs-lookup"><span data-stu-id="a74f6-204">Sensitive</span></span>|<span data-ttu-id="a74f6-205">高、中、低</span><span class="sxs-lookup"><span data-stu-id="a74f6-205">High, medium, low</span></span>|<span data-ttu-id="a74f6-206">三项全选</span><span class="sxs-lookup"><span data-stu-id="a74f6-206">Check all three</span></span>|
| |<span data-ttu-id="a74f6-207">高度管控</span><span class="sxs-lookup"><span data-stu-id="a74f6-207">Highly regulated</span></span>| |<span data-ttu-id="a74f6-208">将所有选项保留为未选中状态以始终强制执行 MFA</span><span class="sxs-lookup"><span data-stu-id="a74f6-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="a74f6-209">访问控制</span><span class="sxs-lookup"><span data-stu-id="a74f6-209">**Access controls**</span></span>

|<span data-ttu-id="a74f6-210">类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-210">Type</span></span>|<span data-ttu-id="a74f6-211">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-211">Properties</span></span>|<span data-ttu-id="a74f6-212">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-212">Values</span></span>|<span data-ttu-id="a74f6-213">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a74f6-214">授予</span><span class="sxs-lookup"><span data-stu-id="a74f6-214">Grant</span></span>|<span data-ttu-id="a74f6-215">授予访问权限</span><span class="sxs-lookup"><span data-stu-id="a74f6-215">Grant access</span></span>|<span data-ttu-id="a74f6-216">True</span><span class="sxs-lookup"><span data-stu-id="a74f6-216">True</span></span>|<span data-ttu-id="a74f6-217">已选定</span><span class="sxs-lookup"><span data-stu-id="a74f6-217">Selected</span></span>|
||<span data-ttu-id="a74f6-218">需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="a74f6-218">Require MFA</span></span>|<span data-ttu-id="a74f6-219">True</span><span class="sxs-lookup"><span data-stu-id="a74f6-219">True</span></span>|<span data-ttu-id="a74f6-220">Check</span><span class="sxs-lookup"><span data-stu-id="a74f6-220">Check</span></span>|
||<span data-ttu-id="a74f6-221">要求将设备标记为合规</span><span class="sxs-lookup"><span data-stu-id="a74f6-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="a74f6-222">False</span><span class="sxs-lookup"><span data-stu-id="a74f6-222">False</span></span>||
||<span data-ttu-id="a74f6-223">要求混合 Azure AD 加入设备</span><span class="sxs-lookup"><span data-stu-id="a74f6-223">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="a74f6-224">False</span><span class="sxs-lookup"><span data-stu-id="a74f6-224">False</span></span>||
||<span data-ttu-id="a74f6-225">需要经批准的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="a74f6-225">Require approved client app</span></span>|<span data-ttu-id="a74f6-226">False</span><span class="sxs-lookup"><span data-stu-id="a74f6-226">False</span></span>||
||<span data-ttu-id="a74f6-227">需要所有已选控件</span><span class="sxs-lookup"><span data-stu-id="a74f6-227">Require all the selected controls</span></span>|<span data-ttu-id="a74f6-228">True</span><span class="sxs-lookup"><span data-stu-id="a74f6-228">True</span></span>|<span data-ttu-id="a74f6-229">已选定</span><span class="sxs-lookup"><span data-stu-id="a74f6-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="a74f6-230">请务必启用此策略, 方法是选择 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="a74f6-230">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="a74f6-231">此外, 请考虑使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具来测试策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-231">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="a74f6-232">阻止不支持新式身份验证的客户端</span><span class="sxs-lookup"><span data-stu-id="a74f6-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="a74f6-233">转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="a74f6-233">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="a74f6-234">成功登录后, 您将看到 "Azure 仪表板"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-234">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="a74f6-235">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="a74f6-236">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="a74f6-237">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-237">Choose **New policy**.</span></span>

<span data-ttu-id="a74f6-238">下表介绍了要为此策略实现的条件访问策略设置。</span><span class="sxs-lookup"><span data-stu-id="a74f6-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="a74f6-239">**作业**</span><span class="sxs-lookup"><span data-stu-id="a74f6-239">**Assignments**</span></span>

|<span data-ttu-id="a74f6-240">类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-240">Type</span></span>|<span data-ttu-id="a74f6-241">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-241">Properties</span></span>|<span data-ttu-id="a74f6-242">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-242">Values</span></span>|<span data-ttu-id="a74f6-243">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a74f6-244">用户和组</span><span class="sxs-lookup"><span data-stu-id="a74f6-244">Users and groups</span></span>|<span data-ttu-id="a74f6-245">包括</span><span class="sxs-lookup"><span data-stu-id="a74f6-245">Include</span></span>|<span data-ttu-id="a74f6-246">选择用户和组 - 选择包含目标用户的特定安全组</span><span class="sxs-lookup"><span data-stu-id="a74f6-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="a74f6-247">从包含试点用户的安全组开始</span><span class="sxs-lookup"><span data-stu-id="a74f6-247">Start with security group including pilot users</span></span>|
||<span data-ttu-id="a74f6-248">排除</span><span class="sxs-lookup"><span data-stu-id="a74f6-248">Exclude</span></span>|<span data-ttu-id="a74f6-249">例外安全组；服务帐户(应用标识)</span><span class="sxs-lookup"><span data-stu-id="a74f6-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="a74f6-250">按需临时修改的成员身份</span><span class="sxs-lookup"><span data-stu-id="a74f6-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="a74f6-251">云应用</span><span class="sxs-lookup"><span data-stu-id="a74f6-251">Cloud apps</span></span>|<span data-ttu-id="a74f6-252">包括</span><span class="sxs-lookup"><span data-stu-id="a74f6-252">Include</span></span>|<span data-ttu-id="a74f6-253">选择要应用此规则的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a74f6-253">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="a74f6-254">例如, 选择 "Office 365 Exchange Online"</span><span class="sxs-lookup"><span data-stu-id="a74f6-254">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="a74f6-255">条件</span><span class="sxs-lookup"><span data-stu-id="a74f6-255">Conditions</span></span>|<span data-ttu-id="a74f6-256">已配置</span><span class="sxs-lookup"><span data-stu-id="a74f6-256">Configured</span></span>|<span data-ttu-id="a74f6-257">是</span><span class="sxs-lookup"><span data-stu-id="a74f6-257">Yes</span></span>|<span data-ttu-id="a74f6-258">配置客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="a74f6-258">Configure Client apps</span></span>|
|<span data-ttu-id="a74f6-259">客户端应用</span><span class="sxs-lookup"><span data-stu-id="a74f6-259">Client apps</span></span>|<span data-ttu-id="a74f6-260">已配置</span><span class="sxs-lookup"><span data-stu-id="a74f6-260">Configured</span></span>|<span data-ttu-id="a74f6-261">是</span><span class="sxs-lookup"><span data-stu-id="a74f6-261">Yes</span></span>|<span data-ttu-id="a74f6-262">移动应用和桌面客户端, 其他客户端 (选择两者)</span><span class="sxs-lookup"><span data-stu-id="a74f6-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="a74f6-263">访问控制</span><span class="sxs-lookup"><span data-stu-id="a74f6-263">**Access controls**</span></span>

|<span data-ttu-id="a74f6-264">类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-264">Type</span></span>|<span data-ttu-id="a74f6-265">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-265">Properties</span></span>|<span data-ttu-id="a74f6-266">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-266">Values</span></span>|<span data-ttu-id="a74f6-267">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a74f6-268">授予</span><span class="sxs-lookup"><span data-stu-id="a74f6-268">Grant</span></span>|<span data-ttu-id="a74f6-269">阻止访问</span><span class="sxs-lookup"><span data-stu-id="a74f6-269">Block access</span></span>|<span data-ttu-id="a74f6-270">True</span><span class="sxs-lookup"><span data-stu-id="a74f6-270">True</span></span>|<span data-ttu-id="a74f6-271">已选定</span><span class="sxs-lookup"><span data-stu-id="a74f6-271">Selected</span></span>|
||<span data-ttu-id="a74f6-272">需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="a74f6-272">Require MFA</span></span>|<span data-ttu-id="a74f6-273">False</span><span class="sxs-lookup"><span data-stu-id="a74f6-273">False</span></span>||
||<span data-ttu-id="a74f6-274">要求将设备标记为合规</span><span class="sxs-lookup"><span data-stu-id="a74f6-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="a74f6-275">False</span><span class="sxs-lookup"><span data-stu-id="a74f6-275">False</span></span>||
||<span data-ttu-id="a74f6-276">要求混合 Azure AD 加入设备</span><span class="sxs-lookup"><span data-stu-id="a74f6-276">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="a74f6-277">False</span><span class="sxs-lookup"><span data-stu-id="a74f6-277">False</span></span>||
||<span data-ttu-id="a74f6-278">需要经批准的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="a74f6-278">Require approved client app</span></span>|<span data-ttu-id="a74f6-279">False</span><span class="sxs-lookup"><span data-stu-id="a74f6-279">False</span></span>||
||<span data-ttu-id="a74f6-280">需要所有已选控件</span><span class="sxs-lookup"><span data-stu-id="a74f6-280">Require all the selected controls</span></span>|<span data-ttu-id="a74f6-281">True</span><span class="sxs-lookup"><span data-stu-id="a74f6-281">True</span></span>|<span data-ttu-id="a74f6-282">已选定</span><span class="sxs-lookup"><span data-stu-id="a74f6-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="a74f6-283">请务必启用此策略, 方法是选择 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="a74f6-283">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="a74f6-284">此外, 请考虑使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具来测试策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-284">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="a74f6-285">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="a74f6-285">High risk users must change password</span></span>
<span data-ttu-id="a74f6-286">若要确保所有高风险用户的受损帐户强制在登录时执行密码更改, 必须应用以下策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-286">To ensure that all high-risk users' compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="a74f6-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span><span class="sxs-lookup"><span data-stu-id="a74f6-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="a74f6-288">**作业**</span><span class="sxs-lookup"><span data-stu-id="a74f6-288">**Assignments**</span></span>

|<span data-ttu-id="a74f6-289">类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-289">Type</span></span>|<span data-ttu-id="a74f6-290">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-290">Properties</span></span>|<span data-ttu-id="a74f6-291">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-291">Values</span></span>|<span data-ttu-id="a74f6-292">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a74f6-293">Users</span><span class="sxs-lookup"><span data-stu-id="a74f6-293">Users</span></span>|<span data-ttu-id="a74f6-294">包括</span><span class="sxs-lookup"><span data-stu-id="a74f6-294">Include</span></span>|<span data-ttu-id="a74f6-295">所有用户</span><span class="sxs-lookup"><span data-stu-id="a74f6-295">All users</span></span>|<span data-ttu-id="a74f6-296">已选择</span><span class="sxs-lookup"><span data-stu-id="a74f6-296">Selected</span></span>|
||<span data-ttu-id="a74f6-297">排除</span><span class="sxs-lookup"><span data-stu-id="a74f6-297">Exclude</span></span>|<span data-ttu-id="a74f6-298">无</span><span class="sxs-lookup"><span data-stu-id="a74f6-298">None</span></span>||
|<span data-ttu-id="a74f6-299">条件</span><span class="sxs-lookup"><span data-stu-id="a74f6-299">Conditions</span></span>|<span data-ttu-id="a74f6-300">用户风险</span><span class="sxs-lookup"><span data-stu-id="a74f6-300">User risk</span></span>|<span data-ttu-id="a74f6-301">高</span><span class="sxs-lookup"><span data-stu-id="a74f6-301">High</span></span>|<span data-ttu-id="a74f6-302">已选择</span><span class="sxs-lookup"><span data-stu-id="a74f6-302">Selected</span></span>|

<span data-ttu-id="a74f6-303">控制</span><span class="sxs-lookup"><span data-stu-id="a74f6-303">**Controls**</span></span>

| <span data-ttu-id="a74f6-304">类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-304">Type</span></span> | <span data-ttu-id="a74f6-305">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-305">Properties</span></span> | <span data-ttu-id="a74f6-306">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-306">Values</span></span>                  | <span data-ttu-id="a74f6-307">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="a74f6-308">Access</span><span class="sxs-lookup"><span data-stu-id="a74f6-308">Access</span></span>     | <span data-ttu-id="a74f6-309">允许访问</span><span class="sxs-lookup"><span data-stu-id="a74f6-309">Allow access</span></span>            | <span data-ttu-id="a74f6-310">True</span><span class="sxs-lookup"><span data-stu-id="a74f6-310">True</span></span>  |
|      | <span data-ttu-id="a74f6-311">Access</span><span class="sxs-lookup"><span data-stu-id="a74f6-311">Access</span></span>     | <span data-ttu-id="a74f6-312">需要更改密码</span><span class="sxs-lookup"><span data-stu-id="a74f6-312">Require password change</span></span> | <span data-ttu-id="a74f6-313">True</span><span class="sxs-lookup"><span data-stu-id="a74f6-313">True</span></span>  |

<span data-ttu-id="a74f6-314">**审阅:** 不适用</span><span class="sxs-lookup"><span data-stu-id="a74f6-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="a74f6-315">请务必启用此策略, 方法是选择 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="a74f6-315">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="a74f6-316">此外, 请考虑使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具来测试策略</span><span class="sxs-lookup"><span data-stu-id="a74f6-316">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="a74f6-317">定义应用保护策略</span><span class="sxs-lookup"><span data-stu-id="a74f6-317">Define app protection policies</span></span>
<span data-ttu-id="a74f6-318">应用保护策略定义哪些应用程序是允许的, 以及可以对组织的数据执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a74f6-318">App protection policies define which apps are allowed and the actions they can take with your organization's data.</span></span> <span data-ttu-id="a74f6-319">从 Azure 门户中创建 Intune 应用保护策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-319">Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="a74f6-320">为每个平台创建一个策略:</span><span class="sxs-lookup"><span data-stu-id="a74f6-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="a74f6-321">iOS</span><span class="sxs-lookup"><span data-stu-id="a74f6-321">iOS</span></span>
- <span data-ttu-id="a74f6-322">Android</span><span class="sxs-lookup"><span data-stu-id="a74f6-322">Android</span></span>
- <span data-ttu-id="a74f6-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a74f6-323">Windows 10</span></span>

<span data-ttu-id="a74f6-324">若要创建新的应用保护策略, 请使用你的管理凭据登录到 Microsoft Azure 门户, 然后导航到**移动应用 > 应用保护策略**。</span><span class="sxs-lookup"><span data-stu-id="a74f6-324">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**.</span></span> <span data-ttu-id="a74f6-325">选择 "**添加策略**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-325">Choose **Add a policy**.</span></span>

<span data-ttu-id="a74f6-326">iOS 和 Android 的应用保护策略选项略有不同。</span><span class="sxs-lookup"><span data-stu-id="a74f6-326">There are slight differences in the app protection policy options between iOS and Android.</span></span> <span data-ttu-id="a74f6-327">以下策略专用于 Android。</span><span class="sxs-lookup"><span data-stu-id="a74f6-327">The below policy is specifically for Android.</span></span> <span data-ttu-id="a74f6-328">将本指南用作其他策略的指南。</span><span class="sxs-lookup"><span data-stu-id="a74f6-328">Use this as a guide for your other policies.</span></span>

<span data-ttu-id="a74f6-329">推荐的应用程序列表包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="a74f6-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="a74f6-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a74f6-330">PowerPoint</span></span>
- <span data-ttu-id="a74f6-331">Excel</span><span class="sxs-lookup"><span data-stu-id="a74f6-331">Excel</span></span>
- <span data-ttu-id="a74f6-332">Word</span><span class="sxs-lookup"><span data-stu-id="a74f6-332">Word</span></span>
- <span data-ttu-id="a74f6-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a74f6-333">Microsoft Teams</span></span>
- <span data-ttu-id="a74f6-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="a74f6-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="a74f6-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="a74f6-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="a74f6-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="a74f6-336">OneDrive</span></span>
- <span data-ttu-id="a74f6-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="a74f6-337">OneNote</span></span>
- <span data-ttu-id="a74f6-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="a74f6-338">Outlook</span></span>

<span data-ttu-id="a74f6-339">下表介绍了推荐的设置:</span><span class="sxs-lookup"><span data-stu-id="a74f6-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="a74f6-340">类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-340">Type</span></span>|<span data-ttu-id="a74f6-341">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-341">Properties</span></span>|<span data-ttu-id="a74f6-342">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-342">Values</span></span>|<span data-ttu-id="a74f6-343">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a74f6-344">数据重定位</span><span class="sxs-lookup"><span data-stu-id="a74f6-344">Data relocation</span></span>|<span data-ttu-id="a74f6-345">阻止 Android 备份</span><span class="sxs-lookup"><span data-stu-id="a74f6-345">Prevent Android backup</span></span>|<span data-ttu-id="a74f6-346">是</span><span class="sxs-lookup"><span data-stu-id="a74f6-346">Yes</span></span>|<span data-ttu-id="a74f6-347">在 iOS 上，这会专门调用 iTunes 和 iCloud</span><span class="sxs-lookup"><span data-stu-id="a74f6-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="a74f6-348">允许应用向其他应用传送数据</span><span class="sxs-lookup"><span data-stu-id="a74f6-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="a74f6-349">策略托管应用</span><span class="sxs-lookup"><span data-stu-id="a74f6-349">Policy managed apps</span></span>||
||<span data-ttu-id="a74f6-350">允许应用从其他应用接收数据</span><span class="sxs-lookup"><span data-stu-id="a74f6-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="a74f6-351">策略托管应用</span><span class="sxs-lookup"><span data-stu-id="a74f6-351">Policy managed apps</span></span>||
||<span data-ttu-id="a74f6-352">防止“另存为”</span><span class="sxs-lookup"><span data-stu-id="a74f6-352">Prevent "Save As"</span></span>|<span data-ttu-id="a74f6-353">是</span><span class="sxs-lookup"><span data-stu-id="a74f6-353">Yes</span></span>||
||<span data-ttu-id="a74f6-354">选择企业数据可保存到其中的存储服务</span><span class="sxs-lookup"><span data-stu-id="a74f6-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="a74f6-355">OneDrive for Business、SharePoint</span><span class="sxs-lookup"><span data-stu-id="a74f6-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="a74f6-356">限制使用其他应用剪切、复制和粘贴</span><span class="sxs-lookup"><span data-stu-id="a74f6-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="a74f6-357">使用 "粘贴到" 的策略托管应用</span><span class="sxs-lookup"><span data-stu-id="a74f6-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="a74f6-358">限制显示在托管浏览器内的 Web 内容</span><span class="sxs-lookup"><span data-stu-id="a74f6-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="a74f6-359">否</span><span class="sxs-lookup"><span data-stu-id="a74f6-359">No</span></span>||
||<span data-ttu-id="a74f6-360">加密应用数据</span><span class="sxs-lookup"><span data-stu-id="a74f6-360">Encrypt app data</span></span>|<span data-ttu-id="a74f6-361">是</span><span class="sxs-lookup"><span data-stu-id="a74f6-361">Yes</span></span>|<span data-ttu-id="a74f6-362">在 iOS 上，选择选项：“锁定设备时”</span><span class="sxs-lookup"><span data-stu-id="a74f6-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="a74f6-363">启用设备时禁用应用程序加密</span><span class="sxs-lookup"><span data-stu-id="a74f6-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="a74f6-364">是</span><span class="sxs-lookup"><span data-stu-id="a74f6-364">Yes</span></span>|<span data-ttu-id="a74f6-365">禁用此设置可避免双重加密</span><span class="sxs-lookup"><span data-stu-id="a74f6-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="a74f6-366">禁用联系人同步</span><span class="sxs-lookup"><span data-stu-id="a74f6-366">Disable contacts sync</span></span>|<span data-ttu-id="a74f6-367">否</span><span class="sxs-lookup"><span data-stu-id="a74f6-367">No</span></span>||
||<span data-ttu-id="a74f6-368">禁用打印</span><span class="sxs-lookup"><span data-stu-id="a74f6-368">Disable printing</span></span>|<span data-ttu-id="a74f6-369">否</span><span class="sxs-lookup"><span data-stu-id="a74f6-369">No</span></span>||
|<span data-ttu-id="a74f6-370">访问</span><span class="sxs-lookup"><span data-stu-id="a74f6-370">Access</span></span>|<span data-ttu-id="a74f6-371">访问需要 PIN</span><span class="sxs-lookup"><span data-stu-id="a74f6-371">Require PIN for access</span></span>|<span data-ttu-id="a74f6-372">是</span><span class="sxs-lookup"><span data-stu-id="a74f6-372">Yes</span></span>||
||<span data-ttu-id="a74f6-373">选择类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-373">Select Type</span></span>|<span data-ttu-id="a74f6-374">数值</span><span class="sxs-lookup"><span data-stu-id="a74f6-374">Numeric</span></span>||
||<span data-ttu-id="a74f6-375">允许使用简单 PIN</span><span class="sxs-lookup"><span data-stu-id="a74f6-375">Allow simple PIN</span></span>|<span data-ttu-id="a74f6-376">否</span><span class="sxs-lookup"><span data-stu-id="a74f6-376">No</span></span>||
||<span data-ttu-id="a74f6-377">PIN 长度</span><span class="sxs-lookup"><span data-stu-id="a74f6-377">PIN length</span></span>|<span data-ttu-id="a74f6-378">型</span><span class="sxs-lookup"><span data-stu-id="a74f6-378">6</span></span>||
||<span data-ttu-id="a74f6-379">允许使用指纹而不是 PIN</span><span class="sxs-lookup"><span data-stu-id="a74f6-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="a74f6-380">是</span><span class="sxs-lookup"><span data-stu-id="a74f6-380">Yes</span></span>||
||<span data-ttu-id="a74f6-381">在管理设备 PIN 时禁用应用 PIN</span><span class="sxs-lookup"><span data-stu-id="a74f6-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="a74f6-382">是</span><span class="sxs-lookup"><span data-stu-id="a74f6-382">Yes</span></span>||
||<span data-ttu-id="a74f6-383">需要公司凭据才能访问</span><span class="sxs-lookup"><span data-stu-id="a74f6-383">Require corporate credentials for access</span></span>|<span data-ttu-id="a74f6-384">否</span><span class="sxs-lookup"><span data-stu-id="a74f6-384">No</span></span>||
||<span data-ttu-id="a74f6-385">在一定时间后重新检查访问要求(分钟)</span><span class="sxs-lookup"><span data-stu-id="a74f6-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="a74f6-386">30</span><span class="sxs-lookup"><span data-stu-id="a74f6-386">30</span></span>||
||<span data-ttu-id="a74f6-387">阻止屏幕捕获和 Android 助手</span><span class="sxs-lookup"><span data-stu-id="a74f6-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="a74f6-388">否</span><span class="sxs-lookup"><span data-stu-id="a74f6-388">No</span></span>|<span data-ttu-id="a74f6-389">在 iOS 上，此选项不可用</span><span class="sxs-lookup"><span data-stu-id="a74f6-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="a74f6-390">登录安全要求</span><span class="sxs-lookup"><span data-stu-id="a74f6-390">Sign-in security requirements</span></span>|<span data-ttu-id="a74f6-391">最大 PIN 尝试次数</span><span class="sxs-lookup"><span data-stu-id="a74f6-391">Max PIN attempts</span></span>|<span data-ttu-id="a74f6-392">5</span><span class="sxs-lookup"><span data-stu-id="a74f6-392">5</span></span>|<span data-ttu-id="a74f6-393">重置 Pin</span><span class="sxs-lookup"><span data-stu-id="a74f6-393">Reset Pin</span></span>|
||<span data-ttu-id="a74f6-394">离线宽限期</span><span class="sxs-lookup"><span data-stu-id="a74f6-394">Offline grace period</span></span>|<span data-ttu-id="a74f6-395">720</span><span class="sxs-lookup"><span data-stu-id="a74f6-395">720</span></span>|<span data-ttu-id="a74f6-396">阻止访问</span><span class="sxs-lookup"><span data-stu-id="a74f6-396">Block access</span></span>|
||<span data-ttu-id="a74f6-397">擦除应用数据之前的脱机间隔时间（天）</span><span class="sxs-lookup"><span data-stu-id="a74f6-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="a74f6-398">90</span><span class="sxs-lookup"><span data-stu-id="a74f6-398">90</span></span>|<span data-ttu-id="a74f6-399">擦除数据</span><span class="sxs-lookup"><span data-stu-id="a74f6-399">Wipe data</span></span>|
||<span data-ttu-id="a74f6-400">已越狱/取得根的设备</span><span class="sxs-lookup"><span data-stu-id="a74f6-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="a74f6-401">擦除数据</span><span class="sxs-lookup"><span data-stu-id="a74f6-401">Wipe data</span></span>|

<span data-ttu-id="a74f6-402">完成后, 请记住选择 "创建"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-402">When complete, remember to select "Create".</span></span> <span data-ttu-id="a74f6-403">重复上述步骤，并将所选平台（下拉列表）替换为 iOS。</span><span class="sxs-lookup"><span data-stu-id="a74f6-403">Repeat the above steps and replace the selected platform (dropdown) with iOS.</span></span> <span data-ttu-id="a74f6-404">这可创建两个应用策略，因此请在创建策略后将组分配到策略，并进行部署。</span><span class="sxs-lookup"><span data-stu-id="a74f6-404">This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="a74f6-405">若要编辑策略并将这些策略分配给用户, 请参阅[如何创建和分配应用保护策略](https://docs.microsoft.com/intune/app-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="a74f6-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="a74f6-406">需要批准的应用程序</span><span class="sxs-lookup"><span data-stu-id="a74f6-406">Require approved apps</span></span>
<span data-ttu-id="a74f6-407">若要要求获得批准的应用:</span><span class="sxs-lookup"><span data-stu-id="a74f6-407">To require approved apps:</span></span>

1. <span data-ttu-id="a74f6-408">转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="a74f6-408">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="a74f6-409">成功登录后, 您将看到 "Azure 仪表板"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-409">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="a74f6-410">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="a74f6-411">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="a74f6-412">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="a74f6-413">输入策略名称，然后选择要应用策略的“用户和组”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="a74f6-414">选择“云应用”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="a74f6-415">选择 "**选择应用**", 从 "**云应用**" 列表中选择所需的应用。</span><span class="sxs-lookup"><span data-stu-id="a74f6-415">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="a74f6-416">例如, 选择 "Office 365 Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-416">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="a74f6-417">选择 "**选择**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-417">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="a74f6-418">选择 "**条件**", 选择 "**设备平台**", 然后选择 "**配置**"</span><span class="sxs-lookup"><span data-stu-id="a74f6-418">Choose **Conditions**, select **Device platforms**, then choose **Configure**</span></span>

9. <span data-ttu-id="a74f6-419">在 "**包含**" 下, 选择 "**选择设备平台**", 选择 " **Android**和**iOS**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-419">Under **Include**, choose **Select device platforms**, select **Android** and **iOS**.</span></span> <span data-ttu-id="a74f6-420">单击 "**完成**" 并再次**执行**</span><span class="sxs-lookup"><span data-stu-id="a74f6-420">Click **Done** and **Done** again</span></span>

10. <span data-ttu-id="a74f6-421">从“访问控制”部分选择“授予”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-421">Choose **Grant** from the **Access controls** section.</span></span>

11. <span data-ttu-id="a74f6-422">选择 "**授予访问权限**", 选择 "**需要批准的客户端应用**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-422">Choose **Grant access**, select **Require approved client app**.</span></span> <span data-ttu-id="a74f6-423">对于多个控件, 选择 "**需要选定的控件**", 然后选择 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-423">For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

12. <span data-ttu-id="a74f6-424">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a74f6-424">Choose **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="a74f6-425">定义设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="a74f6-425">Define device-compliance policies</span></span>

<span data-ttu-id="a74f6-426">设备合规性策略定义设备必须遵循的要求才能标记为合规。</span><span class="sxs-lookup"><span data-stu-id="a74f6-426">Device-compliance policies define the requirements that devices must adhere to in order to be marked as compliant.</span></span> <span data-ttu-id="a74f6-427">从 Azure 门户中创建 Intune 设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="a74f6-427">Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="a74f6-428">为每个平台创建一个策略:</span><span class="sxs-lookup"><span data-stu-id="a74f6-428">Create a policy for each platform:</span></span>
- <span data-ttu-id="a74f6-429">Android</span><span class="sxs-lookup"><span data-stu-id="a74f6-429">Android</span></span>
- <span data-ttu-id="a74f6-430">Android 企业版</span><span class="sxs-lookup"><span data-stu-id="a74f6-430">Android enterprise</span></span>
- <span data-ttu-id="a74f6-431">iOS</span><span class="sxs-lookup"><span data-stu-id="a74f6-431">iOS</span></span>
- <span data-ttu-id="a74f6-432">macOS</span><span class="sxs-lookup"><span data-stu-id="a74f6-432">macOS</span></span>
- <span data-ttu-id="a74f6-433">此设置在以下类型的设备上可用：</span><span class="sxs-lookup"><span data-stu-id="a74f6-433">Windows Phone 8.1</span></span>
- <span data-ttu-id="a74f6-434">Windows 8.1 及更高版本</span><span class="sxs-lookup"><span data-stu-id="a74f6-434">Windows 8.1 and later</span></span>
- <span data-ttu-id="a74f6-435">Windows 10 及更高版本</span><span class="sxs-lookup"><span data-stu-id="a74f6-435">Windows 10 and later</span></span>

<span data-ttu-id="a74f6-436">若要创建设备合规性策略, 请使用你的管理凭据登录到 Microsoft Azure 门户, 然后导航到**Intune > 设备合规性**。</span><span class="sxs-lookup"><span data-stu-id="a74f6-436">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**.</span></span> <span data-ttu-id="a74f6-437">选择 "**创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-437">Select **Create policy**.</span></span>

<span data-ttu-id="a74f6-438">建议将以下设置用于 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="a74f6-438">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="a74f6-439">**设备运行状况: Windows 运行状况证明服务评估规则**</span><span class="sxs-lookup"><span data-stu-id="a74f6-439">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="a74f6-440">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-440">Properties</span></span>|<span data-ttu-id="a74f6-441">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-441">Values</span></span>|<span data-ttu-id="a74f6-442">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-442">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="a74f6-443">需要 BitLocker</span><span class="sxs-lookup"><span data-stu-id="a74f6-443">Require BitLocker</span></span>|<span data-ttu-id="a74f6-444">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-444">Require</span></span>||
|<span data-ttu-id="a74f6-445">要求在设备上启用安全启动</span><span class="sxs-lookup"><span data-stu-id="a74f6-445">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="a74f6-446">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-446">Require</span></span>||
|<span data-ttu-id="a74f6-447">需要代码完整性</span><span class="sxs-lookup"><span data-stu-id="a74f6-447">Require code integrity</span></span>|<span data-ttu-id="a74f6-448">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-448">Require</span></span>||


<span data-ttu-id="a74f6-449">设备属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-449">**Device properties**</span></span>

|<span data-ttu-id="a74f6-450">类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-450">Type</span></span>|<span data-ttu-id="a74f6-451">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-451">Properties</span></span>|<span data-ttu-id="a74f6-452">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-452">Values</span></span>|<span data-ttu-id="a74f6-453">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-453">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a74f6-454">操作系统版本</span><span class="sxs-lookup"><span data-stu-id="a74f6-454">Operating system version</span></span>|<span data-ttu-id="a74f6-455">全部</span><span class="sxs-lookup"><span data-stu-id="a74f6-455">All</span></span>|<span data-ttu-id="a74f6-456">未配置</span><span class="sxs-lookup"><span data-stu-id="a74f6-456">Not configured</span></span>||

<span data-ttu-id="a74f6-457">要将上述所有策略视为已部署，这些策略必须面向用户组。</span><span class="sxs-lookup"><span data-stu-id="a74f6-457">For all the above policies to be considered deployed, they must be targeted at user groups.</span></span> <span data-ttu-id="a74f6-458">为此, 可以通过在 "**策略**" 部分中选择 "**管理部署**" (与 "添加" 相同级别) 来创建策略 (在保存时) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a74f6-458">You can do this by creating the policy (on Save) or later by selecting **Manage Deployment** in the **Policy** section (same level as Add).</span></span>

<span data-ttu-id="a74f6-459">系统安全</span><span class="sxs-lookup"><span data-stu-id="a74f6-459">**System security**</span></span>

|<span data-ttu-id="a74f6-460">类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-460">Type</span></span>|<span data-ttu-id="a74f6-461">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-461">Properties</span></span>|<span data-ttu-id="a74f6-462">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-462">Values</span></span>|<span data-ttu-id="a74f6-463">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-463">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a74f6-464">Password</span><span class="sxs-lookup"><span data-stu-id="a74f6-464">Password</span></span>|<span data-ttu-id="a74f6-465">需要密码才能解锁移动设备</span><span class="sxs-lookup"><span data-stu-id="a74f6-465">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="a74f6-466">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-466">Require</span></span>||
||<span data-ttu-id="a74f6-467">简单密码</span><span class="sxs-lookup"><span data-stu-id="a74f6-467">Simple passwords</span></span>|<span data-ttu-id="a74f6-468">阻止</span><span class="sxs-lookup"><span data-stu-id="a74f6-468">Block</span></span>||
||<span data-ttu-id="a74f6-469">密码类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-469">Password type</span></span>|<span data-ttu-id="a74f6-470">设备默认值</span><span class="sxs-lookup"><span data-stu-id="a74f6-470">Device default</span></span>||
||<span data-ttu-id="a74f6-471">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="a74f6-471">Minimum password length</span></span>|<span data-ttu-id="a74f6-472">型</span><span class="sxs-lookup"><span data-stu-id="a74f6-472">6</span></span>||
||<span data-ttu-id="a74f6-473">在需要密码之前不活动的最长分钟数</span><span class="sxs-lookup"><span data-stu-id="a74f6-473">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="a74f6-474">个</span><span class="sxs-lookup"><span data-stu-id="a74f6-474">15</span></span>|<span data-ttu-id="a74f6-475">Android 版本4.0 及更高版本或 KNOX 4.0 及更高版本支持此设置。</span><span class="sxs-lookup"><span data-stu-id="a74f6-475">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above.</span></span> <span data-ttu-id="a74f6-476">对于 iOS 设备, 支持 iOS 8.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="a74f6-476">For iOS devices, it’s supported for iOS 8.0 and above</span></span>|
||<span data-ttu-id="a74f6-477">密码过期 (天)</span><span class="sxs-lookup"><span data-stu-id="a74f6-477">Password expiration (days)</span></span>|<span data-ttu-id="a74f6-478">41</span><span class="sxs-lookup"><span data-stu-id="a74f6-478">41</span></span>||
||<span data-ttu-id="a74f6-479">用于防止重复使用的以前密码的数目</span><span class="sxs-lookup"><span data-stu-id="a74f6-479">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="a74f6-480">5</span><span class="sxs-lookup"><span data-stu-id="a74f6-480">5</span></span>||
||<span data-ttu-id="a74f6-481">当设备从空闲状态 (移动和全息) 返回时需要密码</span><span class="sxs-lookup"><span data-stu-id="a74f6-481">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="a74f6-482">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-482">Require</span></span>|<span data-ttu-id="a74f6-483">适用于 Windows 10 及更高版本</span><span class="sxs-lookup"><span data-stu-id="a74f6-483">Available for Windows 10 and later</span></span>|
|<span data-ttu-id="a74f6-484">加密</span><span class="sxs-lookup"><span data-stu-id="a74f6-484">Encryption</span></span>|<span data-ttu-id="a74f6-485">设备上的数据存储加密</span><span class="sxs-lookup"><span data-stu-id="a74f6-485">Encryption of data storage on device</span></span>|<span data-ttu-id="a74f6-486">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-486">Require</span></span>||
|<span data-ttu-id="a74f6-487">设备安全性</span><span class="sxs-lookup"><span data-stu-id="a74f6-487">Device Security</span></span>|<span data-ttu-id="a74f6-488">Firewall</span><span class="sxs-lookup"><span data-stu-id="a74f6-488">Firewall</span></span>|<span data-ttu-id="a74f6-489">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-489">Require</span></span>||
||<span data-ttu-id="a74f6-490">防病毒</span><span class="sxs-lookup"><span data-stu-id="a74f6-490">Antivirus</span></span>|<span data-ttu-id="a74f6-491">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-491">Require</span></span>||
||<span data-ttu-id="a74f6-492">间谍</span><span class="sxs-lookup"><span data-stu-id="a74f6-492">Antispyware</span></span>|<span data-ttu-id="a74f6-493">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-493">Require</span></span>|<span data-ttu-id="a74f6-494">此设置需要在 Windows 安全中心中注册的反间谍软件解决方案</span><span class="sxs-lookup"><span data-stu-id="a74f6-494">This setting requires an Anti-Spyware solution registered with Windows Security Center</span></span>|
|<span data-ttu-id="a74f6-495">Defender</span><span class="sxs-lookup"><span data-stu-id="a74f6-495">Defender</span></span>|<span data-ttu-id="a74f6-496">Windows Defender 反恶意软件</span><span class="sxs-lookup"><span data-stu-id="a74f6-496">Windows Defender Antimalware</span></span>|<span data-ttu-id="a74f6-497">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-497">Require</span></span>||
||<span data-ttu-id="a74f6-498">Windows Defender 反恶意软件最低版本</span><span class="sxs-lookup"><span data-stu-id="a74f6-498">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="a74f6-499">仅支持 Windows 10 桌面版。</span><span class="sxs-lookup"><span data-stu-id="a74f6-499">Only supported for Windows 10 desktop.</span></span> <span data-ttu-id="a74f6-500">Microsoft 建议版本的背后不超过最新版本五个</span><span class="sxs-lookup"><span data-stu-id="a74f6-500">Microsoft recommends versions no more than five behind from the most recent version</span></span>|
||<span data-ttu-id="a74f6-501">最新的 Windows Defender 反恶意软件签名</span><span class="sxs-lookup"><span data-stu-id="a74f6-501">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="a74f6-502">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-502">Require</span></span>||
||<span data-ttu-id="a74f6-503">实时保护</span><span class="sxs-lookup"><span data-stu-id="a74f6-503">Real-time protection</span></span>|<span data-ttu-id="a74f6-504">需要</span><span class="sxs-lookup"><span data-stu-id="a74f6-504">Require</span></span>|<span data-ttu-id="a74f6-505">仅支持 Windows 10 桌面版</span><span class="sxs-lookup"><span data-stu-id="a74f6-505">Only supported for Windows 10 desktop</span></span>|

<span data-ttu-id="a74f6-506">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="a74f6-506">**Windows Defender ATP**</span></span>

|<span data-ttu-id="a74f6-507">类型</span><span class="sxs-lookup"><span data-stu-id="a74f6-507">Type</span></span>|<span data-ttu-id="a74f6-508">属性</span><span class="sxs-lookup"><span data-stu-id="a74f6-508">Properties</span></span>|<span data-ttu-id="a74f6-509">值</span><span class="sxs-lookup"><span data-stu-id="a74f6-509">Values</span></span>|<span data-ttu-id="a74f6-510">注意</span><span class="sxs-lookup"><span data-stu-id="a74f6-510">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="a74f6-511">Windows Defender 高级威胁防护规则</span><span class="sxs-lookup"><span data-stu-id="a74f6-511">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="a74f6-512">要求设备在计算机风险得分</span><span class="sxs-lookup"><span data-stu-id="a74f6-512">Require the device to be at or under the machine-risk score</span></span>|<span data-ttu-id="a74f6-513">中</span><span class="sxs-lookup"><span data-stu-id="a74f6-513">Medium</span></span>||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="a74f6-514">需要符合要求的电脑 (但不符合兼容电话和平板电脑)</span><span class="sxs-lookup"><span data-stu-id="a74f6-514">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="a74f6-515">在将策略添加到需要兼容的电脑之前, 请务必在 Intune 中注册设备进行管理。</span><span class="sxs-lookup"><span data-stu-id="a74f6-515">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune.</span></span> <span data-ttu-id="a74f6-516">建议在将设备注册到 Intune 中之前使用多重身份验证, 以确保设备已占有目标用户。</span><span class="sxs-lookup"><span data-stu-id="a74f6-516">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="a74f6-517">若要要求合规的电脑:</span><span class="sxs-lookup"><span data-stu-id="a74f6-517">To require compliant PCs:</span></span>

1. <span data-ttu-id="a74f6-518">转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="a74f6-518">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="a74f6-519">成功登录后, 您将看到 "Azure 仪表板"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-519">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="a74f6-520">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-520">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="a74f6-521">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-521">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="a74f6-522">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-522">Choose **New policy**.</span></span>

5. <span data-ttu-id="a74f6-523">输入策略名称，然后选择要应用策略的“用户和组”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-523">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="a74f6-524">选择“云应用”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-524">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="a74f6-525">选择 "**选择应用**", 从 "**云应用**" 列表中选择所需的应用。</span><span class="sxs-lookup"><span data-stu-id="a74f6-525">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="a74f6-526">例如, 选择 "Office 365 Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-526">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="a74f6-527">选择 "**选择**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-527">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="a74f6-528">若要要求兼容的电脑, 但不符合兼容电话和平板电脑, 请选择 "**条件**" 和 "**设备平台**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-528">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**.</span></span> <span data-ttu-id="a74f6-529">选择 "**选择设备平台**" 并选择 " **Windows**和**macOS**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-529">Choose **Select device platforms** and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="a74f6-530">从“访问控制”部分选择“授予”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-530">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="a74f6-531">选择 "**授予访问权限**", 选择 "**要求设备被标记为合规**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-531">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="a74f6-532">对于多个控件, 选择 **"要求所有选定控件**", 然后选择 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-532">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="a74f6-533">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a74f6-533">Choose **Create**.</span></span>

<span data-ttu-id="a74f6-534">如果您的目标是要求符合合规性的 Pc*和*移动设备, 请不要选择 "平台"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-534">If your objective is to require compliant PCs *and* mobile devices, do not select platforms.</span></span> <span data-ttu-id="a74f6-535">这将强制实施所有设备的符合性。</span><span class="sxs-lookup"><span data-stu-id="a74f6-535">This enforces compliance for all devices.</span></span> 

## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="a74f6-536">需要符合要求*的 pc 和*移动设备</span><span class="sxs-lookup"><span data-stu-id="a74f6-536">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="a74f6-537">若要要求所有设备符合性, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="a74f6-537">To require compliance for all devices:</span></span>

1. <span data-ttu-id="a74f6-538">转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="a74f6-538">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="a74f6-539">成功登录后, 您将看到 "Azure 仪表板"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-539">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="a74f6-540">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-540">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="a74f6-541">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-541">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="a74f6-542">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-542">Choose **New policy**.</span></span>

5. <span data-ttu-id="a74f6-543">输入策略名称，然后选择要应用策略的“用户和组”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-543">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="a74f6-544">选择“云应用”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-544">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="a74f6-545">选择 "**选择应用**", 从 "**云应用**" 列表中选择所需的应用。</span><span class="sxs-lookup"><span data-stu-id="a74f6-545">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="a74f6-546">例如, 选择 "Office 365 Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-546">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="a74f6-547">选择 "**选择**并**完成**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-547">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="a74f6-548">从“访问控制”部分选择“授予”。</span><span class="sxs-lookup"><span data-stu-id="a74f6-548">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="a74f6-549">选择 "**授予访问权限**", 选择 "**要求设备被标记为合规**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-549">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="a74f6-550">对于多个控件, 选择 **"要求所有选定控件**", 然后选择 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="a74f6-550">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="a74f6-551">选择“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a74f6-551">Choose **Create**.</span></span>

<span data-ttu-id="a74f6-552">创建此策略时, 请不要选择平台。</span><span class="sxs-lookup"><span data-stu-id="a74f6-552">When creating this policy, do not select platforms.</span></span> <span data-ttu-id="a74f6-553">这将强制实施符合性的设备。</span><span class="sxs-lookup"><span data-stu-id="a74f6-553">This enforces compliant devices.</span></span>


## <a name="next-steps"></a><span data-ttu-id="a74f6-554">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a74f6-554">Next steps</span></span>

[<span data-ttu-id="a74f6-555">了解有关用于保护电子邮件的策略建议</span><span class="sxs-lookup"><span data-stu-id="a74f6-555">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
