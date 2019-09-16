---
title: 步骤 4：配置安全的用户身份验证
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并为用户帐户配置多重身份验证。
ms.openlocfilehash: 2a4a0926a08ae8279523219a2d7a2386ea0c6742
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981843"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="a7530-103">步骤 4：配置安全的用户身份验证</span><span class="sxs-lookup"><span data-stu-id="a7530-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="a7530-104">设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="a7530-104">Set up multi-factor authentication</span></span>

<span data-ttu-id="a7530-105">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a7530-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a7530-p101">在此步骤中，你将设置多重身份验证 (MFA)，以将第二层安全添加到用户登录和交易。用户正确输入其密码后，MFA 需要其他验证方法。如果没有 MFA，密码就是唯一的验证方法。密码的问题是许多密码容易被攻击者猜出，或者在不知情的情况共享给不受信任方。</span><span class="sxs-lookup"><span data-stu-id="a7530-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="a7530-110">使用 MFA，第二层安全可以是：</span><span class="sxs-lookup"><span data-stu-id="a7530-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="a7530-111">不易被欺骗或者复制的个人和受信任设备，如智能手机。</span><span class="sxs-lookup"><span data-stu-id="a7530-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="a7530-112">生物识别属性，如指纹。</span><span class="sxs-lookup"><span data-stu-id="a7530-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="a7530-113">将启用 MFA 并使用[条件访问策略](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)配置次要身份验证方法，该方法允许使用 Azure Active Directory (Azure AD) 组向指定的用户组（如试点用户、地理区域或部门）推出 MFA。</span><span class="sxs-lookup"><span data-stu-id="a7530-113">You'll enable MFA and configure the secondary authentication method with [conditional access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="a7530-114">请确保用户知道已启用 MFA，以便他们理解要求（如强制使用智能手机进行登录）并可以成功登录。</span><span class="sxs-lookup"><span data-stu-id="a7530-114">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="a7530-115">有关详细信息，请参阅[多重身份验证规划](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)。</span><span class="sxs-lookup"><span data-stu-id="a7530-115">For more information, see [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="a7530-p103">在某些应用程序（如 Microsoft Office 2010 或更低版本和 Apple Mail）中，不能使用 MFA。若要使用这些应用，则需要使用“应用密码”代替传统密码。应用密码可使应用绕过 MFA 并继续工作。若要了解有关应用密码的详细信息，请参阅[为 Office 365 创建应用密码](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)。</span><span class="sxs-lookup"><span data-stu-id="a7530-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a7530-121">测试实验室指南：多重身份验证</span><span class="sxs-lookup"><span data-stu-id="a7530-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="a7530-122">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-mfa)。</span><span class="sxs-lookup"><span data-stu-id="a7530-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="a7530-123">防止密码错误</span><span class="sxs-lookup"><span data-stu-id="a7530-123">Prevent bad passwords</span></span>

<span data-ttu-id="a7530-124">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a7530-124">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a7530-125">若要防止用户创建易于确定的密码，请使用 Azure AD 密码保护，该功能同时使用全局阻止密码列表和你指定的可选的自定义禁止密码列表。</span><span class="sxs-lookup"><span data-stu-id="a7530-125">To prevent users from creating easily determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="a7530-126">例如，你可以指定特定于贵公司的术语，例如</span><span class="sxs-lookup"><span data-stu-id="a7530-126">For example, you can specify terms that are specific to your organization, such as"</span></span>

- <span data-ttu-id="a7530-127">品牌名称</span><span class="sxs-lookup"><span data-stu-id="a7530-127">Brand names</span></span>
- <span data-ttu-id="a7530-128">产品名称</span><span class="sxs-lookup"><span data-stu-id="a7530-128">Product names</span></span>
- <span data-ttu-id="a7530-129">位置（例如公司总部）</span><span class="sxs-lookup"><span data-stu-id="a7530-129">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="a7530-130">特定于公司的内部条款</span><span class="sxs-lookup"><span data-stu-id="a7530-130">Company-specific internal terms</span></span>
- <span data-ttu-id="a7530-131">具有特定公司含义的缩写。</span><span class="sxs-lookup"><span data-stu-id="a7530-131">Abbreviations that have specific company meaning.</span></span>

<span data-ttu-id="a7530-132">可[在云端](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)和[本地 Active Directory 域服务 (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)中禁止错误密码。</span><span class="sxs-lookup"><span data-stu-id="a7530-132">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="a7530-133">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-password-prot)。</span><span class="sxs-lookup"><span data-stu-id="a7530-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="a7530-134">防止凭据泄露</span><span class="sxs-lookup"><span data-stu-id="a7530-134">Protect against credential compromise</span></span>

<span data-ttu-id="a7530-135">*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a7530-135">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a7530-136">在此部分中，将了解如何配置策略，以防止凭据泄露（攻击者可以通过确定用户帐户名称和密码来获取访问组织的云服务和数据的权限）。</span><span class="sxs-lookup"><span data-stu-id="a7530-136">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="a7530-137">Azure AD Identity Protection 可提供多种方式来帮助阻止攻击者在帐户和组中横向移动以最终移至最有价值的数据。</span><span class="sxs-lookup"><span data-stu-id="a7530-137">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="a7530-138">使用 Azure AD Identity Protection，可以：</span><span class="sxs-lookup"><span data-stu-id="a7530-138">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="a7530-139">确定并解决组织身份中的潜在漏洞</span><span class="sxs-lookup"><span data-stu-id="a7530-139">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="a7530-140">Azure AD 使用机器学习功能检测不正常和可疑活动，如登录和登录后活动。</span><span class="sxs-lookup"><span data-stu-id="a7530-140">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span> <span data-ttu-id="a7530-141">通过使用此数据，Azure AD Identity Protection 会生成报告和警报，帮助你评估问题并执行操作。</span><span class="sxs-lookup"><span data-stu-id="a7530-141">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="a7530-142">检测与组织身份相关的可疑操作并自动对其响应</span><span class="sxs-lookup"><span data-stu-id="a7530-142">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="a7530-143">可以配置基于风险的策略，该策略可在达到指定风险级别时自动响应检测到的问题。</span><span class="sxs-lookup"><span data-stu-id="a7530-143">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="a7530-144">除了 Azure AD 与 Microsoft Intune 提供的其他条件性访问控制以外，这些策略也可以自动阻止访问或采取纠正措施，包括密码重置和要求后续登录的多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="a7530-144">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="a7530-145">调查可疑事件并使用管理操作加以解决</span><span class="sxs-lookup"><span data-stu-id="a7530-145">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="a7530-p108">可以使用有关安全事件的信息来调查风险事件。提供的基本工作流可用于跟踪调查和启动修正操作（如密码重置）。</span><span class="sxs-lookup"><span data-stu-id="a7530-p108">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="a7530-148">请参阅[有关 Azure AD Identity Protection 的详细信息](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。</span><span class="sxs-lookup"><span data-stu-id="a7530-148">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="a7530-149">请参阅[启用 Azure AD Identity Protection 的步骤](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</span><span class="sxs-lookup"><span data-stu-id="a7530-149">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="a7530-150">此步骤的结果是，启用了 Azure AD Identity Protection 并用它来：</span><span class="sxs-lookup"><span data-stu-id="a7530-150">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="a7530-151">解决潜在身份漏洞。</span><span class="sxs-lookup"><span data-stu-id="a7530-151">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="a7530-152">检测可能的凭据泄露尝试。</span><span class="sxs-lookup"><span data-stu-id="a7530-152">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="a7530-153">调查和解决正在进行的可疑身份活动。</span><span class="sxs-lookup"><span data-stu-id="a7530-153">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a7530-155">测试实验室指南：Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="a7530-155">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="a7530-156">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-ident-prot)。</span><span class="sxs-lookup"><span data-stu-id="a7530-156">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="a7530-157">监控租户和登录活动</span><span class="sxs-lookup"><span data-stu-id="a7530-157">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="a7530-158">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a7530-158">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a7530-p109">在此步骤中，将使用 Azure AD 报告查看审核日志和登录活动。有两种类型的报告可用。</span><span class="sxs-lookup"><span data-stu-id="a7530-p109">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="a7530-p110">\*\*\*\* 审核日志活动报告 - 记录在 Azure AD 租户中执行的每项任务的历史记录。此报告可回答如下问题：</span><span class="sxs-lookup"><span data-stu-id="a7530-p110">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="a7530-163">谁将某人添加到管理员组？</span><span class="sxs-lookup"><span data-stu-id="a7530-163">Who added someone to an admin group?</span></span>
- <span data-ttu-id="a7530-164">哪些用户将登录到特定应用？</span><span class="sxs-lookup"><span data-stu-id="a7530-164">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="a7530-165">发生多少密码重置？</span><span class="sxs-lookup"><span data-stu-id="a7530-165">How many password resets are happening?</span></span>

<span data-ttu-id="a7530-p111">\*\*\*\* 登录活动报告 - 记录谁执行了审核日志报告所报告的任务。此报告可回答如下问题：</span><span class="sxs-lookup"><span data-stu-id="a7530-p111">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="a7530-168">对于调查中的特定用户，其登录模式是什么？</span><span class="sxs-lookup"><span data-stu-id="a7530-168">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="a7530-169">我每天、每周或每月的登录量是多少？</span><span class="sxs-lookup"><span data-stu-id="a7530-169">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="a7530-170">多少次登录尝试失败及其相关帐户？</span><span class="sxs-lookup"><span data-stu-id="a7530-170">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="a7530-171">有关报告以及如何进行访问的详细信息，请参阅 [Azure Active Directory 报告](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="a7530-171">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="a7530-172">通过此步骤，你将认识这些报告并了解如何使用它们洞察 Azure AD 事件和活动，以用于规划和安全目的。</span><span class="sxs-lookup"><span data-stu-id="a7530-172">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="a7530-173">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a7530-173">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="a7530-174">简化用户访问权限</span><span class="sxs-lookup"><span data-stu-id="a7530-174">Simplify access for users</span></span>](identity-password-reset.md) |

