---
title: 在 Microsoft Defender for Office 365 中查看和管理修正操作
keywords: AIR， autoIR， ATP， 自动化， 调查， 响应， 修正， 威胁， 高级， 威胁， 保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: bcff8f12133ea16e3d91e293943be1593eaf9659
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142689"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="21cea-104">查看和管理 Office 365 中的修正操作</span><span class="sxs-lookup"><span data-stu-id="21cea-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="21cea-105">由于自动调查电子邮件&协作内容会导致裁定（如恶意或可疑）时，会创建某些修正操作。</span><span class="sxs-lookup"><span data-stu-id="21cea-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="21cea-106">在 Microsoft Defender for Office 365 中，修正操作可以包括：</span><span class="sxs-lookup"><span data-stu-id="21cea-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="21cea-107">在单击 (时阻止 URL) </span><span class="sxs-lookup"><span data-stu-id="21cea-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="21cea-108">软删除电子邮件或群集</span><span class="sxs-lookup"><span data-stu-id="21cea-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="21cea-109">隔离电子邮件或电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="21cea-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="21cea-110">关闭外部邮件转发</span><span class="sxs-lookup"><span data-stu-id="21cea-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="21cea-111">除非安全运营团队批准这些修正操作，否则不会执行这些修正操作。</span><span class="sxs-lookup"><span data-stu-id="21cea-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="21cea-112">我们建议尽快审阅和批准任何挂起的操作，以便自动调查及时完成。</span><span class="sxs-lookup"><span data-stu-id="21cea-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="21cea-113">在某些情况下，您可以撤消修正操作。</span><span class="sxs-lookup"><span data-stu-id="21cea-113">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="21cea-114">批准 (或拒绝) 挂起的操作</span><span class="sxs-lookup"><span data-stu-id="21cea-114">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="21cea-115">转到 Microsoft 365 安全中心 [https://security.microsoft.com](https://security.microsoft.com)) 登录。</span><span class="sxs-lookup"><span data-stu-id="21cea-115">Go to the Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="21cea-116">在导航窗格中，选择 **操作中心**。</span><span class="sxs-lookup"><span data-stu-id="21cea-116">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="21cea-117">在 **"挂起** "选项卡上，查看等待审批的操作列表。</span><span class="sxs-lookup"><span data-stu-id="21cea-117">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="21cea-118">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="21cea-118">Select an item in the list.</span></span> <span data-ttu-id="21cea-119">随即打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="21cea-119">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="21cea-120">查看飞出窗格中的信息，然后执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="21cea-120">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="21cea-121">选择 **"打开** 调查"页以查看有关调查的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="21cea-121">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="21cea-122">选择 **"** 批准"以启动挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="21cea-122">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="21cea-123">选择 **"** 拒绝"可阻止执行挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="21cea-123">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="21cea-124">撤消一个修正操作</span><span class="sxs-lookup"><span data-stu-id="21cea-124">Undo one remediation action</span></span>

1. <span data-ttu-id="21cea-125">转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 登录。</span><span class="sxs-lookup"><span data-stu-id="21cea-125">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="21cea-126">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="21cea-126">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="21cea-127">在屏幕右侧窗格中，选择"撤消 **"。**</span><span class="sxs-lookup"><span data-stu-id="21cea-127">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="21cea-128">撤消多个修正操作</span><span class="sxs-lookup"><span data-stu-id="21cea-128">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="21cea-129">转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 登录。</span><span class="sxs-lookup"><span data-stu-id="21cea-129">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="21cea-130">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="21cea-130">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="21cea-131">确保选择操作类型相同的项目。</span><span class="sxs-lookup"><span data-stu-id="21cea-131">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="21cea-132">将打开一个飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="21cea-132">A flyout pane opens.</span></span>
3. <span data-ttu-id="21cea-133">在飞出窗格中，选择"撤消"。</span><span class="sxs-lookup"><span data-stu-id="21cea-133">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="21cea-134">跨多个设备从隔离区删除文件</span><span class="sxs-lookup"><span data-stu-id="21cea-134">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="21cea-135">转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 登录。</span><span class="sxs-lookup"><span data-stu-id="21cea-135">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="21cea-136">在" **历史记录** "选项卡上，选择具有操作类型 **隔离文件的文件**。</span><span class="sxs-lookup"><span data-stu-id="21cea-136">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="21cea-137">在屏幕右侧窗格中，选择"应用到此文件的 **X** 更多实例"，然后选择"**撤消"。**</span><span class="sxs-lookup"><span data-stu-id="21cea-137">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="21cea-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="21cea-138">Next steps</span></span>

- [<span data-ttu-id="21cea-139">使用威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="21cea-139">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="21cea-140">如何在自动调查和响应功能中报告误报/负面影响</span><span class="sxs-lookup"><span data-stu-id="21cea-140">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="21cea-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21cea-141">See also</span></span>

- [<span data-ttu-id="21cea-142">查看 Office 365 中自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="21cea-142">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
