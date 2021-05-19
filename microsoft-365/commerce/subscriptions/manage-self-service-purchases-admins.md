---
title: '管理管理员管理员 (自助服务) '
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce_ssp
search.appverid:
- MET150
description: 管理员可以了解如何管理其组织中用户购买的自助服务。
ms.date: 03/26/2021
ms.openlocfilehash: a4ac4b79a9a73f80fc22e6f14696e25925df9faf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536090"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="75d80-103">管理自助购买（管理员）</span><span class="sxs-lookup"><span data-stu-id="75d80-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="75d80-104">作为管理员，你可以查看组织中人员购买的自助服务。</span><span class="sxs-lookup"><span data-stu-id="75d80-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="75d80-105">你会看到产品名称、购买者名称、购买的订阅、到期日期、购买价格以及每个自助购买的已分配用户。</span><span class="sxs-lookup"><span data-stu-id="75d80-105">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="75d80-106">如果组织要求，可以通过 PowerShell 关闭按产品进行自助购买。</span><span class="sxs-lookup"><span data-stu-id="75d80-106">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="75d80-107">对于通过自助购买或集中购买的产品，您具有相同的数据管理和访问策略。</span><span class="sxs-lookup"><span data-stu-id="75d80-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="75d80-108">还可以控制贵组织的用户是否可以进行自助购买。</span><span class="sxs-lookup"><span data-stu-id="75d80-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="75d80-109">有关详细信息，请参阅将 [AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="75d80-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="75d80-110">查看自助服务订阅</span><span class="sxs-lookup"><span data-stu-id="75d80-110">View self-service subscriptions</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="75d80-111">在管理中心中，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="75d80-112">在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-112">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="75d80-113">在管理中心中，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-113">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="75d80-114">在"**产品**"选项卡上，选择筛选器图标，然后选择"**自助服务"。**</span><span class="sxs-lookup"><span data-stu-id="75d80-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="75d80-115">若要查看有关订阅的更多详细信息，请从列表中选择一个。</span><span class="sxs-lookup"><span data-stu-id="75d80-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="75d80-116">查看谁拥有自助服务购买订阅的许可证</span><span class="sxs-lookup"><span data-stu-id="75d80-116">View who has licenses for a self-service purchase subscription</span></span>

> [!NOTE]
> <span data-ttu-id="75d80-117">作为管理员，你不能为组织中用户购买的自助购买订阅分配或取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="75d80-117">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="75d80-118">你可以 [接管自助购买订阅](#take-over-a-self-service-purchase-subscription)，然后分配或取消分配许可证。</span><span class="sxs-lookup"><span data-stu-id="75d80-118">You can [take over a self-service purchase subscription](#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="75d80-119">在管理中心，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="75d80-120">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="75d80-121">在管理中心，转到“**计费**”\>“<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">许可证</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="75d80-122">选择筛选器图标，然后选择 **"自助服务"。**</span><span class="sxs-lookup"><span data-stu-id="75d80-122">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="75d80-123">选择一个产品以查看分配给人员的许可。</span><span class="sxs-lookup"><span data-stu-id="75d80-123">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="75d80-124">如果产品有多个购买，则该产品仅列出一次，"可用数量"列显示为该产品购买的所有订阅总数。</span><span class="sxs-lookup"><span data-stu-id="75d80-124">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="75d80-125">" **用户** "列表按进行自助购买的用户的姓名进行分组。</span><span class="sxs-lookup"><span data-stu-id="75d80-125">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="75d80-126">若要导出具有这些订阅许可证的用户列表，请选择要导出的订阅，然后选择"导出 **用户"。**</span><span class="sxs-lookup"><span data-stu-id="75d80-126">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="75d80-127">禁用或启用自助服务购买</span><span class="sxs-lookup"><span data-stu-id="75d80-127">Disable or enable self-service purchases</span></span>

<span data-ttu-id="75d80-128">您可以禁用或启用组织中用户的自助购买。</span><span class="sxs-lookup"><span data-stu-id="75d80-128">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="75d80-129">**MSCommerce** PowerShell 模块包括 **AllowSelfServicePurchase** 的 **PolicyID** 参数值，可用于控制组织中用户是否可以进行自助购买以及针对哪些产品进行购买。</span><span class="sxs-lookup"><span data-stu-id="75d80-129">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="75d80-130">您可以使用 **MSCommerce** PowerShell 模块：</span><span class="sxs-lookup"><span data-stu-id="75d80-130">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="75d80-131">查看 **AllowSelfServicePurchase** 参数值的默认状态 — 是按产品启用还是禁用</span><span class="sxs-lookup"><span data-stu-id="75d80-131">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="75d80-132">查看适用产品的列表，以及自助服务购买是启用还是禁用</span><span class="sxs-lookup"><span data-stu-id="75d80-132">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="75d80-133">查看或修改特定产品的当前设置以启用或禁用它</span><span class="sxs-lookup"><span data-stu-id="75d80-133">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="75d80-134">有关详细信息，请参阅将 [AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="75d80-134">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="75d80-135">在单个订阅下集中许可证</span><span class="sxs-lookup"><span data-stu-id="75d80-135">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="75d80-136">可以通过分配给自助服务购买的用户的现有协议分配现有许可证或购买其他订阅。</span><span class="sxs-lookup"><span data-stu-id="75d80-136">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="75d80-137">分配这些集中购买的许可证后，你可以请求购买者取消其现有订阅。</span><span class="sxs-lookup"><span data-stu-id="75d80-137">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="75d80-138">In the admin center go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span><span class="sxs-lookup"><span data-stu-id="75d80-138">In the admin center go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="75d80-139">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>，转到 **账单** > **购买服务** 页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-139">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="75d80-140">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，转到 **账单** > **购买服务** 页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-140">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

2. <span data-ttu-id="75d80-141">找到并选择要购买的产品，然后选择"购买 **"。**</span><span class="sxs-lookup"><span data-stu-id="75d80-141">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="75d80-142">完成其余步骤以完成购买。</span><span class="sxs-lookup"><span data-stu-id="75d80-142">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="75d80-143">按照查看 [谁拥有](#view-who-has-licenses-for-a-self-service-purchase-subscription) 自助购买订阅的许可证中的步骤导出要下一步引用的用户列表。</span><span class="sxs-lookup"><span data-stu-id="75d80-143">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="75d80-144">将许可证分配给在其他订阅中拥有许可证的每个人。</span><span class="sxs-lookup"><span data-stu-id="75d80-144">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="75d80-145">有关完整步骤，请参阅 [向用户分配许可证](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="75d80-145">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="75d80-146">与购买自助服务购买订阅的人联系，并要求他们 [取消订阅](manage-self-service-purchases-users.md#cancel-a-subscription)。</span><span class="sxs-lookup"><span data-stu-id="75d80-146">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="75d80-147">接管自助服务购买订阅</span><span class="sxs-lookup"><span data-stu-id="75d80-147">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="75d80-148">你可以接管组织中用户购买的自助服务购买订阅。</span><span class="sxs-lookup"><span data-stu-id="75d80-148">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="75d80-149">当你接管自助服务购买订阅时，你有两个选项：</span><span class="sxs-lookup"><span data-stu-id="75d80-149">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="75d80-150">将用户移动到其他订阅并取消原始订阅。</span><span class="sxs-lookup"><span data-stu-id="75d80-150">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="75d80-151">取消自助购买订阅，并删除已分配用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="75d80-151">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="75d80-152">将用户移动到其他订阅</span><span class="sxs-lookup"><span data-stu-id="75d80-152">Move users to a different subscription</span></span>

<span data-ttu-id="75d80-153">将用户移动到其他订阅时，旧订阅将自动取消。</span><span class="sxs-lookup"><span data-stu-id="75d80-153">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="75d80-154">最初购买自助服务购买订阅的用户将收到一封电子邮件，指出订阅已取消。</span><span class="sxs-lookup"><span data-stu-id="75d80-154">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="75d80-155">对于要移动用户的订阅中的每个用户，你必须拥有可用的许可证。</span><span class="sxs-lookup"><span data-stu-id="75d80-155">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="75d80-156">在管理中心中，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="75d80-157">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，转到" **帐单** > **""产品"** 页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-157">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="75d80-158">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，转到" **帐单** > **""产品"** 页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-158">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="75d80-159">在"**产品**"选项卡上，选择筛选器图标，然后选择"**自助服务"。**</span><span class="sxs-lookup"><span data-stu-id="75d80-159">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="75d80-160">选择要接管的订阅。</span><span class="sxs-lookup"><span data-stu-id="75d80-160">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="75d80-161">On the subscription details page， in the **Subscriptions and settings** section， select **Take control of this subscription**.</span><span class="sxs-lookup"><span data-stu-id="75d80-161">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="75d80-162">在右侧窗格中，选择"**移动用户"。**</span><span class="sxs-lookup"><span data-stu-id="75d80-162">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="75d80-163">选择要将用户移动到的产品，然后选择"**移动用户"。**</span><span class="sxs-lookup"><span data-stu-id="75d80-163">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="75d80-164">在"**将用户移动到"** 框中，选择"**移动用户"。**</span><span class="sxs-lookup"><span data-stu-id="75d80-164">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="75d80-165">移动过程可能需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="75d80-165">The move process might take several minutes.</span></span> <span data-ttu-id="75d80-166">不要在进程运行时关闭浏览器。</span><span class="sxs-lookup"><span data-stu-id="75d80-166">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="75d80-167">移动过程完成后，关闭" **移动已完成"窗格**。</span><span class="sxs-lookup"><span data-stu-id="75d80-167">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="75d80-168">在订阅详细信息页面上，自助 **购买的** 订阅的订阅状态将显示为 **已删除**。</span><span class="sxs-lookup"><span data-stu-id="75d80-168">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="75d80-169">取消自助购买订阅</span><span class="sxs-lookup"><span data-stu-id="75d80-169">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="75d80-170">当你选择取消自助购买订阅时，具有许可证的用户将失去对该产品的访问权限。</span><span class="sxs-lookup"><span data-stu-id="75d80-170">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="75d80-171">最初购买自助服务购买订阅的用户将收到一封电子邮件，指出订阅已取消。</span><span class="sxs-lookup"><span data-stu-id="75d80-171">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="75d80-172">在管理中心中，转到“**计费**”>“<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-172">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="75d80-173">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>中，转到" **帐单** > **""产品"** 页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-173">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="75d80-174">在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，转到" **帐单** > **""产品"** 页面。</span><span class="sxs-lookup"><span data-stu-id="75d80-174">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="75d80-175">在"**产品**"选项卡上，选择筛选器图标，然后选择"**自助服务"。**</span><span class="sxs-lookup"><span data-stu-id="75d80-175">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="75d80-176">选择想要取消的订阅。</span><span class="sxs-lookup"><span data-stu-id="75d80-176">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="75d80-177">On the subscription details page， in the **Subscriptions and settings** section， select **Take control of this subscription**.</span><span class="sxs-lookup"><span data-stu-id="75d80-177">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="75d80-178">在右侧窗格中，选择"取消 **订阅"。**</span><span class="sxs-lookup"><span data-stu-id="75d80-178">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="75d80-179">从下拉列表中选择取消原因，然后选择取消 **订阅**。</span><span class="sxs-lookup"><span data-stu-id="75d80-179">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="75d80-180">在 **"确定要取消吗？"框中**，选择"取消 **订阅"。**</span><span class="sxs-lookup"><span data-stu-id="75d80-180">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="75d80-181">关闭右窗格。</span><span class="sxs-lookup"><span data-stu-id="75d80-181">Close the right pane.</span></span>
9. <span data-ttu-id="75d80-182">在订阅详细信息页面上， **订阅状态** 将显示为 **已删除**。</span><span class="sxs-lookup"><span data-stu-id="75d80-182">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="75d80-183">需要帮助?</span><span class="sxs-lookup"><span data-stu-id="75d80-183">Need help?</span></span> <span data-ttu-id="75d80-184">请联系我们。</span><span class="sxs-lookup"><span data-stu-id="75d80-184">Contact us.</span></span>

<span data-ttu-id="75d80-185">有关自助服务购买的常见问题，请参阅 [自助服务购买常见问题](self-service-purchase-faq.yml)解答。</span><span class="sxs-lookup"><span data-stu-id="75d80-185">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.yml).</span></span>

<span data-ttu-id="75d80-186">如果你有问题或需要自助服务购买帮助， [请联系支持](../../business-video/get-help-support.md)人员。</span><span class="sxs-lookup"><span data-stu-id="75d80-186">If you have questions or need help with self-service purchases, [contact support](../../business-video/get-help-support.md).</span></span>
