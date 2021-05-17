---
title: 终结点检测和响应功能概述
ms.reviewer: ''
description: 了解 Microsoft Defender for Endpoint 中的终结点检测和响应功能
keywords: 适用于终结点的 Microsoft Defender， 终结点检测和响应， 响应， 检测， 网络安全， 保护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b00bef611a3e4b33bf15a5366b09a96f68d4c1a2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933513"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="24155-104">终结点检测和响应概述</span><span class="sxs-lookup"><span data-stu-id="24155-104">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="24155-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="24155-105">**Applies to:**</span></span>
- [<span data-ttu-id="24155-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="24155-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24155-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24155-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="24155-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="24155-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="24155-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="24155-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="24155-110">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span><span class="sxs-lookup"><span data-stu-id="24155-110">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="24155-111">安全分析员可以有效地确定警报的优先级，了解整个泄露范围，并采取响应措施来修正威胁。</span><span class="sxs-lookup"><span data-stu-id="24155-111">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="24155-112">检测到威胁时，将在系统中创建警报以供分析人员进行调查。</span><span class="sxs-lookup"><span data-stu-id="24155-112">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="24155-113">使用相同攻击技术或归属于同一攻击者的警报会被聚合到名为 _“事件”_ 的实体中。</span><span class="sxs-lookup"><span data-stu-id="24155-113">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="24155-114">以此方式聚合警报可便于分析员更轻松地综合调查和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="24155-114">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="24155-115">受"假设泄露"意识启发，Defender for Endpoint 持续收集行为网络遥测。</span><span class="sxs-lookup"><span data-stu-id="24155-115">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="24155-116">其中包括流程信息、网络活动、内核和内存管理程序的深入信息、用户登录活动、注册表和文件系统更改等。</span><span class="sxs-lookup"><span data-stu-id="24155-116">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="24155-117">此类信息存储六个月，这样分析员可以追溯到攻击开始的时间。</span><span class="sxs-lookup"><span data-stu-id="24155-117">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="24155-118">然后，分析员可以对各种视图进行透视，并通过多个攻击途径展开调查。</span><span class="sxs-lookup"><span data-stu-id="24155-118">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="24155-119">借助响应功能，可以对受影响的实体采取行动，从而快速修正威胁。</span><span class="sxs-lookup"><span data-stu-id="24155-119">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="24155-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="24155-120">Related topics</span></span>
- [<span data-ttu-id="24155-121">安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="24155-121">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="24155-122">事件队列</span><span class="sxs-lookup"><span data-stu-id="24155-122">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="24155-123">警报队列</span><span class="sxs-lookup"><span data-stu-id="24155-123">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="24155-124">设备列表</span><span class="sxs-lookup"><span data-stu-id="24155-124">Devices list</span></span>](machines-view-overview.md)

