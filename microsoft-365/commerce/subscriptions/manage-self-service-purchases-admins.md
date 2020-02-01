---
title: 管理自助服务购买（管理员）
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
- commerce
search.appverid:
- MET150
description: 管理员可以了解如何管理组织中的用户所做的自我服务购买。
ms.openlocfilehash: 5db942b42f398e8951da43add7013569af52c53f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594106"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="df01f-103">管理自助服务购买（管理员）</span><span class="sxs-lookup"><span data-stu-id="df01f-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="df01f-104">作为管理员，你可以查看组织中的人员进行的自助购买。</span><span class="sxs-lookup"><span data-stu-id="df01f-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="df01f-105">您可以查看产品、购买者名称、购买订阅、到期日期、购买价格和分配给每种自助服务购买的用户。</span><span class="sxs-lookup"><span data-stu-id="df01f-105">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="df01f-106">如果你的组织需要，你可以通过 PowerShell 基于每个产品禁用自助购买。</span><span class="sxs-lookup"><span data-stu-id="df01f-106">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="df01f-107">你的数据管理和访问策略与通过自助服务购买或集中购买的产品相同。</span><span class="sxs-lookup"><span data-stu-id="df01f-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="df01f-108">您还可以控制组织中的用户是否可以进行自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="df01f-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="df01f-109">有关详细信息，请参阅[Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="df01f-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="df01f-110">查看自助服务订阅</span><span class="sxs-lookup"><span data-stu-id="df01f-110">View self-service subscriptions</span></span>

1. <span data-ttu-id="df01f-111">在 "管理中心" 中，转到 "**帐单** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">产品 & 服务</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="df01f-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="df01f-112">在 "**优化结果**" 下，从 "**帐户类型**" 下拉选择 "**自助服务**"。</span><span class="sxs-lookup"><span data-stu-id="df01f-112">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="df01f-113">若要查看订阅的更多详细信息，请从列表中选择一个订阅。</span><span class="sxs-lookup"><span data-stu-id="df01f-113">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="df01f-114">查看拥有自助服务购买订阅许可证的所有者</span><span class="sxs-lookup"><span data-stu-id="df01f-114">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="df01f-115">在管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="df01f-115">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="df01f-116">选择 "筛选器" 图标，然后选择 "**自助服务**"。</span><span class="sxs-lookup"><span data-stu-id="df01f-116">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="df01f-117">选择一个产品以查看分配给人员的许可证。</span><span class="sxs-lookup"><span data-stu-id="df01f-117">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df01f-118">如果有多个产品购买，则该产品仅列出一次，"**可用数量**" 列显示为该产品购买的所有订阅的总数。</span><span class="sxs-lookup"><span data-stu-id="df01f-118">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="df01f-119">"**用户**" 列表按进行自助服务购买的人员的姓名进行分组。</span><span class="sxs-lookup"><span data-stu-id="df01f-119">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="df01f-120">若要导出具有这些订阅的许可证的用户列表，请选择要导出的订阅，然后选择 "**导出用户**"。</span><span class="sxs-lookup"><span data-stu-id="df01f-120">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="df01f-121">禁用或启用自助购买</span><span class="sxs-lookup"><span data-stu-id="df01f-121">Disable or enable self-service purchases</span></span>

<span data-ttu-id="df01f-122">您可以为组织中的用户禁用或启用自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="df01f-122">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="df01f-123">**MSCommerce** PowerShell 模块包含**AllowSelfServicePurchase**的**PolicyID**参数值，可让你控制组织中的用户是否可以进行自助购买，以及为哪些产品提供服务。</span><span class="sxs-lookup"><span data-stu-id="df01f-123">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="df01f-124">您可以使用**MSCommerce** PowerShell 模块执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="df01f-124">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="df01f-125">查看**AllowSelfServicePurchase**参数值&mdash;的默认状态，无论它是由产品启用还是禁用</span><span class="sxs-lookup"><span data-stu-id="df01f-125">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="df01f-126">查看适用产品的列表以及是否启用或禁用自助式购买</span><span class="sxs-lookup"><span data-stu-id="df01f-126">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="df01f-127">查看或修改特定产品的当前设置以启用或禁用该产品</span><span class="sxs-lookup"><span data-stu-id="df01f-127">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="df01f-128">有关详细信息，请参阅[Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="df01f-128">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="df01f-129">在单个订阅下集中使用许可证</span><span class="sxs-lookup"><span data-stu-id="df01f-129">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="df01f-130">您可以分配现有许可证，或通过现有协议为分配到自助购买的用户购买其他订阅。</span><span class="sxs-lookup"><span data-stu-id="df01f-130">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="df01f-131">在分配了这些集中购买的许可证之后，可以请求该购买者取消其现有订阅。</span><span class="sxs-lookup"><span data-stu-id="df01f-131">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="df01f-132">使用全局管理员或帐单管理员帐户登录到<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="df01f-132">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="df01f-133">转到 "**付费** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">购买服务</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="df01f-133">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="df01f-134">查找并选择要购买的产品，然后选择 "**购买**"。</span><span class="sxs-lookup"><span data-stu-id="df01f-134">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="df01f-135">完成其余步骤以完成购买。</span><span class="sxs-lookup"><span data-stu-id="df01f-135">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="df01f-136">按照查看在第6步中要引用的用户列表中[查看拥有自助购买订阅的许可证](#view-who-has-licenses-for-a-self-service-purchase-subscription)的步骤中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="df01f-136">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="df01f-137">将许可证分配给在其他订阅中具有许可证的每个人。</span><span class="sxs-lookup"><span data-stu-id="df01f-137">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="df01f-138">有关完整步骤，请参阅向[用户分配许可证](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="df01f-138">For full steps, see [Assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>

7. <span data-ttu-id="df01f-139">请与购买自助服务购买订阅的人员联系，让他们取消该订阅。</span><span class="sxs-lookup"><span data-stu-id="df01f-139">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="df01f-140">需要帮助?</span><span class="sxs-lookup"><span data-stu-id="df01f-140">Need help?</span></span> <span data-ttu-id="df01f-141">联系我们。</span><span class="sxs-lookup"><span data-stu-id="df01f-141">Contact us.</span></span>

<span data-ttu-id="df01f-142">有关自助购买的常见问题，请参阅[自助服务购买 FAQ](self-service-purchase-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="df01f-142">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="df01f-143">如果你有任何疑问或需要有关自助购买的帮助，请[联系支持人员](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="df01f-143">If you have questions or need help with self-service purchases, [contact support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>