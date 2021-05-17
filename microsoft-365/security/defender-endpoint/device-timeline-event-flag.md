---
title: Microsoft Defender for Endpoint 设备时间线事件标志
description: 使用 Microsoft Defender for Endpoint 设备时间线事件标志
keywords: 适用于终结点的 Defender 设备时间线、事件标志
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165149"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a><span data-ttu-id="5ce93-104">Microsoft Defender for Endpoint 设备时间线事件标志</span><span class="sxs-lookup"><span data-stu-id="5ce93-104">Microsoft Defender for Endpoint device timeline event flags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ce93-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5ce93-105">**Applies to:**</span></span>
- [<span data-ttu-id="5ce93-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5ce93-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5ce93-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ce93-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5ce93-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="5ce93-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5ce93-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5ce93-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="5ce93-110">Defender for Endpoint 设备时间线中的事件标志可帮助你在调查潜在攻击时筛选和组织特定事件。</span><span class="sxs-lookup"><span data-stu-id="5ce93-110">Event flags in the Defender for Endpoint device timeline help you filter and organize specific events when you're  investigate potential attacks.</span></span>

<span data-ttu-id="5ce93-111">Defender for Endpoint 设备时间线提供设备上观测到的事件和相关警报的时间顺序视图。</span><span class="sxs-lookup"><span data-stu-id="5ce93-111">The Defender for Endpoint device timeline provides a chronological view of the events and associated alerts observed on a device.</span></span> <span data-ttu-id="5ce93-112">通过此事件列表，可以完全查看在设备上观测到的任何事件、文件和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5ce93-112">This list of events provides full visibility into any events, files, and IP addresses observed on the device.</span></span> <span data-ttu-id="5ce93-113">列表有时可能很长。</span><span class="sxs-lookup"><span data-stu-id="5ce93-113">The list can sometimes be lengthy.</span></span> <span data-ttu-id="5ce93-114">设备时间线事件标志可帮助你跟踪可能相关的事件。</span><span class="sxs-lookup"><span data-stu-id="5ce93-114">Device timeline event flags help you track events that could be related.</span></span> 

<span data-ttu-id="5ce93-115">完成设备时间线后，你可以排序、筛选和导出已标记的特定事件。</span><span class="sxs-lookup"><span data-stu-id="5ce93-115">After you've gone through a device timeline, you can sort, filter, and export the specific events that you flagged.</span></span>

<span data-ttu-id="5ce93-116">在导航设备时间线时，你可以搜索和筛选特定事件。</span><span class="sxs-lookup"><span data-stu-id="5ce93-116">While navigating the device timeline, you can search and filter for specific events.</span></span> <span data-ttu-id="5ce93-117">可以通过：设置事件标志：</span><span class="sxs-lookup"><span data-stu-id="5ce93-117">You can set event flags by:</span></span> 

- <span data-ttu-id="5ce93-118">突出显示最重要的事件</span><span class="sxs-lookup"><span data-stu-id="5ce93-118">Highlighting the most important events</span></span> 
- <span data-ttu-id="5ce93-119">标记需要深入探究的事件</span><span class="sxs-lookup"><span data-stu-id="5ce93-119">Marking events that requires deep dive</span></span> 
- <span data-ttu-id="5ce93-120">构建干净泄露时间线</span><span class="sxs-lookup"><span data-stu-id="5ce93-120">Building a clean breach timeline</span></span>



## <a name="flag-an-event"></a><span data-ttu-id="5ce93-121">标记事件</span><span class="sxs-lookup"><span data-stu-id="5ce93-121">Flag an event</span></span>
1. <span data-ttu-id="5ce93-122">查找要标记的事件</span><span class="sxs-lookup"><span data-stu-id="5ce93-122">Find the event that you want to flag</span></span>
2. <span data-ttu-id="5ce93-123">单击"标志"列中的标志图标。</span><span class="sxs-lookup"><span data-stu-id="5ce93-123">Click the flag icon in the Flag column.</span></span> 
<span data-ttu-id="5ce93-124">![设备时间线标志的图像](images/device-flags.png)</span><span class="sxs-lookup"><span data-stu-id="5ce93-124">![Image of device timeline flag](images/device-flags.png)</span></span>

## <a name="view-flagged-events"></a><span data-ttu-id="5ce93-125">查看标记的事件</span><span class="sxs-lookup"><span data-stu-id="5ce93-125">View flagged events</span></span>  
1. <span data-ttu-id="5ce93-126">在"时间线 **筛选器"** 部分，启用 **"已标记的事件"。**</span><span class="sxs-lookup"><span data-stu-id="5ce93-126">In the timeline **Filters** section, enable **Flagged events**.</span></span>
2. <span data-ttu-id="5ce93-127">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="5ce93-127">Click **Apply**.</span></span> <span data-ttu-id="5ce93-128">只显示标记的事件。</span><span class="sxs-lookup"><span data-stu-id="5ce93-128">Only flagged events are displayed.</span></span>
<span data-ttu-id="5ce93-129">可以通过单击时间栏来应用其他筛选器。</span><span class="sxs-lookup"><span data-stu-id="5ce93-129">You can apply additional filters by clicking on the time bar.</span></span> <span data-ttu-id="5ce93-130">这将只显示标记事件之前的事件。</span><span class="sxs-lookup"><span data-stu-id="5ce93-130">This will only show events prior to the flagged event.</span></span>  
<span data-ttu-id="5ce93-131">![具有筛选功能的设备时间线标志的图像](images/device-flag-filter.png)</span><span class="sxs-lookup"><span data-stu-id="5ce93-131">![Image of device timeline flag with filter on](images/device-flag-filter.png)</span></span>
