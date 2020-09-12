---
title: 管理 (管理员) 的自助服务购买
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 管理员可以了解如何管理组织中的用户所做的自我服务购买。
ms.openlocfilehash: ca25bf0c3e3539196e81dcc289592028cc4dfa47
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546670"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="bb01a-103">管理自助购买（管理员）</span><span class="sxs-lookup"><span data-stu-id="bb01a-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="bb01a-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="bb01a-104">The admin center is changing.</span></span> <span data-ttu-id="bb01a-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="bb01a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="bb01a-106">作为管理员，你可以查看组织中的人员进行的自助购买。</span><span class="sxs-lookup"><span data-stu-id="bb01a-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="bb01a-107">您可以看到产品名称、买方名称、购买订阅、到期日期、购买价格和分配给每种自助服务购买的用户。</span><span class="sxs-lookup"><span data-stu-id="bb01a-107">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="bb01a-108">如果你的组织需要，你可以通过 PowerShell 基于每个产品禁用自助购买。</span><span class="sxs-lookup"><span data-stu-id="bb01a-108">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="bb01a-109">你的数据管理和访问策略与通过自助服务购买或集中购买的产品相同。</span><span class="sxs-lookup"><span data-stu-id="bb01a-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="bb01a-110">您还可以控制组织中的用户是否可以进行自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="bb01a-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="bb01a-111">有关详细信息，请参阅 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bb01a-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="bb01a-112">查看自助服务订阅</span><span class="sxs-lookup"><span data-stu-id="bb01a-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="bb01a-113">在管理中心中，转到 "**付费**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="bb01a-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="bb01a-114">在 " **产品** " 选项卡上，选择 "筛选器" 图标，然后选择 " **自助服务**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="bb01a-115">若要查看订阅的更多详细信息，请从列表中选择一个订阅。</span><span class="sxs-lookup"><span data-stu-id="bb01a-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="bb01a-116">查看拥有自助服务购买订阅许可证的所有者</span><span class="sxs-lookup"><span data-stu-id="bb01a-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="bb01a-117">在管理中心，转到 "**记帐**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="bb01a-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="bb01a-118">选择 "筛选器" 图标，然后选择 " **自助服务**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-118">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="bb01a-119">选择一个产品以查看分配给人员的许可证。</span><span class="sxs-lookup"><span data-stu-id="bb01a-119">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="bb01a-120">如果有多个产品购买，则该产品仅列出一次，" **可用数量** " 列显示为该产品购买的所有订阅的总数。</span><span class="sxs-lookup"><span data-stu-id="bb01a-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="bb01a-121">" **用户** " 列表按进行自助服务购买的人员的姓名进行分组。</span><span class="sxs-lookup"><span data-stu-id="bb01a-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="bb01a-122">若要导出具有这些订阅的许可证的用户列表，请选择要导出的订阅，然后选择 " **导出用户**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="bb01a-123">禁用或启用自助购买</span><span class="sxs-lookup"><span data-stu-id="bb01a-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="bb01a-124">您可以为组织中的用户禁用或启用自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="bb01a-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="bb01a-125">**MSCommerce** PowerShell 模块包含**AllowSelfServicePurchase**的**PolicyID**参数值，可让你控制组织中的用户是否可以进行自助购买，以及为哪些产品提供服务。</span><span class="sxs-lookup"><span data-stu-id="bb01a-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="bb01a-126">您可以使用 **MSCommerce** PowerShell 模块执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bb01a-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="bb01a-127">查看 **AllowSelfServicePurchase** 参数值的默认状态—无论它是由产品启用还是禁用</span><span class="sxs-lookup"><span data-stu-id="bb01a-127">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="bb01a-128">查看适用产品的列表以及是否启用或禁用自助式购买</span><span class="sxs-lookup"><span data-stu-id="bb01a-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="bb01a-129">查看或修改特定产品的当前设置以启用或禁用该产品</span><span class="sxs-lookup"><span data-stu-id="bb01a-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="bb01a-130">有关详细信息，请参阅 [Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="bb01a-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="bb01a-131">在单个订阅下集中使用许可证</span><span class="sxs-lookup"><span data-stu-id="bb01a-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="bb01a-132">您可以分配现有许可证，或通过现有协议为分配到自助购买的用户购买其他订阅。</span><span class="sxs-lookup"><span data-stu-id="bb01a-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="bb01a-133">在分配了这些集中购买的许可证之后，可以请求该购买者取消其现有订阅。</span><span class="sxs-lookup"><span data-stu-id="bb01a-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="bb01a-134">在 "管理中心" 中，转到 " **付费** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">购买服务</a> " 页。</span><span class="sxs-lookup"><span data-stu-id="bb01a-134">In the admin center go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="bb01a-135">查找并选择要购买的产品，然后选择 " **购买**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-135">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="bb01a-136">完成其余步骤以完成购买。</span><span class="sxs-lookup"><span data-stu-id="bb01a-136">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="bb01a-137">按照 [查看具有自助服务购买订阅的许可证的视图](#view-who-has-licenses-for-a-self-service-purchase-subscription) 中的步骤，在下一步中导出要引用的用户列表。</span><span class="sxs-lookup"><span data-stu-id="bb01a-137">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="bb01a-138">将许可证分配给在其他订阅中具有许可证的每个人。</span><span class="sxs-lookup"><span data-stu-id="bb01a-138">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="bb01a-139">有关完整步骤，请参阅向 [用户分配许可证](../../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="bb01a-139">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="bb01a-140">请与购买自助服务购买订阅的人员联系，让他们 [取消该](manage-self-service-purchases-users.md#cancel-a-subscription)订阅。</span><span class="sxs-lookup"><span data-stu-id="bb01a-140">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="bb01a-141">接管自助服务购买订阅</span><span class="sxs-lookup"><span data-stu-id="bb01a-141">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="bb01a-142">您可以接管由组织中的用户所做的自助服务购买订阅。</span><span class="sxs-lookup"><span data-stu-id="bb01a-142">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="bb01a-143">接管自助服务购买订阅时，有两个选项：</span><span class="sxs-lookup"><span data-stu-id="bb01a-143">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="bb01a-144">将用户移动到其他订阅，并取消原始订阅。</span><span class="sxs-lookup"><span data-stu-id="bb01a-144">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="bb01a-145">取消自助服务购买订阅并删除已分配用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="bb01a-145">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="bb01a-146">将用户移动到其他订阅</span><span class="sxs-lookup"><span data-stu-id="bb01a-146">Move users to a different subscription</span></span>

<span data-ttu-id="bb01a-147">将用户移动到其他订阅时，将自动取消旧订阅。</span><span class="sxs-lookup"><span data-stu-id="bb01a-147">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="bb01a-148">最初购买自助服务购买订阅的用户收到一封表明订阅已取消的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bb01a-148">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="bb01a-149">您必须拥有要在将用户移动到的订阅中移动的每个用户的可用许可证。</span><span class="sxs-lookup"><span data-stu-id="bb01a-149">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

1. <span data-ttu-id="bb01a-150">在管理中心中，转到 "**付费**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="bb01a-150">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="bb01a-151">在 " **产品** " 选项卡上，选择 "筛选器" 图标，然后选择 " **自助服务**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-151">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="bb01a-152">选择要接管的订阅。</span><span class="sxs-lookup"><span data-stu-id="bb01a-152">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="bb01a-153">在 "订阅详细信息" 页上的 " **订阅和设置** " 部分中，选择 " **获取此订阅的控制**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-153">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="bb01a-154">在右侧窗格中，选择 " **移动用户**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-154">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="bb01a-155">选择要将用户移动到的产品，然后选择 " **移动用户**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-155">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="bb01a-156">在 " **将用户移动到** " 框中，选择 " **移动用户**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-156">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="bb01a-157">移动过程可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="bb01a-157">The move process might take several minutes.</span></span> <span data-ttu-id="bb01a-158">请勿在进程运行时关闭浏览器。</span><span class="sxs-lookup"><span data-stu-id="bb01a-158">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="bb01a-159">移动过程完成后，关闭 " **移动完成" 窗格**。</span><span class="sxs-lookup"><span data-stu-id="bb01a-159">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="bb01a-160">在 "订阅详细信息" 页上，"自助式购买订阅" 的 **订阅状态** 将显示为 " **已删除**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-160">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="bb01a-161">取消自助服务购买订阅</span><span class="sxs-lookup"><span data-stu-id="bb01a-161">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="bb01a-162">当您选择取消自助购买订阅时，拥有许可证的用户将失去对产品的访问权限。</span><span class="sxs-lookup"><span data-stu-id="bb01a-162">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="bb01a-163">最初购买自助服务购买订阅的用户收到一封表明订阅已取消的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bb01a-163">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

1. <span data-ttu-id="bb01a-164">在管理中心中，转到 "**付费**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="bb01a-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="bb01a-165">在 " **产品** " 选项卡上，选择 "筛选器" 图标，然后选择 " **自助服务**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-165">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="bb01a-166">选择要取消的订阅。</span><span class="sxs-lookup"><span data-stu-id="bb01a-166">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="bb01a-167">在 "订阅详细信息" 页上的 " **订阅和设置** " 部分中，选择 " **获取此订阅的控制**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-167">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="bb01a-168">在右侧窗格中，选择 " **取消订阅**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-168">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="bb01a-169">从下拉列表中选择取消的原因，然后选择 " **取消订阅**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-169">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="bb01a-170">在 " **是否确实要取消？** " 框中，选择 " **取消订阅**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-170">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="bb01a-171">关闭右窗格。</span><span class="sxs-lookup"><span data-stu-id="bb01a-171">Close the right pane.</span></span>
9. <span data-ttu-id="bb01a-172">在 "订阅详细信息" 页上， **订阅状态** 显示为 " **已删除**"。</span><span class="sxs-lookup"><span data-stu-id="bb01a-172">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="bb01a-173">需要帮助？</span><span class="sxs-lookup"><span data-stu-id="bb01a-173">Need help?</span></span> <span data-ttu-id="bb01a-174">联系我们。</span><span class="sxs-lookup"><span data-stu-id="bb01a-174">Contact us.</span></span>

<span data-ttu-id="bb01a-175">有关自助购买的常见问题，请参阅 [自助服务购买 FAQ](self-service-purchase-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="bb01a-175">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="bb01a-176">如果你有任何疑问或需要有关自助购买的帮助，请 [联系支持人员](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="bb01a-176">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>