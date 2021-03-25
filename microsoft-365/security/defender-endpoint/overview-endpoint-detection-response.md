---
title: 终结点检测和响应功能概述
ms.reviewer: ''
description: 了解 Microsoft Defender ATP 中的终结点检测和响应功能
keywords: ''
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
ms.openlocfilehash: 0a5a665fac1883016ac222197ba8322f78e2558f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186169"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="4835d-103">终结点检测和响应概述</span><span class="sxs-lookup"><span data-stu-id="4835d-103">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4835d-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4835d-104">**Applies to:**</span></span>
- [<span data-ttu-id="4835d-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4835d-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4835d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4835d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4835d-107">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4835d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4835d-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4835d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="4835d-109">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span><span class="sxs-lookup"><span data-stu-id="4835d-109">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="4835d-110">安全分析员可以有效地确定警报的优先级，了解整个泄露范围，并采取响应措施来修正威胁。</span><span class="sxs-lookup"><span data-stu-id="4835d-110">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="4835d-111">检测到威胁时，将在系统中创建警报以供分析人员进行调查。</span><span class="sxs-lookup"><span data-stu-id="4835d-111">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="4835d-112">使用相同攻击技术或归属于同一攻击者的警报会被聚合到名为 _“事件”_ 的实体中。</span><span class="sxs-lookup"><span data-stu-id="4835d-112">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="4835d-113">以此方式聚合警报可便于分析员更轻松地综合调查和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="4835d-113">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="4835d-114">受"假设泄露"意识启发，Defender for Endpoint 持续收集行为网络遥测。</span><span class="sxs-lookup"><span data-stu-id="4835d-114">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="4835d-115">其中包括流程信息、网络活动、内核和内存管理程序的深入信息、用户登录活动、注册表和文件系统更改等。</span><span class="sxs-lookup"><span data-stu-id="4835d-115">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="4835d-116">此类信息存储六个月，这样分析员可以追溯到攻击开始的时间。</span><span class="sxs-lookup"><span data-stu-id="4835d-116">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="4835d-117">然后，分析员可以对各种视图进行透视，并通过多个攻击途径展开调查。</span><span class="sxs-lookup"><span data-stu-id="4835d-117">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="4835d-118">借助响应功能，可以对受影响的实体采取行动，从而快速修正威胁。</span><span class="sxs-lookup"><span data-stu-id="4835d-118">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="4835d-119">相关主题</span><span class="sxs-lookup"><span data-stu-id="4835d-119">Related topics</span></span>
- [<span data-ttu-id="4835d-120">安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="4835d-120">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="4835d-121">事件队列</span><span class="sxs-lookup"><span data-stu-id="4835d-121">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="4835d-122">警报队列</span><span class="sxs-lookup"><span data-stu-id="4835d-122">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="4835d-123">设备列表</span><span class="sxs-lookup"><span data-stu-id="4835d-123">Devices list</span></span>](machines-view-overview.md)

