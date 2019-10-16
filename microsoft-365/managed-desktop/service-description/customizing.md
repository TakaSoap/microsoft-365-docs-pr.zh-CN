---
title: 自定义服务
description: ''
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b2b74194c9b73e538fc1be937456b76deef75feb
ms.sourcegitcommit: eed48c21790d31a85292f7e39bf1e30c42f10d36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "37523667"
---
# <a name="customize-the-service"></a><span data-ttu-id="5a760-103">自定义服务</span><span class="sxs-lookup"><span data-stu-id="5a760-103">Customize the service</span></span>

<span data-ttu-id="5a760-104">Microsoft 托管桌面提供 curated 设备列表、[标准设备设置](device-policies.md)、应用程序要求以及某些[可配置的设置](../working-with-managed-desktop/config-setting-overview.md)，所有这些都旨在为最终用户提供安全、高效和愉快的体验。</span><span class="sxs-lookup"><span data-stu-id="5a760-104">Microsoft Managed Desktop provides a curated device list, [standard device settings](device-policies.md), applications requirements, and certain [configurable settings](../working-with-managed-desktop/config-setting-overview.md), all designed to provide a secure, productive, and pleasant experience for end users.</span></span> <span data-ttu-id="5a760-105">最好始终与提供的服务保持联系。</span><span class="sxs-lookup"><span data-stu-id="5a760-105">It’s best to always stay with the service as provided.</span></span> <span data-ttu-id="5a760-106">但是，我们意识到服务的一些详细信息可能无法完全满足您组织的需求。</span><span class="sxs-lookup"><span data-stu-id="5a760-106">However, we recognize that some details of the service might not fit exactly with your organization’s needs.</span></span> <span data-ttu-id="5a760-107">如果你认为需要以某种方式更改服务，请务必按照以下过程请求这些更改。</span><span class="sxs-lookup"><span data-stu-id="5a760-107">If you feel you need to alter the service in some way, it’s important that you follow the following processes to request those changes.</span></span>

 
## <a name="types-of-customizations"></a><span data-ttu-id="5a760-108">自定义项的类型</span><span class="sxs-lookup"><span data-stu-id="5a760-108">Types of customizations</span></span>
<span data-ttu-id="5a760-109">自定义项是对 Microsoft 托管桌面基本配置的任何添加或更改;示例范围从 "USB 端口配置" 到 "部署新的安全代理"。</span><span class="sxs-lookup"><span data-stu-id="5a760-109">A customization is any addition or change to the Microsoft Managed Desktop base configuration; examples range from USB ports configuration to deploying a new security agent.</span></span> <span data-ttu-id="5a760-110">我们将各种自定义项分组，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5a760-110">We group various customizations as follows:</span></span>


|<span data-ttu-id="5a760-111">类型</span><span class="sxs-lookup"><span data-stu-id="5a760-111">Type</span></span>  |<span data-ttu-id="5a760-112">说明</span><span class="sxs-lookup"><span data-stu-id="5a760-112">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="5a760-113">生产力软件</span><span class="sxs-lookup"><span data-stu-id="5a760-113">Productivity software</span></span>     |  <span data-ttu-id="5a760-114">最终用户所需的前台软件（受[应用程序要求](mmd-app-requirements.md)的限制）</span><span class="sxs-lookup"><span data-stu-id="5a760-114">Foreground software needed by end users, restricted by the [application requirements](mmd-app-requirements.md)</span></span>       |
|<span data-ttu-id="5a760-115">& Vpn 的安全代理</span><span class="sxs-lookup"><span data-stu-id="5a760-115">Security agents & VPNs</span></span>     |  <span data-ttu-id="5a760-116">用于保护、监视或更改设备或网络的行为的软件</span><span class="sxs-lookup"><span data-stu-id="5a760-116">Software used to secure, monitor, or change the behavior of the device or network</span></span>       |
|<span data-ttu-id="5a760-117">数字体验监控</span><span class="sxs-lookup"><span data-stu-id="5a760-117">Digital experience monitoring</span></span>     |  <span data-ttu-id="5a760-118">用于跟踪用户设备上的数据以向其报告的软件</span><span class="sxs-lookup"><span data-stu-id="5a760-118">Software used to track data on a user’s device to report to IT</span></span>       |
|<span data-ttu-id="5a760-119">硬件或软件驱动程序</span><span class="sxs-lookup"><span data-stu-id="5a760-119">Hardware or software drivers</span></span>     |   <span data-ttu-id="5a760-120">由[应用程序要求](mmd-app-requirements.md)限制的设备驱动程序</span><span class="sxs-lookup"><span data-stu-id="5a760-120">Device drivers, restricted by the [application requirements](mmd-app-requirements.md)</span></span>      |
|<span data-ttu-id="5a760-121">策略</span><span class="sxs-lookup"><span data-stu-id="5a760-121">Policies</span></span>     | <span data-ttu-id="5a760-122">托管设备上的 Windows 10 或 Office 365 专业增强版设置</span><span class="sxs-lookup"><span data-stu-id="5a760-122">Windows 10 or Office 365 ProPlus settings on a managed device</span></span>        |
|<span data-ttu-id="5a760-123">设备</span><span class="sxs-lookup"><span data-stu-id="5a760-123">Devices</span></span>     | <span data-ttu-id="5a760-124">不在 Microsoft 托管桌面[设备列表](device-list.md)中的设备</span><span class="sxs-lookup"><span data-stu-id="5a760-124">Devices which are not on the Microsoft Managed Desktop [device list](device-list.md)</span></span>        |
|<span data-ttu-id="5a760-125">Other</span><span class="sxs-lookup"><span data-stu-id="5a760-125">Other</span></span>     |  <span data-ttu-id="5a760-126">其他区域未涵盖的任何内容</span><span class="sxs-lookup"><span data-stu-id="5a760-126">Anything not covered by the other areas</span></span>       |



 
## <a name="request-a-customization"></a><span data-ttu-id="5a760-127">请求自定义项</span><span class="sxs-lookup"><span data-stu-id="5a760-127">Request a customization</span></span>

<span data-ttu-id="5a760-128">通过创建更改请求，通过 Microsoft 托管桌面管理门户提交请求。</span><span class="sxs-lookup"><span data-stu-id="5a760-128">Submit requests through the Microsoft Managed Desktop Admin portal by creating a change request.</span></span> <span data-ttu-id="5a760-129">请务必包含以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="5a760-129">Be sure to include these details:</span></span>
-   <span data-ttu-id="5a760-130">自定义类型：它是哪种自定义类别？</span><span class="sxs-lookup"><span data-stu-id="5a760-130">Customization type: Which category of customization is it?</span></span> <span data-ttu-id="5a760-131">（请参阅上表）</span><span class="sxs-lookup"><span data-stu-id="5a760-131">(see the previous table)</span></span>
-   <span data-ttu-id="5a760-132">要求：自定义项的特定业务要求是什么？</span><span class="sxs-lookup"><span data-stu-id="5a760-132">Requirement: What is the specific business requirement for the customization?</span></span>
-   <span data-ttu-id="5a760-133">建议：您的业务请求的解决方案是什么？</span><span class="sxs-lookup"><span data-stu-id="5a760-133">Proposal: Which solution is your business requesting?</span></span>
-   <span data-ttu-id="5a760-134">时间轴：您希望此自定义持续多长时间？</span><span class="sxs-lookup"><span data-stu-id="5a760-134">Timeline: How long do you want this customization to last?</span></span> 


## <a name="how-we-assess-a-customization-request"></a><span data-ttu-id="5a760-135">如何评估自定义请求</span><span class="sxs-lookup"><span data-stu-id="5a760-135">How we assess a customization request</span></span>

<span data-ttu-id="5a760-136">当我们查看自定义请求时，我们将按此顺序评估这些因素：</span><span class="sxs-lookup"><span data-stu-id="5a760-136">When we review customization requests, we assess these factors in this order:</span></span>
 
1.  <span data-ttu-id="5a760-137">Microsoft 托管桌面部署到所有设备的一些应用程序和策略不可转让，因此您的请求不得影响这些应用程序和策略。</span><span class="sxs-lookup"><span data-stu-id="5a760-137">Some applications and policies which Microsoft Managed Desktop deploys to all devices aren't negotiable, so your request must not affect those.</span></span> <span data-ttu-id="5a760-138">有关详细信息，请参阅[设备配置](device-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5a760-138">See [Device configuration](device-policies.md) for more information.</span></span>
2.  <span data-ttu-id="5a760-139">最终用户所需的受限制的生产力软件将可能被批准。</span><span class="sxs-lookup"><span data-stu-id="5a760-139">Restricted productivity software required by an end user to do their job will likely be approved.</span></span> 
3.  <span data-ttu-id="5a760-140">如果我们可以使用 Microsoft 技术满足你的要求，我们可能会在3到12个月的迁移期内批准你的请求（具体取决于项目的范围）。</span><span class="sxs-lookup"><span data-stu-id="5a760-140">If we can meet your requirement by using Microsoft technology, we’ll likely approve your request for a  migration period of three to twelve months (depending on the scope of the project).</span></span>
4.  <span data-ttu-id="5a760-141">如果使用 Microsoft 技术无法满足你的要求，我们可能会批准你的请求，除非违反以下条件之一。</span><span class="sxs-lookup"><span data-stu-id="5a760-141">If we can’t meet your requirement by using Microsoft technology, we’ll likely approve your request unless it violates one of the conditions below.</span></span>  

<span data-ttu-id="5a760-142">这些原则确保 Microsoft 托管桌面始终能够满足您的需求，同时跟踪我们的标准模板的偏差。</span><span class="sxs-lookup"><span data-stu-id="5a760-142">These principles ensure that Microsoft Managed Desktop can always meet your needs while tracking deviations from our standard template.</span></span> 

## <a name="key-conditions"></a><span data-ttu-id="5a760-143">关键条件</span><span class="sxs-lookup"><span data-stu-id="5a760-143">Key conditions</span></span>

<span data-ttu-id="5a760-144">我们会查看自定义项，以确保它们不会违反任何以下条件：</span><span class="sxs-lookup"><span data-stu-id="5a760-144">We review customizations to ensure they don't violate any of these conditions:</span></span>

-   <span data-ttu-id="5a760-145">自定义项不一定会对系统安全性产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="5a760-145">A customization must not adversely impact system security.</span></span> 
-   <span data-ttu-id="5a760-146">维护自定义项不一定会因 Microsoft 托管桌面操作或支持而产生巨大成本。</span><span class="sxs-lookup"><span data-stu-id="5a760-146">Maintaining the customization must not incur a significant cost for either Microsoft Managed Desktop operations or support.</span></span>
-   <span data-ttu-id="5a760-147">自定义项不能影响系统稳定性，例如，通过导致内核模式故障或挂起。</span><span class="sxs-lookup"><span data-stu-id="5a760-147">A customization must not affect system stability, for example, by causing kernel mode crashes or hangs.</span></span>
-   <span data-ttu-id="5a760-148">更改不能限制我们运行服务或与核心 Microsoft 托管桌面技术发生冲突。</span><span class="sxs-lookup"><span data-stu-id="5a760-148">The change must not restrict us from operating the service or conflict with core Microsoft Managed Desktop technology.</span></span>

<span data-ttu-id="5a760-149">这些条件可能会在将来发生变化。</span><span class="sxs-lookup"><span data-stu-id="5a760-149">These conditions could change in the future.</span></span> <span data-ttu-id="5a760-150">如果我们确实进行了此类更改，我们将在这些条件生效前30天通知。</span><span class="sxs-lookup"><span data-stu-id="5a760-150">If we do make such changes, we’ll provide 30 days notice prior to those conditions coming into effect.</span></span>

## <a name="revoking-approval-for-a-customization"></a><span data-ttu-id="5a760-151">撤销对自定义项的审批</span><span class="sxs-lookup"><span data-stu-id="5a760-151">Revoking approval for a customization</span></span>

<span data-ttu-id="5a760-152">在请求的自定义项得到批准和部署后，我们可能会发现一些问题，这些问题可能会导致在最初批准更改时遇到的关键情况不明显。</span><span class="sxs-lookup"><span data-stu-id="5a760-152">After a requested customization is approved and deployed, it’s possible that we might discover problems that violate the key conditions that weren’t evident when we approved the change in the first place.</span></span> <span data-ttu-id="5a760-153">在这种情况下，我们可能必须撤销对自定义项的审批。</span><span class="sxs-lookup"><span data-stu-id="5a760-153">In this situation, we might have to revoke approval for the customization.</span></span>
 
<span data-ttu-id="5a760-154">如果发生这种情况，我们将使用 Microsoft 托管桌面管理门户通知你。</span><span class="sxs-lookup"><span data-stu-id="5a760-154">If this happens, we’ll notify you by using the Microsoft Managed Desktop admin portal.</span></span> <span data-ttu-id="5a760-155">我们第一次通知你，在自定义的设备不再受 Microsoft 托管桌面服务级别协议约束之前，你有90天的时间来删除自定义项。</span><span class="sxs-lookup"><span data-stu-id="5a760-155">From the first time we notify you, you have 90 days to remove the customization before the devices with the customization are no longer bound by Microsoft Managed Desktop service level agreements.</span></span> <span data-ttu-id="5a760-156">我们将根据严格的时间线向你发送几个通知-但是，严重事件或威胁可能需要我们更改时间线或我们关于自定义的决策。</span><span class="sxs-lookup"><span data-stu-id="5a760-156">We'll send you several notifications according to a strict timeline--however, a severe incident or threat might require us to change the timeline or our decisions about a customization.</span></span> <span data-ttu-id="5a760-157">我们不会在你同意的情况下*删除*自定义项，但具有已吊销的自定义的任何设备将不再受我们的服务级别协议的约束。</span><span class="sxs-lookup"><span data-stu-id="5a760-157">We won't *remove* a customization without your consent, but any device with a revoked customization will no longer be bound by our service level agreement.</span></span> <span data-ttu-id="5a760-158">下面是我们将向你发送通知的时间线：</span><span class="sxs-lookup"><span data-stu-id="5a760-158">Here is the timeline of notifications we will send you:</span></span>

- <span data-ttu-id="5a760-159">**第一次通知：** 我们在决定撤消批准时提供了第一次通知，其中包括有关我们吊销批准的原因的信息、我们建议采取的操作、这些操作的截止时间以及要采取的措施（如果您想要采取此决定）。</span><span class="sxs-lookup"><span data-stu-id="5a760-159">**First notice:** We provide the first notice of our decision to revoke approval, including information about why we’re revoking it, the actions we advise you to take, the deadline for those actions, and steps to follow if you want to appeal the decision.</span></span> <span data-ttu-id="5a760-160">在需要将自定义项从所有设备中删除之前，这将提前90天。</span><span class="sxs-lookup"><span data-stu-id="5a760-160">This is 90 days in advance before the customization needs to be removed from all devices.</span></span> 
- <span data-ttu-id="5a760-161">**第二次通知（30天后）：** 我们提供了另一条通知，包括在第一次通知中提供的相同信息。</span><span class="sxs-lookup"><span data-stu-id="5a760-161">**Second notice (30 days later):** We provide a second notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="5a760-162">**第三个通知（第一个通知后的60天）：** 我们提供了第三个通知，包括在第一个通知中提供的相同信息。</span><span class="sxs-lookup"><span data-stu-id="5a760-162">**Third notice (60 days after the first notice):** We provide a third notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="5a760-163">**最终通知（90天截止日期前1周）：** 我们提供了第四个通知，包括在第一次通知中提供的相同信息。</span><span class="sxs-lookup"><span data-stu-id="5a760-163">**Final notice (1 week before the 90-day deadline):** We provide a fourth notice, including the same information provided in the first notice.</span></span>
- <span data-ttu-id="5a760-164">**第一次通知之后的90天：** Microsoft 托管桌面服务级别协议不再适用于具有已吊销自定义项的任何设备。</span><span class="sxs-lookup"><span data-stu-id="5a760-164">**90 days after first notice:** Microsoft Managed Desktop service level agreements no longer apply to any devices that have the revoked customization.</span></span> <span data-ttu-id="5a760-165">在任何时候，您都可以挑战决策，并提供其他注意事项信息，包括升级、配置更改或软件更改。</span><span class="sxs-lookup"><span data-stu-id="5a760-165">At any time, you can challenge the decision and provide additional information for consideration, including upgrade, configuration changes, or change of software.</span></span> 

