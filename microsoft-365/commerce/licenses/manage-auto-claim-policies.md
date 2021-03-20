---
title: 管理自动声明策略
f1.keywords:
- CSH
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
description: 了解如何创建和管理自动声明策略，这些策略可自动为特定应用的用户分配许可证。
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
ms.openlocfilehash: bf3f79e425b3f7cd86f1a5ab95a337ef5127e345
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911466"
---
# <a name="manage-auto-claim-policies"></a><span data-ttu-id="c528b-103">管理自动声明策略</span><span class="sxs-lookup"><span data-stu-id="c528b-103">Manage auto-claim policies</span></span>

<span data-ttu-id="c528b-104">自动声明策略允许用户在首次登录应用时自动声明产品的许可证。</span><span class="sxs-lookup"><span data-stu-id="c528b-104">An auto-claim policy lets users automatically claim a license for a product the first time that they sign into an app.</span></span> <span data-ttu-id="c528b-105">作为管理员，通常手动或通过使用基于组的许可向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c528b-105">As an admin, you typically assign licenses to users either manually, or by using group-based licensing.</span></span> <span data-ttu-id="c528b-106">通过使用自动声明策略，您可以管理用户可以自动声明许可证的产品。</span><span class="sxs-lookup"><span data-stu-id="c528b-106">By using auto-claim policies, you manage the products for which users can automatically claim licenses.</span></span> <span data-ttu-id="c528b-107">还可以控制这些许可证来自哪些产品。</span><span class="sxs-lookup"><span data-stu-id="c528b-107">You can also control which products those licenses come from.</span></span>

<span data-ttu-id="c528b-108">创建自动声明策略后，可以执行以下任务来管理该策略：</span><span class="sxs-lookup"><span data-stu-id="c528b-108">After you create an auto-claim policy, you can do the following tasks to manage the policy:</span></span>

- [<span data-ttu-id="c528b-109">打开或关闭策略</span><span class="sxs-lookup"><span data-stu-id="c528b-109">Turn the policy on or off</span></span>](#turn-a-policy-on-or-off)
- [<span data-ttu-id="c528b-110">编辑策略友好名称</span><span class="sxs-lookup"><span data-stu-id="c528b-110">Edit the policy friendly name</span></span>](#edit-the-policy-friendly-name)
- [<span data-ttu-id="c528b-111">添加或删除备份产品</span><span class="sxs-lookup"><span data-stu-id="c528b-111">Add or remove backup products</span></span>](#add-or-remove-backup-products)
- [<span data-ttu-id="c528b-112">管理分配的应用和服务</span><span class="sxs-lookup"><span data-stu-id="c528b-112">Manage the assigning apps and services</span></span>](#change-the-assigning-apps-and-services)
- [<span data-ttu-id="c528b-113">更改分配顺序</span><span class="sxs-lookup"><span data-stu-id="c528b-113">Change the assigning order</span></span>](#change-the-assigning-order-for-backup-products)
- [<span data-ttu-id="c528b-114">查看策略报告</span><span class="sxs-lookup"><span data-stu-id="c528b-114">View a policy report</span></span>](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> <span data-ttu-id="c528b-115">自动声明策略当前仅适用于 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="c528b-115">Auto-claim policies are currently only available for Microsoft Teams.</span></span> <span data-ttu-id="c528b-116">将来将有更多的产品可供使用。</span><span class="sxs-lookup"><span data-stu-id="c528b-116">More products will be available to use in the future.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c528b-117">开始之前</span><span class="sxs-lookup"><span data-stu-id="c528b-117">Before you begin</span></span>

<span data-ttu-id="c528b-118">你必须是全局管理员才能创建和管理自动声明策略。</span><span class="sxs-lookup"><span data-stu-id="c528b-118">You must be a Global admin to create and manage auto-claim policies.</span></span> <span data-ttu-id="c528b-119">有关详细信息，请参阅[关于 Microsoft 365 管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="c528b-119">For more information, see [About Microsoft 365 admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a><span data-ttu-id="c528b-120">打开或关闭自动声明策略功能</span><span class="sxs-lookup"><span data-stu-id="c528b-120">Turn the auto-claim policy feature on or off</span></span>

<span data-ttu-id="c528b-121">默认情况下，自动声明策略功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="c528b-121">By default, the auto-claim policy feature is turned off.</span></span> <span data-ttu-id="c528b-122">必须先打开该功能，然后才能使用该功能。</span><span class="sxs-lookup"><span data-stu-id="c528b-122">Before you can use the feature, you must first turn it on.</span></span> <span data-ttu-id="c528b-123">启用该功能后，可以创建自动声明策略。</span><span class="sxs-lookup"><span data-stu-id="c528b-123">After you turn on the feature, you can create an auto-claim policy.</span></span>

### <a name="turn-on-auto-claim-policies"></a><span data-ttu-id="c528b-124">启用自动声明策略</span><span class="sxs-lookup"><span data-stu-id="c528b-124">Turn on auto-claim policies</span></span>

1. <span data-ttu-id="c528b-125">在管理中心，转到"帐单 **""** 许可证" \> 页面，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。</span><span class="sxs-lookup"><span data-stu-id="c528b-125">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="c528b-126">在页面的中心，选择" **打开设置"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="c528b-126">In the center of the page, select the **Turn on setting** button.</span></span>

### <a name="turn-off-auto-claim-policies"></a><span data-ttu-id="c528b-127">关闭自动声明策略</span><span class="sxs-lookup"><span data-stu-id="c528b-127">Turn off auto-claim policies</span></span>

1. <span data-ttu-id="c528b-128">在管理中心，转到 **"设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">""组织设置"</a> 页面。</span><span class="sxs-lookup"><span data-stu-id="c528b-128">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Org settings</a> page.</span></span>
2. <span data-ttu-id="c528b-129">在表底部附近，选择 **"用户拥有的应用和服务"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-129">Near the bottom of the table, select **User owned apps and services**.</span></span>
3. <span data-ttu-id="c528b-130">在右窗格中，清除"允许用户在首次登录时自动声明许可证 **"框**。</span><span class="sxs-lookup"><span data-stu-id="c528b-130">In the right pane, clear the box for **Let users auto-claim licenses the first time they sign in**.</span></span>

<span data-ttu-id="c528b-131">如果已有活动策略，但不希望更多用户申请许可证， [请关闭该策略](#turn-a-policy-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="c528b-131">If you already have an active policy, but you don't want any more users to claim licenses, [turn off the policy](#turn-a-policy-on-or-off).</span></span> <span data-ttu-id="c528b-132">关闭自动声明策略后，再多用户就不再能够声明许可证。</span><span class="sxs-lookup"><span data-stu-id="c528b-132">When you turn off an auto-claim policy, no more users can claim a license from that point on.</span></span> <span data-ttu-id="c528b-133">已声明许可证的用户不会丢失其许可证。</span><span class="sxs-lookup"><span data-stu-id="c528b-133">Users who already claimed a license don't lose their license.</span></span>

## <a name="create-an-auto-claim-policy"></a><span data-ttu-id="c528b-134">创建自动声明策略</span><span class="sxs-lookup"><span data-stu-id="c528b-134">Create an auto-claim policy</span></span>

<span data-ttu-id="c528b-135">" <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a> 选项卡列出了您创建的策略。</span><span class="sxs-lookup"><span data-stu-id="c528b-135">The <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab lists the policies that you create.</span></span> <span data-ttu-id="c528b-136">在此选项卡上，你可以看到：策略的名称、与策略关联的应用、分配给策略的产品、可用许可证的数量以及策略的状态。</span><span class="sxs-lookup"><span data-stu-id="c528b-136">On this tab, you can see: the name of the policy, the app that is associated with the policy, the product that's assigned to the policy, the number of available licenses, and the status of the policy.</span></span>

<span data-ttu-id="c528b-137">创建自动声明策略时，可以添加备份产品。</span><span class="sxs-lookup"><span data-stu-id="c528b-137">When you create an auto-claim policy, you can add a backup product to it.</span></span> <span data-ttu-id="c528b-138">如果主产品没有许可证，则使用备份产品向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c528b-138">If the primary product is out of licenses, the backup product is used to assign licenses to users.</span></span> <span data-ttu-id="c528b-139">您最多可以添加四个备份产品， [并更改它们使用的顺序](#change-the-assigning-order-for-backup-products)。</span><span class="sxs-lookup"><span data-stu-id="c528b-139">You can add up to four backup products and [change the order in which they're used](#change-the-assigning-order-for-backup-products).</span></span> <span data-ttu-id="c528b-140">若要了解更多信息，请参阅 [添加或删除备份产品](#add-or-remove-backup-products)。</span><span class="sxs-lookup"><span data-stu-id="c528b-140">To learn more, see [Add or remove backup products](#add-or-remove-backup-products).</span></span>

> [!NOTE]
> <span data-ttu-id="c528b-141">目前，只能创建一个自动声明策略。</span><span class="sxs-lookup"><span data-stu-id="c528b-141">Currently, you can only create one auto-claim policy.</span></span> <span data-ttu-id="c528b-142">随着更多产品能够使用此功能，可以创建的策略数量将会增加。</span><span class="sxs-lookup"><span data-stu-id="c528b-142">The number of policies you can create will increase as more products are able to use this feature.</span></span>

1. <span data-ttu-id="c528b-143">在管理中心，转到"帐单 **""** 许可证" \> 页面，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。</span><span class="sxs-lookup"><span data-stu-id="c528b-143">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="c528b-144">选择 **"添加策略"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-144">Select **Add a policy**.</span></span>
3. <span data-ttu-id="c528b-145">在"**命名此自动声明策略**"页上，输入策略的名称，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-145">On the **Name this auto-claim policy** page, enter a name for the policy, then select **Next**.</span></span>
4. <span data-ttu-id="c528b-146">在 **"设置自动声明应用** 和产品"页上，选择要为其分配许可证的应用和订阅。</span><span class="sxs-lookup"><span data-stu-id="c528b-146">On the **Set an auto-claim app and product** page, select an app and the subscription to assign licenses from.</span></span>
5. <span data-ttu-id="c528b-147">如果要添加备份产品，请选择"将备份产品添加到此策略 **"，** 然后从列表中选择该产品。</span><span class="sxs-lookup"><span data-stu-id="c528b-147">If you want to add a backup product, select **Add a backup product to this policy**, then select the product from the list.</span></span>
6. <span data-ttu-id="c528b-148">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="c528b-148">Select **Next**.</span></span>
7. <span data-ttu-id="c528b-149">在"**选择应用"** 页上，清除或选择要排除或包括在许可证中的应用的框，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-149">On the **Select apps** page, clear or select the boxes for the apps to exclude or include with the license, then select **Next**.</span></span>
8. <span data-ttu-id="c528b-150">如果添加了一个或多个备份产品，请对每个产品重复步骤 7。</span><span class="sxs-lookup"><span data-stu-id="c528b-150">If you added one or more backup products, repeat step 7 for each product.</span></span> <span data-ttu-id="c528b-151">否则，请转到步骤 9。</span><span class="sxs-lookup"><span data-stu-id="c528b-151">Otherwise, go to step 9.</span></span>
9. <span data-ttu-id="c528b-152">在"**查看并完成"** 页上，验证新策略信息，进行必要的更改，然后选择"创建 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-152">On the **Review and finish** page, verify the new policy information, make any necessary changes, then select **Create policy**.</span></span>
10. <span data-ttu-id="c528b-153">选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="c528b-153">Select **Close**.</span></span>

## <a name="turn-a-policy-on-or-off"></a><span data-ttu-id="c528b-154">打开或关闭策略</span><span class="sxs-lookup"><span data-stu-id="c528b-154">Turn a policy on or off</span></span>

<span data-ttu-id="c528b-155">关闭策略后，其他用户无法根据该策略声明许可证。</span><span class="sxs-lookup"><span data-stu-id="c528b-155">When you turn off a policy, no more users can claim licenses under that policy.</span></span> <span data-ttu-id="c528b-156">更改不会影响已根据该策略声明许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="c528b-156">The change doesn't affect users who already claimed licenses under that policy.</span></span>

1. <span data-ttu-id="c528b-157">在管理中心，转到"帐单 **""** 许可证" \> 页面，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。</span><span class="sxs-lookup"><span data-stu-id="c528b-157">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="c528b-158">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="c528b-158">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="c528b-159">在详细信息窗格中的"打开 **或关闭此策略**"下，选中或清除复选框。</span><span class="sxs-lookup"><span data-stu-id="c528b-159">In the details pane, under **Turn this policy on or off**, select or clear the check box.</span></span>
4. <span data-ttu-id="c528b-160">选择 **"保存** "以关闭详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="c528b-160">Select **Save** to close the details pane.</span></span>

## <a name="edit-the-policy-friendly-name"></a><span data-ttu-id="c528b-161">编辑策略友好名称</span><span class="sxs-lookup"><span data-stu-id="c528b-161">Edit the policy friendly name</span></span>

1. <span data-ttu-id="c528b-162">在管理中心，转到"帐单 **""** 许可证" \> 页面，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。</span><span class="sxs-lookup"><span data-stu-id="c528b-162">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="c528b-163">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="c528b-163">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="c528b-164">在详细信息窗格中的"策略名称 **"** 部分，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-164">In the details pane, in the **Policy name** section, select **Edit**.</span></span>
4. <span data-ttu-id="c528b-165">输入新策略名称，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-165">Enter a new policy name, then select **Save**.</span></span>
5. <span data-ttu-id="c528b-166">选择 **"保存** "以关闭详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="c528b-166">Select **Save** to close the details pane.</span></span>

## <a name="add-or-remove-backup-products"></a><span data-ttu-id="c528b-167">添加或删除备份产品</span><span class="sxs-lookup"><span data-stu-id="c528b-167">Add or remove backup products</span></span>

<span data-ttu-id="c528b-168">创建策略时，需要向策略中添加产品。</span><span class="sxs-lookup"><span data-stu-id="c528b-168">When you create a policy, you add a product to it.</span></span> <span data-ttu-id="c528b-169">然后，许可证将自动分配给该许可证池中的用户。</span><span class="sxs-lookup"><span data-stu-id="c528b-169">Licenses are then automatically assigned to users from that pool of licenses.</span></span> <span data-ttu-id="c528b-170">您随时都可以添加或删除自动声明策略的产品。</span><span class="sxs-lookup"><span data-stu-id="c528b-170">You can add or remove products for an auto-claim policy at any time.</span></span> <span data-ttu-id="c528b-171">如果已有一个与策略关联的产品，则添加的任何产品都将被视为备份产品。</span><span class="sxs-lookup"><span data-stu-id="c528b-171">If you already have one product associated with the policy, any products that you add are considered backup products.</span></span> <span data-ttu-id="c528b-172">当使用第一个产品的可用许可证数量时，策略将使用列表中的下一个备份产品来分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c528b-172">When the available number of licenses from the first product are used up, the policy uses the next backup product on the list to assign licenses from.</span></span> <span data-ttu-id="c528b-173">[您可以根据你的需求对产品列表](#change-the-assigning-apps-and-services)重新排序。</span><span class="sxs-lookup"><span data-stu-id="c528b-173">You [can reorder the list of products](#change-the-assigning-apps-and-services) as you like.</span></span>

<span data-ttu-id="c528b-174">删除备份产品时，它不再用于分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c528b-174">When you remove a backup product, it's no longer used to assign licenses.</span></span> <span data-ttu-id="c528b-175">具有现有许可证的用户仍拥有该许可证，但任何新用户无法接收该产品的许可证。</span><span class="sxs-lookup"><span data-stu-id="c528b-175">Users with an existing license still have that license, but no new users can receive licenses for that product.</span></span>

> [!NOTE]
> <span data-ttu-id="c528b-176">自动声明策略必须至少包含一个产品。</span><span class="sxs-lookup"><span data-stu-id="c528b-176">An auto-claim policy must contain at least one product.</span></span> <span data-ttu-id="c528b-177">无法从策略中删除所有产品。</span><span class="sxs-lookup"><span data-stu-id="c528b-177">You can't remove all products from a policy.</span></span> <span data-ttu-id="c528b-178">如果不想再分配来自特定自动声明策略的许可证， [请关闭该策略](#view-an-auto-claim-policy-report)。</span><span class="sxs-lookup"><span data-stu-id="c528b-178">If you don't want to assign licenses from a specific auto-claim policy anymore, [turn off the policy](#view-an-auto-claim-policy-report).</span></span>

### <a name="add-a-backup-product"></a><span data-ttu-id="c528b-179">添加备份产品</span><span class="sxs-lookup"><span data-stu-id="c528b-179">Add a backup product</span></span>

1. <span data-ttu-id="c528b-180">在管理中心，转到"帐单 **""** 许可证" \> 页面，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。</span><span class="sxs-lookup"><span data-stu-id="c528b-180">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="c528b-181">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="c528b-181">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="c528b-182">在详细信息窗格中的底部，选择 **"将备份产品添加到此策略"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-182">In the details pane, at the bottom, select **Add a backup product to this policy**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="c528b-183">如果你看不到此链接，这是因为你只有一个与帐户关联的产品。</span><span class="sxs-lookup"><span data-stu-id="c528b-183">If you don't see this link, it's because you only have one product associated with your account.</span></span>
4. <span data-ttu-id="c528b-184">在 **"添加产品"** 窗格中，使用下拉列表选择要添加到策略的产品，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-184">In the **Add a product** pane, use the drop-down to choose a product to add to the policy, then select **Add**.</span></span>
5. <span data-ttu-id="c528b-185">选择 **"保存** "以关闭详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="c528b-185">Select **Save** to close the details pane.</span></span>

### <a name="remove-a-backup-product"></a><span data-ttu-id="c528b-186">删除备份产品</span><span class="sxs-lookup"><span data-stu-id="c528b-186">Remove a backup product</span></span>

1. <span data-ttu-id="c528b-187">在管理中心，转到"帐单 **""** 许可证" \> 页面，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。</span><span class="sxs-lookup"><span data-stu-id="c528b-187">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="c528b-188">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="c528b-188">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="c528b-189">在详细信息窗格中的底部，选择"**删除产品"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-189">In the details pane, at the bottom, select **Remove a product**.</span></span>
4. <span data-ttu-id="c528b-190">在 **"从策略中删除** 产品"窗格中，选择要删除的策略的框，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-190">In the **Remove a product from the policy** pane, select the box for the policy that you want to remove, then select **Save**.</span></span>
5. <span data-ttu-id="c528b-191">关闭详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="c528b-191">Close the details pane.</span></span>

## <a name="change-the-assigning-apps-and-services"></a><span data-ttu-id="c528b-192">更改分配的应用和服务</span><span class="sxs-lookup"><span data-stu-id="c528b-192">Change the assigning apps and services</span></span>

<span data-ttu-id="c528b-193">每个产品都有一组与其关联的应用和服务。</span><span class="sxs-lookup"><span data-stu-id="c528b-193">Each product has a collection of apps and services associated with it.</span></span>
<span data-ttu-id="c528b-194">对于自动声明策略中的每种产品，可以指定在自动为用户分配产品许可证时包含哪些应用和服务。</span><span class="sxs-lookup"><span data-stu-id="c528b-194">For each product in your auto-claim policy, you can specify which apps and services to include when a user is automatically assigned a license to that product.</span></span>

1. <span data-ttu-id="c528b-195">在管理中心，转到"帐单 **""** 许可证" \> 页面，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。</span><span class="sxs-lookup"><span data-stu-id="c528b-195">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="c528b-196">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="c528b-196">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="c528b-197">在详细信息窗格中的"应用和服务 **"下**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-197">In the details pane, under **Apps and services**, select **Edit**.</span></span>
4. <span data-ttu-id="c528b-198">在"**应用和服务**"窗格中，从"产品"下拉列表中选择一个产品，或选择"**所有产品"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-198">In the **Apps and services** pane, from the **Product** drop-down, select a single product, or select **All products**.</span></span>
5. <span data-ttu-id="c528b-199">选中或清除希望用户拥有或无法访问的应用和服务框。</span><span class="sxs-lookup"><span data-stu-id="c528b-199">Check or clear the boxes for apps and services that you want users to have or not have access to.</span></span>
6. <span data-ttu-id="c528b-200">完成后，选择"保存 **"，** 然后关闭详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="c528b-200">When you're finished, select **Save**, then close the details pane.</span></span>

## <a name="change-the-assigning-order-for-backup-products"></a><span data-ttu-id="c528b-201">更改备份产品的分配顺序</span><span class="sxs-lookup"><span data-stu-id="c528b-201">Change the assigning order for backup products</span></span>

<span data-ttu-id="c528b-202">如果为策略分配了备份产品，可以在用户登录应用时更改用于分配许可证的顺序。</span><span class="sxs-lookup"><span data-stu-id="c528b-202">If you have backup products assigned to the policy, you can change the order in which they're used to assign licenses when users sign in to the app.</span></span>

1. <span data-ttu-id="c528b-203">在管理中心，转到"帐单 **""** 许可证" \> 页面，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。</span><span class="sxs-lookup"><span data-stu-id="c528b-203">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="c528b-204">选择要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="c528b-204">Select the policy that you want to edit.</span></span>
3. <span data-ttu-id="c528b-205">在详细信息窗格中的"产品许可证 **"部分，** 选择要移动的产品旁边的框，然后选择"**上** 移"或"**下移"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-205">In the details pane, in the **Product licenses** section, select the box next to the product that you want to move, then select **Move up** or **Move down**.</span></span>
4. <span data-ttu-id="c528b-206">对要重新排序的每个产品重复步骤 3。</span><span class="sxs-lookup"><span data-stu-id="c528b-206">Repeat step 3 for each product that you want to reorder.</span></span>
5. <span data-ttu-id="c528b-207">完成产品重新排序后，选择"保存"关闭详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="c528b-207">When you're finished reordering the products, select **Save** to close the details pane.</span></span>

## <a name="view-an-auto-claim-policy-report"></a><span data-ttu-id="c528b-208">查看自动声明策略报告</span><span class="sxs-lookup"><span data-stu-id="c528b-208">View an auto-claim policy report</span></span>

1. <span data-ttu-id="c528b-209">在管理中心，转到"帐单 **""** 许可证" \> 页面，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">自动声明策略"</a>选项卡。</span><span class="sxs-lookup"><span data-stu-id="c528b-209">In the admin center, go to the **Billing** \> **Licenses** page, then select the <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Auto-claim policy</a> tab.</span></span>
2. <span data-ttu-id="c528b-210">选择 **"查看报告"。**</span><span class="sxs-lookup"><span data-stu-id="c528b-210">Select **View report**.</span></span> <span data-ttu-id="c528b-211">" **自动声明策略报告"** 页列出了过去 90 天内从每个策略分配的所有许可证。</span><span class="sxs-lookup"><span data-stu-id="c528b-211">The **Auto-claim policy report** page lists all licenses assigned from each policy in the last 90 days.</span></span> <span data-ttu-id="c528b-212">默认情况下，页面显示过去 90 天。</span><span class="sxs-lookup"><span data-stu-id="c528b-212">By default, the page shows the past 90 days.</span></span>
3. <span data-ttu-id="c528b-213">若要更改显示的时间段，请选择"过去 **30** 天"下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c528b-213">To change the time period shown, select the **Past 30 days** drop-down list.</span></span> <span data-ttu-id="c528b-214">可以查看过去 1、7、30 和 90 天的报告。</span><span class="sxs-lookup"><span data-stu-id="c528b-214">You can view reports for the past 1, 7, 30, and 90 days.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c528b-215">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c528b-215">Next steps</span></span>

<span data-ttu-id="c528b-216">你可以定期返回到自动声明 **策略** 选项卡，以查看已根据你创建的策略声明许可证的用户列表。</span><span class="sxs-lookup"><span data-stu-id="c528b-216">You can periodically return to the **Auto-claim policy** tab to see a list of users who have claimed licenses under the policies you created.</span></span>

## <a name="related-content"></a><span data-ttu-id="c528b-217">相关内容</span><span class="sxs-lookup"><span data-stu-id="c528b-217">Related content</span></span>

<span data-ttu-id="c528b-218">[向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="c528b-218">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)\</span></span>
<span data-ttu-id="c528b-219">[购买或删除订阅许可证](buy-licenses.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="c528b-219">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>\
<span data-ttu-id="c528b-220">[了解本文 (](subscriptions-and-licenses.md) 订阅和) </span><span class="sxs-lookup"><span data-stu-id="c528b-220">[Understand subscriptions and licenses](subscriptions-and-licenses.md) (article)</span></span>