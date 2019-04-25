---
title: 步骤 4：配置安全的用户身份验证
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并为用户帐户配置多重身份验证。
ms.openlocfilehash: 44d878a347e7b01263f9ba3a82f6443f5710dc43
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285460"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="18304-103">步骤 4：配置安全的用户身份验证</span><span class="sxs-lookup"><span data-stu-id="18304-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="18304-104">设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="18304-104">Set up multi-factor authentication.</span></span>

<span data-ttu-id="18304-105">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="18304-105">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="18304-p101">在此步骤中，你将设置多重身份验证 (MFA)，以将第二层安全添加到用户登录和交易。用户正确输入其密码后，MFA 需要其他验证方法。如果没有 MFA，密码就是唯一的验证方法。密码的问题是许多密码容易被攻击者猜出，或者在不知情的情况共享给不受信任方。</span><span class="sxs-lookup"><span data-stu-id="18304-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="18304-110">使用 MFA，第二层安全可以是：</span><span class="sxs-lookup"><span data-stu-id="18304-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="18304-111">不易被欺骗或者复制的个人和受信任设备，如智能手机。</span><span class="sxs-lookup"><span data-stu-id="18304-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="18304-112">生物识别属性，如指纹。</span><span class="sxs-lookup"><span data-stu-id="18304-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="18304-p102">将基于每个用户帐户启用 MFA 并配置辅助身份验证方法。请确保用户知道已启用 MFA，以便他们理解（如强制使用智能手机进行登录）要求并可以成功登录。</span><span class="sxs-lookup"><span data-stu-id="18304-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span>

<span data-ttu-id="18304-115">有关详细信息，请参阅[多重身份验证规划](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)。</span><span class="sxs-lookup"><span data-stu-id="18304-115">For more information, see [Plan for multi-factor authentication for Office 365 Deployments](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="18304-p103">在某些应用程序（如 Microsoft Office 2010 或更低版本和 Apple Mail）中，不能使用 MFA。若要使用这些应用，则需要使用“应用密码”代替传统密码。应用密码可使应用绕过 MFA 并继续工作。若要了解有关应用密码的详细信息，请参阅[为 Office 365 创建应用密码](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)。</span><span class="sxs-lookup"><span data-stu-id="18304-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="18304-121">测试实验室指南：多重身份验证</span><span class="sxs-lookup"><span data-stu-id="18304-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="18304-122">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-mfa)。</span><span class="sxs-lookup"><span data-stu-id="18304-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this step.</span></span>



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="18304-123">防止凭据泄露</span><span class="sxs-lookup"><span data-stu-id="18304-123">Protect against credential compromise</span></span>

<span data-ttu-id="18304-124">*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="18304-124">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="18304-125">在此部分中，将了解如何配置策略，以防止凭据泄露（攻击者可以通过确定用户帐户名称和密码来获取访问组织的云服务和数据的权限）。</span><span class="sxs-lookup"><span data-stu-id="18304-125">In this step, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span> <span data-ttu-id="18304-126">Azure AD Identity Protection 可提供多种方式来帮助阻止攻击者在帐户和组中横向移动以最终移至最有价值的数据。</span><span class="sxs-lookup"><span data-stu-id="18304-126">In this step, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="18304-127">使用 Azure AD Identity Protection，可以：</span><span class="sxs-lookup"><span data-stu-id="18304-127">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="18304-128">确定并解决组织身份中的潜在漏洞</span><span class="sxs-lookup"><span data-stu-id="18304-128">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="18304-p105">Azure AD 使用机器学习来检测异常和可疑活动（如登录和后登录活动）。使用此数据，Identity Protection 将生成报告和警报，用以帮助你评估问题并采取行动。</span><span class="sxs-lookup"><span data-stu-id="18304-p105">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="18304-131">检测与组织身份相关的可疑操作并自动对其响应</span><span class="sxs-lookup"><span data-stu-id="18304-131">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="18304-p106">可以配置基于风险的策略，以在达到指定风险级别时自动响应检测到的问题。这些策略，以及由 Azure Active Directory 和企业移动性 + 安全性 (EMS) 提供的其他条件访问控制，可自动阻止访问或采取纠正措施，包括密码重置以及要求对后续登录进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="18304-p106">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="18304-134">调查可疑事件并使用管理操作加以解决</span><span class="sxs-lookup"><span data-stu-id="18304-134">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="18304-p107">可以使用有关安全事件的信息来调查风险事件。提供的基本工作流可用于跟踪调查和启动修正操作（如密码重置）。</span><span class="sxs-lookup"><span data-stu-id="18304-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="18304-137">请参阅[有关 Azure AD Identity Protection 的详细信息](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。</span><span class="sxs-lookup"><span data-stu-id="18304-137">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="18304-138">请参阅[启用 Azure AD Identity Protection 的步骤](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</span><span class="sxs-lookup"><span data-stu-id="18304-138">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="18304-139">此步骤的结果是，启用了 Azure AD Identity Protection 并用它来：</span><span class="sxs-lookup"><span data-stu-id="18304-139">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="18304-140">解决潜在身份漏洞。</span><span class="sxs-lookup"><span data-stu-id="18304-140">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="18304-141">检测可能的凭据泄露尝试。</span><span class="sxs-lookup"><span data-stu-id="18304-141">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="18304-142">调查和解决正在进行的可疑身份活动。</span><span class="sxs-lookup"><span data-stu-id="18304-142">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="18304-144">测试实验室指南：Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="18304-144">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="18304-145">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-ident-prot)。</span><span class="sxs-lookup"><span data-stu-id="18304-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="18304-146">监控租户和登录活动</span><span class="sxs-lookup"><span data-stu-id="18304-146">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="18304-147">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="18304-147">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="18304-p108">在此步骤中，将使用 Azure AD 报告查看审核日志和登录活动。有两种类型的报告可用。</span><span class="sxs-lookup"><span data-stu-id="18304-p108">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="18304-p109">\*\*\*\* 审核日志活动报告 - 记录在 Azure AD 租户中执行的每项任务的历史记录。此报告可回答如下问题：</span><span class="sxs-lookup"><span data-stu-id="18304-p109">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="18304-152">谁将某人添加到管理员组？</span><span class="sxs-lookup"><span data-stu-id="18304-152">Who added someone to an admin group?</span></span>
- <span data-ttu-id="18304-153">哪些用户将登录到特定应用？</span><span class="sxs-lookup"><span data-stu-id="18304-153">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="18304-154">发生多少密码重置？</span><span class="sxs-lookup"><span data-stu-id="18304-154">How many password resets are happening?</span></span>

<span data-ttu-id="18304-p110">\*\*\*\* 登录活动报告 - 记录谁执行了审核日志报告所报告的任务。此报告可回答如下问题：</span><span class="sxs-lookup"><span data-stu-id="18304-p110">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="18304-157">对于调查中的特定用户，其登录模式是什么？</span><span class="sxs-lookup"><span data-stu-id="18304-157">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="18304-158">我每天、每周或每月的登录量是多少？</span><span class="sxs-lookup"><span data-stu-id="18304-158">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="18304-159">多少次登录尝试失败及其相关帐户？</span><span class="sxs-lookup"><span data-stu-id="18304-159">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="18304-160">有关报告以及如何进行访问的详细信息，请参阅 [Azure Active Directory 报告](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="18304-160">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="18304-161">通过此步骤，你将认识这些报告并了解如何使用它们洞察 Azure AD 事件和活动，以用于规划和安全目的。</span><span class="sxs-lookup"><span data-stu-id="18304-161">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>



## <a name="next-step"></a><span data-ttu-id="18304-162">后续步骤</span><span class="sxs-lookup"><span data-stu-id="18304-162">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="18304-163">简化用户访问权限</span><span class="sxs-lookup"><span data-stu-id="18304-163">Simplify access for users</span></span>](identity-password-reset.md) |

