---
title: 查看 Microsoft Defender for Endpoint 中的警报
description: 查看警报信息，包括可视化警报情景和链每个步骤的详细信息。
keywords: 事件， 事件， 计算机， 设备， 用户， 警报， 警报， 调查， 图形， 证据
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b791f2b62cb4a3f8062c80ceeb04ccfa72f704bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054926"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="ab6d9-104">查看 Microsoft Defender for Endpoint 中的警报</span><span class="sxs-lookup"><span data-stu-id="ab6d9-104">Review alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ab6d9-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ab6d9-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab6d9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ab6d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="ab6d9-107">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="ab6d9-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab6d9-108">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="ab6d9-109">Microsoft Defender for Endpoint 中的警报页面通过组合与所选警报相关的攻击信号和警报，为警报提供完整的上下文，以构建详细的警报情景。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-109">The alert page in Microsoft Defender for Endpoint provides full context to the alert, by combining attack signals and alerts related to the selected alert, to construct a detailed alert story.</span></span>

<span data-ttu-id="ab6d9-110">对影响组织的警报快速会审、调查和采取有效操作。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-110">Quickly triage, investigate, and take effective action on alerts that affect your organization.</span></span> <span data-ttu-id="ab6d9-111">了解触发它们的原因，及其从一个位置的影响。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-111">Understand why they were triggered, and their impact from one location.</span></span> <span data-ttu-id="ab6d9-112">有关详细信息，请在此概述中了解。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-112">Learn more in this overview.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a><span data-ttu-id="ab6d9-113">警报入门</span><span class="sxs-lookup"><span data-stu-id="ab6d9-113">Getting started with an alert</span></span>

<span data-ttu-id="ab6d9-114">在 Defender for Endpoint 中选择警报的名称将让你访问其警报页面。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-114">Selecting an alert's name in Defender for Endpoint will land you on its alert page.</span></span> <span data-ttu-id="ab6d9-115">在警报页面上，所有信息都将在所选警报的上下文中显示。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-115">On the alert page, all the information will be shown in context of the selected alert.</span></span> <span data-ttu-id="ab6d9-116">每个警报页面包含 4 个部分：</span><span class="sxs-lookup"><span data-stu-id="ab6d9-116">Each alert page consists of 4 sections:</span></span>

1. <span data-ttu-id="ab6d9-117">**警报标题** 显示警报的名称，并提醒你哪个警报启动了当前调查，无论你在页面上选择了什么内容。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-117">**The alert title** shows the alert's name and is there to remind you which alert started your current investigation regardless of what you have selected on the page.</span></span>
2. <span data-ttu-id="ab6d9-118">[**受影响的资产**](#review-affected-assets) 列出了受此警报影响的设备和用户的卡片，可单击这些卡片了解详细信息和操作。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-118">[**Affected assets**](#review-affected-assets) lists cards of devices and users affected by this alert that are clickable for further information and actions.</span></span>
3. <span data-ttu-id="ab6d9-119">警报 **情景** 通过树视图显示与警报相关的所有实体。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-119">The **alert story** displays all entities related to the alert, interconnected by a tree view.</span></span> <span data-ttu-id="ab6d9-120">当你首次登录所选警报的页面时，标题中的警报将是焦点。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-120">The alert in the title will be the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="ab6d9-121">警报情景中的实体可展开且可单击，通过允许您在警报页面上下文中立即采取措施来提供其他信息并加快响应速度。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-121">Entities in the alert story are expandable and clickable, to provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> <span data-ttu-id="ab6d9-122">使用警报情景开始调查。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-122">Use the alert story to start your investigation.</span></span> <span data-ttu-id="ab6d9-123">在调查 [Microsoft Defender for Endpoint 中的警报中了解如何](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)操作。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-123">Learn how in [Investigate alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>
4. <span data-ttu-id="ab6d9-124">详细信息 **窗格** 将首先显示所选警报的详细信息，以及与此警报相关的详细信息和操作。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-124">The **details pane** will show the details of the selected alert at first, with details and actions related to this alert.</span></span> <span data-ttu-id="ab6d9-125">如果在警报情景中选择任何受影响的资产或实体，详细信息窗格将更改为提供所选对象的上下文信息和操作。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-125">If you select any of the affected assets or entities in the alert story, the details pane will change to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="ab6d9-126">记下警报的检测状态。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-126">Note the detection status for your alert.</span></span> 
- <span data-ttu-id="ab6d9-127">已阻止 – 已避免尝试的可疑操作。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-127">Prevented – The attempted suspicious action was avoided.</span></span> <span data-ttu-id="ab6d9-128">例如，文件未写入磁盘或已执行。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-128">For example, a file either wasn’t written to disk or executed.</span></span>
<span data-ttu-id="ab6d9-129">![显示已阻止威胁的警报页面](images/detstat-prevented.png)</span><span class="sxs-lookup"><span data-stu-id="ab6d9-129">![An alert page showing threat was prevented](images/detstat-prevented.png)</span></span>
- <span data-ttu-id="ab6d9-130">已阻止 – 已执行可疑行为，然后阻止。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-130">Blocked – Suspicious behavior was executed and then blocked.</span></span> <span data-ttu-id="ab6d9-131">例如，进程已执行，但由于它随后呈现了可疑行为，因此进程已终止。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-131">For example, a process was executed but because it subsequently exhibited suspicious behaviors, the process was terminated.</span></span>
<span data-ttu-id="ab6d9-132">![显示已阻止威胁的警报页面](images/detstat-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="ab6d9-132">![An alert page showing threat was blocked](images/detstat-blocked.png)</span></span>
- <span data-ttu-id="ab6d9-133">检测到 – 检测到攻击，并且可能仍处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-133">Detected – An attack was detected and is possibly still active.</span></span>
<span data-ttu-id="ab6d9-134">![显示检测到威胁的警报页面](images/detstat-detected.png)</span><span class="sxs-lookup"><span data-stu-id="ab6d9-134">![An alert page showing threat was detected](images/detstat-detected.png)</span></span>




<span data-ttu-id="ab6d9-135">然后，还可以在警报的详细信息窗格中查看自动调查详细信息，查看已采取的操作，并阅读警报的说明，了解建议的操作。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-135">You can then also review the *automated investigation details* in your alert's details pane, to see which actions were already taken, as well as reading the alert's description for recommended actions.</span></span>

![突出显示了警报说明和自动调查部分的详细信息窗格的代码段](images/alert-air-and-alert-description.png)

<span data-ttu-id="ab6d9-137">当警报打开时，详细信息窗格中提供的其他信息包括 MITRE 技术、源和其他上下文详细信息。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-137">Other information available in the details pane when the alert opens includes MITRE techniques, source, and additional contextual details.</span></span>




## <a name="review-affected-assets"></a><span data-ttu-id="ab6d9-138">查看受影响的资产</span><span class="sxs-lookup"><span data-stu-id="ab6d9-138">Review affected assets</span></span>

<span data-ttu-id="ab6d9-139">在受影响的资源部分中选择设备或用户卡片将在详细信息窗格中切换到设备或用户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-139">Selecting a device or a user card in the affected assets sections will switch to the details of the device or user in the details pane.</span></span>

- <span data-ttu-id="ab6d9-140">**对于设备**，详细信息窗格将显示有关设备本身的信息，如域、操作系统和 IP。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-140">**For devices**, the details pane will display information about the device itself, like Domain, Operating System, and IP.</span></span> <span data-ttu-id="ab6d9-141">Active alerts and the logged on users on that device are also available.</span><span class="sxs-lookup"><span data-stu-id="ab6d9-141">Active alerts and the logged on users on that device are also available.</span></span> <span data-ttu-id="ab6d9-142">可以通过隔离设备、限制应用执行或运行防病毒扫描来立即采取措施。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-142">You can take immediate action by isolating the device, restricting app execution, or running an antivirus scan.</span></span> <span data-ttu-id="ab6d9-143">或者，你可以收集调查包、启动自动调查，或者从设备的角度转到设备页面进行调查。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-143">Alternatively, you could collect an investigation package, initiate an automated investigation, or go to the device page to investigate from the device's point of view.</span></span>

   ![选择设备时详细信息窗格的代码段](images/device-page-details.png)

- <span data-ttu-id="ab6d9-145">**对于用户**，详细信息窗格将显示详细的用户信息，如用户的 SAM 名称和 SID，以及此用户执行的登录类型以及任何与该用户相关的警报和事件。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-145">**For users**, the details pane will display detailed user information, such as the user's SAM name and SID, as well as logon types performed by this user and any alerts and incidents related to it.</span></span> <span data-ttu-id="ab6d9-146">可以选择" *打开用户页面* "以从该用户的角度继续调查。</span><span class="sxs-lookup"><span data-stu-id="ab6d9-146">You can select *Open user page* to continue the investigation from that user's point of view.</span></span>

   ![选择用户时详细信息窗格的代码段](images/user-page-details.png)


## <a name="related-topics"></a><span data-ttu-id="ab6d9-148">相关主题</span><span class="sxs-lookup"><span data-stu-id="ab6d9-148">Related topics</span></span>

- [<span data-ttu-id="ab6d9-149">查看和组织事件队列</span><span class="sxs-lookup"><span data-stu-id="ab6d9-149">View and organize the incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="ab6d9-150">调查事件</span><span class="sxs-lookup"><span data-stu-id="ab6d9-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="ab6d9-151">管理事件</span><span class="sxs-lookup"><span data-stu-id="ab6d9-151">Manage incidents</span></span>](manage-incidents.md)
