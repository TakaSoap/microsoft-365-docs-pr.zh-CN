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
ms.openlocfilehash: ab8454c27cd57b6bd5cc8df6e1526ee2950ac998
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866034"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="2391a-103">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="2391a-103">Common identity and device access policies</span></span>
<span data-ttu-id="2391a-104">本文介绍推荐用于保护权云服务的策略的共同包括本地应用程序发布与 Azure AD 应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="2391a-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="2391a-p101">本指南讨论了如何部署新设置环境中的建议的策略。在单独的实验室环境中的这些策略设置允许您了解和暂存向您的预生产和生产环境推出之前进行评估的建议的策略。新设置的环境可能仅限于云或混合。</span><span class="sxs-lookup"><span data-stu-id="2391a-p101">This guidance discusses how to deploy the recommended policies in a newly-provisioned environment. Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your preproduction and production environments. Your newly provisioned environment may be cloud-only or hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="2391a-108">策略设置</span><span class="sxs-lookup"><span data-stu-id="2391a-108">Policy set</span></span> 

<span data-ttu-id="2391a-p102">下图说明了推荐的策略集。它显示哪一层保护措施适用于每个策略和策略是否适用于 Pc 或电话和平板电脑或设备这两个类别。它还指示配置了这些策略。</span><span class="sxs-lookup"><span data-stu-id="2391a-p102">The following diagram illustrates the recommended set of policies. It shows which tier of protections each policy applies to and whether the policies apply to PCs or phones and tablets, or both categories of devices. It also indicates where these policies are configured.</span></span>

![常见配置标识和设备访问的策略](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="2391a-113">本文的其余部分介绍如何配置这些策略。</span><span class="sxs-lookup"><span data-stu-id="2391a-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="2391a-p103">注册到 Intune 的设备的设备包含在预期的用户所拥有的保证之前，建议使用多因素身份验证。此外必须注册到 Intune 强制实施设备合规性策略之前设备。</span><span class="sxs-lookup"><span data-stu-id="2391a-p103">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user. You must also enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="2391a-p104">要授予时间来完成这些任务，我们建议此表中列出的顺序实现基准策略。但是，在任何时候都可以实现敏感和高管控保护的 MFA 策略。</span><span class="sxs-lookup"><span data-stu-id="2391a-p104">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table. However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="2391a-118">保护级别</span><span class="sxs-lookup"><span data-stu-id="2391a-118">Protection level</span></span>|<span data-ttu-id="2391a-119">Policies</span><span class="sxs-lookup"><span data-stu-id="2391a-119">Policies</span></span>|<span data-ttu-id="2391a-120">更多信息</span><span class="sxs-lookup"><span data-stu-id="2391a-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="2391a-121">**基线**</span><span class="sxs-lookup"><span data-stu-id="2391a-121">**Baseline**</span></span>|[<span data-ttu-id="2391a-122">*中等*或*高*风险登录时需要 MFA</span><span class="sxs-lookup"><span data-stu-id="2391a-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="2391a-123">阻止客户端不支持现代身份验证</span><span class="sxs-lookup"><span data-stu-id="2391a-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="2391a-124">因此，很重要阻止这些，不使用现代的身份验证的客户端可以跳过条件访问规则，</span><span class="sxs-lookup"><span data-stu-id="2391a-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these</span></span>|
|        |[<span data-ttu-id="2391a-125">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="2391a-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="2391a-126">强制用户如果高风险活动检测到其帐户在登录后更改其密码</span><span class="sxs-lookup"><span data-stu-id="2391a-126">Forces users to change their password when signing in if high-risk activity is detected for their account</span></span>|
|        |[<span data-ttu-id="2391a-127">定义应用程序保护策略</span><span class="sxs-lookup"><span data-stu-id="2391a-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="2391a-128">每个平台 (iOS，Android、 Windows) 的一个策略。</span><span class="sxs-lookup"><span data-stu-id="2391a-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="2391a-129">需要已批准应用程序</span><span class="sxs-lookup"><span data-stu-id="2391a-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="2391a-130">强制移动应用程序保护手机和平板电脑</span><span class="sxs-lookup"><span data-stu-id="2391a-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="2391a-131">定义设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="2391a-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="2391a-132">每个平台的的一个策略</span><span class="sxs-lookup"><span data-stu-id="2391a-132">One policy for each platform</span></span>|
|        |[<span data-ttu-id="2391a-133">需要符合标准的 Pc</span><span class="sxs-lookup"><span data-stu-id="2391a-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="2391a-134">强制实施 Pc Intune 的管理</span><span class="sxs-lookup"><span data-stu-id="2391a-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="2391a-135">**敏感**</span><span class="sxs-lookup"><span data-stu-id="2391a-135">**Sensitive**</span></span>|[<span data-ttu-id="2391a-136">*低*、*中*或*高*风险登录时需要 MFA</span><span class="sxs-lookup"><span data-stu-id="2391a-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="2391a-137">需要符合标准的 Pc*和*移动设备</span><span class="sxs-lookup"><span data-stu-id="2391a-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="2391a-138">强制实施 Pc 和平板电脑电话/Intune 的管理</span><span class="sxs-lookup"><span data-stu-id="2391a-138">Enforces Intune management for PCs and phone/tablets</span></span>|
|<span data-ttu-id="2391a-139">**高度管控**</span><span class="sxs-lookup"><span data-stu-id="2391a-139">**Highly regulated**</span></span>|[<span data-ttu-id="2391a-140">*始终*需要 MFA</span><span class="sxs-lookup"><span data-stu-id="2391a-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="2391a-141">向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="2391a-141">Assigning policies to users</span></span>
<span data-ttu-id="2391a-p105">配置策略之前，确定要用于保护每一层的 Azure AD 组。通常，比较基准保护适用于组织中的每个人。包含的比较基准和敏感的保护功能的用户将必须应用的比较基准策略以及敏感的策略。保护累积以及实施最严格策略。</span><span class="sxs-lookup"><span data-stu-id="2391a-p105">Before configuring policies, identify the Azure AD groups you are using for each tier of protection. Typically, baseline protection applies to everybody in the organization. A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies. Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="2391a-p106">建议的做法是创建 Azure AD 组条件访问排除。将该组添加到所有条件访问规则"排除"下。这样，您可以向用户提供访问，而您解决访问问题的方法。这被建议为临时解决方案。监视更改此组，并确保仅适用于正在使用排除组。</span><span class="sxs-lookup"><span data-stu-id="2391a-p106">A recommended practice is to create an Azure AD group for conditional access exclusion. Add this group to all of your conditional access rules under "Exclude". This gives you a method to provide access to a user while you troubleshoot access issues. This is recommended as a temporary solution only. Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="2391a-151">下图提供了用户分配和排除的示例。</span><span class="sxs-lookup"><span data-stu-id="2391a-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![示例用户分配和排除 MFA 规则条件](../images/identity-access-policies-assignment.png)

<span data-ttu-id="2391a-p107">在图 MFA*始终*需要一个条件的访问策略分配"顶部机密项目 X 团队"。应用于用户的更高级别的保护时应谨慎。此项目工作组成员需要提供两种形式的身份验证，每次登录，即使它们不查看高度规范化的内容。</span><span class="sxs-lookup"><span data-stu-id="2391a-p107">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*. Be judicious when applying higher levels of protection to users. Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly-regulated content.</span></span>  

<span data-ttu-id="2391a-p108">创建这些建议的一部分的所有 Azure AD 组必须创建为 Office 365 组。保护 SharePoint Online 中的文档时，这是特别重要部署 Azure 信息保护 (AIP)。</span><span class="sxs-lookup"><span data-stu-id="2391a-p108">All Azure AD groups created as part of these recommendations must be created as Office 365 groups. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![创建 Office 365 组的屏幕截图](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="2391a-159">需要 MFA 根据登录风险</span><span class="sxs-lookup"><span data-stu-id="2391a-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="2391a-p109">需要 MFA 之前, 先使用 Identity 保护 MFA 注册策略注册 MFA 用户。注册用户后，可以强制 MFA 登录。[必备工作](identity-access-prerequisites.md)包括 MFA 中注册的所有用户。</span><span class="sxs-lookup"><span data-stu-id="2391a-p109">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA. After users are registered you can enforce MFA for sign-in. The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="2391a-163">创建新的条件访问策略：</span><span class="sxs-lookup"><span data-stu-id="2391a-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="2391a-p110">转到[Azure 门户](https://portal.azure.com)，并使用您的凭据登录。您已成功登录后，您将看到 Azure 仪表板。</span><span class="sxs-lookup"><span data-stu-id="2391a-p110">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="2391a-166">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="2391a-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="2391a-167">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="2391a-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="2391a-168">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="2391a-168">Choose **New policy**.</span></span>

![基线 CA 策略](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="2391a-170">下表介绍实现此策略的条件的访问策略设置。</span><span class="sxs-lookup"><span data-stu-id="2391a-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="2391a-171">分配</span><span class="sxs-lookup"><span data-stu-id="2391a-171">**Assignments**</span></span>

|<span data-ttu-id="2391a-172">类型</span><span class="sxs-lookup"><span data-stu-id="2391a-172">Type</span></span>|<span data-ttu-id="2391a-173">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-173">Properties</span></span>|<span data-ttu-id="2391a-174">值</span><span class="sxs-lookup"><span data-stu-id="2391a-174">Values</span></span>|<span data-ttu-id="2391a-175">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="2391a-176">用户和组</span><span class="sxs-lookup"><span data-stu-id="2391a-176">Users and groups</span></span>|<span data-ttu-id="2391a-177">包括</span><span class="sxs-lookup"><span data-stu-id="2391a-177">Include</span></span>|<span data-ttu-id="2391a-178">选择用户和组 - 选择包含目标用户的特定安全组</span><span class="sxs-lookup"><span data-stu-id="2391a-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="2391a-179">从包含试点用户的安全组开始</span><span class="sxs-lookup"><span data-stu-id="2391a-179">Start with security group including pilot users</span></span>|
||<span data-ttu-id="2391a-180">排除</span><span class="sxs-lookup"><span data-stu-id="2391a-180">Exclude</span></span>|<span data-ttu-id="2391a-181">例外安全组；服务帐户(应用标识)</span><span class="sxs-lookup"><span data-stu-id="2391a-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="2391a-182">根据需要临时每个修改的成员身份</span><span class="sxs-lookup"><span data-stu-id="2391a-182">Membership modified on an as-needed temporary basis</span></span>|
|<span data-ttu-id="2391a-183">云应用</span><span class="sxs-lookup"><span data-stu-id="2391a-183">Cloud apps</span></span>|<span data-ttu-id="2391a-184">包括</span><span class="sxs-lookup"><span data-stu-id="2391a-184">Include</span></span>|<span data-ttu-id="2391a-p111">选择您希望此规则应用于的应用程序。例如，选择 Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2391a-p111">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="2391a-187">条件</span><span class="sxs-lookup"><span data-stu-id="2391a-187">Conditions</span></span>|<span data-ttu-id="2391a-188">已配置</span><span class="sxs-lookup"><span data-stu-id="2391a-188">Configured</span></span>|<span data-ttu-id="2391a-189">是</span><span class="sxs-lookup"><span data-stu-id="2391a-189">Yes</span></span>|<span data-ttu-id="2391a-190">根据自身环境和需求进行配置</span><span class="sxs-lookup"><span data-stu-id="2391a-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="2391a-191">登录风险</span><span class="sxs-lookup"><span data-stu-id="2391a-191">Sign-in risk</span></span>|<span data-ttu-id="2391a-192">风险级别</span><span class="sxs-lookup"><span data-stu-id="2391a-192">Risk level</span></span>||<span data-ttu-id="2391a-193">请参阅下表中的指南</span><span class="sxs-lookup"><span data-stu-id="2391a-193">See the guidance in the following table</span></span>|

<span data-ttu-id="2391a-194">**登录风险**</span><span class="sxs-lookup"><span data-stu-id="2391a-194">**Sign-in risk**</span></span>

<span data-ttu-id="2391a-195">应用基于您的目标的保护级别的设置。</span><span class="sxs-lookup"><span data-stu-id="2391a-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="2391a-196">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-196">Property</span></span>|<span data-ttu-id="2391a-197">保护级别</span><span class="sxs-lookup"><span data-stu-id="2391a-197">Level of protection</span></span>|<span data-ttu-id="2391a-198">值</span><span class="sxs-lookup"><span data-stu-id="2391a-198">Values</span></span>|<span data-ttu-id="2391a-199">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="2391a-200">风险级别</span><span class="sxs-lookup"><span data-stu-id="2391a-200">Risk level</span></span>|<span data-ttu-id="2391a-201">基线</span><span class="sxs-lookup"><span data-stu-id="2391a-201">Baseline</span></span>|<span data-ttu-id="2391a-202">高、中</span><span class="sxs-lookup"><span data-stu-id="2391a-202">High, medium</span></span>|<span data-ttu-id="2391a-203">两项全选</span><span class="sxs-lookup"><span data-stu-id="2391a-203">Check both</span></span>|
| |<span data-ttu-id="2391a-204">敏感</span><span class="sxs-lookup"><span data-stu-id="2391a-204">Sensitive</span></span>|<span data-ttu-id="2391a-205">高、 中、 低</span><span class="sxs-lookup"><span data-stu-id="2391a-205">High, medium, low</span></span>|<span data-ttu-id="2391a-206">三项全选</span><span class="sxs-lookup"><span data-stu-id="2391a-206">Check all three</span></span>|
| |<span data-ttu-id="2391a-207">高度管控</span><span class="sxs-lookup"><span data-stu-id="2391a-207">Highly regulated</span></span>| |<span data-ttu-id="2391a-208">保留所有选项保持为不选中始终强制实施 MFA</span><span class="sxs-lookup"><span data-stu-id="2391a-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="2391a-209">访问控制</span><span class="sxs-lookup"><span data-stu-id="2391a-209">**Access controls**</span></span>

|<span data-ttu-id="2391a-210">类型</span><span class="sxs-lookup"><span data-stu-id="2391a-210">Type</span></span>|<span data-ttu-id="2391a-211">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-211">Properties</span></span>|<span data-ttu-id="2391a-212">值</span><span class="sxs-lookup"><span data-stu-id="2391a-212">Values</span></span>|<span data-ttu-id="2391a-213">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="2391a-214">授予</span><span class="sxs-lookup"><span data-stu-id="2391a-214">Grant</span></span>|<span data-ttu-id="2391a-215">授予访问权限</span><span class="sxs-lookup"><span data-stu-id="2391a-215">Grant access</span></span>|<span data-ttu-id="2391a-216">True</span><span class="sxs-lookup"><span data-stu-id="2391a-216">True</span></span>|<span data-ttu-id="2391a-217">已选择</span><span class="sxs-lookup"><span data-stu-id="2391a-217">Selected</span></span>|
||<span data-ttu-id="2391a-218">需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="2391a-218">Require MFA</span></span>|<span data-ttu-id="2391a-219">True</span><span class="sxs-lookup"><span data-stu-id="2391a-219">True</span></span>|<span data-ttu-id="2391a-220">Check</span><span class="sxs-lookup"><span data-stu-id="2391a-220">Check</span></span>|
||<span data-ttu-id="2391a-221">需要标记为兼容的设备</span><span class="sxs-lookup"><span data-stu-id="2391a-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="2391a-222">False</span><span class="sxs-lookup"><span data-stu-id="2391a-222">False</span></span>||
||<span data-ttu-id="2391a-223">需要混合 Azure AD 加入设备</span><span class="sxs-lookup"><span data-stu-id="2391a-223">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="2391a-224">False</span><span class="sxs-lookup"><span data-stu-id="2391a-224">False</span></span>||
||<span data-ttu-id="2391a-225">需要批准的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="2391a-225">Require approved client app</span></span>|<span data-ttu-id="2391a-226">False</span><span class="sxs-lookup"><span data-stu-id="2391a-226">False</span></span>||
||<span data-ttu-id="2391a-227">需要所有已选控件</span><span class="sxs-lookup"><span data-stu-id="2391a-227">Require all the selected controls</span></span>|<span data-ttu-id="2391a-228">True</span><span class="sxs-lookup"><span data-stu-id="2391a-228">True</span></span>|<span data-ttu-id="2391a-229">已选择</span><span class="sxs-lookup"><span data-stu-id="2391a-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="2391a-p112">请务必通过选择**在**启用此策略。此外考虑[如果](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具用于测试策略。</span><span class="sxs-lookup"><span data-stu-id="2391a-p112">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="2391a-232">阻止客户端不支持现代身份验证</span><span class="sxs-lookup"><span data-stu-id="2391a-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="2391a-p113">转到[Azure 门户](https://portal.azure.com)，并使用您的凭据登录。您已成功登录后，您将看到 Azure 仪表板。</span><span class="sxs-lookup"><span data-stu-id="2391a-p113">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="2391a-235">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="2391a-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="2391a-236">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="2391a-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="2391a-237">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="2391a-237">Choose **New policy**.</span></span>

<span data-ttu-id="2391a-238">下表介绍实现此策略的条件的访问策略设置。</span><span class="sxs-lookup"><span data-stu-id="2391a-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="2391a-239">分配</span><span class="sxs-lookup"><span data-stu-id="2391a-239">**Assignments**</span></span>

|<span data-ttu-id="2391a-240">类型</span><span class="sxs-lookup"><span data-stu-id="2391a-240">Type</span></span>|<span data-ttu-id="2391a-241">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-241">Properties</span></span>|<span data-ttu-id="2391a-242">值</span><span class="sxs-lookup"><span data-stu-id="2391a-242">Values</span></span>|<span data-ttu-id="2391a-243">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="2391a-244">用户和组</span><span class="sxs-lookup"><span data-stu-id="2391a-244">Users and groups</span></span>|<span data-ttu-id="2391a-245">包括</span><span class="sxs-lookup"><span data-stu-id="2391a-245">Include</span></span>|<span data-ttu-id="2391a-246">选择用户和组 - 选择包含目标用户的特定安全组</span><span class="sxs-lookup"><span data-stu-id="2391a-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="2391a-247">从包含试点用户的安全组开始</span><span class="sxs-lookup"><span data-stu-id="2391a-247">Start with security group including pilot users</span></span>|
||<span data-ttu-id="2391a-248">排除</span><span class="sxs-lookup"><span data-stu-id="2391a-248">Exclude</span></span>|<span data-ttu-id="2391a-249">例外安全组；服务帐户(应用标识)</span><span class="sxs-lookup"><span data-stu-id="2391a-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="2391a-250">按需临时修改的成员身份</span><span class="sxs-lookup"><span data-stu-id="2391a-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="2391a-251">云应用</span><span class="sxs-lookup"><span data-stu-id="2391a-251">Cloud apps</span></span>|<span data-ttu-id="2391a-252">包括</span><span class="sxs-lookup"><span data-stu-id="2391a-252">Include</span></span>|<span data-ttu-id="2391a-p114">选择您希望此规则应用于的应用程序。例如，选择 Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2391a-p114">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="2391a-255">条件</span><span class="sxs-lookup"><span data-stu-id="2391a-255">Conditions</span></span>|<span data-ttu-id="2391a-256">已配置</span><span class="sxs-lookup"><span data-stu-id="2391a-256">Configured</span></span>|<span data-ttu-id="2391a-257">是</span><span class="sxs-lookup"><span data-stu-id="2391a-257">Yes</span></span>|<span data-ttu-id="2391a-258">配置客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="2391a-258">Configure Client apps</span></span>|
|<span data-ttu-id="2391a-259">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="2391a-259">Client apps</span></span>|<span data-ttu-id="2391a-260">已配置</span><span class="sxs-lookup"><span data-stu-id="2391a-260">Configured</span></span>|<span data-ttu-id="2391a-261">是</span><span class="sxs-lookup"><span data-stu-id="2391a-261">Yes</span></span>|<span data-ttu-id="2391a-262">移动应用程序和桌面客户端，其他客户端 （选择两者）</span><span class="sxs-lookup"><span data-stu-id="2391a-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="2391a-263">访问控制</span><span class="sxs-lookup"><span data-stu-id="2391a-263">**Access controls**</span></span>

|<span data-ttu-id="2391a-264">类型</span><span class="sxs-lookup"><span data-stu-id="2391a-264">Type</span></span>|<span data-ttu-id="2391a-265">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-265">Properties</span></span>|<span data-ttu-id="2391a-266">值</span><span class="sxs-lookup"><span data-stu-id="2391a-266">Values</span></span>|<span data-ttu-id="2391a-267">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="2391a-268">授予</span><span class="sxs-lookup"><span data-stu-id="2391a-268">Grant</span></span>|<span data-ttu-id="2391a-269">阻止访问</span><span class="sxs-lookup"><span data-stu-id="2391a-269">Block access</span></span>|<span data-ttu-id="2391a-270">True</span><span class="sxs-lookup"><span data-stu-id="2391a-270">True</span></span>|<span data-ttu-id="2391a-271">已选择</span><span class="sxs-lookup"><span data-stu-id="2391a-271">Selected</span></span>|
||<span data-ttu-id="2391a-272">需要进行 MFA</span><span class="sxs-lookup"><span data-stu-id="2391a-272">Require MFA</span></span>|<span data-ttu-id="2391a-273">False</span><span class="sxs-lookup"><span data-stu-id="2391a-273">False</span></span>||
||<span data-ttu-id="2391a-274">需要标记为兼容的设备</span><span class="sxs-lookup"><span data-stu-id="2391a-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="2391a-275">False</span><span class="sxs-lookup"><span data-stu-id="2391a-275">False</span></span>||
||<span data-ttu-id="2391a-276">需要混合 Azure AD 加入设备</span><span class="sxs-lookup"><span data-stu-id="2391a-276">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="2391a-277">False</span><span class="sxs-lookup"><span data-stu-id="2391a-277">False</span></span>||
||<span data-ttu-id="2391a-278">需要批准的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="2391a-278">Require approved client app</span></span>|<span data-ttu-id="2391a-279">False</span><span class="sxs-lookup"><span data-stu-id="2391a-279">False</span></span>||
||<span data-ttu-id="2391a-280">需要所有已选控件</span><span class="sxs-lookup"><span data-stu-id="2391a-280">Require all the selected controls</span></span>|<span data-ttu-id="2391a-281">True</span><span class="sxs-lookup"><span data-stu-id="2391a-281">True</span></span>|<span data-ttu-id="2391a-282">已选择</span><span class="sxs-lookup"><span data-stu-id="2391a-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="2391a-p115">请务必通过选择**在**启用此策略。此外考虑[如果](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具用于测试策略。</span><span class="sxs-lookup"><span data-stu-id="2391a-p115">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="2391a-285">高风险用户必须更改密码</span><span class="sxs-lookup"><span data-stu-id="2391a-285">High risk users must change password</span></span>
<span data-ttu-id="2391a-286">若要确保所有高风险用户受到攻击的帐户强制执行密码更改时签名中，您必须应用以下策略。</span><span class="sxs-lookup"><span data-stu-id="2391a-286">To ensure that all high-risk users' compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="2391a-287">登录到[Microsoft Azure 门户 (http://portal.azure.com)](http://portal.azure.com/)使用管理员凭据，然后导航到**Azure AD 身份防护 > 用户风险策略**。</span><span class="sxs-lookup"><span data-stu-id="2391a-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="2391a-288">分配</span><span class="sxs-lookup"><span data-stu-id="2391a-288">**Assignments**</span></span>

|<span data-ttu-id="2391a-289">类型</span><span class="sxs-lookup"><span data-stu-id="2391a-289">Type</span></span>|<span data-ttu-id="2391a-290">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-290">Properties</span></span>|<span data-ttu-id="2391a-291">值</span><span class="sxs-lookup"><span data-stu-id="2391a-291">Values</span></span>|<span data-ttu-id="2391a-292">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="2391a-293">Users</span><span class="sxs-lookup"><span data-stu-id="2391a-293">Users</span></span>|<span data-ttu-id="2391a-294">包括</span><span class="sxs-lookup"><span data-stu-id="2391a-294">Include</span></span>|<span data-ttu-id="2391a-295">所有用户</span><span class="sxs-lookup"><span data-stu-id="2391a-295">All users</span></span>|<span data-ttu-id="2391a-296">已选择</span><span class="sxs-lookup"><span data-stu-id="2391a-296">Selected</span></span>|
||<span data-ttu-id="2391a-297">排除</span><span class="sxs-lookup"><span data-stu-id="2391a-297">Exclude</span></span>|<span data-ttu-id="2391a-298">无</span><span class="sxs-lookup"><span data-stu-id="2391a-298">None</span></span>||
|<span data-ttu-id="2391a-299">条件</span><span class="sxs-lookup"><span data-stu-id="2391a-299">Conditions</span></span>|<span data-ttu-id="2391a-300">用户风险</span><span class="sxs-lookup"><span data-stu-id="2391a-300">User risk</span></span>|<span data-ttu-id="2391a-301">高</span><span class="sxs-lookup"><span data-stu-id="2391a-301">High</span></span>|<span data-ttu-id="2391a-302">已选择</span><span class="sxs-lookup"><span data-stu-id="2391a-302">Selected</span></span>|

<span data-ttu-id="2391a-303">控制</span><span class="sxs-lookup"><span data-stu-id="2391a-303">**Controls**</span></span>

| <span data-ttu-id="2391a-304">类型</span><span class="sxs-lookup"><span data-stu-id="2391a-304">Type</span></span> | <span data-ttu-id="2391a-305">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-305">Properties</span></span> | <span data-ttu-id="2391a-306">值</span><span class="sxs-lookup"><span data-stu-id="2391a-306">Values</span></span>                  | <span data-ttu-id="2391a-307">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="2391a-308">访问</span><span class="sxs-lookup"><span data-stu-id="2391a-308">Access</span></span>     | <span data-ttu-id="2391a-309">允许访问</span><span class="sxs-lookup"><span data-stu-id="2391a-309">Allow access</span></span>            | <span data-ttu-id="2391a-310">True</span><span class="sxs-lookup"><span data-stu-id="2391a-310">True</span></span>  |
|      | <span data-ttu-id="2391a-311">访问</span><span class="sxs-lookup"><span data-stu-id="2391a-311">Access</span></span>     | <span data-ttu-id="2391a-312">需要更改密码</span><span class="sxs-lookup"><span data-stu-id="2391a-312">Require password change</span></span> | <span data-ttu-id="2391a-313">True</span><span class="sxs-lookup"><span data-stu-id="2391a-313">True</span></span>  |

<span data-ttu-id="2391a-314">**审阅：** 不适用</span><span class="sxs-lookup"><span data-stu-id="2391a-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="2391a-p116">请务必通过选择**在**启用此策略。此外考虑[如果](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具用于测试策略</span><span class="sxs-lookup"><span data-stu-id="2391a-p116">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="2391a-317">定义应用程序保护策略</span><span class="sxs-lookup"><span data-stu-id="2391a-317">Define app protection policies</span></span>
<span data-ttu-id="2391a-p117">应用程序保护策略定义允许的应用程序并他们与您组织的数据可以执行的操作。创建 Intune 应用程序中的 Azure 门户从保护策略。</span><span class="sxs-lookup"><span data-stu-id="2391a-p117">App protection policies define which apps are allowed and the actions they can take with your organization's data. Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="2391a-320">创建每个平台的策略：</span><span class="sxs-lookup"><span data-stu-id="2391a-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="2391a-321">iOS</span><span class="sxs-lookup"><span data-stu-id="2391a-321">iOS</span></span>
- <span data-ttu-id="2391a-322">Android</span><span class="sxs-lookup"><span data-stu-id="2391a-322">Android</span></span>
- <span data-ttu-id="2391a-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2391a-323">Windows 10</span></span>

<span data-ttu-id="2391a-p118">若要创建新的应用程序保护策略，登录到您的管理凭据的 Microsoft Azure 门户，然后导航到**移动应用程序 > 应用程序保护策略**。选择**添加策略**。</span><span class="sxs-lookup"><span data-stu-id="2391a-p118">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**. Choose **Add a policy**.</span></span>

<span data-ttu-id="2391a-p119">有微小的差异的应用程序保护 iOS 和 Android 之间的策略选项。以下策略是专用于 Android。使用此指南作为在其他策略。</span><span class="sxs-lookup"><span data-stu-id="2391a-p119">There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android. Use this as a guide for your other policies.</span></span>

<span data-ttu-id="2391a-329">推荐的应用程序列表包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="2391a-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="2391a-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2391a-330">PowerPoint</span></span>
- <span data-ttu-id="2391a-331">Excel</span><span class="sxs-lookup"><span data-stu-id="2391a-331">Excel</span></span>
- <span data-ttu-id="2391a-332">Word</span><span class="sxs-lookup"><span data-stu-id="2391a-332">Word</span></span>
- <span data-ttu-id="2391a-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2391a-333">Microsoft Teams</span></span>
- <span data-ttu-id="2391a-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="2391a-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="2391a-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="2391a-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="2391a-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="2391a-336">OneDrive</span></span>
- <span data-ttu-id="2391a-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="2391a-337">OneNote</span></span>
- <span data-ttu-id="2391a-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="2391a-338">Outlook</span></span>

<span data-ttu-id="2391a-339">下表介绍建议的设置：</span><span class="sxs-lookup"><span data-stu-id="2391a-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="2391a-340">类型</span><span class="sxs-lookup"><span data-stu-id="2391a-340">Type</span></span>|<span data-ttu-id="2391a-341">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-341">Properties</span></span>|<span data-ttu-id="2391a-342">值</span><span class="sxs-lookup"><span data-stu-id="2391a-342">Values</span></span>|<span data-ttu-id="2391a-343">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="2391a-344">数据重定位</span><span class="sxs-lookup"><span data-stu-id="2391a-344">Data relocation</span></span>|<span data-ttu-id="2391a-345">阻止 Android 备份</span><span class="sxs-lookup"><span data-stu-id="2391a-345">Prevent Android backup</span></span>|<span data-ttu-id="2391a-346">是</span><span class="sxs-lookup"><span data-stu-id="2391a-346">Yes</span></span>|<span data-ttu-id="2391a-347">在 iOS 上，这会专门调用 iTunes 和 iCloud</span><span class="sxs-lookup"><span data-stu-id="2391a-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="2391a-348">允许应用向其他应用传送数据</span><span class="sxs-lookup"><span data-stu-id="2391a-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="2391a-349">策略托管应用</span><span class="sxs-lookup"><span data-stu-id="2391a-349">Policy managed apps</span></span>||
||<span data-ttu-id="2391a-350">允许应用从其他应用接收数据</span><span class="sxs-lookup"><span data-stu-id="2391a-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="2391a-351">策略托管应用</span><span class="sxs-lookup"><span data-stu-id="2391a-351">Policy managed apps</span></span>||
||<span data-ttu-id="2391a-352">防止“另存为”</span><span class="sxs-lookup"><span data-stu-id="2391a-352">Prevent "Save As"</span></span>|<span data-ttu-id="2391a-353">是</span><span class="sxs-lookup"><span data-stu-id="2391a-353">Yes</span></span>||
||<span data-ttu-id="2391a-354">选择企业数据可保存到其中的存储服务</span><span class="sxs-lookup"><span data-stu-id="2391a-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="2391a-355">OneDrive for Business，SharePoint</span><span class="sxs-lookup"><span data-stu-id="2391a-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="2391a-356">限制使用其他应用剪切、复制和粘贴</span><span class="sxs-lookup"><span data-stu-id="2391a-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="2391a-357">与粘贴中的策略托管应用程序</span><span class="sxs-lookup"><span data-stu-id="2391a-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="2391a-358">限制显示在托管浏览器内的 Web 内容</span><span class="sxs-lookup"><span data-stu-id="2391a-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="2391a-359">否</span><span class="sxs-lookup"><span data-stu-id="2391a-359">No</span></span>||
||<span data-ttu-id="2391a-360">加密应用数据</span><span class="sxs-lookup"><span data-stu-id="2391a-360">Encrypt app data</span></span>|<span data-ttu-id="2391a-361">是</span><span class="sxs-lookup"><span data-stu-id="2391a-361">Yes</span></span>|<span data-ttu-id="2391a-362">在 iOS 上，选择选项：“锁定设备时”</span><span class="sxs-lookup"><span data-stu-id="2391a-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="2391a-363">启用设备时禁用应用程序加密</span><span class="sxs-lookup"><span data-stu-id="2391a-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="2391a-364">是</span><span class="sxs-lookup"><span data-stu-id="2391a-364">Yes</span></span>|<span data-ttu-id="2391a-365">禁用此设置，以避免双加密</span><span class="sxs-lookup"><span data-stu-id="2391a-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="2391a-366">禁用联系人同步</span><span class="sxs-lookup"><span data-stu-id="2391a-366">Disable contacts sync</span></span>|<span data-ttu-id="2391a-367">否</span><span class="sxs-lookup"><span data-stu-id="2391a-367">No</span></span>||
||<span data-ttu-id="2391a-368">禁用打印</span><span class="sxs-lookup"><span data-stu-id="2391a-368">Disable printing</span></span>|<span data-ttu-id="2391a-369">否</span><span class="sxs-lookup"><span data-stu-id="2391a-369">No</span></span>||
|<span data-ttu-id="2391a-370">访问</span><span class="sxs-lookup"><span data-stu-id="2391a-370">Access</span></span>|<span data-ttu-id="2391a-371">访问需要 PIN</span><span class="sxs-lookup"><span data-stu-id="2391a-371">Require PIN for access</span></span>|<span data-ttu-id="2391a-372">是</span><span class="sxs-lookup"><span data-stu-id="2391a-372">Yes</span></span>||
||<span data-ttu-id="2391a-373">选择类型</span><span class="sxs-lookup"><span data-stu-id="2391a-373">Select Type</span></span>|<span data-ttu-id="2391a-374">数字</span><span class="sxs-lookup"><span data-stu-id="2391a-374">Numeric</span></span>||
||<span data-ttu-id="2391a-375">允许使用简单 PIN</span><span class="sxs-lookup"><span data-stu-id="2391a-375">Allow simple PIN</span></span>|<span data-ttu-id="2391a-376">否</span><span class="sxs-lookup"><span data-stu-id="2391a-376">No</span></span>||
||<span data-ttu-id="2391a-377">PIN 长度</span><span class="sxs-lookup"><span data-stu-id="2391a-377">PIN length</span></span>|<span data-ttu-id="2391a-378">6</span><span class="sxs-lookup"><span data-stu-id="2391a-378">6</span></span>||
||<span data-ttu-id="2391a-379">允许使用指纹而不是 PIN</span><span class="sxs-lookup"><span data-stu-id="2391a-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="2391a-380">是</span><span class="sxs-lookup"><span data-stu-id="2391a-380">Yes</span></span>||
||<span data-ttu-id="2391a-381">管理设备 PIN 时禁用应用程序 PIN</span><span class="sxs-lookup"><span data-stu-id="2391a-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="2391a-382">是</span><span class="sxs-lookup"><span data-stu-id="2391a-382">Yes</span></span>||
||<span data-ttu-id="2391a-383">需要访问企业凭据</span><span class="sxs-lookup"><span data-stu-id="2391a-383">Require corporate credentials for access</span></span>|<span data-ttu-id="2391a-384">否</span><span class="sxs-lookup"><span data-stu-id="2391a-384">No</span></span>||
||<span data-ttu-id="2391a-385">在一定时间后重新检查访问要求(分钟)</span><span class="sxs-lookup"><span data-stu-id="2391a-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="2391a-386">30</span><span class="sxs-lookup"><span data-stu-id="2391a-386">30</span></span>||
||<span data-ttu-id="2391a-387">阻止屏幕捕获和 Android 助手</span><span class="sxs-lookup"><span data-stu-id="2391a-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="2391a-388">否</span><span class="sxs-lookup"><span data-stu-id="2391a-388">No</span></span>|<span data-ttu-id="2391a-389">在 iOS 上，此选项不可用</span><span class="sxs-lookup"><span data-stu-id="2391a-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="2391a-390">登录安全要求</span><span class="sxs-lookup"><span data-stu-id="2391a-390">Sign-in security requirements</span></span>|<span data-ttu-id="2391a-391">最大 PIN 尝试</span><span class="sxs-lookup"><span data-stu-id="2391a-391">Max PIN attempts</span></span>|<span data-ttu-id="2391a-392">5</span><span class="sxs-lookup"><span data-stu-id="2391a-392">5</span></span>|<span data-ttu-id="2391a-393">重置 Pin</span><span class="sxs-lookup"><span data-stu-id="2391a-393">Reset Pin</span></span>|
||<span data-ttu-id="2391a-394">离线宽限期</span><span class="sxs-lookup"><span data-stu-id="2391a-394">Offline grace period</span></span>|<span data-ttu-id="2391a-395">720</span><span class="sxs-lookup"><span data-stu-id="2391a-395">720</span></span>|<span data-ttu-id="2391a-396">阻止访问</span><span class="sxs-lookup"><span data-stu-id="2391a-396">Block access</span></span>|
||<span data-ttu-id="2391a-397">擦除应用数据之前的脱机间隔时间（天）</span><span class="sxs-lookup"><span data-stu-id="2391a-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="2391a-398">90</span><span class="sxs-lookup"><span data-stu-id="2391a-398">90</span></span>|<span data-ttu-id="2391a-399">擦除数据</span><span class="sxs-lookup"><span data-stu-id="2391a-399">Wipe data</span></span>|
||<span data-ttu-id="2391a-400">根 Jailbroken/设备</span><span class="sxs-lookup"><span data-stu-id="2391a-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="2391a-401">擦除数据</span><span class="sxs-lookup"><span data-stu-id="2391a-401">Wipe data</span></span>|

<span data-ttu-id="2391a-p120">完成后，请务必选中"创建"。重复上述步骤，并将替换为 iOS 的选定的平台 （下拉）。这将创建两个应用程序策略，因此后创建策略，然后将组分配给策略并将其部署。</span><span class="sxs-lookup"><span data-stu-id="2391a-p120">When complete, remember to select "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="2391a-405">若要编辑策略并将这些策略分配给用户，请参阅[如何创建和分配应用程序保护策略](https://docs.microsoft.com/intune/app-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="2391a-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="2391a-406">需要已批准应用程序</span><span class="sxs-lookup"><span data-stu-id="2391a-406">Require approved apps</span></span>
<span data-ttu-id="2391a-407">若要要求已批准应用程序：</span><span class="sxs-lookup"><span data-stu-id="2391a-407">To require approved apps:</span></span>

1. <span data-ttu-id="2391a-p121">转到[Azure 门户](https://portal.azure.com)，并使用您的凭据登录。您已成功登录后，您将看到 Azure 仪表板。</span><span class="sxs-lookup"><span data-stu-id="2391a-p121">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="2391a-410">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="2391a-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="2391a-411">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="2391a-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="2391a-412">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="2391a-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="2391a-413">输入策略名称，然后选择要应用策略的“用户和组”。</span><span class="sxs-lookup"><span data-stu-id="2391a-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="2391a-414">选择“云应用”。</span><span class="sxs-lookup"><span data-stu-id="2391a-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="2391a-p122">选择**选择应用程序**，从**云应用程序**列表中选择所需的应用程序。例如，选择 Office 365 Exchange Online。选择**选择**并**完成**。</span><span class="sxs-lookup"><span data-stu-id="2391a-p122">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="2391a-418">从“访问控制”部分选择“授予”。</span><span class="sxs-lookup"><span data-stu-id="2391a-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="2391a-p123">选择**授予访问**，选择**需要批准客户端应用程序**。为多个控件中，选择**需要选定的控件**，然后选择**选择**。</span><span class="sxs-lookup"><span data-stu-id="2391a-p123">Choose **Grant access**, select **Require approved client app**. For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="2391a-421">选择" **创建**"。</span><span class="sxs-lookup"><span data-stu-id="2391a-421">Choose **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="2391a-422">定义设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="2391a-422">Define device-compliance policies</span></span>

<span data-ttu-id="2391a-p124">设备合规性策略定义的设备必须遵守才能被标记为兼容的要求。创建 Intune 设备从 Azure 门户中的合规性策略。</span><span class="sxs-lookup"><span data-stu-id="2391a-p124">Device-compliance policies define the requirements that devices must adhere to in order to be marked as compliant. Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="2391a-425">创建每个平台的策略：</span><span class="sxs-lookup"><span data-stu-id="2391a-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="2391a-426">Android</span><span class="sxs-lookup"><span data-stu-id="2391a-426">Android</span></span>
- <span data-ttu-id="2391a-427">Android 企业</span><span class="sxs-lookup"><span data-stu-id="2391a-427">Android enterprise</span></span>
- <span data-ttu-id="2391a-428">iOS</span><span class="sxs-lookup"><span data-stu-id="2391a-428">iOS</span></span>
- <span data-ttu-id="2391a-429">macOS</span><span class="sxs-lookup"><span data-stu-id="2391a-429">macOS</span></span>
- <span data-ttu-id="2391a-430">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="2391a-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="2391a-431">Windows 8.1 及更高版本</span><span class="sxs-lookup"><span data-stu-id="2391a-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="2391a-432">Windows 10 及更高版本</span><span class="sxs-lookup"><span data-stu-id="2391a-432">Windows 10 and later</span></span>

<span data-ttu-id="2391a-p125">若要创建设备合规性策略，登录到您的管理凭据的 Microsoft Azure 门户，然后导航到**Intune > 设备合规性**。选择**创建策略**。</span><span class="sxs-lookup"><span data-stu-id="2391a-p125">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**. Select **Create policy**.</span></span>

<span data-ttu-id="2391a-435">为 Windows 10 建议使用下列设置。</span><span class="sxs-lookup"><span data-stu-id="2391a-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="2391a-436">**设备运行状况： Windows 运行状况审计服务求值规则**</span><span class="sxs-lookup"><span data-stu-id="2391a-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="2391a-437">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-437">Properties</span></span>|<span data-ttu-id="2391a-438">值</span><span class="sxs-lookup"><span data-stu-id="2391a-438">Values</span></span>|<span data-ttu-id="2391a-439">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="2391a-440">需要 BitLocker</span><span class="sxs-lookup"><span data-stu-id="2391a-440">Require BitLocker</span></span>|<span data-ttu-id="2391a-441">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-441">Require</span></span>||
|<span data-ttu-id="2391a-442">需要安全引导设备上启用</span><span class="sxs-lookup"><span data-stu-id="2391a-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="2391a-443">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-443">Require</span></span>||
|<span data-ttu-id="2391a-444">需要代码完整性</span><span class="sxs-lookup"><span data-stu-id="2391a-444">Require code integrity</span></span>|<span data-ttu-id="2391a-445">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-445">Require</span></span>||


<span data-ttu-id="2391a-446">设备属性</span><span class="sxs-lookup"><span data-stu-id="2391a-446">**Device properties**</span></span>

|<span data-ttu-id="2391a-447">类型</span><span class="sxs-lookup"><span data-stu-id="2391a-447">Type</span></span>|<span data-ttu-id="2391a-448">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-448">Properties</span></span>|<span data-ttu-id="2391a-449">值</span><span class="sxs-lookup"><span data-stu-id="2391a-449">Values</span></span>|<span data-ttu-id="2391a-450">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="2391a-451">操作系统版本</span><span class="sxs-lookup"><span data-stu-id="2391a-451">Operating system version</span></span>|<span data-ttu-id="2391a-452">全部</span><span class="sxs-lookup"><span data-stu-id="2391a-452">All</span></span>|<span data-ttu-id="2391a-453">未配置</span><span class="sxs-lookup"><span data-stu-id="2391a-453">Not configured</span></span>||

<span data-ttu-id="2391a-p126">对于所有上述策略视为部署，它们必须针对用户组。您可以执行此操作通过创建策略 （保存） 或更高版本，通过选择在**策略**部分 （相同级别添加） 的**管理部署**。</span><span class="sxs-lookup"><span data-stu-id="2391a-p126">For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting **Manage Deployment** in the **Policy** section (same level as Add).</span></span>

<span data-ttu-id="2391a-456">系统安全</span><span class="sxs-lookup"><span data-stu-id="2391a-456">**System security**</span></span>

|<span data-ttu-id="2391a-457">类型</span><span class="sxs-lookup"><span data-stu-id="2391a-457">Type</span></span>|<span data-ttu-id="2391a-458">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-458">Properties</span></span>|<span data-ttu-id="2391a-459">值</span><span class="sxs-lookup"><span data-stu-id="2391a-459">Values</span></span>|<span data-ttu-id="2391a-460">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="2391a-461">密码</span><span class="sxs-lookup"><span data-stu-id="2391a-461">Password</span></span>|<span data-ttu-id="2391a-462">需要密码以解锁移动设备</span><span class="sxs-lookup"><span data-stu-id="2391a-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="2391a-463">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-463">Require</span></span>||
||<span data-ttu-id="2391a-464">简单密码</span><span class="sxs-lookup"><span data-stu-id="2391a-464">Simple passwords</span></span>|<span data-ttu-id="2391a-465">阻止</span><span class="sxs-lookup"><span data-stu-id="2391a-465">Block</span></span>||
||<span data-ttu-id="2391a-466">密码类型</span><span class="sxs-lookup"><span data-stu-id="2391a-466">Password type</span></span>|<span data-ttu-id="2391a-467">默认设备</span><span class="sxs-lookup"><span data-stu-id="2391a-467">Device default</span></span>||
||<span data-ttu-id="2391a-468">最短密码长度</span><span class="sxs-lookup"><span data-stu-id="2391a-468">Minimum password length</span></span>|<span data-ttu-id="2391a-469">6</span><span class="sxs-lookup"><span data-stu-id="2391a-469">6</span></span>||
||<span data-ttu-id="2391a-470">最大分钟无活动需要密码之前</span><span class="sxs-lookup"><span data-stu-id="2391a-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="2391a-471">15 </span><span class="sxs-lookup"><span data-stu-id="2391a-471">15</span></span>|<span data-ttu-id="2391a-p127">此设置支持 Android 版本 4.0 和上方或 KNOX 4.0 及以上。对于 iOS 设备，它支持针对 iOS 8.0 和上方</span><span class="sxs-lookup"><span data-stu-id="2391a-p127">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above. For iOS devices, it’s supported for iOS 8.0 and above</span></span>|
||<span data-ttu-id="2391a-474">密码过期(天)</span><span class="sxs-lookup"><span data-stu-id="2391a-474">Password expiration (days)</span></span>|<span data-ttu-id="2391a-475">41</span><span class="sxs-lookup"><span data-stu-id="2391a-475">41</span></span>||
||<span data-ttu-id="2391a-476">以前的密码，以防止重复使用的数量</span><span class="sxs-lookup"><span data-stu-id="2391a-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="2391a-477">5</span><span class="sxs-lookup"><span data-stu-id="2391a-477">5</span></span>||
||<span data-ttu-id="2391a-478">从空闲状态 （Mobile 和全息） 返回设备时需要密码</span><span class="sxs-lookup"><span data-stu-id="2391a-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="2391a-479">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-479">Require</span></span>|<span data-ttu-id="2391a-480">适用于 Windows 10 及更高版本</span><span class="sxs-lookup"><span data-stu-id="2391a-480">Available for Windows 10 and later</span></span>|
|<span data-ttu-id="2391a-481">加密</span><span class="sxs-lookup"><span data-stu-id="2391a-481">Encryption</span></span>|<span data-ttu-id="2391a-482">在设备上的数据存储的加密</span><span class="sxs-lookup"><span data-stu-id="2391a-482">Encryption of data storage on device</span></span>|<span data-ttu-id="2391a-483">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-483">Require</span></span>||
|<span data-ttu-id="2391a-484">设备安全</span><span class="sxs-lookup"><span data-stu-id="2391a-484">Device Security</span></span>|<span data-ttu-id="2391a-485">防火墙</span><span class="sxs-lookup"><span data-stu-id="2391a-485">Firewall</span></span>|<span data-ttu-id="2391a-486">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-486">Require</span></span>||
||<span data-ttu-id="2391a-487">防病毒</span><span class="sxs-lookup"><span data-stu-id="2391a-487">Antivirus</span></span>|<span data-ttu-id="2391a-488">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-488">Require</span></span>||
||<span data-ttu-id="2391a-489">反间谍软件</span><span class="sxs-lookup"><span data-stu-id="2391a-489">Antispyware</span></span>|<span data-ttu-id="2391a-490">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-490">Require</span></span>|<span data-ttu-id="2391a-491">此设置，需要使用 Windows 安全中心注册反间谍软件解决方案</span><span class="sxs-lookup"><span data-stu-id="2391a-491">This setting requires an Anti-Spyware solution registered with Windows Security Center</span></span>|
|<span data-ttu-id="2391a-492">Defender</span><span class="sxs-lookup"><span data-stu-id="2391a-492">Defender</span></span>|<span data-ttu-id="2391a-493">Windows Defender 反恶意软件</span><span class="sxs-lookup"><span data-stu-id="2391a-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="2391a-494">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-494">Require</span></span>||
||<span data-ttu-id="2391a-495">Windows Defender 反恶意软件的最低版本</span><span class="sxs-lookup"><span data-stu-id="2391a-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="2391a-p128">仅支持 Windows 10 桌面。Microsoft 建议版本不超过 5 后面从最新版本</span><span class="sxs-lookup"><span data-stu-id="2391a-p128">Only supported for Windows 10 desktop. Microsoft recommends versions no more than five behind from the most recent version</span></span>|
||<span data-ttu-id="2391a-498">最新的 Windows Defender 反恶意软件签名</span><span class="sxs-lookup"><span data-stu-id="2391a-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="2391a-499">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-499">Require</span></span>||
||<span data-ttu-id="2391a-500">“实时保护”</span><span class="sxs-lookup"><span data-stu-id="2391a-500">Real-time protection</span></span>|<span data-ttu-id="2391a-501">需要</span><span class="sxs-lookup"><span data-stu-id="2391a-501">Require</span></span>|<span data-ttu-id="2391a-502">仅支持 Windows 10 桌面支持</span><span class="sxs-lookup"><span data-stu-id="2391a-502">Only supported for Windows 10 desktop</span></span>|

<span data-ttu-id="2391a-503">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="2391a-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="2391a-504">类型</span><span class="sxs-lookup"><span data-stu-id="2391a-504">Type</span></span>|<span data-ttu-id="2391a-505">属性</span><span class="sxs-lookup"><span data-stu-id="2391a-505">Properties</span></span>|<span data-ttu-id="2391a-506">值</span><span class="sxs-lookup"><span data-stu-id="2391a-506">Values</span></span>|<span data-ttu-id="2391a-507">注释</span><span class="sxs-lookup"><span data-stu-id="2391a-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="2391a-508">Windows Defender 高级威胁保护规则</span><span class="sxs-lookup"><span data-stu-id="2391a-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="2391a-509">需要为在或下的计算机风险分数的设备</span><span class="sxs-lookup"><span data-stu-id="2391a-509">Require the device to be at or under the machine-risk score</span></span>|<span data-ttu-id="2391a-510">中等</span><span class="sxs-lookup"><span data-stu-id="2391a-510">Medium</span></span>||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="2391a-511">需要符合 Pc （但不是符合标准的电话和平板电脑）</span><span class="sxs-lookup"><span data-stu-id="2391a-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="2391a-p129">添加之前需要符合 Pc 的策略，请务必注册到 Intune 的管理设备。注册到 Intune 的设备的设备包含在预期的用户所拥有的保证之前，建议使用多因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="2391a-p129">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="2391a-514">需要符合 Pc:</span><span class="sxs-lookup"><span data-stu-id="2391a-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="2391a-p130">转到[Azure 门户](https://portal.azure.com)，并使用您的凭据登录。您已成功登录后，您将看到 Azure 仪表板。</span><span class="sxs-lookup"><span data-stu-id="2391a-p130">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="2391a-517">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="2391a-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="2391a-518">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="2391a-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="2391a-519">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="2391a-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="2391a-520">输入策略名称，然后选择要应用策略的“用户和组”。</span><span class="sxs-lookup"><span data-stu-id="2391a-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="2391a-521">选择“云应用”。</span><span class="sxs-lookup"><span data-stu-id="2391a-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="2391a-p131">选择**选择应用程序**，从**云应用程序**列表中选择所需的应用程序。例如，选择 Office 365 Exchange Online。选择**选择**并**完成**。</span><span class="sxs-lookup"><span data-stu-id="2391a-p131">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="2391a-p132">如果需要符合 Pc，但不是符合手机和平板电脑，请选择**条件**和**设备平台**。选择**选择设备平台**，并选择**Windows**和**macOS**。</span><span class="sxs-lookup"><span data-stu-id="2391a-p132">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**. Choose **Select device platforms** and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="2391a-527">从“访问控制”部分选择“授予”。</span><span class="sxs-lookup"><span data-stu-id="2391a-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="2391a-p133">选择**授予访问**，选择**需要标记为兼容的设备**。为多个控件中，选择**需要所有选定的控件**，然后选择**选择**。</span><span class="sxs-lookup"><span data-stu-id="2391a-p133">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="2391a-530">选择" **创建**"。</span><span class="sxs-lookup"><span data-stu-id="2391a-530">Choose **Create**.</span></span>

<span data-ttu-id="2391a-p134">如果您的目标是需要兼容的 Pc*和*移动设备，则不要选择平台。这将强制所有设备法规遵从性。</span><span class="sxs-lookup"><span data-stu-id="2391a-p134">If your objective is to require compliant PCs *and* mobile devices, do not select platforms. This enforces compliance for all devices.</span></span> 

## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="2391a-533">需要符合标准的 Pc*和*移动设备</span><span class="sxs-lookup"><span data-stu-id="2391a-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="2391a-534">若要为所有设备要求合规性：</span><span class="sxs-lookup"><span data-stu-id="2391a-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="2391a-p135">转到[Azure 门户](https://portal.azure.com)，并使用您的凭据登录。您已成功登录后，您将看到 Azure 仪表板。</span><span class="sxs-lookup"><span data-stu-id="2391a-p135">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="2391a-537">从左侧菜单中选择“Azure Active Directory”。</span><span class="sxs-lookup"><span data-stu-id="2391a-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="2391a-538">在“安全”部分之下，选择“条件访问”。</span><span class="sxs-lookup"><span data-stu-id="2391a-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="2391a-539">选择“新策略”。</span><span class="sxs-lookup"><span data-stu-id="2391a-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="2391a-540">输入策略名称，然后选择要应用策略的“用户和组”。</span><span class="sxs-lookup"><span data-stu-id="2391a-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="2391a-541">选择“云应用”。</span><span class="sxs-lookup"><span data-stu-id="2391a-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="2391a-p136">选择**选择应用程序**，从**云应用程序**列表中选择所需的应用程序。例如，选择 Office 365 Exchange Online。选择**选择**并**完成**。</span><span class="sxs-lookup"><span data-stu-id="2391a-p136">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="2391a-545">从“访问控制”部分选择“授予”。</span><span class="sxs-lookup"><span data-stu-id="2391a-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="2391a-p137">选择**授予访问**，选择**需要标记为兼容的设备**。为多个控件中，选择**需要所有选定的控件**，然后选择**选择**。</span><span class="sxs-lookup"><span data-stu-id="2391a-p137">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="2391a-548">选择" **创建**"。</span><span class="sxs-lookup"><span data-stu-id="2391a-548">Choose **Create**.</span></span>

<span data-ttu-id="2391a-p138">在创建此策略时，不要选中平台。这将强制兼容的设备。</span><span class="sxs-lookup"><span data-stu-id="2391a-p138">When creating this policy, do not select platforms. This enforces compliant devices.</span></span>




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
## <a name="next-steps"></a><span data-ttu-id="2391a-551">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2391a-551">Next steps</span></span>

[<span data-ttu-id="2391a-552">了解有关用于保护电子邮件的策略建议</span><span class="sxs-lookup"><span data-stu-id="2391a-552">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
