---
title: 步骤 5：简化用户访问权限
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Azure AD 自助密码重置 (SSPR)。
ms.openlocfilehash: b57291aabf1b51e7866dba10ba50eacc27291a2a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073722"
---
# <a name="step-5-simplify-access-for-users"></a><span data-ttu-id="a2673-103">步骤 5：简化用户访问权限</span><span class="sxs-lookup"><span data-stu-id="a2673-103">Step 5: Simplify access for users</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="a2673-104">简化密码更新</span><span class="sxs-lookup"><span data-stu-id="a2673-104">Simplify password updates</span></span>

<span data-ttu-id="a2673-105">*这对于混合环境来说是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a2673-105">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a2673-106">在此部分中，将允许用户通过 Azure Active Directory (AD) 重置其密码，然后复制到本地 Active Directory 域服务 (AD DS)。</span><span class="sxs-lookup"><span data-stu-id="a2673-106">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="a2673-107">此过程称为密码写回。</span><span class="sxs-lookup"><span data-stu-id="a2673-107">This process is known as password writeback.</span></span> <span data-ttu-id="a2673-108">通过密码写回，用户不需要通过本地 AD DS（用户帐户及其属性的存储位置）更新其密码。</span><span class="sxs-lookup"><span data-stu-id="a2673-108">With password writeback, users don’t need to update their passwords through the on-premises Active Directory Domain Services (AD DS) where user accounts and their attributes are stored.</span></span> <span data-ttu-id="a2673-109">这非常适用于对本地网络没有远程访问连接的漫游或远程用户。</span><span class="sxs-lookup"><span data-stu-id="a2673-109">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="a2673-110">需要密码写回才可充分利用 Identity Protection 功能，例如，当检测到高风险的帐户泄露时要求用户更改其本地密码。</span><span class="sxs-lookup"><span data-stu-id="a2673-110">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="a2673-111">有关其他信息和配置说明，请参阅 [Azure AD SSPR 密码写回](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)。</span><span class="sxs-lookup"><span data-stu-id="a2673-111">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="a2673-p102">升级到最新版本的 Azure AD Connect，以确保即时获取最佳体验和新功能。有关详细信息，请参阅 [Azure AD Connect 自定义安装](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。</span><span class="sxs-lookup"><span data-stu-id="a2673-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a2673-115">测试实验室指南：密码写回</span><span class="sxs-lookup"><span data-stu-id="a2673-115">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="a2673-116">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-pw-writeback)。</span><span class="sxs-lookup"><span data-stu-id="a2673-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="a2673-117">简化密码重置</span><span class="sxs-lookup"><span data-stu-id="a2673-117">Simplify password resets</span></span>

<span data-ttu-id="a2673-118">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a2673-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a2673-119">在此部分中，将启用自助密码重置 (SSPR)，以允许用户重置或解除锁定其密码或帐户。</span><span class="sxs-lookup"><span data-stu-id="a2673-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="a2673-120">为提醒你避免误用或滥用，可以使用详细报告，跟踪用户访问系统的时间，并进行通知。</span><span class="sxs-lookup"><span data-stu-id="a2673-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="a2673-121">必须先启用密码写回，然后才能部署密码重置。</span><span class="sxs-lookup"><span data-stu-id="a2673-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="a2673-122">请参阅[推出密码重置说明](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。</span><span class="sxs-lookup"><span data-stu-id="a2673-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a2673-124">测试实验室指南：密码重置</span><span class="sxs-lookup"><span data-stu-id="a2673-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="a2673-125">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-pw-reset)。</span><span class="sxs-lookup"><span data-stu-id="a2673-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="a2673-126">简化用户登录</span><span class="sxs-lookup"><span data-stu-id="a2673-126">Simplify user sign-in</span></span>

<span data-ttu-id="a2673-127">*这对于混合环境来说是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a2673-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a2673-128">在此部分中，将设置 Azure Active Directory 无缝单一登录（Azure AD 无缝 SSO），以允许用户登录到使用 Azure AD 用户帐户的服务，而无需键入其密码（在许多情况下，还无需键入用户名）。</span><span class="sxs-lookup"><span data-stu-id="a2673-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="a2673-129">这可使用户更方便地访问基于云的应用程序（如 Office 365）而无需任何额外的本地组件（如联合身份验证服务器）。</span><span class="sxs-lookup"><span data-stu-id="a2673-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="a2673-130">将使用 Azure AD Connect 工具配置 Azure AD 无缝 SSO。</span><span class="sxs-lookup"><span data-stu-id="a2673-130">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="a2673-131">请参阅[配置 Azure AD 无缝 SSO 说明](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。</span><span class="sxs-lookup"><span data-stu-id="a2673-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a2673-133">测试实验室指南：Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="a2673-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="a2673-134">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-sso)。</span><span class="sxs-lookup"><span data-stu-id="a2673-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="a2673-135">自定义 Office 365 登录页</span><span class="sxs-lookup"><span data-stu-id="a2673-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="a2673-136">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a2673-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a2673-137">在此部分中，将帮助用户通过添加公司名称、徽标和其他可识别元素来识别组织的登录页。</span><span class="sxs-lookup"><span data-stu-id="a2673-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="a2673-138">使用 Microsoft 365 企业版，可以自定义登录页和访问面板页的外观，使其包含公司徽标、配色方案和自定义用户信息。</span><span class="sxs-lookup"><span data-stu-id="a2673-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="a2673-139">当用户试图从设备登录时，在自定义之前\*\*，他们会在 Office 365 登录页上看到类似以下示例的内容。</span><span class="sxs-lookup"><span data-stu-id="a2673-139">When a user attempts to sign in from a device, they see something like the following example on the Office 365 sign-in page *before customization*.</span></span>

![自定义之前的 Office 365 登录页示例](./media/identity-customize-office-365-sign-in/id-step01-sign-in-before.png)

<span data-ttu-id="a2673-141">下面是在自定义之后\*\* Contoso Corporation 的同一用户会看到的内容。</span><span class="sxs-lookup"><span data-stu-id="a2673-141">And here is what the same user of the Contoso Corporation would see *after customization*.</span></span>

![自定义后的 Office 365 登录页示例](./media/identity-customize-office-365-sign-in/id-step01-sign-in-after.png)

<span data-ttu-id="a2673-143">有关详细信息，请参阅[向 Office 365 登录页添加公司品牌](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)。</span><span class="sxs-lookup"><span data-stu-id="a2673-143">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="a2673-144">有关配置说明，请参阅[向登录页和访问面板页添加公司品牌](http://aka.ms/aadpaddbranding)。</span><span class="sxs-lookup"><span data-stu-id="a2673-144">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="a2673-145">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-custom-sign-in)。</span><span class="sxs-lookup"><span data-stu-id="a2673-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="a2673-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a2673-146">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="a2673-147">使用组实现更轻松地管理</span><span class="sxs-lookup"><span data-stu-id="a2673-147">Use groups for easier management</span></span>](identity-self-service-group-management.md) |


