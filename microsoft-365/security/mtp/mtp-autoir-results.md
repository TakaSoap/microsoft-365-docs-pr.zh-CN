---
title: 自动调查的详细信息和结果
description: 在自动调查期间和之后，可以查看结果和关键发现
keywords: 自动化， 调查， 结果， 分析， 详细信息， 修正， autoair
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
ms.date: 09/16/2020
ms.openlocfilehash: 39f6be70ad7a611f9919bb0529e8c8ed7f9dc339
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683351"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="97aa3-104">自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="97aa3-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="97aa3-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="97aa3-105">**Applies to:**</span></span>
- <span data-ttu-id="97aa3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97aa3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="97aa3-107">当 Microsoft 365 Defender 中发生自动调查时，可在自动调查过程期间和之后获得有关该调查的详细信息。</span><span class="sxs-lookup"><span data-stu-id="97aa3-107">When an automated investigation occurs in Microsoft 365 Defender, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="97aa3-108">如果您具有 [必要的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)，可以在调查详细信息视图中查看这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="97aa3-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="97aa3-109">调查详细信息视图为您提供了最新状态以及批准任何挂起操作的能力。</span><span class="sxs-lookup"><span data-stu-id="97aa3-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![调查详细信息](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="97aa3-111">打开调查详细信息视图</span><span class="sxs-lookup"><span data-stu-id="97aa3-111">Open the investigation details view</span></span>

<span data-ttu-id="97aa3-112">可以使用下列方法之一打开调查详细信息视图：</span><span class="sxs-lookup"><span data-stu-id="97aa3-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="97aa3-113">选择操作中心中的项目</span><span class="sxs-lookup"><span data-stu-id="97aa3-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="97aa3-114">从事件详细信息页面选择调查</span><span class="sxs-lookup"><span data-stu-id="97aa3-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="97aa3-115">选择操作中心中的项目</span><span class="sxs-lookup"><span data-stu-id="97aa3-115">Select an item in the Action center</span></span>

<span data-ttu-id="97aa3-116">使用操作中心在"历史记录"选项卡 ("挂起"选项卡) 或 (**挂起审批**) 。 </span><span class="sxs-lookup"><span data-stu-id="97aa3-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="97aa3-117">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="97aa3-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="97aa3-118">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="97aa3-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="97aa3-119">在" **挂起"或** " **历史记录"** 选项卡上，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="97aa3-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="97aa3-120">如果您具有必要的 [权限](mtp-action-center.md#required-permissions-for-action-center-tasks)，您可以批准 (或拒绝) 挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="97aa3-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="97aa3-121">从事件详细信息页面打开调查</span><span class="sxs-lookup"><span data-stu-id="97aa3-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="97aa3-122">使用事件详细信息页面查看有关事件的详细信息，包括触发的有关任何受影响设备、用户帐户或邮箱的信息的警报。</span><span class="sxs-lookup"><span data-stu-id="97aa3-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="97aa3-123">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="97aa3-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="97aa3-124">在导航窗格中，选择 **"事件"。**</span><span class="sxs-lookup"><span data-stu-id="97aa3-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="97aa3-125">选择列表中的某个项目以打开事件详细信息视图。</span><span class="sxs-lookup"><span data-stu-id="97aa3-125">Select an item in the list to open the incident details view.</span></span><br/>![事件详细信息](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="97aa3-127">在 **"调查"** 选项卡上，选择列表中的调查。</span><span class="sxs-lookup"><span data-stu-id="97aa3-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="97aa3-128">调查详细信息</span><span class="sxs-lookup"><span data-stu-id="97aa3-128">Investigation details</span></span>

<span data-ttu-id="97aa3-129">使用调查详细信息视图查看过去、当前和挂起的与调查相关的活动。</span><span class="sxs-lookup"><span data-stu-id="97aa3-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="97aa3-130">调查详细信息视图类似于下图：</span><span class="sxs-lookup"><span data-stu-id="97aa3-130">The investigation details view resembles the following image:</span></span>

![调查详细信息](../../media/mtp-air-investdetails.png)

<span data-ttu-id="97aa3-132">在"调查详细信息"视图中，你可以看到"调查"**图**、警报、设备、标识、关键发现、实体、日志和待定操作选项卡上的信息，如下表所述。   </span><span class="sxs-lookup"><span data-stu-id="97aa3-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

| <span data-ttu-id="97aa3-133">Tab</span><span class="sxs-lookup"><span data-stu-id="97aa3-133">Tab</span></span> | <span data-ttu-id="97aa3-134">说明</span><span class="sxs-lookup"><span data-stu-id="97aa3-134">Description</span></span> |
|--------|--------|
| <span data-ttu-id="97aa3-135">**调查图**</span><span class="sxs-lookup"><span data-stu-id="97aa3-135">**Investigation graph**</span></span>   | <span data-ttu-id="97aa3-136">提供调查的直观表示形式。</span><span class="sxs-lookup"><span data-stu-id="97aa3-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="97aa3-137">描述实体并列出发现的威胁，以及警报以及是否正在等待批准任何操作。</span><span class="sxs-lookup"><span data-stu-id="97aa3-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="97aa3-138">你可以单击图形上的项目以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="97aa3-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="97aa3-139">例如，单击"找到 **的威胁** "图标将你进入" **关键发现"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="97aa3-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
| <span data-ttu-id="97aa3-140">**警告**</span><span class="sxs-lookup"><span data-stu-id="97aa3-140">**Alerts**</span></span>    | <span data-ttu-id="97aa3-141">列出与调查相关的警报。</span><span class="sxs-lookup"><span data-stu-id="97aa3-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="97aa3-142">警报可能来自用户计算机上的威胁防护功能、Office 应用、云应用安全和其他 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="97aa3-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="97aa3-143">**设备**</span><span class="sxs-lookup"><span data-stu-id="97aa3-143">**Devices**</span></span> | <span data-ttu-id="97aa3-144">列出调查中包含的计算机以及修正级别。</span><span class="sxs-lookup"><span data-stu-id="97aa3-144">Lists machines included in the investigation along with remediation level.</span></span>|
| <span data-ttu-id="97aa3-145">**关键发现**</span><span class="sxs-lookup"><span data-stu-id="97aa3-145">**Key findings**</span></span>  | <span data-ttu-id="97aa3-146">列出调查的结果以及执行或挂起的状态和操作。</span><span class="sxs-lookup"><span data-stu-id="97aa3-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="97aa3-147">你可以批准此选项卡上设备和标识的挂起操作。</span><span class="sxs-lookup"><span data-stu-id="97aa3-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
| <span data-ttu-id="97aa3-148">**Entities**</span><span class="sxs-lookup"><span data-stu-id="97aa3-148">**Entities**</span></span>  | <span data-ttu-id="97aa3-149">列出与调查关联的用户活动、文件、进程、服务、驱动程序、IP 地址和持久性方法，以及状态和采取的操作。</span><span class="sxs-lookup"><span data-stu-id="97aa3-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="97aa3-150">**Log**</span><span class="sxs-lookup"><span data-stu-id="97aa3-150">**Log**</span></span>    | <span data-ttu-id="97aa3-151">提供调查期间执行的所有步骤的详细视图以及状态。</span><span class="sxs-lookup"><span data-stu-id="97aa3-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
| <span data-ttu-id="97aa3-152">**挂起的操作**</span><span class="sxs-lookup"><span data-stu-id="97aa3-152">**Pending actions**</span></span> | <span data-ttu-id="97aa3-153">列出需要审批的项目以继续。</span><span class="sxs-lookup"><span data-stu-id="97aa3-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="97aa3-154">后续步骤</span><span class="sxs-lookup"><span data-stu-id="97aa3-154">Next steps</span></span>

- [<span data-ttu-id="97aa3-155">批准或拒绝与自动调查和响应相关的操作</span><span class="sxs-lookup"><span data-stu-id="97aa3-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="97aa3-156">查看修正操作</span><span class="sxs-lookup"><span data-stu-id="97aa3-156">Review remediation actions</span></span>](mtp-remediation-actions.md)
