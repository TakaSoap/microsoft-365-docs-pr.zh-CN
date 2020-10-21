---
title: 允许用户重置自己的密码
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 了解如何使用自助密码重置工具来重置密码。
ms.openlocfilehash: 7ecadaa42610e0b77dc1727c11140080bd7b1779
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646675"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="f66eb-103">允许用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="f66eb-103">Let users reset their own passwords</span></span>

<span data-ttu-id="f66eb-104">作为 Microsoft 365 管理员，你可以让用户使用 [自助密码重置工具](https://go.microsoft.com/fwlink/p/?LinkId=522677) ，这样你就不必重置它们的密码。</span><span class="sxs-lookup"><span data-stu-id="f66eb-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="f66eb-105">减少工作量！</span><span class="sxs-lookup"><span data-stu-id="f66eb-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="f66eb-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="f66eb-106">Before you begin</span></span>
  
- <span data-ttu-id="f66eb-107">通过任何 Microsoft 365 商业版、教育版或非盈利的计划 **免费** 为云用户获取自助服务密码重置。</span><span class="sxs-lookup"><span data-stu-id="f66eb-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="f66eb-108">它不适用于 Microsoft 365 试用版。</span><span class="sxs-lookup"><span data-stu-id="f66eb-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="f66eb-p103">该功能使用 Azure。将在执行下面的步骤时，自动在 Azure 中 **免费** 获得此功能。如果不使用其他 Azure 功能，则不需要支付任何费用即可启用自助密码重置功能。</span><span class="sxs-lookup"><span data-stu-id="f66eb-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="f66eb-112">**如果使用的是本地 Active Directory**，则不适用以上两个点。</span><span class="sxs-lookup"><span data-stu-id="f66eb-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="f66eb-113">相反，您可以对此进行设置，但 **需要付费的 AZURE AD Premium 订阅**。</span><span class="sxs-lookup"><span data-stu-id="f66eb-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="f66eb-114">本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。</span><span class="sxs-lookup"><span data-stu-id="f66eb-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="f66eb-115">若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f66eb-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="f66eb-116">什么是管理员帐户？</span><span class="sxs-lookup"><span data-stu-id="f66eb-116">What's an admin account?</span></span>](../admin-overview/admin-overview.md)

<span data-ttu-id="f66eb-117">您必须是 [全局管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="f66eb-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="f66eb-118">手表：让用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="f66eb-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="f66eb-119">如果你觉得这段视频有用，请查看[适用于小型企业和 Microsoft 365 新手的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="f66eb-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="f66eb-120">步骤：让用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="f66eb-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="f66eb-121">以下步骤将为企业中的所有人启用自助密码重置。</span><span class="sxs-lookup"><span data-stu-id="f66eb-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="f66eb-122">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>中，转到 " **设置** > **组织设置** " 页。</span><span class="sxs-lookup"><span data-stu-id="f66eb-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f66eb-123">在 " <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>" 中，转到 " **设置** \> **安全 &amp; 隐私** " 页。</span><span class="sxs-lookup"><span data-stu-id="f66eb-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f66eb-124">在<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，转到 "**设置** \> **设置** \> **安全 &amp; 隐私**" 页。</span><span class="sxs-lookup"><span data-stu-id="f66eb-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="f66eb-125">在 " **组织设置** " 页的顶部，选择 " **安全性" & "隐私** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f66eb-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="f66eb-126">选择 " **自助密码重置**"。</span><span class="sxs-lookup"><span data-stu-id="f66eb-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="f66eb-127">在 " **自助密码重置**" 下，选择 **"转到 Azure 门户" 以启用自助密码重置**。</span><span class="sxs-lookup"><span data-stu-id="f66eb-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="f66eb-128">在左侧导航窗格中，选择 " **用户**"，然后在 " **用户" | ""所有用户** " 页上，选择 " **密码重置**"。</span><span class="sxs-lookup"><span data-stu-id="f66eb-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="f66eb-129">在 " **属性** " 页上，选择 " **全部** " 以为企业中的所有人启用它，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="f66eb-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="f66eb-130">当用户登录时，系统会提示他们输入其他联系人信息，这将帮助他们将来重置其密码。</span><span class="sxs-lookup"><span data-stu-id="f66eb-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="f66eb-131">相关内容</span><span class="sxs-lookup"><span data-stu-id="f66eb-131">Related content</span></span>

[<span data-ttu-id="f66eb-132">为组织设置密码过期策略</span><span class="sxs-lookup"><span data-stu-id="f66eb-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="f66eb-133">将个人用户密码设置为永不过期</span><span class="sxs-lookup"><span data-stu-id="f66eb-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="f66eb-134">Microsoft 365 商业版培训视频</span><span class="sxs-lookup"><span data-stu-id="f66eb-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
