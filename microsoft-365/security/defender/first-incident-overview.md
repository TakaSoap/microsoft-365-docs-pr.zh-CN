---
title: 第一个事件响应简介
description: 在 Defender 中响应第一个事件的Microsoft 365基础知识。
keywords: 事件， 警报， 调查， 关联， 攻击， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: f66c9821e5db00cc3da5718f52b8aaaeff5a431e
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114531"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="8595c-104">第一个事件响应简介</span><span class="sxs-lookup"><span data-stu-id="8595c-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8595c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8595c-105">**Applies to:**</span></span>
- <span data-ttu-id="8595c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8595c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8595c-107">组织的事件响应策略决定了其处理破坏性不断增加的安全事件和混乱的能力。</span><span class="sxs-lookup"><span data-stu-id="8595c-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="8595c-108">采取预防性措施很重要，但快速采取行动以控制、抑制和从检测到的事件中恢复的能力可以最大限度地减少损失和业务损失。</span><span class="sxs-lookup"><span data-stu-id="8595c-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="8595c-109">此事件响应演练演示了作为安全运营团队的一部分，如何在 Microsoft 365 Defender 中执行主要事件响应步骤。</span><span class="sxs-lookup"><span data-stu-id="8595c-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="8595c-110">步骤如下：</span><span class="sxs-lookup"><span data-stu-id="8595c-110">Here are the steps:</span></span>

- <span data-ttu-id="8595c-111">准备安全状态</span><span class="sxs-lookup"><span data-stu-id="8595c-111">Preparation of your security posture</span></span>
- <span data-ttu-id="8595c-112">对于每个事件：</span><span class="sxs-lookup"><span data-stu-id="8595c-112">For each incident:</span></span>
  - <span data-ttu-id="8595c-113">步骤 1：会审和分析</span><span class="sxs-lookup"><span data-stu-id="8595c-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="8595c-114">步骤 2： (控制、抑制和恢复) </span><span class="sxs-lookup"><span data-stu-id="8595c-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="8595c-115">步骤 3：事后评审</span><span class="sxs-lookup"><span data-stu-id="8595c-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="8595c-116">美国国家标准和技术协会 NIST () 将安全事件定义为"实际或可能危及信息系统的机密性、完整性或可用性的事件;或系统处理、存储或传输的信息;或构成违反安全策略、安全程序或可接受使用策略的违反或即将发生的威胁。"</span><span class="sxs-lookup"><span data-stu-id="8595c-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="8595c-117">Microsoft 365 Defender 中的事件是分析和事件响应的逻辑起点。</span><span class="sxs-lookup"><span data-stu-id="8595c-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="8595c-118">分析和修正事件通常包括安全运营团队大部分任务。</span><span class="sxs-lookup"><span data-stu-id="8595c-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="8595c-119">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8595c-119">Next step</span></span>

<span data-ttu-id="8595c-120">[![准备你的组织和Microsoft 365租户](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="8595c-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="8595c-121">请确保你的组织和租户Microsoft 365[事件处理做好准备](first-incident-prepare.md)。</span><span class="sxs-lookup"><span data-stu-id="8595c-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8595c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8595c-122">See also</span></span>

- [<span data-ttu-id="8595c-123">事件概述</span><span class="sxs-lookup"><span data-stu-id="8595c-123">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="8595c-124">分析事件</span><span class="sxs-lookup"><span data-stu-id="8595c-124">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="8595c-125">管理事件</span><span class="sxs-lookup"><span data-stu-id="8595c-125">Manage incidents</span></span>](manage-incidents.md)
