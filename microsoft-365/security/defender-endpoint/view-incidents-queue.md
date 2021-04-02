---
title: 查看和组织事件队列
ms.reviewer: ''
description: 查看事件列表，了解如何应用筛选器来限制列表并获取更集中的视图。
keywords: 视图， 组织， 事件， 聚合， 调查， 队列， ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93aa685f12e0241758bf86d3aa956717db052e5f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499936"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="6eb24-104">查看和组织 Microsoft Defender 终结点事件队列</span><span class="sxs-lookup"><span data-stu-id="6eb24-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6eb24-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6eb24-105">**Applies to:**</span></span>
- [<span data-ttu-id="6eb24-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6eb24-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6eb24-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6eb24-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6eb24-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="6eb24-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6eb24-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6eb24-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="6eb24-110">**"事件队列**"显示从网络中设备标记的事件集合。</span><span class="sxs-lookup"><span data-stu-id="6eb24-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="6eb24-111">它可以帮助你对事件进行排序，从而确定优先级并制定明智的网络安全响应决策。</span><span class="sxs-lookup"><span data-stu-id="6eb24-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="6eb24-112">默认情况下，队列显示最近 30 天内看到的事件，最新事件显示在列表顶部，帮助你首先查看最近事件。</span><span class="sxs-lookup"><span data-stu-id="6eb24-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="6eb24-113">有几种选项可供选择以自定义事件队列视图。</span><span class="sxs-lookup"><span data-stu-id="6eb24-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="6eb24-114">在顶部导航上，你可以：</span><span class="sxs-lookup"><span data-stu-id="6eb24-114">On the top navigation you can:</span></span>
- <span data-ttu-id="6eb24-115">自定义列以添加或删除列</span><span class="sxs-lookup"><span data-stu-id="6eb24-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="6eb24-116">修改每页要查看的项目数</span><span class="sxs-lookup"><span data-stu-id="6eb24-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="6eb24-117">选择要按页显示的项目</span><span class="sxs-lookup"><span data-stu-id="6eb24-117">Select the items to show per page</span></span>
- <span data-ttu-id="6eb24-118">批量选择要分配的事件</span><span class="sxs-lookup"><span data-stu-id="6eb24-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="6eb24-119">在页面之间导航</span><span class="sxs-lookup"><span data-stu-id="6eb24-119">Navigate between pages</span></span>
- <span data-ttu-id="6eb24-120">应用筛选器</span><span class="sxs-lookup"><span data-stu-id="6eb24-120">Apply filters</span></span>

![事件队列的图像](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="6eb24-122">对事件队列进行排序和筛选</span><span class="sxs-lookup"><span data-stu-id="6eb24-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="6eb24-123">可以应用以下筛选器来限制事件列表，并获取更集中的视图。</span><span class="sxs-lookup"><span data-stu-id="6eb24-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="6eb24-124">Severity</span><span class="sxs-lookup"><span data-stu-id="6eb24-124">Severity</span></span>

<span data-ttu-id="6eb24-125">事件严重性</span><span class="sxs-lookup"><span data-stu-id="6eb24-125">Incident severity</span></span> | <span data-ttu-id="6eb24-126">说明</span><span class="sxs-lookup"><span data-stu-id="6eb24-126">Description</span></span>
:---|:---
<span data-ttu-id="6eb24-127">高</span><span class="sxs-lookup"><span data-stu-id="6eb24-127">High</span></span> </br><span data-ttu-id="6eb24-128"> (红色) </span><span class="sxs-lookup"><span data-stu-id="6eb24-128">(Red)</span></span> | <span data-ttu-id="6eb24-129">通常与高级永久性威胁和 APT (相关的) 。</span><span class="sxs-lookup"><span data-stu-id="6eb24-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="6eb24-130">这些事件表明，由于设备可造成严重损坏，因此存在高风险。</span><span class="sxs-lookup"><span data-stu-id="6eb24-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="6eb24-131">中</span><span class="sxs-lookup"><span data-stu-id="6eb24-131">Medium</span></span> </br><span data-ttu-id="6eb24-132"> (橙色) </span><span class="sxs-lookup"><span data-stu-id="6eb24-132">(Orange)</span></span> | <span data-ttu-id="6eb24-133">很少在组织中观察到的威胁，例如异常注册表更改、可疑文件的执行和观察到的攻击阶段典型行为。</span><span class="sxs-lookup"><span data-stu-id="6eb24-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="6eb24-134">低</span><span class="sxs-lookup"><span data-stu-id="6eb24-134">Low</span></span> </br><span data-ttu-id="6eb24-135"> (黄色) </span><span class="sxs-lookup"><span data-stu-id="6eb24-135">(Yellow)</span></span> | <span data-ttu-id="6eb24-136">与流行恶意软件和黑客工具关联的威胁，这些威胁不一定表示针对组织的高级威胁。</span><span class="sxs-lookup"><span data-stu-id="6eb24-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="6eb24-137">信息性</span><span class="sxs-lookup"><span data-stu-id="6eb24-137">Informational</span></span> </br><span data-ttu-id="6eb24-138"> (灰色) </span><span class="sxs-lookup"><span data-stu-id="6eb24-138">(Grey)</span></span> | <span data-ttu-id="6eb24-139">信息事件可能被视为对网络没有危害，但可以跟踪。</span><span class="sxs-lookup"><span data-stu-id="6eb24-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="6eb24-140">分配到</span><span class="sxs-lookup"><span data-stu-id="6eb24-140">Assigned to</span></span>
<span data-ttu-id="6eb24-141">可选择通过选择分配给任何人/分配给你的人来筛选列表。</span><span class="sxs-lookup"><span data-stu-id="6eb24-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="6eb24-142">Category</span><span class="sxs-lookup"><span data-stu-id="6eb24-142">Category</span></span>
<span data-ttu-id="6eb24-143">根据网络安全终止链所处于的阶段的说明对事件进行分类。</span><span class="sxs-lookup"><span data-stu-id="6eb24-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="6eb24-144">此视图可帮助威胁分析员根据上下文确定要部署的优先级、紧急程度和相应的响应策略。</span><span class="sxs-lookup"><span data-stu-id="6eb24-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="6eb24-145">状态</span><span class="sxs-lookup"><span data-stu-id="6eb24-145">Status</span></span>
<span data-ttu-id="6eb24-146">可以根据事件的状态选择限制所显示事件的列表，以查看哪些事件处于活动状态/已解决状态。</span><span class="sxs-lookup"><span data-stu-id="6eb24-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="6eb24-147">数据敏感性</span><span class="sxs-lookup"><span data-stu-id="6eb24-147">Data sensitivity</span></span>
<span data-ttu-id="6eb24-148">使用此筛选器显示包含敏感度标签的事件。</span><span class="sxs-lookup"><span data-stu-id="6eb24-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="6eb24-149">事件命名</span><span class="sxs-lookup"><span data-stu-id="6eb24-149">Incident naming</span></span>

<span data-ttu-id="6eb24-150">为了一目了然地了解事件的范围，事件名称会基于警报属性自动生成，如受影响的终结点数量、受影响的用户、检测源或类别。</span><span class="sxs-lookup"><span data-stu-id="6eb24-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="6eb24-151">例如： *多个源报告的多个终结点上的多阶段事件。*</span><span class="sxs-lookup"><span data-stu-id="6eb24-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="6eb24-152">在推出自动事件命名之前已存在的事件将保留其名称。</span><span class="sxs-lookup"><span data-stu-id="6eb24-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="6eb24-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6eb24-153">See also</span></span>
- [<span data-ttu-id="6eb24-154">事件队列</span><span class="sxs-lookup"><span data-stu-id="6eb24-154">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="6eb24-155">管理事件</span><span class="sxs-lookup"><span data-stu-id="6eb24-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="6eb24-156">调查事件</span><span class="sxs-lookup"><span data-stu-id="6eb24-156">Investigate incidents</span></span>](investigate-incidents.md)

