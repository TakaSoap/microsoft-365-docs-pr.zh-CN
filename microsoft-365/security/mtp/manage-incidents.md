---
title: 管理 Microsoft 威胁防护中的事件
description: 了解如何分配、更新状态
keywords: 事件, 事件, 警报, 相关警报, 分配, 更新, 状态, 管理, 分类, microsoft, 365, m365
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b8f7e3bbb6d2348c3f19e8df251d700d8adf8e33
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235081"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="6c61c-104">管理 Microsoft 威胁防护中的事件</span><span class="sxs-lookup"><span data-stu-id="6c61c-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="6c61c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6c61c-105">**Applies to:**</span></span>
- <span data-ttu-id="6c61c-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="6c61c-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="6c61c-107">管理事件对于确保控制和解决威胁至关重要。</span><span class="sxs-lookup"><span data-stu-id="6c61c-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="6c61c-108">在 Microsoft 威胁防护中，你有权管理设备、用户和邮箱相关事件。</span><span class="sxs-lookup"><span data-stu-id="6c61c-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="6c61c-109">从“事件队列”\*\*\*\* 中选择事件后，就可以管理事件了。</span><span class="sxs-lookup"><span data-stu-id="6c61c-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="6c61c-110">可以编辑事件的名称、解决事件、设置其分类和确定。</span><span class="sxs-lookup"><span data-stu-id="6c61c-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="6c61c-111">还可以将事件分配给自己，添加事件标记和备注。</span><span class="sxs-lookup"><span data-stu-id="6c61c-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="6c61c-112">如果在调查时希望将警报从一个事件转移到另一个事件，还可以从“警报”选项卡执行相关操作，从而创建一个包含所有相关警报的较大或较小的事件。</span><span class="sxs-lookup"><span data-stu-id="6c61c-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="6c61c-113">编辑事件名称</span><span class="sxs-lookup"><span data-stu-id="6c61c-113">Edit incident name</span></span>
<span data-ttu-id="6c61c-114">默认情况下，将为事件分配一个编号。</span><span class="sxs-lookup"><span data-stu-id="6c61c-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="6c61c-115">可以修改事件名称，以便更好地与首选命名约定保持一致。</span><span class="sxs-lookup"><span data-stu-id="6c61c-115">You can modify the incident name to better align with your preferred naming convention.</span></span>
 
## <a name="assign-incidents"></a><span data-ttu-id="6c61c-116">分配事件</span><span class="sxs-lookup"><span data-stu-id="6c61c-116">Assign incidents</span></span>
<span data-ttu-id="6c61c-117">如果尚未分配事件，可以选择“分配给我”\*\*\*\* 将事件分配给自己。</span><span class="sxs-lookup"><span data-stu-id="6c61c-117">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="6c61c-118">执行此操作时，假定所有权不仅限于事件，而且还针对与之关联的所有警报。</span><span class="sxs-lookup"><span data-stu-id="6c61c-118">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="6c61c-119">设置状态和分类</span><span class="sxs-lookup"><span data-stu-id="6c61c-119">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="6c61c-120">事件状态</span><span class="sxs-lookup"><span data-stu-id="6c61c-120">Incident status</span></span>
<span data-ttu-id="6c61c-121">可通过在调查期间更改事件的状态来为事件分类（例如“活动”\*\*\*\* 或“已解决”\*\*\*\*）。</span><span class="sxs-lookup"><span data-stu-id="6c61c-121">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="6c61c-122">这可帮助你整理和管理团队对事件的响应方式。</span><span class="sxs-lookup"><span data-stu-id="6c61c-122">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="6c61c-123">例如，SOC 分析人员可以查看当天的紧急“活动”\*\*\*\* 事件，并决定将其分配给自己进行调查。</span><span class="sxs-lookup"><span data-stu-id="6c61c-123">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="6c61c-124">或者，如果事件已得到修正，SOC 分析人员可能将该事件设置为“已解决”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6c61c-124">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="6c61c-125">解决事件后，系统将自动关闭事件中仍处于打开状态的所有警报。</span><span class="sxs-lookup"><span data-stu-id="6c61c-125">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="6c61c-126">分类和确定</span><span class="sxs-lookup"><span data-stu-id="6c61c-126">Classification and determination</span></span>
<span data-ttu-id="6c61c-127">可以选择不设置分类，也可以决定指定事件为真实/误报事件。</span><span class="sxs-lookup"><span data-stu-id="6c61c-127">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="6c61c-128">这样做有助于团队查看模式并从中了解相关信息。</span><span class="sxs-lookup"><span data-stu-id="6c61c-128">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="6c61c-129">添加备注</span><span class="sxs-lookup"><span data-stu-id="6c61c-129">Add comments</span></span>
<span data-ttu-id="6c61c-130">可以添加备注并查看有关事件的历史事件，以便了解以前对其所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6c61c-130">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="6c61c-131">每当对警报进行更改或添加备注时，都会在“备注”和“历史记录”部分进行记录。</span><span class="sxs-lookup"><span data-stu-id="6c61c-131">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="6c61c-132">添加的备注会立即显示在窗格中。</span><span class="sxs-lookup"><span data-stu-id="6c61c-132">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="6c61c-133">添加事件标记</span><span class="sxs-lookup"><span data-stu-id="6c61c-133">Add incident tags</span></span>
<span data-ttu-id="6c61c-134">可以向事件添加自定义标记，例如，标记一组具有共同特征的事件。</span><span class="sxs-lookup"><span data-stu-id="6c61c-134">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="6c61c-135">以后可以筛选包含特定标记的所有事件的事件队列。</span><span class="sxs-lookup"><span data-stu-id="6c61c-135">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>

