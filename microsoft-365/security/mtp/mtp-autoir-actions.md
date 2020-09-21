---
title: 在自动调查后批准或拒绝待处理的操作
description: 使用操作中心管理与自动调查和响应相关的操作
keywords: 操作, 中心, autoair, 自动化, 调查, 响应, 修正
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: d7739ac6184509abe4df3aaf140db66f6039717c
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962649"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="5b08f-104">在自动调查后批准或拒绝待处理的操作</span><span class="sxs-lookup"><span data-stu-id="5b08f-104">Approve or reject pending actions following an automated investigation</span></span>

<span data-ttu-id="5b08f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5b08f-105">**Applies to:**</span></span>
- <span data-ttu-id="5b08f-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="5b08f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="5b08f-107">运行自动调查后，可能会生成一个或多个[修正操作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)，需要批准这些操作才能继续。</span><span class="sxs-lookup"><span data-stu-id="5b08f-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="5b08f-108">例如，可能需要删除电子邮件的群集，或者可能需要删除已隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="5b08f-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="5b08f-109">应尽快批准（或拒绝）挂起的操作，以便自动调查可以继续并及时完成。</span><span class="sxs-lookup"><span data-stu-id="5b08f-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="5b08f-110">如果你认为在 Microsoft 威胁防护中，自动调查和响应功能已丢失或错误地检测到了某些内容，请告诉我们！</span><span class="sxs-lookup"><span data-stu-id="5b08f-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="5b08f-111">请参阅 [如何在自动调查和响应中报告误报/负面 (AIR) 在 Microsoft 威胁防护中的功能](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="5b08f-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="5b08f-112">可以使用 [操作中心](#review-a-pending-action-in-the-action-center) 或 [调查详细信息视图](#review-a-pending-action-in-the-investigation-details-view)来审阅和批准挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="5b08f-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="5b08f-113">必须具有[相应的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)才能批准或拒绝修正操作。</span><span class="sxs-lookup"><span data-stu-id="5b08f-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="5b08f-114">在操作中心中查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="5b08f-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="5b08f-115">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="5b08f-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="5b08f-116">在“导航”窗格中，选择“操作中心”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b08f-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="5b08f-117">在操作中心中的“挂起”选项卡上，选择列表中的某个项\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b08f-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="5b08f-118">如果选择“调查编号”列中的某个项，将打开“调查详细信息”页面\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b08f-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="5b08f-119">可以在此处查看调查结果，然后批准或拒绝建议的操作。</span><span class="sxs-lookup"><span data-stu-id="5b08f-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="5b08f-120">如果选择列表中的某一行，将打开浮出控件，可在其中查看有关该项的信息。</span><span class="sxs-lookup"><span data-stu-id="5b08f-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![批准或拒绝操作](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="5b08f-122">使用链接查看关联的警报或调查，并批准或拒绝该操作。</span><span class="sxs-lookup"><span data-stu-id="5b08f-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="5b08f-123">在“调查详细信息”视图中查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="5b08f-123">Review a pending action in the investigation details view</span></span>

![调查详细信息](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="5b08f-125">在[调查详细信息](mtp-autoir-results.md)页上，选择“挂起的操作”（或“操作”）选项卡。此处列出了等待批准的项\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b08f-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="5b08f-126">选择列表中的某个项，然后选择“批准”或“拒绝”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b08f-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b08f-127">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5b08f-127">Next steps</span></span>

- [<span data-ttu-id="5b08f-128">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="5b08f-128">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="5b08f-129">处理自动调查和响应功能中的误报/否定</span><span class="sxs-lookup"><span data-stu-id="5b08f-129">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
