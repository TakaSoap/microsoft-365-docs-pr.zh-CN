---
title: 手动更改 Microsoft 365 商业版计划
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: 通过购买新订阅并确保订阅已列出并处于活动状态来手动更改订阅。
ms.openlocfilehash: fcaa3ebfd9d20fa50c9f37f3366aec9d4dd69103
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046188"
---
# <a name="change-plans-manually"></a><span data-ttu-id="79e39-103">手动更改计划</span><span class="sxs-lookup"><span data-stu-id="79e39-103">Change plans manually</span></span>

## <a name="step-1-decide-how-to-change-plans"></a><span data-ttu-id="79e39-104">步骤1：决定如何更改计划</span><span class="sxs-lookup"><span data-stu-id="79e39-104">Step 1: Decide how to change plans</span></span>

<span data-ttu-id="79e39-105">将所有用户从一个计划更改为另一个计划的最佳方法是[使用 "升级" 选项卡](upgrade-to-different-plan.md)。有时，这是不可能的。</span><span class="sxs-lookup"><span data-stu-id="79e39-105">The best way to change all your users from one plan to another is to [use the Upgrade tab](upgrade-to-different-plan.md). Sometimes this isn't possible.</span></span> <span data-ttu-id="79e39-106">改为手动更改计划：</span><span class="sxs-lookup"><span data-stu-id="79e39-106">Change plans manually instead:</span></span>

- <span data-ttu-id="79e39-107">如果 "**升级**" 选项卡指示您无法升级当前计划。</span><span class="sxs-lookup"><span data-stu-id="79e39-107">If the **Upgrade** tab indicates you can't upgrade the current plan.</span></span>

- <span data-ttu-id="79e39-108">如果选择 "**升级**" 选项卡时，将不会列出所需的计划。</span><span class="sxs-lookup"><span data-stu-id="79e39-108">If, when you select the **Upgrade** tab, the plan you want isn't listed.</span></span>

- <span data-ttu-id="79e39-109">如果您不想以相同的方式升级所有用户。</span><span class="sxs-lookup"><span data-stu-id="79e39-109">If you don't want to upgrade all your users in the same way.</span></span> <span data-ttu-id="79e39-110">一些企业需要订阅不同计划的不同用户。</span><span class="sxs-lookup"><span data-stu-id="79e39-110">Some businesses need different users subscribed to different plans.</span></span> <span data-ttu-id="79e39-111">对此使用手动更改。</span><span class="sxs-lookup"><span data-stu-id="79e39-111">Use a manual change for this.</span></span>

<span data-ttu-id="79e39-112">若要继续进行手动更改，请阅读[第2步：](#step-2-buy-a-new-subscription)在本主题中购买新订阅。</span><span class="sxs-lookup"><span data-stu-id="79e39-112">To continue with a manual change, read [Step 2: Buy a new subscription](#step-2-buy-a-new-subscription) in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79e39-113">如果要将数据相关服务的计划更改为与当前计划（降级）少的计划，则需要手动备份任何要保留的数据。</span><span class="sxs-lookup"><span data-stu-id="79e39-113">If you are changing to a plan with fewer data-related services than your current plan (downgrading), you need to manually back up any data you wish to keep.</span></span> <span data-ttu-id="79e39-114">有关详细信息，请参阅[在更改计划前备份数据](back-up-data-before-switching-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="79e39-114">For more information, see [Back up data before changing plans](back-up-data-before-switching-plans.md).</span></span>

## <a name="step-2-buy-a-new-subscription"></a><span data-ttu-id="79e39-115">步骤2：购买新订阅</span><span class="sxs-lookup"><span data-stu-id="79e39-115">Step 2: Buy a new subscription</span></span>

<span data-ttu-id="79e39-116">**已购买？**</span><span class="sxs-lookup"><span data-stu-id="79e39-116">**Already purchased?**</span></span> <span data-ttu-id="79e39-117">如果您已有要将用户移动到的订阅，请跳过此步骤并转到本主题中的[步骤3：检查您的新订阅和许可证](#step-3-check-your-new-subscription-and-licenses)。</span><span class="sxs-lookup"><span data-stu-id="79e39-117">If you already have a subscription you want to move users to, skip this step and go to [Step 3: Check your new subscription and licenses](#step-3-check-your-new-subscription-and-licenses) in this topic.</span></span>

<span data-ttu-id="79e39-118">OR</span><span class="sxs-lookup"><span data-stu-id="79e39-118">OR</span></span>

<span data-ttu-id="79e39-119">**购买新的订阅和许可证：** 按照 "[购买其他 Microsoft 365 for business 订阅](../buy-another-subscription.md)" 中的步骤购买新订阅。</span><span class="sxs-lookup"><span data-stu-id="79e39-119">**Purchase a new subscription and licenses:** Follow the steps in [Buy another Microsoft 365 for business subscription](../buy-another-subscription.md) to buy a new subscription.</span></span>

<span data-ttu-id="79e39-120">请确保您购买了用户当前所在组织的订阅。</span><span class="sxs-lookup"><span data-stu-id="79e39-120">Make sure you purchase a subscription for the same organization that the users are in now.</span></span> <span data-ttu-id="79e39-121">例如，检查您要移动的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="79e39-121">For example, check the email addresses for the users you want to move.</span></span> <span data-ttu-id="79e39-122">如果他们的电子邮件\@地址包含 contoso.com，则必须购买 contoso.com 的新订阅。</span><span class="sxs-lookup"><span data-stu-id="79e39-122">If their email addresses include \@contoso.com, you must purchase a new subscription for contoso.com.</span></span>
<span data-ttu-id="79e39-123">为您要移动的每个用户包含一个许可证。</span><span class="sxs-lookup"><span data-stu-id="79e39-123">Include a license for each user that you want to move.</span></span>

## <a name="step-3-check-your-new-subscription-and-licenses"></a><span data-ttu-id="79e39-124">步骤3：检查新的订阅和许可证</span><span class="sxs-lookup"><span data-stu-id="79e39-124">Step 3: Check your new subscription and licenses</span></span>

1. <span data-ttu-id="79e39-125">在管理中心中，转到 "**付费** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="79e39-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="79e39-126">**验证这两个订阅是否都已列出并处于活动状态**您要将用户移出的订阅和要将用户移动到的订阅必须一起列出。</span><span class="sxs-lookup"><span data-stu-id="79e39-126">**Verify that both subscriptions are listed and active** The subscription that you're moving users from and the subscription that you're moving users to must be listed together.</span></span> <span data-ttu-id="79e39-127">如果在首次检查时新订阅不在此处，请稍后重试。</span><span class="sxs-lookup"><span data-stu-id="79e39-127">If the new subscription isn't there when you first check, try again later.</span></span> <span data-ttu-id="79e39-128">检查两个订阅是否都处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="79e39-128">Check that both subscriptions are active.</span></span> <span data-ttu-id="79e39-129">[新订阅未列出或未处于活动状态](#the-new-subscription-isnt-listed-or-isnt-active)。</span><span class="sxs-lookup"><span data-stu-id="79e39-129">[The new subscription isn't listed, or isn't active](#the-new-subscription-isnt-listed-or-isnt-active).</span></span>

3. <span data-ttu-id="79e39-130">**检查是否有针对每个用户的足够许可证**每个用户都需要一个与其订阅相匹配的许可证。</span><span class="sxs-lookup"><span data-stu-id="79e39-130">**Check that you have enough licenses for each user** Each user needs a license that matches their subscription.</span></span> <span data-ttu-id="79e39-131">因此，如果要将十个用户移动到 Microsoft 365 商业高级版，则需要确保十个许可证可用。</span><span class="sxs-lookup"><span data-stu-id="79e39-131">So if you want to move ten users to Microsoft 365 Business Premium, you'll need to make sure ten licenses are available.</span></span>

4. <span data-ttu-id="79e39-132">**是否需要新订阅的更多许可证？**</span><span class="sxs-lookup"><span data-stu-id="79e39-132">**Need more licenses for the new subscription?**</span></span>
   <span data-ttu-id="79e39-133">转到 "**产品**" 页面并[购买更多许可证](../licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="79e39-133">Go to the **Your products** page and [buy more licenses](../licenses/buy-licenses.md).</span></span>

> [<span data-ttu-id="79e39-134">旧的许可证是什么？</span><span class="sxs-lookup"><span data-stu-id="79e39-134">What about the old licenses?</span></span>](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a><span data-ttu-id="79e39-135">新订阅未列出，或未处于活动状态</span><span class="sxs-lookup"><span data-stu-id="79e39-135">The new subscription isn't listed, or isn't active</span></span>

- <span data-ttu-id="79e39-136">**如果你购买了两个订阅，但未在此处列出**它们，则可能是为不同的组织（针对不同的域）购买了这些订阅。</span><span class="sxs-lookup"><span data-stu-id="79e39-136">**If you purchased two subscriptions and they are not both listed here**, they may have been purchased for different organizations (for different domains).</span></span> <span data-ttu-id="79e39-137">订阅无法跨组织边界。</span><span class="sxs-lookup"><span data-stu-id="79e39-137">Subscriptions can't cross organization boundaries.</span></span>

- <span data-ttu-id="79e39-138">**如果你知道你有其他订阅**，并且未在此处列出或未处于活动状态，请[致电 Microsoft 支持部门](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="79e39-138">**If you know you have an additional subscription**, and it's not listed here, or is not active, [call Microsoft support](../../admin/contact-support-for-business-products.md).</span></span>

### <a name="what-about-the-old-licenses"></a><span data-ttu-id="79e39-139">旧的许可证是什么？</span><span class="sxs-lookup"><span data-stu-id="79e39-139">What about the old licenses?</span></span>

<span data-ttu-id="79e39-140">将稍后删除当前订阅的许可证;您只需支付新用户许可证的费用。</span><span class="sxs-lookup"><span data-stu-id="79e39-140">The licenses for the current subscription will be removed later; you'll only pay for the new user licenses from then on.</span></span>

## <a name="step-4-reassign-licenses"></a><span data-ttu-id="79e39-141">步骤4：重新分配许可证</span><span class="sxs-lookup"><span data-stu-id="79e39-141">Step 4: Reassign licenses</span></span>

### <a name="reassign-a-license-for-one-user"></a><span data-ttu-id="79e39-142">为一个用户重新分配许可证</span><span class="sxs-lookup"><span data-stu-id="79e39-142">Reassign a license for one user</span></span>

1. <span data-ttu-id="79e39-143">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="79e39-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="79e39-144">在 "**活动用户**" 页上，选择要为其分配许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="79e39-144">On the **Active users** page, select the user to whom you want to assign a license.</span></span>

3. <span data-ttu-id="79e39-145">在 "通过 te**许可证和应用**" 选项卡上，展开 "**许可证**"，选择要分配的许可证对应的框，然后选择 "**保存更改**"。</span><span class="sxs-lookup"><span data-stu-id="79e39-145">On te **Licenses and Apps** tab, expand **Licenses**, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

### <a name="reassign-licenses-for-multiple-users-at-once"></a><span data-ttu-id="79e39-146">一次为多个用户重新分配许可证</span><span class="sxs-lookup"><span data-stu-id="79e39-146">Reassign licenses for multiple users at once</span></span>

1. <span data-ttu-id="79e39-147">在管理中心，转到“**用户**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">活动用户</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="79e39-147">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="79e39-148">选择要为其替换现有许可证的用户的名称旁边的圆圈。</span><span class="sxs-lookup"><span data-stu-id="79e39-148">Select the circles next to the names of the users for whom you want to replace existing licenses.</span></span>

3. <span data-ttu-id="79e39-149">在顶部，选择 "**更多选项**（**...**）"，然后选择 "**管理产品许可证**"。</span><span class="sxs-lookup"><span data-stu-id="79e39-149">At the top, select **More options** (**...**), and then choose **Manage product licenses**.</span></span>

4. <span data-ttu-id="79e39-150">选择" **替换现有的产品许可证分配**"\>" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="79e39-150">Select **Replace existing product license assignments** \> **Next**.</span></span>

5. <span data-ttu-id="79e39-151">将您要分配给这些用户的产品的开关切换到 "**开**" 位置。</span><span class="sxs-lookup"><span data-stu-id="79e39-151">Switch the toggle to the **On** position for the products you want to assign to these users.</span></span>

    > [!TIP]
    > - <span data-ttu-id="79e39-152">若要限制哪些服务对用户可用，请切换到要为该用户删除的服务的**关闭**位置。</span><span class="sxs-lookup"><span data-stu-id="79e39-152">To limit which services are available to the user, switch to toggles to the **Off** position for the services that you want to remove for that user.</span></span> <span data-ttu-id="79e39-153">例如，如果您希望用户能够访问除 Skype for Business Online 之外的所有可用服务，则可以将 Skype for business Online 服务的切换切换到 "**关**" 位置。</span><span class="sxs-lookup"><span data-stu-id="79e39-153">For example, if you want the user to have access to all available services except Skype for Business Online, you can switch the toggle for the Skype for Business Online service to the **Off** position.</span></span>
    > - <span data-ttu-id="79e39-154">这将删除所选用户之前的所有许可证分配。</span><span class="sxs-lookup"><span data-stu-id="79e39-154">Any previous license assignments for the selected users will be removed.</span></span>

6. <span data-ttu-id="79e39-155">在“**替换现有产品**”窗格底部，选择“**替换**”\>“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="79e39-155">At the bottom of the **Replace existing products** pane, select **Replace** \> **Close**.</span></span>

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a><span data-ttu-id="79e39-156">步骤5：取消订阅或删除不再需要的许可证（可选）</span><span class="sxs-lookup"><span data-stu-id="79e39-156">Step 5: Cancel subscriptions or remove licenses that you no longer need (Optional)</span></span>

<span data-ttu-id="79e39-157">If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="79e39-157">If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).</span></span>

<span data-ttu-id="79e39-158">如果仅将一些用户移动到其他订阅，请[删除](../licenses/remove-licenses-from-subscription.md)不再需要的许可证。</span><span class="sxs-lookup"><span data-stu-id="79e39-158">If you moved only some users to a different subscription, [remove licenses](../licenses/remove-licenses-from-subscription.md) that you no longer need.</span></span>

## <a name="call-support-to-help-you-change-plans"></a><span data-ttu-id="79e39-159">致电支持部门以帮助你更改计划</span><span class="sxs-lookup"><span data-stu-id="79e39-159">Call support to help you change plans</span></span>
[<span data-ttu-id="79e39-160">致电 Microsoft 支持部门</span><span class="sxs-lookup"><span data-stu-id="79e39-160">Call Microsoft support</span></span>](../../admin/contact-support-for-business-products.md)