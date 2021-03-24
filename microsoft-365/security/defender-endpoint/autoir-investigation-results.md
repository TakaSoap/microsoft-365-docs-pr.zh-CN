---
title: 自动调查的详细信息和结果
description: 在自动调查期间和之后，可以查看结果和关键发现
keywords: 自动化， 调查， 结果， 分析， 详细信息， 修正， autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
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
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 02/02/2021
ms.openlocfilehash: c11d9cd1ce4c2ca49315ec62b51c23ef981555f4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056224"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="2e9da-104">自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="2e9da-104">Details and results of an automated investigation</span></span>

<span data-ttu-id="2e9da-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="2e9da-105">**Applies to:**</span></span>
- <span data-ttu-id="2e9da-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2e9da-106">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="2e9da-107">使用 Microsoft Defender for [Endpoint，当自动](automated-investigations.md) 调查运行时，有关该调查的详细信息在自动调查过程期间和之后均可用。</span><span class="sxs-lookup"><span data-stu-id="2e9da-107">With Microsoft Defender for Endpoint, when an [automated investigation](automated-investigations.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="2e9da-108">如果您具有必要的权限，您可以在调查详细信息视图中查看这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="2e9da-108">If you have the necessary permissions, you can view those details in an investigation details view.</span></span> <span data-ttu-id="2e9da-109">调查详细信息视图为您提供了最新状态以及批准任何挂起操作的能力。</span><span class="sxs-lookup"><span data-stu-id="2e9da-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

## <a name="new-unified-investigation-page"></a><span data-ttu-id="2e9da-110"> ("新建！) 统一调查"页</span><span class="sxs-lookup"><span data-stu-id="2e9da-110">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="2e9da-111">最近更新了调查页面，以包含跨设备、电子邮件和协作内容的信息。</span><span class="sxs-lookup"><span data-stu-id="2e9da-111">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="2e9da-112">新的统一调查页面定义通用语言，并提供跨 [Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md)  和 Microsoft Defender [for Office 365](/microsoft-365/security/defender-365-security/office-365-atp)自动调查的统一体验。</span><span class="sxs-lookup"><span data-stu-id="2e9da-112">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md)  and [Microsoft Defender for Office 365](/microsoft-365/security/defender-365-security/office-365-atp).</span></span> 

> [!TIP]
> <span data-ttu-id="2e9da-113">若要了解有关变化内容的信息，请参阅 ([ NEW！) 统一调查页](/microsoft-365/security/mtp/mtp-autoir-results)。</span><span class="sxs-lookup"><span data-stu-id="2e9da-113">To learn more about what's changing, see [(NEW!) Unified investigation page](/microsoft-365/security/mtp/mtp-autoir-results).</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="2e9da-114">打开调查详细信息视图</span><span class="sxs-lookup"><span data-stu-id="2e9da-114">Open the investigation details view</span></span>

<span data-ttu-id="2e9da-115">可以使用以下方法之一打开调查详细信息视图：</span><span class="sxs-lookup"><span data-stu-id="2e9da-115">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="2e9da-116">选择操作中心中的项目</span><span class="sxs-lookup"><span data-stu-id="2e9da-116">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="2e9da-117">从事件详细信息页面选择调查</span><span class="sxs-lookup"><span data-stu-id="2e9da-117">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="2e9da-118">选择操作中心中的项目</span><span class="sxs-lookup"><span data-stu-id="2e9da-118">Select an item in the Action center</span></span>

<span data-ttu-id="2e9da-119">改进的操作[中心](auto-investigation-action-center.md)将跨设备、电子邮件[](manage-auto-investigation.md#remediation-actions)、协作内容和标识&修正操作汇集在一起。</span><span class="sxs-lookup"><span data-stu-id="2e9da-119">The improved [Action center](auto-investigation-action-center.md) brings together [remediation actions](manage-auto-investigation.md#remediation-actions) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="2e9da-120">列出的操作包括自动或手动采取的修正操作。</span><span class="sxs-lookup"><span data-stu-id="2e9da-120">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="2e9da-121">在操作中心中，可以查看等待审批的操作以及已获得批准或已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="2e9da-121">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="2e9da-122">还可以导航到更多详细信息，如调查页面。</span><span class="sxs-lookup"><span data-stu-id="2e9da-122">You can also navigate to more details, such as an investigation page.</span></span>

1. <span data-ttu-id="2e9da-123">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="2e9da-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="2e9da-124">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="2e9da-124">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="2e9da-125">在"挂起 **"或** " **历史记录"** 选项卡上，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="2e9da-125">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="2e9da-126">将打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="2e9da-126">Its flyout pane opens.</span></span>
4. <span data-ttu-id="2e9da-127">查看飞出窗格中的信息，然后执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="2e9da-127">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="2e9da-128">选择 **"打开调查"** 页以查看有关调查的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="2e9da-128">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="2e9da-129">选择 **"批准** "以启动挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="2e9da-129">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="2e9da-130">选择 **"** 拒绝"以防止执行挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="2e9da-130">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="2e9da-131">选择 **"开始搜寻**"转到"[高级搜寻"。](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2e9da-131">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="2e9da-132">从事件详细信息页面打开调查</span><span class="sxs-lookup"><span data-stu-id="2e9da-132">Open an investigation from an incident details page</span></span>

<span data-ttu-id="2e9da-133">使用事件详细信息页面查看有关事件的详细信息，包括触发的有关任何受影响的设备、用户帐户或邮箱的信息的警报。</span><span class="sxs-lookup"><span data-stu-id="2e9da-133">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="2e9da-134">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="2e9da-134">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="2e9da-135">在导航窗格中，选择"**事件&事件**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="2e9da-135">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 
3. <span data-ttu-id="2e9da-136">选择列表中的某个项目，然后选择"打开 **事件页面"。**</span><span class="sxs-lookup"><span data-stu-id="2e9da-136">Select an item in the list, and then choose **Open incident page**.</span></span>
4. <span data-ttu-id="2e9da-137">选择 **"调查"** 选项卡，然后在列表中选择调查。</span><span class="sxs-lookup"><span data-stu-id="2e9da-137">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="2e9da-138">将打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="2e9da-138">Its flyout pane opens.</span></span>
5. <span data-ttu-id="2e9da-139">选择 **"打开调查"页**。</span><span class="sxs-lookup"><span data-stu-id="2e9da-139">Select **Open investigation page**.</span></span> 

## <a name="investigation-details"></a><span data-ttu-id="2e9da-140">调查详细信息</span><span class="sxs-lookup"><span data-stu-id="2e9da-140">Investigation details</span></span>

<span data-ttu-id="2e9da-141">使用调查详细信息视图可查看过去、当前和挂起的与调查相关的活动。</span><span class="sxs-lookup"><span data-stu-id="2e9da-141">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="2e9da-142">调查详细信息视图类似于下图：</span><span class="sxs-lookup"><span data-stu-id="2e9da-142">The investigation details view resembles the following image:</span></span>

<span data-ttu-id="2e9da-143">在调查详细信息视图中，你可以看到调查 **图形**、警报、设备、标识、关键发现、实体、日志和挂起操作选项卡上的信息，如下表所述。    </span><span class="sxs-lookup"><span data-stu-id="2e9da-143">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="2e9da-144">你在调查详细信息页面中看到的特定选项卡取决于你的订阅包括的内容。</span><span class="sxs-lookup"><span data-stu-id="2e9da-144">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="2e9da-145">例如，如果你的订阅不包括 Microsoft Defender for Office 365 计划 2，你将看不到"邮箱 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2e9da-145">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="2e9da-146">Tab</span><span class="sxs-lookup"><span data-stu-id="2e9da-146">Tab</span></span> | <span data-ttu-id="2e9da-147">说明</span><span class="sxs-lookup"><span data-stu-id="2e9da-147">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="2e9da-148">**调查图**</span><span class="sxs-lookup"><span data-stu-id="2e9da-148">**Investigation graph**</span></span>   | <span data-ttu-id="2e9da-149">提供调查的可视化表示形式。</span><span class="sxs-lookup"><span data-stu-id="2e9da-149">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="2e9da-150">描述实体并列出发现的威胁，以及警报以及是否正在等待批准任何操作。</span><span class="sxs-lookup"><span data-stu-id="2e9da-150">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="2e9da-151">可以选择图形上的项目以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="2e9da-151">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="2e9da-152">例如，选择 **"证据**"图标将你带至"证据"选项卡，可在其中查看检测到的实体及其裁定。</span><span class="sxs-lookup"><span data-stu-id="2e9da-152">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="2e9da-153">**警告**</span><span class="sxs-lookup"><span data-stu-id="2e9da-153">**Alerts**</span></span>    | <span data-ttu-id="2e9da-154">列出与调查相关的警报。</span><span class="sxs-lookup"><span data-stu-id="2e9da-154">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="2e9da-155">警报可能来自用户设备上的威胁防护功能、Office 应用、云应用安全和其他 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="2e9da-155">Alerts can come from threat protection features on a user's device, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="2e9da-156">**设备**</span><span class="sxs-lookup"><span data-stu-id="2e9da-156">**Devices**</span></span> | <span data-ttu-id="2e9da-157">列出包含在调查中的设备及其修正级别。</span><span class="sxs-lookup"><span data-stu-id="2e9da-157">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="2e9da-158"> (修正级别对应于设备[组 .) ](automation-levels.md)</span><span class="sxs-lookup"><span data-stu-id="2e9da-158">(Remediation levels correspond to the [automation level for device groups](automation-levels.md).)</span></span> |
| <span data-ttu-id="2e9da-159">**邮箱**</span><span class="sxs-lookup"><span data-stu-id="2e9da-159">**Mailboxes**</span></span> |<span data-ttu-id="2e9da-160">列出受检测到的威胁影响的邮箱。</span><span class="sxs-lookup"><span data-stu-id="2e9da-160">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="2e9da-161">**用户**</span><span class="sxs-lookup"><span data-stu-id="2e9da-161">**Users**</span></span>  | <span data-ttu-id="2e9da-162">列出受检测到的威胁影响的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2e9da-162">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="2e9da-163">**证据**</span><span class="sxs-lookup"><span data-stu-id="2e9da-163">**Evidence**</span></span> | <span data-ttu-id="2e9da-164">列出由警报/调查引发的证据片段。</span><span class="sxs-lookup"><span data-stu-id="2e9da-164">Lists pieces of evidence raised by alerts/investigations.</span></span> <span data-ttu-id="2e9da-165">包括有关 *(、**可疑或**未找到* 威胁) 和修正状态裁定。</span><span class="sxs-lookup"><span data-stu-id="2e9da-165">Includes verdicts (*Malicious*, *Suspicious*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="2e9da-166">**Entities**</span><span class="sxs-lookup"><span data-stu-id="2e9da-166">**Entities**</span></span>  | <span data-ttu-id="2e9da-167">提供有关每个已分析实体的详细信息，包括每个实体类型裁定 (*恶意*、可疑或未找到任何威胁) 。 </span><span class="sxs-lookup"><span data-stu-id="2e9da-167">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="2e9da-168">**Log**</span><span class="sxs-lookup"><span data-stu-id="2e9da-168">**Log**</span></span>    | <span data-ttu-id="2e9da-169">提供触发警报后执行的所有调查操作按时间顺序的详细视图。</span><span class="sxs-lookup"><span data-stu-id="2e9da-169">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="2e9da-170">**挂起的操作**</span><span class="sxs-lookup"><span data-stu-id="2e9da-170">**Pending actions**</span></span> | <span data-ttu-id="2e9da-171">列出需要审批的项目以继续。</span><span class="sxs-lookup"><span data-stu-id="2e9da-171">Lists items that require approval to proceed.</span></span> <span data-ttu-id="2e9da-172">转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 审批挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="2e9da-172">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2e9da-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e9da-173">See also</span></span>

- [<span data-ttu-id="2e9da-174">在自动调查后查看修正操作</span><span class="sxs-lookup"><span data-stu-id="2e9da-174">Review remediation actions following an automated investigation</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="2e9da-175">查看和组织 Microsoft Defender 终结点事件队列</span><span class="sxs-lookup"><span data-stu-id="2e9da-175">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>](view-incidents-queue.md)