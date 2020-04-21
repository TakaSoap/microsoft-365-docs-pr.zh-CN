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
ms.openlocfilehash: 4a829aa597596564b9c2f468e72f3a766b198372
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627676"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="c30cb-103">设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="c30cb-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c30cb-104">如果你在2019年10月21日之后购买了订阅或试用，并且意外提示您进行 MFA，则已为你的订阅自动启用[安全默认设置](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="c30cb-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="c30cb-105">每个新 Microsoft 365 订阅将自动启用安全默认设置。</span><span class="sxs-lookup"><span data-stu-id="c30cb-105">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="c30cb-106">这意味着每位用户都必须在其移动设备上设置多重身份验证 (MFA) 并安装 Authenticator 应用。</span><span class="sxs-lookup"><span data-stu-id="c30cb-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="c30cb-107">有关详细信息，请参阅[为 Microsoft 365 设置2步验证](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)。</span><span class="sxs-lookup"><span data-stu-id="c30cb-107">For more information, see [Set up 2-step verification for Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="c30cb-108">下面九种管理员角色每次登录时都需要执行额外的身份验证：</span><span class="sxs-lookup"><span data-stu-id="c30cb-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="c30cb-109">全局管理员</span><span class="sxs-lookup"><span data-stu-id="c30cb-109">Global administrator</span></span>
- <span data-ttu-id="c30cb-110">SharePoint 管理员</span><span class="sxs-lookup"><span data-stu-id="c30cb-110">SharePoint administrator</span></span>
- <span data-ttu-id="c30cb-111">Exchange 管理员</span><span class="sxs-lookup"><span data-stu-id="c30cb-111">Exchange administrator</span></span>
- <span data-ttu-id="c30cb-112">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="c30cb-112">Conditional Access administrator</span></span>
- <span data-ttu-id="c30cb-113">安全管理员</span><span class="sxs-lookup"><span data-stu-id="c30cb-113">Security administrator</span></span>
- <span data-ttu-id="c30cb-114">支持管理员/密码管理员</span><span class="sxs-lookup"><span data-stu-id="c30cb-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="c30cb-115">计费管理员</span><span class="sxs-lookup"><span data-stu-id="c30cb-115">Billing administrator</span></span>
- <span data-ttu-id="c30cb-116">用户管理员</span><span class="sxs-lookup"><span data-stu-id="c30cb-116">User administrator</span></span>
- <span data-ttu-id="c30cb-117">身份验证管理员</span><span class="sxs-lookup"><span data-stu-id="c30cb-117">Authentication administrator</span></span>

<span data-ttu-id="c30cb-118">必要时，系统将要求其他所有用户执行额外的身份验证。</span><span class="sxs-lookup"><span data-stu-id="c30cb-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="c30cb-119">有关详细信息，请参阅[什么是安全性默认值？](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="c30cb-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

> [!NOTE]
> <span data-ttu-id="c30cb-120">您必须是全局管理员才能设置或修改多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="c30cb-120">You must be a global admin to set up or modify multi-factor authentication.</span></span> <br><br>
> <span data-ttu-id="c30cb-121">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="c30cb-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="c30cb-122">如果之前使用基线策略设置了 MFA，则[必须将其关闭，再打开安全性默认值](#move-from-baseline-policies-to-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="c30cb-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="c30cb-123">但是，如果你有 Microsoft 365 商业版，或者你的订阅包含 [Azure Active Directory Premium 1 或 Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/)，则你还可设置[条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)策略。</span><span class="sxs-lookup"><span data-stu-id="c30cb-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="c30cb-124">若要使用条件访问策略，需要确保已启用[新式身份验证](#enable-modern-authentication-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="c30cb-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="c30cb-125">若要向你的用户说明如何设置 Authenticator 应用，请访问[将 Microsoft Authenticator 用于 Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)。</span><span class="sxs-lookup"><span data-stu-id="c30cb-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="c30cb-126">管理安全性默认值</span><span class="sxs-lookup"><span data-stu-id="c30cb-126">Manage security defaults</span></span>

1. <span data-ttu-id="c30cb-127">使用全局管理员凭据登录[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)。</span><span class="sxs-lookup"><span data-stu-id="c30cb-127">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="c30cb-128">转到 [Azure Active Directory 属性](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="c30cb-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="c30cb-129">在页面底部，选择“**管理安全性默认值**”。</span><span class="sxs-lookup"><span data-stu-id="c30cb-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="c30cb-130">选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="c30cb-130">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="c30cb-131">从基线策略改为安全性默认值</span><span class="sxs-lookup"><span data-stu-id="c30cb-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="c30cb-132">在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)中，选择“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="c30cb-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="c30cb-133">在“**登录和安全**”旁边，**使登录更安全**下，选择“**查看**”。</span><span class="sxs-lookup"><span data-stu-id="c30cb-133">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="c30cb-134">在“**使登录更安全**”下，选择“**管理**”。</span><span class="sxs-lookup"><span data-stu-id="c30cb-134">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="c30cb-135">在 "**条件访问-策略**" 页上，选择每个已**启用**的基线策略，并将其设置为 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="c30cb-135">On the **Conditional Access - Policies** page, choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="c30cb-136">转到 [Azure Active Directory 属性](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)页面。</span><span class="sxs-lookup"><span data-stu-id="c30cb-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="c30cb-137">在页面底部，选择 "**管理安全性默认**设置"，然后在 "**启用安全性**默认设置" 窗格中，将 "**启用安全默认**设置" 切换为 **"是**"，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c30cb-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="c30cb-138">为你的组织启用新式验证</span><span class="sxs-lookup"><span data-stu-id="c30cb-138">Enable modern authentication for your organization</span></span>

<span data-ttu-id="c30cb-139">所有 Office 2016 客户端应用程序均通过使用 Active Directory 身份验证库 (ADAL) 支持 MFA。</span><span class="sxs-lookup"><span data-stu-id="c30cb-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="c30cb-140">这意味着 Office 2016 客户端无需应用密码。</span><span class="sxs-lookup"><span data-stu-id="c30cb-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="c30cb-141">但是，您需要确保为您的 Microsoft 365 订阅启用 ADAL 或新式验证。</span><span class="sxs-lookup"><span data-stu-id="c30cb-141">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="c30cb-142">若要启用新式验证，请在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)内依次选择“设置”\*\*\*\*\>“设置”\*\*\*\*，然后从“服务”\*\*\*\* 选项卡中的列表内选择“新式验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c30cb-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="c30cb-143">选中**新式验证**面板中的 "**启用新式验证（推荐）** " 框，然后选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="c30cb-143">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![在“新式验证”面板中已选中启用复选框。](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="c30cb-145">从2017年8月起，所有新的包含 Skype for Business online 和 Exchange online 的 Microsoft 365 订阅默认启用新式身份验证。</span><span class="sxs-lookup"><span data-stu-id="c30cb-145">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="c30cb-146">若要检查 Skype for Business Online 的新式验证状态，请通过全局管理员凭据使用 Skype for Business Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c30cb-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="c30cb-147">运行 Get-CsOAuthConfiguration 可检查 -ClientADALAuthOverride 的输出。</span><span class="sxs-lookup"><span data-stu-id="c30cb-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="c30cb-148">如果 -ClientADALAuthOverride 的输出为“Allowed”，表明新式验证处于开启状态。</span><span class="sxs-lookup"><span data-stu-id="c30cb-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="c30cb-149">若要查看 Exchange Online 的 MA 状态，请访问[在 Exchange Online 中启用新式身份验证](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="c30cb-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="c30cb-150">相关文章</span><span class="sxs-lookup"><span data-stu-id="c30cb-150">Related articles</span></span>

[<span data-ttu-id="c30cb-151">保护 Microsoft 365 商业版计划的十大方法</span><span class="sxs-lookup"><span data-stu-id="c30cb-151">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="c30cb-152">在 Windows 设备上启用适用于 Office 2013 的新式验证</span><span class="sxs-lookup"><span data-stu-id="c30cb-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
