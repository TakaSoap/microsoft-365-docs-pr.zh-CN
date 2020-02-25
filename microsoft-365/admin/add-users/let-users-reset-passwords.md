---
title: 允许用户在 Office 365 中重置其密码
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 了解如何使用自助密码重置工具来重置密码。
ms.openlocfilehash: 87accc393d08b922ebc3f75ef1aa5ddb2d0b2955
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238152"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="64f1e-103">允许用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="64f1e-103">Let users reset their own passwords</span></span>

<span data-ttu-id="64f1e-104">因不断为用户重置密码而感到崩溃？</span><span class="sxs-lookup"><span data-stu-id="64f1e-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="64f1e-105">作为 Microsoft 365 管理员，你可以让用户使用[自助密码重置工具](https://go.microsoft.com/fwlink/p/?LinkId=522677)，这样你就不必重置它们的密码。</span><span class="sxs-lookup"><span data-stu-id="64f1e-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="64f1e-106">减少工作量！</span><span class="sxs-lookup"><span data-stu-id="64f1e-106">Less work for you!</span></span> 
  
<span data-ttu-id="64f1e-107">以下是需要了解的一些事项：</span><span class="sxs-lookup"><span data-stu-id="64f1e-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="64f1e-p102">可以通过任意 Office 365 商业版、教育版或非营利组织付费的计划 **免费** 为云用户获取自助密码重置服务。但不适用于 Office 365 试用版。</span><span class="sxs-lookup"><span data-stu-id="64f1e-p102">You get self-service password reset for cloud users **free** with any Office 365 business, education, or nonprofit paid plan. It doesn't work with Office 365 trial.</span></span> 
    
- <span data-ttu-id="64f1e-p103">该功能使用 Azure。将在执行下面的步骤时，自动在 Azure 中 **免费** 获得此功能。如果不使用其他 Azure 功能，则不需要支付任何费用即可启用自助密码重置功能。</span><span class="sxs-lookup"><span data-stu-id="64f1e-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="64f1e-113">**如果使用的是本地 Active Directory**，则不适用以上两个点。</span><span class="sxs-lookup"><span data-stu-id="64f1e-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="64f1e-114">相反，您可以对此进行设置，但**需要付费的 AZURE AD Premium 订阅**。</span><span class="sxs-lookup"><span data-stu-id="64f1e-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="64f1e-115">观看有关允许用户重置其自己的密码的简短视频。</span><span class="sxs-lookup"><span data-stu-id="64f1e-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="64f1e-116">如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="64f1e-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="64f1e-117">允许用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="64f1e-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="64f1e-118">以下步骤将为企业中的所有人启用自助密码重置。</span><span class="sxs-lookup"><span data-stu-id="64f1e-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1.  <span data-ttu-id="64f1e-119">在 "管理中心" 中，转到 "**设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">安全 & 隐私</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="64f1e-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="64f1e-120">在 "<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>" 中，转到 "**设置** \> **安全&amp;隐私**" 页。</span><span class="sxs-lookup"><span data-stu-id="64f1e-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="64f1e-121">在 "<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>" 中，转到 "**设置** \> **安全&amp;隐私**" 页。</span><span class="sxs-lookup"><span data-stu-id="64f1e-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="64f1e-122">在 "**允许你的用户重置其密码**" 下，选择 " **Azure AD 管理中心**" 的链接。</span><span class="sxs-lookup"><span data-stu-id="64f1e-122">Under **Let your people reset their own passwords**, select the link for the **Azure AD admin center**.</span></span> <span data-ttu-id="64f1e-123">将免费获得 Azure！</span><span class="sxs-lookup"><span data-stu-id="64f1e-123">You'll get Azure for free!</span></span>
  
3. <span data-ttu-id="64f1e-124">在左侧导航栏中选择 "**用户**"，然后选择 "**密码重置**"。</span><span class="sxs-lookup"><span data-stu-id="64f1e-124">Select **Users** in the left navigation, and then select **Password reset**.</span></span>
  
4. <span data-ttu-id="64f1e-125">在 "属性" 页上，选择 "**全部**" 以为企业中的所有人启用它，然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="64f1e-125">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="64f1e-126">当你的用户登录到 Office 365 时，系统将提示他们输入其他联系信息，这可帮助他们在将来重置密码。</span><span class="sxs-lookup"><span data-stu-id="64f1e-126">When your users sign in to Office 365, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="64f1e-127">相关文章</span><span class="sxs-lookup"><span data-stu-id="64f1e-127">Related articles</span></span>

[<span data-ttu-id="64f1e-128">为组织设置密码过期策略</span><span class="sxs-lookup"><span data-stu-id="64f1e-128">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="64f1e-129">将个人用户密码设置为永不过期</span><span class="sxs-lookup"><span data-stu-id="64f1e-129">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="64f1e-130">Microsoft 365 商业版培训视频</span><span class="sxs-lookup"><span data-stu-id="64f1e-130">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
