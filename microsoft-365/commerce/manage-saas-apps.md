---
title: 为您的组织管理软件即服务应用程序
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
search.appverid: MET150
description: 了解如何在 Microsoft 365 管理中心中激活和管理第三方应用程序。
ms.openlocfilehash: eb2826a4b0c69d61eb35a9dfff37e9dc2dd6ad71
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141184"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="8f330-103">为你的组织管理第三方应用订阅</span><span class="sxs-lookup"><span data-stu-id="8f330-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8f330-104">管理员中心正在更改。</span><span class="sxs-lookup"><span data-stu-id="8f330-104">The admin center is changing.</span></span> <span data-ttu-id="8f330-105">如果你的体验与此处提供的详细信息不匹配，请参阅[关于新的 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="8f330-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="8f330-106">您可以在启用了预览模式的 Microsoft 365 管理中心中管理第三方应用程序的许可证和帐单。</span><span class="sxs-lookup"><span data-stu-id="8f330-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="8f330-107">更新的功能包括增强的订阅管理、改进的对帐单信息的访问权限，并提高了管理帐单的灵活性。</span><span class="sxs-lookup"><span data-stu-id="8f330-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="8f330-108">订阅管理基于 Microsoft 的更新的商业平台。</span><span class="sxs-lookup"><span data-stu-id="8f330-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="8f330-109">这适用于客户直接购买或从第三方提供商购买的软件即服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f330-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="8f330-110">如何获取服务软件应用程序</span><span class="sxs-lookup"><span data-stu-id="8f330-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="8f330-111">有几种方法可以购买第三方应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f330-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="8f330-112">**直接购买**–客户可以直接从[Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)或[AppSource](https://www.appsource.com/)购买订阅。</span><span class="sxs-lookup"><span data-stu-id="8f330-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="8f330-113">**合作伙伴购买**–通过合作伙伴中心与合作伙伴合作购买订阅。</span><span class="sxs-lookup"><span data-stu-id="8f330-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="8f330-114">**Microsoft 建议**–响应 microsoft Sales 中包括第三方应用程序的建议。</span><span class="sxs-lookup"><span data-stu-id="8f330-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="8f330-115">一旦客户购买了应用并接受 Microsoft 客户协议，他们就可以在 Microsoft 365 管理中心或 Microsoft Store for Business 中管理它们。</span><span class="sxs-lookup"><span data-stu-id="8f330-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="8f330-116">应用程序提供商以单层方式或通过购买用户的许可证销售应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f330-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="8f330-117">**平汇率**–也称为基于网站的定价，应用按月或年价格定价。</span><span class="sxs-lookup"><span data-stu-id="8f330-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="8f330-118">在 "应用程序" 页上，许可证数量列出时不受限制。</span><span class="sxs-lookup"><span data-stu-id="8f330-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="8f330-119">**许可证**–按许可证定价应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f330-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="8f330-120">客户将许可证分配给其组织中的每个用户</span><span class="sxs-lookup"><span data-stu-id="8f330-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="8f330-121">支持的区域</span><span class="sxs-lookup"><span data-stu-id="8f330-121">Supported regions</span></span>

<span data-ttu-id="8f330-122">以下地区提供了对第三方应用程序的支持：</span><span class="sxs-lookup"><span data-stu-id="8f330-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="8f330-123">阿根廷</span><span class="sxs-lookup"><span data-stu-id="8f330-123">Argentina</span></span>
- <span data-ttu-id="8f330-124">澳大利亚</span><span class="sxs-lookup"><span data-stu-id="8f330-124">Australia</span></span>
- <span data-ttu-id="8f330-125">加拿大</span><span class="sxs-lookup"><span data-stu-id="8f330-125">Canada</span></span>
- <span data-ttu-id="8f330-126">智利</span><span class="sxs-lookup"><span data-stu-id="8f330-126">Chile</span></span>
- <span data-ttu-id="8f330-127">法国</span><span class="sxs-lookup"><span data-stu-id="8f330-127">France</span></span>
- <span data-ttu-id="8f330-128">德国</span><span class="sxs-lookup"><span data-stu-id="8f330-128">Germany</span></span>
- <span data-ttu-id="8f330-129">希腊</span><span class="sxs-lookup"><span data-stu-id="8f330-129">Greece</span></span>
- <span data-ttu-id="8f330-130">波多黎各</span><span class="sxs-lookup"><span data-stu-id="8f330-130">Puerto Rico</span></span>
- <span data-ttu-id="8f330-131">南非</span><span class="sxs-lookup"><span data-stu-id="8f330-131">South Africa</span></span>
- <span data-ttu-id="8f330-132">英国</span><span class="sxs-lookup"><span data-stu-id="8f330-132">United Kingdom</span></span>
- <span data-ttu-id="8f330-133">美国</span><span class="sxs-lookup"><span data-stu-id="8f330-133">United States</span></span>
- <span data-ttu-id="8f330-134">西欧</span><span class="sxs-lookup"><span data-stu-id="8f330-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="8f330-135">激活第三方应用程序</span><span class="sxs-lookup"><span data-stu-id="8f330-135">Activate third-party apps</span></span>

<span data-ttu-id="8f330-136">管理员必须先激活第三方应用程序，然后才能将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="8f330-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="8f330-137">这些应用程序将在第三方发布者的门户中激活。</span><span class="sxs-lookup"><span data-stu-id="8f330-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="8f330-138">在管理中心中，转到 "**付费** > **产品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">应用程序</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="8f330-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="8f330-139">查找并选择要管理的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f330-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="8f330-140">在 "**设置" & "操作**" 下，选择 "**在 Publisher 门户中管理**"。</span><span class="sxs-lookup"><span data-stu-id="8f330-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="8f330-141">您将转到应用程序发布者的网站，您可以在其中激活应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f330-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="8f330-142">管理第三方应用</span><span class="sxs-lookup"><span data-stu-id="8f330-142">Manage third-party apps</span></span>

<span data-ttu-id="8f330-143">管理员在两个位置管理第三方应用： Microsoft 365 管理中心和第三方应用程序提供商的门户。</span><span class="sxs-lookup"><span data-stu-id="8f330-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="8f330-144">可在每个门户中执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="8f330-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="8f330-145">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="8f330-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="8f330-146">应用程序发布者门户</span><span class="sxs-lookup"><span data-stu-id="8f330-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="8f330-147">更改许可证数量</span><span class="sxs-lookup"><span data-stu-id="8f330-147">Change license quantity</span></span> <br> <span data-ttu-id="8f330-148">管理你的帐单支付方式</span><span class="sxs-lookup"><span data-stu-id="8f330-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="8f330-149">管理你的帐单支付方式</span><span class="sxs-lookup"><span data-stu-id="8f330-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="8f330-150">更改支付方式（信用卡）</span><span class="sxs-lookup"><span data-stu-id="8f330-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="8f330-151">查看发票</span><span class="sxs-lookup"><span data-stu-id="8f330-151">View invoice</span></span> <br> <span data-ttu-id="8f330-152">取消应用订阅</span><span class="sxs-lookup"><span data-stu-id="8f330-152">Cancel app subscription</span></span> | <span data-ttu-id="8f330-153">设置应用程序（为每个应用一次）</span><span class="sxs-lookup"><span data-stu-id="8f330-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="8f330-154">向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="8f330-154">Assign licenses to users</span></span> <br> <span data-ttu-id="8f330-155">技术支持</span><span class="sxs-lookup"><span data-stu-id="8f330-155">Technical support</span></span> |

<span data-ttu-id="8f330-156">在激活应用程序后，它将一直处于活动状态，除非它被取消、过期或付款不是最新的。</span><span class="sxs-lookup"><span data-stu-id="8f330-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="8f330-157">这些事件将应用程序状态更改为禁用。</span><span class="sxs-lookup"><span data-stu-id="8f330-157">These events change the app status to disabled.</span></span> <span data-ttu-id="8f330-158">在应用程序被禁用后，将无法重新激活。</span><span class="sxs-lookup"><span data-stu-id="8f330-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="8f330-159">若要继续使用该应用，请购买另一份副本。</span><span class="sxs-lookup"><span data-stu-id="8f330-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="8f330-160">分配许可证</span><span class="sxs-lookup"><span data-stu-id="8f330-160">Assign licenses</span></span>

<span data-ttu-id="8f330-161">管理员需要先激活第三方应用程序，然后才能将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="8f330-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="8f330-162">它们是在第三方发布者的门户中激活的。</span><span class="sxs-lookup"><span data-stu-id="8f330-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="8f330-163">在 "应用程序" 页上的 "**设置" & "操作**" 下，选择要分配许可证的链接。</span><span class="sxs-lookup"><span data-stu-id="8f330-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="8f330-164">在管理中心中，转到 "**付费** > **产品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">应用程序</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="8f330-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="8f330-165">查找并选择要管理的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f330-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="8f330-166">在 "**设置" & "操作**" 下，选择要**在 publisher 的门户中管理**的链接。</span><span class="sxs-lookup"><span data-stu-id="8f330-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="8f330-167">更改许可证数量</span><span class="sxs-lookup"><span data-stu-id="8f330-167">Change license quantity</span></span>

<span data-ttu-id="8f330-168">管理员可以更改其组织拥有的许可证的数量。</span><span class="sxs-lookup"><span data-stu-id="8f330-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="8f330-169">这仅适用于使用基于座位的定价购买的应用。</span><span class="sxs-lookup"><span data-stu-id="8f330-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="8f330-170">在管理中心中，转到 "**付费** > **产品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">应用程序</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="8f330-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="8f330-171">查找并选择要管理的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f330-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="8f330-172">选择 "**更改许可证数量**"。</span><span class="sxs-lookup"><span data-stu-id="8f330-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="8f330-173">管理支付方式</span><span class="sxs-lookup"><span data-stu-id="8f330-173">Manage payment methods</span></span>

<span data-ttu-id="8f330-174">每个软件即服务应用程序都有分配给他们的计费配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f330-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="8f330-175">通过计费配置文件，您可以自定义发票中包含的产品，以及您如何支付发票。</span><span class="sxs-lookup"><span data-stu-id="8f330-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="8f330-176">它们包括：</span><span class="sxs-lookup"><span data-stu-id="8f330-176">They include:</span></span>

- <span data-ttu-id="8f330-177">**支付方式**–信用卡或支票/电汇转移</span><span class="sxs-lookup"><span data-stu-id="8f330-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="8f330-178">**联系人信息**–帐单地址和联系人姓名</span><span class="sxs-lookup"><span data-stu-id="8f330-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="8f330-179">**角色**–允许您更改帐单配置文件、支付帐单或使用付费配置文件的付款方式进行购买的角色。</span><span class="sxs-lookup"><span data-stu-id="8f330-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="8f330-180">有关计费配置文件的详细信息，请参阅[了解计费配置文件](https://docs.microsoft.com/microsoft-store/billing-profile)。</span><span class="sxs-lookup"><span data-stu-id="8f330-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="8f330-181">更改软件即服务应用订阅上的记帐配置文件</span><span class="sxs-lookup"><span data-stu-id="8f330-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="8f330-182">在管理中心中，转到 "**付费** > **产品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">应用程序</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="8f330-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="8f330-183">查找并选择要管理的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f330-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="8f330-184">在 "**记帐配置文件**" 旁边，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="8f330-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="8f330-185">有关发票的详细信息，请参阅[了解你的发票](billing-and-payments/understand-your-invoice.md)。</span><span class="sxs-lookup"><span data-stu-id="8f330-185">For more information on invoices, see [Understand your invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="8f330-186">取消软件即服务应用订阅</span><span class="sxs-lookup"><span data-stu-id="8f330-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="8f330-187">您可以从应用程序页取消软件即服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f330-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="8f330-188">在管理中心中，转到 "**付费** > **产品** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">应用程序</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="8f330-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="8f330-189">查找并选择要管理的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f330-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="8f330-190">在 "**设置" & "操作**" 下，选择 "**取消订阅**"。</span><span class="sxs-lookup"><span data-stu-id="8f330-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>
