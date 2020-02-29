---
title: 为 Office 365 用户设置多重身份验证
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
description: 了解如何使用安全性默认值为 Office 365 用户设置多重身份验证。
monikerRange: o365-worldwide
ms.openlocfilehash: cb2205e5f5b7df4f6e7d8f7263a91fb2f0f4d3e2
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341246"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="a6771-103">设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="a6771-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="a6771-104">每个新的 Office 365 商业版或 Microsoft 365 商业版订阅都将自动启用安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="a6771-104">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="a6771-105">这意味着每位用户都必须在其移动设备上设置多重身份验证 (MFA) 并安装 Authenticator 应用。</span><span class="sxs-lookup"><span data-stu-id="a6771-105">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="a6771-106">有关详细信息，请参阅[为 Office 365 设置双重验证](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)。</span><span class="sxs-lookup"><span data-stu-id="a6771-106">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="a6771-107">下面九种管理员角色每次登录时都需要执行额外的身份验证：</span><span class="sxs-lookup"><span data-stu-id="a6771-107">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="a6771-108">全局管理员</span><span class="sxs-lookup"><span data-stu-id="a6771-108">Global administrator</span></span>
- <span data-ttu-id="a6771-109">SharePoint 管理员</span><span class="sxs-lookup"><span data-stu-id="a6771-109">SharePoint administrator</span></span>
- <span data-ttu-id="a6771-110">Exchange 管理员</span><span class="sxs-lookup"><span data-stu-id="a6771-110">Exchange administrator</span></span>
- <span data-ttu-id="a6771-111">条件访问管理员</span><span class="sxs-lookup"><span data-stu-id="a6771-111">Conditional Access administrator</span></span>
- <span data-ttu-id="a6771-112">安全管理员</span><span class="sxs-lookup"><span data-stu-id="a6771-112">Security administrator</span></span>
- <span data-ttu-id="a6771-113">支持管理员/密码管理员</span><span class="sxs-lookup"><span data-stu-id="a6771-113">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="a6771-114">计费管理员</span><span class="sxs-lookup"><span data-stu-id="a6771-114">Billing administrator</span></span>
- <span data-ttu-id="a6771-115">用户管理员</span><span class="sxs-lookup"><span data-stu-id="a6771-115">User administrator</span></span>
- <span data-ttu-id="a6771-116">身份验证管理员</span><span class="sxs-lookup"><span data-stu-id="a6771-116">Authentication administrator</span></span>

<span data-ttu-id="a6771-117">必要时，系统将要求其他所有用户执行额外的身份验证。</span><span class="sxs-lookup"><span data-stu-id="a6771-117">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="a6771-118">有关详细信息，请参阅[什么是安全性默认值？](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="a6771-118">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="a6771-p103">必须是 Office 365 全局管理员才能设置或修改多重身份验证。 </span><span class="sxs-lookup"><span data-stu-id="a6771-p103">You must be an Office 365 global admin to set up or modify multi-factor authentication. </span></span><br><br>
> <span data-ttu-id="a6771-120">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="a6771-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="a6771-121">如果之前使用基线策略设置了 MFA，则[必须将其关闭，再打开安全性默认值](#move-from-baseline-policies-to-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="a6771-121">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="a6771-122">但是，如果你有 Microsoft 365 商业版，或者你的订阅包含 [Azure Active Directory Premium 1 或 Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/)，则你还可设置[条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)策略。</span><span class="sxs-lookup"><span data-stu-id="a6771-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="a6771-123">若要使用条件访问策略，你需要确保[已启用新式验证](#enable-multi-factor-authentication-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="a6771-123">To use conditional access policies, you need to make sure [modern authentication is enabled](#enable-multi-factor-authentication-for-your-organization).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="a6771-124">管理安全性默认值</span><span class="sxs-lookup"><span data-stu-id="a6771-124">Manage security defaults</span></span>

1. <span data-ttu-id="a6771-125">使用全局管理员凭据登录[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)。</span><span class="sxs-lookup"><span data-stu-id="a6771-125">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="a6771-126">转到 [Azure Active Directory 属性](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="a6771-126">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="a6771-127">在页面底部，选择“**管理安全性默认值**”。</span><span class="sxs-lookup"><span data-stu-id="a6771-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="a6771-128">选择“**是**”启用安全性默认值，或选择“**否**”禁用安全性默认值。</span><span class="sxs-lookup"><span data-stu-id="a6771-128">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="a6771-129">从基线策略改为安全性默认值</span><span class="sxs-lookup"><span data-stu-id="a6771-129">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="a6771-130">在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)中，选择“**设置**”。</span><span class="sxs-lookup"><span data-stu-id="a6771-130">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="a6771-131">在“**登录和安全**”旁边，**使登录更安全**下，选择“**查看**”。</span><span class="sxs-lookup"><span data-stu-id="a6771-131">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="a6771-132">在“**使登录更安全**”下，选择“**管理**”。</span><span class="sxs-lookup"><span data-stu-id="a6771-132">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="a6771-133">在“\*\* 门户条件访问 - 策略**”页面上，选择已**启用**的每项基线策略并将其设置为“**关\*\*”。</span><span class="sxs-lookup"><span data-stu-id="a6771-133">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="a6771-134">转到 [Azure Active Directory 属性](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)页面。</span><span class="sxs-lookup"><span data-stu-id="a6771-134">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="a6771-135">在页面底部，选择“**管理安全性默认值**”，再在“**启用安全性默认值**”窗格中，将“**启用安全性默认值**”开关设置为“**是**”。</span><span class="sxs-lookup"><span data-stu-id="a6771-135">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="a6771-136">为你的组织启用新式验证</span><span class="sxs-lookup"><span data-stu-id="a6771-136">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="a6771-137">所有 Office 2016 客户端应用程序均通过使用 Active Directory 身份验证库 (ADAL) 支持 MFA。</span><span class="sxs-lookup"><span data-stu-id="a6771-137">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="a6771-138">这意味着 Office 2016 客户端无需应用密码。</span><span class="sxs-lookup"><span data-stu-id="a6771-138">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="a6771-139">但是，需要确保为 Office 365 订阅启用了 ADAL 或新式验证。</span><span class="sxs-lookup"><span data-stu-id="a6771-139">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="a6771-140">若要启用新式验证，请在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)内依次选择“设置”\*\*\*\*\>“设置”\*\*\*\*，然后从“服务”\*\*\*\* 选项卡中的列表内选择“新式验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a6771-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="a6771-141">选中“**新式验证**”面板中的“**启用新式验证**”框。</span><span class="sxs-lookup"><span data-stu-id="a6771-141">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![在“新式验证”面板中已选中启用复选框。](../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a><span data-ttu-id="a6771-143">为组织启用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="a6771-143">Enable multi-factor authentication for your organization</span></span>
    
1. <span data-ttu-id="a6771-144">在[管理中心](https://go.microsoft.com/fwlink/p/?linkid=834822)内，选择 "**用户**和**活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="a6771-144">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Users** and **Active Users**.</span></span>

2. <span data-ttu-id="a6771-145">在 "**活动用户**" 部分，单击 "**多重身份验证**"。</span><span class="sxs-lookup"><span data-stu-id="a6771-145">In the **Active Users** section, Click on  **multi-factor authentication**.</span></span>

3. <span data-ttu-id="a6771-146">在 "**多重身份验证**" 页上，如果要为一个用户启用此项，请选择 "**用户**"，或者选择 "**批量更新**" 以启用多个用户。</span><span class="sxs-lookup"><span data-stu-id="a6771-146">On the **Multi-factor authentication** page, select **user** if you are enabling this for one user or select **Bulk Update** to enable multiple users.</span></span>

4. <span data-ttu-id="a6771-147">单击 "**快速步骤**" 下的 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="a6771-147">CLick on **Enable** under **Quick Steps**.</span></span>

5. <span data-ttu-id="a6771-148">在弹出窗口中，单击 "**启用多重身份验证**"。</span><span class="sxs-lookup"><span data-stu-id="a6771-148">In the Pop-up window, Click on **Enable Multi-Factor Authentication**.</span></span>

<span data-ttu-id="a6771-149">为你的组织设置多重身份验证后，你的用户将需要在其设备上设置双重验证。</span><span class="sxs-lookup"><span data-stu-id="a6771-149">After you set up multi-factor authentication for your organization, your users will be required to set up two-step verification on their devices.</span></span> <span data-ttu-id="a6771-150">有关详细信息，请参阅[为 Office 365 设置双重验证](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14)。</span><span class="sxs-lookup"><span data-stu-id="a6771-150">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>
    
> [!TIP]
> <span data-ttu-id="a6771-151">若要向你的用户说明如何设置 Authenticator 应用，请访问[将 Microsoft Authenticator 用于 Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1)。</span><span class="sxs-lookup"><span data-stu-id="a6771-151">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a6771-152">自 2017 年 8 月起，包括 Skype for Business Online 和 Exchange Online 在内的所有新 Office 365 租户都默认启用新式验证。</span><span class="sxs-lookup"><span data-stu-id="a6771-152">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="a6771-153">若要检查 Skype for Business Online 的新式验证状态，请通过全局管理员凭据使用 Skype for Business Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a6771-153">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="a6771-154">运行 Get-CsOAuthConfiguration 可检查 -ClientADALAuthOverride 的输出。</span><span class="sxs-lookup"><span data-stu-id="a6771-154">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="a6771-155">如果 -ClientADALAuthOverride 的输出为“Allowed”，表明新式验证处于开启状态。</span><span class="sxs-lookup"><span data-stu-id="a6771-155">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="a6771-156">若要查看 Exchange Online 的 MA 状态，请访问[在 Exchange Online 中启用新式身份验证](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="a6771-156">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="a6771-157">相关文章</span><span class="sxs-lookup"><span data-stu-id="a6771-157">Related articles</span></span>

[<span data-ttu-id="a6771-158">确保 Office 365 和 Microsoft 365 商业版计划安全的十大方法</span><span class="sxs-lookup"><span data-stu-id="a6771-158">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="a6771-159">在 Windows 设备上启用适用于 Office 2013 的新式验证</span><span class="sxs-lookup"><span data-stu-id="a6771-159">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
