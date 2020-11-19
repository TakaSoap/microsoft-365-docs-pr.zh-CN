---
title: Microsoft 365 Defender 中的事件概述
description: 调查在设备、用户和邮箱中看到的事件。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 6149b6f128b3c96d2338e325caa8df835c292b13
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357607"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="bcded-104">Microsoft 365 Defender 中的事件概述</span><span class="sxs-lookup"><span data-stu-id="bcded-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bcded-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bcded-105">**Applies to:**</span></span>
- <span data-ttu-id="bcded-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bcded-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="bcded-107">想要体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="bcded-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="bcded-108">您可以 [在实验室环境中对其进行评估](https://aka.ms/mtp-trial-lab) ，也可以 [在生产中运行试点项目](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="bcded-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="bcded-109">事件基于相关警报。</span><span class="sxs-lookup"><span data-stu-id="bcded-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="bcded-110">当网络中出现恶意事件或活动时，将创建警报。</span><span class="sxs-lookup"><span data-stu-id="bcded-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="bcded-111">各个警报提供有关现有攻击的有价值的线索。</span><span class="sxs-lookup"><span data-stu-id="bcded-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="bcded-112">但是，攻击通常采用各种不同的矢量和技术来发动入侵。</span><span class="sxs-lookup"><span data-stu-id="bcded-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="bcded-113">将各个线索 Piecing 在一起可能会非常困难且耗时。</span><span class="sxs-lookup"><span data-stu-id="bcded-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="bcded-114">此简短视频提供了 Microsoft 365 Defender 中的事件概述。</span><span class="sxs-lookup"><span data-stu-id="bcded-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="bcded-115">事件是构成攻击情景的相关警报的集合。</span><span class="sxs-lookup"><span data-stu-id="bcded-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="bcded-116">在网络中的不同设备、用户和邮箱实体中找到的恶意事件和可疑事件会自动由 Microsoft 365 Defender 进行聚合。</span><span class="sxs-lookup"><span data-stu-id="bcded-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="bcded-117">将相关警报分组到事件中可使安全 defenders 全面的攻击视图。</span><span class="sxs-lookup"><span data-stu-id="bcded-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="bcded-118">例如，安全 defenders 可以查看攻击的启动位置、使用的策略以及攻击已进入网络的程度。</span><span class="sxs-lookup"><span data-stu-id="bcded-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="bcded-119">他们还可以看到攻击的范围，如受影响的设备、用户和邮箱的数量、影响的严重性以及受影响的实体的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="bcded-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="bcded-120">如果启用此功能，则 Microsoft 365 Defender 可以通过自动化和人工智能自动调查和解决各个警报。</span><span class="sxs-lookup"><span data-stu-id="bcded-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="bcded-121">安全 defenders 还可以执行其他补救步骤，以便从事件视图中直接解决攻击。</span><span class="sxs-lookup"><span data-stu-id="bcded-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="bcded-122">来自最近30天的事件显示在事件队列中。</span><span class="sxs-lookup"><span data-stu-id="bcded-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="bcded-123">在此，安全 defenders 可以根据风险级别和其他因素查看应优先考虑的事件。</span><span class="sxs-lookup"><span data-stu-id="bcded-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="bcded-124">安全 defenders 还可以将事件重命名、将其分配给各个分析人员、分类并将标记添加到事件中，以实现更好更好的自定义事件管理体验。</span><span class="sxs-lookup"><span data-stu-id="bcded-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="bcded-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcded-125">See also</span></span>
- [<span data-ttu-id="bcded-126">确定事件优先级</span><span class="sxs-lookup"><span data-stu-id="bcded-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="bcded-127">调查事件</span><span class="sxs-lookup"><span data-stu-id="bcded-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="bcded-128">管理事件</span><span class="sxs-lookup"><span data-stu-id="bcded-128">Manage incidents</span></span>](manage-incidents.md)
