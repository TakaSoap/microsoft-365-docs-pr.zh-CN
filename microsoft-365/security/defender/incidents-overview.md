---
title: Microsoft 365 Defender 中的事件
description: 调查在设备、用户和邮箱中看到的事件。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
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
ms.openlocfilehash: 5b2baa2041a8cffcea212eb449d40b9a9cbfc22a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759482"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="eed86-104">Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="eed86-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="eed86-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="eed86-105">**Applies to:**</span></span>
- <span data-ttu-id="eed86-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eed86-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="eed86-107">希望体验 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="eed86-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="eed86-108">你可[在验室环境中评估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[生产中运行试点项目](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="eed86-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="eed86-109">Microsoft 365 Defender 中的事件是关联警报和关联数据的集合，这些警报和关联数据是攻击案例的一部分。</span><span class="sxs-lookup"><span data-stu-id="eed86-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="eed86-110">Microsoft 365 服务和应用在检测到可疑或恶意事件或活动时创建警报。</span><span class="sxs-lookup"><span data-stu-id="eed86-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="eed86-111">个别警报提供有关已完成或持续攻击的有价值的线索。</span><span class="sxs-lookup"><span data-stu-id="eed86-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="eed86-112">但是，攻击通常对不同类型的实体（如设备、用户和邮箱）使用各种技术。</span><span class="sxs-lookup"><span data-stu-id="eed86-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="eed86-113">结果是租户中多个实体收到多个警报。</span><span class="sxs-lookup"><span data-stu-id="eed86-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="eed86-114">由于将各个警报分组在一起以深入了解攻击可能非常困难且耗时，因此 Microsoft 365 Defender 会自动将警报及其相关信息聚合到事件中。</span><span class="sxs-lookup"><span data-stu-id="eed86-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender 如何将实体中的事件关联到事件中":::

<span data-ttu-id="eed86-116">观看此简短概述，了解 Microsoft 365 Defender (4 分钟) 。</span><span class="sxs-lookup"><span data-stu-id="eed86-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="eed86-117">将相关警报分组到事件可为你提供攻击的全面视图。</span><span class="sxs-lookup"><span data-stu-id="eed86-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="eed86-118">例如，可以看到：</span><span class="sxs-lookup"><span data-stu-id="eed86-118">For example, you can see:</span></span>

- <span data-ttu-id="eed86-119">攻击的开始位置。</span><span class="sxs-lookup"><span data-stu-id="eed86-119">Where the attack started.</span></span>
- <span data-ttu-id="eed86-120">使用了哪些策略。</span><span class="sxs-lookup"><span data-stu-id="eed86-120">What tactics were used.</span></span>
- <span data-ttu-id="eed86-121">攻击已进入你的租户多远。</span><span class="sxs-lookup"><span data-stu-id="eed86-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="eed86-122">攻击范围，如影响的设备、用户和邮箱数量。</span><span class="sxs-lookup"><span data-stu-id="eed86-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="eed86-123">与攻击关联的所有数据。</span><span class="sxs-lookup"><span data-stu-id="eed86-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="eed86-124">如果 [启用，Microsoft](m365d-enable.md)365 Defender 可以通过自动化和人工智能自动调查和解决警报。</span><span class="sxs-lookup"><span data-stu-id="eed86-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="eed86-125">还可以执行其他修正步骤来解决攻击。</span><span class="sxs-lookup"><span data-stu-id="eed86-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="eed86-126">Microsoft 365 安全中心中的事件和警报</span><span class="sxs-lookup"><span data-stu-id="eed86-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="eed86-127">在快速启动 Microsoft  365 安全中心&事件>事件或事件管理事件 (security.microsoft.com) 。 [](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="eed86-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="eed86-128">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="eed86-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 安全中心中的&quot;事件&quot;页面":::

<span data-ttu-id="eed86-130">选择事件名称将显示事件摘要，并提供对包含其他信息的选项卡的访问权限。</span><span class="sxs-lookup"><span data-stu-id="eed86-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 安全中心内事件的&quot;摘要&quot;页面示例":::

<span data-ttu-id="eed86-132">事件的其他选项卡包括：</span><span class="sxs-lookup"><span data-stu-id="eed86-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="eed86-133">警报</span><span class="sxs-lookup"><span data-stu-id="eed86-133">Alerts</span></span> 

  <span data-ttu-id="eed86-134">与事件及其信息相关的所有警报。</span><span class="sxs-lookup"><span data-stu-id="eed86-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="eed86-135">设备</span><span class="sxs-lookup"><span data-stu-id="eed86-135">Devices</span></span>

  <span data-ttu-id="eed86-136">标识为事件的一部分或与事件相关的所有设备。</span><span class="sxs-lookup"><span data-stu-id="eed86-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="eed86-137">用户</span><span class="sxs-lookup"><span data-stu-id="eed86-137">Users</span></span>

  <span data-ttu-id="eed86-138">标识为事件的一部分或与事件相关的所有用户。</span><span class="sxs-lookup"><span data-stu-id="eed86-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="eed86-139">邮箱</span><span class="sxs-lookup"><span data-stu-id="eed86-139">Mailboxes</span></span>

  <span data-ttu-id="eed86-140">已标识为事件的一部分或与事件相关的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="eed86-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="eed86-141">调查</span><span class="sxs-lookup"><span data-stu-id="eed86-141">Investigations</span></span>

  <span data-ttu-id="eed86-142">事件警报触发的所有自动调查。</span><span class="sxs-lookup"><span data-stu-id="eed86-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="eed86-143">证据和响应</span><span class="sxs-lookup"><span data-stu-id="eed86-143">Evidence and Response</span></span>

  <span data-ttu-id="eed86-144">事件警报中支持的所有事件和可疑实体。</span><span class="sxs-lookup"><span data-stu-id="eed86-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="eed86-145">下面是 Microsoft 365 安全中心内事件及其数据与事件选项卡之间的关系。</span><span class="sxs-lookup"><span data-stu-id="eed86-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Microsoft 365 安全中心内事件及其数据与事件选项卡的关系":::

## <a name="next-step"></a><span data-ttu-id="eed86-147">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eed86-147">Next step</span></span>

<span data-ttu-id="eed86-148">"事件"页 **中的事件** 队列列出了最近事件。</span><span class="sxs-lookup"><span data-stu-id="eed86-148">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="eed86-149">在这里，你可以：</span><span class="sxs-lookup"><span data-stu-id="eed86-149">From here, you can:</span></span>

- <span data-ttu-id="eed86-150">查看应基于严重性 [和](incident-queue.md) 其他因素对哪些事件进行优先排序。</span><span class="sxs-lookup"><span data-stu-id="eed86-150">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="eed86-151">对 [事件](investigate-incidents.md) 进行调查。</span><span class="sxs-lookup"><span data-stu-id="eed86-151">Perform an [investigation](investigate-incidents.md) of an incident.</span></span>
- <span data-ttu-id="eed86-152">[管理事件](manage-incidents.md)，包括重命名、分配事件、对事件管理工作流进行分类和添加标记。</span><span class="sxs-lookup"><span data-stu-id="eed86-152">[Manage incidents](manage-incidents.md), which includes renaming, assigning them, classifying, and adding tags for your incident management workflow.</span></span>
