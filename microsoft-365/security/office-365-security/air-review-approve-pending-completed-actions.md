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
ms.date: 01/29/2021
ms.openlocfilehash: 525f6cf922f80067219f6c33a2c11559e9e58a39
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878768"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="dd7c9-104">在管理中查看和管理Office 365</span><span class="sxs-lookup"><span data-stu-id="dd7c9-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="dd7c9-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="dd7c9-105">**Applies to**</span></span>
- [<span data-ttu-id="dd7c9-106">适用于 Office 365 计划 2 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dd7c9-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="dd7c9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd7c9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="dd7c9-108">由于自动调查电子邮件&协作内容会导致裁定（如恶意或可疑）时，会创建某些修正操作。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-108">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="dd7c9-109">在 Microsoft Defender for Office 365 中，修正操作可能包括：</span><span class="sxs-lookup"><span data-stu-id="dd7c9-109">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="dd7c9-110">阻止 URL (单击时) </span><span class="sxs-lookup"><span data-stu-id="dd7c9-110">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="dd7c9-111">软删除电子邮件或群集</span><span class="sxs-lookup"><span data-stu-id="dd7c9-111">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="dd7c9-112">隔离电子邮件或电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="dd7c9-112">Quarantining email or email attachments</span></span>
- <span data-ttu-id="dd7c9-113">关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="dd7c9-113">Turning off external mail forwarding</span></span>

<span data-ttu-id="dd7c9-114">除非安全运营团队批准这些修正操作，否则不会执行这些修正操作。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-114">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="dd7c9-115">我们建议尽快审阅和批准任何挂起的操作，以便自动调查及时完成。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-115">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="dd7c9-116">在某些情况下，您可以撤消修正操作。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-116">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="dd7c9-117">批准 (或拒绝) 挂起的操作</span><span class="sxs-lookup"><span data-stu-id="dd7c9-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="dd7c9-118">转到"Microsoft 365 Defender <https://security.microsoft.com> () 并登录。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-118">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="dd7c9-119">在导航窗格中，选择操作 **中心**。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="dd7c9-120">在 **"挂起** "选项卡上，查看等待审批的操作列表。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="dd7c9-121">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-121">Select an item in the list.</span></span> <span data-ttu-id="dd7c9-122">将打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="dd7c9-123">查看飞出窗格中的信息，然后执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="dd7c9-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="dd7c9-124">选择 **"打开调查"** 页以查看有关调查的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="dd7c9-125">选择 **"批准** "以启动挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="dd7c9-126">选择 **"** 拒绝"以防止执行挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="dd7c9-127">撤消一个修正操作</span><span class="sxs-lookup"><span data-stu-id="dd7c9-127">Undo one remediation action</span></span>

1. <span data-ttu-id="dd7c9-128">转到操作中心 <https://security.microsoft.com/action-center> () 并登录。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="dd7c9-129">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="dd7c9-130">在屏幕右侧窗格中，选择"撤消 **"。**</span><span class="sxs-lookup"><span data-stu-id="dd7c9-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="dd7c9-131">撤消多个修正操作</span><span class="sxs-lookup"><span data-stu-id="dd7c9-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="dd7c9-132">转到操作中心 <https://security.microsoft.com/action-center> () 并登录。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="dd7c9-133">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="dd7c9-134">确保选择操作类型相同的项目。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="dd7c9-135">将打开一个飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="dd7c9-136">在飞出窗格中，选择"撤消"。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="dd7c9-137">跨多个设备从隔离中删除文件</span><span class="sxs-lookup"><span data-stu-id="dd7c9-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="dd7c9-138">转到操作中心 <https://security.microsoft.com/action-center> () 并登录。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="dd7c9-139">在" **历史记录"** 选项卡上，选择操作类型为"隔离 **文件"的文件**。</span><span class="sxs-lookup"><span data-stu-id="dd7c9-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="dd7c9-140">在屏幕右侧窗格中，选择"应用到此文件的 **X** 更多实例"，然后选择"撤消 **"。**</span><span class="sxs-lookup"><span data-stu-id="dd7c9-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dd7c9-141">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dd7c9-141">Next steps</span></span>

- [<span data-ttu-id="dd7c9-142">使用威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="dd7c9-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="dd7c9-143">如何在自动调查和响应功能中报告误报/负面影响</span><span class="sxs-lookup"><span data-stu-id="dd7c9-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="dd7c9-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd7c9-144">See also</span></span>

- [<span data-ttu-id="dd7c9-145">查看自动调查的详细信息和Office 365</span><span class="sxs-lookup"><span data-stu-id="dd7c9-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
