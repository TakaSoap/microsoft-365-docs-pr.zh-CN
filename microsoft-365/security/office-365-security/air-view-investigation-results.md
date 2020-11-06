---
title: 在 Microsoft 365 中查看自动调查的结果
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 在 Microsoft 365 中进行自动调查的过程中和之后，您可以查看结果和主要发现。
ms.date: 11/05/2020
ms.openlocfilehash: 0f472c117ff1f6c2b563063d0eeb9a27cc5afebe
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931986"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a><span data-ttu-id="e1118-104">Microsoft 365 中的自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="e1118-104">Details and results of an automated investigation in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e1118-105">在[Microsoft Defender For Office 365](office-365-atp.md)中进行[自动调查](office-365-air.md)时，有关调查的详细信息在自动调查过程期间和之后都可用。</span><span class="sxs-lookup"><span data-stu-id="e1118-105">When an [automated investigation](office-365-air.md) occurs in [Microsoft Defender for Office 365](office-365-atp.md), details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="e1118-106">如果您具有必要的权限，则可以在 Microsoft 365 安全中心中查看这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="e1118-106">If you have the necessary permissions, you can view those details in the Microsoft 365 security center.</span></span> <span data-ttu-id="e1118-107">调查详细信息为你提供最新状态，并能够批准任何挂起的操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-107">Investigation details provide you with up-to-date status, and the ability to approve any pending actions.</span></span>

## <a name="investigation-status"></a><span data-ttu-id="e1118-108">调查状态</span><span class="sxs-lookup"><span data-stu-id="e1118-108">Investigation status</span></span>

<span data-ttu-id="e1118-109">调查状态指示分析和操作的进度。</span><span class="sxs-lookup"><span data-stu-id="e1118-109">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="e1118-110">在调查运行时，状态更改以指示是否发现威胁，以及是否已批准操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-110">As the investigation runs, status changes to indicate whether threats were found, and whether actions have been approved.</span></span>

|<span data-ttu-id="e1118-111">状态</span><span class="sxs-lookup"><span data-stu-id="e1118-111">Status</span></span>|<span data-ttu-id="e1118-112">说明</span><span class="sxs-lookup"><span data-stu-id="e1118-112">Description</span></span>|
|:---|:---|
|<span data-ttu-id="e1118-113">**即将开始**</span><span class="sxs-lookup"><span data-stu-id="e1118-113">**Starting**</span></span> | <span data-ttu-id="e1118-114">调查已触发并等待开始运行。</span><span class="sxs-lookup"><span data-stu-id="e1118-114">The investigation has been triggered and waiting to start running.</span></span>|
|<span data-ttu-id="e1118-115">**正在运行**</span><span class="sxs-lookup"><span data-stu-id="e1118-115">**Running**</span></span> | <span data-ttu-id="e1118-116">调查过程已开始，正在进行中。</span><span class="sxs-lookup"><span data-stu-id="e1118-116">The investigation process has started and is underway.</span></span> <span data-ttu-id="e1118-117">在审批 [挂起的操作](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions#approve-or-reject-pending-actions) 时，也会发生此状态。</span><span class="sxs-lookup"><span data-stu-id="e1118-117">This state also occurs when [pending actions](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions#approve-or-reject-pending-actions) are approved.</span></span>|
|<span data-ttu-id="e1118-118">**找不到威胁**</span><span class="sxs-lookup"><span data-stu-id="e1118-118">**No Threats Found**</span></span> | <span data-ttu-id="e1118-119">调查已完成，且未标识 (用户帐户、电子邮件、URL 或文件) 的威胁。</span><span class="sxs-lookup"><span data-stu-id="e1118-119">The investigation has finished and no threats (user account, email message, URL, or file) were identified.</span></span> <br/><br/><span data-ttu-id="e1118-120">**提示** ：如果你怀疑缺少某些内容 (例如误报) ，则可以使用 [威胁资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)执行操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-120">**TIP** : If you suspect something was missed (such as a false negative), you can take action using [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).</span></span>|
|<span data-ttu-id="e1118-121">**发现威胁**</span><span class="sxs-lookup"><span data-stu-id="e1118-121">**Threats Found**</span></span> |<span data-ttu-id="e1118-122">自动调查发现了问题，但没有解决这些问题的具体补救措施。</span><span class="sxs-lookup"><span data-stu-id="e1118-122">The automated investigation found issues, but there are no specific remediation actions to resolve those issues.</span></span><br/><br/> <span data-ttu-id="e1118-123">当确定了某些类型的用户活动但没有可用的清除操作时，可能会出现 " **威胁已发现** " 状态。</span><span class="sxs-lookup"><span data-stu-id="e1118-123">The **Threats Found** status can occur when some type of user activity was identified but no cleanup actions are available.</span></span> <span data-ttu-id="e1118-124">示例包括以下任何用户活动：</span><span class="sxs-lookup"><span data-stu-id="e1118-124">Examples include any of the following user activities:</span></span> <br/><span data-ttu-id="e1118-125">- (DLP) 事件的[数据丢失防护](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies)</span><span class="sxs-lookup"><span data-stu-id="e1118-125">- A [data loss prevention](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) (DLP) event</span></span> <br/><span data-ttu-id="e1118-126">-发送异常的电子邮件</span><span class="sxs-lookup"><span data-stu-id="e1118-126">- An email sending anomaly</span></span> <br/><span data-ttu-id="e1118-127">-发送的恶意软件</span><span class="sxs-lookup"><span data-stu-id="e1118-127">- Sent malware</span></span> <br/><span data-ttu-id="e1118-128">-发送的网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="e1118-128">- Sent phish</span></span><br/><span data-ttu-id="e1118-129">调查发现没有要修正的恶意 Url、文件或电子邮件，并且没有要修复的邮箱活动，例如关闭转发规则或委派。</span><span class="sxs-lookup"><span data-stu-id="e1118-129">The investigation found no malicious URLs, files, or email messages to remediate, and no mailbox activity to fix, such as turning off forwarding rules or delegation.</span></span> <br/><br/><span data-ttu-id="e1118-130">**提示** ：如果你怀疑缺少某些内容 (例如误报) ，则可以使用 [威胁资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)进行调查并采取措施。</span><span class="sxs-lookup"><span data-stu-id="e1118-130">**TIP** : If you suspect something was missed (such as a false negative), you can investigate and take action using [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).</span></span>|
|<span data-ttu-id="e1118-131">**已由系统终止**</span><span class="sxs-lookup"><span data-stu-id="e1118-131">**Terminated By System**</span></span> | <span data-ttu-id="e1118-132">调查已停止。</span><span class="sxs-lookup"><span data-stu-id="e1118-132">The investigation stopped.</span></span> <span data-ttu-id="e1118-133">调查可能因以下几个原因而停止：</span><span class="sxs-lookup"><span data-stu-id="e1118-133">An investigation can stop for several reasons:</span></span><br/><span data-ttu-id="e1118-134">-调查的待处理操作已过期。</span><span class="sxs-lookup"><span data-stu-id="e1118-134">- The investigation's pending actions expired.</span></span> <span data-ttu-id="e1118-135">等待为期一周的批准后，待处理的操作超时。</span><span class="sxs-lookup"><span data-stu-id="e1118-135">Pending actions time out after awaiting approval for one week.</span></span> <br/><span data-ttu-id="e1118-136">-操作过多。</span><span class="sxs-lookup"><span data-stu-id="e1118-136">- There are too many actions.</span></span> <span data-ttu-id="e1118-137">例如，如果单击恶意 Url 的用户过多，则可能会超过调查运行所有分析器的能力，因此调查将暂停。</span><span class="sxs-lookup"><span data-stu-id="e1118-137">For example, if there are too many users clicking on malicious URLs, it can exceed the investigation's ability to run all the analyzers, so the investigation halts.</span></span> <br/><br/><span data-ttu-id="e1118-138">**提示** ：如果调查在执行操作之前停止，请尝试使用 [威胁资源管理器](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) 查找和解决威胁。</span><span class="sxs-lookup"><span data-stu-id="e1118-138">**TIP** : If an investigation halts before actions were taken, try using [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) to find and address threats.</span></span>|
|<span data-ttu-id="e1118-139">**挂起的操作**</span><span class="sxs-lookup"><span data-stu-id="e1118-139">**Pending Action**</span></span> | <span data-ttu-id="e1118-140">调查发现威胁，如恶意电子邮件、恶意 URL 或有风险的邮箱设置，以及用于补救威胁正在 [等待批准](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions)的操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-140">The investigation has found a threat, such as a malicious email, a malicious URL, or a risky mailbox setting, and an action to remediate that threat is [awaiting approval](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions).</span></span><br/><br/><span data-ttu-id="e1118-141">如果发现任何具有相应操作的威胁，则会触发 **挂起操作** 状态。</span><span class="sxs-lookup"><span data-stu-id="e1118-141">The **Pending Action** state is triggered when any threat with a corresponding action is found.</span></span> <span data-ttu-id="e1118-142">但是，在调查运行时，挂起操作的列表可能会增加。</span><span class="sxs-lookup"><span data-stu-id="e1118-142">However, the list of pending actions can increase as an investigation runs.</span></span> <span data-ttu-id="e1118-143">检查 [调查日志](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#playbook-log) 以查看其他项目是否仍处于待完成状态。</span><span class="sxs-lookup"><span data-stu-id="e1118-143">Check the [investigation log](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#playbook-log) to see if other items are still pending completion.</span></span>|
|<span data-ttu-id="e1118-144">**已修正**</span><span class="sxs-lookup"><span data-stu-id="e1118-144">**Remediated**</span></span> | <span data-ttu-id="e1118-145">调查已完成，并批准了所有修正操作 (这将被视为完全修正) 。</span><span class="sxs-lookup"><span data-stu-id="e1118-145">The investigation finished and all remediation actions were approved (this is noted as fully remediated).</span></span><br/><br/><span data-ttu-id="e1118-146">**注意** ：批准的修正操作可能会出现错误，从而导致无法执行操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-146">**NOTE** : Approved remediation actions can have errors that prevent the actions from being taken.</span></span> <span data-ttu-id="e1118-147">无论纠正措施是否成功完成，调查状态不会更改。</span><span class="sxs-lookup"><span data-stu-id="e1118-147">Regardless of whether remediation actions are successfully completed, the investigation status does not change.</span></span> <span data-ttu-id="e1118-148">检查 [调查日志](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results) 中的详细结果。</span><span class="sxs-lookup"><span data-stu-id="e1118-148">Check the [investigation log](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results) for detailed results.</span></span>|
|<span data-ttu-id="e1118-149">**部分修正**</span><span class="sxs-lookup"><span data-stu-id="e1118-149">**Partially Remediated**</span></span>| <span data-ttu-id="e1118-150">调查导致了补救措施，有些已批准并已完成。</span><span class="sxs-lookup"><span data-stu-id="e1118-150">The investigation resulted in remediation actions, and some were approved and completed.</span></span> <span data-ttu-id="e1118-151">其他操作仍 [处于挂起状态](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions)。</span><span class="sxs-lookup"><span data-stu-id="e1118-151">Other actions are still [pending](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions).</span></span>|
|<span data-ttu-id="e1118-152">**失败**</span><span class="sxs-lookup"><span data-stu-id="e1118-152">**Failed**</span></span> | <span data-ttu-id="e1118-153">至少一个调查分析器遇到无法正确完成的问题。</span><span class="sxs-lookup"><span data-stu-id="e1118-153">At least one investigation analyzer ran into a problem where it could not complete properly.</span></span> <br/><br/><span data-ttu-id="e1118-154">**注意** ：如果在批准了修正操作后调查失败，则修正操作可能仍为 "成功"。</span><span class="sxs-lookup"><span data-stu-id="e1118-154">**NOTE** : If an investigation fails after remediation actions were approved, the remediation actions might still have succeeded.</span></span> <span data-ttu-id="e1118-155">检查 [调查日志](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results) 中的详细结果。</span><span class="sxs-lookup"><span data-stu-id="e1118-155">Check the [investigation log](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results) for detailed results.</span></span>|
|<span data-ttu-id="e1118-156">**按限制排队**</span><span class="sxs-lookup"><span data-stu-id="e1118-156">**Queued By Throttling**</span></span> | <span data-ttu-id="e1118-157">在队列中保留调查。</span><span class="sxs-lookup"><span data-stu-id="e1118-157">An investigation is being held in a queue.</span></span> <span data-ttu-id="e1118-158">当其他调查完成时，将开始排队调查。</span><span class="sxs-lookup"><span data-stu-id="e1118-158">When other investigations complete, queued investigations begin.</span></span> <span data-ttu-id="e1118-159">限制有助于避免较差的服务性能。</span><span class="sxs-lookup"><span data-stu-id="e1118-159">Throttling helps avoid poor service performance.</span></span> <br/><br/><span data-ttu-id="e1118-160">**提示** ：挂起的操作可能会限制可运行的新调查数。</span><span class="sxs-lookup"><span data-stu-id="e1118-160">**TIP** : Pending actions can limit how many new investigations can run.</span></span> <span data-ttu-id="e1118-161">请务必 [批准 (或拒绝) 挂起的操作](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions#approve-or-reject-pending-actions)。</span><span class="sxs-lookup"><span data-stu-id="e1118-161">Make sure to [approve (or reject) pending actions](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-review-approve-pending-completed-actions#approve-or-reject-pending-actions).</span></span>|
|<span data-ttu-id="e1118-162">**已通过限制终止**</span><span class="sxs-lookup"><span data-stu-id="e1118-162">**Terminated By Throttling**</span></span> | <span data-ttu-id="e1118-163">如果队列中保留的调查过长，它将停止。</span><span class="sxs-lookup"><span data-stu-id="e1118-163">If an investigation is held in the queue too long, it stops.</span></span> <br/><br/><span data-ttu-id="e1118-164">**提示** ：您可以 [从威胁资源管理器开始调查](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="e1118-164">**TIP** : You can [start an investigation from Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>|
|

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="e1118-165">查看调查的详细信息</span><span class="sxs-lookup"><span data-stu-id="e1118-165">View details of an investigation</span></span>

1. <span data-ttu-id="e1118-166">请转到 Security & 合规性中心 ([https://protection.office.com](https://protection.office.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="e1118-166">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="e1118-167">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="e1118-167">Do one of the following actions:</span></span>

    - <span data-ttu-id="e1118-168">转到 " **威胁管理**  >  **仪表板** "。</span><span class="sxs-lookup"><span data-stu-id="e1118-168">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="e1118-169">这将转到 [安全仪表板](security-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="e1118-169">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="e1118-170">您的空中小组件显示在 [安全仪表板](security-dashboard.md)的顶部。</span><span class="sxs-lookup"><span data-stu-id="e1118-170">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="e1118-171">选择一个小部件，如 **调查摘要** 。</span><span class="sxs-lookup"><span data-stu-id="e1118-171">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="e1118-172">转到 **威胁管理**  >  **调查** 。</span><span class="sxs-lookup"><span data-stu-id="e1118-172">Go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="e1118-173">每种方法都将转到调查列表。</span><span class="sxs-lookup"><span data-stu-id="e1118-173">Either method takes you to a list of investigations.</span></span>

    ![空气的主要调查页面](../../media/air-maininvestigationpage.png)

3. <span data-ttu-id="e1118-175">在调查列表中，选择 " **ID** " 列中的项目。</span><span class="sxs-lookup"><span data-stu-id="e1118-175">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="e1118-176">这将打开 "调查详细信息" 页，从视图中的调查图形开始。</span><span class="sxs-lookup"><span data-stu-id="e1118-176">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![空中调查图形页面](../../media/air-investigationgraphpage.png)

   <span data-ttu-id="e1118-178">使用各种选项卡了解有关调查的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e1118-178">Use the various tabs to learn more about the investigation.</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="e1118-179">查看与调查相关的警报的详细信息</span><span class="sxs-lookup"><span data-stu-id="e1118-179">View details about an alert related to an investigation</span></span>

<span data-ttu-id="e1118-180">某些类型的警报会在 Microsoft 365 中触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="e1118-180">Certain kinds of alerts trigger automated investigation in Microsoft 365.</span></span> <span data-ttu-id="e1118-181">若要了解详细信息，请参阅 [触发自动调查的警报策略](office-365-air.md#which-alert-policies-trigger-automated-investigations)。</span><span class="sxs-lookup"><span data-stu-id="e1118-181">To learn more, see [alert policies that trigger automated investigations](office-365-air.md#which-alert-policies-trigger-automated-investigations).</span></span> 

<span data-ttu-id="e1118-182">使用以下过程可查看与自动调查相关联的警报的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e1118-182">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="e1118-183">请转到 Security & 合规性中心 ([https://protection.office.com](https://protection.office.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="e1118-183">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="e1118-184">转到 **威胁管理**  >  **调查** 。</span><span class="sxs-lookup"><span data-stu-id="e1118-184">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="e1118-185">在调查列表中，选择 " **ID** " 列中的项目。</span><span class="sxs-lookup"><span data-stu-id="e1118-185">In the list of investigations, select an item in the **ID** column.</span></span>

4. <span data-ttu-id="e1118-186">通过打开调查的详细信息，选择 " **通知** " 选项卡。下面列出了所有触发调查的警报。</span><span class="sxs-lookup"><span data-stu-id="e1118-186">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="e1118-187">选择列表项。</span><span class="sxs-lookup"><span data-stu-id="e1118-187">Select an item in the list.</span></span> <span data-ttu-id="e1118-188">将打开一个浮出控件，其中包含有关该警报的详细信息以及指向其他信息和操作的链接。</span><span class="sxs-lookup"><span data-stu-id="e1118-188">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="e1118-189">查看浮出控件上的信息，根据特定的通知执行操作，如 **Resolve** 、 **隐含** 或 **通知用户** 。</span><span class="sxs-lookup"><span data-stu-id="e1118-189">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve** , **Suppress** , or **Notify users**.</span></span>

    - <span data-ttu-id="e1118-190">**Resolve** 等效于关闭通知</span><span class="sxs-lookup"><span data-stu-id="e1118-190">**Resolve** is equivalent to closing an alert</span></span>

    - <span data-ttu-id="e1118-191">**禁止** 使策略在指定时间段内触发警报</span><span class="sxs-lookup"><span data-stu-id="e1118-191">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>

    - <span data-ttu-id="e1118-192">**通知用户** 启动电子邮件，其中包含已输入的用户电子邮件地址，并允许安全操作团队向这些用户键入邮件。</span><span class="sxs-lookup"><span data-stu-id="e1118-192">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="e1118-193"> (这类似于使用 [威胁资源管理器](threat-explorer.md)向收件人发送邮件。 ) </span><span class="sxs-lookup"><span data-stu-id="e1118-193">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>

## <a name="how-to-use-the-various-tabs"></a><span data-ttu-id="e1118-194">如何使用各种选项卡</span><span class="sxs-lookup"><span data-stu-id="e1118-194">How to use the various tabs</span></span>

<span data-ttu-id="e1118-195">以下各节将引导您完成 "自动调查" 页面上的各种选项卡，以及如何使用这些信息。</span><span class="sxs-lookup"><span data-stu-id="e1118-195">The following sections walk you through the various tabs on the automated investigations page and how you can use the information.</span></span>

### <a name="automated-investigations-page"></a><span data-ttu-id="e1118-196">自动调查页面</span><span class="sxs-lookup"><span data-stu-id="e1118-196">Automated investigations page</span></span>

<span data-ttu-id="e1118-197">"自动调查" 页面显示您的组织的调查及其当前状态。</span><span class="sxs-lookup"><span data-stu-id="e1118-197">The automated investigations page shows your organization's investigations and their current states.</span></span>

![空气的主要调查页面](../../media/air-maininvestigationpage.png)

<span data-ttu-id="e1118-199">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e1118-199">You can:</span></span>

- <span data-ttu-id="e1118-200">直接导航到调查 (选择 **调查 ID** ) 。</span><span class="sxs-lookup"><span data-stu-id="e1118-200">Navigate directly to an investigation (select an **Investigation ID** ).</span></span>

- <span data-ttu-id="e1118-201">应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="e1118-201">Apply filters.</span></span> <span data-ttu-id="e1118-202">从 **调查类型** 、 **时间范围** 、 **状态** 或这些情况的组合中进行选择。</span><span class="sxs-lookup"><span data-stu-id="e1118-202">Choose from **Investigation Type** , **Time range** , **Status** , or a combination of these.</span></span>

- <span data-ttu-id="e1118-203">将数据导出到 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="e1118-203">Export the data to a .csv file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="e1118-204">调查图形</span><span class="sxs-lookup"><span data-stu-id="e1118-204">Investigation graph</span></span>

<span data-ttu-id="e1118-205">当您打开特定调查时，您将看到 "调查图形" 页。</span><span class="sxs-lookup"><span data-stu-id="e1118-205">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="e1118-206">此页面显示了所有不同的实体：电子邮件、用户 (及其活动) ，以及作为触发的警报的一部分自动调查的设备。</span><span class="sxs-lookup"><span data-stu-id="e1118-206">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![空中调查图形页面](../../media/air-investigationgraphpage.png)

<span data-ttu-id="e1118-208">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e1118-208">You can:</span></span>

- <span data-ttu-id="e1118-209">获取当前调查的直观概述。</span><span class="sxs-lookup"><span data-stu-id="e1118-209">Get a visual overview of the current investigation.</span></span>

- <span data-ttu-id="e1118-210">查看调查持续时间的摘要。</span><span class="sxs-lookup"><span data-stu-id="e1118-210">View a summary of the investigation duration.</span></span>

- <span data-ttu-id="e1118-211">在可视化中选择一个节点以查看该节点的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e1118-211">Select a node in the visualization to view details for that node.</span></span>

- <span data-ttu-id="e1118-212">在顶部选择一个选项卡以查看该选项卡的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e1118-212">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="e1118-213">通知调查</span><span class="sxs-lookup"><span data-stu-id="e1118-213">Alert investigation</span></span>

<span data-ttu-id="e1118-214">在调查的 " **通知** " 选项卡上，您可以查看与调查相关的警报。</span><span class="sxs-lookup"><span data-stu-id="e1118-214">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="e1118-215">详细信息包括触发调查的警报以及与调查相关的其他关联警报（如有风险的登录、 [DLP 策略](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) 冲突等）。</span><span class="sxs-lookup"><span data-stu-id="e1118-215">Details include the alert that triggered the investigation and other correlated alerts, such as risky sign-in, [DLP policy](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) violations, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="e1118-216">在此页面中，安全分析员还可以查看各个通知的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="e1118-216">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![空气警报页面](../../media/air-investigationalertspage.png)

<span data-ttu-id="e1118-218">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e1118-218">You can:</span></span>

- <span data-ttu-id="e1118-219">获取当前触发警报和任何关联警报的直观概述。</span><span class="sxs-lookup"><span data-stu-id="e1118-219">Get a visual overview of the current triggering alert and any associated alerts.</span></span>

- <span data-ttu-id="e1118-220">在列表中选择一个警报，打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="e1118-220">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="e1118-221">电子邮件调查</span><span class="sxs-lookup"><span data-stu-id="e1118-221">Email investigation</span></span>

<span data-ttu-id="e1118-222">在调查的 " **电子邮件** " 选项卡上，您可以查看原始电子邮件和在调查过程中标识的类似电子邮件的群集。</span><span class="sxs-lookup"><span data-stu-id="e1118-222">On the **Email** tab for an investigation, you can see the original emails and the clusters of similar email identified as part of the investigation.</span></span> <span data-ttu-id="e1118-223">" **电子邮件** " 选项卡还显示与调查相关的电子邮件项目，例如用户报告的电子邮件详细信息、报告的原始电子邮件、电子邮件 (s) zapped 由于恶意软件/网络钓鱼诈骗等。</span><span class="sxs-lookup"><span data-stu-id="e1118-223">The **Email** tab also shows email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

![空中电子邮件调查页面](../../media/air-investigationemailpage.png)

<span data-ttu-id="e1118-225">通过电子邮件调查，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e1118-225">With email investigation, you can:</span></span>

- <span data-ttu-id="e1118-226">获取当前群集结果和发现的威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="e1118-226">Get a visual overview of the current clustering results and threats found.</span></span>

- <span data-ttu-id="e1118-227">单击 "群集" 实体或威胁列表打开显示完整警报详细信息的弹出页面。</span><span class="sxs-lookup"><span data-stu-id="e1118-227">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>

- <span data-ttu-id="e1118-228">通过单击 " **电子邮件群集详细信息** " 选项卡顶部的 " **在资源管理器中打开** " 链接进一步调查电子邮件群集</span><span class="sxs-lookup"><span data-stu-id="e1118-228">Further investigate the email cluster by clicking the **Open in Explorer** link at the top of the **Email cluster details** tab</span></span>

![使用浮出控件详细信息的航空调查电子邮件](../../media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="e1118-230">鉴于组织中的用户发送和接收的大量电子邮件，以及电子邮件通信和攻击的多用户性质，以下过程可能需要很长时间：</span><span class="sxs-lookup"><span data-stu-id="e1118-230">Given the sheer volume of email that users in an organization send and receive, plus the multi-user nature of email communications and attacks, the following process can take a significant amount of time:</span></span>

1. <span data-ttu-id="e1118-231">根据邮件头、正文、URL 和附件中的类似属性来群集电子邮件</span><span class="sxs-lookup"><span data-stu-id="e1118-231">Clustering email messages based on similar attributes from a message header, body, URL, and attachments</span></span>

2. <span data-ttu-id="e1118-232">将恶意电子邮件与优质电子邮件分开</span><span class="sxs-lookup"><span data-stu-id="e1118-232">Separating malicious email from the good email</span></span>

3. <span data-ttu-id="e1118-233">对恶意电子邮件采取操作</span><span class="sxs-lookup"><span data-stu-id="e1118-233">Taking action on malicious email messages</span></span>

<span data-ttu-id="e1118-234">AIR 自动化了此过程，从而节省了贵组织的安全团队时间和精力。</span><span class="sxs-lookup"><span data-stu-id="e1118-234">AIR automates this process, saving your organization's security team time and effort.</span></span> 

#### <a name="types-of-email-clusters"></a><span data-ttu-id="e1118-235">电子邮件群集的类型</span><span class="sxs-lookup"><span data-stu-id="e1118-235">Types of email clusters</span></span>

<span data-ttu-id="e1118-236">电子邮件分析步骤中可以识别三种不同类型的电子邮件群集：相似性群集 (所有调查) 、指示器群集 (所有调查) 和邮箱/用户群集。</span><span class="sxs-lookup"><span data-stu-id="e1118-236">Three different types of email clusters can be identified during the email analysis step: similarity clusters (all investigations), indicator clusters (all investigations), and mailbox/user clusters.</span></span> <span data-ttu-id="e1118-237">下表介绍了这些类型的电子邮件群集。</span><span class="sxs-lookup"><span data-stu-id="e1118-237">The following table describes these types of email clusters.</span></span>

|<span data-ttu-id="e1118-238">电子邮件群集</span><span class="sxs-lookup"><span data-stu-id="e1118-238">Email cluster</span></span>  |<span data-ttu-id="e1118-239">说明</span><span class="sxs-lookup"><span data-stu-id="e1118-239">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="e1118-240">相似性群集</span><span class="sxs-lookup"><span data-stu-id="e1118-240">Similarity clusters</span></span>     |<span data-ttu-id="e1118-241">通过搜寻电子邮件（具有类似的发件人和内容属性）来识别的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e1118-241">Email messages identified by hunting for emails with similar sender and content attributes.</span></span> <span data-ttu-id="e1118-242">根据原始检测结果评估这些群集中的恶意内容。</span><span class="sxs-lookup"><span data-stu-id="e1118-242">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="e1118-243">包含足够恶意电子邮件检测的电子邮件群集被视为恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e1118-243">Email clusters that contain enough malicious email detections are considered malicious.</span></span>         |
|<span data-ttu-id="e1118-244">指示器群集</span><span class="sxs-lookup"><span data-stu-id="e1118-244">Indicator clusters</span></span> | <span data-ttu-id="e1118-245">通过搜寻同一指示器实体标识的电子邮件 (来自原始电子邮件的文件哈希或 URL) 。</span><span class="sxs-lookup"><span data-stu-id="e1118-245">Email messages that are identified by hunting for the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="e1118-246">将原始文件/URL 实体标识为恶意时，AIR 会将指示器判定为包含该实体的电子邮件的整个群集。</span><span class="sxs-lookup"><span data-stu-id="e1118-246">When the original file/URL entity is identified as malicious, AIR applies the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="e1118-247">被标识为恶意软件的文件意味着包含该文件的电子邮件群集将被视为恶意软件电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e1118-247">A file identified as malware means that the cluster of email messages containing that file are treated as malware email messages.</span></span> |
|<span data-ttu-id="e1118-248">邮箱/用户群集</span><span class="sxs-lookup"><span data-stu-id="e1118-248">Mailbox/user clusters</span></span> | <span data-ttu-id="e1118-249">与用户泄露调查中涉及的用户相关的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e1118-249">Email messages related to the user involved in a user compromise investigation.</span></span>  <span data-ttu-id="e1118-250">这些电子邮件群集可供安全操作团队进行进一步分析，且不会生成电子邮件修正操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-250">These email clusters are for further analysis by the security operations team and will not generate email remediation actions.</span></span> <br/> <span data-ttu-id="e1118-251">已损坏的用户安全行动手册将检查要分析的用户发送的电子邮件，以便了解从邮箱发送的电子邮件的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="e1118-251">The compromised user security playbook  reviews the emails being sent by the user being analyzed in order to understand the potential impact of the emails being sent from the mailbox.</span></span> |

> [!NOTE]
> <span data-ttu-id="e1118-252">群集的目标是查找和查找与攻击或市场活动中的同一发件人发送的其他相关电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e1118-252">The goal of clustering is to hunt and find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>  <span data-ttu-id="e1118-253">在某些情况下，合法的电子邮件可能会触发调查 (例如，用户会报告营销电子邮件) 。</span><span class="sxs-lookup"><span data-stu-id="e1118-253">In some cases, legitimate email might trigger an investigation (for example, a user reports a marketing email).</span></span>  <span data-ttu-id="e1118-254">在这些方案中，电子邮件群集应确定电子邮件群集不是恶意的–如果它相应地执行此操作，则不会表示威胁，也 **不** 会建议删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e1118-254">In these scenarios, the email clustering should identify that email clusters are not malicious – when it appropriately does so, it will **not** indicate a threat, nor will it recommend email removal.</span></span>

#### <a name="email-classifications"></a><span data-ttu-id="e1118-255">电子邮件分类</span><span class="sxs-lookup"><span data-stu-id="e1118-255">Email classifications</span></span>

<span data-ttu-id="e1118-256">在分析电子邮件时，会将它们归为 " *恶意* "、" *可疑* " 或 " *清除* " (，但 *不标识为威胁* ) ：</span><span class="sxs-lookup"><span data-stu-id="e1118-256">As email messages are analyzed, they are classified as *malicious* , *suspicious* , or *clean* (as in, *not identified as a threat* ):</span></span>

- <span data-ttu-id="e1118-257">从邮箱/用户发送的 *恶意电子邮件* 表明邮箱/帐户可能会受到危害。</span><span class="sxs-lookup"><span data-stu-id="e1118-257">*Malicious emails* sent from the mailbox/user  indicate potential compromise of the mailbox/account.</span></span> <span data-ttu-id="e1118-258">将显示可能受恶意电子邮件影响的其他用户/邮箱作为危害的一部分。</span><span class="sxs-lookup"><span data-stu-id="e1118-258">Other users/mailboxes that are potentially impacted by malicious email as part of a compromise are shown.</span></span>

- <span data-ttu-id="e1118-259">邮箱/用户发送的 *可疑电子邮件* 表明可能存在已损坏的帐户或不需要的电子邮件活动。</span><span class="sxs-lookup"><span data-stu-id="e1118-259">*Suspicious emails* sent by the mailbox/user indicate the potential for a compromised account or unwanted email activity.</span></span> <span data-ttu-id="e1118-260">这些邮件包括从邮箱发送的任何垃圾邮件/批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e1118-260">These messages include any spam/bulk email sent from the mailbox.</span></span>

- <span data-ttu-id="e1118-261">*清理电子邮件* (被视为不受) 邮箱/用户发送的威胁的电子邮件可以向安全操作团队提供已发送的合法用户电子邮件的视图。</span><span class="sxs-lookup"><span data-stu-id="e1118-261">*Clean emails* (emails that are considered not a threat) sent by the mailbox/user can provide your security operations team with a view of legitimate user emails sent.</span></span> <span data-ttu-id="e1118-262">但是，如果电子邮件帐户受到威胁，这些电子邮件也可能包含数据 exfiltration。</span><span class="sxs-lookup"><span data-stu-id="e1118-262">However, these emails can also include data exfiltration if the email account is compromised.</span></span>

#### <a name="more-about-email-counts"></a><span data-ttu-id="e1118-263">有关电子邮件计数的详细信息</span><span class="sxs-lookup"><span data-stu-id="e1118-263">More about email counts</span></span>

<span data-ttu-id="e1118-264">"电子邮件" 选项卡上标识的电子邮件计数当前表示在 " **电子邮件** " 选项卡上显示的所有电子邮件的总数。由于电子邮件存在于多个群集中，因此 (的电子邮件的实际总数) 是在所有群集和原始收件人的电子邮件中显示的唯一电子邮件数。</span><span class="sxs-lookup"><span data-stu-id="e1118-264">The email count identified on the email tab currently represents the sum total of all email messages that shown on the **Email** tab. Because email messages are present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) is the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span>

<span data-ttu-id="e1118-265">根据每个收件人， [资源管理器](threat-explorer.md) 和空中计数电子邮件，因为安全 verdicts、操作和传递位置在每个收件人的基础上是不同的。</span><span class="sxs-lookup"><span data-stu-id="e1118-265">Both [Explorer](threat-explorer.md) and AIR count email messages on a per-recipient basis, because the security verdicts, actions, and delivery locations vary on a per-recipient basis.</span></span> <span data-ttu-id="e1118-266">因此，发送给三个用户的原始电子邮件总共计三封电子邮件，而不是一封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e1118-266">Thus, an original email sent to three users counts as a total of three email messages instead of one email.</span></span> 

<span data-ttu-id="e1118-267">在某些情况下，可能会对电子邮件进行两次或多次计数，例如电子邮件在其上有多个操作，或当所有操作发生时有多个电子邮件副本时。</span><span class="sxs-lookup"><span data-stu-id="e1118-267">There might be cases where an email gets counted two or more times, such as when an email has multiple actions on it, or when there are multiple copies of the email when all the actions occur.</span></span> 

<span data-ttu-id="e1118-268">例如，在传递时检测到的恶意软件电子邮件会导致阻止 (隔离) 电子邮件，并将替换的电子邮件 (威胁文件替换为警告文件，然后传递到用户的邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="e1118-268">For example, a malware email that is detected at delivery can result in both a blocked (quarantined) email and a replaced email (threat file replaced with a warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="e1118-269">由于系统中的电子邮件有两个副本，这两个副本可能会在群集计数中进行计数。</span><span class="sxs-lookup"><span data-stu-id="e1118-269">Because there are literally two copies of the email in the system, both might be counted in cluster counts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1118-270">下面是一些需要注意的事项：</span><span class="sxs-lookup"><span data-stu-id="e1118-270">Here are a few points to keep in mind:</span></span>
> 
> - <span data-ttu-id="e1118-271">电子邮件计数是在调查时计算的，在您打开基于基础查询) 的调查 flyouts (时，会重新计算一些计数。</span><span class="sxs-lookup"><span data-stu-id="e1118-271">Email counts are calculated at the time of the investigation, and some counts are recalculated when you open investigation flyouts (based on an underlying query).</span></span> 
> 
> - <span data-ttu-id="e1118-272">为 " **电子邮件** " 选项卡上的电子邮件群集显示的电子邮件计数，在调查时将计算在 "群集浮出控件" 上显示的电子邮件数量值，并且不要更改。</span><span class="sxs-lookup"><span data-stu-id="e1118-272">The email counts shown for the email clusters on the **Email** tab and the email quantity value shown on cluster flyout are calculated at the time of investigation, and do not change.</span></span> 
> 
> - <span data-ttu-id="e1118-273">在电子邮件群集浮出控件的 " **电子邮件** " 选项卡底部显示的电子邮件计数，资源管理器中显示的电子邮件计数反映在调查的初始分析之后收到的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e1118-273">The email count shown at the bottom of the **Email** tab of the email cluster flyout and the count of email messages shown in Explorer reflect email messages received after the investigation's initial analysis.</span></span> 

<span data-ttu-id="e1118-274">因此，显示原始数量10封电子邮件的电子邮件群集将在调查分析阶段和管理员审查调查时，显示一个电子邮件列表总计15封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e1118-274">Thus, an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when five more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span> <span data-ttu-id="e1118-275">同样，旧调查可能会开始显示比资源管理器查询更高的计数，因为 Microsoft Defender for Office 365 计划2中的数据在试用版的7天后过期，在30天后适用于付费许可证。</span><span class="sxs-lookup"><span data-stu-id="e1118-275">Likewise, old investigations might start showing higher counts than Explorer queries show, because data in Microsoft Defender for Office 365 Plan 2 expires after 7 days for trials and after 30 days for paid licenses.</span></span>  

<span data-ttu-id="e1118-276">在不同视图中显示计数历史和当前计数已完成，以指示调查时的电子邮件影响和当前影响，直到运行补救时间为止。</span><span class="sxs-lookup"><span data-stu-id="e1118-276">Showing both count historical and current counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

> [!NOTE]
> <span data-ttu-id="e1118-277">在电子邮件上下文中，您可能会在调查过程中看到一个卷异常威胁曲面。</span><span class="sxs-lookup"><span data-stu-id="e1118-277">In the context of email, you might see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="e1118-278">卷异常表明调查事件时间与之前的时间框架相比，与调查事件的类似电子邮件中的峰值。</span><span class="sxs-lookup"><span data-stu-id="e1118-278">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="e1118-279">这种具有类似特征的电子邮件通信中的此峰值 (例如，subject 和发件人域、正文相似性和发件人 IP) 通常是电子邮件市场活动或攻击的开始。</span><span class="sxs-lookup"><span data-stu-id="e1118-279">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span> <span data-ttu-id="e1118-280">但是，批量、垃圾邮件和合法电子邮件活动通常共享这些特征。</span><span class="sxs-lookup"><span data-stu-id="e1118-280">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span> 
>
> <span data-ttu-id="e1118-281">由于使用反病毒引擎、沙箱或恶意信誉识别的恶意软件或网络钓鱼威胁相比，大量异常会带来潜在的威胁，因此可能会降低严重程度。</span><span class="sxs-lookup"><span data-stu-id="e1118-281">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="e1118-282">用户调查</span><span class="sxs-lookup"><span data-stu-id="e1118-282">User investigation</span></span>

<span data-ttu-id="e1118-283">在 " **用户** " 选项卡上，您可以看到标识为调查的一部分的所有用户。</span><span class="sxs-lookup"><span data-stu-id="e1118-283">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="e1118-284">当存在事件或指示这些用户帐户可能受到影响或受到威胁时，用户帐户将出现在调查中。</span><span class="sxs-lookup"><span data-stu-id="e1118-284">User accounts appear in the investigation when there is an event or indication that those user accounts might be affected or compromised.</span></span>

<span data-ttu-id="e1118-285">例如，在下图中，空气根据创建的新收件箱规则确定了安全指标和异常情况。</span><span class="sxs-lookup"><span data-stu-id="e1118-285">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="e1118-286">可通过此选项卡中的详细视图获取调查 (证据) 的其他详细信息。损坏的现象和异常也可能包含来自 [Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)的异常检测。</span><span class="sxs-lookup"><span data-stu-id="e1118-286">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies might also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![空中调查用户页](../../media/air-investigationuserspage.png)

<span data-ttu-id="e1118-288">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e1118-288">You can:</span></span>

- <span data-ttu-id="e1118-289">获取已确定的用户结果和发现的风险的直观概述。</span><span class="sxs-lookup"><span data-stu-id="e1118-289">Get a visual overview of identified user results and risks found.</span></span>

- <span data-ttu-id="e1118-290">选择用户以打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="e1118-290">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="e1118-291">机器调查</span><span class="sxs-lookup"><span data-stu-id="e1118-291">Machine investigation</span></span>

<span data-ttu-id="e1118-292">在 " **计算机** " 选项卡上，您可以看到标识为调查的一部分的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="e1118-292">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span>

![空中调查计算机页面](../../media/air-investigationmachinepage.png)

<span data-ttu-id="e1118-294">作为一些行动手册的一部分，空中将电子邮件威胁与设备关联 (例如，Zapped 恶意软件) 。</span><span class="sxs-lookup"><span data-stu-id="e1118-294">As part of some playbooks, AIR correlates email threats to devices (for example, Zapped malware).</span></span> <span data-ttu-id="e1118-295">例如，调查会将恶意文件哈希传递到 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) 以进行调查。</span><span class="sxs-lookup"><span data-stu-id="e1118-295">For example, an investigation passes a malicious file hash across to [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) to investigate.</span></span> <span data-ttu-id="e1118-296">这样，就可以为您的用户自动调查相关的计算机，以帮助确保在云中和终结点上解决威胁。</span><span class="sxs-lookup"><span data-stu-id="e1118-296">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span>

<span data-ttu-id="e1118-297">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e1118-297">You can:</span></span>

- <span data-ttu-id="e1118-298">获取发现的当前计算机和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="e1118-298">Get a visual overview of the current machines and threats found.</span></span>

-  <span data-ttu-id="e1118-299">选择一台计算机以打开在 Microsoft Defender 安全中心的相关 [Microsoft defender For Endpoint 调查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 中的视图。</span><span class="sxs-lookup"><span data-stu-id="e1118-299">Select a machine to open a view that into the related [Microsoft Defender for Endpoint investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) in the Microsoft Defender Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="e1118-300">实体调查</span><span class="sxs-lookup"><span data-stu-id="e1118-300">Entity investigation</span></span>

<span data-ttu-id="e1118-301">在 " **实体** " 选项卡上，您可以看到在调查过程中标识和分析的实体。</span><span class="sxs-lookup"><span data-stu-id="e1118-301">On the **Entities** tab, you can see the entities identified and analyzed as part of the investigation.</span></span>

<span data-ttu-id="e1118-302">在这里，您可以查看调查的实体和实体类型的详细信息，例如电子邮件、群集、IP 地址、用户等。</span><span class="sxs-lookup"><span data-stu-id="e1118-302">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="e1118-303">您还可以查看已分析的实体数以及与每个实体相关联的威胁。</span><span class="sxs-lookup"><span data-stu-id="e1118-303">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span>

!["航空调查实体" 页](../../media/air-investigationentitiespage.png)

<span data-ttu-id="e1118-305">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e1118-305">You can:</span></span>

- <span data-ttu-id="e1118-306">获取发现的调查实体和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="e1118-306">Get a visual overview of the investigation entities and threats found.</span></span>

- <span data-ttu-id="e1118-307">选择一个实体以打开显示相关实体详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="e1118-307">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![空中调查实体详细信息](../../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="e1118-309">行动手册日志</span><span class="sxs-lookup"><span data-stu-id="e1118-309">Playbook log</span></span>

<span data-ttu-id="e1118-310">在 " **日志** " 选项卡上，您可以查看调查过程中的所有操作手册步骤。</span><span class="sxs-lookup"><span data-stu-id="e1118-310">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="e1118-311">该日志将捕获由 Office 365 自动调查功能作为空气的一部分完成的所有分析器和操作的完整清单。</span><span class="sxs-lookup"><span data-stu-id="e1118-311">The log captures a complete inventory of all analyzers and actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="e1118-312">它提供了所执行的所有步骤的清晰视图，包括操作本身、说明以及实际 "开始到完成" 的持续时间。</span><span class="sxs-lookup"><span data-stu-id="e1118-312">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span>

![航空调查日志页](../../media/air-investigationlogpage.png)

<span data-ttu-id="e1118-314">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e1118-314">You can:</span></span>

- <span data-ttu-id="e1118-315">获取有关执行操作手册步骤的直观概述。</span><span class="sxs-lookup"><span data-stu-id="e1118-315">Get see a visual overview of the playbook steps taken.</span></span>

- <span data-ttu-id="e1118-316">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="e1118-316">Export the results to a CSV file.</span></span>
- <span data-ttu-id="e1118-317">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="e1118-317">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="e1118-318">建议的操作</span><span class="sxs-lookup"><span data-stu-id="e1118-318">Recommended actions</span></span>

<span data-ttu-id="e1118-319">在 " **操作** " 选项卡上，您可以查看在调查完成后建议用于修正的所有操作手册操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-319">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> <span data-ttu-id="e1118-320">操作会捕获 Microsoft 建议在调查结束时执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="e1118-320">Actions capture the steps Microsoft recommends you take at the end of an investigation.</span></span> <span data-ttu-id="e1118-321">您可以通过选择一个或多个操作来采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="e1118-321">You can take remediation actions here by selecting one or more actions.</span></span> 

<span data-ttu-id="e1118-322">选择 " **批准** " 可开始进行修正。</span><span class="sxs-lookup"><span data-stu-id="e1118-322">Selecting **Approve** allows remediation to begin.</span></span> <span data-ttu-id="e1118-323"> (需要适当的权限-必须具备 **搜索和清除** 角色才能从资源管理器和 AIR) 运行操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-323">(Appropriate permissions are needed - the **Search And Purge** role is required to run actions from Explorer and AIR).</span></span> 

<span data-ttu-id="e1118-324">例如，安全读者可以查看操作，但不能批准。</span><span class="sxs-lookup"><span data-stu-id="e1118-324">For example, a Security Reader can view actions, but not approve them.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e1118-325">您无需批准每个操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-325">You do not have to approve every action.</span></span> <span data-ttu-id="e1118-326">如果您不同意建议的操作，或者您的组织未选择特定类型的操作，则可以选择 **拒绝** 这些操作，也可以仅忽略它们，不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-326">If you do not agree with the recommended action or your organization does not choose certain types of actions, then you can choose to **Reject** the actions or simply ignore them and take no action.</span></span> <span data-ttu-id="e1118-327">"批准和/或拒绝所有操作" 可让调查完全关闭 (状态变为 "已修正") ，而保留某些操作不完整将导致调查状态更改为 "部分修正" 状态。</span><span class="sxs-lookup"><span data-stu-id="e1118-327">Approving and/or rejecting all actions lets the investigation fully close (status becomes remediated), while leaving some actions incomplete results in the investigation status changing to a partially remediated state.</span></span>

![航空调查操作页](../../media/air-investigationactionspage.png)

<span data-ttu-id="e1118-329">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e1118-329">You can:</span></span>

- <span data-ttu-id="e1118-330">获取对操作手册建议的操作的直观概述。</span><span class="sxs-lookup"><span data-stu-id="e1118-330">Get a visual overview of the playbook-recommended actions.</span></span>

- <span data-ttu-id="e1118-331">选择一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-331">Select a single action or multiple actions.</span></span>

- <span data-ttu-id="e1118-332">使用注释批准或拒绝建议的操作。</span><span class="sxs-lookup"><span data-stu-id="e1118-332">Approve or reject recommended actions with comments.</span></span>

- <span data-ttu-id="e1118-333">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="e1118-333">Export the results to a CSV file.</span></span>

- <span data-ttu-id="e1118-334">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="e1118-334">Filter the view.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e1118-335">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e1118-335">Next steps</span></span>

- [<span data-ttu-id="e1118-336">查看和批准挂起的操作</span><span class="sxs-lookup"><span data-stu-id="e1118-336">Review and approve pending actions</span></span>](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)

