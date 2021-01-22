---
title: 批准或拒绝自动调查后挂起的操作
description: 使用操作中心管理与自动调查和响应相关的操作
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930374"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="3b524-104">批准或拒绝自动调查后挂起的操作</span><span class="sxs-lookup"><span data-stu-id="3b524-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3b524-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3b524-105">**Applies to:**</span></span>
- <span data-ttu-id="3b524-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b524-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3b524-107">运行自动调查后，可能会生成一个或多个[修正操作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)，需要批准这些操作才能继续。</span><span class="sxs-lookup"><span data-stu-id="3b524-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="3b524-108">例如，可能需要删除电子邮件的群集，或者可能需要删除已隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="3b524-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="3b524-109">应尽快批准（或拒绝）挂起的操作，以便自动调查可以继续并及时完成。</span><span class="sxs-lookup"><span data-stu-id="3b524-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="3b524-110">如果认为 Microsoft 365 Defender 中的自动调查和响应功能遗漏或检测错误，请告诉我们！</span><span class="sxs-lookup"><span data-stu-id="3b524-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="3b524-111">请参阅 [如何在 Microsoft 365](mtp-autoir-report-false-positives-negatives.md)Defender 中的 AIR (功能中的自动调查和响应) 误报/负数。</span><span class="sxs-lookup"><span data-stu-id="3b524-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="3b524-112">挂起的操作可以通过使用操作中心或 [调查详细信息视图](#review-a-pending-action-in-the-action-center) 进行 [审阅和批准](#review-a-pending-action-in-the-investigation-details-view)。</span><span class="sxs-lookup"><span data-stu-id="3b524-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="3b524-113">必须具有[相应的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)才能批准或拒绝修正操作。</span><span class="sxs-lookup"><span data-stu-id="3b524-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="3b524-114">有关详细信息，请参阅 [Microsoft 365 Defender 中自动调查和响应的先决条件](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="3b524-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="3b524-115">在操作中心中查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="3b524-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="3b524-116">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="3b524-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="3b524-117">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="3b524-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="3b524-118">在操作中心中的“挂起”选项卡上，选择列表中的某个项。</span><span class="sxs-lookup"><span data-stu-id="3b524-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="3b524-119">如果选择“调查编号”列中的某个项，将打开“调查详细信息”页面。</span><span class="sxs-lookup"><span data-stu-id="3b524-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="3b524-120">可以在此处查看调查结果，然后批准或拒绝建议的操作。</span><span class="sxs-lookup"><span data-stu-id="3b524-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="3b524-121">如果选择列表中的某一行，将打开浮出控件，可在其中查看有关该项的信息。</span><span class="sxs-lookup"><span data-stu-id="3b524-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![批准或拒绝操作](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="3b524-123">使用链接查看关联的警报或调查，并批准或拒绝该操作。</span><span class="sxs-lookup"><span data-stu-id="3b524-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="3b524-124">在“调查详细信息”视图中查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="3b524-124">Review a pending action in the investigation details view</span></span>

![调查详细信息](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="3b524-126">在[调查详细信息](mtp-autoir-results.md)页上，选择“挂起的操作”（或“操作”）选项卡。此处列出了等待批准的项。</span><span class="sxs-lookup"><span data-stu-id="3b524-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="3b524-127">选择列表中的某个项，然后选择“批准”或“拒绝”。</span><span class="sxs-lookup"><span data-stu-id="3b524-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="undo-completed-actions"></a><span data-ttu-id="3b524-128">撤消已完成的操作</span><span class="sxs-lookup"><span data-stu-id="3b524-128">Undo completed actions</span></span>

<span data-ttu-id="3b524-129">如果你已确定设备或文件不是威胁，你可以撤消已采取的修正操作，无论这些操作是自动执行还是手动执行。</span><span class="sxs-lookup"><span data-stu-id="3b524-129">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="3b524-130">在操作中心的"历史记录 **"** 选项卡上，可以撤消以下任何操作：</span><span class="sxs-lookup"><span data-stu-id="3b524-130">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="3b524-131">操作源</span><span class="sxs-lookup"><span data-stu-id="3b524-131">Action source</span></span> | <span data-ttu-id="3b524-132">支持的操作</span><span class="sxs-lookup"><span data-stu-id="3b524-132">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="3b524-133">- 自动调查</span><span class="sxs-lookup"><span data-stu-id="3b524-133">- Automated investigation</span></span> <br/><span data-ttu-id="3b524-134">- Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="3b524-134">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="3b524-135">- 手动响应操作</span><span class="sxs-lookup"><span data-stu-id="3b524-135">- Manual response actions</span></span> | <span data-ttu-id="3b524-136">- 隔离设备</span><span class="sxs-lookup"><span data-stu-id="3b524-136">- Isolate device</span></span> <br/><span data-ttu-id="3b524-137">- 限制代码执行</span><span class="sxs-lookup"><span data-stu-id="3b524-137">- Restrict code execution</span></span> <br/><span data-ttu-id="3b524-138">- 隔离文件</span><span class="sxs-lookup"><span data-stu-id="3b524-138">- Quarantine a file</span></span> <br/><span data-ttu-id="3b524-139">- 删除注册表项</span><span class="sxs-lookup"><span data-stu-id="3b524-139">- Remove a registry key</span></span> <br/><span data-ttu-id="3b524-140">- 停止服务</span><span class="sxs-lookup"><span data-stu-id="3b524-140">- Stop a service</span></span> <br/><span data-ttu-id="3b524-141">- 禁用驱动程序</span><span class="sxs-lookup"><span data-stu-id="3b524-141">- Disable a driver</span></span> <br/><span data-ttu-id="3b524-142">- 删除计划任务</span><span class="sxs-lookup"><span data-stu-id="3b524-142">- Remove a scheduled task</span></span> |

### <a name="to-undo-a-remediation-action"></a><span data-ttu-id="3b524-143">撤消修正操作</span><span class="sxs-lookup"><span data-stu-id="3b524-143">To undo a remediation action</span></span>

1. <span data-ttu-id="3b524-144">转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 登录。</span><span class="sxs-lookup"><span data-stu-id="3b524-144">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="3b524-145">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="3b524-145">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="3b524-146">在屏幕右侧窗格中，选择"撤消 **"。**</span><span class="sxs-lookup"><span data-stu-id="3b524-146">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="3b524-147">跨多个设备从隔离区删除文件</span><span class="sxs-lookup"><span data-stu-id="3b524-147">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="3b524-148">转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 登录。</span><span class="sxs-lookup"><span data-stu-id="3b524-148">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="3b524-149">在" **历史记录** "选项卡上，选择具有操作类型 **隔离文件的文件**。</span><span class="sxs-lookup"><span data-stu-id="3b524-149">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="3b524-150">在屏幕右侧窗格中，选择"应用到此文件的 **X** 更多实例"，然后选择"**撤消"。**</span><span class="sxs-lookup"><span data-stu-id="3b524-150">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b524-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3b524-151">Next steps</span></span>

- [<span data-ttu-id="3b524-152">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="3b524-152">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="3b524-153">处理自动调查和响应功能中的误报/负数</span><span class="sxs-lookup"><span data-stu-id="3b524-153">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
