---
title: Microsoft 威胁防护中的事件概述
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
- m365-initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0cfa6ed4af6ef9c5686cb25d5b2f0522d818860
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412894"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="b0a17-104">Microsoft 威胁防护中的事件概述</span><span class="sxs-lookup"><span data-stu-id="b0a17-104">Incidents overview in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b0a17-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b0a17-105">**Applies to:**</span></span>
- <span data-ttu-id="b0a17-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="b0a17-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="b0a17-107">事件基于相关警报。</span><span class="sxs-lookup"><span data-stu-id="b0a17-107">Incidents are based on related alerts.</span></span> <span data-ttu-id="b0a17-108">当网络中出现恶意事件或活动时，将创建警报。</span><span class="sxs-lookup"><span data-stu-id="b0a17-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="b0a17-109">各个警报提供有关现有攻击的有价值的线索。</span><span class="sxs-lookup"><span data-stu-id="b0a17-109">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="b0a17-110">但是，攻击通常采用各种不同的矢量和技术来发动入侵。</span><span class="sxs-lookup"><span data-stu-id="b0a17-110">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="b0a17-111">将各个线索 Piecing 在一起可能会非常困难且耗时。</span><span class="sxs-lookup"><span data-stu-id="b0a17-111">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="b0a17-112">此简短视频提供 Microsoft 威胁防护中的事件概述。</span><span class="sxs-lookup"><span data-stu-id="b0a17-112">This short video gives an overview of incidents in Microsoft Threat Protection.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="b0a17-113">事件是构成攻击情景的相关警报的集合。</span><span class="sxs-lookup"><span data-stu-id="b0a17-113">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="b0a17-114">在网络中的不同设备、用户和邮箱实体中找到的恶意事件和可疑事件会自动通过 Microsoft 威胁防护进行聚合。</span><span class="sxs-lookup"><span data-stu-id="b0a17-114">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft Threat Protection.</span></span> <span data-ttu-id="b0a17-115">将相关警报分组到事件中可使安全 defenders 全面的攻击视图。</span><span class="sxs-lookup"><span data-stu-id="b0a17-115">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="b0a17-116">例如，安全 defenders 可以查看攻击的启动位置、使用的策略以及攻击已进入网络的程度。</span><span class="sxs-lookup"><span data-stu-id="b0a17-116">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="b0a17-117">他们还可以看到攻击的范围，如受影响的设备、用户和邮箱的数量、影响的严重性以及受影响的实体的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="b0a17-117">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="b0a17-118">如果启用，Microsoft 威胁防护可以通过自动化和人工智能来自动调查和解决各个警报。</span><span class="sxs-lookup"><span data-stu-id="b0a17-118">If enabled, Microsoft Threat Protection can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="b0a17-119">安全 defenders 还可以执行其他补救步骤，以便从事件视图中直接解决攻击。</span><span class="sxs-lookup"><span data-stu-id="b0a17-119">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="b0a17-120">来自最近30天的事件显示在事件队列中。</span><span class="sxs-lookup"><span data-stu-id="b0a17-120">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="b0a17-121">在此，安全 defenders 可以根据风险级别和其他因素查看应优先考虑的事件。</span><span class="sxs-lookup"><span data-stu-id="b0a17-121">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="b0a17-122">安全 defenders 还可以将事件重命名、将其分配给各个分析人员、分类并将标记添加到事件中，以实现更好更好的自定义事件管理体验。</span><span class="sxs-lookup"><span data-stu-id="b0a17-122">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="b0a17-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0a17-123">See also</span></span>
- [<span data-ttu-id="b0a17-124">确定事件优先级</span><span class="sxs-lookup"><span data-stu-id="b0a17-124">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="b0a17-125">调查事件</span><span class="sxs-lookup"><span data-stu-id="b0a17-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="b0a17-126">管理事件</span><span class="sxs-lookup"><span data-stu-id="b0a17-126">Manage incidents</span></span>](manage-incidents.md)
