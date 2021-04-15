---
title: 在 Microsoft 365 Defender 中管理事件
description: 了解如何分配、更新状态
keywords: 事件, 事件, 警报, 相关警报, 分配, 更新, 状态, 管理, 分类, microsoft, 365, m365
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
ms.openlocfilehash: 2d2bf18c6cacb377e710f34b74ec8f83bb77d3b1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760059"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="d4433-104">在 Microsoft 365 Defender 中管理事件</span><span class="sxs-lookup"><span data-stu-id="d4433-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d4433-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d4433-105">**Applies to:**</span></span>
- <span data-ttu-id="d4433-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4433-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d4433-107">事件管理对于确保包含和解决威胁至关重要。</span><span class="sxs-lookup"><span data-stu-id="d4433-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="d4433-108">在快速启动 Microsoft  365 安全中心&事件>事件或事件管理事件 (security.microsoft.com) 。 [](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d4433-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="d4433-109">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="d4433-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件队列示例":::

<span data-ttu-id="d4433-111">以下是管理事件的方法：</span><span class="sxs-lookup"><span data-stu-id="d4433-111">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="d4433-112">更改事件名称</span><span class="sxs-lookup"><span data-stu-id="d4433-112">Change the incident name</span></span>
- <span data-ttu-id="d4433-113">添加事件标记。</span><span class="sxs-lookup"><span data-stu-id="d4433-113">Add incident tags.</span></span>
- <span data-ttu-id="d4433-114">将事件分配给用户帐户</span><span class="sxs-lookup"><span data-stu-id="d4433-114">Assign the incident to a user account</span></span>
- <span data-ttu-id="d4433-115">解决它们</span><span class="sxs-lookup"><span data-stu-id="d4433-115">Resolve them</span></span> 
- <span data-ttu-id="d4433-116">设置其分类和确定</span><span class="sxs-lookup"><span data-stu-id="d4433-116">Set its classification and determination</span></span>
- <span data-ttu-id="d4433-117">添加注释。</span><span class="sxs-lookup"><span data-stu-id="d4433-117">Add comments.</span></span>

<span data-ttu-id="d4433-118">可以从事件的"管理事件 **"窗格中** 管理事件。</span><span class="sxs-lookup"><span data-stu-id="d4433-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="d4433-119">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="d4433-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="事件的&quot;管理事件&quot;窗格示例":::

<span data-ttu-id="d4433-121">可以从以下位置的"管理 **事件"链接显示** 此窗格：</span><span class="sxs-lookup"><span data-stu-id="d4433-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="d4433-122">事件队列中事件的属性窗格。</span><span class="sxs-lookup"><span data-stu-id="d4433-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="d4433-123">**事件的** 摘要页。</span><span class="sxs-lookup"><span data-stu-id="d4433-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="d4433-124">在调查时，若要将警报从一个事件移动到另一个事件，也可以从"警报"选项卡进行移动，从而创建包含所有相关警报的较大或较小的事件。</span><span class="sxs-lookup"><span data-stu-id="d4433-124">In cases where, while investigating you would like to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="d4433-125">编辑事件名称</span><span class="sxs-lookup"><span data-stu-id="d4433-125">Edit the incident name</span></span>

<span data-ttu-id="d4433-126">根据警报属性（如受影响的终结点数、受影响的用户数、检测源或类别）自动为事件分配名称。</span><span class="sxs-lookup"><span data-stu-id="d4433-126">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="d4433-127">这使您可以快速了解事件的范围。</span><span class="sxs-lookup"><span data-stu-id="d4433-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="d4433-128">例如： *多个源报告的多个终结点上的多阶段事件。*</span><span class="sxs-lookup"><span data-stu-id="d4433-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="d4433-129">可以从"管理事件"窗格上的" **事件名称** "字段中 **编辑事件** 名称。</span><span class="sxs-lookup"><span data-stu-id="d4433-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="d4433-130">推出自动事件命名功能之前已存在的事件将保留其名称。</span><span class="sxs-lookup"><span data-stu-id="d4433-130">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="d4433-131">添加事件标记</span><span class="sxs-lookup"><span data-stu-id="d4433-131">Add incident tags</span></span>

<span data-ttu-id="d4433-132">可以将自定义标记添加到事件，例如，标记一组具有共同特征的事件。</span><span class="sxs-lookup"><span data-stu-id="d4433-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="d4433-133">稍后可以筛选包含特定标记的所有事件的事件队列。</span><span class="sxs-lookup"><span data-stu-id="d4433-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="d4433-134">开始键入时，您可以选择从所选标记列表进行选择。</span><span class="sxs-lookup"><span data-stu-id="d4433-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="d4433-135">分配事件</span><span class="sxs-lookup"><span data-stu-id="d4433-135">Assign incidents</span></span>

<span data-ttu-id="d4433-136">如果尚未分配事件，可以选择"分配给 **"并指定** 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d4433-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="d4433-137">这样做将分配事件的所有权以及与其关联的所有警报。</span><span class="sxs-lookup"><span data-stu-id="d4433-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-incident"></a><span data-ttu-id="d4433-138">解决事件</span><span class="sxs-lookup"><span data-stu-id="d4433-138">Resolve incident</span></span>

<span data-ttu-id="d4433-139">如果事件已修复，请选择"解决 **事件** "以将切换开关向右移动。</span><span class="sxs-lookup"><span data-stu-id="d4433-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="d4433-140">请注意，解决事件还会解决与事件相关的所有链接和活动警报。</span><span class="sxs-lookup"><span data-stu-id="d4433-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="d4433-141">未解决的事件显示为"活动 **"。**</span><span class="sxs-lookup"><span data-stu-id="d4433-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="d4433-142">设置分类和确定</span><span class="sxs-lookup"><span data-stu-id="d4433-142">Set the classification and determination</span></span>

<span data-ttu-id="d4433-143">事件分类是真正的警报还是假警报，从"分类"字段 **进行** 配置。</span><span class="sxs-lookup"><span data-stu-id="d4433-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="d4433-144">如果这是真正的警报，则还应使用"确定"字段指定 **威胁的类型。**</span><span class="sxs-lookup"><span data-stu-id="d4433-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="d4433-145">指定威胁类型可帮助安全团队查看威胁模式，并采取行动保护组织抵御威胁模式。</span><span class="sxs-lookup"><span data-stu-id="d4433-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="d4433-146">添加备注</span><span class="sxs-lookup"><span data-stu-id="d4433-146">Add comments</span></span>

<span data-ttu-id="d4433-147">可以使用"注释"字段向事件添加 **多个** 注释。</span><span class="sxs-lookup"><span data-stu-id="d4433-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="d4433-148">每个注释将添加到事件的历史事件中。</span><span class="sxs-lookup"><span data-stu-id="d4433-148">Each comment is added to the historical events of the incident.</span></span> <span data-ttu-id="d4433-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span><span class="sxs-lookup"><span data-stu-id="d4433-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>
