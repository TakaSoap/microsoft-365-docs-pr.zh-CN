---
title: 在操作中心查看和管理操作
description: 使用操作中心查看和管理修正操作
keywords: 操作, 中心, autoair, 自动化, 调查, 响应, 修正
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 01/29/2021
ms.technology: m365d
ms.openlocfilehash: d78bf3689020b5a24863e5a0f1ec817af50178ad
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055869"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="bdecd-104">在操作中心查看和管理操作</span><span class="sxs-lookup"><span data-stu-id="bdecd-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bdecd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bdecd-105">**Applies to:**</span></span>
- <span data-ttu-id="bdecd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdecd-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bdecd-107">Microsoft 365 Defender 中的威胁防护功能可能会导致某些修正操作。</span><span class="sxs-lookup"><span data-stu-id="bdecd-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="bdecd-108">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="bdecd-108">Here are some examples:</span></span>
- <span data-ttu-id="bdecd-109">[自动调查](m365d-autoir.md) 可能会导致自动执行修正操作或等待审批。</span><span class="sxs-lookup"><span data-stu-id="bdecd-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await approval.</span></span>
- <span data-ttu-id="bdecd-110">防病毒、反恶意软件和其他威胁防护功能可能会导致修正操作，例如阻止文件、URL 或进程，或将项目发送到隔离区。</span><span class="sxs-lookup"><span data-stu-id="bdecd-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="bdecd-111">安全运营团队可以手动采取修正操作，例如，在高级搜寻[期间](advanced-hunting-overview.md)或在调查[警报或](investigate-alerts.md)[事件时](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="bdecd-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bdecd-112">必须具有[相应的权限](m365d-action-center.md#required-permissions-for-action-center-tasks)才能批准或拒绝修正操作。</span><span class="sxs-lookup"><span data-stu-id="bdecd-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="bdecd-113">有关详细信息，请参阅 Microsoft [365 Defender 中的自动调查和响应的先决条件](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="bdecd-113">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="bdecd-114">在操作中心查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="bdecd-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="bdecd-115">应尽快批准（或拒绝）挂起的操作，以便自动调查可以继续并及时完成。</span><span class="sxs-lookup"><span data-stu-id="bdecd-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

![批准或拒绝操作](../../media/air-actioncenter-itemselected.png)

1. <span data-ttu-id="bdecd-117">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="bdecd-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="bdecd-118">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="bdecd-118">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="bdecd-119">在操作中心中的“挂起”选项卡上，选择列表中的某个项。</span><span class="sxs-lookup"><span data-stu-id="bdecd-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="bdecd-120">将打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="bdecd-120">Its flyout pane opens.</span></span>
4. <span data-ttu-id="bdecd-121">查看飞出窗格中的信息，然后执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="bdecd-121">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="bdecd-122">选择 **"打开调查"** 页以查看有关调查的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="bdecd-122">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="bdecd-123">选择 **"批准** "以启动挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="bdecd-123">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="bdecd-124">选择 **"** 拒绝"以防止执行挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="bdecd-124">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="bdecd-125">选择 **"开始搜寻**"转到"[高级搜寻"。](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bdecd-125">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="bdecd-126">撤消已完成的操作</span><span class="sxs-lookup"><span data-stu-id="bdecd-126">Undo completed actions</span></span>

<span data-ttu-id="bdecd-127">如果你已确定设备或文件不是威胁，你可以撤消已采取的修正操作，无论这些操作是自动执行还是手动执行。</span><span class="sxs-lookup"><span data-stu-id="bdecd-127">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="bdecd-128">在操作中心的"历史记录 **"** 选项卡上，可以撤消以下任何操作：</span><span class="sxs-lookup"><span data-stu-id="bdecd-128">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="bdecd-129">操作源</span><span class="sxs-lookup"><span data-stu-id="bdecd-129">Action source</span></span> | <span data-ttu-id="bdecd-130">支持的操作</span><span class="sxs-lookup"><span data-stu-id="bdecd-130">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="bdecd-131">- 自动调查</span><span class="sxs-lookup"><span data-stu-id="bdecd-131">- Automated investigation</span></span> <br/><span data-ttu-id="bdecd-132">- Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="bdecd-132">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="bdecd-133">- 手动响应操作</span><span class="sxs-lookup"><span data-stu-id="bdecd-133">- Manual response actions</span></span> | <span data-ttu-id="bdecd-134">- 隔离设备</span><span class="sxs-lookup"><span data-stu-id="bdecd-134">- Isolate device</span></span> <br/><span data-ttu-id="bdecd-135">- 限制代码执行</span><span class="sxs-lookup"><span data-stu-id="bdecd-135">- Restrict code execution</span></span> <br/><span data-ttu-id="bdecd-136">- 隔离文件</span><span class="sxs-lookup"><span data-stu-id="bdecd-136">- Quarantine a file</span></span> <br/><span data-ttu-id="bdecd-137">- 删除注册表项</span><span class="sxs-lookup"><span data-stu-id="bdecd-137">- Remove a registry key</span></span> <br/><span data-ttu-id="bdecd-138">- 停止服务</span><span class="sxs-lookup"><span data-stu-id="bdecd-138">- Stop a service</span></span> <br/><span data-ttu-id="bdecd-139">- 禁用驱动程序</span><span class="sxs-lookup"><span data-stu-id="bdecd-139">- Disable a driver</span></span> <br/><span data-ttu-id="bdecd-140">- 删除计划任务</span><span class="sxs-lookup"><span data-stu-id="bdecd-140">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="bdecd-141">撤消一个修正操作</span><span class="sxs-lookup"><span data-stu-id="bdecd-141">Undo one remediation action</span></span>

1. <span data-ttu-id="bdecd-142">转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="bdecd-142">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="bdecd-143">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="bdecd-143">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="bdecd-144">在屏幕右侧窗格中，选择"撤消 **"。**</span><span class="sxs-lookup"><span data-stu-id="bdecd-144">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="bdecd-145">撤消多个修正操作</span><span class="sxs-lookup"><span data-stu-id="bdecd-145">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="bdecd-146">转到操作中心 (https://security.microsoft.com/action-center) 并登录。</span><span class="sxs-lookup"><span data-stu-id="bdecd-146">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="bdecd-147">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="bdecd-147">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="bdecd-148">确保选择操作类型相同的项目。</span><span class="sxs-lookup"><span data-stu-id="bdecd-148">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="bdecd-149">将打开一个飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="bdecd-149">A flyout pane opens.</span></span>
3. <span data-ttu-id="bdecd-150">在飞出窗格中， **选择撤消**。</span><span class="sxs-lookup"><span data-stu-id="bdecd-150">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="bdecd-151">跨多个设备从隔离中删除文件</span><span class="sxs-lookup"><span data-stu-id="bdecd-151">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="bdecd-152">转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="bdecd-152">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="bdecd-153">在" **历史记录"** 选项卡上，选择操作类型为"隔离 **文件"的文件**。</span><span class="sxs-lookup"><span data-stu-id="bdecd-153">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="bdecd-154">在屏幕右侧窗格中，选择"应用到此文件的 **X** 更多实例"，然后选择"撤消 **"。**</span><span class="sxs-lookup"><span data-stu-id="bdecd-154">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bdecd-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bdecd-155">Next steps</span></span>

- [<span data-ttu-id="bdecd-156">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="bdecd-156">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="bdecd-157">了解如何在获得一个 (时处理误报/) </span><span class="sxs-lookup"><span data-stu-id="bdecd-157">Learn how to handle false positives/negatives (if you get one)</span></span>](m365d-autoir-report-false-positives-negatives.md)
