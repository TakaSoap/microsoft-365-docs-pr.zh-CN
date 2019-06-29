---
title: Microsoft 托管桌面产品生命周期
description: 本主题列出了 Microsoft 托管桌面中使用的设备规格。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 88abd7bd8b2b4a9af37a1daf5579ac6268a9f927
ms.sourcegitcommit: e5aa684dab9b4dbe92002d31e69e7225bd8f95a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "35348861"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a><span data-ttu-id="ce6b9-104">Microsoft 托管桌面产品生命周期</span><span class="sxs-lookup"><span data-stu-id="ce6b9-104">Microsoft Managed Desktop product lifecycle</span></span>

<span data-ttu-id="ce6b9-105">Microsoft 托管桌面优势最终用户确保他们始终使用提供最佳性能、可靠性、设计和安全功能的设备 (例如, 支持 Windows Hello 等功能)。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-105">Microsoft Managed Desktop benefits end-users assuring that they always use devices that offer the best performance, reliability, design, and security capabilities (such as support for features like Windows Hello).</span></span> <span data-ttu-id="ce6b9-106">为实现此目的, Microsoft 托管桌面维护了连续更新的[经过审批的设备](device-list.md)的简短目录。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-106">To accomplish this, Microsoft Managed Desktop maintains a short catalog of continuously updated [approved devices](device-list.md).</span></span> 
 
<span data-ttu-id="ce6b9-107">本主题详细介绍了设备在被批准的目录中添加和删除时的生命周期。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-107">This topic details the lifecycle of devices as they are added and removed from the approved catalog.</span></span> 

> [!NOTE]
> <span data-ttu-id="ce6b9-108">在本主题中, 我们将对 "设备" 和 "产品" 进行区分。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-108">In this topic, we'll make a distinction between a "device" and a "product."</span></span> <span data-ttu-id="ce6b9-109">"设备" 是指一个单独的特定计算机。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-109">By “device,” we mean one individual, specific computer.</span></span> <span data-ttu-id="ce6b9-110">例如, "序列号 1234", "帐单的膝上型电脑", "共享 VM XYZ" 指的是特定设备。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-110">For example, “Serial number 1234”, “Bill’s laptop”, “Shared VM XYZ” refer to specific devices.</span></span> <span data-ttu-id="ce6b9-111">但是, "product" 指的是集合或设备系列。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-111">A “product”, however, refers to a collection or family of devices.</span></span> <span data-ttu-id="ce6b9-112">例如, "Fabrikam 便携式电脑"、"Adatum ZX450 膝上型电脑" 等。这一点很重要, 因为产品将添加到我们的[已批准列表](device-list.md)或目录中, 并且设备是注册到 Microsoft 托管桌面的内容。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-112">For example, “Fabrikam Laptop”, “Adatum ZX450 Laptop”, etc. This is important because products are added to our [approved list](device-list.md), or catalog, and devices are what get enrolled into Microsoft Managed Desktop.</span></span>

## <a name="product-lifecycle"></a><span data-ttu-id="ce6b9-113">产品生命周期</span><span class="sxs-lookup"><span data-stu-id="ce6b9-113">Product lifecycle</span></span>

 <span data-ttu-id="ce6b9-114">通常情况下, 产品将经历以下这些生命周期阶段:</span><span class="sxs-lookup"><span data-stu-id="ce6b9-114">Generally, products move through these lifecycle phases:</span></span>

- [<span data-ttu-id="ce6b9-115">产品发布和评估</span><span class="sxs-lookup"><span data-stu-id="ce6b9-115">Product release and evaluation</span></span>](#product-release-and-evaluation)
- [<span data-ttu-id="ce6b9-116">产品主可用性周期</span><span class="sxs-lookup"><span data-stu-id="ce6b9-116">Product primary availability period</span></span>](#product-primary-availability-period)
- [<span data-ttu-id="ce6b9-117">产品宽限期</span><span class="sxs-lookup"><span data-stu-id="ce6b9-117">Product grace period</span></span>](#product-grace-period)
- [<span data-ttu-id="ce6b9-118">产品退休</span><span class="sxs-lookup"><span data-stu-id="ce6b9-118">Product retirement</span></span>](#product-retirement)


<span data-ttu-id="ce6b9-119">本图中描述了整个序列:</span><span class="sxs-lookup"><span data-stu-id="ce6b9-119">The entire sequence is depicted in this illustration:</span></span>

![生命周期日程表](images/non-dark1-edits.PNG)

<span data-ttu-id="ce6b9-121">产品保留在最多24个月的目录中, 但*设备*在管理下的时间将根据其各自的注册日期保留3年。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-121">Products remain on the catalog for up to 24 months, but *devices* remain under management for 3 years based on their individual enrollment dates.</span></span> <span data-ttu-id="ce6b9-122">实际上, 每个产品都有三个重要日期, 但每个设备只有一个。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-122">Effectively, each product has three important dates, but each device has only one.</span></span> <span data-ttu-id="ce6b9-123">对于产品, 这三个日期都是根据*审批日期*计算得出的, 因此, 我们会在批准时发布这些日期, 以便您始终能够提前查看并规划产品的整个生命周期。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-123">For products, all three of these dates are calculated based on the *approval date*, and therefore we publish these dates upon approval so that you can always look ahead and plan appropriately for the product's entire lifecycle.</span></span>

<span data-ttu-id="ce6b9-124">此表显示理论产品的示例日期:</span><span class="sxs-lookup"><span data-stu-id="ce6b9-124">This table shows example dates for a theoretical product:</span></span>


|<span data-ttu-id="ce6b9-125">产品</span><span class="sxs-lookup"><span data-stu-id="ce6b9-125">Product</span></span>  |<span data-ttu-id="ce6b9-126">批准日期</span><span class="sxs-lookup"><span data-stu-id="ce6b9-126">Approved date</span></span>  |<span data-ttu-id="ce6b9-127">主可用性结束</span><span class="sxs-lookup"><span data-stu-id="ce6b9-127">End of primary availability</span></span>  |<span data-ttu-id="ce6b9-128">Eligiblity 的结尾</span><span class="sxs-lookup"><span data-stu-id="ce6b9-128">End of eligiblity</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="ce6b9-129">Fabrikam 便携式计算机</span><span class="sxs-lookup"><span data-stu-id="ce6b9-129">Fabrikam Laptop</span></span>    | <span data-ttu-id="ce6b9-130">1/1/2017</span><span class="sxs-lookup"><span data-stu-id="ce6b9-130">1/1/2017</span></span> | <span data-ttu-id="ce6b9-131">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="ce6b9-131">6/1/2019</span></span> | <span data-ttu-id="ce6b9-132">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="ce6b9-132">6/1/2022</span></span> |
|<span data-ttu-id="ce6b9-133">Adatum 便携式计算机</span><span class="sxs-lookup"><span data-stu-id="ce6b9-133">Adatum Laptop</span></span>   | <span data-ttu-id="ce6b9-134">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="ce6b9-134">1/1/2018</span></span> | <span data-ttu-id="ce6b9-135">6/1/2020</span><span class="sxs-lookup"><span data-stu-id="ce6b9-135">6/1/2020</span></span> | <span data-ttu-id="ce6b9-136">6/1/2023</span><span class="sxs-lookup"><span data-stu-id="ce6b9-136">6/1/2023</span></span>  |

<span data-ttu-id="ce6b9-137">此表显示理论*设备*的示例日期:</span><span class="sxs-lookup"><span data-stu-id="ce6b9-137">This table shows example dates for theoretical *devices*:</span></span>


|<span data-ttu-id="ce6b9-138">设备 ID</span><span class="sxs-lookup"><span data-stu-id="ce6b9-138">Device ID</span></span>  |<span data-ttu-id="ce6b9-139">注册日期</span><span class="sxs-lookup"><span data-stu-id="ce6b9-139">Enrollment date</span></span>  |<span data-ttu-id="ce6b9-140">退休日期</span><span class="sxs-lookup"><span data-stu-id="ce6b9-140">Retirement date</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ce6b9-141">便携式 #123412</span><span class="sxs-lookup"><span data-stu-id="ce6b9-141">Laptop #123412</span></span>     |  <span data-ttu-id="ce6b9-142">2/3/2018</span><span class="sxs-lookup"><span data-stu-id="ce6b9-142">2/3/2018</span></span>       |  <span data-ttu-id="ce6b9-143">2/3/2021</span><span class="sxs-lookup"><span data-stu-id="ce6b9-143">2/3/2021</span></span>       |
|<span data-ttu-id="ce6b9-144">桌面 #321513</span><span class="sxs-lookup"><span data-stu-id="ce6b9-144">Desktop #321513</span></span>     | <span data-ttu-id="ce6b9-145">6/2/2018</span><span class="sxs-lookup"><span data-stu-id="ce6b9-145">6/2/2018</span></span>        |  <span data-ttu-id="ce6b9-146">6/2/2021</span><span class="sxs-lookup"><span data-stu-id="ce6b9-146">6/2/2021</span></span>       |


## <a name="product-release-and-evaluation"></a><span data-ttu-id="ce6b9-147">产品发布和评估</span><span class="sxs-lookup"><span data-stu-id="ce6b9-147">Product release and evaluation</span></span>

<span data-ttu-id="ce6b9-148">产品生命周期在制造商公开发布产品时启动:</span><span class="sxs-lookup"><span data-stu-id="ce6b9-148">The product lifecycle starts when a manufacturer publicly releases the product:</span></span>

![显示发布和评估期的生命周期时间线](images/non-dark3-edits.PNG)

<span data-ttu-id="ce6b9-150">在此阶段中, Microsoft 托管桌面工程团队将对产品进行评估和认证。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-150">During this stage, the Microsoft Managed Desktop engineering team does their evaluation and certification of a product.</span></span> <span data-ttu-id="ce6b9-151">团队使用 Windows、市场看法、库存和通道准备情况评估诸如可靠性和性能等方面的内容, 以及其他一些内容。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-151">The team evaluates things like reliability and performance with Windows, compliance with a hardware baseline, market sentiment, and inventory and channel readiness, among other things.</span></span> <span data-ttu-id="ce6b9-152">此过程通常大约需要6周。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-152">This process typically takes approximately 6 weeks.</span></span>
  
<span data-ttu-id="ce6b9-153">Microsoft 托管桌面将仅在其前6个月的可用性范围内评估用于认证的设备。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-153">Microsoft Managed Desktop will only evaluate devices for certification within their first 6 months of availability.</span></span> <span data-ttu-id="ce6b9-154">这可确保我们始终将精力集中在最新一代的硬件上。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-154">This ensures that we’re always focusing our efforts on the latest generation of hardware.</span></span>
 
<span data-ttu-id="ce6b9-155">在此阶段结束时, Microsoft 托管桌面将产品添加到[已批准的列表](device-list.md)中, 并有效地发布产品以供客户注册。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-155">At the end of this phase, Microsoft Managed Desktop adds the product to the [approved list](device-list.md), effectively releasing the product for customer enrollments.</span></span> <span data-ttu-id="ce6b9-156">无论设备经过认证的日期如何, 其批准的**日期**都将追溯到产品本身的常规可用性日期。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-156">Regardless of the date when a device is certified, its **approved date** is be back-dated to the products own general availability date.</span></span> 


## <a name="product-primary-availability-period"></a><span data-ttu-id="ce6b9-157">产品主可用性周期</span><span class="sxs-lookup"><span data-stu-id="ce6b9-157">Product primary availability period</span></span>

<span data-ttu-id="ce6b9-158">此时间段是产品可用性的核心:</span><span class="sxs-lookup"><span data-stu-id="ce6b9-158">This period is the core of product availability:</span></span>

![显示主要 availibility 的生命周期日程表](images/non-dark4-edits.PNG)

<span data-ttu-id="ce6b9-160">在此期间内注册的任何设备都将从 Microsoft 托管桌面接收全部三年的支持 (如蓝色时间线所示)。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-160">Any device enrolled during this period receives the full three years of support from Microsoft Managed Desktop (as shown by the blue timeline).</span></span> <span data-ttu-id="ce6b9-161">此时段一直持续到结束日期设置为从一般可用性日期起的24个月。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-161">This period lasts until an end date set to 24 months from the general availability date.</span></span>

<span data-ttu-id="ce6b9-162">你可以将此期间视为有效的 "打开注册", 因此, 要最大限度地提高 Microsoft 托管桌面的价值, 应瞄准你的采购模型和所选的产品在此时间段内。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-162">You can think of this period as effectively “open enrollment”, so to maximize the value of Microsoft Managed Desktop, you should target your procurement models and selected products to fall within this period.</span></span> <span data-ttu-id="ce6b9-163">举例来说, 客户应避免使用主可用性的最后一个月的产品结算两年期滚动期–大多数设备不会收到全部三年的 Microsoft 托管桌面管理 (请参阅[宽限期时间段](#product-grace-period), 了解详细信息)。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-163">As a small example, a customer should avoid settling on a two-year roll-out period using a product that is in its final month of primary availability – most of those devices will not receive the full three years of Microsoft Managed Desktop management (see [grace period](#product-grace-period) for more information).</span></span>  

## <a name="product-grace-period"></a><span data-ttu-id="ce6b9-164">产品宽限期</span><span class="sxs-lookup"><span data-stu-id="ce6b9-164">Product grace period</span></span>

<span data-ttu-id="ce6b9-165">产品宽限期是一个三年期的主可用性。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-165">The product grace period is a three-year period following primary availability.</span></span> <span data-ttu-id="ce6b9-166">此阶段允许你注册来自受支持的产品系列的设备, 但仍将公司保留为 Microsoft 托管桌面对新式硬件和设备性能的承诺。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-166">This phase allows you to enroll devices that are from a supported product family, but still hold firm to the promises of Microsoft Managed Desktop regarding modern hardware and device performance.</span></span> <span data-ttu-id="ce6b9-167">此阶段非常适合于在了解 Microsoft 托管桌面之前做出了采购决策的客户。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-167">This phase is ideal for customers who have made procurement decisions before knowing about Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="ce6b9-168">如果你最近在注册 Microsoft 托管桌面之前购买了大量经批准的设备, 你仍然可以注册, 但你将不会收到全部三年的管理。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-168">If you've recently bought a number of approved devices prior to enrolling with Microsoft Managed Desktop, you can still enroll them, but you won’t receive a full three years of management.</span></span> <span data-ttu-id="ce6b9-169">相反, 它们将因退休日期而不符合要求, 无论他们何时注册都是如此。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-169">Instead, they’ll fall out of compliance on the retirement date, regardless of when they were enrolled.</span></span> <span data-ttu-id="ce6b9-170">在幕后, Microsoft 托管桌面会将这些设备视为在主可用性的最后一天进行了注册。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-170">Behind the scenes, Microsoft Managed Desktop will treat these devices as if they were enrolled on the last day of primary availability.</span></span> <span data-ttu-id="ce6b9-171">在此图中, 你可以通过注意蓝色和绿色设备在同一天结束, 而不考虑其在注册中的年差异, 来查看这一方案:</span><span class="sxs-lookup"><span data-stu-id="ce6b9-171">In this illustration, you can see this scenario by noting that both the blue and green device end on the same day, despite their one-year difference in enrollment:</span></span>


![显示宽限期的生命周期时间线](images/non-dark2-edits.PNG)

<span data-ttu-id="ce6b9-173">上表中的 Fabrikam 便携式计算机示例说明了这种情况:</span><span class="sxs-lookup"><span data-stu-id="ce6b9-173">The Fabrikam Laptop example from the previous table illustrates this situation:</span></span> 

|<span data-ttu-id="ce6b9-174">产品</span><span class="sxs-lookup"><span data-stu-id="ce6b9-174">Product</span></span>  |<span data-ttu-id="ce6b9-175">批准日期</span><span class="sxs-lookup"><span data-stu-id="ce6b9-175">Approved date</span></span>  |<span data-ttu-id="ce6b9-176">主可用性结束</span><span class="sxs-lookup"><span data-stu-id="ce6b9-176">End of primary availability</span></span>  |<span data-ttu-id="ce6b9-177">Eligiblity 的结尾</span><span class="sxs-lookup"><span data-stu-id="ce6b9-177">End of eligiblity</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="ce6b9-178">Fabrikam 便携式计算机</span><span class="sxs-lookup"><span data-stu-id="ce6b9-178">Fabrikam Laptop</span></span>    | <span data-ttu-id="ce6b9-179">6/1/2017</span><span class="sxs-lookup"><span data-stu-id="ce6b9-179">6/1/2017</span></span> | <span data-ttu-id="ce6b9-180">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="ce6b9-180">6/1/2019</span></span> | <span data-ttu-id="ce6b9-181">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="ce6b9-181">6/1/2022</span></span> |

<span data-ttu-id="ce6b9-182">作为一项客户, 您可以在6/1/2022 之前注册 Fabrikam 笔记本电脑, 但这些笔记本都将被视为在6/1/2019 上注册。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-182">As a customer, you can enroll Fabrikam Laptops all the way until 6/1/2022 – however they will all be treated as though you enrolled them on 6/1/2019.</span></span> <span data-ttu-id="ce6b9-183">如果你在6/1/2021 上注册 Fabrikam 的便携式电脑, 你将仅获得一年的管理。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-183">If you enroll a Fabrikam Laptop on 6/1/2021 you'll only get one year of management.</span></span> <span data-ttu-id="ce6b9-184">此策略允许你从以前支持的产品中提取部分生命周期, 而无需提前购买新设备。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-184">This policy allows you to extract partial lifecycles from products that were previously supported, rather than having to procure new devices prematurely.</span></span> 

<span data-ttu-id="ce6b9-185">最后, 在此阶段中, 将从[设备列表](device-list.md)中删除设备并将其移至[存档设备列表](archived-device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-185">Finally, during this phase the device is removed from the [device list](device-list.md) and moved to the [archived device list](archived-device-list.md).</span></span>


## <a name="product-retirement"></a><span data-ttu-id="ce6b9-186">产品退休</span><span class="sxs-lookup"><span data-stu-id="ce6b9-186">Product retirement</span></span>

<span data-ttu-id="ce6b9-187">产品退休是生命周期的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-187">Product retirement is the final phase of the lifecycle.</span></span> <span data-ttu-id="ce6b9-188">在此阶段, 不能在 Microsoft 托管桌面中注册该产品类型的新设备, 并且根据定义, 所有现有设备现在都超出了其允许的三年期限。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-188">In this phase, no new devices of that product type can be enrolled in Microsoft Managed Desktop and, by definition, all existing devices are now outside their allowed three-year term.</span></span> <span data-ttu-id="ce6b9-189">在这段时间内, Microsoft 托管桌面将从公共列表中完全删除该设备。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-189">During this time, Microsoft Managed Desktop will remove the device from the public list entirely.</span></span> <span data-ttu-id="ce6b9-190">此外, 在此阶段, 如果尚未推出替换, 你将会在 Microsoft 托管桌面开始在不符合合规性的设备上开始向下滚动, 以查看降低的服务。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-190">It’s also during this phase where, if you haven't already procured replacements, you'll start to see diminished services as Microsoft Managed Desktop starts to ramp down on the devices which are out of compliance.</span></span> 

## <a name="devices-that-are-out-of-compliance"></a><span data-ttu-id="ce6b9-191">不符合合规性的设备</span><span class="sxs-lookup"><span data-stu-id="ce6b9-191">Devices that are out of compliance</span></span>

<span data-ttu-id="ce6b9-192">在 Microsoft 托管桌面管理的允许的窗口已过去时, 设备不符合合规性。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-192">A device is out of compliance when its allowed window for Microsoft Managed Desktop management has elapsed.</span></span> <span data-ttu-id="ce6b9-193">当设备已达到三年期的管理或从设备目录中删除该产品类型时, 将发生这种情况, 具体情况先发生。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-193">This occurs when the device has reached three years of management or when that product type is removed from the device catalog, whichever occurs first.</span></span> <span data-ttu-id="ce6b9-194">您应始终瞄准您的采购周期, 以便在当前设备不符合合规性之前部署新设备。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-194">You should always target your procurement cycles such that new devices are deployed prior to current devices going out of compliance.</span></span>

<span data-ttu-id="ce6b9-195">Microsoft 托管桌面团队知道采购周期较长, 并根据长期运行的预算进行规划。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-195">The Microsoft Managed Desktop team knows that procurement cycles are long and planned around long-running budgets.</span></span> <span data-ttu-id="ce6b9-196">为了确保你始终了解设备填充的状态, 我们提供了一个[网站](https://aka.ms/mmdportal), 其中列出了管理下的每个设备、将来的退休日期以及表明其符合性的状态。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-196">To ensure that you're always aware of the state of your device population, we provide a [website](https://aka.ms/mmdportal) that lists every device under management, its future retirement date, and a status indicating its compliance.</span></span> <span data-ttu-id="ce6b9-197">这意味着您始终拥有有关设备年龄的最新信息, 并可在任何采购计划周期中利用报告。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-197">This means you always have the latest information regarding device age and can leverage the report in any procurement planning cycle.</span></span> 


<span data-ttu-id="ce6b9-198">此外, 我们还将执行以下自动操作, 以确保新设备按时部署:</span><span class="sxs-lookup"><span data-stu-id="ce6b9-198">In addition, the we will also take the following automated actions to ensure that new devices are deployed on time:</span></span>


|<span data-ttu-id="ce6b9-199">日程表</span><span class="sxs-lookup"><span data-stu-id="ce6b9-199">Timeline</span></span>  |<span data-ttu-id="ce6b9-200">操作</span><span class="sxs-lookup"><span data-stu-id="ce6b9-200">Action</span></span>  |
|---------|---------|
|<span data-ttu-id="ce6b9-201">T-90</span><span class="sxs-lookup"><span data-stu-id="ce6b9-201">T-90</span></span>     | <span data-ttu-id="ce6b9-202">我们将立即将此设备标记为 "**即将过期**", 并在设备清单网站上加上黄色标记。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-202">We'll flag this device as **expiring soon**, with a yellow marker on the device inventory website.</span></span>  |
|<span data-ttu-id="ce6b9-203">T-60</span><span class="sxs-lookup"><span data-stu-id="ce6b9-203">T-60</span></span>     | <span data-ttu-id="ce6b9-204">我们将使用设备清单网站上的红色标记将此设备标记为**过期**。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-204">We'll flag this device as **expiring** with a red marker on the device inventory website.</span></span>       |
|<span data-ttu-id="ce6b9-205">T-30</span><span class="sxs-lookup"><span data-stu-id="ce6b9-205">T-30</span></span>     | <span data-ttu-id="ce6b9-206">我们将向管理门户发布一封邮件, 指出设备正在 imminently "已退出合规性"。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-206">We'll post a message to the Admin Portal saying that devices are imminently exiting compliance.</span></span>       |
|<span data-ttu-id="ce6b9-207">0</span><span class="sxs-lookup"><span data-stu-id="ce6b9-207">0</span></span>     |  <span data-ttu-id="ce6b9-208">我们将调整管理门户, 以指示设备现在已过期将管理员重定向到设备列表中的土地。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-208">We'll adjust the Admin Portal to say that devices are now expired redirect admins to land on the device list first.</span></span>       |
|<span data-ttu-id="ce6b9-209">T + 30</span><span class="sxs-lookup"><span data-stu-id="ce6b9-209">T+30</span></span>     |  <span data-ttu-id="ce6b9-210">在部署新设备之前, 我们将减少管理门户功能。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-210">We'll reduce Admin Portal functionality until new devices are deployed.</span></span>       |
|<span data-ttu-id="ce6b9-211">T + 60</span><span class="sxs-lookup"><span data-stu-id="ce6b9-211">T+60</span></span>     |  <span data-ttu-id="ce6b9-212">在部署新设备之前, 我们将减少管理门户功能。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-212">We'll reduce Admin Portal functionality until new devices are deployed.</span></span>       |
|<span data-ttu-id="ce6b9-213">T + 90</span><span class="sxs-lookup"><span data-stu-id="ce6b9-213">T+90</span></span>     |  <span data-ttu-id="ce6b9-214">我们将设备从管理中删除。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-214">We remove the device from management.</span></span> <span data-ttu-id="ce6b9-215">在这种情况下, 设备只是您自己的责任, 您不应再认为它是安全的, 也不是最新的。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-215">At this point, the device is solely your own responsibility and you should no longer consider it secure nor up to date.</span></span> <span data-ttu-id="ce6b9-216">此外, 设备将处于未知状态, 因为每个配置服务提供程序控制其自己的设置。</span><span class="sxs-lookup"><span data-stu-id="ce6b9-216">Also the device will be in an unknown state since each Configuration Service provider controls its own settings.</span></span>|




