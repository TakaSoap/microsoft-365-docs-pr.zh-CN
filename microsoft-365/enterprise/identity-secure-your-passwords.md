---
title: 步骤2：保护密码安全
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
description: 你需要确保你的密码在整个组织中都强大并易于管理。
ms.openlocfilehash: 375f4a678e85dccb544ffaf56f648e98609841d9
ms.sourcegitcommit: 2aeafb631aaabc53eea0a8029711eb891e48d249
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2019
ms.locfileid: "37746508"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="b5c4f-103">第 2 步：保护密码安全</span><span class="sxs-lookup"><span data-stu-id="b5c4f-103">Step 2: Secure your passwords</span></span>

![第 2 阶段 - 标识](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="b5c4f-105">防止密码错误</span><span class="sxs-lookup"><span data-stu-id="b5c4f-105">Prevent bad passwords</span></span>

<span data-ttu-id="b5c4f-106">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b5c4f-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b5c4f-107">所有用户都应使用 [Microsoft 的密码指南](https://www.microsoft.com/research/publication/password-guidance/)来创建用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-107">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance/) to create their user account passwords.</span></span>

<span data-ttu-id="b5c4f-108">若要防止用户创建易于确定的密码，请使用 Azure AD 密码保护，该功能同时使用全局阻止密码列表和你指定的可选的自定义禁止密码列表。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-108">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="b5c4f-109">例如，你可以指定特定于贵组织的术语，例如：</span><span class="sxs-lookup"><span data-stu-id="b5c4f-109">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="b5c4f-110">品牌名称</span><span class="sxs-lookup"><span data-stu-id="b5c4f-110">Brand names</span></span>
- <span data-ttu-id="b5c4f-111">产品名称</span><span class="sxs-lookup"><span data-stu-id="b5c4f-111">Product names</span></span>
- <span data-ttu-id="b5c4f-112">位置（例如公司总部）</span><span class="sxs-lookup"><span data-stu-id="b5c4f-112">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="b5c4f-113">特定于公司的内部条款</span><span class="sxs-lookup"><span data-stu-id="b5c4f-113">Company-specific internal terms</span></span>
- <span data-ttu-id="b5c4f-114">具有特定公司含义的缩写</span><span class="sxs-lookup"><span data-stu-id="b5c4f-114">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="b5c4f-115">可[在云端](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)和[本地 Active Directory 域服务 (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) 中禁止错误密码。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-115">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="b5c4f-116">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-password-prot)。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="b5c4f-117">简化密码重置</span><span class="sxs-lookup"><span data-stu-id="b5c4f-117">Simplify password resets</span></span>

<span data-ttu-id="b5c4f-118">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b5c4f-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b5c4f-119">在此部分中，将启用自助密码重置 (SSPR)，以允许用户重置或解除锁定其密码或帐户。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="b5c4f-120">为提醒你避免误用或滥用，可以使用详细报告，跟踪用户访问系统的时间，并进行通知。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="b5c4f-121">必须先启用密码写回，然后才能部署密码重置。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="b5c4f-122">请参阅[推出密码重置说明](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b5c4f-124">测试实验室指南：密码重置</span><span class="sxs-lookup"><span data-stu-id="b5c4f-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="b5c4f-125">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-pw-reset)。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="b5c4f-126">简化用户登录</span><span class="sxs-lookup"><span data-stu-id="b5c4f-126">Simplify user sign-in</span></span>

<span data-ttu-id="b5c4f-127">*这对于混合环境来说是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b5c4f-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b5c4f-128">在此部分中，将设置 Azure Active Directory 无缝单一登录（Azure AD 无缝 SSO），该功能与密码哈希同步 (PHS) 和传递身份验证 (PTA) 一起使用，以允许用户登录到使用 Azure AD 用户帐户的服务，而无需键入其密码（在许多情况下，还无需键入用户名）。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO), which works with Password Hash Synchronization (PHS) and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="b5c4f-129">这可使用户更方便地访问基于云的应用程序（如 Office 365）而无需任何额外的本地组件（如联合身份验证服务器）。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="b5c4f-130">将使用 Azure AD Connect 工具配置 Azure AD 无缝 SSO。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-130">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="b5c4f-131">请参阅[配置 Azure AD 无缝 SSO 说明](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b5c4f-133">测试实验室指南：Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="b5c4f-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="b5c4f-134">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-sso)。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="b5c4f-135">自定义 Office 365 登录页</span><span class="sxs-lookup"><span data-stu-id="b5c4f-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="b5c4f-136">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="b5c4f-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b5c4f-137">在此部分中，将帮助用户通过添加公司名称、徽标和其他可识别元素来识别组织的登录页。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="b5c4f-138">使用 Microsoft 365 企业版，可以自定义登录页和访问面板页的外观，使其包含公司徽标、配色方案和自定义用户信息。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="b5c4f-139">有关详细信息，请参阅[向 Office 365 登录页添加公司品牌](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-139">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="b5c4f-140">有关配置说明，请参阅[向登录页和访问面板页添加公司品牌](https://aka.ms/aadpaddbranding)。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="b5c4f-141">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-custom-sign-in)。</span><span class="sxs-lookup"><span data-stu-id="b5c4f-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="b5c4f-142">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b5c4f-142">Next step</span></span>

|||
|:-------|:-----|
|![第 3 步](./media/stepnumbers/Step3.png)| [<span data-ttu-id="b5c4f-144">保护和管理用户登录</span><span class="sxs-lookup"><span data-stu-id="b5c4f-144">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
