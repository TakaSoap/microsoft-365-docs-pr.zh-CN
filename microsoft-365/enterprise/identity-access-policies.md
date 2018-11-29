---
title: 常见的标识和设备访问策略-Microsoft 365 企业版 |Microsoft 文档
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
ms.openlocfilehash: 72a957222ed3bba449e1576873bfc87a614c075b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866034"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="b8e07-103">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="b8e07-103">Common identity and device access policies</span></span>
<span data-ttu-id="b8e07-104">本文介绍推荐用于保护权云服务的策略的共同包括本地应用程序发布与 Azure AD 应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="b8e07-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="b8e07-p101">本指南讨论如何在新预配的环境中部署推荐的策略。 通过在单独的实验室环境中设置这些策略，可以先了解和评估推荐的策略，然后再分阶段推出到预生产和生产环境。 新预配的环境可能仅限云，也可能是混合环境。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p101">This guidance discusses how to deploy the recommended policies in a newly provisioned environment. Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your pre-production and production environments. Your newly provisioned environment may be cloud-only or Hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="b8e07-108">策略设置</span><span class="sxs-lookup"><span data-stu-id="b8e07-108">Policy set</span></span> 

<span data-ttu-id="b8e07-p102">下图说明了推荐的策略集。它显示哪一层保护措施适用于每个策略和策略是否适用于 Pc、 电话和平板电脑或设备这两个类别。它还指示配置了这些策略。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p102">The following diagram illustrates the recommended set of policies. It shows which tier of protections each policy applies to and whether the policies apply to PCs, phones and tablets, or both categories of devices. It also indicates where these policies are configured.</span></span>

![常见配置标识和设备访问的策略](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="b8e07-113">本文的其余部分介绍如何配置这些策略。</span><span class="sxs-lookup"><span data-stu-id="b8e07-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="b8e07-p103">注册到 Intune 的设备的设备包含在预期的用户所拥有的保证之前，建议使用多因素身份验证。您必须注册设备到 Intune 强制实施设备合规性策略之前。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p103">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user. And you must enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="b8e07-p104">要授予时间来完成这些任务，我们建议此表中列出的顺序实现基准策略。但是，在任何时候都可以实现敏感和高管控保护的 MFA 策略。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p104">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table. However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="b8e07-118">保护级别</span><span class="sxs-lookup"><span data-stu-id="b8e07-118">Protection level</span></span>|<span data-ttu-id="b8e07-119">Policies</span><span class="sxs-lookup"><span data-stu-id="b8e07-119">Policies</span></span>|<span data-ttu-id="b8e07-120">更多信息</span><span class="sxs-lookup"><span data-stu-id="b8e07-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="b8e07-121">**基线**</span><span class="sxs-lookup"><span data-stu-id="b8e07-121">**Baseline**</span></span>|[<span data-ttu-id="b8e07-122">*中等*或*高*风险登录时需要 MFA</span><span class="sxs-lookup"><span data-stu-id="b8e07-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="b8e07-123">阻止客户端不支持现代身份验证</span><span class="sxs-lookup"><span data-stu-id="b8e07-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="b8e07-124">不使用现代的身份验证的客户端可以跳过条件访问规则，因此很重要阻止这些。</span><span class="sxs-lookup"><span data-stu-id="b8e07-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these.</span></span>|
|        |[<span data-ttu-id="b8e07-125">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="b8e07-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="b8e07-126">强制用户如果高风险活动检测到其帐户在登录后更改其密码。</span><span class="sxs-lookup"><span data-stu-id="b8e07-126">Forces users to change their password when signing in if high risk activity is detected for their account.</span></span>|
|        |[<span data-ttu-id="b8e07-127">定义应用程序保护策略</span><span class="sxs-lookup"><span data-stu-id="b8e07-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="b8e07-128">每个平台 (iOS，Android、 Windows) 的一个策略。</span><span class="sxs-lookup"><span data-stu-id="b8e07-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="b8e07-129">需要已批准应用程序</span><span class="sxs-lookup"><span data-stu-id="b8e07-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="b8e07-130">强制移动应用程序保护手机和平板电脑</span><span class="sxs-lookup"><span data-stu-id="b8e07-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="b8e07-131">定义设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="b8e07-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="b8e07-132">每个平台的的一个策略。</span><span class="sxs-lookup"><span data-stu-id="b8e07-132">One policy for each platform.</span></span>|
|        |[<span data-ttu-id="b8e07-133">需要符合标准的 Pc</span><span class="sxs-lookup"><span data-stu-id="b8e07-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="b8e07-134">强制实施 Pc Intune 的管理</span><span class="sxs-lookup"><span data-stu-id="b8e07-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="b8e07-135">**敏感**</span><span class="sxs-lookup"><span data-stu-id="b8e07-135">**Sensitive**</span></span>|[<span data-ttu-id="b8e07-136">*低*、*中*或*高*风险登录时需要 MFA</span><span class="sxs-lookup"><span data-stu-id="b8e07-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="b8e07-137">需要符合标准的 Pc*和*移动设备</span><span class="sxs-lookup"><span data-stu-id="b8e07-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="b8e07-138">强制执行 Pc 和平板电脑电话/Intune 的管理。</span><span class="sxs-lookup"><span data-stu-id="b8e07-138">Enforces Intune management for PCs and phone/tablets.</span></span>|
|<span data-ttu-id="b8e07-139">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="b8e07-139">**Highly regulated**</span></span>|[<span data-ttu-id="b8e07-140">*始终*需要 MFA</span><span class="sxs-lookup"><span data-stu-id="b8e07-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="b8e07-141">向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="b8e07-141">Assigning policies to users</span></span>
<span data-ttu-id="b8e07-p105">配置策略之前，确定要用于保护每一层的 Azure AD 组。通常，比较基准保护适用于组织中的每个人。包含的比较基准和敏感的保护功能的用户将必须应用的比较基准策略以及敏感的策略。保护累积以及实施最严格策略。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p105">Before configuring policies, identify the Azure AD groups you are using for each tier of protection. Typically, baseline protection applies to everybody in the organization. A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies. Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="b8e07-p106">建议的做法是创建 Azure AD 组条件访问排除。将该组添加到所有条件访问规则"排除"下。这样，您可以向用户提供访问，而您解决访问问题的方法。这被建议为临时解决方案。监视更改此组，并确保仅适用于正在使用排除组。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p106">A recommended practice is to create an Azure AD group for conditional access exclusion. Add this group to all of your conditional access rules under "Exclude". This gives you a method to provide access to a user while you troubleshoot access issues. This is recommended as a temporary solution only. Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="b8e07-151">下图提供了用户分配和排除的示例。</span><span class="sxs-lookup"><span data-stu-id="b8e07-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![示例用户分配和排除 MFA 规则条件](../images/identity-access-policies-assignment.png)

<span data-ttu-id="b8e07-p107">在图 MFA*始终*需要一个条件的访问策略分配"顶部机密项目 X 团队"。应用于用户的更高级别的保护时应谨慎。此项目工作组成员需要提供两种形式的身份验证，每次登录，即使它们不查看高度管控的内容。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p107">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*. Be judicious when applying higher levels of protection to users. Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly regulated content.</span></span>  

 <span data-ttu-id="b8e07-p108">创建这些建议的一部分的所有 Azure AD 组必须创建为 Office 365 组。保护 SharePoint Online 中的文档时，这是特别重要部署 Azure 信息保护 (AIP)。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p108">All Azure AD groups created as part of these recommendations must be created as Office 365 groups. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![创建 Office 365 组的屏幕截图](../images/identity-device-AAD-groups.png)




## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="b8e07-159">需要 MFA 根据登录风险</span><span class="sxs-lookup"><span data-stu-id="b8e07-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="b8e07-p109">需要 MFA 之前, 先使用 Identity 保护 MFA 注册策略注册 MFA 用户。注册用户后，可以强制 MFA 登录。[必备工作](identity-access-prerequisites.md)包括 MFA 中注册的所有用户。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p109">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA. After users are registered you can enforce MFA for sign-in. The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="b8e07-163">创建新的条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="b8e07-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="b8e07-p110">转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，会看到 Azure 仪表板。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p110">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="b8e07-166">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="b8e07-167">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="b8e07-168">选择**新策略**，如下面的屏幕截图中所示：</span><span class="sxs-lookup"><span data-stu-id="b8e07-168">Choose **New policy** as shown in the screenshot below:</span></span>

![基线 CA 策略](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="b8e07-170">下表介绍实现此策略的条件的访问策略设置。</span><span class="sxs-lookup"><span data-stu-id="b8e07-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="b8e07-171">分配</span><span class="sxs-lookup"><span data-stu-id="b8e07-171">**Assignments**</span></span>

|<span data-ttu-id="b8e07-172">类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-172">Type</span></span>|<span data-ttu-id="b8e07-173">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-173">Properties</span></span>|<span data-ttu-id="b8e07-174">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-174">Values</span></span>|<span data-ttu-id="b8e07-175">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b8e07-176">用户和组</span><span class="sxs-lookup"><span data-stu-id="b8e07-176">Users and groups</span></span>|<span data-ttu-id="b8e07-177">包括</span><span class="sxs-lookup"><span data-stu-id="b8e07-177">Include</span></span>|<span data-ttu-id="b8e07-178">选择用户和组 - 选择包含目标用户的特定安全组</span><span class="sxs-lookup"><span data-stu-id="b8e07-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="b8e07-179">从包含试点用户的安全组开始。</span><span class="sxs-lookup"><span data-stu-id="b8e07-179">Start with security group including pilot users.</span></span>|
||<span data-ttu-id="b8e07-180">排除</span><span class="sxs-lookup"><span data-stu-id="b8e07-180">Exclude</span></span>|<span data-ttu-id="b8e07-181">例外安全组；服务帐户(应用标识)</span><span class="sxs-lookup"><span data-stu-id="b8e07-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="b8e07-182">按需临时修改的成员身份</span><span class="sxs-lookup"><span data-stu-id="b8e07-182">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="b8e07-183">云应用</span><span class="sxs-lookup"><span data-stu-id="b8e07-183">Cloud apps</span></span>|<span data-ttu-id="b8e07-184">包括</span><span class="sxs-lookup"><span data-stu-id="b8e07-184">Include</span></span>|<span data-ttu-id="b8e07-p111">选择您希望此规则应用于的应用程序。例如，选择 Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b8e07-p111">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="b8e07-187">条件</span><span class="sxs-lookup"><span data-stu-id="b8e07-187">Conditions</span></span>|<span data-ttu-id="b8e07-188">已配置</span><span class="sxs-lookup"><span data-stu-id="b8e07-188">Configured</span></span>|<span data-ttu-id="b8e07-189">是</span><span class="sxs-lookup"><span data-stu-id="b8e07-189">Yes</span></span>|<span data-ttu-id="b8e07-190">根据自身环境和需求进行配置</span><span class="sxs-lookup"><span data-stu-id="b8e07-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="b8e07-191">登录风险</span><span class="sxs-lookup"><span data-stu-id="b8e07-191">Sign-in risk</span></span>|<span data-ttu-id="b8e07-192">风险级别</span><span class="sxs-lookup"><span data-stu-id="b8e07-192">Risk level</span></span>||<span data-ttu-id="b8e07-193">请参阅下表中的指南</span><span class="sxs-lookup"><span data-stu-id="b8e07-193">See the guidance in the following table</span></span>|

<span data-ttu-id="b8e07-194">**登录风险**</span><span class="sxs-lookup"><span data-stu-id="b8e07-194">**Sign-in risk**</span></span>

<span data-ttu-id="b8e07-195">应用基于您的目标的保护级别的设置。</span><span class="sxs-lookup"><span data-stu-id="b8e07-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="b8e07-196">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-196">Property</span></span>|<span data-ttu-id="b8e07-197">保护级别</span><span class="sxs-lookup"><span data-stu-id="b8e07-197">Level of protection</span></span>|<span data-ttu-id="b8e07-198">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-198">Values</span></span>|<span data-ttu-id="b8e07-199">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b8e07-200">风险级别</span><span class="sxs-lookup"><span data-stu-id="b8e07-200">Risk level</span></span>|<span data-ttu-id="b8e07-201">基线</span><span class="sxs-lookup"><span data-stu-id="b8e07-201">Baseline</span></span>|<span data-ttu-id="b8e07-202">高、中</span><span class="sxs-lookup"><span data-stu-id="b8e07-202">High, medium</span></span>|<span data-ttu-id="b8e07-203">两项全选</span><span class="sxs-lookup"><span data-stu-id="b8e07-203">Check both</span></span>|
| |<span data-ttu-id="b8e07-204">敏感</span><span class="sxs-lookup"><span data-stu-id="b8e07-204">Sensitive</span></span>|<span data-ttu-id="b8e07-205">高、 中、 低</span><span class="sxs-lookup"><span data-stu-id="b8e07-205">High, medium, low</span></span>|<span data-ttu-id="b8e07-206">三项全选</span><span class="sxs-lookup"><span data-stu-id="b8e07-206">Check all three</span></span>|
| |<span data-ttu-id="b8e07-207">高度管控</span><span class="sxs-lookup"><span data-stu-id="b8e07-207">Highly regulated</span></span>| |<span data-ttu-id="b8e07-208">保留所有选项保持为不选中始终强制实施 MFA</span><span class="sxs-lookup"><span data-stu-id="b8e07-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="b8e07-209">访问控制</span><span class="sxs-lookup"><span data-stu-id="b8e07-209">**Access controls**</span></span>

|<span data-ttu-id="b8e07-210">类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-210">Type</span></span>|<span data-ttu-id="b8e07-211">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-211">Properties</span></span>|<span data-ttu-id="b8e07-212">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-212">Values</span></span>|<span data-ttu-id="b8e07-213">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b8e07-214">授予</span><span class="sxs-lookup"><span data-stu-id="b8e07-214">Grant</span></span>|<span data-ttu-id="b8e07-215">授予访问权限</span><span class="sxs-lookup"><span data-stu-id="b8e07-215">Grant access</span></span>|<span data-ttu-id="b8e07-216">True</span><span class="sxs-lookup"><span data-stu-id="b8e07-216">True</span></span>|<span data-ttu-id="b8e07-217">已选择</span><span class="sxs-lookup"><span data-stu-id="b8e07-217">Selected</span></span>|
||<span data-ttu-id="b8e07-218">需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="b8e07-218">Require MFA</span></span>|<span data-ttu-id="b8e07-219">True</span><span class="sxs-lookup"><span data-stu-id="b8e07-219">True</span></span>|<span data-ttu-id="b8e07-220">Check</span><span class="sxs-lookup"><span data-stu-id="b8e07-220">Check</span></span>|
||<span data-ttu-id="b8e07-221">需要标记为兼容的设备</span><span class="sxs-lookup"><span data-stu-id="b8e07-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="b8e07-222">False</span><span class="sxs-lookup"><span data-stu-id="b8e07-222">False</span></span>||
||<span data-ttu-id="b8e07-223">需要混合 Azure AD 联接的设备</span><span class="sxs-lookup"><span data-stu-id="b8e07-223">Require Hybrid Azure AD joined device</span></span>|<span data-ttu-id="b8e07-224">False</span><span class="sxs-lookup"><span data-stu-id="b8e07-224">False</span></span>||
||<span data-ttu-id="b8e07-225">需要批准的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="b8e07-225">Require approved client app</span></span>|<span data-ttu-id="b8e07-226">False</span><span class="sxs-lookup"><span data-stu-id="b8e07-226">False</span></span>||
||<span data-ttu-id="b8e07-227">需要所有已选控件</span><span class="sxs-lookup"><span data-stu-id="b8e07-227">Require all the selected controls</span></span>|<span data-ttu-id="b8e07-228">True</span><span class="sxs-lookup"><span data-stu-id="b8e07-228">True</span></span>|<span data-ttu-id="b8e07-229">已选择</span><span class="sxs-lookup"><span data-stu-id="b8e07-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="b8e07-p112">一定要启用此策略，通过**单击**。此外考虑[如果](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具用于测试策略</span><span class="sxs-lookup"><span data-stu-id="b8e07-p112">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="b8e07-232">阻止客户端不支持现代身份验证</span><span class="sxs-lookup"><span data-stu-id="b8e07-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="b8e07-p113">转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，会看到 Azure 仪表板。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p113">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="b8e07-235">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="b8e07-236">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="b8e07-237">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-237">Choose **New policy**.</span></span>

<span data-ttu-id="b8e07-238">下表介绍实现此策略的条件的访问策略设置。</span><span class="sxs-lookup"><span data-stu-id="b8e07-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="b8e07-239">分配</span><span class="sxs-lookup"><span data-stu-id="b8e07-239">**Assignments**</span></span>

|<span data-ttu-id="b8e07-240">类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-240">Type</span></span>|<span data-ttu-id="b8e07-241">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-241">Properties</span></span>|<span data-ttu-id="b8e07-242">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-242">Values</span></span>|<span data-ttu-id="b8e07-243">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b8e07-244">用户和组</span><span class="sxs-lookup"><span data-stu-id="b8e07-244">Users and groups</span></span>|<span data-ttu-id="b8e07-245">包括</span><span class="sxs-lookup"><span data-stu-id="b8e07-245">Include</span></span>|<span data-ttu-id="b8e07-246">选择用户和组 - 选择包含目标用户的特定安全组</span><span class="sxs-lookup"><span data-stu-id="b8e07-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="b8e07-247">从包含试点用户的安全组开始。</span><span class="sxs-lookup"><span data-stu-id="b8e07-247">Start with security group including pilot users.</span></span>|
||<span data-ttu-id="b8e07-248">排除</span><span class="sxs-lookup"><span data-stu-id="b8e07-248">Exclude</span></span>|<span data-ttu-id="b8e07-249">例外安全组；服务帐户(应用标识)</span><span class="sxs-lookup"><span data-stu-id="b8e07-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="b8e07-250">按需临时修改的成员身份</span><span class="sxs-lookup"><span data-stu-id="b8e07-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="b8e07-251">云应用</span><span class="sxs-lookup"><span data-stu-id="b8e07-251">Cloud apps</span></span>|<span data-ttu-id="b8e07-252">包括</span><span class="sxs-lookup"><span data-stu-id="b8e07-252">Include</span></span>|<span data-ttu-id="b8e07-p114">选择您希望此规则应用于的应用程序。例如，选择 Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b8e07-p114">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="b8e07-255">条件</span><span class="sxs-lookup"><span data-stu-id="b8e07-255">Conditions</span></span>|<span data-ttu-id="b8e07-256">已配置</span><span class="sxs-lookup"><span data-stu-id="b8e07-256">Configured</span></span>|<span data-ttu-id="b8e07-257">是</span><span class="sxs-lookup"><span data-stu-id="b8e07-257">Yes</span></span>|<span data-ttu-id="b8e07-258">配置客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="b8e07-258">Configure Client apps</span></span>|
|<span data-ttu-id="b8e07-259">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="b8e07-259">Client apps</span></span>|<span data-ttu-id="b8e07-260">已配置</span><span class="sxs-lookup"><span data-stu-id="b8e07-260">Configured</span></span>|<span data-ttu-id="b8e07-261">是</span><span class="sxs-lookup"><span data-stu-id="b8e07-261">Yes</span></span>|<span data-ttu-id="b8e07-262">移动应用程序和桌面客户端，其他客户端 （选择两者）</span><span class="sxs-lookup"><span data-stu-id="b8e07-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="b8e07-263">访问控制</span><span class="sxs-lookup"><span data-stu-id="b8e07-263">**Access controls**</span></span>

|<span data-ttu-id="b8e07-264">类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-264">Type</span></span>|<span data-ttu-id="b8e07-265">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-265">Properties</span></span>|<span data-ttu-id="b8e07-266">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-266">Values</span></span>|<span data-ttu-id="b8e07-267">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b8e07-268">授予</span><span class="sxs-lookup"><span data-stu-id="b8e07-268">Grant</span></span>|<span data-ttu-id="b8e07-269">阻止访问</span><span class="sxs-lookup"><span data-stu-id="b8e07-269">Block access</span></span>|<span data-ttu-id="b8e07-270">True</span><span class="sxs-lookup"><span data-stu-id="b8e07-270">True</span></span>|<span data-ttu-id="b8e07-271">已选择</span><span class="sxs-lookup"><span data-stu-id="b8e07-271">Selected</span></span>|
||<span data-ttu-id="b8e07-272">需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="b8e07-272">Require MFA</span></span>|<span data-ttu-id="b8e07-273">False</span><span class="sxs-lookup"><span data-stu-id="b8e07-273">False</span></span>||
||<span data-ttu-id="b8e07-274">需要标记为兼容的设备</span><span class="sxs-lookup"><span data-stu-id="b8e07-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="b8e07-275">False</span><span class="sxs-lookup"><span data-stu-id="b8e07-275">False</span></span>||
||<span data-ttu-id="b8e07-276">需要混合 Azure AD 联接的设备</span><span class="sxs-lookup"><span data-stu-id="b8e07-276">Require Hybrid Azure AD joined device</span></span>|<span data-ttu-id="b8e07-277">False</span><span class="sxs-lookup"><span data-stu-id="b8e07-277">False</span></span>||
||<span data-ttu-id="b8e07-278">需要批准的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="b8e07-278">Require approved client app</span></span>|<span data-ttu-id="b8e07-279">False</span><span class="sxs-lookup"><span data-stu-id="b8e07-279">False</span></span>||
||<span data-ttu-id="b8e07-280">需要所有已选控件</span><span class="sxs-lookup"><span data-stu-id="b8e07-280">Require all the selected controls</span></span>|<span data-ttu-id="b8e07-281">True</span><span class="sxs-lookup"><span data-stu-id="b8e07-281">True</span></span>|<span data-ttu-id="b8e07-282">已选择</span><span class="sxs-lookup"><span data-stu-id="b8e07-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="b8e07-p115">一定要启用此策略，通过**单击**。此外考虑[如果](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具用于测试策略</span><span class="sxs-lookup"><span data-stu-id="b8e07-p115">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="b8e07-285">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="b8e07-285">High risk users must change password</span></span>
<span data-ttu-id="b8e07-286">为了确保在登录时对受侵害的所有高风险用户帐户强制执行密码更改，必须应用下列策略。</span><span class="sxs-lookup"><span data-stu-id="b8e07-286">To ensure that all high-risk users compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="b8e07-287">登录到[Microsoft Azure 门户 (http://portal.azure.com)](http://portal.azure.com/)使用管理员凭据，然后导航到**Azure AD 身份防护 > 用户风险策略**。</span><span class="sxs-lookup"><span data-stu-id="b8e07-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="b8e07-288">分配</span><span class="sxs-lookup"><span data-stu-id="b8e07-288">**Assignments**</span></span>

|<span data-ttu-id="b8e07-289">类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-289">Type</span></span>|<span data-ttu-id="b8e07-290">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-290">Properties</span></span>|<span data-ttu-id="b8e07-291">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-291">Values</span></span>|<span data-ttu-id="b8e07-292">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b8e07-293">Users</span><span class="sxs-lookup"><span data-stu-id="b8e07-293">Users</span></span>|<span data-ttu-id="b8e07-294">包括</span><span class="sxs-lookup"><span data-stu-id="b8e07-294">Include</span></span>|<span data-ttu-id="b8e07-295">所有用户</span><span class="sxs-lookup"><span data-stu-id="b8e07-295">All users</span></span>|<span data-ttu-id="b8e07-296">已选择</span><span class="sxs-lookup"><span data-stu-id="b8e07-296">Selected</span></span>|
||<span data-ttu-id="b8e07-297">排除</span><span class="sxs-lookup"><span data-stu-id="b8e07-297">Exclude</span></span>|<span data-ttu-id="b8e07-298">无</span><span class="sxs-lookup"><span data-stu-id="b8e07-298">None</span></span>||
|<span data-ttu-id="b8e07-299">条件</span><span class="sxs-lookup"><span data-stu-id="b8e07-299">Conditions</span></span>|<span data-ttu-id="b8e07-300">用户风险</span><span class="sxs-lookup"><span data-stu-id="b8e07-300">User risk</span></span>|<span data-ttu-id="b8e07-301">高</span><span class="sxs-lookup"><span data-stu-id="b8e07-301">High</span></span>|<span data-ttu-id="b8e07-302">已选择</span><span class="sxs-lookup"><span data-stu-id="b8e07-302">Selected</span></span>|

<span data-ttu-id="b8e07-303">控制</span><span class="sxs-lookup"><span data-stu-id="b8e07-303">**Controls**</span></span>

| <span data-ttu-id="b8e07-304">类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-304">Type</span></span> | <span data-ttu-id="b8e07-305">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-305">Properties</span></span> | <span data-ttu-id="b8e07-306">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-306">Values</span></span>                  | <span data-ttu-id="b8e07-307">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="b8e07-308">访问</span><span class="sxs-lookup"><span data-stu-id="b8e07-308">Access</span></span>     | <span data-ttu-id="b8e07-309">允许访问</span><span class="sxs-lookup"><span data-stu-id="b8e07-309">Allow access</span></span>            | <span data-ttu-id="b8e07-310">True</span><span class="sxs-lookup"><span data-stu-id="b8e07-310">True</span></span>  |
|      | <span data-ttu-id="b8e07-311">访问</span><span class="sxs-lookup"><span data-stu-id="b8e07-311">Access</span></span>     | <span data-ttu-id="b8e07-312">需要更改密码</span><span class="sxs-lookup"><span data-stu-id="b8e07-312">Require password change</span></span> | <span data-ttu-id="b8e07-313">True</span><span class="sxs-lookup"><span data-stu-id="b8e07-313">True</span></span>  |

<span data-ttu-id="b8e07-314">**审阅：** 不适用</span><span class="sxs-lookup"><span data-stu-id="b8e07-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="b8e07-p116">一定要启用此策略，通过**单击**。此外考虑[如果](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具用于测试策略</span><span class="sxs-lookup"><span data-stu-id="b8e07-p116">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="b8e07-317">定义应用程序保护策略</span><span class="sxs-lookup"><span data-stu-id="b8e07-317">Define app protection policies</span></span>
<span data-ttu-id="b8e07-p117">应用程序保护策略定义允许的应用程序并他们与您组织的数据可以执行的操作。创建 Intune 应用程序中的 Azure 门户从保护策略。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p117">App protection policies define which apps are allowed and the actions they can take with your organization data. Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="b8e07-320">创建每个平台的策略：</span><span class="sxs-lookup"><span data-stu-id="b8e07-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="b8e07-321">iOS</span><span class="sxs-lookup"><span data-stu-id="b8e07-321">iOS</span></span>
- <span data-ttu-id="b8e07-322">Android</span><span class="sxs-lookup"><span data-stu-id="b8e07-322">Android</span></span>
- <span data-ttu-id="b8e07-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b8e07-323">Windows 10</span></span>

<span data-ttu-id="b8e07-p118">若要创建新的应用程序保护策略，登录到您的管理凭据的 Microsoft Azure 门户，然后导航到**移动应用程序 > 应用程序保护策略**。单击**添加策略**。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p118">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**. Click **Add a policy**.</span></span>

<span data-ttu-id="b8e07-p119">有微小的差异的应用程序保护 iOS 和 Android 之间的策略选项。以下策略是专用于 Android。使用此指南作为在其他策略。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p119">There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android. Use this as a guide for your other policies.</span></span>

<span data-ttu-id="b8e07-329">推荐的应用程序列表包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="b8e07-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="b8e07-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b8e07-330">PowerPoint</span></span>
- <span data-ttu-id="b8e07-331">Excel</span><span class="sxs-lookup"><span data-stu-id="b8e07-331">Excel</span></span>
- <span data-ttu-id="b8e07-332">Word</span><span class="sxs-lookup"><span data-stu-id="b8e07-332">Word</span></span>
- <span data-ttu-id="b8e07-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8e07-333">Microsoft Teams</span></span>
- <span data-ttu-id="b8e07-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="b8e07-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="b8e07-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="b8e07-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="b8e07-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="b8e07-336">OneDrive</span></span>
- <span data-ttu-id="b8e07-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="b8e07-337">OneNote</span></span>
- <span data-ttu-id="b8e07-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="b8e07-338">Outlook</span></span>

<span data-ttu-id="b8e07-339">下表介绍建议的设置：</span><span class="sxs-lookup"><span data-stu-id="b8e07-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="b8e07-340">类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-340">Type</span></span>|<span data-ttu-id="b8e07-341">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-341">Properties</span></span>|<span data-ttu-id="b8e07-342">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-342">Values</span></span>|<span data-ttu-id="b8e07-343">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b8e07-344">数据重定位</span><span class="sxs-lookup"><span data-stu-id="b8e07-344">Data relocation</span></span>|<span data-ttu-id="b8e07-345">阻止 Android 备份</span><span class="sxs-lookup"><span data-stu-id="b8e07-345">Prevent Android backup</span></span>|<span data-ttu-id="b8e07-346">是</span><span class="sxs-lookup"><span data-stu-id="b8e07-346">Yes</span></span>|<span data-ttu-id="b8e07-347">在 iOS 上，这会专门调用 iTunes 和 iCloud</span><span class="sxs-lookup"><span data-stu-id="b8e07-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="b8e07-348">允许应用向其他应用传送数据</span><span class="sxs-lookup"><span data-stu-id="b8e07-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="b8e07-349">策略托管应用</span><span class="sxs-lookup"><span data-stu-id="b8e07-349">Policy managed apps</span></span>||
||<span data-ttu-id="b8e07-350">允许应用从其他应用接收数据</span><span class="sxs-lookup"><span data-stu-id="b8e07-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="b8e07-351">策略托管应用</span><span class="sxs-lookup"><span data-stu-id="b8e07-351">Policy managed apps</span></span>||
||<span data-ttu-id="b8e07-352">防止“另存为”</span><span class="sxs-lookup"><span data-stu-id="b8e07-352">Prevent "Save As"</span></span>|<span data-ttu-id="b8e07-353">是</span><span class="sxs-lookup"><span data-stu-id="b8e07-353">Yes</span></span>||
||<span data-ttu-id="b8e07-354">选择企业数据可保存到其中的存储服务</span><span class="sxs-lookup"><span data-stu-id="b8e07-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="b8e07-355">OneDrive for Business，SharePoint</span><span class="sxs-lookup"><span data-stu-id="b8e07-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="b8e07-356">限制使用其他应用剪切、复制和粘贴</span><span class="sxs-lookup"><span data-stu-id="b8e07-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="b8e07-357">与粘贴中的策略托管应用程序</span><span class="sxs-lookup"><span data-stu-id="b8e07-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="b8e07-358">限制显示在托管浏览器内的 Web 内容</span><span class="sxs-lookup"><span data-stu-id="b8e07-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="b8e07-359">否</span><span class="sxs-lookup"><span data-stu-id="b8e07-359">No</span></span>||
||<span data-ttu-id="b8e07-360">加密应用数据</span><span class="sxs-lookup"><span data-stu-id="b8e07-360">Encrypt app data</span></span>|<span data-ttu-id="b8e07-361">是</span><span class="sxs-lookup"><span data-stu-id="b8e07-361">Yes</span></span>|<span data-ttu-id="b8e07-362">在 iOS 上，选择选项：“锁定设备时”</span><span class="sxs-lookup"><span data-stu-id="b8e07-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="b8e07-363">启用设备时禁用应用程序加密</span><span class="sxs-lookup"><span data-stu-id="b8e07-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="b8e07-364">是</span><span class="sxs-lookup"><span data-stu-id="b8e07-364">Yes</span></span>|<span data-ttu-id="b8e07-365">禁用此设置，以避免双加密</span><span class="sxs-lookup"><span data-stu-id="b8e07-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="b8e07-366">禁用联系人同步</span><span class="sxs-lookup"><span data-stu-id="b8e07-366">Disable contacts sync</span></span>|<span data-ttu-id="b8e07-367">否</span><span class="sxs-lookup"><span data-stu-id="b8e07-367">No</span></span>||
||<span data-ttu-id="b8e07-368">禁用打印</span><span class="sxs-lookup"><span data-stu-id="b8e07-368">Disable printing</span></span>|<span data-ttu-id="b8e07-369">否</span><span class="sxs-lookup"><span data-stu-id="b8e07-369">No</span></span>||
|<span data-ttu-id="b8e07-370">访问</span><span class="sxs-lookup"><span data-stu-id="b8e07-370">Access</span></span>|<span data-ttu-id="b8e07-371">访问需要 PIN</span><span class="sxs-lookup"><span data-stu-id="b8e07-371">Require PIN for access</span></span>|<span data-ttu-id="b8e07-372">是</span><span class="sxs-lookup"><span data-stu-id="b8e07-372">Yes</span></span>||
||<span data-ttu-id="b8e07-373">选择类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-373">Select Type</span></span>|<span data-ttu-id="b8e07-374">数字</span><span class="sxs-lookup"><span data-stu-id="b8e07-374">Numeric</span></span>||
||<span data-ttu-id="b8e07-375">允许使用简单 PIN</span><span class="sxs-lookup"><span data-stu-id="b8e07-375">Allow simple PIN</span></span>|<span data-ttu-id="b8e07-376">否</span><span class="sxs-lookup"><span data-stu-id="b8e07-376">No</span></span>||
||<span data-ttu-id="b8e07-377">PIN 长度</span><span class="sxs-lookup"><span data-stu-id="b8e07-377">PIN length</span></span>|<span data-ttu-id="b8e07-378">6 </span><span class="sxs-lookup"><span data-stu-id="b8e07-378">6</span></span>||
||<span data-ttu-id="b8e07-379">允许使用指纹而不是 PIN</span><span class="sxs-lookup"><span data-stu-id="b8e07-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="b8e07-380">是</span><span class="sxs-lookup"><span data-stu-id="b8e07-380">Yes</span></span>||
||<span data-ttu-id="b8e07-381">管理设备 PIN 时禁用应用程序 PIN</span><span class="sxs-lookup"><span data-stu-id="b8e07-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="b8e07-382">是</span><span class="sxs-lookup"><span data-stu-id="b8e07-382">Yes</span></span>||
||<span data-ttu-id="b8e07-383">需要访问企业凭据</span><span class="sxs-lookup"><span data-stu-id="b8e07-383">Require corporate credentials for access</span></span>|<span data-ttu-id="b8e07-384">否</span><span class="sxs-lookup"><span data-stu-id="b8e07-384">No</span></span>||
||<span data-ttu-id="b8e07-385">在一定时间后重新检查访问要求(分钟)</span><span class="sxs-lookup"><span data-stu-id="b8e07-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="b8e07-386">30</span><span class="sxs-lookup"><span data-stu-id="b8e07-386">30</span></span>||
||<span data-ttu-id="b8e07-387">阻止屏幕捕获和 Android 助手</span><span class="sxs-lookup"><span data-stu-id="b8e07-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="b8e07-388">否</span><span class="sxs-lookup"><span data-stu-id="b8e07-388">No</span></span>|<span data-ttu-id="b8e07-389">在 iOS 上，此选项不可用</span><span class="sxs-lookup"><span data-stu-id="b8e07-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="b8e07-390">登录安全要求</span><span class="sxs-lookup"><span data-stu-id="b8e07-390">Sign-in security requirements</span></span>|<span data-ttu-id="b8e07-391">最大 PIN 尝试</span><span class="sxs-lookup"><span data-stu-id="b8e07-391">Max PIN attempts</span></span>|<span data-ttu-id="b8e07-392">5 </span><span class="sxs-lookup"><span data-stu-id="b8e07-392">5</span></span>|<span data-ttu-id="b8e07-393">重置 Pin</span><span class="sxs-lookup"><span data-stu-id="b8e07-393">Reset Pin</span></span>|
||<span data-ttu-id="b8e07-394">离线宽限期</span><span class="sxs-lookup"><span data-stu-id="b8e07-394">Offline grace period</span></span>|<span data-ttu-id="b8e07-395">720</span><span class="sxs-lookup"><span data-stu-id="b8e07-395">720</span></span>|<span data-ttu-id="b8e07-396">阻止访问</span><span class="sxs-lookup"><span data-stu-id="b8e07-396">Block access</span></span>|
||<span data-ttu-id="b8e07-397">擦除应用数据之前的脱机间隔时间（天）</span><span class="sxs-lookup"><span data-stu-id="b8e07-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="b8e07-398">90</span><span class="sxs-lookup"><span data-stu-id="b8e07-398">90</span></span>|<span data-ttu-id="b8e07-399">擦除数据</span><span class="sxs-lookup"><span data-stu-id="b8e07-399">Wipe data</span></span>|
||<span data-ttu-id="b8e07-400">根 Jailbroken/设备</span><span class="sxs-lookup"><span data-stu-id="b8e07-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="b8e07-401">擦除数据</span><span class="sxs-lookup"><span data-stu-id="b8e07-401">Wipe data</span></span>|

<span data-ttu-id="b8e07-p120">完成后，请记住单击“创建”。 重复上述步骤，并将所选平台（下拉列表）替换为 iOS。 这可创建两个应用策略，因此请在创建策略后将组分配到策略，并进行部署。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p120">When complete, remember to click "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="b8e07-405">若要编辑策略并将这些策略分配给用户，请参阅[如何创建和分配应用程序保护策略](https://docs.microsoft.com/intune/app-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="b8e07-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="b8e07-406">需要已批准应用程序</span><span class="sxs-lookup"><span data-stu-id="b8e07-406">Require approved apps</span></span>
<span data-ttu-id="b8e07-407">若要要求已批准应用程序：</span><span class="sxs-lookup"><span data-stu-id="b8e07-407">To require approved apps:</span></span>

1. <span data-ttu-id="b8e07-p121">转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，会看到 Azure 仪表板。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p121">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="b8e07-410">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="b8e07-411">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="b8e07-412">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="b8e07-413">输入策略名称，然后选择要应用策略的“用户和组”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="b8e07-414">选择“云应用”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="b8e07-p122">选择**选择应用程序**，从**云应用程序**列表中选择所需的应用程序。例如，选择 Office 365 Exchange Online。单击**选择**并**完成**。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p122">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="b8e07-418">从“访问控制”部分选择“授予”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="b8e07-p123">选择**授予访问**，选择**需要批准客户端应用程序**。 为多个控件中，选择**需要选定的控件**，然后选择**选择**。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p123">Choose **Grant access**, select **Require approved client app**.  For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="b8e07-421">单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8e07-421">Click **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="b8e07-422">定义设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="b8e07-422">Define device compliance policies</span></span>

<span data-ttu-id="b8e07-p124">设备合规性策略定义的设备必须遵守才能被标记为兼容的要求。创建 Intune 设备从 Azure 门户中的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p124">Device compliance policies define the requirements that devices must adhere to in order to be marked as compliant. Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="b8e07-425">创建每个平台的策略：</span><span class="sxs-lookup"><span data-stu-id="b8e07-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="b8e07-426">Android</span><span class="sxs-lookup"><span data-stu-id="b8e07-426">Android</span></span>
- <span data-ttu-id="b8e07-427">Android 企业</span><span class="sxs-lookup"><span data-stu-id="b8e07-427">Android enterprise</span></span>
- <span data-ttu-id="b8e07-428">iOS</span><span class="sxs-lookup"><span data-stu-id="b8e07-428">iOS</span></span>
- <span data-ttu-id="b8e07-429">macOS</span><span class="sxs-lookup"><span data-stu-id="b8e07-429">macOS</span></span>
- <span data-ttu-id="b8e07-430">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="b8e07-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="b8e07-431">Windows 8.1 及更高版本</span><span class="sxs-lookup"><span data-stu-id="b8e07-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="b8e07-432">Windows 10 及更高版本</span><span class="sxs-lookup"><span data-stu-id="b8e07-432">Windows 10 and later</span></span>

<span data-ttu-id="b8e07-p125">若要创建设备合规性策略，登录到您的管理凭据的 Microsoft Azure 门户，然后导航到**Intune > 设备合规性**。单击**创建策略**。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p125">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**. Click **Create policy**.</span></span>

<span data-ttu-id="b8e07-435">为 Windows 10 建议使用下列设置。</span><span class="sxs-lookup"><span data-stu-id="b8e07-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="b8e07-436">**设备运行状况： Windows 运行状况审计服务求值规则**</span><span class="sxs-lookup"><span data-stu-id="b8e07-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="b8e07-437">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-437">Properties</span></span>|<span data-ttu-id="b8e07-438">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-438">Values</span></span>|<span data-ttu-id="b8e07-439">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="b8e07-440">需要 BitLocker</span><span class="sxs-lookup"><span data-stu-id="b8e07-440">Require BitLocker</span></span>|<span data-ttu-id="b8e07-441">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-441">Require</span></span>||
|<span data-ttu-id="b8e07-442">需要安全引导设备上启用</span><span class="sxs-lookup"><span data-stu-id="b8e07-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="b8e07-443">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-443">Require</span></span>||
|<span data-ttu-id="b8e07-444">需要代码完整性</span><span class="sxs-lookup"><span data-stu-id="b8e07-444">Require code integrity</span></span>|<span data-ttu-id="b8e07-445">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-445">Require</span></span>||


<span data-ttu-id="b8e07-446">设备属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-446">**Device properties**</span></span>

|<span data-ttu-id="b8e07-447">类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-447">Type</span></span>|<span data-ttu-id="b8e07-448">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-448">Properties</span></span>|<span data-ttu-id="b8e07-449">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-449">Values</span></span>|<span data-ttu-id="b8e07-450">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b8e07-451">操作系统版本</span><span class="sxs-lookup"><span data-stu-id="b8e07-451">Operating system version</span></span>|<span data-ttu-id="b8e07-452">全部</span><span class="sxs-lookup"><span data-stu-id="b8e07-452">All</span></span>|<span data-ttu-id="b8e07-453">未配置</span><span class="sxs-lookup"><span data-stu-id="b8e07-453">Not configured</span></span>||

<span data-ttu-id="b8e07-p126">要将上述所有策略视为已部署，这些策略必须面向用户组。 要完成此操作，可以创建策略（在“保存”上），或稍后在“策略”部分（与“添加”在同一级别）中选择“管理部署”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p126">For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting Manage Deployment in the Policy section (same level as Add).</span></span>

<span data-ttu-id="b8e07-456">系统安全</span><span class="sxs-lookup"><span data-stu-id="b8e07-456">**System security**</span></span>

|<span data-ttu-id="b8e07-457">类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-457">Type</span></span>|<span data-ttu-id="b8e07-458">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-458">Properties</span></span>|<span data-ttu-id="b8e07-459">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-459">Values</span></span>|<span data-ttu-id="b8e07-460">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b8e07-461">密码</span><span class="sxs-lookup"><span data-stu-id="b8e07-461">Password</span></span>|<span data-ttu-id="b8e07-462">需要密码以解锁移动设备</span><span class="sxs-lookup"><span data-stu-id="b8e07-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="b8e07-463">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-463">Require</span></span>||
||<span data-ttu-id="b8e07-464">简单密码</span><span class="sxs-lookup"><span data-stu-id="b8e07-464">Simple passwords</span></span>|<span data-ttu-id="b8e07-465">阻止</span><span class="sxs-lookup"><span data-stu-id="b8e07-465">Block</span></span>||
||<span data-ttu-id="b8e07-466">密码类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-466">Password type</span></span>|<span data-ttu-id="b8e07-467">默认设备</span><span class="sxs-lookup"><span data-stu-id="b8e07-467">Device default</span></span>||
||<span data-ttu-id="b8e07-468">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="b8e07-468">Minimum password length</span></span>|<span data-ttu-id="b8e07-469">6 </span><span class="sxs-lookup"><span data-stu-id="b8e07-469">6</span></span>||
||<span data-ttu-id="b8e07-470">最大分钟无活动需要密码之前</span><span class="sxs-lookup"><span data-stu-id="b8e07-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="b8e07-471">15 </span><span class="sxs-lookup"><span data-stu-id="b8e07-471">15</span></span>|<span data-ttu-id="b8e07-p127">此设置支持 Android 版本 4.0 和上方或 KNOX 4.0 及以上。对于 iOS 设备，支持适用于 iOS 8.0 和上方。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p127">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above. For iOS devices, it’s supported for iOS 8.0 and above.</span></span>|
||<span data-ttu-id="b8e07-474">密码过期(天)</span><span class="sxs-lookup"><span data-stu-id="b8e07-474">Password expiration (days)</span></span>|<span data-ttu-id="b8e07-475">41</span><span class="sxs-lookup"><span data-stu-id="b8e07-475">41</span></span>||
||<span data-ttu-id="b8e07-476">以前的密码，以防止重复使用的数量</span><span class="sxs-lookup"><span data-stu-id="b8e07-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="b8e07-477">5 </span><span class="sxs-lookup"><span data-stu-id="b8e07-477">5</span></span>||
||<span data-ttu-id="b8e07-478">从空闲状态 （Mobile 和全息） 返回设备时需要密码</span><span class="sxs-lookup"><span data-stu-id="b8e07-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="b8e07-479">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-479">Require</span></span>|<span data-ttu-id="b8e07-480">适用于 Windows 10 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="b8e07-480">Available for Windows 10 and later.</span></span>|
|<span data-ttu-id="b8e07-481">加密</span><span class="sxs-lookup"><span data-stu-id="b8e07-481">Encryption</span></span>|<span data-ttu-id="b8e07-482">在设备上的数据存储的加密</span><span class="sxs-lookup"><span data-stu-id="b8e07-482">Encryption of data storage on device</span></span>|<span data-ttu-id="b8e07-483">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-483">Require</span></span>||
|<span data-ttu-id="b8e07-484">设备安全</span><span class="sxs-lookup"><span data-stu-id="b8e07-484">Device Security</span></span>|<span data-ttu-id="b8e07-485">防火墙</span><span class="sxs-lookup"><span data-stu-id="b8e07-485">Firewall</span></span>|<span data-ttu-id="b8e07-486">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-486">Require</span></span>||
||<span data-ttu-id="b8e07-487">防病毒</span><span class="sxs-lookup"><span data-stu-id="b8e07-487">Antivirus</span></span>|<span data-ttu-id="b8e07-488">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-488">Require</span></span>||
||<span data-ttu-id="b8e07-489">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="b8e07-489">Antispyware</span></span>|<span data-ttu-id="b8e07-490">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-490">Require</span></span>|<span data-ttu-id="b8e07-491">此设置要求注册 Windows 安全中心反间谍软件解决方案。</span><span class="sxs-lookup"><span data-stu-id="b8e07-491">This setting requires an Anti-Spyware solution registered with Windows Security Center.</span></span>|
|<span data-ttu-id="b8e07-492">Defender</span><span class="sxs-lookup"><span data-stu-id="b8e07-492">Defender</span></span>|<span data-ttu-id="b8e07-493">Windows Defender 反恶意软件</span><span class="sxs-lookup"><span data-stu-id="b8e07-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="b8e07-494">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-494">Require</span></span>||
||<span data-ttu-id="b8e07-495">Windows Defender 反恶意软件的最低版本</span><span class="sxs-lookup"><span data-stu-id="b8e07-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="b8e07-p128">仅支持 Windows 10 桌面。Microsoft 建议版本不超过 5 后面从最新版本。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p128">Only supported for Windows 10 desktop. Microsoft recommends versions no more than five behind from the most recent version.</span></span>|
||<span data-ttu-id="b8e07-498">最新的 Windows Defender 反恶意软件签名</span><span class="sxs-lookup"><span data-stu-id="b8e07-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="b8e07-499">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-499">Require</span></span>||
||<span data-ttu-id="b8e07-500">“实时保护”</span><span class="sxs-lookup"><span data-stu-id="b8e07-500">Real-time protection</span></span>|<span data-ttu-id="b8e07-501">需要</span><span class="sxs-lookup"><span data-stu-id="b8e07-501">Require</span></span>|<span data-ttu-id="b8e07-502">仅支持 Windows 10 桌面。</span><span class="sxs-lookup"><span data-stu-id="b8e07-502">Only supported for Windows 10 desktop.</span></span>|

<span data-ttu-id="b8e07-503">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="b8e07-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="b8e07-504">类型</span><span class="sxs-lookup"><span data-stu-id="b8e07-504">Type</span></span>|<span data-ttu-id="b8e07-505">属性</span><span class="sxs-lookup"><span data-stu-id="b8e07-505">Properties</span></span>|<span data-ttu-id="b8e07-506">值</span><span class="sxs-lookup"><span data-stu-id="b8e07-506">Values</span></span>|<span data-ttu-id="b8e07-507">注释</span><span class="sxs-lookup"><span data-stu-id="b8e07-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b8e07-508">Windows Defender 高级威胁保护规则</span><span class="sxs-lookup"><span data-stu-id="b8e07-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="b8e07-509">需要为在或下的计算机风险分数的设备</span><span class="sxs-lookup"><span data-stu-id="b8e07-509">Require the device to be at or under the machine risk score</span></span>|<span data-ttu-id="b8e07-510">中等</span><span class="sxs-lookup"><span data-stu-id="b8e07-510">Medium</span></span>||





## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="b8e07-511">需要符合 Pc （但不是符合标准的电话和平板电脑）</span><span class="sxs-lookup"><span data-stu-id="b8e07-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="b8e07-p129">添加之前需要符合 Pc 的策略，请务必注册到 Intune 的管理设备。注册到 Intune 的设备的设备包含在预期的用户所拥有的保证之前，建议使用多因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p129">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="b8e07-514">需要符合 Pc:</span><span class="sxs-lookup"><span data-stu-id="b8e07-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="b8e07-p130">转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，会看到 Azure 仪表板。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p130">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="b8e07-517">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="b8e07-518">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="b8e07-519">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="b8e07-520">输入策略名称，然后选择要应用策略的“用户和组”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="b8e07-521">选择“云应用”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="b8e07-p131">选择**选择应用程序**，从**云应用程序**列表中选择所需的应用程序。例如，选择 Office 365 Exchange Online。单击**选择**并**完成**。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p131">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="b8e07-p132">如果需要符合 Pc，但不是符合手机和平板电脑，请选择**条件**和**设备平台**。选择"选择设备平台"并选择**Windows**和**macOS**。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p132">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**. Choose "Select device platforms" and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="b8e07-527">从“访问控制”部分选择“授予”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="b8e07-p133">选择**授予访问**，选择**需要标记为兼容的设备**。 为多个控件中，选择**需要所有选定的控件**，然后选择**选择**。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p133">Choose **Grant access**, select **Require device to be marked as compliant**.  For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="b8e07-530">单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8e07-530">Click **Create**.</span></span>

<span data-ttu-id="b8e07-p134">如果您的目标是需要兼容的 Pc*和*移动设备，则不要选择平台。强制执行兼容的所有设备。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p134">If your objective is to require compliant PCs *and* mobile devices, do not select platforms. This enforces compliant for all devices.</span></span> 




## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="b8e07-533">需要符合标准的 Pc*和*移动设备</span><span class="sxs-lookup"><span data-stu-id="b8e07-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="b8e07-534">若要为所有设备要求合规性：</span><span class="sxs-lookup"><span data-stu-id="b8e07-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="b8e07-p135">转到 [Azure 门户](https://portal.azure.com)，然后使用你的凭据登录。 成功登录后，会看到 Azure 仪表板。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p135">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="b8e07-537">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="b8e07-538">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="b8e07-539">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="b8e07-540">输入策略名称，然后选择要应用策略的“用户和组”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="b8e07-541">选择“云应用”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="b8e07-p136">选择**选择应用程序**，从**云应用程序**列表中选择所需的应用程序。例如，选择 Office 365 Exchange Online。单击**选择**并**完成**。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p136">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="b8e07-545">从“访问控制”部分选择“授予”。</span><span class="sxs-lookup"><span data-stu-id="b8e07-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="b8e07-p137">选择**授予访问**，选择**需要标记为兼容的设备**。为多个控件中，选择**需要所有选定的控件**，然后选择**选择**。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p137">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="b8e07-548">单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8e07-548">Click **Create**.</span></span>

<span data-ttu-id="b8e07-p138">在创建此策略时，不要选中平台。这将强制兼容的设备。</span><span class="sxs-lookup"><span data-stu-id="b8e07-p138">When creating this policy, do not select platforms. This enforces compliant devices.</span></span>















<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a><span data-ttu-id="b8e07-551">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b8e07-551">Next steps</span></span>

[<span data-ttu-id="b8e07-552">了解有关用于保护电子邮件的策略建议</span><span class="sxs-lookup"><span data-stu-id="b8e07-552">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
