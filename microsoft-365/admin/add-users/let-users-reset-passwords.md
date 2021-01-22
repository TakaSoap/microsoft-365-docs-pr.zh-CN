---
title: 允许用户重置自己的密码
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 了解如何使用自助服务密码重置工具重置密码。
ms.openlocfilehash: c777b9d840e0e9e467c1283fff94eca9a061ee73
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925550"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="ea22a-103">允许用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="ea22a-103">Let users reset their own passwords</span></span>

<span data-ttu-id="ea22a-104">作为 Microsoft 365 管理员，你可以允许用户使用[](https://go.microsoft.com/fwlink/p/?LinkId=522677)自助服务密码重置工具，因此不必重置其密码。</span><span class="sxs-lookup"><span data-stu-id="ea22a-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="ea22a-105">减少工作量！</span><span class="sxs-lookup"><span data-stu-id="ea22a-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="ea22a-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="ea22a-106">Before you begin</span></span>
  
- <span data-ttu-id="ea22a-107">通过任何 Microsoft 365商业版、教育版或非盈利性付费计划，你可以免费为云用户重置自助服务密码。</span><span class="sxs-lookup"><span data-stu-id="ea22a-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="ea22a-108">它不能与 Microsoft 365 试用版一起使用。</span><span class="sxs-lookup"><span data-stu-id="ea22a-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="ea22a-p103">该功能使用 Azure。将在执行下面的步骤时，自动在 Azure 中 **免费** 获得此功能。如果不使用其他 Azure 功能，则不需要支付任何费用即可启用自助密码重置功能。</span><span class="sxs-lookup"><span data-stu-id="ea22a-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="ea22a-112">**如果使用的是本地 Active Directory，** 则上述两点不适用。</span><span class="sxs-lookup"><span data-stu-id="ea22a-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="ea22a-113">相反，你可以设置它， **但它需要 Azure AD Premium** 的付费订阅。</span><span class="sxs-lookup"><span data-stu-id="ea22a-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="ea22a-114">本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。</span><span class="sxs-lookup"><span data-stu-id="ea22a-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="ea22a-115">若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ea22a-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="ea22a-116">什么是管理员帐户？</span><span class="sxs-lookup"><span data-stu-id="ea22a-116">What's an admin account?</span></span>](../admin-overview/admin-overview.md)

<span data-ttu-id="ea22a-117">您必须是全局 [管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="ea22a-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="ea22a-118">观看：让用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="ea22a-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="ea22a-119">如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。</span><span class="sxs-lookup"><span data-stu-id="ea22a-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="ea22a-120">步骤：让用户重置自己的密码</span><span class="sxs-lookup"><span data-stu-id="ea22a-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="ea22a-121">以下步骤将为企业中的所有人启用自助密码重置。</span><span class="sxs-lookup"><span data-stu-id="ea22a-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="ea22a-122">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>， **转到"设置** > **组织设置"** 页。</span><span class="sxs-lookup"><span data-stu-id="ea22a-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ea22a-123">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>，转到"设置 \> **安全性 &amp; "隐私** 页面。</span><span class="sxs-lookup"><span data-stu-id="ea22a-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ea22a-124">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，**转到"设置** \> **设置** \> **安全性 &amp; "隐私** 页面。</span><span class="sxs-lookup"><span data-stu-id="ea22a-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="ea22a-125">在"组织设置" **页的顶部** ，选择"安全& **隐私"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="ea22a-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="ea22a-126">选择 **"自助服务密码重置"。**</span><span class="sxs-lookup"><span data-stu-id="ea22a-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="ea22a-127">在 **"自助服务密码重置"下**，选择"转到 Azure 门户"以 **启用自助服务密码重置**。</span><span class="sxs-lookup"><span data-stu-id="ea22a-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="ea22a-128">在左侧导航窗格中，**选择"** 用户"，然后在"用户"| **所有用户页面**，选择 **"密码重置"。**</span><span class="sxs-lookup"><span data-stu-id="ea22a-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="ea22a-129">在"**属性**"**页上，选择**"全部"为企业中的每个人启用它，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="ea22a-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="ea22a-130">当用户登录时，系统将提示他们输入其他联系人信息，以帮助他们在将来重置密码。</span><span class="sxs-lookup"><span data-stu-id="ea22a-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="ea22a-131">相关内容</span><span class="sxs-lookup"><span data-stu-id="ea22a-131">Related content</span></span>

[<span data-ttu-id="ea22a-132">为组织设置密码过期策略</span><span class="sxs-lookup"><span data-stu-id="ea22a-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="ea22a-133">将个人用户密码设置为永不过期</span><span class="sxs-lookup"><span data-stu-id="ea22a-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="ea22a-134">Microsoft 365 商业版培训视频</span><span class="sxs-lookup"><span data-stu-id="ea22a-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
