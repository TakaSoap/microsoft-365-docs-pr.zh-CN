---
title: 自动调查的详细信息和结果
description: 在自动调查期间和之后，可以查看结果和关键发现
keywords: 自动化， 调查， 结果， 分析， 详细信息， 修正， autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
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
ms.date: 02/08/2021
ms.openlocfilehash: fb4ffc2a3061934340c69d2655ffbd29bdff3100
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50925240"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="a975c-104">自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="a975c-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a975c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a975c-105">**Applies to:**</span></span>
- <span data-ttu-id="a975c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a975c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a975c-107">使用 Microsoft 365 Defender，当自动调查运行时，有关该调查的详细信息在自动调查过程期间和之后均可用。 [](mtp-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="a975c-107">With Microsoft 365 Defender, when an [automated investigation](mtp-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="a975c-108">如果您具有 [必要的权限，](mtp-action-center.md#required-permissions-for-action-center-tasks)可以在调查详细信息视图中查看这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="a975c-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="a975c-109">调查详细信息视图为您提供了最新状态以及批准任何挂起操作的能力。</span><span class="sxs-lookup"><span data-stu-id="a975c-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![调查详细信息](../../media/mtp-air-investdetails.png)

## <a name="new-unified-investigation-page"></a><span data-ttu-id="a975c-111"> ("新建！) 统一调查"页</span><span class="sxs-lookup"><span data-stu-id="a975c-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="a975c-112">最近更新了调查页面，以包含跨设备、电子邮件和协作内容的信息。</span><span class="sxs-lookup"><span data-stu-id="a975c-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="a975c-113">新的统一调查页面定义通用语言，并提供跨 [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 和 Microsoft Defender [for Office 365](../office-365-security/office-365-atp.md)自动调查的统一体验。</span><span class="sxs-lookup"><span data-stu-id="a975c-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/office-365-atp.md).</span></span> <span data-ttu-id="a975c-114">若要访问统一调查页面，请选择你将在以下位置看到的黄色横幅中的链接：</span><span class="sxs-lookup"><span data-stu-id="a975c-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>
- <span data-ttu-id="a975c-115">Office 365 安全与合规中心&调查 [https://protection.office.com](https://protection.office.com) () </span><span class="sxs-lookup"><span data-stu-id="a975c-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="a975c-116">Microsoft Defender 安全中心内的任何调查 [https://securitycenter.windows.com](https://securitycenter.windows.com) () </span><span class="sxs-lookup"><span data-stu-id="a975c-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="a975c-117">改进的 Microsoft 365 安全中心安全中心 () [https://security.microsoft.com](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a975c-117">Any incident or Action center experience in the improved Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="a975c-118">打开调查详细信息视图</span><span class="sxs-lookup"><span data-stu-id="a975c-118">Open the investigation details view</span></span>

<span data-ttu-id="a975c-119">可以使用以下方法之一打开调查详细信息视图：</span><span class="sxs-lookup"><span data-stu-id="a975c-119">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="a975c-120">选择操作中心中的项目</span><span class="sxs-lookup"><span data-stu-id="a975c-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="a975c-121">从事件详细信息页面选择调查</span><span class="sxs-lookup"><span data-stu-id="a975c-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="a975c-122">选择操作中心中的项目</span><span class="sxs-lookup"><span data-stu-id="a975c-122">Select an item in the Action center</span></span>

<span data-ttu-id="a975c-123">改进[的操作中心](mtp-action-center.md) () 跨设备、电子邮件和协作内容和标识& [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 修正操作[](mtp-remediation-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="a975c-123">The improved [Action center](mtp-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](mtp-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="a975c-124">列出的操作包括自动或手动采取的修正操作。</span><span class="sxs-lookup"><span data-stu-id="a975c-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="a975c-125">在操作中心中，可以查看等待审批的操作以及已获得批准或已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="a975c-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="a975c-126">还可以导航到更多详细信息，如调查页面。</span><span class="sxs-lookup"><span data-stu-id="a975c-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="a975c-127">您必须具有 [某些权限才能](mtp-action-center.md#required-permissions-for-action-center-tasks) 批准、拒绝或撤消操作。</span><span class="sxs-lookup"><span data-stu-id="a975c-127">You must have [certain permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="a975c-128">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="a975c-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="a975c-129">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="a975c-129">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="a975c-130">在"挂起 **"或** " **历史记录"** 选项卡上，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="a975c-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="a975c-131">将打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="a975c-131">Its flyout pane opens.</span></span>
4. <span data-ttu-id="a975c-132">查看飞出窗格中的信息，然后执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="a975c-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="a975c-133">选择 **"打开调查"** 页以查看有关调查的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="a975c-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="a975c-134">选择 **"批准** "以启动挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="a975c-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="a975c-135">选择 **"** 拒绝"以防止执行挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="a975c-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="a975c-136">选择 **"开始搜寻**"转到"[高级搜寻"。](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a975c-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="a975c-137">从事件详细信息页面打开调查</span><span class="sxs-lookup"><span data-stu-id="a975c-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="a975c-138">使用事件详细信息页面查看有关事件的详细信息，包括触发的有关任何受影响的设备、用户帐户或邮箱的信息的警报。</span><span class="sxs-lookup"><span data-stu-id="a975c-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

![事件详细信息](../../media/mtp-incidentdetails-tabs.png)

1. <span data-ttu-id="a975c-140">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="a975c-140">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="a975c-141">在导航窗格中，选择"**事件&事件**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="a975c-141">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 
3. <span data-ttu-id="a975c-142">选择列表中的某个项目，然后选择"打开 **事件页面"。**</span><span class="sxs-lookup"><span data-stu-id="a975c-142">Select an item in the list, and then choose **Open incident page**.</span></span>
4. <span data-ttu-id="a975c-143">选择 **"调查"** 选项卡，然后在列表中选择调查。</span><span class="sxs-lookup"><span data-stu-id="a975c-143">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="a975c-144">将打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="a975c-144">Its flyout pane opens.</span></span>
5. <span data-ttu-id="a975c-145">选择 **"打开调查"页**。</span><span class="sxs-lookup"><span data-stu-id="a975c-145">Select **Open investigation page**.</span></span> 

## <a name="investigation-details"></a><span data-ttu-id="a975c-146">调查详细信息</span><span class="sxs-lookup"><span data-stu-id="a975c-146">Investigation details</span></span>

<span data-ttu-id="a975c-147">使用调查详细信息视图可查看过去、当前和挂起的与调查相关的活动。</span><span class="sxs-lookup"><span data-stu-id="a975c-147">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="a975c-148">调查详细信息视图类似于下图：</span><span class="sxs-lookup"><span data-stu-id="a975c-148">The investigation details view resembles the following image:</span></span>

![调查详细信息](../../media/mtp-air-investdetails.png)

<span data-ttu-id="a975c-150">在调查详细信息视图中，你可以看到调查 **图形**、警报、设备、标识、关键发现、实体、日志和挂起操作选项卡上的信息，如下表所述。    </span><span class="sxs-lookup"><span data-stu-id="a975c-150">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="a975c-151">你在调查详细信息页面中看到的特定选项卡取决于你的订阅包括的内容。</span><span class="sxs-lookup"><span data-stu-id="a975c-151">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="a975c-152">例如，如果你的订阅不包括 Microsoft Defender for Office 365 计划 2，你将看不到"邮箱 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a975c-152">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="a975c-153">选项卡</span><span class="sxs-lookup"><span data-stu-id="a975c-153">Tab</span></span> | <span data-ttu-id="a975c-154">说明</span><span class="sxs-lookup"><span data-stu-id="a975c-154">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="a975c-155">**调查图**</span><span class="sxs-lookup"><span data-stu-id="a975c-155">**Investigation graph**</span></span>   | <span data-ttu-id="a975c-156">提供调查的可视化表示形式。</span><span class="sxs-lookup"><span data-stu-id="a975c-156">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="a975c-157">描述实体并列出发现的威胁，以及警报以及是否正在等待批准任何操作。</span><span class="sxs-lookup"><span data-stu-id="a975c-157">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="a975c-158">可以选择图形上的项目以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="a975c-158">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="a975c-159">例如，选择 **"证据**"图标将你带至"证据"选项卡，可在其中查看检测到的实体及其裁定。</span><span class="sxs-lookup"><span data-stu-id="a975c-159">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="a975c-160">**警告**</span><span class="sxs-lookup"><span data-stu-id="a975c-160">**Alerts**</span></span>    | <span data-ttu-id="a975c-161">列出与调查相关的警报。</span><span class="sxs-lookup"><span data-stu-id="a975c-161">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="a975c-162">警报可能来自用户设备上的威胁防护功能、Office 应用、云应用安全和其他 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="a975c-162">Alerts can come from threat protection features on a user's device, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="a975c-163">**设备**</span><span class="sxs-lookup"><span data-stu-id="a975c-163">**Devices**</span></span> | <span data-ttu-id="a975c-164">列出包含在调查中的设备及其修正级别。</span><span class="sxs-lookup"><span data-stu-id="a975c-164">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="a975c-165"> (修正级别对应于设备[组 .) ](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)</span><span class="sxs-lookup"><span data-stu-id="a975c-165">(Remediation levels correspond to [the automation level for device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="a975c-166">**邮箱**</span><span class="sxs-lookup"><span data-stu-id="a975c-166">**Mailboxes**</span></span> |<span data-ttu-id="a975c-167">列出受检测到的威胁影响的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a975c-167">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="a975c-168">**用户**</span><span class="sxs-lookup"><span data-stu-id="a975c-168">**Users**</span></span>  | <span data-ttu-id="a975c-169">列出受检测到的威胁影响的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a975c-169">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="a975c-170">**证据**</span><span class="sxs-lookup"><span data-stu-id="a975c-170">**Evidence**</span></span> | <span data-ttu-id="a975c-171">列出由警报/调查引发的证据片段。</span><span class="sxs-lookup"><span data-stu-id="a975c-171">Lists pieces of evidence raised by alerts/investigations.</span></span> <span data-ttu-id="a975c-172">包括有关 *(、**可疑或**未找到* 威胁) 和修正状态裁定。</span><span class="sxs-lookup"><span data-stu-id="a975c-172">Includes verdicts (*Malicious*, *Suspicious*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="a975c-173">**Entities**</span><span class="sxs-lookup"><span data-stu-id="a975c-173">**Entities**</span></span>  | <span data-ttu-id="a975c-174">提供有关每个已分析实体的详细信息，包括每个实体类型裁定 (*恶意*、可疑或未找到任何威胁) 。 </span><span class="sxs-lookup"><span data-stu-id="a975c-174">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="a975c-175">**Log**</span><span class="sxs-lookup"><span data-stu-id="a975c-175">**Log**</span></span>    | <span data-ttu-id="a975c-176">提供触发警报后执行的所有调查操作按时间顺序的详细视图。</span><span class="sxs-lookup"><span data-stu-id="a975c-176">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="a975c-177">**挂起的操作**</span><span class="sxs-lookup"><span data-stu-id="a975c-177">**Pending actions**</span></span> | <span data-ttu-id="a975c-178">列出需要审批的项目以继续。</span><span class="sxs-lookup"><span data-stu-id="a975c-178">Lists items that require approval to proceed.</span></span> <span data-ttu-id="a975c-179">转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 审批挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="a975c-179">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="a975c-180">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a975c-180">Next steps</span></span>

- [<span data-ttu-id="a975c-181">在自动调查后批准或拒绝修正操作</span><span class="sxs-lookup"><span data-stu-id="a975c-181">Approve or reject remediation actions following an automated investigation</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="a975c-182">详细了解修正操作</span><span class="sxs-lookup"><span data-stu-id="a975c-182">Learn more about remediation actions</span></span>](mtp-remediation-actions.md)
