---
title: Microsoft 托管桌面产品生命周期
description: 本文列出了 Microsoft 托管桌面中使用的设备规范。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75e6c2853a0ff41efdf7d5639f675927f3b95ea4
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841195"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a><span data-ttu-id="3cae9-104">Microsoft 托管桌面产品生命周期</span><span class="sxs-lookup"><span data-stu-id="3cae9-104">Microsoft Managed Desktop product lifecycle</span></span>

<span data-ttu-id="3cae9-105">Microsoft 托管桌面使用户受益，他们确保他们始终使用提供最佳性能、可靠性、设计和安全功能的设备 (例如支持 Windows Hello) 。</span><span class="sxs-lookup"><span data-stu-id="3cae9-105">Microsoft Managed Desktop benefits users assuring that they always use devices that offer the best performance, reliability, design, and security capabilities (such as support for features like Windows Hello).</span></span> <span data-ttu-id="3cae9-106">为完成此操作，Microsoft 托管桌面维护了一个持续更新的已批准设备的 [简短目录](device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="3cae9-106">To accomplish this, Microsoft Managed Desktop maintains a short catalog of continuously updated [approved devices](device-list.md).</span></span> 
 
<span data-ttu-id="3cae9-107">本文详细介绍了在已批准目录中添加和删除设备时设备的生命周期。</span><span class="sxs-lookup"><span data-stu-id="3cae9-107">This article details the lifecycle of devices as they are added and removed from the approved catalog.</span></span> 

> [!NOTE]
> <span data-ttu-id="3cae9-108">在本主题中，我们将区分"设备"和"产品"。</span><span class="sxs-lookup"><span data-stu-id="3cae9-108">In this topic, we'll make a distinction between a "device" and a "product."</span></span> <span data-ttu-id="3cae9-109">通过"设备"，我们是指一台单独的特定计算机。</span><span class="sxs-lookup"><span data-stu-id="3cae9-109">By "device," we mean one individual, specific computer.</span></span> <span data-ttu-id="3cae9-110">例如，"序列号 1234"、"Bill's laptop"、"Shared VM XYZ"指特定设备。</span><span class="sxs-lookup"><span data-stu-id="3cae9-110">For example, "Serial number 1234", "Bill's laptop", "Shared VM XYZ" refer to specific devices.</span></span> <span data-ttu-id="3cae9-111">但是，"产品"是指设备的集合或系列。</span><span class="sxs-lookup"><span data-stu-id="3cae9-111">A "product", however, refers to a collection or family of devices.</span></span> <span data-ttu-id="3cae9-112">例如，"Fabrikam Laptop"、"Adatum ZX450 Laptop"等。这一点很重要，因为产品已添加到[](device-list.md)已批准列表或目录，设备是注册到 Microsoft 托管桌面的内容。</span><span class="sxs-lookup"><span data-stu-id="3cae9-112">For example, "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. This is important because products are added to our [approved list](device-list.md), or catalog, and devices are what get enrolled into Microsoft Managed Desktop.</span></span>

## <a name="product-lifecycle"></a><span data-ttu-id="3cae9-113">产品生命周期</span><span class="sxs-lookup"><span data-stu-id="3cae9-113">Product lifecycle</span></span>

 <span data-ttu-id="3cae9-114">通常，产品会经历以下生命周期阶段：</span><span class="sxs-lookup"><span data-stu-id="3cae9-114">Generally, products move through these lifecycle phases:</span></span>

- [<span data-ttu-id="3cae9-115">产品发布和评估</span><span class="sxs-lookup"><span data-stu-id="3cae9-115">Product release and evaluation</span></span>](#product-release-and-evaluation)
- [<span data-ttu-id="3cae9-116">产品主要可用性期</span><span class="sxs-lookup"><span data-stu-id="3cae9-116">Product primary availability period</span></span>](#product-primary-availability-period)
- [<span data-ttu-id="3cae9-117">产品宽限期</span><span class="sxs-lookup"><span data-stu-id="3cae9-117">Product grace period</span></span>](#product-grace-period)
- [<span data-ttu-id="3cae9-118">产品停用</span><span class="sxs-lookup"><span data-stu-id="3cae9-118">Product retirement</span></span>](#product-retirement)


<span data-ttu-id="3cae9-119">此图显示了整个序列：</span><span class="sxs-lookup"><span data-stu-id="3cae9-119">This illustration shows the entire sequence:</span></span>

![生命周期时间线：从产品常规可用性开始，"主要可用性"持续两年。](../../media/non-dark1-edits.PNG)

<span data-ttu-id="3cae9-125">产品在目录中最多保留 24 个月，但设备<em></em>根据个人注册日期在管理中保留三年。</span><span class="sxs-lookup"><span data-stu-id="3cae9-125">Products remain on the catalog for up to 24 months, but <em>devices</em> remain under management for three years based on their individual enrollment dates.</span></span> <span data-ttu-id="3cae9-126">实际上，每个产品都有三个重要日期，但每个设备只有一个。</span><span class="sxs-lookup"><span data-stu-id="3cae9-126">Effectively, each product has three important dates, but each device has only one.</span></span> <span data-ttu-id="3cae9-127">对于产品，所有这三个日期都是根据审批日期计算的，<em></em>因此我们在审批后发布这些日期，以便你可以始终向前看并针对产品的整个生命周期进行相应的规划。</span><span class="sxs-lookup"><span data-stu-id="3cae9-127">For products, all three of these dates are calculated based on the <em>approval date</em>, and therefore we publish these dates upon approval so that you can always look ahead and plan appropriately for the product's entire lifecycle.</span></span>

<span data-ttu-id="3cae9-128">下表显示了一个理论上产品的示例日期：</span><span class="sxs-lookup"><span data-stu-id="3cae9-128">This table shows example dates for a theoretical product:</span></span>


|<span data-ttu-id="3cae9-129">产品</span><span class="sxs-lookup"><span data-stu-id="3cae9-129">Product</span></span>  |<span data-ttu-id="3cae9-130">批准日期</span><span class="sxs-lookup"><span data-stu-id="3cae9-130">Approved date</span></span>  |<span data-ttu-id="3cae9-131">主可用性结束</span><span class="sxs-lookup"><span data-stu-id="3cae9-131">End of primary availability</span></span>  |<span data-ttu-id="3cae9-132">资格结束</span><span class="sxs-lookup"><span data-stu-id="3cae9-132">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="3cae9-133">Fabrikam Laptop</span><span class="sxs-lookup"><span data-stu-id="3cae9-133">Fabrikam Laptop</span></span>    | <span data-ttu-id="3cae9-134">1/1/2017</span><span class="sxs-lookup"><span data-stu-id="3cae9-134">1/1/2017</span></span> | <span data-ttu-id="3cae9-135">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="3cae9-135">6/1/2019</span></span> | <span data-ttu-id="3cae9-136">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="3cae9-136">6/1/2022</span></span> |
|<span data-ttu-id="3cae9-137">Adatum Laptop</span><span class="sxs-lookup"><span data-stu-id="3cae9-137">Adatum Laptop</span></span>   | <span data-ttu-id="3cae9-138">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="3cae9-138">1/1/2018</span></span> | <span data-ttu-id="3cae9-139">6/1/2020</span><span class="sxs-lookup"><span data-stu-id="3cae9-139">6/1/2020</span></span> | <span data-ttu-id="3cae9-140">6/1/2023</span><span class="sxs-lookup"><span data-stu-id="3cae9-140">6/1/2023</span></span>  |

<span data-ttu-id="3cae9-141">下表显示了理论上设备的示例 *日期*：</span><span class="sxs-lookup"><span data-stu-id="3cae9-141">This table shows example dates for theoretical *devices*:</span></span>


|<span data-ttu-id="3cae9-142">设备 ID</span><span class="sxs-lookup"><span data-stu-id="3cae9-142">Device ID</span></span>  |<span data-ttu-id="3cae9-143">注册日期</span><span class="sxs-lookup"><span data-stu-id="3cae9-143">Enrollment date</span></span>  |<span data-ttu-id="3cae9-144">停用日期</span><span class="sxs-lookup"><span data-stu-id="3cae9-144">Retirement date</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="3cae9-145">笔记本电脑#123412</span><span class="sxs-lookup"><span data-stu-id="3cae9-145">Laptop #123412</span></span>     |  <span data-ttu-id="3cae9-146">2/3/2018</span><span class="sxs-lookup"><span data-stu-id="3cae9-146">2/3/2018</span></span>       |  <span data-ttu-id="3cae9-147">2/3/2021</span><span class="sxs-lookup"><span data-stu-id="3cae9-147">2/3/2021</span></span>       |
|<span data-ttu-id="3cae9-148">桌面#321513</span><span class="sxs-lookup"><span data-stu-id="3cae9-148">Desktop #321513</span></span>     | <span data-ttu-id="3cae9-149">6/2/2018</span><span class="sxs-lookup"><span data-stu-id="3cae9-149">6/2/2018</span></span>        |  <span data-ttu-id="3cae9-150">6/2/2021</span><span class="sxs-lookup"><span data-stu-id="3cae9-150">6/2/2021</span></span>       |


## <a name="product-release-and-evaluation"></a><span data-ttu-id="3cae9-151">产品发布和评估</span><span class="sxs-lookup"><span data-stu-id="3cae9-151">Product release and evaluation</span></span>

<span data-ttu-id="3cae9-152">当制造商公开发布产品时，产品生命周期将开始：</span><span class="sxs-lookup"><span data-stu-id="3cae9-152">The product lifecycle starts when a manufacturer publicly releases the product:</span></span>

![显示发布和评估期的生命周期时间线](../../media/non-dark3-edits.PNG)

<span data-ttu-id="3cae9-154">在此阶段，Microsoft 托管桌面工程团队对产品进行评估和认证。</span><span class="sxs-lookup"><span data-stu-id="3cae9-154">During this stage, the Microsoft Managed Desktop engineering team does their evaluation and certification of a product.</span></span> <span data-ttu-id="3cae9-155">该团队对 Windows 的可靠性和性能、硬件基线的合规性、市场情绪、库存和频道准备情况等进行评估。</span><span class="sxs-lookup"><span data-stu-id="3cae9-155">The team evaluates things like reliability and performance with Windows, compliance with a hardware baseline, market sentiment, and inventory and channel readiness, among other things.</span></span> <span data-ttu-id="3cae9-156">此过程通常需要大约六周的时间。</span><span class="sxs-lookup"><span data-stu-id="3cae9-156">This process typically takes approximately six weeks.</span></span>
  
<span data-ttu-id="3cae9-157">Microsoft 托管桌面仅评估设备在其前六个月内的认证。</span><span class="sxs-lookup"><span data-stu-id="3cae9-157">Microsoft Managed Desktop will only evaluate devices for certification within their first six months of availability.</span></span> <span data-ttu-id="3cae9-158">此策略可确保我们始终专注于最新一代硬件。</span><span class="sxs-lookup"><span data-stu-id="3cae9-158">This policy ensures that we're always focusing our efforts on the latest generation of hardware.</span></span>
 
<span data-ttu-id="3cae9-159">在此阶段结束时，Microsoft 托管桌面将产品添加到已批准列表中，从而[](device-list.md)有效地发布用于客户注册的产品。</span><span class="sxs-lookup"><span data-stu-id="3cae9-159">At the end of this phase, Microsoft Managed Desktop adds the product to the [approved list](device-list.md), effectively releasing the product for customer enrollments.</span></span> <span data-ttu-id="3cae9-160">无论设备通过认证的日期如何，其批准日期都晚于产品自己的正式发布日期。</span><span class="sxs-lookup"><span data-stu-id="3cae9-160">Regardless of the date when a device is certified, its **approved date** is back-dated to the product's own general availability date.</span></span> 


## <a name="product-primary-availability-period"></a><span data-ttu-id="3cae9-161">产品主要可用性期</span><span class="sxs-lookup"><span data-stu-id="3cae9-161">Product primary availability period</span></span>

<span data-ttu-id="3cae9-162">此时段是产品可用性的核心：</span><span class="sxs-lookup"><span data-stu-id="3cae9-162">This period is the core of product availability:</span></span>

![显示主要可用性的生命周期时间线](../../media/non-dark4-edits.PNG)

<span data-ttu-id="3cae9-164">在此期间注册的任何设备都从 Microsoft 托管桌面设备 (为期三年的支持，如蓝色时间线) 。</span><span class="sxs-lookup"><span data-stu-id="3cae9-164">Any device enrolled during this period receives the full three years of support from Microsoft Managed Desktop (as shown by the blue timeline).</span></span> <span data-ttu-id="3cae9-165">此期间持续到从一般发布日期起设置为 24 个月的结束日期。</span><span class="sxs-lookup"><span data-stu-id="3cae9-165">This period lasts until an end date set to 24 months from the general availability date.</span></span>

<span data-ttu-id="3cae9-166">你可以将此阶段视为有效的"开放式注册"，因此，若要最大化 Microsoft 托管桌面的价值，应面向采购模型和所选产品，使其在此时段内实现。</span><span class="sxs-lookup"><span data-stu-id="3cae9-166">You can think of this period as effectively "open enrollment", so to maximize the value of Microsoft Managed Desktop, you should target your procurement models and selected products to fall within this period.</span></span> <span data-ttu-id="3cae9-167">作为一个小示例，应避免使用在其主要可用性的最后一个月的产品在两年推出周期中过度使用，大多数这些设备将不会收到为期三年的 Microsoft 托管桌面管理 (请参阅宽限期，了解) 。 [](#product-grace-period)</span><span class="sxs-lookup"><span data-stu-id="3cae9-167">As a small example, you should avoid settling on a two-year roll-out period using a product that is in its final month of primary availability – most of those devices will not receive the full three years of Microsoft Managed Desktop management (see [grace period](#product-grace-period) for more information).</span></span>  

## <a name="product-grace-period"></a><span data-ttu-id="3cae9-168">产品宽限期</span><span class="sxs-lookup"><span data-stu-id="3cae9-168">Product grace period</span></span>

<span data-ttu-id="3cae9-169">产品宽限期为主要可用性后三年。</span><span class="sxs-lookup"><span data-stu-id="3cae9-169">The product grace period is a three-year period following primary availability.</span></span> <span data-ttu-id="3cae9-170">此阶段允许你注册来自受支持产品系列的设备，但仍坚持遵守 Microsoft 托管桌面有关现代硬件和设备性能的承诺。</span><span class="sxs-lookup"><span data-stu-id="3cae9-170">This phase allows you to enroll devices that are from a supported product family, but still hold firm to the promises of Microsoft Managed Desktop regarding modern hardware and device performance.</span></span> <span data-ttu-id="3cae9-171">此阶段非常适合在了解 Microsoft 托管桌面之前做出采购决策的客户。</span><span class="sxs-lookup"><span data-stu-id="3cae9-171">This phase is ideal for customers who have made procurement decisions before knowing about Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="3cae9-172">如果你在注册 Microsoft 托管桌面之前最近购买了已批准的设备，你仍然可以注册它们，但你将不会获得为期三年的管理。</span><span class="sxs-lookup"><span data-stu-id="3cae9-172">If you've recently bought approved devices prior to enrolling with Microsoft Managed Desktop, you can still enroll them, but you won't receive a full three years of management.</span></span> <span data-ttu-id="3cae9-173">相反，他们将在停用日期不合规，无论他们何时注册。</span><span class="sxs-lookup"><span data-stu-id="3cae9-173">Instead, they'll fall out of compliance on the retirement date, regardless of when they were enrolled.</span></span> <span data-ttu-id="3cae9-174">在后台，Microsoft 托管桌面将这些设备视为在主要可用性的最后一天注册。</span><span class="sxs-lookup"><span data-stu-id="3cae9-174">Behind the scenes, Microsoft Managed Desktop will treat these devices as if they were enrolled on the last day of primary availability.</span></span> <span data-ttu-id="3cae9-175">在此图中，你可以注意，尽管蓝绿色设备在注册方面存在一年差异，但均在同一天结束，可以看到此方案：</span><span class="sxs-lookup"><span data-stu-id="3cae9-175">In this illustration, you can see this scenario by noting that both the blue and green device end on the same day, despite their one-year difference in enrollment:</span></span>


![显示宽限期的生命周期时间线](../../media/non-dark2-edits.PNG)

<span data-ttu-id="3cae9-177">上表中的 Fabrikam Laptop 示例说明了这种情况：</span><span class="sxs-lookup"><span data-stu-id="3cae9-177">The Fabrikam Laptop example from the previous table illustrates this situation:</span></span> 

|<span data-ttu-id="3cae9-178">产品</span><span class="sxs-lookup"><span data-stu-id="3cae9-178">Product</span></span>  |<span data-ttu-id="3cae9-179">批准日期</span><span class="sxs-lookup"><span data-stu-id="3cae9-179">Approved date</span></span>  |<span data-ttu-id="3cae9-180">主可用性结束</span><span class="sxs-lookup"><span data-stu-id="3cae9-180">End of primary availability</span></span>  |<span data-ttu-id="3cae9-181">资格结束</span><span class="sxs-lookup"><span data-stu-id="3cae9-181">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="3cae9-182">Fabrikam Laptop</span><span class="sxs-lookup"><span data-stu-id="3cae9-182">Fabrikam Laptop</span></span>    | <span data-ttu-id="3cae9-183">6/1/2017</span><span class="sxs-lookup"><span data-stu-id="3cae9-183">6/1/2017</span></span> | <span data-ttu-id="3cae9-184">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="3cae9-184">6/1/2019</span></span> | <span data-ttu-id="3cae9-185">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="3cae9-185">6/1/2022</span></span> |

<span data-ttu-id="3cae9-186">作为客户，你可以一直注册 Fabrikam 便携式计算机，直到 2022 年 6 月 1 日 ，但是它们将被视为在 2019 年 6 月 1 日注册。</span><span class="sxs-lookup"><span data-stu-id="3cae9-186">As a customer, you can enroll Fabrikam Laptops all the way until 6/1/2022 – however they will all be treated as though you enrolled them on 6/1/2019.</span></span> <span data-ttu-id="3cae9-187">如果在 2021 年 6 月 1 日注册 Fabrikam 便携式计算机，则只能获得一年的管理。</span><span class="sxs-lookup"><span data-stu-id="3cae9-187">If you enroll a Fabrikam Laptop on 6/1/2021, you'll only get one year of management.</span></span> <span data-ttu-id="3cae9-188">此策略允许你从以前支持的产品中提取部分生命周期，而不必提前购买新设备。</span><span class="sxs-lookup"><span data-stu-id="3cae9-188">This policy allows you to extract partial lifecycles from products that were previously supported, rather than having to procure new devices prematurely.</span></span> 

<span data-ttu-id="3cae9-189">最后，在此阶段，设备从设备 [列表中](device-list.md) 删除并移动到 [存档的设备列表](archived-device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="3cae9-189">Finally, during this phase the device is removed from the [device list](device-list.md) and moved to the [archived device list](archived-device-list.md).</span></span>


## <a name="product-retirement"></a><span data-ttu-id="3cae9-190">产品停用</span><span class="sxs-lookup"><span data-stu-id="3cae9-190">Product retirement</span></span>

<span data-ttu-id="3cae9-191">产品停用是生命周期的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="3cae9-191">Product retirement is the final phase of the lifecycle.</span></span> <span data-ttu-id="3cae9-192">在此阶段中，无法将该产品类型的新设备注册到 Microsoft 托管桌面，根据定义，所有现有设备现在都超出其允许的三年期限。</span><span class="sxs-lookup"><span data-stu-id="3cae9-192">In this phase, no new devices of that product type can be enrolled in Microsoft Managed Desktop and, by definition, all existing devices are now outside their allowed three-year term.</span></span> <span data-ttu-id="3cae9-193">在此期间，Microsoft 托管桌面将完全从公用列表中删除设备。</span><span class="sxs-lookup"><span data-stu-id="3cae9-193">During this time, Microsoft Managed Desktop will remove the device from the public list entirely.</span></span> <span data-ttu-id="3cae9-194">在这一阶段中，如果你尚未安装替换项，你将开始看到服务降低，因为 Microsoft 托管桌面开始在不符合要求的设备上逐渐降低。</span><span class="sxs-lookup"><span data-stu-id="3cae9-194">It's also during this phase where, if you haven't already procured replacements, you'll start to see diminished services as Microsoft Managed Desktop starts to ramp down on the devices that are out of compliance.</span></span> 

## <a name="devices-that-are-out-of-compliance"></a><span data-ttu-id="3cae9-195">不符合要求的设备</span><span class="sxs-lookup"><span data-stu-id="3cae9-195">Devices that are out of compliance</span></span>

<span data-ttu-id="3cae9-196">设备在经过 Microsoft 托管桌面管理的允许窗口后不符合要求。</span><span class="sxs-lookup"><span data-stu-id="3cae9-196">A device is out of compliance when its allowed window for Microsoft Managed Desktop management has elapsed.</span></span> <span data-ttu-id="3cae9-197">当设备管理时间达到三年或从设备目录中删除该产品类型（以先发生者为准）时，会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="3cae9-197">This situation occurs when the device has reached three years of management or when that product type is removed from the device catalog, whichever occurs first.</span></span> <span data-ttu-id="3cae9-198">应始终面向采购周期，这样在当前设备不符合要求之前部署新设备。</span><span class="sxs-lookup"><span data-stu-id="3cae9-198">You should always target your procurement cycles such that new devices are deployed prior to current devices going out of compliance.</span></span>

<span data-ttu-id="3cae9-199">Microsoft 托管桌面团队知道采购周期很长，并且围绕长期运行的预算进行规划。</span><span class="sxs-lookup"><span data-stu-id="3cae9-199">The Microsoft Managed Desktop team knows that procurement cycles are long and planned around long-running budgets.</span></span> <span data-ttu-id="3cae9-200">为了确保你始终了解设备总体的状态，我们提供了一个网站，其中列出了管理下的每台设备[](https://aka.ms/mmdportal)、设备使用时间以及指示其合规性的状态。</span><span class="sxs-lookup"><span data-stu-id="3cae9-200">To ensure that you're always aware of the state of your device population, we provide a [website](https://aka.ms/mmdportal) that lists every device under management, its age, and a status indicating its compliance.</span></span> <span data-ttu-id="3cae9-201">该网站可帮助你始终获得有关设备使用时间的最新信息，并可在任何采购规划周期中使用此报告。</span><span class="sxs-lookup"><span data-stu-id="3cae9-201">The website helps you always have the latest information regarding device age and can use the report in any procurement planning cycle.</span></span> 







