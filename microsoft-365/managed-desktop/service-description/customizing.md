---
title: 服务计划的例外情况
description: 如何请求标准服务计划的例外
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 59a2b8227eb7e410ecf8506ce288978213537edc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245512"
---
# <a name="exceptions-to-the-service-plan"></a><span data-ttu-id="e81ee-104">服务计划的例外情况</span><span class="sxs-lookup"><span data-stu-id="e81ee-104">Exceptions to the service plan</span></span>

<span data-ttu-id="e81ee-105">Microsoft 托管桌面提供了一个精心设计的设备列表、标准设备[](device-policies.md)设置、应用程序要求和某些可配置设置[](../working-with-managed-desktop/config-setting-overview.md)，所有这些都旨在为用户提供安全、高效且令人愉悦的体验。</span><span class="sxs-lookup"><span data-stu-id="e81ee-105">Microsoft Managed Desktop provides a curated device list, [standard device settings](device-policies.md), applications requirements, and certain [configurable settings](../working-with-managed-desktop/config-setting-overview.md), all designed to provide a secure, productive, and pleasant experience for users.</span></span> <span data-ttu-id="e81ee-106">最好始终使用所提供的服务。</span><span class="sxs-lookup"><span data-stu-id="e81ee-106">It’s best to always stay with the service as provided.</span></span> <span data-ttu-id="e81ee-107">但是，我们意识到服务的一些详细信息可能并不完全符合贵组织的需求。</span><span class="sxs-lookup"><span data-stu-id="e81ee-107">However, we recognize that some details of the service might not fit exactly with your organization’s needs.</span></span> <span data-ttu-id="e81ee-108">如果您觉得需要通过某种方式更改服务，则按照以下过程请求这些更改非常重要。</span><span class="sxs-lookup"><span data-stu-id="e81ee-108">If you feel you need to alter the service in some way, it’s important that you follow the following processes to request those changes.</span></span>
 
## <a name="types-of-exceptions"></a><span data-ttu-id="e81ee-109">异常类型</span><span class="sxs-lookup"><span data-stu-id="e81ee-109">Types of exceptions</span></span>

<span data-ttu-id="e81ee-110">例外情况是，对基本配置进行Microsoft 托管桌面更改;示例范围从 USB 端口配置到部署新设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e81ee-110">An exception is any addition or change to the Microsoft Managed Desktop base configuration; examples range from USB ports configuration to deploying a new device driver.</span></span> <span data-ttu-id="e81ee-111">我们按如下方式对各种例外进行分组：</span><span class="sxs-lookup"><span data-stu-id="e81ee-111">We group various exceptions as follows:</span></span>

|<span data-ttu-id="e81ee-112">类型</span><span class="sxs-lookup"><span data-stu-id="e81ee-112">Type</span></span>  |<span data-ttu-id="e81ee-113">说明</span><span class="sxs-lookup"><span data-stu-id="e81ee-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="e81ee-114">工作效率软件</span><span class="sxs-lookup"><span data-stu-id="e81ee-114">Productivity software</span></span>     |  <span data-ttu-id="e81ee-115">用户所需的前台软件，受应用程序 [要求限制](mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="e81ee-115">Foreground software needed by users, restricted by the [application requirements](mmd-app-requirements.md)</span></span>       |
|<span data-ttu-id="e81ee-116">VPN &代理</span><span class="sxs-lookup"><span data-stu-id="e81ee-116">Security agents & VPNs</span></span>     |  <span data-ttu-id="e81ee-117">用于保护、监视或更改设备或网络行为的软件</span><span class="sxs-lookup"><span data-stu-id="e81ee-117">Software used to secure, monitor, or change the behavior of the device or network</span></span>       |
|<span data-ttu-id="e81ee-118">数字体验监视</span><span class="sxs-lookup"><span data-stu-id="e81ee-118">Digital experience monitoring</span></span>     |  <span data-ttu-id="e81ee-119">用于跟踪用户设备上要报告给 IT 的数据的软件</span><span class="sxs-lookup"><span data-stu-id="e81ee-119">Software used to track data on a user’s device to report to IT</span></span>       |
|<span data-ttu-id="e81ee-120">硬件或软件驱动程序</span><span class="sxs-lookup"><span data-stu-id="e81ee-120">Hardware or software drivers</span></span>     |   <span data-ttu-id="e81ee-121">受应用程序要求限制的设备 [驱动程序](mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="e81ee-121">Device drivers, restricted by the [application requirements](mmd-app-requirements.md)</span></span>      |
|<span data-ttu-id="e81ee-122">策略</span><span class="sxs-lookup"><span data-stu-id="e81ee-122">Policies</span></span>     | <span data-ttu-id="e81ee-123">Windows 10托管Microsoft 365 企业应用版或设置</span><span class="sxs-lookup"><span data-stu-id="e81ee-123">Windows 10 or Microsoft 365 Apps for enterprise settings on a managed device</span></span>        |
|<span data-ttu-id="e81ee-124">设备</span><span class="sxs-lookup"><span data-stu-id="e81ee-124">Devices</span></span>     | <span data-ttu-id="e81ee-125">不在设备列表中的Microsoft 托管桌面[设备](device-list.md)</span><span class="sxs-lookup"><span data-stu-id="e81ee-125">Devices that are not on the Microsoft Managed Desktop [device list](device-list.md)</span></span>        |
|<span data-ttu-id="e81ee-126">其他</span><span class="sxs-lookup"><span data-stu-id="e81ee-126">Other</span></span>     |  <span data-ttu-id="e81ee-127">任何其他区域未涵盖的内容</span><span class="sxs-lookup"><span data-stu-id="e81ee-127">Anything not covered by the other areas</span></span>       |
 
## <a name="request-an-exception"></a><span data-ttu-id="e81ee-128">请求异常</span><span class="sxs-lookup"><span data-stu-id="e81ee-128">Request an exception</span></span>

<span data-ttu-id="e81ee-129">通过管理门户Microsoft 托管桌面更改请求提交请求。</span><span class="sxs-lookup"><span data-stu-id="e81ee-129">Submit requests through the Microsoft Managed Desktop Admin portal by creating a change request.</span></span> <span data-ttu-id="e81ee-130">请务必包含以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="e81ee-130">Be sure to include these details:</span></span>

- <span data-ttu-id="e81ee-131">免除类型：属于哪个类别的例外？</span><span class="sxs-lookup"><span data-stu-id="e81ee-131">Exemption type: Which category of exception is it?</span></span> <span data-ttu-id="e81ee-132"> (上表) </span><span class="sxs-lookup"><span data-stu-id="e81ee-132">(see the previous table)</span></span>
- <span data-ttu-id="e81ee-133">要求：异常的特定业务需求是什么？</span><span class="sxs-lookup"><span data-stu-id="e81ee-133">Requirement: What is the specific business requirement for the exception?</span></span>
- <span data-ttu-id="e81ee-134">建议：你的业务正在请求哪个解决方案？</span><span class="sxs-lookup"><span data-stu-id="e81ee-134">Proposal: Which solution is your business requesting?</span></span>
- <span data-ttu-id="e81ee-135">时间线：希望此异常持续多久？</span><span class="sxs-lookup"><span data-stu-id="e81ee-135">Timeline: How long do you want this exception to last?</span></span> 

## <a name="how-we-assess-an-exception-request"></a><span data-ttu-id="e81ee-136">如何评估异常请求</span><span class="sxs-lookup"><span data-stu-id="e81ee-136">How we assess an exception request</span></span>

<span data-ttu-id="e81ee-137">查看异常请求时，我们将按以下顺序评估这些因素：</span><span class="sxs-lookup"><span data-stu-id="e81ee-137">When we review exception requests, we assess these factors in this order:</span></span>
 
1. <span data-ttu-id="e81ee-138">某些要部署到Microsoft 托管桌面的应用程序和策略不会带来任何影响，因此请求不得影响它们。</span><span class="sxs-lookup"><span data-stu-id="e81ee-138">Some applications and policies which Microsoft Managed Desktop deploys to all devices aren't negotiable, so your request must not affect those.</span></span> <span data-ttu-id="e81ee-139">有关详细信息 [，请参阅](device-policies.md) 设备配置。</span><span class="sxs-lookup"><span data-stu-id="e81ee-139">See [Device configuration](device-policies.md) for more information.</span></span>
2. <span data-ttu-id="e81ee-140">用户完成工作所需的受限工作效率软件可能会获得批准。</span><span class="sxs-lookup"><span data-stu-id="e81ee-140">Restricted productivity software required by a user to do their job will likely be approved.</span></span> 
3. <span data-ttu-id="e81ee-141">如果我们可以使用 Microsoft 技术满足你的要求，我们很可能会批准你请求的例外迁移期为 (3 到 12 个月，具体取决于项目迁移) 。</span><span class="sxs-lookup"><span data-stu-id="e81ee-141">If we can meet your requirement by using Microsoft technology, we’ll likely approve your request for an exception migration period of three to 12 months (depending on the scope of the project).</span></span>
4. <span data-ttu-id="e81ee-142">如果我们使用 Microsoft 技术无法满足您的要求，我们很可能会批准你的请求，除非它违反了以下条件之一。</span><span class="sxs-lookup"><span data-stu-id="e81ee-142">If we can’t meet your requirement by using Microsoft technology, we’ll likely approve your request unless it violates one of the conditions below.</span></span>  

<span data-ttu-id="e81ee-143">这些原则可确保在Microsoft 托管桌面模板的偏差时，始终满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="e81ee-143">These principles ensure that Microsoft Managed Desktop can always meet your needs while tracking deviations from our standard template.</span></span> 

## <a name="key-conditions"></a><span data-ttu-id="e81ee-144">关键条件</span><span class="sxs-lookup"><span data-stu-id="e81ee-144">Key conditions</span></span>

<span data-ttu-id="e81ee-145">我们查看例外以确保它们不会违反以下任何条件：</span><span class="sxs-lookup"><span data-stu-id="e81ee-145">We review exceptions to ensure they don't violate any of these conditions:</span></span>

- <span data-ttu-id="e81ee-146">例外不得对系统安全性产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="e81ee-146">An exception must not adversely impact system security.</span></span> 
- <span data-ttu-id="e81ee-147">维护异常不得使运行或支持产生Microsoft 托管桌面成本。</span><span class="sxs-lookup"><span data-stu-id="e81ee-147">Maintaining the exception must not incur a significant cost for either Microsoft Managed Desktop operations or support.</span></span>
- <span data-ttu-id="e81ee-148">异常不得影响系统稳定性，例如，导致内核模式崩溃或挂起。</span><span class="sxs-lookup"><span data-stu-id="e81ee-148">An exception must not affect system stability, for example, by causing kernel mode crashes or hangs.</span></span>
- <span data-ttu-id="e81ee-149">更改不得限制我们运营该服务或与核心技术Microsoft 托管桌面冲突。</span><span class="sxs-lookup"><span data-stu-id="e81ee-149">The change must not restrict us from operating the service or conflict with core Microsoft Managed Desktop technology.</span></span>

<span data-ttu-id="e81ee-150">这些条件将来可能会更改。</span><span class="sxs-lookup"><span data-stu-id="e81ee-150">These conditions could change in the future.</span></span> <span data-ttu-id="e81ee-151">如果我们进行此类更改，我们将在这些条件生效之前提前 30 天发出通知。</span><span class="sxs-lookup"><span data-stu-id="e81ee-151">If we do make such changes, we’ll provide 30 days notice prior to those conditions coming into effect.</span></span>  <span data-ttu-id="e81ee-152">如果Microsoft 托管桌面提供满足已批准例外的替代方法，Microsoft 托管桌面通知客户Microsoft 托管桌面更改支持例外的方式。</span><span class="sxs-lookup"><span data-stu-id="e81ee-152">If Microsoft Managed Desktop delivers an alternative way to meet an approved exception, Microsoft Managed Desktop will notify the customer should Microsoft Managed Desktop alter the way in supporting the exception.</span></span> 

## <a name="revoking-approval-for-an-exception"></a><span data-ttu-id="e81ee-153">撤销对异常的审批</span><span class="sxs-lookup"><span data-stu-id="e81ee-153">Revoking approval for an exception</span></span>

<span data-ttu-id="e81ee-154">批准并部署请求的异常后，我们可能会发现违反最初批准更改时未明显的关键条件的问题。</span><span class="sxs-lookup"><span data-stu-id="e81ee-154">After a requested exception is approved and deployed, it’s possible that we might discover problems that violate the key conditions that weren’t evident when we approved the change in the first place.</span></span> <span data-ttu-id="e81ee-155">在这种情况下，我们可能需要撤销对异常的批准。</span><span class="sxs-lookup"><span data-stu-id="e81ee-155">In this situation, we might have to revoke approval for the exception.</span></span>
 
<span data-ttu-id="e81ee-156">如果发生这种情况，我们将使用管理门户Microsoft 托管桌面通知你。</span><span class="sxs-lookup"><span data-stu-id="e81ee-156">If this happens, we’ll notify you by using the Microsoft Managed Desktop admin portal.</span></span> <span data-ttu-id="e81ee-157">从我们第一次通知你开始，你有 90 天的时间来删除例外，然后例外的设备不再受服务Microsoft 托管桌面限制。</span><span class="sxs-lookup"><span data-stu-id="e81ee-157">From the first time we notify you, you have 90 days to remove the exception before the devices with the exception are no longer bound by Microsoft Managed Desktop service level agreements.</span></span> <span data-ttu-id="e81ee-158">我们将根据严格的时间线向您发送多个通知，但是，严重事件或威胁可能要求我们更改日程表或有关异常的决策。</span><span class="sxs-lookup"><span data-stu-id="e81ee-158">We'll send you several notifications according to a strict timeline--however, a severe incident or threat might require us to change the timeline or our decisions about an exception.</span></span> <span data-ttu-id="e81ee-159">未经你的 *同意* ，我们不会删除例外，但任何具有已撤销例外的设备将不再受到服务级别协议的约束。</span><span class="sxs-lookup"><span data-stu-id="e81ee-159">We won't *remove* an exception without your consent, but any device with a revoked exception will no longer be bound by our service level agreement.</span></span> <span data-ttu-id="e81ee-160">以下是我们将向您发送的通知时间线：</span><span class="sxs-lookup"><span data-stu-id="e81ee-160">Here is the timeline of notifications we will send you:</span></span>

- <span data-ttu-id="e81ee-161">**首先请注意：** 我们提供了撤销审批决定的第一个通知，包括有关我们撤销批准的原因、建议你采取的操作、这些操作的期限以及当你要就决定进行诉讼时要执行的步骤的信息。</span><span class="sxs-lookup"><span data-stu-id="e81ee-161">**First notice:** We provide the first notice of our decision to revoke approval, including information about why we’re revoking it, the actions we advise you to take, the deadline for those actions, and steps to follow if you want to appeal the decision.</span></span> <span data-ttu-id="e81ee-162">此通知在需要从所有设备中删除异常前提前 90 天发生。</span><span class="sxs-lookup"><span data-stu-id="e81ee-162">This notice occurs 90 days in advance before the exception needs to be removed from all devices.</span></span> 
- <span data-ttu-id="e81ee-163">**第二次 (30 天后) ：** 我们提供了第二次通知，其中包括第一次通知中提供的相同信息。</span><span class="sxs-lookup"><span data-stu-id="e81ee-163">**Second notice (30 days later):** We provide a second notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="e81ee-164">**第三 (第一次通知后 60) ：** 我们提供了第三次通知，其中包括第一次通知中提供的相同信息。</span><span class="sxs-lookup"><span data-stu-id="e81ee-164">**Third notice (60 days after the first notice):** We provide a third notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="e81ee-165">**最终通知 (90** 天截止时间前的一周) ：我们提供了第四个通知，其中包括第一个通知中提供的相同信息。</span><span class="sxs-lookup"><span data-stu-id="e81ee-165">**Final notice (one week before the 90-day deadline):** We provide a fourth notice, including the same information provided in the first notice.</span></span>
- <span data-ttu-id="e81ee-166">**首次通知后 90 天：Microsoft 托管桌面** 服务级别协议不再适用于具有已撤销异常的任何设备。</span><span class="sxs-lookup"><span data-stu-id="e81ee-166">**90 days after first notice:** Microsoft Managed Desktop service level agreements no longer apply to any devices that have the revoked exception.</span></span> <span data-ttu-id="e81ee-167">你随时都可以对决定进行质询，并提供其他要考虑的信息，包括升级、配置更改或软件更改。</span><span class="sxs-lookup"><span data-stu-id="e81ee-167">At any time, you can challenge the decision and provide additional information for consideration, including upgrade, configuration changes, or change of software.</span></span> 


