---
title: 自助服务购买常见问题解答
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
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: 查找有关自助式购买的常见问题的解答。
ms.date: 08/12/2020
ms.openlocfilehash: 78a7082a966a866f18ac2aa378198dbb33d8c158
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653697"
---
# <a name="self-service-purchase-faq"></a><span data-ttu-id="5a888-103">自助服务购买常见问题解答</span><span class="sxs-lookup"><span data-stu-id="5a888-103">Self-service purchase FAQ</span></span>

<span data-ttu-id="5a888-104">自助服务购买为用户提供了尝试新技术的机会，并开发最终受益于其大型组织的解决方案。</span><span class="sxs-lookup"><span data-stu-id="5a888-104">Self-service purchase gives users a chance to try out new technologies and develop solutions that ultimately benefit their larger organizations.</span></span> <span data-ttu-id="5a888-105">集中采购和 IT 团队可查看通过<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>购买和部署自助服务购买解决方案的所有用户。</span><span class="sxs-lookup"><span data-stu-id="5a888-105">Central procurement and IT teams have visibility to all users who buy and deploy self-service purchase solutions through the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="5a888-106">管理员可以通过 PowerShell 以每个产品为基础关闭自助购买。</span><span class="sxs-lookup"><span data-stu-id="5a888-106">Admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="5a888-107">若要了解详细信息，请参阅[Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="5a888-107">To learn more, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

<span data-ttu-id="5a888-108">自助服务购买适用于 Power Platform (Power BI、Power Apps 和 Power) 、Project 和 Visio 的自动运行。</span><span class="sxs-lookup"><span data-stu-id="5a888-108">Self-service purchase is available for Power Platform (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span>

> [!NOTE]
> <span data-ttu-id="5a888-109">自助服务购买不适用于印度，也不适用于政府或教育客户。</span><span class="sxs-lookup"><span data-stu-id="5a888-109">Self-service purchase isn’t available in India, and isn’t available to government or education customers.</span></span>

## <a name="making-a-self-service-purchase"></a><span data-ttu-id="5a888-110">进行自助服务购买</span><span class="sxs-lookup"><span data-stu-id="5a888-110">Making a self-service purchase</span></span>

### <a name="how-does-a-customer-make-a-self-service-purchase"></a><span data-ttu-id="5a888-111">客户如何购买自助服务？</span><span class="sxs-lookup"><span data-stu-id="5a888-111">How does a customer make a self-service purchase?</span></span>

<span data-ttu-id="5a888-112">客户可以从产品网站或应用程序购买提示中进行自助在线购买。</span><span class="sxs-lookup"><span data-stu-id="5a888-112">Customers can make a self-service purchase online from the product websites or from in-app purchase prompts.</span></span> <span data-ttu-id="5a888-113">首先，客户需要输入电子邮件地址，以确保他们是现有 Azure Active Directory (AD) 租户中的用户。</span><span class="sxs-lookup"><span data-stu-id="5a888-113">Customers are first asked to enter an email address to ensure that they're a user in an existing Azure Active Directory (AD) tenant.</span></span> <span data-ttu-id="5a888-114">接下来，使用他们的 Azure AD 凭据引导他们登录。</span><span class="sxs-lookup"><span data-stu-id="5a888-114">Next, they're directed to sign in by using their Azure AD credentials.</span></span> <span data-ttu-id="5a888-115">登录后，系统会要求客户选择要购买的订阅数，并提供信用卡付款。</span><span class="sxs-lookup"><span data-stu-id="5a888-115">After signing in, the customer is asked to select how many subscriptions they want to buy, and to provide credit card payment.</span></span> <span data-ttu-id="5a888-116">购买完成后，即可开始使用其订阅。</span><span class="sxs-lookup"><span data-stu-id="5a888-116">When the purchase is complete, they can start using their subscription.</span></span> <span data-ttu-id="5a888-117">买方可以访问<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>的有限视图，在其中，他们可以向组织中的其他人员分配产品许可证。</span><span class="sxs-lookup"><span data-stu-id="5a888-117">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> where they can assign licenses to the product to other people in their organization.</span></span>

### <a name="what-are-the-payment-options-for-self-service-purchases"></a><span data-ttu-id="5a888-118">自助服务购买的付款选项是什么？</span><span class="sxs-lookup"><span data-stu-id="5a888-118">What are the payment options for self-service purchases?</span></span>

<span data-ttu-id="5a888-119">目前，信用卡是唯一可用的支付方式。</span><span class="sxs-lookup"><span data-stu-id="5a888-119">Currently, credit card is the only available payment method.</span></span> <span data-ttu-id="5a888-120">不支持通过发票付款。</span><span class="sxs-lookup"><span data-stu-id="5a888-120">Payment through invoicing isn't supported.</span></span>

### <a name="who-can-buy-through-self-service-purchase"></a><span data-ttu-id="5a888-121">谁可以通过自助购买购买？</span><span class="sxs-lookup"><span data-stu-id="5a888-121">Who can buy through self-service purchase?</span></span>

<span data-ttu-id="5a888-122">在托管 Azure AD 租户中具有非来宾用户帐户的任何用户都可以进行自我服务购买。</span><span class="sxs-lookup"><span data-stu-id="5a888-122">Any user with a non-guest user account in a managed Azure AD tenant can make a self-service purchase.</span></span> <span data-ttu-id="5a888-123">自助服务购买不适用于作为政府或教育组织的租户。</span><span class="sxs-lookup"><span data-stu-id="5a888-123">Self-service purchasing isn’t available to tenants that are government or education organizations.</span></span> <span data-ttu-id="5a888-124">如果这适用于您的组织，则无需执行任何其他操作即可控制自助购买。</span><span class="sxs-lookup"><span data-stu-id="5a888-124">If this applies to your organization, then no additional action is required to control self-service purchase.</span></span>

<span data-ttu-id="5a888-125">不符合自助购买条件的组织或市场中的用户会看到一条消息，要求他们联系其 IT 管理员。</span><span class="sxs-lookup"><span data-stu-id="5a888-125">Users in organizations or markets who aren’t eligible for self-service purchase see a message asking them to contact their IT admin.</span></span>

### <a name="can-guest-users-buy-through-self-service-purchase"></a><span data-ttu-id="5a888-126">来宾用户是否可以通过自助购买服务购买？</span><span class="sxs-lookup"><span data-stu-id="5a888-126">Can guest users buy through self-service purchase?</span></span>

<span data-ttu-id="5a888-127">否，来宾用户无法在其为来宾的租户中完成自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="5a888-127">No, guest users can’t complete a self-service purchase in a tenant in which they're a guest.</span></span>

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a><span data-ttu-id="5a888-128">是否可以通过自助购买从本地 Active Directory 购买的用户进行同步？</span><span class="sxs-lookup"><span data-stu-id="5a888-128">Can users synced from an on-premises Active Directory buy through self-service purchase?</span></span>

<span data-ttu-id="5a888-129">如果用户在符合条件的 Azure AD 租户中具有活动用户帐户，则可以完成自助购买。</span><span class="sxs-lookup"><span data-stu-id="5a888-129">If a user has an active user account in an eligible Azure AD tenant, they can complete a self-service purchase.</span></span>

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a><span data-ttu-id="5a888-130">谁可以由自助服务购买者将许可证分配给？</span><span class="sxs-lookup"><span data-stu-id="5a888-130">Who can self-service purchasers assign licenses to?</span></span>

<span data-ttu-id="5a888-131">自助式购买者只能将许可证分配给同一 Azure AD 租户中的用户。</span><span class="sxs-lookup"><span data-stu-id="5a888-131">Self-service purchasers can only assign licenses to users in the same Azure AD tenant.</span></span> <span data-ttu-id="5a888-132">买方有权访问<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>的有限视图，以分配许可证。</span><span class="sxs-lookup"><span data-stu-id="5a888-132">The purchaser has access to a limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> to assign licenses.</span></span> <span data-ttu-id="5a888-133">"购买者" 可将许可证分配给他们通过自助服务购买购买的产品，并且只能将这些许可证分配给同一 Azure AD 租户中的用户。</span><span class="sxs-lookup"><span data-stu-id="5a888-133">Purchasers can assign licenses to those products that they've bought through self-service purchase, and can only assign those licenses to users in the same Azure AD tenant.</span></span>

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a><span data-ttu-id="5a888-134">自助式买方在哪里查看和管理他们的采购？</span><span class="sxs-lookup"><span data-stu-id="5a888-134">Where does the self-service purchaser see and manage their purchases?</span></span>

<span data-ttu-id="5a888-135">自助服务购买者可以在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>的受限视图中管理其购买。</span><span class="sxs-lookup"><span data-stu-id="5a888-135">Self-service purchasers can manage their purchases in the limited view of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="5a888-136">购买者可以始终从内置于所有 Microsoft 365 和 Dynamics online 应用的应用启动器中的 "**管理员**" 磁贴进入管理中心。</span><span class="sxs-lookup"><span data-stu-id="5a888-136">Purchasers can always get to the admin center from the **Admin** tile in the app launcher built into all Microsoft 365 and Dynamics online apps.</span></span> <span data-ttu-id="5a888-137">"购买者" 可以查看他们所做的购买、购买同一服务的其他订阅，以及将这些订阅的许可证分配给组织中的其他用户。</span><span class="sxs-lookup"><span data-stu-id="5a888-137">Purchasers can view the purchases they've made, buy additional subscriptions to the same service, and assign licenses for those subscriptions to other users in their organization.</span></span> <span data-ttu-id="5a888-138">此外，购买者可以查看和支付自己的帐单、更新其付款方式，并取消其订阅。</span><span class="sxs-lookup"><span data-stu-id="5a888-138">Additionally, purchasers can view and pay their bill, update their payment method, and cancel their subscription.</span></span>

## <a name="pricing"></a><span data-ttu-id="5a888-139">定价</span><span class="sxs-lookup"><span data-stu-id="5a888-139">Pricing</span></span>

### <a name="what-is-the-pricing-for-self-service-purchases"></a><span data-ttu-id="5a888-140">自助购买的定价是什么？</span><span class="sxs-lookup"><span data-stu-id="5a888-140">What is the pricing for self-service purchases?</span></span>

<span data-ttu-id="5a888-141">在 Microsoft 网站上提供了每个用于自助购买的产品的定价。</span><span class="sxs-lookup"><span data-stu-id="5a888-141">Pricing for each of the products for self-service purchase is available on the Microsoft website.</span></span> <span data-ttu-id="5a888-142">在用户进行自助购买时，价格也显示为结帐体验的一部分。</span><span class="sxs-lookup"><span data-stu-id="5a888-142">Prices are also displayed as part of the checkout experience when users make a self-service purchase.</span></span> <span data-ttu-id="5a888-143">这些价格可能与组织在通过合作伙伴提供的集中购买或价格时支付的价格不同。</span><span class="sxs-lookup"><span data-stu-id="5a888-143">These prices may differ from the prices an organization pays when making central purchases or prices offered through a partner.</span></span>

### <a name="who-is-responsible-for-payment"></a><span data-ttu-id="5a888-144">谁负责付款？</span><span class="sxs-lookup"><span data-stu-id="5a888-144">Who is responsible for payment?</span></span>

<span data-ttu-id="5a888-145">通过 "自助式购买" 购买订阅的人员是根据购买条款和定价向其收取费用的人员，以及负责付款的人员。</span><span class="sxs-lookup"><span data-stu-id="5a888-145">The person who buys the subscription through self-service purchase is the person who is billed and who is responsible for payment based on the terms and pricing of the purchase.</span></span>

## <a name="admin-capabilities"></a><span data-ttu-id="5a888-146">管理员功能</span><span class="sxs-lookup"><span data-stu-id="5a888-146">Admin capabilities</span></span>

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a><span data-ttu-id="5a888-147">管理员对自助购买有哪些功能？</span><span class="sxs-lookup"><span data-stu-id="5a888-147">What capabilities does an admin have for self-service purchases?</span></span>

<span data-ttu-id="5a888-148">管理员可以在其组织中查看在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>内进行的所有自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="5a888-148">Admins can view all self-service purchases made in their organization in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="5a888-149">他们可以查看每个自助购买的产品、购买者名称、购买订阅、到期日期、订单历史记录、购买价格和分配的用户。</span><span class="sxs-lookup"><span data-stu-id="5a888-149">They can see the product, purchaser name, subscriptions purchased, expiry date, order history, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="5a888-150">在 Power Platform 管理中心中，管理员还可以查看自助服务购买容量。</span><span class="sxs-lookup"><span data-stu-id="5a888-150">In the Power Platform Admin Center, admins can also view self-service purchases capacity.</span></span> <span data-ttu-id="5a888-151">如果组织需要，管理员可以通过 PowerShell 以每个产品为基础关闭自助购买。</span><span class="sxs-lookup"><span data-stu-id="5a888-151">If required for their organization, admins can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="5a888-152">管理员对通过自助购买或集中购买的产品具有相同的数据管理和访问策略。</span><span class="sxs-lookup"><span data-stu-id="5a888-152">Admins have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="5a888-153">管理员还可以控制组织中的用户是否可以进行自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="5a888-153">Admins can also control whether users in their organization can make self-service purchases.</span></span> <span data-ttu-id="5a888-154">有关详细信息，请参阅[Use AllowSelfServicePurchase for The MSCommerce PowerShell module](allowselfservicepurchase-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="5a888-154">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a><span data-ttu-id="5a888-155">Microsoft 如何通过启用自助购买来尊重数据治理和合规性？</span><span class="sxs-lookup"><span data-stu-id="5a888-155">How is Microsoft respecting data governance and compliance by enabling self-service purchase?</span></span>

<span data-ttu-id="5a888-156">管理员可以根据其数据治理和合规性要求，控制其租户中提供的服务和产品。</span><span class="sxs-lookup"><span data-stu-id="5a888-156">Admins maintain control over what services and products are available within their tenant based on their data governance and compliance requirements.</span></span> <span data-ttu-id="5a888-157">您的组织打开的所有数据管理和访问策略都适用于可用的自助式购买服务。</span><span class="sxs-lookup"><span data-stu-id="5a888-157">All data management and access policies that your organization turned on apply to available self-service purchased services.</span></span>

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a><span data-ttu-id="5a888-158">谁负责从自助购买创建的产品数据？</span><span class="sxs-lookup"><span data-stu-id="5a888-158">Who owns the product data created from self-service purchases?</span></span>

<span data-ttu-id="5a888-159">从通过自助购买购买的产品中创建的数据由组织拥有和控制。</span><span class="sxs-lookup"><span data-stu-id="5a888-159">Data created from products bought through self-service purchase is owned and controlled by the organization.</span></span>

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a><span data-ttu-id="5a888-160">如何通过 "自助式购买" 集中进行购买？</span><span class="sxs-lookup"><span data-stu-id="5a888-160">How do I centralize the purchases made through self-service purchase?</span></span>

<span data-ttu-id="5a888-161">管理员可以通过现有协议和定价为分配到自助购买的用户的现有协议和定价，分配现有许可证或购买其他自助服务购买产品订阅。</span><span class="sxs-lookup"><span data-stu-id="5a888-161">Admins can assign existing licenses or buy additional subscriptions of self-service purchase products through existing agreements and pricing for users assigned to self-service purchases.</span></span> <span data-ttu-id="5a888-162">在分配这些集中购买的许可证之后，管理员可以请求购买者取消其现有订阅。</span><span class="sxs-lookup"><span data-stu-id="5a888-162">After assigning these centrally purchased licenses, admins can then request that the purchasers cancel their existing subscriptions.</span></span>

### <a name="where-does-the-admin-see-self-service-purchases"></a><span data-ttu-id="5a888-163">管理员在哪里查看自我服务购买？</span><span class="sxs-lookup"><span data-stu-id="5a888-163">Where does the admin see self-service purchases?</span></span>

<span data-ttu-id="5a888-164">全局管理员和计费管理员可以通过在**Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>的**产品**中付费购买的产品查看购买的订阅。</span><span class="sxs-lookup"><span data-stu-id="5a888-164">Global and billing admins can see subscriptions bought through self-service purchase in **Billing** > **Your products** in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.</span></span> <span data-ttu-id="5a888-165">他们可以筛选 "产品" 列表，以仅显示通过中央采购购买的订阅，或包括通过自助购买购买的订阅。</span><span class="sxs-lookup"><span data-stu-id="5a888-165">They can filter the products list to only show the subscriptions purchased through central procurement, or to include subscriptions bought through self-service purchase.</span></span>

<span data-ttu-id="5a888-166">管理员可以查看产品、买方名称、购买订阅、到期日期、订单历史记录、采购价和分配的用户。</span><span class="sxs-lookup"><span data-stu-id="5a888-166">Admins can see the product, purchaser name, subscription purchased, expiry date, order history, the purchase price, and assigned users.</span></span>

## <a name="support-and-training"></a><span data-ttu-id="5a888-167">支持和培训</span><span class="sxs-lookup"><span data-stu-id="5a888-167">Support and training</span></span>

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a><span data-ttu-id="5a888-168">客户的 IT 部门或合作伙伴是否希望支持通过自助购买购买的产品？</span><span class="sxs-lookup"><span data-stu-id="5a888-168">Are customers' IT departments or partners expected to support products bought through self-service purchase?</span></span>

<span data-ttu-id="5a888-169">IT 部门和合作伙伴不希望为通过自助购买购买的产品提供支持。</span><span class="sxs-lookup"><span data-stu-id="5a888-169">IT departments and partners aren't expected to provide support for products bought through self-service purchase.</span></span> <span data-ttu-id="5a888-170">Microsoft 为自助服务购买者提供标准支持。</span><span class="sxs-lookup"><span data-stu-id="5a888-170">Microsoft provides standard support for self-service purchasers.</span></span>

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a><span data-ttu-id="5a888-171">如果自助服务购买者呼叫支持，是否会使用客户的首要支持事件？</span><span class="sxs-lookup"><span data-stu-id="5a888-171">If a self-service purchaser calls support, does that use the customer's Premier Support incidents?</span></span>

<span data-ttu-id="5a888-172">自助服务购买者不会使用客户的首要支持事件接收自助服务购买支持。</span><span class="sxs-lookup"><span data-stu-id="5a888-172">Self-service purchasers won't use a customer's Premier Support incidents for receiving support for their self-service purchases.</span></span>

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a><span data-ttu-id="5a888-173">用户期望如何在通过自助购买的产品上接收有关他们购买的产品的培训？</span><span class="sxs-lookup"><span data-stu-id="5a888-173">How are users expected to receive training on the products they buy through self-service purchase?</span></span>

<span data-ttu-id="5a888-174">产品网站上提供了针对用户的广泛培训。</span><span class="sxs-lookup"><span data-stu-id="5a888-174">Extensive training for users is provided on the product websites.</span></span> <span data-ttu-id="5a888-175">这些产品具有指导性的学习、文档、示例和强大的社区，可直接从其他用户获取答案和提示。</span><span class="sxs-lookup"><span data-stu-id="5a888-175">The products have guided learning, documentation, samples, and strong communities to get answers and tips directly from other users.</span></span>

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a><span data-ttu-id="5a888-176">如果用户离开组织，自我服务购买会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="5a888-176">What happens to a self-service purchase if a user leaves the organization?</span></span>

<span data-ttu-id="5a888-177">如果最初购买自助服务购买产品的人离开了组织，有效用户将继续在订阅期间完全使用产品。</span><span class="sxs-lookup"><span data-stu-id="5a888-177">If the person who originally bought the self-service purchase product leaves the organization, valid users continue to have full use of the product for the duration of the subscription.</span></span> <span data-ttu-id="5a888-178">在买方直接取消该订阅或通过客户支持取消订阅的管理员请求之前，订阅将一直保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="5a888-178">The subscription remains active until the purchaser directly cancels it or an admin requests cancellation of the subscription through customer support.</span></span> <span data-ttu-id="5a888-179">管理员还可以选择将已集中购买的许可证分配给已取消订阅的用户。</span><span class="sxs-lookup"><span data-stu-id="5a888-179">Admins may also choose to assign a centrally purchased license to users of the canceled subscription.</span></span>

## <a name="partners"></a><span data-ttu-id="5a888-180">合作伙伴</span><span class="sxs-lookup"><span data-stu-id="5a888-180">Partners</span></span>

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a><span data-ttu-id="5a888-181">在自助服务购买中，Microsoft 合作伙伴的角色是什么？</span><span class="sxs-lookup"><span data-stu-id="5a888-181">What's the role of Microsoft's partners in self-service purchases?</span></span>

<span data-ttu-id="5a888-182">拥有委派管理权限的合作伙伴可以在<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>中查看自助购买，就像管理员一样。合作伙伴可以帮助您支持要通过自助购买来集中购买产品的组织。</span><span class="sxs-lookup"><span data-stu-id="5a888-182">Partners who have delegated administration privileges can see self-service purchases in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, just like an admin. Partners can help support an organization that wants to centralize products bought through self-service purchases.</span></span> <span data-ttu-id="5a888-183">此外，合作伙伴可以提供用于扩展自助购买功能的解决方案。</span><span class="sxs-lookup"><span data-stu-id="5a888-183">Additionally, partners may offer solutions to extend the capabilities of a self-service purchase.</span></span>