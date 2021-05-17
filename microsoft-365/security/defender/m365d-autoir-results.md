---
title: 自动调查的详细信息和结果
description: 查看 Microsoft 365 Defender 中自动调查的结果和主要发现
keywords: 自动化， 调查， 结果， 分析， 详细信息， 修正， autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: ad774fc36f4f167cb7a4e695b9f572ceb55b968b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274672"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="023dc-104">自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="023dc-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="023dc-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="023dc-105">**Applies to:**</span></span>
- <span data-ttu-id="023dc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="023dc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="023dc-107">使用 Microsoft 365 Defender，当自动[调查运行时，](m365d-autoir.md)有关该调查的详细信息在自动调查过程期间和之后均可用。</span><span class="sxs-lookup"><span data-stu-id="023dc-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="023dc-108">如果您具有 [必要的权限，](m365d-action-center.md#required-permissions-for-action-center-tasks)可以在调查详细信息视图中查看这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="023dc-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="023dc-109">此视图为您提供了最新状态以及批准任何挂起操作的能力。</span><span class="sxs-lookup"><span data-stu-id="023dc-109">This view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![调查详细信息](../../media/mtp-air-investdetails.png)

## <a name="new-unified-investigation-page"></a><span data-ttu-id="023dc-111"> ("新建！) 统一调查"页</span><span class="sxs-lookup"><span data-stu-id="023dc-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="023dc-112">最近更新了调查页面，以包含跨设备、电子邮件和协作内容的信息。</span><span class="sxs-lookup"><span data-stu-id="023dc-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="023dc-113">新的统一调查页面定义通用语言，并提供跨[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)和 Microsoft Defender for Office 365 进行自动[调查的统一体验](../office-365-security/defender-for-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="023dc-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="023dc-114">若要访问统一调查页面，请选择你将在以下位置看到的黄色横幅中的链接：</span><span class="sxs-lookup"><span data-stu-id="023dc-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>

- <span data-ttu-id="023dc-115">Office 365 安全与&中心 () [https://protection.office.com](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="023dc-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="023dc-116">Microsoft Defender 安全中心 () [https://securitycenter.windows.com](https://securitycenter.windows.com)</span><span class="sxs-lookup"><span data-stu-id="023dc-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="023dc-117">安全中心安全中心Microsoft 365事件 [https://security.microsoft.com](https://security.microsoft.com) () </span><span class="sxs-lookup"><span data-stu-id="023dc-117">Any incident or Action center experience in the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="023dc-118">打开调查详细信息视图</span><span class="sxs-lookup"><span data-stu-id="023dc-118">Open the investigation details view</span></span>

<span data-ttu-id="023dc-119">可以使用以下方法之一打开调查详细信息视图：</span><span class="sxs-lookup"><span data-stu-id="023dc-119">You can open the investigation details view by using one of the following methods:</span></span>

- [<span data-ttu-id="023dc-120">选择操作中心中的项目</span><span class="sxs-lookup"><span data-stu-id="023dc-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="023dc-121">从事件详细信息页面选择调查</span><span class="sxs-lookup"><span data-stu-id="023dc-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="023dc-122">选择操作中心中的项目</span><span class="sxs-lookup"><span data-stu-id="023dc-122">Select an item in the Action center</span></span>

<span data-ttu-id="023dc-123">改进[的操作中心](m365d-action-center.md) () 跨设备、电子邮件和协作内容和标识& [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 修正操作[](m365d-remediation-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="023dc-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="023dc-124">列出的操作包括自动或手动采取的修正操作。</span><span class="sxs-lookup"><span data-stu-id="023dc-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="023dc-125">在操作中心中，可以查看等待审批的操作以及已获得批准或已完成的操作。</span><span class="sxs-lookup"><span data-stu-id="023dc-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="023dc-126">还可以导航到更多详细信息，如调查页面。</span><span class="sxs-lookup"><span data-stu-id="023dc-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="023dc-127">您必须具有 [某些权限才能](m365d-action-center.md#required-permissions-for-action-center-tasks) 批准、拒绝或撤消操作。</span><span class="sxs-lookup"><span data-stu-id="023dc-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="023dc-128">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="023dc-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="023dc-129">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="023dc-129">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="023dc-130">在"挂起 **"或** " **历史记录"** 选项卡上，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="023dc-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="023dc-131">将打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="023dc-131">Its flyout pane opens.</span></span>

4. <span data-ttu-id="023dc-132">查看飞出窗格中的信息，然后执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="023dc-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="023dc-133">选择 **"打开调查"** 页以查看有关调查的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="023dc-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="023dc-134">选择 **"批准** "以启动挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="023dc-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="023dc-135">选择 **"** 拒绝"以防止执行挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="023dc-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="023dc-136">选择 **"开始搜寻**"转到"[高级搜寻"。](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="023dc-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="023dc-137">从事件详细信息页面打开调查</span><span class="sxs-lookup"><span data-stu-id="023dc-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="023dc-138">使用事件详细信息页面查看有关事件的详细信息，包括触发的有关任何受影响的设备、用户帐户或邮箱的信息的警报。</span><span class="sxs-lookup"><span data-stu-id="023dc-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="023dc-139">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="023dc-139">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="023dc-140">在导航窗格中，选择"**事件&事件**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="023dc-140">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 

3. <span data-ttu-id="023dc-141">选择列表中的某个项目，然后选择"打开 **事件页面"。**</span><span class="sxs-lookup"><span data-stu-id="023dc-141">Select an item in the list, and then choose **Open incident page**.</span></span>

4. <span data-ttu-id="023dc-142">选择 **"调查"** 选项卡，然后在列表中选择调查。</span><span class="sxs-lookup"><span data-stu-id="023dc-142">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="023dc-143">将打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="023dc-143">Its flyout pane opens.</span></span>

5. <span data-ttu-id="023dc-144">选择 **"打开调查"页**。</span><span class="sxs-lookup"><span data-stu-id="023dc-144">Select **Open investigation page**.</span></span> 

<span data-ttu-id="023dc-145">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="023dc-145">Here's an example.</span></span>

![事件详细信息](../../media/mtp-incidentdetails-tabs.png)

## <a name="investigation-details"></a><span data-ttu-id="023dc-147">调查详细信息</span><span class="sxs-lookup"><span data-stu-id="023dc-147">Investigation details</span></span>

<span data-ttu-id="023dc-148">使用调查详细信息视图可查看过去、当前和挂起的与调查相关的活动。</span><span class="sxs-lookup"><span data-stu-id="023dc-148">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="023dc-149">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="023dc-149">Here's an example.</span></span>

![调查详细信息](../../media/mtp-air-investdetails.png)

<span data-ttu-id="023dc-151">在调查详细信息视图中，你可以看到调查 **图形**、警报、设备、标识、关键发现、实体、日志和挂起操作选项卡上的信息，如下表所述。    </span><span class="sxs-lookup"><span data-stu-id="023dc-151">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="023dc-152">你在调查详细信息页面中看到的特定选项卡取决于你的订阅包括的内容。</span><span class="sxs-lookup"><span data-stu-id="023dc-152">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="023dc-153">例如，如果你的订阅不包括 Microsoft Defender for Office 365计划 2，你将看不到"邮箱 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="023dc-153">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="023dc-154">选项卡</span><span class="sxs-lookup"><span data-stu-id="023dc-154">Tab</span></span> | <span data-ttu-id="023dc-155">说明</span><span class="sxs-lookup"><span data-stu-id="023dc-155">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="023dc-156">**调查图**</span><span class="sxs-lookup"><span data-stu-id="023dc-156">**Investigation graph**</span></span>   | <span data-ttu-id="023dc-157">提供调查的可视化表示形式。</span><span class="sxs-lookup"><span data-stu-id="023dc-157">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="023dc-158">描述实体并列出发现的威胁，以及警报以及是否正在等待批准任何操作。</span><span class="sxs-lookup"><span data-stu-id="023dc-158">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="023dc-159">可以选择图形上的项目以查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="023dc-159">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="023dc-160">例如，选择 **"证据**"图标将你带至"证据"选项卡，可在其中查看检测到的实体及其裁定。</span><span class="sxs-lookup"><span data-stu-id="023dc-160">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="023dc-161">**警告**</span><span class="sxs-lookup"><span data-stu-id="023dc-161">**Alerts**</span></span>    | <span data-ttu-id="023dc-162">列出与调查相关的警报。</span><span class="sxs-lookup"><span data-stu-id="023dc-162">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="023dc-163">警报可能来自用户设备上的威胁防护功能、Office、Microsoft Cloud App Security和其他 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="023dc-163">Alerts can come from threat protection features on a user's device, in Office apps, Microsoft Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="023dc-164">**设备**</span><span class="sxs-lookup"><span data-stu-id="023dc-164">**Devices**</span></span> | <span data-ttu-id="023dc-165">列出包含在调查中的设备及其修正级别。</span><span class="sxs-lookup"><span data-stu-id="023dc-165">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="023dc-166"> (修正级别对应于设备[组 .) ](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)</span><span class="sxs-lookup"><span data-stu-id="023dc-166">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="023dc-167">**邮箱**</span><span class="sxs-lookup"><span data-stu-id="023dc-167">**Mailboxes**</span></span> |<span data-ttu-id="023dc-168">列出受检测到的威胁影响的邮箱。</span><span class="sxs-lookup"><span data-stu-id="023dc-168">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="023dc-169">**用户**</span><span class="sxs-lookup"><span data-stu-id="023dc-169">**Users**</span></span>  | <span data-ttu-id="023dc-170">列出受检测到的威胁影响的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="023dc-170">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="023dc-171">**证据**</span><span class="sxs-lookup"><span data-stu-id="023dc-171">**Evidence**</span></span> | <span data-ttu-id="023dc-172">列出由警报或调查引发的证据片段。</span><span class="sxs-lookup"><span data-stu-id="023dc-172">Lists pieces of evidence raised by alerts or investigations.</span></span> <span data-ttu-id="023dc-173">包括有关 *(、可疑*、*未知* 或未找到威胁) 和修正状态裁定。</span><span class="sxs-lookup"><span data-stu-id="023dc-173">Includes verdicts (*Malicious*, *Suspicious*, *Unknown*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="023dc-174">**Entities**</span><span class="sxs-lookup"><span data-stu-id="023dc-174">**Entities**</span></span>  | <span data-ttu-id="023dc-175">提供有关每个已分析实体的详细信息，包括每个实体类型裁定 (*恶意*、可疑或未找到任何威胁) 。 </span><span class="sxs-lookup"><span data-stu-id="023dc-175">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="023dc-176">**Log**</span><span class="sxs-lookup"><span data-stu-id="023dc-176">**Log**</span></span>    | <span data-ttu-id="023dc-177">提供触发警报后执行的所有调查操作按时间顺序的详细视图。</span><span class="sxs-lookup"><span data-stu-id="023dc-177">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="023dc-178">**挂起的操作历史记录**</span><span class="sxs-lookup"><span data-stu-id="023dc-178">**Pending actions history**</span></span> | <span data-ttu-id="023dc-179">列出需要审批的项目以继续。</span><span class="sxs-lookup"><span data-stu-id="023dc-179">Lists items that require approval to proceed.</span></span> <span data-ttu-id="023dc-180">转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 审批挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="023dc-180">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="023dc-181">后续步骤</span><span class="sxs-lookup"><span data-stu-id="023dc-181">Next steps</span></span>

- [<span data-ttu-id="023dc-182">查看和管理修正操作</span><span class="sxs-lookup"><span data-stu-id="023dc-182">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="023dc-183">详细了解修正操作</span><span class="sxs-lookup"><span data-stu-id="023dc-183">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)
