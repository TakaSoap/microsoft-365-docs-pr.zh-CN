---
title: 查看和管理 Microsoft Defender for Office 365
keywords: AIR， autoIR， Microsoft Defender for Endpoint， 自动化， 调查， 响应， 修正， 威胁， 高级， 威胁， 保护
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 了解 Microsoft Defender for Office 365 计划 2 中的自动调查和响应功能中的修正操作。
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 8fc01ab0dd5178032ea7b101f5361c25bb10bbea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028927"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="4b284-104">在管理中查看和管理Office 365</span><span class="sxs-lookup"><span data-stu-id="4b284-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="4b284-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="4b284-105">**Applies to**</span></span>
- [<span data-ttu-id="4b284-106">适用于 Office 365 计划 2 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4b284-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="4b284-107">由于自动调查电子邮件&协作内容会导致裁定（如恶意或可疑）时，会创建某些修正操作。</span><span class="sxs-lookup"><span data-stu-id="4b284-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="4b284-108">在 Microsoft Defender for Office 365 中，修正操作可能包括：</span><span class="sxs-lookup"><span data-stu-id="4b284-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="4b284-109">软删除电子邮件或群集</span><span class="sxs-lookup"><span data-stu-id="4b284-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="4b284-110">关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="4b284-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="4b284-111">除非安全运营团队批准这些修正操作，否则不会执行这些修正操作。</span><span class="sxs-lookup"><span data-stu-id="4b284-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="4b284-112">我们建议尽快审阅和批准任何挂起的操作，以便自动调查及时完成。</span><span class="sxs-lookup"><span data-stu-id="4b284-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="4b284-113">在某些情况下，你可以重新思考提交的操作。</span><span class="sxs-lookup"><span data-stu-id="4b284-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="4b284-114">在采取任何操作之前，你需要&清除角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="4b284-114">You need to be part of Search & purge role before taking any actions.</span></span>


## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="4b284-115">批准 (或拒绝) 挂起的操作</span><span class="sxs-lookup"><span data-stu-id="4b284-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="4b284-116">有四种不同的方法可查找和执行自动调查操作：</span><span class="sxs-lookup"><span data-stu-id="4b284-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="4b284-117">事件队列</span><span class="sxs-lookup"><span data-stu-id="4b284-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="4b284-118">操作中心</span><span class="sxs-lookup"><span data-stu-id="4b284-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="4b284-119">调查本身 (事件或警报报告访问) </span><span class="sxs-lookup"><span data-stu-id="4b284-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="4b284-120">调查和修正调查队列</span><span class="sxs-lookup"><span data-stu-id="4b284-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="4b284-121">事件队列</span><span class="sxs-lookup"><span data-stu-id="4b284-121">Incident queue</span></span>
1. <span data-ttu-id="4b284-122">转到安全[Microsoft 365并](https://security.microsoft.com)登录。</span><span class="sxs-lookup"><span data-stu-id="4b284-122">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="4b284-123">在导航窗格中，选择"事件 **&事件>警报"。**</span><span class="sxs-lookup"><span data-stu-id="4b284-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="4b284-124">选择事件名称以打开其摘要页面。</span><span class="sxs-lookup"><span data-stu-id="4b284-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="4b284-125">选择" **证据和响应"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b284-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="4b284-126">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="4b284-126">Select an item in the list.</span></span> <span data-ttu-id="4b284-127">其侧窗格将打开。</span><span class="sxs-lookup"><span data-stu-id="4b284-127">Its side pane opens.</span></span>
6. <span data-ttu-id="4b284-128">在侧窗格中，执行批准或拒绝操作。</span><span class="sxs-lookup"><span data-stu-id="4b284-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="4b284-129">调查队列</span><span class="sxs-lookup"><span data-stu-id="4b284-129">Investigation queue</span></span> 
1. <span data-ttu-id="4b284-130">转到安全[Microsoft 365并](https://security.microsoft.com)登录。</span><span class="sxs-lookup"><span data-stu-id="4b284-130">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="4b284-131">从警报/事件页面导航。</span><span class="sxs-lookup"><span data-stu-id="4b284-131">Navigate from the alerts/incident page.</span></span> 
3. <span data-ttu-id="4b284-132">在"调查"页上，转到" **挂起的操作"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b284-132">On the Investigation page, go to the **pending actions** tab.</span></span> 
4. <span data-ttu-id="4b284-133">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="4b284-133">Select an item in the list.</span></span> <span data-ttu-id="4b284-134">其侧窗格将打开。</span><span class="sxs-lookup"><span data-stu-id="4b284-134">Its side pane opens.</span></span>  
5. <span data-ttu-id="4b284-135">在侧窗格中，执行批准或拒绝操作。</span><span class="sxs-lookup"><span data-stu-id="4b284-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="4b284-136">操作中心</span><span class="sxs-lookup"><span data-stu-id="4b284-136">Action center</span></span>
1. <span data-ttu-id="4b284-137">转到安全[Microsoft 365并](https://security.microsoft.com)登录。</span><span class="sxs-lookup"><span data-stu-id="4b284-137">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="4b284-138">在导航窗格中，选择操作 **中心**。</span><span class="sxs-lookup"><span data-stu-id="4b284-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="4b284-139">在 **"挂起** "选项卡上，查看等待审批的操作列表。</span><span class="sxs-lookup"><span data-stu-id="4b284-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="4b284-140">选择 **"打开调查"** 页以查看有关调查的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b284-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="4b284-141">选择 **"批准** "以启动挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="4b284-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="4b284-142">选择 **"** 拒绝"以防止执行挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="4b284-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="4b284-143">调查和修正调查队列</span><span class="sxs-lookup"><span data-stu-id="4b284-143">Investigation and remediation investigations queue</span></span>
1. <span data-ttu-id="4b284-144">转到安全[Microsoft 365并](https://security.microsoft.com)登录。</span><span class="sxs-lookup"><span data-stu-id="4b284-144">Go to the [Microsoft 365 security center](https://security.microsoft.com) and sign in.</span></span>
2. <span data-ttu-id="4b284-145">打开待定调查。</span><span class="sxs-lookup"><span data-stu-id="4b284-145">Open pending investigations.</span></span> 
3. <span data-ttu-id="4b284-146">在"调查"页上，转到" **挂起的操作"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b284-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="4b284-147">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="4b284-147">Select an item in the list.</span></span> <span data-ttu-id="4b284-148">其侧窗格将打开。</span><span class="sxs-lookup"><span data-stu-id="4b284-148">Its side pane opens.</span></span>  
5. <span data-ttu-id="4b284-149">在侧窗格中，执行批准或拒绝操作。</span><span class="sxs-lookup"><span data-stu-id="4b284-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="4b284-150">更改或撤消一个修正操作</span><span class="sxs-lookup"><span data-stu-id="4b284-150">Change or undo one remediation action</span></span>

<span data-ttu-id="4b284-151">有两种不同的方法可以重新考虑提交的操作：</span><span class="sxs-lookup"><span data-stu-id="4b284-151">There are two different ways to reconsider submitted actions:</span></span>
   - <span data-ttu-id="4b284-152">通过统 [一操作中心](https://security.microsoft.com/action-center)。</span><span class="sxs-lookup"><span data-stu-id="4b284-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
   - <span data-ttu-id="4b284-153">但是[，Office操作中心](https://security.microsoft.com/threatincidents)。</span><span class="sxs-lookup"><span data-stu-id="4b284-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>
   
## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="4b284-154">通过统一操作中心更改或撤消</span><span class="sxs-lookup"><span data-stu-id="4b284-154">Change or undo through the unified action center</span></span>
1. <span data-ttu-id="4b284-155">转到统 [一操作中心](https://security.microsoft.com/action-center) 并登录。</span><span class="sxs-lookup"><span data-stu-id="4b284-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="4b284-156">在 **"历史记录** "选项卡上，选择要更改或撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="4b284-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="4b284-157">在屏幕右侧窗格中，选择相应的操作 (移动到 **收件箱**、移动到垃圾邮件、移动到已删除项目、\*\*软删除"或硬删除) 。  </span><span class="sxs-lookup"><span data-stu-id="4b284-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, \*\*soft delete", or **hard delete**).</span></span>

 ## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="4b284-158">通过操作中心Office或撤消</span><span class="sxs-lookup"><span data-stu-id="4b284-158">Change or undo through the Office action center</span></span> 
1. <span data-ttu-id="4b284-159">转到Office[中心并](https://security.microsoft.com/threatincidents)登录。</span><span class="sxs-lookup"><span data-stu-id="4b284-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="4b284-160">选择适当的修正。</span><span class="sxs-lookup"><span data-stu-id="4b284-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="4b284-161">在侧窗格中，单击邮件提交条目并等待列表加载。</span><span class="sxs-lookup"><span data-stu-id="4b284-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span> 
4. <span data-ttu-id="4b284-162">等待顶部的"操作"按钮启用并选择"操作"按钮以更改操作类型。</span><span class="sxs-lookup"><span data-stu-id="4b284-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span> 
5. <span data-ttu-id="4b284-163">这将创建相应的操作。</span><span class="sxs-lookup"><span data-stu-id="4b284-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4b284-164">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4b284-164">Next steps</span></span>

- [<span data-ttu-id="4b284-165">使用威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="4b284-165">Use Threat Explorer</span></span>](threat-explorer.md) 
- [<span data-ttu-id="4b284-166">管理员/手动操作</span><span class="sxs-lookup"><span data-stu-id="4b284-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="4b284-167">如何在自动调查和响应功能中报告误报/负面影响</span><span class="sxs-lookup"><span data-stu-id="4b284-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="4b284-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b284-168">See also</span></span>

- [<span data-ttu-id="4b284-169">查看自动调查的详细信息和Office 365</span><span class="sxs-lookup"><span data-stu-id="4b284-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
