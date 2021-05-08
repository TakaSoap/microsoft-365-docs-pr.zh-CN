---
title: Microsoft 托管桌面产品生命周期
description: 本文列出了本文中使用的设备Microsoft 托管桌面。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a8b8abc58b82d08d004d204396cfd8e381c6303a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245308"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a><span data-ttu-id="79388-104">Microsoft 托管桌面产品生命周期</span><span class="sxs-lookup"><span data-stu-id="79388-104">Microsoft Managed Desktop product lifecycle</span></span>

<span data-ttu-id="79388-105">Microsoft 托管桌面使用户受益，因为他们始终使用提供最佳性能、可靠性、设计和安全功能的设备 (如支持 Windows Hello) 。</span><span class="sxs-lookup"><span data-stu-id="79388-105">Microsoft Managed Desktop benefits users assuring that they always use devices that offer the best performance, reliability, design, and security capabilities (such as support for features like Windows Hello).</span></span> <span data-ttu-id="79388-106">为实现这一Microsoft 托管桌面，需要维护一个持续更新的已批准设备的简短目录。</span><span class="sxs-lookup"><span data-stu-id="79388-106">To accomplish this, Microsoft Managed Desktop maintains a short catalog of continuously updated approved devices.</span></span> <span data-ttu-id="79388-107">可以通过在"购买商业Microsoft 托管桌面"网站上筛选Windows 10 专业版[批准的](https://www.microsoft.com/windowsforbusiness/view-all-devices)设备。</span><span class="sxs-lookup"><span data-stu-id="79388-107">You can view approved devices by filtering for Microsoft Managed Desktop on the [Shop Windows 10 Pro business devices](https://www.microsoft.com/windowsforbusiness/view-all-devices) site.</span></span>
 
<span data-ttu-id="79388-108">本文详细介绍了在已批准目录中添加和删除设备的生命周期。</span><span class="sxs-lookup"><span data-stu-id="79388-108">This article details the lifecycle of devices as they are added and removed from the approved catalog.</span></span> 

> [!NOTE]
> <span data-ttu-id="79388-109">在本主题中，我们将区分"设备"和"产品"。</span><span class="sxs-lookup"><span data-stu-id="79388-109">In this topic, we'll make a distinction between a "device" and a "product."</span></span> <span data-ttu-id="79388-110">通过"设备"，我们是指一台单独的特定计算机。</span><span class="sxs-lookup"><span data-stu-id="79388-110">By "device," we mean one individual, specific computer.</span></span> <span data-ttu-id="79388-111">例如，"序列号 1234"、"Bill's laptop"、"Shared VM XYZ"是指特定设备。</span><span class="sxs-lookup"><span data-stu-id="79388-111">For example, "Serial number 1234", "Bill's laptop", "Shared VM XYZ" refer to specific devices.</span></span> <span data-ttu-id="79388-112">但是，"产品"是指设备的集合或系列。</span><span class="sxs-lookup"><span data-stu-id="79388-112">A "product", however, refers to a collection or family of devices.</span></span> <span data-ttu-id="79388-113">例如，"Fabrikam Laptop"、"Adatum ZX450 Laptop"等。这一点很重要，因为产品已添加到已批准列表或目录，设备是注册到Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="79388-113">For example, "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. This is important because products are added to our approved list, or catalog, and devices are what get enrolled into Microsoft Managed Desktop.</span></span>

## <a name="product-lifecycle"></a><span data-ttu-id="79388-114">产品生命周期</span><span class="sxs-lookup"><span data-stu-id="79388-114">Product lifecycle</span></span>

 <span data-ttu-id="79388-115">通常，产品会经历以下生命周期阶段：</span><span class="sxs-lookup"><span data-stu-id="79388-115">Generally, products move through these lifecycle phases:</span></span>

- [<span data-ttu-id="79388-116">产品发布和评估</span><span class="sxs-lookup"><span data-stu-id="79388-116">Product release and evaluation</span></span>](#product-release-and-evaluation)
- [<span data-ttu-id="79388-117">产品主可用性周期</span><span class="sxs-lookup"><span data-stu-id="79388-117">Product primary availability period</span></span>](#product-primary-availability-period)
- [<span data-ttu-id="79388-118">产品宽限期</span><span class="sxs-lookup"><span data-stu-id="79388-118">Product grace period</span></span>](#product-grace-period)
- [<span data-ttu-id="79388-119">产品停用</span><span class="sxs-lookup"><span data-stu-id="79388-119">Product retirement</span></span>](#product-retirement)


<span data-ttu-id="79388-120">此图显示了整个序列：</span><span class="sxs-lookup"><span data-stu-id="79388-120">This illustration shows the entire sequence:</span></span>

![生命周期时间线：从产品常规可用性开始，"主要可用性"持续两年。](../../media/non-dark1-edits.PNG)

<span data-ttu-id="79388-126">产品在目录中保留最多 24 个月，但设备<em></em>根据个人注册日期将管理 3 年。</span><span class="sxs-lookup"><span data-stu-id="79388-126">Products remain on the catalog for up to 24 months, but <em>devices</em> remain under management for three years based on their individual enrollment dates.</span></span> <span data-ttu-id="79388-127">实际上，每个产品都有三个重要日期，但每个设备只有一个。</span><span class="sxs-lookup"><span data-stu-id="79388-127">Effectively, each product has three important dates, but each device has only one.</span></span> <span data-ttu-id="79388-128">对于产品，这三个日期都是基于审批日期计算的，<em></em>因此我们将在批准后发布这些日期，以便你可以始终向前看并针对产品的整个生命周期进行相应的规划。</span><span class="sxs-lookup"><span data-stu-id="79388-128">For products, all three of these dates are calculated based on the <em>approval date</em>, and therefore we publish these dates upon approval so that you can always look ahead and plan appropriately for the product's entire lifecycle.</span></span>

<span data-ttu-id="79388-129">此表显示了理论上产品的示例日期：</span><span class="sxs-lookup"><span data-stu-id="79388-129">This table shows example dates for a theoretical product:</span></span>


|<span data-ttu-id="79388-130">产品</span><span class="sxs-lookup"><span data-stu-id="79388-130">Product</span></span>  |<span data-ttu-id="79388-131">批准日期</span><span class="sxs-lookup"><span data-stu-id="79388-131">Approved date</span></span>  |<span data-ttu-id="79388-132">主可用性结束</span><span class="sxs-lookup"><span data-stu-id="79388-132">End of primary availability</span></span>  |<span data-ttu-id="79388-133">资格结束</span><span class="sxs-lookup"><span data-stu-id="79388-133">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="79388-134">Fabrikam Laptop</span><span class="sxs-lookup"><span data-stu-id="79388-134">Fabrikam Laptop</span></span>    | <span data-ttu-id="79388-135">1/1/2017</span><span class="sxs-lookup"><span data-stu-id="79388-135">1/1/2017</span></span> | <span data-ttu-id="79388-136">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="79388-136">6/1/2019</span></span> | <span data-ttu-id="79388-137">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="79388-137">6/1/2022</span></span> |
|<span data-ttu-id="79388-138">Adatum Laptop</span><span class="sxs-lookup"><span data-stu-id="79388-138">Adatum Laptop</span></span>   | <span data-ttu-id="79388-139">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="79388-139">1/1/2018</span></span> | <span data-ttu-id="79388-140">6/1/2020</span><span class="sxs-lookup"><span data-stu-id="79388-140">6/1/2020</span></span> | <span data-ttu-id="79388-141">6/1/2023</span><span class="sxs-lookup"><span data-stu-id="79388-141">6/1/2023</span></span>  |

<span data-ttu-id="79388-142">此表显示了理论上设备 *的示例日期*：</span><span class="sxs-lookup"><span data-stu-id="79388-142">This table shows example dates for theoretical *devices*:</span></span>


|<span data-ttu-id="79388-143">设备 ID</span><span class="sxs-lookup"><span data-stu-id="79388-143">Device ID</span></span>  |<span data-ttu-id="79388-144">注册日期</span><span class="sxs-lookup"><span data-stu-id="79388-144">Enrollment date</span></span>  |<span data-ttu-id="79388-145">停用日期</span><span class="sxs-lookup"><span data-stu-id="79388-145">Retirement date</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="79388-146">笔记本电脑#123412</span><span class="sxs-lookup"><span data-stu-id="79388-146">Laptop #123412</span></span>     |  <span data-ttu-id="79388-147">2/3/2018</span><span class="sxs-lookup"><span data-stu-id="79388-147">2/3/2018</span></span>       |  <span data-ttu-id="79388-148">2/3/2021</span><span class="sxs-lookup"><span data-stu-id="79388-148">2/3/2021</span></span>       |
|<span data-ttu-id="79388-149">桌面#321513</span><span class="sxs-lookup"><span data-stu-id="79388-149">Desktop #321513</span></span>     | <span data-ttu-id="79388-150">6/2/2018</span><span class="sxs-lookup"><span data-stu-id="79388-150">6/2/2018</span></span>        |  <span data-ttu-id="79388-151">6/2/2021</span><span class="sxs-lookup"><span data-stu-id="79388-151">6/2/2021</span></span>       |


## <a name="product-release-and-evaluation"></a><span data-ttu-id="79388-152">产品发布和评估</span><span class="sxs-lookup"><span data-stu-id="79388-152">Product release and evaluation</span></span>

<span data-ttu-id="79388-153">当制造商公开发布产品时，产品生命周期将开始：</span><span class="sxs-lookup"><span data-stu-id="79388-153">The product lifecycle starts when a manufacturer publicly releases the product:</span></span>

![显示发布和评估期的生命周期时间线](../../media/non-dark3-edits.PNG)

<span data-ttu-id="79388-155">在此阶段，Microsoft 托管桌面团队对产品进行评估和认证。</span><span class="sxs-lookup"><span data-stu-id="79388-155">During this stage, the Microsoft Managed Desktop engineering team does their evaluation and certification of a product.</span></span> <span data-ttu-id="79388-156">该团队评估产品的可靠性和性能Windows、硬件基线的合规性、市场情绪以及库存和渠道准备情况等。</span><span class="sxs-lookup"><span data-stu-id="79388-156">The team evaluates things like reliability and performance with Windows, compliance with a hardware baseline, market sentiment, and inventory and channel readiness, among other things.</span></span> <span data-ttu-id="79388-157">此过程通常需要大约六周的时间。</span><span class="sxs-lookup"><span data-stu-id="79388-157">This process typically takes approximately six weeks.</span></span>
  
<span data-ttu-id="79388-158">Microsoft 托管桌面将仅评估设备在其前六个月内是否获得认证。</span><span class="sxs-lookup"><span data-stu-id="79388-158">Microsoft Managed Desktop will only evaluate devices for certification within their first six months of availability.</span></span> <span data-ttu-id="79388-159">此策略可确保我们始终专注于最新一代的硬件。</span><span class="sxs-lookup"><span data-stu-id="79388-159">This policy ensures that we're always focusing our efforts on the latest generation of hardware.</span></span>
 
<span data-ttu-id="79388-160">在此阶段结束时，Microsoft 托管桌面产品添加到已批准列表中，从而有效地发布产品进行客户[](device-list.md)注册。</span><span class="sxs-lookup"><span data-stu-id="79388-160">At the end of this phase, Microsoft Managed Desktop adds the product to the [approved list](device-list.md), effectively releasing the product for customer enrollments.</span></span> <span data-ttu-id="79388-161">无论设备经过认证的日期如何，其批准日期都晚于产品自己的正式发布日期。</span><span class="sxs-lookup"><span data-stu-id="79388-161">Regardless of the date when a device is certified, its **approved date** is back-dated to the product's own general availability date.</span></span> 


## <a name="product-primary-availability-period"></a><span data-ttu-id="79388-162">产品主可用性周期</span><span class="sxs-lookup"><span data-stu-id="79388-162">Product primary availability period</span></span>

<span data-ttu-id="79388-163">此时段是产品可用性的核心：</span><span class="sxs-lookup"><span data-stu-id="79388-163">This period is the core of product availability:</span></span>

![显示主要可用性的生命周期时间线](../../media/non-dark4-edits.PNG)

<span data-ttu-id="79388-165">在此期间注册的任何设备都从 Microsoft 托管桌面 (收到完整三年的支持，如蓝色时间线) 。</span><span class="sxs-lookup"><span data-stu-id="79388-165">Any device enrolled during this period receives the full three years of support from Microsoft Managed Desktop (as shown by the blue timeline).</span></span> <span data-ttu-id="79388-166">此期间持续到从一般发布日期起设置为 24 个月的结束日期。</span><span class="sxs-lookup"><span data-stu-id="79388-166">This period lasts until an end date set to 24 months from the general availability date.</span></span>

<span data-ttu-id="79388-167">你可以将此阶段视为有效的"开放注册"，因此，若要最大限度地提高 Microsoft 托管桌面，您应该将采购模型和所选产品作为目标，使其适合此期间。</span><span class="sxs-lookup"><span data-stu-id="79388-167">You can think of this period as effectively "open enrollment", so to maximize the value of Microsoft Managed Desktop, you should target your procurement models and selected products to fall within this period.</span></span> <span data-ttu-id="79388-168">作为一个小示例，应避免使用在其最终主要可用性的最后一个月的产品在两年推出期间进行购买 - 其中大多数设备将不会收到 Microsoft 托管桌面 管理的完整三年 (请参阅宽限期，了解) 。 [](#product-grace-period)</span><span class="sxs-lookup"><span data-stu-id="79388-168">As a small example, you should avoid settling on a two-year roll-out period using a product that is in its final month of primary availability – most of those devices will not receive the full three years of Microsoft Managed Desktop management (see [grace period](#product-grace-period) for more information).</span></span>  

## <a name="product-grace-period"></a><span data-ttu-id="79388-169">产品宽限期</span><span class="sxs-lookup"><span data-stu-id="79388-169">Product grace period</span></span>

<span data-ttu-id="79388-170">产品宽限期为主要可用性后三年。</span><span class="sxs-lookup"><span data-stu-id="79388-170">The product grace period is a three-year period following primary availability.</span></span> <span data-ttu-id="79388-171">通过此阶段，你可以注册来自受支持产品系列的设备，但仍承诺承诺Microsoft 托管桌面现代硬件和设备性能。</span><span class="sxs-lookup"><span data-stu-id="79388-171">This phase allows you to enroll devices that are from a supported product family, but still hold firm to the promises of Microsoft Managed Desktop regarding modern hardware and device performance.</span></span> <span data-ttu-id="79388-172">此阶段非常适合在了解采购计划之前做出采购Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="79388-172">This phase is ideal for customers who have made procurement decisions before knowing about Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="79388-173">如果你最近在注册 Microsoft 托管桌面 之前购买了已批准的设备，你仍然可以注册它们，但你将不会获得为期三年的管理。</span><span class="sxs-lookup"><span data-stu-id="79388-173">If you've recently bought approved devices prior to enrolling with Microsoft Managed Desktop, you can still enroll them, but you won't receive a full three years of management.</span></span> <span data-ttu-id="79388-174">相反，他们将在停用日期不合规，无论他们何时注册。</span><span class="sxs-lookup"><span data-stu-id="79388-174">Instead, they'll fall out of compliance on the retirement date, regardless of when they were enrolled.</span></span> <span data-ttu-id="79388-175">在后台，Microsoft 托管桌面将这些设备视为在主要可用性的最后一天注册。</span><span class="sxs-lookup"><span data-stu-id="79388-175">Behind the scenes, Microsoft Managed Desktop will treat these devices as if they were enrolled on the last day of primary availability.</span></span> <span data-ttu-id="79388-176">在此图中，你可以注意蓝色和绿色设备在同一天结束，尽管它们注册的年差为一年，但你可以查看此方案：</span><span class="sxs-lookup"><span data-stu-id="79388-176">In this illustration, you can see this scenario by noting that both the blue and green device end on the same day, despite their one-year difference in enrollment:</span></span>


![显示宽限期的生命周期时间线](../../media/non-dark2-edits.PNG)

<span data-ttu-id="79388-178">上表中的 Fabrikam Laptop 示例说明了这种情况：</span><span class="sxs-lookup"><span data-stu-id="79388-178">The Fabrikam Laptop example from the previous table illustrates this situation:</span></span> 

|<span data-ttu-id="79388-179">产品</span><span class="sxs-lookup"><span data-stu-id="79388-179">Product</span></span>  |<span data-ttu-id="79388-180">批准日期</span><span class="sxs-lookup"><span data-stu-id="79388-180">Approved date</span></span>  |<span data-ttu-id="79388-181">主可用性结束</span><span class="sxs-lookup"><span data-stu-id="79388-181">End of primary availability</span></span>  |<span data-ttu-id="79388-182">资格结束</span><span class="sxs-lookup"><span data-stu-id="79388-182">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="79388-183">Fabrikam Laptop</span><span class="sxs-lookup"><span data-stu-id="79388-183">Fabrikam Laptop</span></span>    | <span data-ttu-id="79388-184">6/1/2017</span><span class="sxs-lookup"><span data-stu-id="79388-184">6/1/2017</span></span> | <span data-ttu-id="79388-185">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="79388-185">6/1/2019</span></span> | <span data-ttu-id="79388-186">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="79388-186">6/1/2022</span></span> |

<span data-ttu-id="79388-187">作为客户，您可以在 2022 年 6 月 1 日至 2022 年 6 月 1 日一直注册 Fabrikam 便携式计算机，但是它们将被视为在 2019 年 6 月 1 日注册。</span><span class="sxs-lookup"><span data-stu-id="79388-187">As a customer, you can enroll Fabrikam Laptops all the way until 6/1/2022 – however they will all be treated as though you enrolled them on 6/1/2019.</span></span> <span data-ttu-id="79388-188">如果你在 2021 年 6 月 1 日注册 Fabrikam Laptop，则只能获得一年的管理。</span><span class="sxs-lookup"><span data-stu-id="79388-188">If you enroll a Fabrikam Laptop on 6/1/2021, you'll only get one year of management.</span></span> <span data-ttu-id="79388-189">此策略允许你从以前支持的产品中提取部分生命周期，而不必提前购买新设备。</span><span class="sxs-lookup"><span data-stu-id="79388-189">This policy allows you to extract partial lifecycles from products that were previously supported, rather than having to procure new devices prematurely.</span></span> 

<span data-ttu-id="79388-190">最后，在此阶段中，设备从 [设备列表中删除](device-list.md) 并移动到 [存档的设备列表](archived-device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="79388-190">Finally, during this phase the device is removed from the [device list](device-list.md) and moved to the [archived device list](archived-device-list.md).</span></span>


## <a name="product-retirement"></a><span data-ttu-id="79388-191">产品停用</span><span class="sxs-lookup"><span data-stu-id="79388-191">Product retirement</span></span>

<span data-ttu-id="79388-192">产品停用是生命周期的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="79388-192">Product retirement is the final phase of the lifecycle.</span></span> <span data-ttu-id="79388-193">在此阶段，该产品类型的新设备无法注册到 Microsoft 托管桌面并且根据定义，所有现有设备现在都超出其允许的三年期限。</span><span class="sxs-lookup"><span data-stu-id="79388-193">In this phase, no new devices of that product type can be enrolled in Microsoft Managed Desktop and, by definition, all existing devices are now outside their allowed three-year term.</span></span> <span data-ttu-id="79388-194">在此期间，Microsoft 托管桌面将设备从公用列表中完全删除。</span><span class="sxs-lookup"><span data-stu-id="79388-194">During this time, Microsoft Managed Desktop will remove the device from the public list entirely.</span></span> <span data-ttu-id="79388-195">在这一阶段中，如果尚未准备替换，随着 Microsoft 托管桌面 开始在不符合要求的设备上逐渐降低，你将开始看到服务降低。</span><span class="sxs-lookup"><span data-stu-id="79388-195">It's also during this phase where, if you haven't already procured replacements, you'll start to see diminished services as Microsoft Managed Desktop starts to ramp down on the devices that are out of compliance.</span></span> 

## <a name="devices-that-are-out-of-compliance"></a><span data-ttu-id="79388-196">不符合要求的设备</span><span class="sxs-lookup"><span data-stu-id="79388-196">Devices that are out of compliance</span></span>

<span data-ttu-id="79388-197">设备在经过允许的用于管理Microsoft 托管桌面不符合要求。</span><span class="sxs-lookup"><span data-stu-id="79388-197">A device is out of compliance when its allowed window for Microsoft Managed Desktop management has elapsed.</span></span> <span data-ttu-id="79388-198">当设备管理时间达到三年或者从设备目录中删除该产品类型（以先发生者为准）时，会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="79388-198">This situation occurs when the device has reached three years of management or when that product type is removed from the device catalog, whichever occurs first.</span></span> <span data-ttu-id="79388-199">你应始终面向采购周期，这样在当前设备不符合要求之前部署新设备。</span><span class="sxs-lookup"><span data-stu-id="79388-199">You should always target your procurement cycles such that new devices are deployed prior to current devices going out of compliance.</span></span>

<span data-ttu-id="79388-200">工作组Microsoft 托管桌面知道采购周期很长，并且围绕长期运行的预算进行规划。</span><span class="sxs-lookup"><span data-stu-id="79388-200">The Microsoft Managed Desktop team knows that procurement cycles are long and planned around long-running budgets.</span></span> <span data-ttu-id="79388-201">为了确保你始终了解设备总体的状态，我们提供了一个网站，其中列出了管理中的每个设备[](https://aka.ms/mmdportal)、设备使用时间以及指示其合规性的状态。</span><span class="sxs-lookup"><span data-stu-id="79388-201">To ensure that you're always aware of the state of your device population, we provide a [website](https://aka.ms/mmdportal) that lists every device under management, its age, and a status indicating its compliance.</span></span> <span data-ttu-id="79388-202">该网站可帮助你始终获得有关设备使用时间的最新信息，并可在任何采购规划周期中使用此报告。</span><span class="sxs-lookup"><span data-stu-id="79388-202">The website helps you always have the latest information regarding device age and can use the report in any procurement planning cycle.</span></span> 







