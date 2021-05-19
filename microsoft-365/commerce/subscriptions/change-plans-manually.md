---
title: 手动Microsoft 365更改商业计划更新
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: 通过购买新订阅并确保两个订阅都列出且处于活动状态，手动更改订阅。
ROBOTS: NOINDEX
ms.date: 03/17/2021
ms.openlocfilehash: f5a44b7a3c01883ed42ca4ed203b63ccf77f9b72
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536102"
---
# <a name="change-plans-manually"></a><span data-ttu-id="2746d-103">手动更改计划</span><span class="sxs-lookup"><span data-stu-id="2746d-103">Change plans manually</span></span>

## <a name="step-1-decide-how-to-change-plans"></a><span data-ttu-id="2746d-104">步骤 1：确定如何更改计划</span><span class="sxs-lookup"><span data-stu-id="2746d-104">Step 1: Decide how to change plans</span></span>

<span data-ttu-id="2746d-105">将所有用户从一个计划更改为另一个计划的最佳方法就是 [使用"升级"选项卡](upgrade-to-different-plan.md)。有时这不可能。</span><span class="sxs-lookup"><span data-stu-id="2746d-105">The best way to change all your users from one plan to another is to [use the Upgrade tab](upgrade-to-different-plan.md). Sometimes this isn't possible.</span></span> <span data-ttu-id="2746d-106">改为手动更改计划：</span><span class="sxs-lookup"><span data-stu-id="2746d-106">Change plans manually instead:</span></span>

- <span data-ttu-id="2746d-107">如果 **"** 升级"选项卡指示无法升级当前计划。</span><span class="sxs-lookup"><span data-stu-id="2746d-107">If the **Upgrade** tab indicates you can't upgrade the current plan.</span></span>

- <span data-ttu-id="2746d-108">If， when you select the **Upgrade** tab， the plan you want isn't listed.</span><span class="sxs-lookup"><span data-stu-id="2746d-108">If, when you select the **Upgrade** tab, the plan you want isn't listed.</span></span>

- <span data-ttu-id="2746d-109">如果您不想以相同方式升级所有用户。</span><span class="sxs-lookup"><span data-stu-id="2746d-109">If you don't want to upgrade all your users in the same way.</span></span> <span data-ttu-id="2746d-110">一些企业需要订阅不同计划的不同用户。</span><span class="sxs-lookup"><span data-stu-id="2746d-110">Some businesses need different users subscribed to different plans.</span></span> <span data-ttu-id="2746d-111">对此使用手动更改。</span><span class="sxs-lookup"><span data-stu-id="2746d-111">Use a manual change for this.</span></span>

<span data-ttu-id="2746d-112">若要继续手动更改，请阅读本主题中的 [步骤 2：](#step-2-buy-a-new-subscription) 购买新订阅。</span><span class="sxs-lookup"><span data-stu-id="2746d-112">To continue with a manual change, read [Step 2: Buy a new subscription](#step-2-buy-a-new-subscription) in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2746d-113">如果要更改的计划与数据相关的服务数少于当前计划 (降级) ，则需要手动备份要保留的任何数据。</span><span class="sxs-lookup"><span data-stu-id="2746d-113">If you are changing to a plan with fewer data-related services than your current plan (downgrading), you need to manually back up any data you wish to keep.</span></span> <span data-ttu-id="2746d-114">有关详细信息，请参阅在 [更改计划之前备份数据](back-up-data-before-switching-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="2746d-114">For more information, see [Back up data before changing plans](back-up-data-before-switching-plans.md).</span></span>

## <a name="step-2-buy-a-new-subscription"></a><span data-ttu-id="2746d-115">步骤 2：购买新订阅</span><span class="sxs-lookup"><span data-stu-id="2746d-115">Step 2: Buy a new subscription</span></span>

<span data-ttu-id="2746d-116">**已购买？**</span><span class="sxs-lookup"><span data-stu-id="2746d-116">**Already purchased?**</span></span> <span data-ttu-id="2746d-117">如果你已有想要将用户移动到的订阅，请跳过此步骤并转到本主题中的步骤 [3：检查](#step-3-check-your-new-subscription-and-licenses) 新订阅和许可证。</span><span class="sxs-lookup"><span data-stu-id="2746d-117">If you already have a subscription you want to move users to, skip this step and go to [Step 3: Check your new subscription and licenses](#step-3-check-your-new-subscription-and-licenses) in this topic.</span></span>

<span data-ttu-id="2746d-118">OR</span><span class="sxs-lookup"><span data-stu-id="2746d-118">OR</span></span>

<span data-ttu-id="2746d-119">**购买新订阅和许可证：** 按照购买另 [一Microsoft 365商业版订阅中的步骤](../try-or-buy-microsoft-365.md)购买新订阅。</span><span class="sxs-lookup"><span data-stu-id="2746d-119">**Purchase a new subscription and licenses:** Follow the steps in [Buy another Microsoft 365 for business subscription](../try-or-buy-microsoft-365.md) to buy a new subscription.</span></span>

<span data-ttu-id="2746d-120">请确保为用户当前在同一组织购买订阅。</span><span class="sxs-lookup"><span data-stu-id="2746d-120">Make sure you purchase a subscription for the same organization that the users are in now.</span></span> <span data-ttu-id="2746d-121">例如，检查要移动的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2746d-121">For example, check the email addresses for the users you want to move.</span></span> <span data-ttu-id="2746d-122">如果他们的电子邮件地址包含 contoso.com，则必须购买新订阅 \@ contoso.com。</span><span class="sxs-lookup"><span data-stu-id="2746d-122">If their email addresses include \@contoso.com, you must purchase a new subscription for contoso.com.</span></span>
<span data-ttu-id="2746d-123">包括要移动的每个用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="2746d-123">Include a license for each user that you want to move.</span></span>

## <a name="step-3-check-your-new-subscription-and-licenses"></a><span data-ttu-id="2746d-124">步骤 3：检查新订阅和许可证</span><span class="sxs-lookup"><span data-stu-id="2746d-124">Step 3: Check your new subscription and licenses</span></span>

1. <span data-ttu-id="2746d-125">在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="2746d-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="2746d-126">**验证这两个订阅是否列出且处于活动状态** 用户迁移自的订阅和要移动用户的订阅必须一起列出。</span><span class="sxs-lookup"><span data-stu-id="2746d-126">**Verify that both subscriptions are listed and active** The subscription that you're moving users from and the subscription that you're moving users to must be listed together.</span></span> <span data-ttu-id="2746d-127">如果首次检查时新订阅不存在，请稍后重试。</span><span class="sxs-lookup"><span data-stu-id="2746d-127">If the new subscription isn't there when you first check, try again later.</span></span> <span data-ttu-id="2746d-128">检查这两个订阅是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="2746d-128">Check that both subscriptions are active.</span></span> <span data-ttu-id="2746d-129">[新订阅未列出，或不是活动订阅](#the-new-subscription-isnt-listed-or-isnt-active)。</span><span class="sxs-lookup"><span data-stu-id="2746d-129">[The new subscription isn't listed, or isn't active](#the-new-subscription-isnt-listed-or-isnt-active).</span></span>

3. <span data-ttu-id="2746d-130">**检查是否有足够的许可证供每个用户使用** 每个用户都需要一个匹配其订阅的许可证。</span><span class="sxs-lookup"><span data-stu-id="2746d-130">**Check that you have enough licenses for each user** Each user needs a license that matches their subscription.</span></span> <span data-ttu-id="2746d-131">因此，如果你想要将 10 个用户Microsoft 365 商业高级版，你将需要确保 10 个许可证可用。</span><span class="sxs-lookup"><span data-stu-id="2746d-131">So if you want to move ten users to Microsoft 365 Business Premium, you'll need to make sure ten licenses are available.</span></span>

4. <span data-ttu-id="2746d-132">**需要新订阅的更多许可证？**</span><span class="sxs-lookup"><span data-stu-id="2746d-132">**Need more licenses for the new subscription?**</span></span>
   <span data-ttu-id="2746d-133">转到你的 **产品页面** 并 [购买更多许可证](../licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="2746d-133">Go to the **Your products** page and [buy more licenses](../licenses/buy-licenses.md).</span></span>

> [<span data-ttu-id="2746d-134">旧许可证呢？</span><span class="sxs-lookup"><span data-stu-id="2746d-134">What about the old licenses?</span></span>](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a><span data-ttu-id="2746d-135">新订阅未列出或未处于活动状态</span><span class="sxs-lookup"><span data-stu-id="2746d-135">The new subscription isn't listed, or isn't active</span></span>

- <span data-ttu-id="2746d-136">**如果您购买了两个** 订阅，但此处未列出这两个订阅，则它们可能是为不同组织购买， (用于不同域) 。</span><span class="sxs-lookup"><span data-stu-id="2746d-136">**If you purchased two subscriptions and they are not both listed here**, they may have been purchased for different organizations (for different domains).</span></span> <span data-ttu-id="2746d-137">订阅不能跨越组织边界。</span><span class="sxs-lookup"><span data-stu-id="2746d-137">Subscriptions can't cross organization boundaries.</span></span>

- <span data-ttu-id="2746d-138">**如果您知道您具有其他订阅**，并且此处未列出，或者它未处于活动状态， [请致电 Microsoft 支持](../../business-video/get-help-support.md)人员。</span><span class="sxs-lookup"><span data-stu-id="2746d-138">**If you know you have an additional subscription**, and it's not listed here, or is not active, [call Microsoft support](../../business-video/get-help-support.md).</span></span>

### <a name="what-about-the-old-licenses"></a><span data-ttu-id="2746d-139">旧许可证呢？</span><span class="sxs-lookup"><span data-stu-id="2746d-139">What about the old licenses?</span></span>

<span data-ttu-id="2746d-140">当前订阅的许可证将在以后删除;你稍后将仅支付新用户许可证。</span><span class="sxs-lookup"><span data-stu-id="2746d-140">The licenses for the current subscription will be removed later; you'll only pay for the new user licenses from then on.</span></span>

## <a name="step-4-reassign-licenses"></a><span data-ttu-id="2746d-141">步骤 4：重新分配许可证</span><span class="sxs-lookup"><span data-stu-id="2746d-141">Step 4: Reassign licenses</span></span>

### <a name="reassign-a-license-for-one-user"></a><span data-ttu-id="2746d-142">为一个用户重新分配许可证</span><span class="sxs-lookup"><span data-stu-id="2746d-142">Reassign a license for one user</span></span>

1. <span data-ttu-id="2746d-143">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="2746d-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="2746d-144">在 **"活动用户** "页上，选择要为其分配许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="2746d-144">On the **Active users** page, select the user to whom you want to assign a license.</span></span>

3. <span data-ttu-id="2746d-145">在"**许可证和应用"** 选项卡上，展开"许可证 **"，** 选择要分配的许可证的框，然后选择"保存 **更改"。**</span><span class="sxs-lookup"><span data-stu-id="2746d-145">On the **Licenses and Apps** tab, expand **Licenses**, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

### <a name="reassign-licenses-for-multiple-users-at-once"></a><span data-ttu-id="2746d-146">一次为多个用户重新分配许可证</span><span class="sxs-lookup"><span data-stu-id="2746d-146">Reassign licenses for multiple users at once</span></span>

1. <span data-ttu-id="2746d-147">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="2746d-147">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="2746d-148">选择要替换现有许可证的用户姓名旁边的圆圈。</span><span class="sxs-lookup"><span data-stu-id="2746d-148">Select the circles next to the names of the users for whom you want to replace existing licenses.</span></span>

3. <span data-ttu-id="2746d-149">At the top， select the three dots (more actions) ， and then choose **Manage product licenses**.</span><span class="sxs-lookup"><span data-stu-id="2746d-149">At the top, select the three dots (more actions), and then choose **Manage product licenses**.</span></span>

4. <span data-ttu-id="2746d-150">选择" **替换现有的产品许可证分配**"\>" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2746d-150">Select **Replace existing product license assignments** \> **Next**.</span></span>

5. <span data-ttu-id="2746d-151">将要分配给 **这些用户** 的产品的开关切换到"开"位置。</span><span class="sxs-lookup"><span data-stu-id="2746d-151">Switch the toggle to the **On** position for the products you want to assign to these users.</span></span>

    > [!TIP]
    > - <span data-ttu-id="2746d-152">若要限制哪些服务可供用户使用，请切换到要为该用户删除的服务的"关"位置。</span><span class="sxs-lookup"><span data-stu-id="2746d-152">To limit which services are available to the user, switch to toggles to the **Off** position for the services that you want to remove for that user.</span></span> <span data-ttu-id="2746d-153">例如，如果希望用户能够访问除 Skype for Business Online 之外的所有可用服务，可以将 Skype for Business Online 服务的开关切换到"关 **"位置。**</span><span class="sxs-lookup"><span data-stu-id="2746d-153">For example, if you want the user to have access to all available services except Skype for Business Online, you can switch the toggle for the Skype for Business Online service to the **Off** position.</span></span>
    > - <span data-ttu-id="2746d-154">这将删除所选用户之前的所有许可证分配。</span><span class="sxs-lookup"><span data-stu-id="2746d-154">Any previous license assignments for the selected users will be removed.</span></span>

6. <span data-ttu-id="2746d-155">在“**替换现有产品**”窗格底部，选择“**替换**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="2746d-155">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a><span data-ttu-id="2746d-156">步骤 5：取消订阅或删除不再需要的许可证 (可选) </span><span class="sxs-lookup"><span data-stu-id="2746d-156">Step 5: Cancel subscriptions or remove licenses that you no longer need (Optional)</span></span>

<span data-ttu-id="2746d-157">If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="2746d-157">If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).</span></span>

<span data-ttu-id="2746d-158">如果仅将部分用户移动到其他订阅 [，请删除](../licenses/buy-licenses.md) 不再需要的许可证。</span><span class="sxs-lookup"><span data-stu-id="2746d-158">If you moved only some users to a different subscription, [remove licenses](../licenses/buy-licenses.md) that you no longer need.</span></span>

## <a name="call-support-to-help-you-change-plans"></a><span data-ttu-id="2746d-159">致电支持人员，帮助你更改计划</span><span class="sxs-lookup"><span data-stu-id="2746d-159">Call support to help you change plans</span></span>
[<span data-ttu-id="2746d-160">致电 Microsoft 支持人员</span><span class="sxs-lookup"><span data-stu-id="2746d-160">Call Microsoft support</span></span>](../../business-video/get-help-support.md)
