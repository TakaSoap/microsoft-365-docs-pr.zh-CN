---
title: 为用户设置多重身份验证
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 了解如何使用安全性默认值为用户设置多重身份验证。
monikerRange: o365-worldwide
ms.openlocfilehash: 4c0df9198db8154c1aa748a68eff29dd9bf3bca1
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213006"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="d5287-103">设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="d5287-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d5287-104">如果你在2019年10月21日之后购买了订阅或试用，并且意外提示了多重身份验证（MFA），则已为你的订阅自动启用[安全默认设置](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="d5287-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="d5287-105">每个新 Microsoft 365 订阅将自动启用[安全默认设置](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="d5287-105">Every new Microsoft 365 subscription will automatically have [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) turned on.</span></span> <span data-ttu-id="d5287-106">这意味着，每个用户都必须设置多重身份验证（MFA），并在其移动设备上安装 Microsoft 身份验证器应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5287-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="d5287-107">有关详细信息，请参阅为[Microsoft 365 帐户设置 MFA](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)。</span><span class="sxs-lookup"><span data-stu-id="d5287-107">For more information, see [Set up MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="d5287-108">下面九种管理员角色每次登录时都需要执行额外的身份验证：</span><span class="sxs-lookup"><span data-stu-id="d5287-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="d5287-109">全局管理员</span><span class="sxs-lookup"><span data-stu-id="d5287-109">Global administrator</span></span>
- <span data-ttu-id="d5287-110">SharePoint 管理员</span><span class="sxs-lookup"><span data-stu-id="d5287-110">SharePoint administrator</span></span>
- <span data-ttu-id="d5287-111">Exchange 管理员</span><span class="sxs-lookup"><span data-stu-id="d5287-111">Exchange administrator</span></span>
- <span data-ttu-id="d5287-112">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="d5287-112">Conditional Access administrator</span></span>
- <span data-ttu-id="d5287-113">安全管理员</span><span class="sxs-lookup"><span data-stu-id="d5287-113">Security administrator</span></span>
- <span data-ttu-id="d5287-114">支持管理员/密码管理员</span><span class="sxs-lookup"><span data-stu-id="d5287-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="d5287-115">计费管理员</span><span class="sxs-lookup"><span data-stu-id="d5287-115">Billing administrator</span></span>
- <span data-ttu-id="d5287-116">用户管理员</span><span class="sxs-lookup"><span data-stu-id="d5287-116">User administrator</span></span>
- <span data-ttu-id="d5287-117">身份验证管理员</span><span class="sxs-lookup"><span data-stu-id="d5287-117">Authentication administrator</span></span>

<span data-ttu-id="d5287-118">必要时，系统将要求其他所有用户执行额外的身份验证。</span><span class="sxs-lookup"><span data-stu-id="d5287-118">All other users will be asked to perform additional authentication when needed.</span></span>

> [!NOTE]
> <span data-ttu-id="d5287-119">您必须是全局管理员才能设置或修改 MFA</span><span class="sxs-lookup"><span data-stu-id="d5287-119">You must be a global admin to set up or modify MFA</span></span> <br><br>
> <span data-ttu-id="d5287-120">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="d5287-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="d5287-121">如果您以前设置了具有基准策略的 MFA，[则必须将其关闭以启用安全默认](#move-from-baseline-policies-to-security-defaults)设置。</span><span class="sxs-lookup"><span data-stu-id="d5287-121">If you have previously set up MFA with baseline policies, [you must turn them off to turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="d5287-122">但是，如果你拥有 Microsoft 365 业务或你的订阅包括[Azure Active Directory 高级 P1 或 Azure Active Directory 高级 P2](https://azure.microsoft.com/pricing/details/active-directory/)，则还可以设置[条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)策略。</span><span class="sxs-lookup"><span data-stu-id="d5287-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="d5287-123">若要使用条件访问策略，您需要确保禁用安全默认设置并启用[新式验证](#enable-modern-authentication-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="d5287-123">To use Conditional Access policies, you need to make sure security defaults are disabled and [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="d5287-124">若要向您的用户说明如何设置 Microsoft 身份验证器应用程序，请参阅[使用 Microsoft 身份验证器与 Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411)。</span><span class="sxs-lookup"><span data-stu-id="d5287-124">To explain to your users how to set up the Microsoft Authenticator app, see [Use Microsoft Authenticator with Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="d5287-125">管理安全性默认值</span><span class="sxs-lookup"><span data-stu-id="d5287-125">Manage security defaults</span></span>

1. <span data-ttu-id="d5287-126">使用全局管理员凭据登录[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)。</span><span class="sxs-lookup"><span data-stu-id="d5287-126">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with global admin credentials.</span></span>
2. <span data-ttu-id="d5287-127">转到 " [Azure Active Directory-属性" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="d5287-127">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="d5287-128">在页面底部，选择“**管理安全性默认值**”。</span><span class="sxs-lookup"><span data-stu-id="d5287-128">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="d5287-129">选择 **"是"** 启用安全默认设置，单击 "**否**" 禁用安全默认设置，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d5287-129">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="d5287-130">从基线策略改为安全性默认值</span><span class="sxs-lookup"><span data-stu-id="d5287-130">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="d5287-131">转到 "[条件访问策略" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)。</span><span class="sxs-lookup"><span data-stu-id="d5287-131">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="d5287-132">选择启用的每个基准策略，并将 "**启用策略**" 设置为 "**关闭** **"** 。</span><span class="sxs-lookup"><span data-stu-id="d5287-132">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="d5287-133">转到 " [Azure Active Directory-属性" 页](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="d5287-133">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="d5287-134">在页面底部，选择 "**管理安全性默认**设置"，然后在 "**启用安全性**默认设置" 窗格中，将 "**启用安全默认**设置" 切换为 **"是**"，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d5287-134">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="d5287-135">为你的组织启用新式验证</span><span class="sxs-lookup"><span data-stu-id="d5287-135">Enable modern authentication for your organization</span></span>

<span data-ttu-id="d5287-136">所有 Office 2016 客户端应用程序均通过使用 Active Directory 身份验证库 (ADAL) 支持 MFA。</span><span class="sxs-lookup"><span data-stu-id="d5287-136">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="d5287-137">这意味着 Office 2016 客户端无需应用密码。</span><span class="sxs-lookup"><span data-stu-id="d5287-137">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="d5287-138">有关详细信息，请参阅[本文](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords)。</span><span class="sxs-lookup"><span data-stu-id="d5287-138">See [this article](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) for more information.</span></span>

<span data-ttu-id="d5287-139">但是，您需要确保为您的 Microsoft 365 订阅启用 ADAL 或新式验证。</span><span class="sxs-lookup"><span data-stu-id="d5287-139">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="d5287-140">若要启用新式验证，请在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)内依次选择“设置”\*\*\*\*\>“设置”\*\*\*\*，然后从“服务”\*\*\*\* 选项卡中的列表内选择“新式验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d5287-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="d5287-141">选中**新式验证**面板中的 "**启用新式验证（推荐）** " 框，然后选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="d5287-141">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![在“新式验证”面板中已选中启用复选框。](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="d5287-143">从2017年8月起，所有新的包含 Skype for Business online 和 Exchange online 的 Microsoft 365 订阅默认启用新式身份验证。</span><span class="sxs-lookup"><span data-stu-id="d5287-143">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="d5287-144">若要检查 Skype for Business Online 的新式验证状态，请通过全局管理员凭据使用 Skype for Business Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d5287-144">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="d5287-145">运行 Get-CsOAuthConfiguration 可检查 -ClientADALAuthOverride 的输出。</span><span class="sxs-lookup"><span data-stu-id="d5287-145">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="d5287-146">如果 -ClientADALAuthOverride 的输出为“Allowed”，表明新式验证处于开启状态。</span><span class="sxs-lookup"><span data-stu-id="d5287-146">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="d5287-147">若要查看 Exchange Online 的 MA 状态，请访问[在 Exchange Online 中启用新式身份验证](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="d5287-147">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="d5287-148">相关文章</span><span class="sxs-lookup"><span data-stu-id="d5287-148">Related articles</span></span>

[<span data-ttu-id="d5287-149">保护 Microsoft 365 商业版计划的十大方法</span><span class="sxs-lookup"><span data-stu-id="d5287-149">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="d5287-150">在 Windows 设备上启用适用于 Office 2013 的新式验证</span><span class="sxs-lookup"><span data-stu-id="d5287-150">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
