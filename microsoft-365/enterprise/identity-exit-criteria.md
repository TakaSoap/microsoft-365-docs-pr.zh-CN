---
title: 阶段 2：身份基础结构退出条件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 确保你的配置符合 Microsoft 365 企业版针对基于身份的服务和基础结构的条件。
ms.openlocfilehash: 49ba7801b740b2a1cfd77955517646ee80174712
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866003"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="1c241-103">阶段 2：身份基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="1c241-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="1c241-p101">转到第 3 阶段之前，请确保你的身份基础结构满足这些条件。另请参阅[先决条件](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites)，以了解有关身份基础结构的其他建议。</span><span class="sxs-lookup"><span data-stu-id="1c241-p101">Before you move on to Phase 3, make sure that your identity infrastructure meets these conditions. Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-user-groups"></a>
## <a name="required-all-users-groups-and-group-memberships-have-been-created"></a><span data-ttu-id="1c241-106">必需：已创建所有用户、组和组成员身份</span><span class="sxs-lookup"><span data-stu-id="1c241-106">Required: All users, groups, and group memberships have been created</span></span>

<span data-ttu-id="1c241-107">已创建用户帐户和组，以便：</span><span class="sxs-lookup"><span data-stu-id="1c241-107">You've created user accounts and groups so that:</span></span>

- <span data-ttu-id="1c241-108">组织内的员工和供应商、承包商以及与组织协同工作的合作伙伴在 Azure Active Directory (AD) 中具有相应的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1c241-108">Employees in your organization and the vendors, contractors, and partners that work for or with your organization have a corresponding user account in Azure Active Directory (AD).</span></span>
- <span data-ttu-id="1c241-109">Azure AD 组及其成员包含用于各种用途的用户帐户和其他组，如 Microsoft 云服务的安全设置预配、自动许可和其他用途。</span><span class="sxs-lookup"><span data-stu-id="1c241-109">Azure AD groups and their members contain user accounts and other groups for various purposes, such as the provisioning of security settings for Microsoft cloud services, automatic licensing, and other uses.</span></span>

<span data-ttu-id="1c241-110">如果需要，可在[步骤 1](identity-plan-users-groups.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="1c241-110">If needed, [Step 1](identity-plan-users-groups.md) can help you meet this requirement.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="1c241-111">必需：用户和组与 Azure AD 已同步</span><span class="sxs-lookup"><span data-stu-id="1c241-111">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="1c241-112">如果你有现有的本地标识提供者，如 Windows Server Active Directory (AD)，则已使用 Azure AD Connect 将用户帐户和组从本地标识提供者同步到 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="1c241-112">If you have an existing on-premises identity provider, such as Windows Server Active Directory (AD), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="1c241-113">通过目录同步，你的用户可以使用与登录到其计算机相同的凭据登录到 Office 365 和其他 Microsoft 云服务，并访问本地资源。</span><span class="sxs-lookup"><span data-stu-id="1c241-113">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="1c241-114">如果需要，请执行[步骤 7](identity-azure-ad-connect.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="1c241-114">If needed, [Step 7](identity-azure-ad-connect.md) can help you meet this requirement.</span></span>

<span data-ttu-id="1c241-115">如果忽略此要求，将具有两组用户帐户和组：</span><span class="sxs-lookup"><span data-stu-id="1c241-115">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="1c241-116">位于本地标识提供者的用户帐户和组</span><span class="sxs-lookup"><span data-stu-id="1c241-116">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="1c241-117">位于 Azure AD 租户组的用户帐户和组</span><span class="sxs-lookup"><span data-stu-id="1c241-117">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="1c241-p102">在此状态下，两组用户帐户和组必须由 IT 管理员和用户手动维护。这会不可避免地导致帐户、密码和组不同步。</span><span class="sxs-lookup"><span data-stu-id="1c241-p102">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c241-120">如何测试</span><span class="sxs-lookup"><span data-stu-id="1c241-120">How to test</span></span>
<span data-ttu-id="1c241-121">要验证本地凭据身份验证是否正常运行，请使用本地凭据登录到 Office 365 门户。</span><span class="sxs-lookup"><span data-stu-id="1c241-121">To verify that authentication with on-premises credentials works correctly, sign in to the Office 365 portal with your on-premises credentials.</span></span>

<span data-ttu-id="1c241-122">要验证目录同步正常运行，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1c241-122">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="1c241-123">在 Windows Server AD 中创建新的测试组。</span><span class="sxs-lookup"><span data-stu-id="1c241-123">Create a new test group in Windows Server AD.</span></span>
2.  <span data-ttu-id="1c241-124">等待同步时间。</span><span class="sxs-lookup"><span data-stu-id="1c241-124">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="1c241-125">检查 Azure AD 租户以验证新测试组的名称是否出现。</span><span class="sxs-lookup"><span data-stu-id="1c241-125">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="1c241-126">必需：全局管理员帐户受到保护</span><span class="sxs-lookup"><span data-stu-id="1c241-126">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="1c241-127">已[保护 Office 365 全局管理员帐户](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560)，以避免凭据泄露，进而可能导致 Office 365 订阅漏洞。</span><span class="sxs-lookup"><span data-stu-id="1c241-127">You've [protected your Office 365 global administrator accounts](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560) to avoid compromising credentials that can lead to breaches of an Office 365 subscription.</span></span>

<span data-ttu-id="1c241-128">如果忽略此要求，全局管理员帐户很容易受到攻击和入侵，攻击者可以获取系统范围内的数据访问权限并加以收集、销毁或勒索。</span><span class="sxs-lookup"><span data-stu-id="1c241-128">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="1c241-129">如果需要，请执行[步骤 2](identity-designate-protect-admin-accounts.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="1c241-129">If needed, [Step 2](identity-designate-protect-admin-accounts.md) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c241-130">如何测试</span><span class="sxs-lookup"><span data-stu-id="1c241-130">How to test</span></span>

<span data-ttu-id="1c241-131">使用这些步骤验证是否已保护全局管理员帐户：</span><span class="sxs-lookup"><span data-stu-id="1c241-131">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="1c241-p103">在 PowerShell 命令提示符处运行以下 Azure AD V2 命令。应仅看到专用全局管理员帐户列表。</span><span class="sxs-lookup"><span data-stu-id="1c241-p103">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="1c241-p104">使用步骤 1 中的每个帐户登录到 Office 365。每个登录必须要求多重身份验证和组织中可用的最强形式的辅助身份验证。</span><span class="sxs-lookup"><span data-stu-id="1c241-p104">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="1c241-136">有关安装 Azure AD V2 PowerShell 模块和登录到 Office 365 的说明，请参阅[连接到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1c241-136">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in to Office 365.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="1c241-137">可选：个性化组织的 Office 365 登录屏幕</span><span class="sxs-lookup"><span data-stu-id="1c241-137">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="1c241-138">你已使用[将公司品牌添加到登录和访问面板页面](http://aka.ms/aadpaddbranding)，将组织的品牌添加到 Office 365 登录页面。</span><span class="sxs-lookup"><span data-stu-id="1c241-138">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="1c241-139">如果忽略此选项，你的用户将看到通用的 Office 365 登录屏幕，可能会让他们疑惑是否登录到了组织的网站。</span><span class="sxs-lookup"><span data-stu-id="1c241-139">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="1c241-140">如果需要，可在[步骤 11](identity-customize-office-365-sign-in.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1c241-140">If needed, [Step 11](identity-customize-office-365-sign-in.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c241-141">测试操作</span><span class="sxs-lookup"><span data-stu-id="1c241-141">How to test</span></span>

<span data-ttu-id="1c241-p105">使用用户帐户名称及多重身份验证登录到 Office 365 门户。应在登录页面上看到自定义的品牌元素。</span><span class="sxs-lookup"><span data-stu-id="1c241-p105">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>

<a name="crit-identity-mfa"></a>
## <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="1c241-144">可选：已为你的用户启用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="1c241-144">Optional: Multi-factor authentication is enabled for your users</span></span>

<span data-ttu-id="1c241-145">已使用 [Office 365 部署的多重身份验证计划](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)和[为 Office 365 用户设置多因素身份验证](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)，以为用户帐户启用多重身份验证 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="1c241-145">You used [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba) and [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) to enable multifactor authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="1c241-p106">如果忽略此选项，你的用户帐户会很容易受到网络攻击者的攻击，导致凭据泄露。如果用户帐户的密码遭到破坏，帐户的所有资源和功能（如管理员角色）都可供攻击者使用。这会使得攻击者能够复制、销毁或持有内部文档和其他数据，进而进行勒索。</span><span class="sxs-lookup"><span data-stu-id="1c241-p106">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="1c241-149">如果需要，可在[步骤 5](identity-multi-factor-authentication.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1c241-149">If needed, [Step 5](identity-multi-factor-authentication.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c241-150">如何测试</span><span class="sxs-lookup"><span data-stu-id="1c241-150">How to test</span></span>

1.  <span data-ttu-id="1c241-151">在 Office 365 管理门户中创建一个测试用户帐户并对其分配许可证。</span><span class="sxs-lookup"><span data-stu-id="1c241-151">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="1c241-152">通过用于真实用户帐户的其他验证方法为测试用户帐户配置多重身份验证，如向手机发送消息。</span><span class="sxs-lookup"><span data-stu-id="1c241-152">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="1c241-153">通过测试用户帐户登录到 Office 365 或 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="1c241-153">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="1c241-154">确保 MFA 提示你输入其他验证信息且身份验证成功。</span><span class="sxs-lookup"><span data-stu-id="1c241-154">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="1c241-155">删除该测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1c241-155">Delete the test user account.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="1c241-156">可选：监控目录同步</span><span class="sxs-lookup"><span data-stu-id="1c241-156">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="1c241-157">已使用[使用 Azure AD Connect Health 进行同步](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)（适用于密码同步）或[在 AD FS 中使用 Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)（适用于联合身份验证），并部署了 Azure 的 AD Connect Health，其中涉及：</span><span class="sxs-lookup"><span data-stu-id="1c241-157">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="1c241-158">在每个本地标识服务器上安装 Azure AD Connect Health 代理。</span><span class="sxs-lookup"><span data-stu-id="1c241-158">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="1c241-159">使用 Azure AD Connect Health 门户监控持续同步的状态。</span><span class="sxs-lookup"><span data-stu-id="1c241-159">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="1c241-160">如果忽略此选项，则可以更准确地评估基于云的身份基础结构状态。</span><span class="sxs-lookup"><span data-stu-id="1c241-160">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="1c241-161">如果需要，可在[步骤 8](identity-azure-ad-connect-health.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1c241-161">If needed, [Step 8](identity-azure-ad-connect-health.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c241-162">如何测试</span><span class="sxs-lookup"><span data-stu-id="1c241-162">How to test</span></span>
<span data-ttu-id="1c241-163">Azure AD Connect Health 门户显示本地标识服务器和持续同步的当前和正确状态。</span><span class="sxs-lookup"><span data-stu-id="1c241-163">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="1c241-164">可选：用户可以重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="1c241-164">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="1c241-165">已使用 [Azure AD 自助密码重置快速部署](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)，为你的用户配置密码重置。</span><span class="sxs-lookup"><span data-stu-id="1c241-165">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="1c241-166">如果不符合此条件，用户将依赖用户帐户管理员来重置其密码，这会导致额外的 IT 管理开销。</span><span class="sxs-lookup"><span data-stu-id="1c241-166">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="1c241-167">如果需要，可在[步骤 4](identity-password-reset.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1c241-167">If needed, [Step 4](identity-password-reset.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c241-168">如何测试</span><span class="sxs-lookup"><span data-stu-id="1c241-168">How to test</span></span>

1. <span data-ttu-id="1c241-169">创建包含初始密码的测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1c241-169">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="1c241-170">使用[让用户在 Office 365 中重置自己的密码](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a)中的步骤来重置测试用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="1c241-170">Use the steps in [Let users reset their own passwords in Office 365](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="1c241-171">注销，然后使用重置密码登录到测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1c241-171">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="1c241-172">删除该测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1c241-172">Delete the test user account.</span></span>

<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="1c241-173">可选：为你的用户启用密码写回功能</span><span class="sxs-lookup"><span data-stu-id="1c241-173">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="1c241-174">已使用 [Azure AD SSPR 密码写回](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)中的说明为 Microsoft 365 企业版订阅的 Azure AD 租户启用密码写回。</span><span class="sxs-lookup"><span data-stu-id="1c241-174">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="1c241-175">如果忽略此选项，未连接到本地网络的用户必须通过 IT 管理员重置或解除锁定其 Windows Server AD 密码。</span><span class="sxs-lookup"><span data-stu-id="1c241-175">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their Windows Server AD passwords through an IT administrator.</span></span>

<span data-ttu-id="1c241-176">如果需要，可在[步骤 9](identity-password-writeback.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1c241-176">If needed, [Step 9](identity-password-writeback.md) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="1c241-177">需要密码写回才可充分利用 Azure AD Identity Protection 功能，例如，当 Azure AD 检测到高风险的帐户泄露时要求用户更改其本地密码。</span><span class="sxs-lookup"><span data-stu-id="1c241-177">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="1c241-178">测试操作</span><span class="sxs-lookup"><span data-stu-id="1c241-178">How to test</span></span>

<span data-ttu-id="1c241-p107">通过在 Office 365 中更改密码来测试密码写回。你应能够使用帐户和新的密码来访问本地 Windows Server AD 资源。</span><span class="sxs-lookup"><span data-stu-id="1c241-p107">You test password writeback by changing your password in Office 365. You should be able to use your account and new password to access on-premises Windows Server AD resources.</span></span>

1. <span data-ttu-id="1c241-181">在本地 Windows Server AD 中创建测试用户帐户，允许进行目录同步，然后在 Office 365 管理门户中授予 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="1c241-181">Create a test user account in your on-premises Windows Server AD, allow directory synchronization to occur, and then grant it an Office 365 license in the Office 365 admin portal.</span></span>
2. <span data-ttu-id="1c241-182">从加入到本地 Windows Server AD 域的远程计算机，使用测试用户帐户的凭据登录到计算机和 Office 365 门户。</span><span class="sxs-lookup"><span data-stu-id="1c241-182">From a remote computer that is joined to your on-premises Windows Server AD domain, sign in to the computer and the Office 365 portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="1c241-183">选择“设置 > Office 365 设置 > 密码 > 更改密码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1c241-183">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="1c241-184">键入当前密码、键入新密码，然后确认。</span><span class="sxs-lookup"><span data-stu-id="1c241-184">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="1c241-p108">注销 Office 365 门户和远程计算机，然后使用测试用户帐户及其新密码登录到计算机。这可证明你是否能够使用 Azure AD 租户更改本地 Windows Server AD 用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="1c241-p108">Sign out of the Office 365 portal and the remote computer and then sign in to the computer using the test user account and its new password. This proves that you were able to change the password of an on-premises Windows Server AD user account using the Azure AD tenant.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-single-sign-on"></a><span data-ttu-id="1c241-187">可选：用户可以使用单一登录进行登录</span><span class="sxs-lookup"><span data-stu-id="1c241-187">Optional: Users can sign in using single sign-on</span></span>

<span data-ttu-id="1c241-188">已为组织启用 [Azure AD Connect: 无缝单一登录](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)，以简化用户登录到基于云的应用程序（如 Office 365）的方式。</span><span class="sxs-lookup"><span data-stu-id="1c241-188">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="1c241-189">如果忽略此选项，当用户访问使用 Azure AD 的其他应用程序时，系统可能会提示你的用户提供凭据。</span><span class="sxs-lookup"><span data-stu-id="1c241-189">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="1c241-190">如果需要，可在[步骤 10](identity-single-sign-on.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1c241-190">If needed, [Step 10](identity-single-sign-on.md) can help you with this option.</span></span>


<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="1c241-191">可选：基于组的许可能够根据组成员身份自动分配和删除用户帐户的许可证</span><span class="sxs-lookup"><span data-stu-id="1c241-191">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="1c241-192">为相应 Azure AD 安全组[启用基于组的许可](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)，以便自动分配或删除适用于 Office 365 和 EMS 的许可证。</span><span class="sxs-lookup"><span data-stu-id="1c241-192">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="1c241-193">如果忽略此选项，则必须手动：</span><span class="sxs-lookup"><span data-stu-id="1c241-193">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="1c241-194">向希望访问 Office 365 和 EMS 的新用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="1c241-194">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="1c241-195">删除不再属于你的组织或不再有权访问 Office 365 和 EMS 的用户许可证。</span><span class="sxs-lookup"><span data-stu-id="1c241-195">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="1c241-196">如果需要，可在[步骤 12](identity-group-based-licensing.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1c241-196">If needed, [Step 12](identity-group-based-licensing.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c241-197">如何测试</span><span class="sxs-lookup"><span data-stu-id="1c241-197">How to test</span></span>

1. <span data-ttu-id="1c241-198">在具有 Azure 门户的 Azure AD 中创建测试安全组，并配置基于组的许可来分配 Office 365 和 EMS 许可证。</span><span class="sxs-lookup"><span data-stu-id="1c241-198">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="1c241-199">在 Azure AD 中创建测试用户帐户并将其添加到测试安全组。</span><span class="sxs-lookup"><span data-stu-id="1c241-199">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="1c241-200">在 Office 365 管理门户中检查用户帐户的属性，确保其分配了 Office 365 和 EMS 许可证。</span><span class="sxs-lookup"><span data-stu-id="1c241-200">Examine the properties of the user account in the Office 365 admin portal to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="1c241-201">从测试安全组删除测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1c241-201">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="1c241-202">检查用户帐户的属性，确保它不再分配有 Office 365 和 EMS 许可证。</span><span class="sxs-lookup"><span data-stu-id="1c241-202">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="1c241-203">删除测试安全组和测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1c241-203">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="1c241-204">可选：动态组成员身份设置根据用户帐户属性自动将用户帐户添加到组</span><span class="sxs-lookup"><span data-stu-id="1c241-204">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="1c241-205">你已确定 Azure AD 动态组集并使用 [Azure Active Directory 中基于属性的动态组成员身份](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)中的说明来创建组和规则（用于确定用户帐户属性集和组成员身份值）。</span><span class="sxs-lookup"><span data-stu-id="1c241-205">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="1c241-p109">如果忽略此选项，则随着添加新帐户或更改用户帐户属性，需要手动设置组成员身份。例如，如果某人从销售部门移动到会计部门，则必须：</span><span class="sxs-lookup"><span data-stu-id="1c241-p109">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="1c241-208">更新该用户帐户的部门属性值。</span><span class="sxs-lookup"><span data-stu-id="1c241-208">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="1c241-209">从销售组中手动删除此人。</span><span class="sxs-lookup"><span data-stu-id="1c241-209">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="1c241-210">手动将其添加到会计组。</span><span class="sxs-lookup"><span data-stu-id="1c241-210">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="1c241-211">如果销售和会计组是动态的，只需更改该用户帐户的部门值即可。</span><span class="sxs-lookup"><span data-stu-id="1c241-211">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="1c241-212">如果需要，可在[步骤 15](identity-automatic-group-membership.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1c241-212">If needed, [Step 15](identity-automatic-group-membership.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c241-213">测试操作</span><span class="sxs-lookup"><span data-stu-id="1c241-213">How to test</span></span>

1. <span data-ttu-id="1c241-214">在具有 Azure 门户的 Azure AD 中创建测试动态组，并对名为“test1”的部门配置规则。</span><span class="sxs-lookup"><span data-stu-id="1c241-214">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="1c241-215">在 Azure AD 中创建测试用户帐户并将部门属性设为“test1”。</span><span class="sxs-lookup"><span data-stu-id="1c241-215">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="1c241-216">检查用户帐户属性，以确保其已成为测试动态组的成员。</span><span class="sxs-lookup"><span data-stu-id="1c241-216">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="1c241-217">将测试用户帐户的部门属性值更改为“test2”。</span><span class="sxs-lookup"><span data-stu-id="1c241-217">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="1c241-218">检查用户帐户属性，以确保其不再是测试动态组的成员。</span><span class="sxs-lookup"><span data-stu-id="1c241-218">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="1c241-219">删除测试动态组和测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1c241-219">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="1c241-220">可选：为特定 Azure AD 安全和 Office 365 组启用了自助服务组管理</span><span class="sxs-lookup"><span data-stu-id="1c241-220">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="1c241-221">已确定哪些组适用于自助服务管理，对所有者说明了组管理工作流和职责，并为这些组[在 Azure AD 中设置自助服务管理](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。</span><span class="sxs-lookup"><span data-stu-id="1c241-221">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="1c241-222">如果忽略此选项，则所有 Azure AD 组管理任务必须由 IT 管理员执行。</span><span class="sxs-lookup"><span data-stu-id="1c241-222">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="1c241-223">如果需要，可在[步骤 14](identity-self-service-group-management.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1c241-223">If needed, [Step 14](identity-self-service-group-management.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="1c241-224">如何测试</span><span class="sxs-lookup"><span data-stu-id="1c241-224">How to test</span></span>
1.  <span data-ttu-id="1c241-225">在具有 Azure 门户的 Azure AD 中创建测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1c241-225">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="1c241-226">使用测试用户帐户登录并创建测试 Azure AD 安全组。</span><span class="sxs-lookup"><span data-stu-id="1c241-226">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="1c241-227">注销，然后使用 IT 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="1c241-227">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="1c241-228">针对测试用户帐户，配置测试安全组进行自助服务管理。</span><span class="sxs-lookup"><span data-stu-id="1c241-228">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="1c241-229">注销，然后使用测试用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="1c241-229">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="1c241-230">使用 Azure 门户将成员添加到测试安全组。</span><span class="sxs-lookup"><span data-stu-id="1c241-230">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="1c241-231">删除测试安全组和测试用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1c241-231">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise"></a><span data-ttu-id="1c241-232">可选：启用了 Azure AD Identity Protection 以防止凭据泄露</span><span class="sxs-lookup"><span data-stu-id="1c241-232">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="1c241-233">已启用 Azure AD Identity Protection，可以：</span><span class="sxs-lookup"><span data-stu-id="1c241-233">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="1c241-234">解决潜在标识漏洞。</span><span class="sxs-lookup"><span data-stu-id="1c241-234">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="1c241-235">检测可能的凭据泄露尝试。</span><span class="sxs-lookup"><span data-stu-id="1c241-235">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="1c241-236">调查和处理正在进行的可疑标识活动。</span><span class="sxs-lookup"><span data-stu-id="1c241-236">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="1c241-p110">如果忽略此选项，你将无法检测或自动阻止凭据泄露尝试或调查标识相关的安全事件。这可能会使你的组织很容易受到凭据泄露的攻击，进而对组织的敏感数据造成威胁。</span><span class="sxs-lookup"><span data-stu-id="1c241-p110">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="1c241-239">如果需要，可在[步骤 6](identity-azure-ad-identity-protection.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1c241-239">If needed, [Step 6](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="1c241-240">可选：已经设置了 Privileged Identity Management，以支持按需分配全局管理员角色</span><span class="sxs-lookup"><span data-stu-id="1c241-240">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="1c241-241">已使用[配置 Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) 中的说明，在 Azure AD 租户中启用 PIM 并将全局管理员帐户配置为符合条件的管理员。</span><span class="sxs-lookup"><span data-stu-id="1c241-241">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="1c241-242">已使用[针对 Azure AD 中混合部署和云部署的特权访问安全](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)中的建议制定路线图，以确保特权访问能够防止网络攻击者。</span><span class="sxs-lookup"><span data-stu-id="1c241-242">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="1c241-243">如果忽略此选项，全局管理员帐户可能会受到持续在线攻击，并且如果泄露，将使得攻击者能够获取、销毁或持有敏感信息进行勒索。</span><span class="sxs-lookup"><span data-stu-id="1c241-243">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="1c241-244">如果需要，可在[步骤 3](identity-azure-ad-identity-protection.md) 中设置此选项。</span><span class="sxs-lookup"><span data-stu-id="1c241-244">If needed, [Step 3](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>


## <a name="next-phase"></a><span data-ttu-id="1c241-245">下一阶段</span><span class="sxs-lookup"><span data-stu-id="1c241-245">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="1c241-246">Microsoft 365 企业版端到端部署过程中的下一个阶段是 [Windows 10 企业版](windows10-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="1c241-246">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

