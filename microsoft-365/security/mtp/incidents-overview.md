---
title: Microsoft 365 Defender 中的事件概述
description: 调查在设备、用户和邮箱中看到的事件。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7fcbecddd5e8f83e9c78d6db90939fbfc2f2df07
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929278"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="f6dbd-104">Microsoft 365 Defender 中的事件概述</span><span class="sxs-lookup"><span data-stu-id="f6dbd-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f6dbd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f6dbd-105">**Applies to:**</span></span>
- <span data-ttu-id="f6dbd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6dbd-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="f6dbd-107">想要体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="f6dbd-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="f6dbd-108">可以在[实验室环境中对其进行评估或在](https://aka.ms/mtp-trial-lab)[生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="f6dbd-109">事件基于相关警报。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="f6dbd-110">当网络中出现恶意事件或活动时，将创建警报。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="f6dbd-111">个别警报提供有关进行中攻击的有价值的线索。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="f6dbd-112">但是，攻击通常使用各种矢量和技术来实施入侵。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="f6dbd-113">将各个线索拼合在一起可能非常困难且耗时。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="f6dbd-114">此简短视频概述了 Microsoft 365 Defender 中的事件。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="f6dbd-115">事件是相关警报的集合，这些警报是攻击的一部分。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="f6dbd-116">Microsoft 365 Defender 会自动聚合网络中不同设备、用户和邮箱实体中的恶意和可疑事件。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="f6dbd-117">将相关警报分组到事件后，安全防御者可以全面查看攻击。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="f6dbd-118">例如，安全防御者可以看到攻击的开始位置、使用的策略以及攻击已进入网络多远。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="f6dbd-119">他们还可以查看攻击的范围，如受影响的设备、用户和邮箱数量、影响严重，以及受影响实体的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="f6dbd-120">如果启用，Microsoft 365 Defender 可以通过自动化和人工智能自动调查和解决个别警报。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="f6dbd-121">安全防御者还可以执行其他修正步骤，直接从事件视图解决攻击。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="f6dbd-122">最近 30 天的事件显示在事件队列中。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="f6dbd-123">从此处，安全防御者可以看到哪些事件应基于风险级别和其他因素确定优先级。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="f6dbd-124">安全防御者还可以重命名事件、将其分配给各个分析员、对事件进行分类和添加标记，以提供更好的和自定义的事件管理体验。</span><span class="sxs-lookup"><span data-stu-id="f6dbd-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="f6dbd-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6dbd-125">See also</span></span>
- [<span data-ttu-id="f6dbd-126">确定事件优先级</span><span class="sxs-lookup"><span data-stu-id="f6dbd-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="f6dbd-127">调查事件</span><span class="sxs-lookup"><span data-stu-id="f6dbd-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="f6dbd-128">管理事件</span><span class="sxs-lookup"><span data-stu-id="f6dbd-128">Manage incidents</span></span>](manage-incidents.md)
