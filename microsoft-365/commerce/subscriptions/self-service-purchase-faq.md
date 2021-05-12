---
title: 自助服务购买常见问题解答
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
ms.collection: M365-subscription-management
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
- commerce_ssp
search.appverid:
- MET150
description: 查找有关自助服务购买的常见问题的解答。
ms.date: 09/15/2020
ms.openlocfilehash: 964eca8e94f64fd2f212745abfff0cf25d45bfca
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333190"
---
# <a name="self-service-purchase-faq"></a><span data-ttu-id="ab20f-103">自助服务购买常见问题解答</span><span class="sxs-lookup"><span data-stu-id="ab20f-103">Self-service purchase FAQ</span></span>

<span data-ttu-id="ab20f-104">自助购买为用户提供了尝试新技术和开发最终使大型组织受益的解决方案的机会。</span><span class="sxs-lookup"><span data-stu-id="ab20f-104">Self-service purchase gives users a chance to try out new technologies and develop solutions that ultimately benefit their larger organizations.</span></span> <span data-ttu-id="ab20f-105">中央采购和 IT 团队对通过管理中心购买和部署自助服务购买解决方案的Microsoft 365<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">可见性</a>。</span><span class="sxs-lookup"><span data-stu-id="ab20f-105">Central procurement and IT teams have visibility to all users who buy and deploy self-service purchase solutions through the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="ab20f-106">管理员可以通过 PowerShell 按产品关闭自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="ab20f-106">Admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="ab20f-107">若要了解更多信息，请参阅 [将 AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="ab20f-107">To learn more, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

<span data-ttu-id="ab20f-108">自助服务购买适用于 Power Platform (Power BI、Power Apps 和 Power Automate) 、Project 和 Visio。</span><span class="sxs-lookup"><span data-stu-id="ab20f-108">Self-service purchase is available for Power Platform (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span>

> [!NOTE]
> <span data-ttu-id="ab20f-109">自助购买不适用于印度或政府或教育客户。</span><span class="sxs-lookup"><span data-stu-id="ab20f-109">Self-service purchase isn’t available in India or for government or education customers.</span></span> <span data-ttu-id="ab20f-110">Project Visio和卢旺达共和国提供自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="ab20f-110">Project and Visio are not available for self-service purchase in Brazil and the Democratic Republic of Congo.</span></span>

## <a name="making-a-self-service-purchase"></a><span data-ttu-id="ab20f-111">进行自助服务购买</span><span class="sxs-lookup"><span data-stu-id="ab20f-111">Making a self-service purchase</span></span>

### <a name="how-does-a-customer-make-a-self-service-purchase"></a><span data-ttu-id="ab20f-112">客户如何进行自助购买？</span><span class="sxs-lookup"><span data-stu-id="ab20f-112">How does a customer make a self-service purchase?</span></span>

<span data-ttu-id="ab20f-113">客户可以从产品网站或应用内购买提示在线进行自助购买。</span><span class="sxs-lookup"><span data-stu-id="ab20f-113">Customers can make a self-service purchase online from the product websites or from in-app purchase prompts.</span></span> <span data-ttu-id="ab20f-114">首先要求客户输入电子邮件地址，以确保他们是现有 AD 租户Azure Active Directory (用户) 用户。</span><span class="sxs-lookup"><span data-stu-id="ab20f-114">Customers are first asked to enter an email address to ensure that they're a user in an existing Azure Active Directory (AD) tenant.</span></span> <span data-ttu-id="ab20f-115">接下来，他们被定向到使用其 Azure AD 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="ab20f-115">Next, they're directed to sign in by using their Azure AD credentials.</span></span> <span data-ttu-id="ab20f-116">登录后，要求客户选择要购买的订阅数并提供信用卡付款。</span><span class="sxs-lookup"><span data-stu-id="ab20f-116">After signing in, the customer is asked to select how many subscriptions they want to buy, and to provide credit card payment.</span></span> <span data-ttu-id="ab20f-117">购买完成后，他们可以开始使用其订阅。</span><span class="sxs-lookup"><span data-stu-id="ab20f-117">When the purchase is complete, they can start using their subscription.</span></span> <span data-ttu-id="ab20f-118">购买者有权访问管理中心的有限视图Microsoft 365，他们可以在这里<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a>将产品许可证分配给其组织的其他人员。</span><span class="sxs-lookup"><span data-stu-id="ab20f-118">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> where they can assign licenses to the product to other people in their organization.</span></span>

### <a name="what-are-the-payment-options-for-self-service-purchases"></a><span data-ttu-id="ab20f-119">自助服务购买的付款选项是什么？</span><span class="sxs-lookup"><span data-stu-id="ab20f-119">What are the payment options for self-service purchases?</span></span>

<span data-ttu-id="ab20f-120">目前，信用卡是唯一可用的付款方式。</span><span class="sxs-lookup"><span data-stu-id="ab20f-120">Currently, credit card is the only available payment method.</span></span> <span data-ttu-id="ab20f-121">不支持通过发票付款。</span><span class="sxs-lookup"><span data-stu-id="ab20f-121">Payment through invoicing isn't supported.</span></span>

### <a name="who-can-buy-through-self-service-purchase"></a><span data-ttu-id="ab20f-122">Who自助服务购买购买？</span><span class="sxs-lookup"><span data-stu-id="ab20f-122">Who can buy through self-service purchase?</span></span>

<span data-ttu-id="ab20f-123">在托管 Azure AD 租户中拥有非来宾用户帐户的任何用户都可以进行自助购买。</span><span class="sxs-lookup"><span data-stu-id="ab20f-123">Any user with a non-guest user account in a managed Azure AD tenant can make a self-service purchase.</span></span> <span data-ttu-id="ab20f-124">自助服务购买不适用于政府或教育组织的租户。</span><span class="sxs-lookup"><span data-stu-id="ab20f-124">Self-service purchasing isn’t available to tenants that are government or education organizations.</span></span> <span data-ttu-id="ab20f-125">如果此操作适用于你的组织，则无需执行任何其他操作来控制自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="ab20f-125">If this applies to your organization, then no additional action is required to control self-service purchase.</span></span>

<span data-ttu-id="ab20f-126">组织或市场中的不符合自助服务购买条件的用户会看到一条消息，要求他们联系 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="ab20f-126">Users in organizations or markets who aren’t eligible for self-service purchase see a message asking them to contact their IT admin.</span></span>

### <a name="can-guest-users-buy-through-self-service-purchase"></a><span data-ttu-id="ab20f-127">来宾用户能否通过自助购买购买？</span><span class="sxs-lookup"><span data-stu-id="ab20f-127">Can guest users buy through self-service purchase?</span></span>

<span data-ttu-id="ab20f-128">否，来宾用户无法完成作为来宾的租户中的自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="ab20f-128">No, guest users can’t complete a self-service purchase in a tenant in which they're a guest.</span></span>

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a><span data-ttu-id="ab20f-129">用户能否通过自助购买从本地 Active Directory 进行同步购买？</span><span class="sxs-lookup"><span data-stu-id="ab20f-129">Can users synced from an on-premises Active Directory buy through self-service purchase?</span></span>

<span data-ttu-id="ab20f-130">如果用户在符合条件的 Azure AD 租户中具有活动用户帐户，则他们可以完成自助购买。</span><span class="sxs-lookup"><span data-stu-id="ab20f-130">If a user has an active user account in an eligible Azure AD tenant, they can complete a self-service purchase.</span></span>

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a><span data-ttu-id="ab20f-131">Who自助服务购买者能否将许可证分配给他们？</span><span class="sxs-lookup"><span data-stu-id="ab20f-131">Who can self-service purchasers assign licenses to?</span></span>

<span data-ttu-id="ab20f-132">自助服务购买者只能向同一 Azure AD 租户中的用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="ab20f-132">Self-service purchasers can only assign licenses to users in the same Azure AD tenant.</span></span> <span data-ttu-id="ab20f-133">购买者有权访问管理中心的有限视图Microsoft 365<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">分配</a>许可证。</span><span class="sxs-lookup"><span data-stu-id="ab20f-133">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> to assign licenses.</span></span> <span data-ttu-id="ab20f-134">购买者可以将许可证分配给通过自助购买购买的产品，并且只能向同一 Azure AD 租户中的用户分配这些许可证。</span><span class="sxs-lookup"><span data-stu-id="ab20f-134">Purchasers can assign licenses to those products that they've bought through self-service purchase, and can only assign those licenses to users in the same Azure AD tenant.</span></span>

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a><span data-ttu-id="ab20f-135">自助服务购买者在哪里查看和管理他们的购买？</span><span class="sxs-lookup"><span data-stu-id="ab20f-135">Where does the self-service purchaser see and manage their purchases?</span></span>

<span data-ttu-id="ab20f-136">自助服务购买者可以在管理中心的有限视图中管理Microsoft 365<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">购买</a>。</span><span class="sxs-lookup"><span data-stu-id="ab20f-136">Self-service purchasers can manage their purchases in the limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="ab20f-137">购买者始终可以从内置到所有应用和 Dynamics  online 应用中的应用启动器中的"管理"磁贴Microsoft 365管理中心。</span><span class="sxs-lookup"><span data-stu-id="ab20f-137">Purchasers can always get to the admin center from the **Admin** tile in the app launcher built into all Microsoft 365 and Dynamics online apps.</span></span> <span data-ttu-id="ab20f-138">购买者可以查看他们进行购买、购买相同服务的其他订阅，并将这些订阅的许可证分配给其组织中其他用户。</span><span class="sxs-lookup"><span data-stu-id="ab20f-138">Purchasers can view the purchases they've made, buy additional subscriptions to the same service, and assign licenses for those subscriptions to other users in their organization.</span></span> <span data-ttu-id="ab20f-139">此外，购买者可以查看和支付帐单、更新付款方式以及取消订阅。</span><span class="sxs-lookup"><span data-stu-id="ab20f-139">Additionally, purchasers can view and pay their bill, update their payment method, and cancel their subscription.</span></span>

## <a name="pricing"></a><span data-ttu-id="ab20f-140">定价</span><span class="sxs-lookup"><span data-stu-id="ab20f-140">Pricing</span></span>

### <a name="what-is-the-pricing-for-self-service-purchases"></a><span data-ttu-id="ab20f-141">自助服务购买的定价是什么？</span><span class="sxs-lookup"><span data-stu-id="ab20f-141">What is the pricing for self-service purchases?</span></span>

<span data-ttu-id="ab20f-142">Microsoft 网站上提供了自助服务购买的每个产品的定价。</span><span class="sxs-lookup"><span data-stu-id="ab20f-142">Pricing for each of the products for self-service purchase is available on the Microsoft website.</span></span> <span data-ttu-id="ab20f-143">当用户进行自助购买时，价格还会显示为结帐体验的一部分。</span><span class="sxs-lookup"><span data-stu-id="ab20f-143">Prices are also displayed as part of the checkout experience when users make a self-service purchase.</span></span> <span data-ttu-id="ab20f-144">这些价格可能与组织进行集中购买时所支付的价格或合作伙伴提供的价格不同。</span><span class="sxs-lookup"><span data-stu-id="ab20f-144">These prices may differ from the prices an organization pays when making central purchases or prices offered through a partner.</span></span>

### <a name="who-is-responsible-for-payment"></a><span data-ttu-id="ab20f-145">Who负责付款？</span><span class="sxs-lookup"><span data-stu-id="ab20f-145">Who is responsible for payment?</span></span>

<span data-ttu-id="ab20f-146">通过自助购买购买订阅的人是计费人员，负责根据购买的条款和定价付款。</span><span class="sxs-lookup"><span data-stu-id="ab20f-146">The person who buys the subscription through self-service purchase is the person who is billed and who is responsible for payment based on the terms and pricing of the purchase.</span></span>

## <a name="admin-capabilities"></a><span data-ttu-id="ab20f-147">管理功能</span><span class="sxs-lookup"><span data-stu-id="ab20f-147">Admin capabilities</span></span>

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a><span data-ttu-id="ab20f-148">管理员具有哪些自助服务购买功能？</span><span class="sxs-lookup"><span data-stu-id="ab20f-148">What capabilities does an admin have for self-service purchases?</span></span>

<span data-ttu-id="ab20f-149">管理员可以在管理中心 查看其组织Microsoft 365<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">购买</a>。</span><span class="sxs-lookup"><span data-stu-id="ab20f-149">Admins can view all self-service purchases made in their organization in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="ab20f-150">他们可以看到产品、购买者名称、购买的订阅、到期日期、订单历史记录、购买价格以及每个自助购买的已分配用户。</span><span class="sxs-lookup"><span data-stu-id="ab20f-150">They can see the product, purchaser name, subscriptions purchased, expiry date, order history, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="ab20f-151">在 Power Platform Admin Center 中，管理员还可以查看自助服务购买容量。</span><span class="sxs-lookup"><span data-stu-id="ab20f-151">In the Power Platform Admin Center, admins can also view self-service purchases capacity.</span></span> <span data-ttu-id="ab20f-152">如果组织需要，管理员可以通过 PowerShell 关闭按产品进行自助购买。</span><span class="sxs-lookup"><span data-stu-id="ab20f-152">If required for their organization, admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="ab20f-153">对于通过自助购买或集中购买的产品，管理员具有相同的数据管理和访问策略。</span><span class="sxs-lookup"><span data-stu-id="ab20f-153">Admins have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="ab20f-154">管理员还可以控制其组织的用户是否可以进行自助购买。</span><span class="sxs-lookup"><span data-stu-id="ab20f-154">Admins can also control whether users in their organization can make self-service purchases.</span></span> <span data-ttu-id="ab20f-155">有关详细信息，请参阅将 [AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="ab20f-155">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a><span data-ttu-id="ab20f-156">Microsoft 如何通过启用自助购买来尊重数据管理和合规性？</span><span class="sxs-lookup"><span data-stu-id="ab20f-156">How is Microsoft respecting data governance and compliance by enabling self-service purchase?</span></span>

<span data-ttu-id="ab20f-157">管理员根据数据管理和合规性要求维持对租户中可用服务和产品的控制。</span><span class="sxs-lookup"><span data-stu-id="ab20f-157">Admins maintain control over what services and products are available within their tenant based on their data governance and compliance requirements.</span></span> <span data-ttu-id="ab20f-158">组织启用的所有数据管理和访问策略均适用于可用的自助购买服务。</span><span class="sxs-lookup"><span data-stu-id="ab20f-158">All data management and access policies that your organization turned on apply to available self-service purchased services.</span></span>

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a><span data-ttu-id="ab20f-159">Who由自助服务购买创建的产品数据？</span><span class="sxs-lookup"><span data-stu-id="ab20f-159">Who owns the product data created from self-service purchases?</span></span>

<span data-ttu-id="ab20f-160">从通过自助购买购买的产品创建的数据归组织所有和控制。</span><span class="sxs-lookup"><span data-stu-id="ab20f-160">Data created from products bought through self-service purchase is owned and controlled by the organization.</span></span>

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a><span data-ttu-id="ab20f-161">如何集中通过自助服务购买进行购买？</span><span class="sxs-lookup"><span data-stu-id="ab20f-161">How do I centralize the purchases made through self-service purchase?</span></span>

<span data-ttu-id="ab20f-162">管理员可以分配现有许可证，或者通过分配给自助服务购买的用户的现有协议和定价购买自助服务购买产品的其他订阅。</span><span class="sxs-lookup"><span data-stu-id="ab20f-162">Admins can assign existing licenses or buy additional subscriptions of self-service purchase products through existing agreements and pricing for users assigned to self-service purchases.</span></span> <span data-ttu-id="ab20f-163">分配这些集中购买的许可证后，管理员可以请求购买者取消其现有订阅。</span><span class="sxs-lookup"><span data-stu-id="ab20f-163">After assigning these centrally purchased licenses, admins can then request that the purchasers cancel their existing subscriptions.</span></span>

### <a name="where-does-the-admin-see-self-service-purchases"></a><span data-ttu-id="ab20f-164">管理员在哪里看到自助服务购买？</span><span class="sxs-lookup"><span data-stu-id="ab20f-164">Where does the admin see self-service purchases?</span></span>

<span data-ttu-id="ab20f-165">全局管理员和帐单管理员可以在管理中心的"帐单""你的产品"Microsoft 365  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">购买订阅</a>。</span><span class="sxs-lookup"><span data-stu-id="ab20f-165">Global and billing admins can see subscriptions bought through self-service purchase in **Billing** > **Your products** in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="ab20f-166">他们可以筛选产品列表，以只显示通过中央采购购买的订阅，或包括通过自助购买购买的订阅。</span><span class="sxs-lookup"><span data-stu-id="ab20f-166">They can filter the products list to only show the subscriptions purchased through central procurement, or to include subscriptions bought through self-service purchase.</span></span>

<span data-ttu-id="ab20f-167">管理员可以查看产品、购买者名称、购买的订阅、到期日期、订单历史记录、购买价格以及分配的用户。</span><span class="sxs-lookup"><span data-stu-id="ab20f-167">Admins can see the product, purchaser name, subscription purchased, expiry date, order history, the purchase price, and assigned users.</span></span>

## <a name="support-and-training"></a><span data-ttu-id="ab20f-168">支持和培训</span><span class="sxs-lookup"><span data-stu-id="ab20f-168">Support and training</span></span>

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a><span data-ttu-id="ab20f-169">客户的 IT 部门或合作伙伴是否期望支持通过自助购买购买的产品？</span><span class="sxs-lookup"><span data-stu-id="ab20f-169">Are customers' IT departments or partners expected to support products bought through self-service purchase?</span></span>

<span data-ttu-id="ab20f-170">IT 部门和合作伙伴不能为通过自助购买购买的产品提供支持。</span><span class="sxs-lookup"><span data-stu-id="ab20f-170">IT departments and partners aren't expected to provide support for products bought through self-service purchase.</span></span> <span data-ttu-id="ab20f-171">Microsoft 为自助服务购买者提供标准支持。</span><span class="sxs-lookup"><span data-stu-id="ab20f-171">Microsoft provides standard support for self-service purchasers.</span></span>

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a><span data-ttu-id="ab20f-172">如果自助服务购买者呼叫支持人员，这是否使用了客户的顶级支持事件？</span><span class="sxs-lookup"><span data-stu-id="ab20f-172">If a self-service purchaser calls support, does that use the customer's Premier Support incidents?</span></span>

<span data-ttu-id="ab20f-173">自助服务购买者不会使用客户的顶级支持事件接收对自助购买的支持。</span><span class="sxs-lookup"><span data-stu-id="ab20f-173">Self-service purchasers won't use a customer's Premier Support incidents for receiving support for their self-service purchases.</span></span>

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a><span data-ttu-id="ab20f-174">用户期望如何接收有关通过自助购买购买的产品的培训？</span><span class="sxs-lookup"><span data-stu-id="ab20f-174">How are users expected to receive training on the products they buy through self-service purchase?</span></span>

<span data-ttu-id="ab20f-175">产品网站上提供了针对用户的广泛培训。</span><span class="sxs-lookup"><span data-stu-id="ab20f-175">Extensive training for users is provided on the product websites.</span></span> <span data-ttu-id="ab20f-176">产品指导学习、文档、示例和强社区直接从其他用户获取答案和提示。</span><span class="sxs-lookup"><span data-stu-id="ab20f-176">The products have guided learning, documentation, samples, and strong communities to get answers and tips directly from other users.</span></span>

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a><span data-ttu-id="ab20f-177">如果用户离开组织，那么自助服务购买会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="ab20f-177">What happens to a self-service purchase if a user leaves the organization?</span></span>

<span data-ttu-id="ab20f-178">如果最初购买自助购买产品的人离开组织，有效的用户在订阅期间将继续充分利用该产品。</span><span class="sxs-lookup"><span data-stu-id="ab20f-178">If the person who originally bought the self-service purchase product leaves the organization, valid users continue to have full use of the product for the duration of the subscription.</span></span> <span data-ttu-id="ab20f-179">订阅保持活动状态，直到购买者直接取消订阅或管理员通过客户支持请求取消订阅。</span><span class="sxs-lookup"><span data-stu-id="ab20f-179">The subscription remains active until the purchaser directly cancels it or an admin requests cancellation of the subscription through customer support.</span></span> <span data-ttu-id="ab20f-180">管理员还可以选择将集中购买的许可证分配给已取消订阅的用户。</span><span class="sxs-lookup"><span data-stu-id="ab20f-180">Admins may also choose to assign a centrally purchased license to users of the canceled subscription.</span></span>

## <a name="partners"></a><span data-ttu-id="ab20f-181">合作伙伴</span><span class="sxs-lookup"><span data-stu-id="ab20f-181">Partners</span></span>

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a><span data-ttu-id="ab20f-182">Microsoft 的合作伙伴在自助服务购买中的角色是什么？</span><span class="sxs-lookup"><span data-stu-id="ab20f-182">What's the role of Microsoft's partners in self-service purchases?</span></span>

<span data-ttu-id="ab20f-183">具有委派管理权限的合作伙伴可以在管理中心内Microsoft 365自助服务购买，就像管理员一样<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a>。合作伙伴可以帮助支持希望集中通过自助购买购买的产品的组织。</span><span class="sxs-lookup"><span data-stu-id="ab20f-183">Partners who have delegated administration privileges can see self-service purchases in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, just like an admin. Partners can help support an organization that wants to centralize products bought through self-service purchases.</span></span> <span data-ttu-id="ab20f-184">此外，合作伙伴还可以提供解决方案来扩展自助服务购买的功能。</span><span class="sxs-lookup"><span data-stu-id="ab20f-184">Additionally, partners may offer solutions to extend the capabilities of a self-service purchase.</span></span>