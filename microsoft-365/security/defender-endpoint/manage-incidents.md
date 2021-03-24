---
title: 管理 Microsoft Defender ATP 事件
description: 通过分配事件、更新其状态或设置其分类来管理事件。
keywords: 事件， 管理， 分配， 状态， 分类， 真警报， 假警报
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 412938e506895aaabfa0796cb1d46ea892876435
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054931"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="99420-104">管理 Microsoft Defender 终结点事件</span><span class="sxs-lookup"><span data-stu-id="99420-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="99420-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="99420-105">**Applies to:**</span></span>
- [<span data-ttu-id="99420-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="99420-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="99420-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99420-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="99420-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="99420-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="99420-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="99420-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="99420-110">管理事件是每个网络安全操作的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="99420-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="99420-111">可以通过从"事件"队列或"事件管理"窗格中选择事件 **来管理事件**。</span><span class="sxs-lookup"><span data-stu-id="99420-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="99420-112">从事件队列中 **选择事件将** 打开"事件管理"窗格，您可以在其中打开事件页面了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="99420-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![事件管理窗格的图像](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="99420-114">你可以为自己分配事件、更改状态和分类、重命名或注释它们以跟踪其进度。</span><span class="sxs-lookup"><span data-stu-id="99420-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="99420-115">为了一目了然，事件名称会基于警报属性自动生成，如受影响的终结点数量、受影响的用户、检测源或类别。</span><span class="sxs-lookup"><span data-stu-id="99420-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="99420-116">这使您可以快速了解事件的范围。</span><span class="sxs-lookup"><span data-stu-id="99420-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="99420-117">例如： *多个源报告的多个终结点上的多阶段事件。*</span><span class="sxs-lookup"><span data-stu-id="99420-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="99420-118">在推出自动事件命名之前已存在的事件将保留其名称。</span><span class="sxs-lookup"><span data-stu-id="99420-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![事件详细信息页面的图像](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="99420-120">分配事件</span><span class="sxs-lookup"><span data-stu-id="99420-120">Assign incidents</span></span>
<span data-ttu-id="99420-121">如果尚未分配事件，可以选择"分配给 **我** "将事件分配给自己。</span><span class="sxs-lookup"><span data-stu-id="99420-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="99420-122">执行此操作时，假定所有权不仅限于事件，而且还针对与之关联的所有警报。</span><span class="sxs-lookup"><span data-stu-id="99420-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="99420-123">设置状态和分类</span><span class="sxs-lookup"><span data-stu-id="99420-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="99420-124">事件状态</span><span class="sxs-lookup"><span data-stu-id="99420-124">Incident status</span></span>
<span data-ttu-id="99420-125">可通过在调查期间更改事件的状态来为事件分类（例如“活动”或“已解决”）。</span><span class="sxs-lookup"><span data-stu-id="99420-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="99420-126">这可帮助你整理和管理团队对事件的响应方式。</span><span class="sxs-lookup"><span data-stu-id="99420-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="99420-127">例如，SoC 分析师可以审阅当天的紧急 **活动** 事件，并决定将其分配给自己进行调查。</span><span class="sxs-lookup"><span data-stu-id="99420-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="99420-128">或者，如果事件已修复，SoC 分析师可能会将事件设置为"已解决"。</span><span class="sxs-lookup"><span data-stu-id="99420-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="99420-129">分类</span><span class="sxs-lookup"><span data-stu-id="99420-129">Classification</span></span>
<span data-ttu-id="99420-130">可以选择不设置分类，也可以决定指定事件为真实/误报事件。</span><span class="sxs-lookup"><span data-stu-id="99420-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="99420-131">这样做有助于团队查看模式并从中了解相关信息。</span><span class="sxs-lookup"><span data-stu-id="99420-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="99420-132">添加备注</span><span class="sxs-lookup"><span data-stu-id="99420-132">Add comments</span></span>
<span data-ttu-id="99420-133">可以添加备注并查看有关事件的历史事件，以便了解以前对其所做的更改。</span><span class="sxs-lookup"><span data-stu-id="99420-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="99420-134">每当对警报进行更改或添加备注时，都会在“备注”和“历史记录”部分进行记录。</span><span class="sxs-lookup"><span data-stu-id="99420-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="99420-135">添加的备注会立即显示在窗格中。</span><span class="sxs-lookup"><span data-stu-id="99420-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="99420-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="99420-136">Related topics</span></span>
- [<span data-ttu-id="99420-137">事件队列</span><span class="sxs-lookup"><span data-stu-id="99420-137">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="99420-138">查看和组织事件队列</span><span class="sxs-lookup"><span data-stu-id="99420-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="99420-139">调查事件</span><span class="sxs-lookup"><span data-stu-id="99420-139">Investigate incidents</span></span>](investigate-incidents.md)
