---
title: 我的订阅结束后对我的数据和访问权限有何影响？
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
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: 了解当 Microsoft 365 for business 订阅过期、被禁用或取消时数据会发生什么情况。
ms.openlocfilehash: 2a5a9e587b6b00017d3e489d948c9cee3db4777b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634870"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a><span data-ttu-id="a60b5-103">Microsoft 365 for business 订阅结束时我的数据和访问会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="a60b5-103">What happens to my data and access when my Microsoft 365 for business subscription ends?</span></span>

<span data-ttu-id="a60b5-104">如果你的订阅结束（因为它已过期或你决定取消），则在订阅完全关闭之前，你对 Microsoft 365 服务、应用程序和客户数据的访问会经历多个状态，或*deprovisioned*。</span><span class="sxs-lookup"><span data-stu-id="a60b5-104">If your subscription ends—either because it expires, or because you decide to cancel—your access to Microsoft 365 services, applications, and customer data go through multiple states before the subscription is fully turned off, or *deprovisioned*.</span></span> <span data-ttu-id="a60b5-105">如果你知道这一进展，你将能够更好地将你的订阅恢复到处于活动状态过晚的状态，或者，如果你离开 Microsoft 365，请先备份你的数据，然后再将其最终删除。</span><span class="sxs-lookup"><span data-stu-id="a60b5-105">If you are aware of this progression, you'll be better equipped to return your subscription to an active state before it's too late, or—if you're leaving Microsoft 365—back up your data before it is ultimately deleted.</span></span>
  
## <a name="microsoft-365-for-business-subscription-lifecycle"></a><span data-ttu-id="a60b5-106">Microsoft 365 for business：订阅生命周期</span><span class="sxs-lookup"><span data-stu-id="a60b5-106">Microsoft 365 for business: Subscription lifecycle</span></span>
- <span data-ttu-id="a60b5-107">如果你的订阅已过期，则会经历以下阶段：已过期/已禁用/Deprovisioned。</span><span class="sxs-lookup"><span data-stu-id="a60b5-107">If your subscription expires, it goes through the following stages: Expired / Disabled / Deprovisioned.</span></span> <span data-ttu-id="a60b5-108">过期的阶段在订阅到达其结束日期后立即开始。</span><span class="sxs-lookup"><span data-stu-id="a60b5-108">The Expired stage starts immediately after the subscription has reached its end date.</span></span>
- <span data-ttu-id="a60b5-109">如果您关闭年度订阅的定期帐单，它会经历与过期订阅相同的阶段。</span><span class="sxs-lookup"><span data-stu-id="a60b5-109">If you turn off recurring billing on your annual subscription, it goes through the same stages as an expired subscription.</span></span> <span data-ttu-id="a60b5-110">第一阶段的开始是每年订阅的周年纪念，而不是在关闭订阅的定期记帐设置的日期上启动的。</span><span class="sxs-lookup"><span data-stu-id="a60b5-110">The first stage starts are the anniversary of the annual subscription, not starting on the date that you turned off the subscription's recurring billing setting.</span></span>
- <span data-ttu-id="a60b5-111">如果取消每月订阅，则会立即禁用它（在取消日期时）。</span><span class="sxs-lookup"><span data-stu-id="a60b5-111">If you cancel your monthly subscription, it will be disabled immediately (at the date of cancellation).</span></span> <span data-ttu-id="a60b5-112">这意味着您的用户将立即失去对 Microsoft 365 资产的访问权限，并且只有管理员才能在接下来的90天访问数据。</span><span class="sxs-lookup"><span data-stu-id="a60b5-112">This means your users will lose access to the Microsoft 365 assets immediately and only admins will have access to the data for the next 90 days.</span></span>

<span data-ttu-id="a60b5-113">下表介绍了付费 Microsoft 365 for business 订阅过期时的预期效果。</span><span class="sxs-lookup"><span data-stu-id="a60b5-113">The following table explains what you can expect when a paid Microsoft 365 for business subscription expires.</span></span>

| <span data-ttu-id="a60b5-114">**Active**</span><span class="sxs-lookup"><span data-stu-id="a60b5-114">**Active**</span></span>                                                             | <span data-ttu-id="a60b5-115">**过期<br/>（30天\*）**</span><span class="sxs-lookup"><span data-stu-id="a60b5-115">**Expired <br/>(30 days\*)**</span></span>                                                | <span data-ttu-id="a60b5-116">**已<br/>禁用（90\*天）**</span><span class="sxs-lookup"><span data-stu-id="a60b5-116">**Disabled <br/>(90 days\*)**</span></span>                                               | <span data-ttu-id="a60b5-117">**已取消设置**</span><span class="sxs-lookup"><span data-stu-id="a60b5-117">**Deprovisioned**</span></span>                                                                         |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="a60b5-118">*所有可访问的数据*</span><span class="sxs-lookup"><span data-stu-id="a60b5-118">*Data accessible to all*</span></span>                                               | <span data-ttu-id="a60b5-119">*所有可访问的数据*</span><span class="sxs-lookup"><span data-stu-id="a60b5-119">*Data accessible to all*</span></span>                                                     | <span data-ttu-id="a60b5-120">*仅供管理员访问的数据*</span><span class="sxs-lookup"><span data-stu-id="a60b5-120">*Data accessible to admins only*</span></span>                                             | <span data-ttu-id="a60b5-121">**删除了<br/>数据删除的 Azure Active Directory （如果未被其他服务使用）**</span><span class="sxs-lookup"><span data-stu-id="a60b5-121">**Data deleted<br/>Azure Active Directory is removed, if not in use by other services**</span></span> |
| <span data-ttu-id="a60b5-122">用户具有对 Microsoft 365、数据和 Office 应用程序的常规访问权限</span><span class="sxs-lookup"><span data-stu-id="a60b5-122">Users have normal access to Microsoft 365, data, and Office applications</span></span>  | <span data-ttu-id="a60b5-123">用户具有对 Microsoft 365、文件和应用程序的常规访问权限</span><span class="sxs-lookup"><span data-stu-id="a60b5-123">Users have normal access to Microsoft 365, files, and applications</span></span>              | <span data-ttu-id="a60b5-124">用户无法访问 Microsoft 365、文件或应用程序</span><span class="sxs-lookup"><span data-stu-id="a60b5-124">Users can't access Microsoft 365, files, or applications</span></span>                        | <span data-ttu-id="a60b5-125">用户无法访问 Microsoft 365、文件或应用程序</span><span class="sxs-lookup"><span data-stu-id="a60b5-125">Users can't access Microsoft 365, files, or applications</span></span>                                     |
| <span data-ttu-id="a60b5-126">管理员具有对 Microsoft 365、数据和 Office 应用程序的常规访问权限</span><span class="sxs-lookup"><span data-stu-id="a60b5-126">Admins have normal access to Microsoft 365, data, and Office applications</span></span> | <span data-ttu-id="a60b5-127">管理员可以访问管理中心</span><span class="sxs-lookup"><span data-stu-id="a60b5-127">Admins can access the admin center</span></span>                                           | <span data-ttu-id="a60b5-128">管理员可以访问管理中心，但不能向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="a60b5-128">Admins can access the admin center, but can't assign licenses to users</span></span>       | <span data-ttu-id="a60b5-129">管理员可以访问管理中心来购买和管理其他订阅</span><span class="sxs-lookup"><span data-stu-id="a60b5-129">Admins can access the admin center to purchase and manage other subscriptions</span></span>             |
|                                                                        | <span data-ttu-id="a60b5-130">全局管理员或帐单管理员可以在管理中心重新激活订阅</span><span class="sxs-lookup"><span data-stu-id="a60b5-130">Global or billing admins can reactivate the subscription in the admin center</span></span> | <span data-ttu-id="a60b5-131">全局管理员或帐单管理员可以在管理中心重新激活订阅</span><span class="sxs-lookup"><span data-stu-id="a60b5-131">Global or billing admins can reactivate the subscription in the admin center</span></span> |                                                                                           |

<span data-ttu-id="a60b5-132">\* 在大多数国家和地区，大多数产品提供。</span><span class="sxs-lookup"><span data-stu-id="a60b5-132">\*For most offers, in most countries and regions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a60b5-133">**什么是 "客户数据"？**</span><span class="sxs-lookup"><span data-stu-id="a60b5-133">**What is "customer data"?**</span></span> <span data-ttu-id="a60b5-134">客户数据（如[Microsoft Online 服务条款](https://go.microsoft.com/fwlink/p/?LinkId=613649)中所定义）是指所有数据，包括所有的数据，包括由客户通过 microsoft 365 服务提供给 microsoft 的所有文本、声音或图像文件。</span><span class="sxs-lookup"><span data-stu-id="a60b5-134">Customer data, as defined in the [Microsoft Online Service Terms](https://go.microsoft.com/fwlink/p/?LinkId=613649), refers to all data, including all text, sound, or image files that are provided to Microsoft by, or on behalf of, the customer through the customer's use of Microsoft 365 services.</span></span> <span data-ttu-id="a60b5-135">若要了解有关客户数据保护的详细信息，请参阅[Microsoft 服务信任门户入门](https://support.office.com/article/f30e2353-0bd6-41ed-8347-eea1fb8d2662)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-135">To learn more about the protection of customer data, see the [Get started with the Microsoft Service Trust Portal](https://support.office.com/article/f30e2353-0bd6-41ed-8347-eea1fb8d2662).</span></span>
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a><span data-ttu-id="a60b5-136">如果我的订阅即将过期，我的选项是什么？</span><span class="sxs-lookup"><span data-stu-id="a60b5-136">What are my options if my subscription is about to expire?</span></span>

<span data-ttu-id="a60b5-137">订阅处于活动状态时，您和最终用户对数据具有常规访问权限，如电子邮件和 OneDrive for Business，以及 Office 应用程序等服务。</span><span class="sxs-lookup"><span data-stu-id="a60b5-137">While a subscription is active, you and your end users have normal access to your data, services like email and OneDrive for Business, and Office applications.</span></span> <span data-ttu-id="a60b5-138">作为管理员，你将在你的订阅临近到期日期时通过电子邮件和管理中心收到一系列通知。</span><span class="sxs-lookup"><span data-stu-id="a60b5-138">As the admin, you'll receive a series of notifications via email and in the admin center as your subscription nears its expiration date.</span></span>
  
<span data-ttu-id="a60b5-139">在订阅实际达到到期日期之前，您有几个选项：</span><span class="sxs-lookup"><span data-stu-id="a60b5-139">Before the subscription actually reaches its expiration date, you have a few options:</span></span>

::: moniker range="o365-worldwide"
  
- <span data-ttu-id="a60b5-140">**为订阅启用定期帐单。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-140">**Enable recurring billing for the subscription.**</span></span>

  - <span data-ttu-id="a60b5-141">如果**定期记帐**已打开，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="a60b5-141">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="a60b5-142">你的订阅将自动计费，并且将根据你当前的付款频率，向你收取额外一年或一个月的费用。</span><span class="sxs-lookup"><span data-stu-id="a60b5-142">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="a60b5-143">如果您已关闭**定期付费**的任何原因，您始终可以[重新启用定期付费](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-143">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

  - <span data-ttu-id="a60b5-144">如果使用预付卡购买了 Microsoft 365 的商业应用程序，则可以为订阅[启用定期帐单](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-144">If you purchased Microsoft 365 Apps for business with a prepaid card, you can [turn on Recurring billing](renew-your-subscription.md) for your subscription.</span></span>

  - <span data-ttu-id="a60b5-145">如果你是一位预付一年期免费订阅的批量许可客户，请联系你的合作伙伴购买新的产品密钥。</span><span class="sxs-lookup"><span data-stu-id="a60b5-145">If you're an Open Volume Licensing customer with a prepaid, one-year subscription, contact your partner to purchase a new product key.</span></span> <span data-ttu-id="a60b5-146">你将通过电子邮件收到说明，以在[批量许可服务中心](https://go.microsoft.com/fwlink/p/?LinkID=282016)中激活你的密钥。</span><span class="sxs-lookup"><span data-stu-id="a60b5-146">You'll receive instructions via email to activate your key in the [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016).</span></span> <span data-ttu-id="a60b5-147">若要了解如何查找新合作伙伴或以前使用过的合作伙伴，请参阅[查找合作伙伴或经销商](../../admin/manage/find-your-partner-or-reseller.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-147">To learn how to find a new partner, or the partner you've worked with in the past, see [Find your partner or reseller](../../admin/manage/find-your-partner-or-reseller.md).</span></span>

  - <span data-ttu-id="a60b5-148">如果你有 Microsoft 365 应用程序的商业版，请参阅[管理你的订阅的定期帐单](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-148">If you have Microsoft 365 Apps for business, see [Manage recurring billing for your subscription](renew-your-subscription.md).</span></span>

- <span data-ttu-id="a60b5-149">**允许订阅过期。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-149">**Let the subscription expire.**</span></span>

  - <span data-ttu-id="a60b5-150">如果是通过信用卡或发票付款，并且不希望继续订阅，请关闭[定期付费](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-150">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="a60b5-151">你的订阅将在到期日期后过期，你可以忽略所有相关的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="a60b5-151">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

  - <span data-ttu-id="a60b5-152">如果您是与合作伙伴合作的开放式批量许可客户，您可以通过不采取任何措施让订阅过期。</span><span class="sxs-lookup"><span data-stu-id="a60b5-152">If you're an Open Volume Licensing customer working with a partner, you can let your subscription expire by taking no action.</span></span>

  - <span data-ttu-id="a60b5-153">如果你是 Office 365 小型企业高级版客户，并且你预付 Office 365 并使用产品密钥激活它，则可以通过不采取任何措施让你的订阅过期。</span><span class="sxs-lookup"><span data-stu-id="a60b5-153">If you're a Office 365 Small Business Premium customer, and you prepaid for Office 365 and activated it with a product key, you can let your subscription expire by taking no action.</span></span>

- <span data-ttu-id="a60b5-154">**在订阅过期之前取消。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-154">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="a60b5-155">有关详细信息，请参阅[取消订阅](cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-155">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
  
- <span data-ttu-id="a60b5-156">**管理订阅的定期帐单。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-156">**Manage recurring billing for the subscription.**</span></span>

  - <span data-ttu-id="a60b5-157">如果**定期记帐**已打开，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="a60b5-157">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="a60b5-158">你的订阅将自动计费，并且将根据你当前的付款频率，向你收取额外一年或一个月的费用。</span><span class="sxs-lookup"><span data-stu-id="a60b5-158">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="a60b5-159">如果您已关闭**定期付费**的任何原因，您始终可以[重新启用定期付费](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-159">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

  - <span data-ttu-id="a60b5-160">如果使用预付卡购买了 Microsoft 365 的商业应用程序，则可以为订阅[启用定期帐单](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-160">If you purchased Microsoft 365 Apps for business with a prepaid card, you can [turn on Recurring billing](renew-your-subscription.md) for your subscription.</span></span>

  - <span data-ttu-id="a60b5-161">如果你是一位预付一年期免费订阅的批量许可客户，请联系你的合作伙伴购买新的产品密钥。</span><span class="sxs-lookup"><span data-stu-id="a60b5-161">If you're an Open Volume Licensing customer with a prepaid, one-year subscription, contact your partner to purchase a new product key.</span></span> <span data-ttu-id="a60b5-162">你将通过电子邮件收到说明，以在[批量许可服务中心](https://go.microsoft.com/fwlink/p/?LinkID=282016)中激活你的密钥。</span><span class="sxs-lookup"><span data-stu-id="a60b5-162">You'll receive instructions via email to activate your key in the [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016).</span></span> <span data-ttu-id="a60b5-163">若要了解如何查找新合作伙伴或以前使用过的合作伙伴，请参阅[查找合作伙伴或经销商](../../admin/manage/find-your-partner-or-reseller.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-163">To learn how to find a new partner, or the partner you've worked with in the past, see [Find your partner or reseller](../../admin/manage/find-your-partner-or-reseller.md).</span></span>

  - <span data-ttu-id="a60b5-164">如果你有 Microsoft 365 应用程序的商业版，请参阅[续订订阅](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-164">If you have Microsoft 365 Apps for business, see [Renew your subscription](renew-your-subscription.md).</span></span>

- <span data-ttu-id="a60b5-165">**允许订阅过期。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-165">**Let the subscription expire.**</span></span>

  - <span data-ttu-id="a60b5-166">如果是通过信用卡或发票付款，并且不希望继续订阅，请关闭[定期付费](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-166">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="a60b5-167">你的订阅将在到期日期后过期，你可以忽略所有相关的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="a60b5-167">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

  - <span data-ttu-id="a60b5-168">如果您是与合作伙伴合作的开放式批量许可客户，您可以通过不采取任何措施让订阅过期。</span><span class="sxs-lookup"><span data-stu-id="a60b5-168">If you're an Open Volume Licensing customer working with a partner, you can let your subscription expire by taking no action.</span></span>

  - <span data-ttu-id="a60b5-169">如果你是 Office 365 小型企业高级版客户，并且你预付 Office 365 并使用产品密钥激活它，则可以通过不采取任何措施让你的订阅过期。</span><span class="sxs-lookup"><span data-stu-id="a60b5-169">If you're a Office 365 Small Business Premium customer, and you prepaid for Office 365 and activated it with a product key, you can let your subscription expire by taking no action.</span></span>

- <span data-ttu-id="a60b5-170">**在订阅过期之前取消。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-170">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="a60b5-171">有关详细信息，请参阅[取消订阅](cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-171">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- <span data-ttu-id="a60b5-172">**续订订阅。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-172">**Renew the subscription.**</span></span> <span data-ttu-id="a60b5-173">如果**定期记帐**已打开，则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="a60b5-173">If **Recurring billing** is already turned on, you don't have to take any action.</span></span> <span data-ttu-id="a60b5-174">你的订阅将自动计费，并且将根据你当前的付款频率，向你收取额外一年或一个月的费用。</span><span class="sxs-lookup"><span data-stu-id="a60b5-174">Your subscription will be automatically billed, and you'll be charged for an additional year or month, depending on your current payment frequency.</span></span> <span data-ttu-id="a60b5-175">如果您已关闭**定期付费**的任何原因，您始终可以[重新启用定期付费](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-175">If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).</span></span>

- <span data-ttu-id="a60b5-176">**允许订阅过期。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-176">**Let the subscription expire.**</span></span> <span data-ttu-id="a60b5-177">如果是通过信用卡或发票付款，并且不希望继续订阅，请关闭[定期付费](renew-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-177">If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md).</span></span> <span data-ttu-id="a60b5-178">你的订阅将在到期日期后过期，你可以忽略所有相关的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="a60b5-178">Your subscription will expire on its expiration date, and you can ignore all related email notifications.</span></span>

- <span data-ttu-id="a60b5-179">**在订阅过期之前取消。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-179">**Cancel before the subscription expires.**</span></span> <span data-ttu-id="a60b5-180">有关详细信息，请参阅[取消订阅](cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-180">For details, see [Cancel your subscription](cancel-your-subscription.md).</span></span>

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a><span data-ttu-id="a60b5-181">我的订阅过期后会发生什么？</span><span class="sxs-lookup"><span data-stu-id="a60b5-181">What happens after my subscription expires?</span></span>
<span data-ttu-id="a60b5-182">如果你的订阅过期，它会在最终删除前经历多个状态。</span><span class="sxs-lookup"><span data-stu-id="a60b5-182">If you let your subscription expire, it goes through multiple states before it is ultimately deleted.</span></span> <span data-ttu-id="a60b5-183">如果您想要继续执行该服务，或在决定不再需要订阅时备份您的数据，这将使您（作为管理员、重新激活的时间）。</span><span class="sxs-lookup"><span data-stu-id="a60b5-183">This gives you, as the admin, time to reactivate if you want to continue the service, or to back up your data if you decide you no longer want the subscription.</span></span>
  
<span data-ttu-id="a60b5-184">以下是你的订阅处于每种状态时的预期效果。</span><span class="sxs-lookup"><span data-stu-id="a60b5-184">Here's what you can expect when your subscription is in each state.</span></span>
  
### <a name="state-expired"></a><span data-ttu-id="a60b5-185">状态：已过期</span><span class="sxs-lookup"><span data-stu-id="a60b5-185">State: Expired</span></span>
  
::: moniker range="o365-worldwide"

 <span data-ttu-id="a60b5-186">**预期内容：** 过期状态将为大多数订阅（包括在大多数国家和地区中通过[Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298)购买的订阅）持续30天。</span><span class="sxs-lookup"><span data-stu-id="a60b5-186">**What to expect:** The expired state lasts for 30 days for most subscriptions, including subscriptions purchased through [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), in most countries and regions.</span></span> <span data-ttu-id="a60b5-187">对于批量许可产品，除了 Microsoft 开放之外，过期状态将持续90天。</span><span class="sxs-lookup"><span data-stu-id="a60b5-187">For Volume Licensing products, except for Microsoft Open, the expired state lasts 90 days.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 <span data-ttu-id="a60b5-188">**预期内容：** 过期状态将为大多数订阅（包括在大多数国家和地区中通过[Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298)购买的订阅）持续30天。</span><span class="sxs-lookup"><span data-stu-id="a60b5-188">**What to expect:** The expired state lasts for 30 days for most subscriptions, including subscriptions purchased through [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), in most countries and regions.</span></span> <span data-ttu-id="a60b5-189">对于批量许可产品，除了 Microsoft 开放之外，过期状态将持续90天。</span><span class="sxs-lookup"><span data-stu-id="a60b5-189">For Volume Licensing products, except for Microsoft Open, the expired state lasts 90 days.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 <span data-ttu-id="a60b5-190">**预期内容：** 在大多数国家和地区，过期状态为大多数订阅的30天。</span><span class="sxs-lookup"><span data-stu-id="a60b5-190">**What to expect:** The expired state is 30 days for most subscriptions, in most countries and regions.</span></span>

::: moniker-end

<span data-ttu-id="a60b5-191">在此状态下，用户可以正常访问 Microsoft 365 门户、Office 应用程序和服务（如电子邮件和 SharePoint Online）。</span><span class="sxs-lookup"><span data-stu-id="a60b5-191">In this state, users have normal access to the Microsoft 365 portal, Office applications, and services such as email and SharePoint Online.</span></span>
  
<span data-ttu-id="a60b5-192">作为管理员，你仍然可以访问管理中心。</span><span class="sxs-lookup"><span data-stu-id="a60b5-192">As an admin, you still have access to the admin center.</span></span> <span data-ttu-id="a60b5-193">别担心，全局或帐单管理员可以[重新激活订阅](reactivate-your-subscription.md)并继续使用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a60b5-193">Don't worry—global or billing admins can [reactivate the subscription](reactivate-your-subscription.md) and continue using Microsoft 365.</span></span> <span data-ttu-id="a60b5-194">如果不重新激活，请务必[备份你的数据](back-up-data-before-switching-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-194">If you don't reactivate, be sure to [back up your data](back-up-data-before-switching-plans.md).</span></span>
  
### <a name="state-disabled"></a><span data-ttu-id="a60b5-195">状态：已禁用</span><span class="sxs-lookup"><span data-stu-id="a60b5-195">State: Disabled</span></span>
  
::: moniker range="o365-worldwide"

 <span data-ttu-id="a60b5-196">**预期内容：** 如果您在订阅处于 "已过期" 状态时不重新激活它，则它将进入禁用状态，这在大多数国家和地区中会在大多数订阅中持续90天。</span><span class="sxs-lookup"><span data-stu-id="a60b5-196">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which lasts for 90 days for most subscriptions, in most countries and regions.</span></span> <span data-ttu-id="a60b5-197">对于批量许可产品，禁用状态将持续30天。</span><span class="sxs-lookup"><span data-stu-id="a60b5-197">For Volume Licensing products, the disabled state lasts 30 days.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 <span data-ttu-id="a60b5-198">**预期内容：** 如果您在订阅处于 "已过期" 状态时不重新激活它，则它将进入禁用状态，这在大多数国家和地区中会在大多数订阅中持续90天。</span><span class="sxs-lookup"><span data-stu-id="a60b5-198">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which lasts for 90 days for most subscriptions, in most countries and regions.</span></span> <span data-ttu-id="a60b5-199">对于批量许可产品，禁用状态将持续30天。</span><span class="sxs-lookup"><span data-stu-id="a60b5-199">For Volume Licensing products, the disabled state lasts 30 days.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 <span data-ttu-id="a60b5-200">**预期内容：** 如果您在订阅处于 "已过期" 状态时不重新激活它，则会在大多数国家和地区中将其移至禁用状态，即大多数订阅的90天。</span><span class="sxs-lookup"><span data-stu-id="a60b5-200">**What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which is 90 days for most subscriptions, in most countries and regions.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="a60b5-201">在此状态下，您的访问会显著降低。</span><span class="sxs-lookup"><span data-stu-id="a60b5-201">In this state, your access decreases significantly.</span></span> <span data-ttu-id="a60b5-202">您的用户无法登录，或者无法访问电子邮件或 SharePoint Online 等服务。</span><span class="sxs-lookup"><span data-stu-id="a60b5-202">Your users can't sign in, or access services like email or SharePoint Online.</span></span> <span data-ttu-id="a60b5-203">Office 应用程序最终将移动到只读、缩减功能模式，并显示未[授权的产品通知](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-203">Office applications eventually move into a read-only, reduced functionality mode and display [Unlicensed Product notifications](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).</span></span> <span data-ttu-id="a60b5-204">您仍可以登录并进入管理中心，但不能向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="a60b5-204">You can still sign in and get to the admin center, but can't assign licenses to users.</span></span> <span data-ttu-id="a60b5-205">您的客户数据（包括所有用户数据、电子邮件和工作组网站上的文件）仅供您和其他管理员使用。</span><span class="sxs-lookup"><span data-stu-id="a60b5-205">Your customer data, including all user data, email, and files on team sites, is available only to you and other admins.</span></span>

::: moniker-end

<span data-ttu-id="a60b5-206">作为全局管理员或帐单管理员，你可以[重新激活订阅](reactivate-your-subscription.md)，并继续使用 Microsoft 365，让你的所有客户数据保持不变。</span><span class="sxs-lookup"><span data-stu-id="a60b5-206">As a global or billing admin, you can [reactivate the subscription](reactivate-your-subscription.md) and continue using Microsoft 365 with all of your customer data intact.</span></span> <span data-ttu-id="a60b5-207">如果选择不重新激活，请务必[备份你的数据](back-up-data-before-switching-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-207">If you choose not to reactivate, be sure to [back up your data](back-up-data-before-switching-plans.md).</span></span>

### <a name="state-deprovisioned"></a><span data-ttu-id="a60b5-208">状态： Deprovisioned</span><span class="sxs-lookup"><span data-stu-id="a60b5-208">State: Deprovisioned</span></span>
  
 <span data-ttu-id="a60b5-209">**预期内容：** 如果您在您的订阅处于宽限期或已禁用状态时不重新激活它，则该订阅是 deprovisioned。</span><span class="sxs-lookup"><span data-stu-id="a60b5-209">**What to expect:** If you don't reactivate your subscription while it is in grace or disabled, the subscription is deprovisioned.</span></span>
  
<span data-ttu-id="a60b5-210">管理员和用户不再有权访问订阅附带的服务或 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a60b5-210">Admins and users no longer have access to the services or Office applications that came with the subscription.</span></span> <span data-ttu-id="a60b5-211">所有客户数据（从用户数据到文档和电子邮件）都将永久删除，并且无法以任何方式恢复。</span><span class="sxs-lookup"><span data-stu-id="a60b5-211">All customer data—from user data to documents and email—is permanently deleted and unable to be recovered in any way.</span></span>
  
<span data-ttu-id="a60b5-212">此时，无法重新激活订阅。</span><span class="sxs-lookup"><span data-stu-id="a60b5-212">At this point, you can't reactivate the subscription.</span></span> <span data-ttu-id="a60b5-213">但是，作为全局或帐单管理员，你仍可以访问管理中心来管理其他订阅，或购买新订阅以满足你的业务需求。</span><span class="sxs-lookup"><span data-stu-id="a60b5-213">However, as a global or billing admin, you can still access the admin center to manage other subscriptions, or to buy new subscriptions to meet your business needs.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a60b5-214">添加已 deprovisioned 的相同类型的新订阅不会还原与 deprovisioned 订阅关联的数据。</span><span class="sxs-lookup"><span data-stu-id="a60b5-214">Adding a new subscription of the same type that has been deprovisioned does not restore the data that was associated with the deprovisioned subscription.</span></span>

### <a name="what-happens-when-my-trial-ends"></a><span data-ttu-id="a60b5-215">我的试用版结束时会发生什么？</span><span class="sxs-lookup"><span data-stu-id="a60b5-215">What happens when my trial ends?</span></span>

<span data-ttu-id="a60b5-216">试用版结束后，你将无法继续使用 Microsoft 365 免费版。</span><span class="sxs-lookup"><span data-stu-id="a60b5-216">When your trial ends, you won't be able to continue using Microsoft 365 for free.</span></span> <span data-ttu-id="a60b5-217">您有几个选项：</span><span class="sxs-lookup"><span data-stu-id="a60b5-217">You have a few options:</span></span>

::: moniker range="o365-worldwide"
- <span data-ttu-id="a60b5-218">**购买 Microsoft 365。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-218">**Buy Microsoft 365.**</span></span> <span data-ttu-id="a60b5-219">试用期到期后，它会移动到宽限期，为你提供另外30天（在大多数国家和地区的实验中），以购买 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a60b5-219">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Microsoft 365.</span></span> <span data-ttu-id="a60b5-220">若要了解如何将试用版转换为付费订阅，请参阅[购买试用版的 Microsoft 365 for business](../buy-a-subscription-from-your-free-trial.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-220">To learn how to convert your trial into a paid subscription, see [Buy your trial version of Microsoft 365 for business](../buy-a-subscription-from-your-free-trial.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"
- <span data-ttu-id="a60b5-221">**购买 Microsoft 365。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-221">**Buy Microsoft 365.**</span></span> <span data-ttu-id="a60b5-222">试用期到期后，它会移动到宽限期，为你提供另外30天（在大多数国家和地区的实验中），以购买 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a60b5-222">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Microsoft 365.</span></span> <span data-ttu-id="a60b5-223">若要了解如何将试用版转换为付费订阅，请参阅[购买试用版的 Microsoft 365 for business](../buy-a-subscription-from-your-free-trial.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-223">To learn how to convert your trial into a paid subscription, see [Buy your trial version of Microsoft 365 for business](../buy-a-subscription-from-your-free-trial.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"
- <span data-ttu-id="a60b5-224">**购买 Office 365。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-224">**Buy Office 365.**</span></span> <span data-ttu-id="a60b5-225">试用期到期后，它会移动到宽限期，为你提供另外30天（在大多数国家和地区的实验中），以购买 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a60b5-225">When your trial expires, it moves into a grace period, giving you another 30 days (for most trials, in most countries and regions) to purchase Office 365.</span></span> <span data-ttu-id="a60b5-226">若要了解如何将试用版转换为付费订阅，请参阅[购买或尝试订阅由世纪互联运营的 Office 365](../../admin/services-in-china/buy-or-try-subscriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-226">To learn how to convert your trial into a paid subscription, see [Buy or try subscriptions for Office 365 operated by 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).</span></span>

::: moniker-end

- <span data-ttu-id="a60b5-227">**延长试用版。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-227">**Extend your trial.**</span></span> <span data-ttu-id="a60b5-228">需要更多时间来评估 Microsoft 365？</span><span class="sxs-lookup"><span data-stu-id="a60b5-228">Need more time to evaluate Microsoft 365?</span></span> <span data-ttu-id="a60b5-229">在某些情况下，您可以[延长试用版](../extend-your-trial.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-229">In certain cases, you may be able to [extend your trial](../extend-your-trial.md).</span></span>

- <span data-ttu-id="a60b5-230">**取消试用版或让其过期。**</span><span class="sxs-lookup"><span data-stu-id="a60b5-230">**Cancel the trial or let it expire.**</span></span> <span data-ttu-id="a60b5-231">如果你决定不购买 Microsoft 365，你可以让你的试用版过期或[取消](cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-231">If you decide not to buy Microsoft 365, you can let your trial expire or [cancel it](cancel-your-subscription.md).</span></span> <span data-ttu-id="a60b5-232">请务必备份要保留的所有数据。</span><span class="sxs-lookup"><span data-stu-id="a60b5-232">Be sure to back up any data you want to keep.</span></span> <span data-ttu-id="a60b5-233">30天宽限期后不久，你的试用帐户信息和数据将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="a60b5-233">Soon after the 30 day grace period, your trial account information and data is permanently erased.</span></span>

## <a name="what-happens-if-i-cancel-a-subscription"></a><span data-ttu-id="a60b5-234">如果我取消订阅会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="a60b5-234">What happens if I cancel a subscription?</span></span>

<span data-ttu-id="a60b5-235">如果您在期限结束日期之前取消了订阅，订阅将跳过已过期状态并直接移到禁用状态，在大多数国家和地区中，大多数订阅为90天。</span><span class="sxs-lookup"><span data-stu-id="a60b5-235">If you cancel your subscription before its term end date, the subscription skips the expired state and moves directly into the disabled state, which is 90 days for most subscriptions, in most countries and regions.</span></span> <span data-ttu-id="a60b5-236">建议您在取消之前[备份数据](back-up-data-before-switching-plans.md)，但作为管理员，您仍可以访问和备份您的组织的数据，同时处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="a60b5-236">We recommend that you [back up your data](back-up-data-before-switching-plans.md) before canceling, but as an admin, you can still access and back up data for your organization while it is in the disabled state.</span></span> <span data-ttu-id="a60b5-237">你留下的任何客户数据都可能在取消的 90 天之后、180 天之前被删除。</span><span class="sxs-lookup"><span data-stu-id="a60b5-237">Any customer data that you leave behind may be deleted after 90 days, and will be deleted no later than 180 days after cancellation.</span></span>
  
<span data-ttu-id="a60b5-238">如果取消订阅，则会为你和你的用户提供预期。</span><span class="sxs-lookup"><span data-stu-id="a60b5-238">Here's what to expect for you and your users if you cancel a subscription.</span></span>
  
- <span data-ttu-id="a60b5-239">**管理员访问**管理员仍可以登录并访问管理中心，并根据需要购买其他订阅。</span><span class="sxs-lookup"><span data-stu-id="a60b5-239">**Admin access** Admins can still sign in and access the admin center, and buy other subscriptions as needed.</span></span> <span data-ttu-id="a60b5-240">作为全局或帐单管理员，你有90天的时间来[重新激活订阅](reactivate-your-subscription.md)的所有数据都完好无损。</span><span class="sxs-lookup"><span data-stu-id="a60b5-240">As a global or billing admin, you have 90 days to [reactivate the subscription](reactivate-your-subscription.md) with all data intact.</span></span>

- <span data-ttu-id="a60b5-241">**用户访问**您的用户不能使用 OneDrive for Business 等服务，也不能访问客户数据，例如，电子邮件或工作组网站上的文档。</span><span class="sxs-lookup"><span data-stu-id="a60b5-241">**User access** Your users won't be able to use services like OneDrive for Business, or access customer data—for example, email or documents on team sites.</span></span> <span data-ttu-id="a60b5-242">Word 和 Excel 等 Office 应用程序最终将进入只读的缩减功能模式，并显示 [未经授权的产品通知](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-242">Office applications, like Word and Excel, will eventually move into a read-only, reduced functionality mode and display [Unlicensed Product notifications](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).</span></span>

<span data-ttu-id="a60b5-243">若要了解如何取消，请参阅[取消订阅](cancel-your-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-243">To learn how to cancel, see [Cancel your subscription](cancel-your-subscription.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a60b5-244">如果您希望在典型禁用的时段之前删除订阅数据，则可以请求快速取消准备。</span><span class="sxs-lookup"><span data-stu-id="a60b5-244">If you want your subscription data to be deleted before the typical Disabled period is over, you can request expedited deprovisioning.</span></span> <span data-ttu-id="a60b5-245">如果请求快速解除配置，则订阅数据将在取消后的 3 天内删除。</span><span class="sxs-lookup"><span data-stu-id="a60b5-245">When you request expedited deprovisioning, your subscription data is deleted within 3 days of cancellation.</span></span> <span data-ttu-id="a60b5-246">若要使用加速解除，请[致电支持人员](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="a60b5-246">To use expedited deprovisioning, [call support](../../admin/contact-support-for-business-products.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a60b5-247">此页面上的信息受[Microsoft 策略免责声明和更改通知](https://go.microsoft.com/fwlink/p/?LinkId=613651)的制约。</span><span class="sxs-lookup"><span data-stu-id="a60b5-247">The information on this page is subject to the [Microsoft Policy Disclaimer and Change Notice](https://go.microsoft.com/fwlink/p/?LinkId=613651).</span></span> <span data-ttu-id="a60b5-248">定期返回到此网站以查看任何更改。</span><span class="sxs-lookup"><span data-stu-id="a60b5-248">Return to this site periodically to review any changes.</span></span>
