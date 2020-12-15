---
title: 批准或拒绝自动调查后挂起的操作
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.openlocfilehash: b34f4a532571d6215500ab2bec022489fd462d0f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683355"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="62f9e-104">批准或拒绝自动调查后挂起的操作</span><span class="sxs-lookup"><span data-stu-id="62f9e-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="62f9e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="62f9e-105">**Applies to:**</span></span>
- <span data-ttu-id="62f9e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62f9e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="62f9e-107">运行自动调查后，可能会生成一个或多个[修正操作](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)，需要批准这些操作才能继续。</span><span class="sxs-lookup"><span data-stu-id="62f9e-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="62f9e-108">例如，可能需要删除电子邮件的群集，或者可能需要删除已隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="62f9e-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="62f9e-109">应尽快批准（或拒绝）挂起的操作，以便自动调查可以继续并及时完成。</span><span class="sxs-lookup"><span data-stu-id="62f9e-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="62f9e-110">如果认为 Microsoft 365 Defender 中的自动调查和响应功能遗漏或检测错误，请告诉我们！</span><span class="sxs-lookup"><span data-stu-id="62f9e-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="62f9e-111">请参阅 [如何在 Microsoft 365](mtp-autoir-report-false-positives-negatives.md)Defender 中的 AIR (功能中的自动调查和响应) 误报/负数。</span><span class="sxs-lookup"><span data-stu-id="62f9e-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="62f9e-112">挂起的操作可以通过使用操作中心或 [调查详细信息视图](#review-a-pending-action-in-the-action-center) 进行 [审阅和批准](#review-a-pending-action-in-the-investigation-details-view)。</span><span class="sxs-lookup"><span data-stu-id="62f9e-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="62f9e-113">必须具有[相应的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)才能批准或拒绝修正操作。</span><span class="sxs-lookup"><span data-stu-id="62f9e-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="62f9e-114">有关详细信息，请参阅 [Microsoft 365 Defender 中自动调查和响应的先决条件](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="62f9e-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="62f9e-115">在操作中心中查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="62f9e-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="62f9e-116">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="62f9e-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="62f9e-117">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="62f9e-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="62f9e-118">在操作中心中的“挂起”选项卡上，选择列表中的某个项。</span><span class="sxs-lookup"><span data-stu-id="62f9e-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="62f9e-119">如果选择“调查编号”列中的某个项，将打开“调查详细信息”页面。</span><span class="sxs-lookup"><span data-stu-id="62f9e-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="62f9e-120">可以在此处查看调查结果，然后批准或拒绝建议的操作。</span><span class="sxs-lookup"><span data-stu-id="62f9e-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="62f9e-121">如果选择列表中的某一行，将打开浮出控件，可在其中查看有关该项的信息。</span><span class="sxs-lookup"><span data-stu-id="62f9e-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![批准或拒绝操作](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="62f9e-123">使用链接查看关联的警报或调查，并批准或拒绝该操作。</span><span class="sxs-lookup"><span data-stu-id="62f9e-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="62f9e-124">在“调查详细信息”视图中查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="62f9e-124">Review a pending action in the investigation details view</span></span>

![调查详细信息](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="62f9e-126">在[调查详细信息](mtp-autoir-results.md)页上，选择“挂起的操作”（或“操作”）选项卡。此处列出了等待批准的项。</span><span class="sxs-lookup"><span data-stu-id="62f9e-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="62f9e-127">选择列表中的某个项，然后选择“批准”或“拒绝”。</span><span class="sxs-lookup"><span data-stu-id="62f9e-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="62f9e-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="62f9e-128">Next steps</span></span>

- [<span data-ttu-id="62f9e-129">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="62f9e-129">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="62f9e-130">处理自动调查和响应功能中的误报/负数</span><span class="sxs-lookup"><span data-stu-id="62f9e-130">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
