---
title: 批准或拒绝自动调查后的挂起操作
description: 使用操作中心管理与自动调查和响应相关的操作
keywords: 操作, 中心, autoair, 自动化, 调查, 响应, 修正
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: edc952a0361ee8cfa6ed3df2eaf80f0fc4bf7fd5
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808457"
---
# <a name="approve-or-reject-pending-actions-from-automated-investigations"></a><span data-ttu-id="ce68d-104">批准或拒绝自动调查的挂起操作</span><span class="sxs-lookup"><span data-stu-id="ce68d-104">Approve or reject pending actions from automated investigations</span></span>

<span data-ttu-id="ce68d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ce68d-105">**Applies to:**</span></span>
- <span data-ttu-id="ce68d-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="ce68d-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="ce68d-107">运行自动调查后，可能会生成一个或多个[修正操作](mtp-action-center.md#remediation-actions)，需要批准这些操作才能继续。</span><span class="sxs-lookup"><span data-stu-id="ce68d-107">When an automated investigation runs, it can result in one or more [remediation actions](mtp-action-center.md#remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="ce68d-108">例如，可能需要删除电子邮件的群集，或者可能需要删除已隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="ce68d-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="ce68d-109">应尽快批准（或拒绝）挂起的操作，以便自动调查可以继续并及时完成。</span><span class="sxs-lookup"><span data-stu-id="ce68d-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

<span data-ttu-id="ce68d-110">可以使用以下几种方法之一来查看和批准挂起的操作：</span><span class="sxs-lookup"><span data-stu-id="ce68d-110">Pending actions can be reviewed and approved by using one of several methods:</span></span>
- [<span data-ttu-id="ce68d-111">使用操作中心</span><span class="sxs-lookup"><span data-stu-id="ce68d-111">Use the Action center</span></span>](#review-a-pending-action-in-the-action-center)
- [<span data-ttu-id="ce68d-112">使用“调查详细信息”视图</span><span class="sxs-lookup"><span data-stu-id="ce68d-112">Use the investigation details view</span></span>](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> <span data-ttu-id="ce68d-113">必须具有[相应的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)才能批准或拒绝修正操作。</span><span class="sxs-lookup"><span data-stu-id="ce68d-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="ce68d-114">在操作中心中查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="ce68d-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="ce68d-115">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="ce68d-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="ce68d-116">在“导航”窗格中，选择“操作中心”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ce68d-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="ce68d-117">在操作中心中的“挂起”选项卡上，选择列表中的某个项\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ce68d-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="ce68d-118">如果选择“调查编号”列中的某个项，将打开“调查详细信息”页面\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ce68d-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="ce68d-119">可以在此处查看调查结果，然后批准或拒绝建议的操作。</span><span class="sxs-lookup"><span data-stu-id="ce68d-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="ce68d-120">如果选择列表中的某一行，将打开浮出控件，可在其中查看有关该项的信息。</span><span class="sxs-lookup"><span data-stu-id="ce68d-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![批准或拒绝操作](../images/air-actioncenter-itemselected.png)<br/><span data-ttu-id="ce68d-122">使用链接查看关联的警报或调查，并批准或拒绝该操作。</span><span class="sxs-lookup"><span data-stu-id="ce68d-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="ce68d-123">在“调查详细信息”视图中查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="ce68d-123">Review a pending action in the investigation details view</span></span>

![调查详细信息](../images/mtp-air-investdetails.png)

1. <span data-ttu-id="ce68d-125">在[调查详细信息](mtp-autoir-results.md)页上，选择“挂起的操作”（或“操作”）选项卡。此处列出了等待批准的项\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ce68d-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="ce68d-126">选择列表中的某个项，然后选择“批准”或“拒绝”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ce68d-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce68d-127">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ce68d-127">Next steps</span></span>

- [<span data-ttu-id="ce68d-128">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="ce68d-128">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="ce68d-129">详细了解事件</span><span class="sxs-lookup"><span data-stu-id="ce68d-129">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="ce68d-130">详细了解搜寻</span><span class="sxs-lookup"><span data-stu-id="ce68d-130">Learn about hunting</span></span>](advanced-hunting-overview.md)
