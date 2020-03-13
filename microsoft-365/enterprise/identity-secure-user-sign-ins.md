---
title: 步骤 3：保护和管理用户登录
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 你可以让用户更安全地登录到 Windows 设备和 Microsoft 365。
ms.openlocfilehash: c541f5b74fe3ea6e94b002212f21ec8645e8e87e
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544011"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="5fbff-103">步骤 3：保护和管理用户登录</span><span class="sxs-lookup"><span data-stu-id="5fbff-103">Step 3: Secure and manage your user sign-ins</span></span>

![第 2 阶段 - 标识](../media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="5fbff-105">使用 Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="5fbff-105">Use Windows Hello for Business</span></span>

<span data-ttu-id="5fbff-106">*这是可选的，适用于 Microsoft 365 的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="5fbff-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="5fbff-107">Windows 10 企业版中的 Windows Hello 企业版在 Windows 设备上签名时，会将密码替换为强双因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="5fbff-107">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="5fbff-108">这两个因素是一种与设备和生物识别或 PIN 相关联的新型用户凭据。</span><span class="sxs-lookup"><span data-stu-id="5fbff-108">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="5fbff-109">有关详细信息，请参阅 [Windows Hello 企业版概述](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。</span><span class="sxs-lookup"><span data-stu-id="5fbff-109">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="5fbff-110">设置 Azure 多因素身份验证</span><span class="sxs-lookup"><span data-stu-id="5fbff-110">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="5fbff-111">*这是可选的，适用于 Microsoft 365 的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="5fbff-111">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="5fbff-112">在此步骤中，将设置 Azure 多因素身份验证 (MFA)，为用户登录和事务添加第二层安全性。</span><span class="sxs-lookup"><span data-stu-id="5fbff-112">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="5fbff-113">用户正确输入密码后，MFA 需要一种附加验证方法。</span><span class="sxs-lookup"><span data-stu-id="5fbff-113">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="5fbff-114">如果不使用 MFA，则密码是唯一的验证方法。</span><span class="sxs-lookup"><span data-stu-id="5fbff-114">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="5fbff-115">对于密码而言，其问题在于许多密码很容易被攻击者猜到，或在不知情的情况下与非受信任方共享。</span><span class="sxs-lookup"><span data-stu-id="5fbff-115">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="5fbff-116">使用 MFA，第二层安全可以是：</span><span class="sxs-lookup"><span data-stu-id="5fbff-116">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="5fbff-117">不易被欺骗或者复制的个人和受信任设备，如智能手机。</span><span class="sxs-lookup"><span data-stu-id="5fbff-117">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="5fbff-118">生物识别属性，如指纹。</span><span class="sxs-lookup"><span data-stu-id="5fbff-118">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="5fbff-119">将启用 MFA 并使用[条件访问策略](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)配置次要身份验证方法，该方法允许使用 Azure Active Directory (Azure AD) 组向指定的用户组（如试点用户、地理区域或部门）推出 MFA。</span><span class="sxs-lookup"><span data-stu-id="5fbff-119">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="5fbff-120">请确保用户知道已启用 MFA，以便他们理解要求（如强制使用智能手机进行登录）并可以成功登录。</span><span class="sxs-lookup"><span data-stu-id="5fbff-120">Make sure to let your users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="5fbff-121">有关详细信息，请参阅[规划基于云的 Azure 多因素身份验证部署](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)。</span><span class="sxs-lookup"><span data-stu-id="5fbff-121">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5fbff-123">测试实验室指南：Azure 多因素身份验证</span><span class="sxs-lookup"><span data-stu-id="5fbff-123">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="5fbff-124">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-mfa)。</span><span class="sxs-lookup"><span data-stu-id="5fbff-124">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="5fbff-125">防止凭据泄露</span><span class="sxs-lookup"><span data-stu-id="5fbff-125">Protect against credential compromise</span></span>

<span data-ttu-id="5fbff-126">*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="5fbff-126">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="5fbff-127">在此部分中，将了解如何配置策略，以防止凭据泄露（攻击者可以通过确定用户帐户名称和密码来获取访问组织的云服务和数据的权限）。</span><span class="sxs-lookup"><span data-stu-id="5fbff-127">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="5fbff-128">Azure AD Identity Protection 可提供多种方式来帮助阻止攻击者破坏用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="5fbff-128">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="5fbff-129">使用 Azure AD Identity Protection，可以：</span><span class="sxs-lookup"><span data-stu-id="5fbff-129">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="5fbff-130">确定并解决组织身份中的潜在漏洞</span><span class="sxs-lookup"><span data-stu-id="5fbff-130">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="5fbff-131">Azure AD 使用机器学习功能检测不正常和可疑活动，如登录和登录后活动。</span><span class="sxs-lookup"><span data-stu-id="5fbff-131">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="5fbff-132">通过使用此数据，Azure AD Identity Protection 会生成报告和警报，帮助你评估问题并执行操作。</span><span class="sxs-lookup"><span data-stu-id="5fbff-132">Using this data, Azure AD Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="5fbff-133">检测与组织身份相关的可疑操作并自动对其响应</span><span class="sxs-lookup"><span data-stu-id="5fbff-133">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="5fbff-134">可以配置基于风险的策略，该策略可在达到指定风险级别时自动响应检测到的问题。</span><span class="sxs-lookup"><span data-stu-id="5fbff-134">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="5fbff-135">除了 Azure AD 与 Microsoft Intune 提供的其他条件性访问控制以外，这些策略也可以自动阻止访问或采取纠正措施，包括密码重置和要求后续登录的 Azure 多因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="5fbff-135">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="5fbff-136">调查可疑事件并使用管理操作加以解决</span><span class="sxs-lookup"><span data-stu-id="5fbff-136">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="5fbff-p107">可以使用有关安全事件的信息来调查风险事件。提供的基本工作流可用于跟踪调查和启动修正操作（如密码重置）。</span><span class="sxs-lookup"><span data-stu-id="5fbff-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="5fbff-139">请参阅[有关 Azure AD Identity Protection 的详细信息](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。</span><span class="sxs-lookup"><span data-stu-id="5fbff-139">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="5fbff-140">请参阅[启用 Azure AD Identity Protection 的步骤](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</span><span class="sxs-lookup"><span data-stu-id="5fbff-140">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="5fbff-141">此步骤的结果是，启用了 Azure AD Identity Protection 并用它来：</span><span class="sxs-lookup"><span data-stu-id="5fbff-141">The results of this step are that you've enabled Azure AD Identity Protection and you are using it to:</span></span>

- <span data-ttu-id="5fbff-142">解决潜在标识漏洞。</span><span class="sxs-lookup"><span data-stu-id="5fbff-142">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="5fbff-143">检测可能的凭据泄露尝试。</span><span class="sxs-lookup"><span data-stu-id="5fbff-143">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="5fbff-144">调查和解决正在进行的可疑身份活动。</span><span class="sxs-lookup"><span data-stu-id="5fbff-144">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5fbff-146">测试实验室指南：Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5fbff-146">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="5fbff-147">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-ident-prot)。</span><span class="sxs-lookup"><span data-stu-id="5fbff-147">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![第 4 步](../media/stepnumbers/Step4.png)| [<span data-ttu-id="5fbff-149">添加用户帐户</span><span class="sxs-lookup"><span data-stu-id="5fbff-149">Add your user accounts</span></span>](identity-add-user-accounts.md) |
