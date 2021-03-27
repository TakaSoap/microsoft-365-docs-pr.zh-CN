---
title: 打开安全默认值
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解安全默认值如何通过提供预配置的安全设置来帮助保护组织免受与标识相关的攻击。
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398286"
---
# <a name="turn-on-security-defaults"></a><span data-ttu-id="333b8-103">打开安全默认值</span><span class="sxs-lookup"><span data-stu-id="333b8-103">Turn on security defaults</span></span>

<span data-ttu-id="333b8-104">安全默认值通过提供 Microsoft 代表组织管理的预配置安全设置来帮助保护组织免受与标识相关的攻击。</span><span class="sxs-lookup"><span data-stu-id="333b8-104">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="333b8-105">这些设置包括在所有管理员和用户帐户 (MFA) 多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="333b8-105">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="333b8-106">对于大多数组织来说，安全默认值提供了良好的附加登录安全级别。</span><span class="sxs-lookup"><span data-stu-id="333b8-106">For most organizations, security defaults offer a good level of additional sign-in security.</span></span>

<span data-ttu-id="333b8-107">有关安全默认值及其强制策略详细信息，请参阅 [什么是安全默认值？](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="333b8-107">For more information about security defaults and the policies they enforce, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="333b8-108">如果订阅是在 2019 年 10 月 22 日当天或之后创建的，则可能会自动启用安全默认值，你应该 &mdash; 检查设置以确认。</span><span class="sxs-lookup"><span data-stu-id="333b8-108">If your subscription was created on or after October 22, 2019, security defaults might have been automatically enabled for you&mdash;you should check your settings to confirm.</span></span>

<span data-ttu-id="333b8-109">若要在 Azure AD (Azure Active Directory 中启用) 或检查它们是否已启用：</span><span class="sxs-lookup"><span data-stu-id="333b8-109">To enable security defaults in your Azure Active Directory (Azure AD) or to check to see if they're already enabled:</span></span>

1. <span data-ttu-id="333b8-110">使用全局管理员凭据登录 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> 管理中心。</span><span class="sxs-lookup"><span data-stu-id="333b8-110">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> with Global admin credentials.</span></span>

2. <span data-ttu-id="333b8-111">在左侧窗格中，选择"**全部显示**"，然后在"**管理中心**"下，选择 **"Azure Active Directory"。**</span><span class="sxs-lookup"><span data-stu-id="333b8-111">In the left pane, select **Show All,** and then under **Admin centers**, select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="333b8-112">在 Azure Active **Directory** 管理中心的左侧窗格中，选择 **"Azure Active Directory"。**</span><span class="sxs-lookup"><span data-stu-id="333b8-112">In the left pane of the **Azure Active Directory admin center,** select **Azure Active Directory**.</span></span>

4. <span data-ttu-id="333b8-113">从仪表板的左侧菜单中的"管理"**部分**，选择"属性 **"。**</span><span class="sxs-lookup"><span data-stu-id="333b8-113">From the left menu of the Dashboard, in the **Manage** section, select **Properties**.</span></span>

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="显示&quot;属性&quot;菜单项位置的 Azure Active Directory 管理中心的屏幕截图。":::

5. <span data-ttu-id="333b8-115">在"属性"页 **底部**，选择"**管理安全性默认值"。**</span><span class="sxs-lookup"><span data-stu-id="333b8-115">At the bottom of the **Properties** page, select **Manage Security defaults**.</span></span>

6. <span data-ttu-id="333b8-116">在右侧窗格中，你将看到" **启用安全性默认设置"** 设置。</span><span class="sxs-lookup"><span data-stu-id="333b8-116">In the right pane, you'll see the **Enable Security defaults** setting.</span></span> <span data-ttu-id="333b8-117">如果 **选择了** "是"，则已启用安全默认值，无需执行任何进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="333b8-117">If **Yes** is selected, then security defaults are already enabled and no further action is required.</span></span> <span data-ttu-id="333b8-118">如果当前未启用安全默认值，请选择"是"以启用它们，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="333b8-118">If security defaults are not currently enabled, then select **Yes** to enable them, and then select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="333b8-119">如果一直使用条件访问策略，则需要在使用安全默认值之前将其关闭。</span><span class="sxs-lookup"><span data-stu-id="333b8-119">If you've been using Conditional Access policies, you'll need to turn them off before using security defaults.</span></span>
>
> <span data-ttu-id="333b8-120">可以使用安全默认值或条件访问策略，但不能同时使用这两者。</span><span class="sxs-lookup"><span data-stu-id="333b8-120">You can use either security defaults or Conditional Access policies, but you can't use both at the same time.</span></span>

## <a name="consider-using-conditional-access"></a><span data-ttu-id="333b8-121">考虑使用条件访问</span><span class="sxs-lookup"><span data-stu-id="333b8-121">Consider using Conditional Access</span></span>

<span data-ttu-id="333b8-122">如果您的组织具有复杂的安全要求，或者您需要更精细地控制安全策略，则应考虑使用条件访问而非安全默认值来实现类似或更高的安全状况。</span><span class="sxs-lookup"><span data-stu-id="333b8-122">If your organization has complex security requirements or you need more granular control over your security policies, then you should consider using Conditional Access instead of security defaults to achieve a similar or higher security posture.</span></span> 

<span data-ttu-id="333b8-123">条件访问允许你创建和定义对登录事件做出反应的策略，并请求执行其他操作，然后再向用户授予应用程序或服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="333b8-123">Conditional Access lets you create and define policies that react to sign-in events and request additional actions before a user is granted access to an application or service.</span></span> <span data-ttu-id="333b8-124">条件访问策略可以精细具体化，使用户能够随时随地高效工作，还可以保护组织。</span><span class="sxs-lookup"><span data-stu-id="333b8-124">Conditional Access policies can be granular and specific, empowering users to be productive wherever and whenever, but also protecting your organization.</span></span>

<span data-ttu-id="333b8-125">安全默认值可供所有客户使用，而条件访问需要以下计划之一的许可证：</span><span class="sxs-lookup"><span data-stu-id="333b8-125">Security defaults are available to all customers, while Conditional Access requires a license for one of the following plans:</span></span>

- <span data-ttu-id="333b8-126">Azure Active Directory Premium P1 或 P2</span><span class="sxs-lookup"><span data-stu-id="333b8-126">Azure Active Directory Premium P1 or P2</span></span>
- <span data-ttu-id="333b8-127">Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="333b8-127">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="333b8-128">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="333b8-128">Microsoft 365 E3 or E5</span></span>
- <span data-ttu-id="333b8-129">企业移动性&安全性 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="333b8-129">Enterprise Mobility & Security E3 or E5</span></span>

<span data-ttu-id="333b8-130">如果要使用条件访问配置与安全默认值启用的策略等效的策略，请查看以下分步指南：</span><span class="sxs-lookup"><span data-stu-id="333b8-130">If you want to use Conditional Access to configure policies equivalent to those enabled by security defaults, check out the following step-by-step guides:</span></span>

- [<span data-ttu-id="333b8-131">要求对管理员执行 MFA</span><span class="sxs-lookup"><span data-stu-id="333b8-131">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="333b8-132">需要 MFA 进行 Azure 管理</span><span class="sxs-lookup"><span data-stu-id="333b8-132">Require MFA for Azure management</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [<span data-ttu-id="333b8-133">阻止旧身份验证</span><span class="sxs-lookup"><span data-stu-id="333b8-133">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [<span data-ttu-id="333b8-134">要求对所有用户执行 MFA</span><span class="sxs-lookup"><span data-stu-id="333b8-134">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- <span data-ttu-id="333b8-135">[需要 Azure AD MFA 注册](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - 需要 Azure AD Identity Protection，这是 Azure Active Directory Premium P2 的一部分</span><span class="sxs-lookup"><span data-stu-id="333b8-135">[Require Azure AD MFA registration](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requires Azure AD Identity Protection, which is part of Azure Active Directory Premium P2</span></span>

<span data-ttu-id="333b8-136">若要详细了解条件访问，请参阅 [什么是条件访问？](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="333b8-136">To learn more about Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span> <span data-ttu-id="333b8-137">有关创建条件访问策略的信息，请参阅 [创建条件访问策略](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)。</span><span class="sxs-lookup"><span data-stu-id="333b8-137">For more information about creating Conditional Access policies, see [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span></span>

> [!NOTE]
> <span data-ttu-id="333b8-138">如果你有提供条件访问但尚未创建任何条件访问策略的计划或许可证，则欢迎使用安全默认值。</span><span class="sxs-lookup"><span data-stu-id="333b8-138">If you have a plan or license that provides Conditional Access but haven't yet created any Conditional Access policies, you're welcome to use security defaults.</span></span> <span data-ttu-id="333b8-139">但是，您需要先关闭安全默认值，然后才能使用条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="333b8-139">However, you'll need to turn off security defaults before you can use Conditional Access policies.</span></span>
