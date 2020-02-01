---
title: 查看自动调查的详细信息和结果
description: 在自动调查期间和之后，您可以查看结果和主要发现
keywords: 自动化、调查、结果、分析、详细信息、修正、autoair
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
ms.openlocfilehash: 208cbb49afc2f4520fa44a4ef283194bcaff22be
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600089"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a><span data-ttu-id="8cc9b-104">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="8cc9b-104">View the details and results of an automated investigation</span></span>

<span data-ttu-id="8cc9b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8cc9b-105">**Applies to:**</span></span>
- <span data-ttu-id="8cc9b-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="8cc9b-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8cc9b-107">在 Microsoft 威胁防护中进行自动调查时，有关该调查的详细信息在自动调查过程的过程中和之后都是可用的。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="8cc9b-108">如果您具有[所需的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)，则可以在调查详细信息视图中查看这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="8cc9b-109">调查详细信息视图为您提供了最新状态，并能够批准任何挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![调查详细信息](../images/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="8cc9b-111">打开调查详细信息视图</span><span class="sxs-lookup"><span data-stu-id="8cc9b-111">Open the investigation details view</span></span>

<span data-ttu-id="8cc9b-112">您可以使用以下方法之一打开调查详细信息视图：</span><span class="sxs-lookup"><span data-stu-id="8cc9b-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="8cc9b-113">在操作中心中选择一个项目</span><span class="sxs-lookup"><span data-stu-id="8cc9b-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="8cc9b-114">从 "事件详细信息" 页中选择调查</span><span class="sxs-lookup"><span data-stu-id="8cc9b-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="8cc9b-115">在操作中心中选择一个项目</span><span class="sxs-lookup"><span data-stu-id="8cc9b-115">Select an item in the Action center</span></span>

<span data-ttu-id="8cc9b-116">使用操作中心查看处于待审批状态的操作（在 "**待定**" 选项卡上）或已批准的操作（在 "**历史记录**" 选项卡上）。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="8cc9b-117">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="8cc9b-118">在“导航”窗格中，选择“操作中心”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="8cc9b-119">在 "**挂起**" 或 "**历史记录**" 选项卡上，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="8cc9b-120">如果您具有[所需的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)，则可以批准（或拒绝）挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="8cc9b-121">从 "事件详细信息" 页打开调查</span><span class="sxs-lookup"><span data-stu-id="8cc9b-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="8cc9b-122">使用 "事件详细信息" 页查看有关事件的详细信息，包括触发了任何受影响的设备、用户帐户或邮箱的信息的警报。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="8cc9b-123">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="8cc9b-124">在导航窗格中，选择 "**事件**"。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="8cc9b-125">在列表中选择一个项目以打开 "事件详细信息" 视图。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-125">Select an item in the list to open the incident details view.</span></span><br/>![事件详细信息](../images/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="8cc9b-127">在 "**调查**" 选项卡上，选择列表中的调查。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="8cc9b-128">调查详细信息</span><span class="sxs-lookup"><span data-stu-id="8cc9b-128">Investigation details</span></span>

<span data-ttu-id="8cc9b-129">使用调查详细信息视图查看与调查相关的过去、当前和待定活动。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="8cc9b-130">调查详细信息视图类似于以下图像：</span><span class="sxs-lookup"><span data-stu-id="8cc9b-130">The investigation details view resembles the following image:</span></span>

![调查详细信息](../images/mtp-air-investdetails.png)

<span data-ttu-id="8cc9b-132">在调查详细信息视图中，您可以查看下表中所述的有关**调查图**、**警报**、**设备**、**标识**、**关键发现**、**实体**、**日志**和**待定操作**选项卡的信息。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="8cc9b-133">Tab</span><span class="sxs-lookup"><span data-stu-id="8cc9b-133">Tab</span></span>    |<span data-ttu-id="8cc9b-134">说明</span><span class="sxs-lookup"><span data-stu-id="8cc9b-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="8cc9b-135">调查图形</span><span class="sxs-lookup"><span data-stu-id="8cc9b-135">Investigation graph</span></span>    |<span data-ttu-id="8cc9b-136">提供调查的直观表示形式。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="8cc9b-137">描述实体并列出发现的威胁以及警报以及是否有任何操作正在等待审批。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="8cc9b-138">您可以单击关系图上的某一项以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="8cc9b-139">例如，单击 "**发现威胁**" 图标将转到 "**关键调查结果**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="8cc9b-140">警报</span><span class="sxs-lookup"><span data-stu-id="8cc9b-140">Alerts</span></span> |<span data-ttu-id="8cc9b-141">列出与调查相关的警报。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="8cc9b-142">警报可以来自用户计算机上的威胁防护功能、Office 应用程序、云应用安全和其他 Microsoft 365 威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="8cc9b-143">设备</span><span class="sxs-lookup"><span data-stu-id="8cc9b-143">Devices</span></span>|<span data-ttu-id="8cc9b-144">列出调查中包含的计算机以及修正级别。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="8cc9b-145">主要发现</span><span class="sxs-lookup"><span data-stu-id="8cc9b-145">Key findings</span></span>   |<span data-ttu-id="8cc9b-146">列出调查结果以及所执行或挂起的状态和操作。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="8cc9b-147">您可以在此选项卡上为设备和标识批准挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="8cc9b-148">实体</span><span class="sxs-lookup"><span data-stu-id="8cc9b-148">Entities</span></span>   |<span data-ttu-id="8cc9b-149">列出与调查相关联的用户活动、文件、进程、服务、驱动程序、IP 地址和持久性方法，以及所执行的状态和操作。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="8cc9b-150">Log</span><span class="sxs-lookup"><span data-stu-id="8cc9b-150">Log</span></span>    |<span data-ttu-id="8cc9b-151">提供调查过程中执行的所有步骤的详细视图以及状态。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="8cc9b-152">挂起的操作</span><span class="sxs-lookup"><span data-stu-id="8cc9b-152">Pending actions</span></span>    |<span data-ttu-id="8cc9b-153">列出需要审批才能继续的项目。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-153">Lists items that require approval to proceed.</span></span>|

## <a name="remediation-actions-following-automated-investigation"></a><span data-ttu-id="8cc9b-154">自动调查后的补救措施</span><span class="sxs-lookup"><span data-stu-id="8cc9b-154">Remediation actions following automated investigation</span></span>

<span data-ttu-id="8cc9b-155">当自动调查完成时，将达到涉及的每条证据的结论，并确定修正操作。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-155">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="8cc9b-156">在某些情况下，将自动执行更正操作;在其他情况下，补救措施等待审批。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-156">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="8cc9b-157">下表列出了可能的 verdicts 和结果：</span><span class="sxs-lookup"><span data-stu-id="8cc9b-157">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="8cc9b-158">Verdict</span><span class="sxs-lookup"><span data-stu-id="8cc9b-158">Verdict</span></span>    |<span data-ttu-id="8cc9b-159">区域</span><span class="sxs-lookup"><span data-stu-id="8cc9b-159">Area</span></span>   |<span data-ttu-id="8cc9b-160">结果</span><span class="sxs-lookup"><span data-stu-id="8cc9b-160">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="8cc9b-161">恶意</span><span class="sxs-lookup"><span data-stu-id="8cc9b-161">Malicious</span></span>  |<span data-ttu-id="8cc9b-162">设备（终结点）</span><span class="sxs-lookup"><span data-stu-id="8cc9b-162">Devices (endpoints)</span></span>    |<span data-ttu-id="8cc9b-163">将自动执行更正操作</span><span class="sxs-lookup"><span data-stu-id="8cc9b-163">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="8cc9b-164">恶意</span><span class="sxs-lookup"><span data-stu-id="8cc9b-164">Malicious</span></span>  |<span data-ttu-id="8cc9b-165">电子邮件内容（Url 或附件）</span><span class="sxs-lookup"><span data-stu-id="8cc9b-165">Email content (URLs or attachments)</span></span> | <span data-ttu-id="8cc9b-166">建议的修正操作处于待审批状态</span><span class="sxs-lookup"><span data-stu-id="8cc9b-166">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="8cc9b-167">引入</span><span class="sxs-lookup"><span data-stu-id="8cc9b-167">Suspicious</span></span> |<span data-ttu-id="8cc9b-168">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="8cc9b-168">Devices or email content</span></span> |<span data-ttu-id="8cc9b-169">建议的修正操作处于待审批状态</span><span class="sxs-lookup"><span data-stu-id="8cc9b-169">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="8cc9b-170">清理</span><span class="sxs-lookup"><span data-stu-id="8cc9b-170">Clean</span></span>  |<span data-ttu-id="8cc9b-171">设备或电子邮件内容</span><span class="sxs-lookup"><span data-stu-id="8cc9b-171">Devices or email content</span></span>   |<span data-ttu-id="8cc9b-172">不需要任何修正操作</span><span class="sxs-lookup"><span data-stu-id="8cc9b-172">No remediation actions are needed</span></span>|

[<span data-ttu-id="8cc9b-173">在操作中心中查看挂起的操作</span><span class="sxs-lookup"><span data-stu-id="8cc9b-173">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="8cc9b-174">如果你认为在 Microsoft 威胁防护中，自动调查和响应功能已丢失或错误地检测到了某些内容，请告诉我们！</span><span class="sxs-lookup"><span data-stu-id="8cc9b-174">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="8cc9b-175">请参阅[如何在 Microsoft 威胁防护中报告误报/负面的自动调查和响应（空中）功能](mtp-autoir-report-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="8cc9b-175">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8cc9b-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8cc9b-176">Next steps</span></span>

- [<span data-ttu-id="8cc9b-177">获取操作中心权限的概述</span><span class="sxs-lookup"><span data-stu-id="8cc9b-177">Get an overview of Action center permissions</span></span>](mtp-action-center.md#required-permissions-for-action-center-tasks)
- [<span data-ttu-id="8cc9b-178">批准或拒绝与自动调查和响应相关的操作</span><span class="sxs-lookup"><span data-stu-id="8cc9b-178">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

