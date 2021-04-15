---
title: 解决 Microsoft Defender for终结点的误报/负数
description: 了解如何在 Microsoft Defender for Endpoint 中处理误报或漏报。
keywords: 防病毒， 异常， 排除， defender atp， 误报， 假负， 阻止的文件， 阻止的 URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
- m365solution-scenario
- m365scenario-fpfn
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs, yonghree, jcedola
ms.custom: FPFN
ms.openlocfilehash: f2615cf5ec49c9df27472f04c367f30511e9c0cc
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759866"
---
# <a name="address-false-positivesnegatives-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="fea5a-104">解决 Microsoft Defender for终结点的误报/负数</span><span class="sxs-lookup"><span data-stu-id="fea5a-104">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fea5a-105">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="fea5a-105">**Applies to**</span></span>

- [<span data-ttu-id="fea5a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fea5a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146806)

<span data-ttu-id="fea5a-107">在终结点保护解决方案中，误报是一个实体（如文件或进程）被检测并标识为恶意实体，即使实体实际上不是威胁。</span><span class="sxs-lookup"><span data-stu-id="fea5a-107">In endpoint protection solutions, a false positive is an entity, such as a file or a process, that was detected and identified as malicious, even though the entity isn't actually a threat.</span></span> <span data-ttu-id="fea5a-108">漏报是未检测为威胁的实体，即使它实际上是恶意实体。</span><span class="sxs-lookup"><span data-stu-id="fea5a-108">A false negative is an entity that was not detected as a threat, even though it actually is malicious.</span></span> <span data-ttu-id="fea5a-109">任何威胁防护解决方案（包括 [Microsoft Defender for Endpoint）](microsoft-defender-endpoint.md)都可能发生误报/负面影响。</span><span class="sxs-lookup"><span data-stu-id="fea5a-109">False positives/negatives can occur with any threat protection solution, including [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).</span></span>

![Defender for Endpoint 中的误报和负值定义](images/false-positives-overview.png)

<span data-ttu-id="fea5a-111">幸运的是，可以采取措施来解决并减少此类问题。</span><span class="sxs-lookup"><span data-stu-id="fea5a-111">Fortunately, steps can be taken to address and reduce these kinds of issues.</span></span> <span data-ttu-id="fea5a-112">如果你在 [Microsoft Defender](../defender/microsoft-365-security-center-mde.md)安全中心看到误报/负面影响，你的安全操作可以通过以下过程采取一些措施来解决这些问题：</span><span class="sxs-lookup"><span data-stu-id="fea5a-112">If you're seeing false positives/negatives in your [Microsoft Defender Security Center](../defender/microsoft-365-security-center-mde.md), your security operations can take steps to address them by using the following process:</span></span>

1.  [<span data-ttu-id="fea5a-113">查看警报并进行分类</span><span class="sxs-lookup"><span data-stu-id="fea5a-113">Review and classify alerts</span></span>](#part-1-review-and-classify-alerts) 
2.  [<span data-ttu-id="fea5a-114">查看已采取的修正操作</span><span class="sxs-lookup"><span data-stu-id="fea5a-114">Review remediation actions that were taken</span></span>](#part-2-review-remediation-actions)
3.  [<span data-ttu-id="fea5a-115">查看并定义排除项</span><span class="sxs-lookup"><span data-stu-id="fea5a-115">Review and define exclusions</span></span>](#part-3-review-or-define-exclusions)
4.  [<span data-ttu-id="fea5a-116">提交实体进行分析</span><span class="sxs-lookup"><span data-stu-id="fea5a-116">Submit an entity for analysis</span></span>](#part-4-submit-a-file-for-analysis)
5.  [<span data-ttu-id="fea5a-117">查看和调整威胁防护设置</span><span class="sxs-lookup"><span data-stu-id="fea5a-117">Review and adjust your threat protection settings</span></span>](#part-5-review-and-adjust-your-threat-protection-settings)

<span data-ttu-id="fea5a-118">执行本文所述任务后，如果仍有误报/负值问题，可以获取帮助。</span><span class="sxs-lookup"><span data-stu-id="fea5a-118">You can get help if you still have issues with false positives/negatives after performing the tasks described in this article.</span></span> <span data-ttu-id="fea5a-119">请参阅 [是否仍然需要帮助？](#still-need-help)</span><span class="sxs-lookup"><span data-stu-id="fea5a-119">See [Still need help?](#still-need-help)</span></span>

![解决误报和负面影响的步骤](images/false-positives-step-diagram.png)

> [!NOTE]
> <span data-ttu-id="fea5a-121">本文旨在指导使用 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)的安全操作员和安全管理员。</span><span class="sxs-lookup"><span data-stu-id="fea5a-121">This article is intended as guidance for security operators and security administrators who are using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).</span></span>

## <a name="part-1-review-and-classify-alerts"></a><span data-ttu-id="fea5a-122">第 1 部分：查看警报并分类</span><span class="sxs-lookup"><span data-stu-id="fea5a-122">Part 1: Review and classify alerts</span></span>

<span data-ttu-id="fea5a-123">如果 [看到由于检测到](alerts.md) 恶意或可疑的警报而触发的警报，可以抑制该实体的警报。</span><span class="sxs-lookup"><span data-stu-id="fea5a-123">If you see an [alert](alerts.md) that was triggered because something was detected as malicious or suspicious that should not have been, you can suppress the alert for that entity.</span></span> <span data-ttu-id="fea5a-124">您还可以禁止不一定是误报但不重要的警报。</span><span class="sxs-lookup"><span data-stu-id="fea5a-124">You can also suppress alerts that are not necessarily false positives, but are unimportant.</span></span> <span data-ttu-id="fea5a-125">建议您对警报进行分类。</span><span class="sxs-lookup"><span data-stu-id="fea5a-125">We recommend that you classify alerts as well.</span></span> 

<span data-ttu-id="fea5a-126">管理警报和分类真/假误报有助于培训威胁防护解决方案，并随着时间的推移减少误报或漏报数量。</span><span class="sxs-lookup"><span data-stu-id="fea5a-126">Managing your alerts and classifying true/false positives helps to train your threat protection solution and can reduce the number of false positives or false negatives over time.</span></span> <span data-ttu-id="fea5a-127">执行这些步骤还有助于减少安全操作仪表板中的干扰，以便安全团队可以专注于优先级较高的工作项。</span><span class="sxs-lookup"><span data-stu-id="fea5a-127">Taking these steps also helps reduce noise in your security operations dashboard so that your security team can focus on higher priority work items.</span></span>

### <a name="determine-whether-an-alert-is-accurate"></a><span data-ttu-id="fea5a-128">确定警报是否准确</span><span class="sxs-lookup"><span data-stu-id="fea5a-128">Determine whether an alert is accurate</span></span>

<span data-ttu-id="fea5a-129">在分类或抑制警报之前，请确定警报是准确、误报还是恶意。</span><span class="sxs-lookup"><span data-stu-id="fea5a-129">Before you classify or suppress an alert, determine whether the alert is accurate, a false positive, or benign.</span></span>

1. <span data-ttu-id="fea5a-130">转到 Microsoft Defender 安全中心 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-130">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-131">在导航窗格中，选择"**警报队列"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-131">In the navigation pane, choose **Alerts queue**.</span></span>

3. <span data-ttu-id="fea5a-132">选择警报以了解有关警报的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="fea5a-132">Select an alert to more details about the alert.</span></span> <span data-ttu-id="fea5a-133"> (查看 Microsoft [Defender 终结点](review-alerts.md).) 中的警报</span><span class="sxs-lookup"><span data-stu-id="fea5a-133">(See [Review alerts in Microsoft Defender for Endpoint](review-alerts.md).)</span></span>

4. <span data-ttu-id="fea5a-134">根据警报状态，执行下表中所述的步骤：</span><span class="sxs-lookup"><span data-stu-id="fea5a-134">Depending on the alert status, take the steps described in the following table:</span></span> 

| <span data-ttu-id="fea5a-135">警报状态</span><span class="sxs-lookup"><span data-stu-id="fea5a-135">Alert status</span></span> | <span data-ttu-id="fea5a-136">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="fea5a-136">What to do</span></span> |
|:---|:---|
| <span data-ttu-id="fea5a-137">警报准确无误</span><span class="sxs-lookup"><span data-stu-id="fea5a-137">The alert is accurate</span></span> | <span data-ttu-id="fea5a-138">分配警报，然后 [进一步调查](investigate-alerts.md) 。</span><span class="sxs-lookup"><span data-stu-id="fea5a-138">Assign the alert, and then [investigate it](investigate-alerts.md) further.</span></span> |
| <span data-ttu-id="fea5a-139">警报为误报</span><span class="sxs-lookup"><span data-stu-id="fea5a-139">The alert is a false positive</span></span> | <span data-ttu-id="fea5a-140">[1. 将警报](#classify-an-alert)分类为误报。</span><span class="sxs-lookup"><span data-stu-id="fea5a-140">1. [Classify the alert](#classify-an-alert) as a false positive.</span></span> <br/><span data-ttu-id="fea5a-141">2. [禁止显示警报](#suppress-an-alert)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-141">2. [Suppress the alert](#suppress-an-alert).</span></span> <br/> <span data-ttu-id="fea5a-142">3. [为](#indicators-for-microsoft-defender-for-endpoint) Microsoft Defender 终结点创建指示器。</span><span class="sxs-lookup"><span data-stu-id="fea5a-142">3. [Create an indicator](#indicators-for-microsoft-defender-for-endpoint) for Microsoft Defender for Endpoint.</span></span> <br/> <span data-ttu-id="fea5a-143">4. [将文件提交给 Microsoft 进行分析](#part-4-submit-a-file-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-143">4. [Submit a file to Microsoft for analysis](#part-4-submit-a-file-for-analysis).</span></span> |
| <span data-ttu-id="fea5a-144">警报准确无误，但 (不重要) </span><span class="sxs-lookup"><span data-stu-id="fea5a-144">The alert is accurate, but benign (unimportant)</span></span> | <span data-ttu-id="fea5a-145">[将警报分类](#classify-an-alert) 为真正的正数，然后 [抑制该警报](#suppress-an-alert)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-145">[Classify the alert](#classify-an-alert) as a true positive, and then [suppress the alert](#suppress-an-alert).</span></span> |

### <a name="classify-an-alert"></a><span data-ttu-id="fea5a-146">对警报进行分类</span><span class="sxs-lookup"><span data-stu-id="fea5a-146">Classify an alert</span></span>

<span data-ttu-id="fea5a-147">可以在 Microsoft Defender 安全中心将警报分类为误报或真正的误报。</span><span class="sxs-lookup"><span data-stu-id="fea5a-147">Alerts can be classified as false positives or true positives in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="fea5a-148">对警报进行分类有助于训练 Microsoft Defender for Endpoint，以便随着时间的推移，你将看到更多真实警报和更少的假警报。</span><span class="sxs-lookup"><span data-stu-id="fea5a-148">Classifying alerts helps train Microsoft Defender for Endpoint so that, over time, you'll see more true alerts and fewer false alerts.</span></span>

1. <span data-ttu-id="fea5a-149">转到 Microsoft Defender 安全中心 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-149">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-150">选择 **"警报队列**"，然后选择警报。</span><span class="sxs-lookup"><span data-stu-id="fea5a-150">Select **Alerts queue**, and then select an alert.</span></span>

3. <span data-ttu-id="fea5a-151">对于所选警报，选择"**操作""**  >  **管理警报"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-151">For the selected alert, select **Actions** > **Manage alert**.</span></span> <span data-ttu-id="fea5a-152">将打开一个飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="fea5a-152">A flyout pane opens.</span></span>

4. <span data-ttu-id="fea5a-153">在"**管理警报"** 部分，选择"**真警报"或**"**假警报"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-153">In the **Manage alert** section, select either **True alert** or **False alert**.</span></span> <span data-ttu-id="fea5a-154"> (使用 False **警报** 对误报进行分类。) </span><span class="sxs-lookup"><span data-stu-id="fea5a-154">(Use **False alert** to classify a false positive.)</span></span>

> [!TIP]
> <span data-ttu-id="fea5a-155">有关抑制警报的信息，请参阅管理 [适用于终结点的 Microsoft Defender 警报](/microsoft-365/security/defender-endpoint/manage-alerts)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-155">For more information about suppressing alerts, see [Manage Microsoft Defender for Endpoint alerts](/microsoft-365/security/defender-endpoint/manage-alerts).</span></span> <span data-ttu-id="fea5a-156">此外，如果你的组织在 SIEM (使用安全信息和事件) ，请确保也定义抑制规则。</span><span class="sxs-lookup"><span data-stu-id="fea5a-156">And, if your organization is using a security information and event management (SIEM) server, make sure to define a suppression rule there, too.</span></span> 

### <a name="suppress-an-alert"></a><span data-ttu-id="fea5a-157">抑制警报</span><span class="sxs-lookup"><span data-stu-id="fea5a-157">Suppress an alert</span></span>

<span data-ttu-id="fea5a-158">如果你的警报是误报或真正的误报，但对于不重要的事件，可以在 Microsoft Defender 安全中心中抑制这些警报。</span><span class="sxs-lookup"><span data-stu-id="fea5a-158">If you have alerts that are either false positives or that are true positives but for unimportant events, you can suppress those alerts in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="fea5a-159">抑制警报有助于减少安全操作仪表板中的噪音。</span><span class="sxs-lookup"><span data-stu-id="fea5a-159">Suppressing alerts helps reduce noise in your security operations dashboard.</span></span> 

1. <span data-ttu-id="fea5a-160">转到 Microsoft Defender 安全中心 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-160">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-161">在导航窗格中，选择 **警报队列**。</span><span class="sxs-lookup"><span data-stu-id="fea5a-161">In the navigation pane, select **Alerts queue**.</span></span>

3. <span data-ttu-id="fea5a-162">选择要禁止的警报以打开其" **详细信息"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="fea5a-162">Select an alert that you want to suppress to open its **Details** pane.</span></span>

4. <span data-ttu-id="fea5a-163">在"**详细信息"** 窗格中，选择省略号 **" (...) "，** 然后选择"**创建抑制规则"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-163">In the **Details** pane, choose the ellipsis (**...**), and then **Create a suppression rule**.</span></span>

5. <span data-ttu-id="fea5a-164">指定抑制规则的所有设置，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-164">Specify all the settings for your suppression rule, and then choose **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="fea5a-165">需要有关抑制规则的帮助？</span><span class="sxs-lookup"><span data-stu-id="fea5a-165">Need help with suppression rules?</span></span> <span data-ttu-id="fea5a-166">请参阅 [抑制警报并创建新的抑制规则](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-166">See [Suppress an alert and create a new suppression rule](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule).</span></span>

## <a name="part-2-review-remediation-actions"></a><span data-ttu-id="fea5a-167">第 2 部分：查看修正操作</span><span class="sxs-lookup"><span data-stu-id="fea5a-167">Part 2: Review remediation actions</span></span>

<span data-ttu-id="fea5a-168">[修正操作](manage-auto-investigation.md#remediation-actions)（例如，将文件发送到隔离或停止进程）对 (实体执行，) 被检测为威胁的文件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-168">[Remediation actions](manage-auto-investigation.md#remediation-actions), such as sending a file to quarantine or stopping a process, are taken on entities (such as files) that are detected as threats.</span></span> <span data-ttu-id="fea5a-169">多种类型的修正操作通过自动调查和 Microsoft Defender 防病毒自动执行：</span><span class="sxs-lookup"><span data-stu-id="fea5a-169">Several types of remediation actions occur automatically through automated investigation and Microsoft Defender Antivirus:</span></span>   
- <span data-ttu-id="fea5a-170">隔离文件</span><span class="sxs-lookup"><span data-stu-id="fea5a-170">Quarantine a file</span></span>
- <span data-ttu-id="fea5a-171">删除注册表项</span><span class="sxs-lookup"><span data-stu-id="fea5a-171">Remove a registry key</span></span>
- <span data-ttu-id="fea5a-172">终止进程</span><span class="sxs-lookup"><span data-stu-id="fea5a-172">Kill a process</span></span>
- <span data-ttu-id="fea5a-173">停止服务</span><span class="sxs-lookup"><span data-stu-id="fea5a-173">Stop a service</span></span>
- <span data-ttu-id="fea5a-174">禁用驱动程序</span><span class="sxs-lookup"><span data-stu-id="fea5a-174">Disable a driver</span></span>
- <span data-ttu-id="fea5a-175">删除计划任务</span><span class="sxs-lookup"><span data-stu-id="fea5a-175">Remove a scheduled task</span></span>

<span data-ttu-id="fea5a-176">其他操作（如启动防病毒扫描或收集调查包）手动发生，或者通过 [实时响应发生](live-response.md)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-176">Other actions, such as starting an antivirus scan or collecting an investigation package, occur manually or through [Live Response](live-response.md).</span></span> <span data-ttu-id="fea5a-177">无法撤消通过实时响应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="fea5a-177">Actions taken through Live Response cannot be undone.</span></span>

<span data-ttu-id="fea5a-178">查看警报后，下一步是 [查看修正操作](manage-auto-investigation.md)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-178">After you have reviewed your alerts, your next step is to [review remediation actions](manage-auto-investigation.md).</span></span> <span data-ttu-id="fea5a-179">如果由于误报而进行了任何操作，您可以撤消大多数种类的修正操作。</span><span class="sxs-lookup"><span data-stu-id="fea5a-179">If any actions were taken as a result of false positives, you can undo most kinds of remediation actions.</span></span> <span data-ttu-id="fea5a-180">具体来说，您可以：</span><span class="sxs-lookup"><span data-stu-id="fea5a-180">Specifically, you can:</span></span>

- [<span data-ttu-id="fea5a-181">从操作中心还原隔离文件</span><span class="sxs-lookup"><span data-stu-id="fea5a-181">Restore a quarantined file from the Action Center</span></span>](#restore-a-quarantined-file-from-the-action-center)
- [<span data-ttu-id="fea5a-182">一次撤消多个操作</span><span class="sxs-lookup"><span data-stu-id="fea5a-182">Undo multiple actions at one time</span></span>](#undo-multiple-actions-at-one-time)
- <span data-ttu-id="fea5a-183">[跨多个设备从隔离中删除文件](#remove-a-file-from-quarantine-across-multiple-devices)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-183">[Remove a file from quarantine across multiple devices](#remove-a-file-from-quarantine-across-multiple-devices).</span></span>  <span data-ttu-id="fea5a-184">和</span><span class="sxs-lookup"><span data-stu-id="fea5a-184">and</span></span> 
- [<span data-ttu-id="fea5a-185">从隔离区还原文件</span><span class="sxs-lookup"><span data-stu-id="fea5a-185">Restore file from quarantine</span></span>](#restore-file-from-quarantine)

<span data-ttu-id="fea5a-186">检查和撤消由于误报而采取的操作后，请继续查看 [或定义排除项](#part-3-review-or-define-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-186">When you're done reviewing and undoing actions that were taken as a result of false positives, proceed to [review or define exclusions](#part-3-review-or-define-exclusions).</span></span>

### <a name="review-completed-actions"></a><span data-ttu-id="fea5a-187">查看已完成的操作</span><span class="sxs-lookup"><span data-stu-id="fea5a-187">Review completed actions</span></span>

1. <span data-ttu-id="fea5a-188">转到操作中心 [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-188">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span> 

2. <span data-ttu-id="fea5a-189">选择 **"历史记录** "选项卡以查看已采取的操作列表。</span><span class="sxs-lookup"><span data-stu-id="fea5a-189">Select the **History** tab to view a list of actions that were taken.</span></span>  

3. <span data-ttu-id="fea5a-190">选择一个项目以查看有关已采取的修正操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fea5a-190">Select an item to view more details about the remediation action that was taken.</span></span>

### <a name="restore-a-quarantined-file-from-the-action-center"></a><span data-ttu-id="fea5a-191">从操作中心还原隔离文件</span><span class="sxs-lookup"><span data-stu-id="fea5a-191">Restore a quarantined file from the Action Center</span></span>

1. <span data-ttu-id="fea5a-192">转到操作中心 [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-192">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-193">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="fea5a-193">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="fea5a-194">在飞出窗格中， **选择撤消**。</span><span class="sxs-lookup"><span data-stu-id="fea5a-194">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="fea5a-195">如果使用此方法无法撤消该操作，则看不到"撤消 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="fea5a-195">If the action cannot be undone with this method, you will not see an **Undo** button.</span></span> <span data-ttu-id="fea5a-196"> (有关详细信息，请参阅 Undo [completed actions](manage-auto-investigation.md#undo-completed-actions).) </span><span class="sxs-lookup"><span data-stu-id="fea5a-196">(To learn more, see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions).)</span></span>

### <a name="undo-multiple-actions-at-one-time"></a><span data-ttu-id="fea5a-197">一次撤消多个操作</span><span class="sxs-lookup"><span data-stu-id="fea5a-197">Undo multiple actions at one time</span></span>

1. <span data-ttu-id="fea5a-198">转到操作中心 [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-198">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-199">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="fea5a-199">On the **History** tab, select the actions that you want to undo.</span></span>

3. <span data-ttu-id="fea5a-200">在屏幕右侧窗格中，选择"撤消 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-200">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="fea5a-201">跨多个设备从隔离中删除文件</span><span class="sxs-lookup"><span data-stu-id="fea5a-201">Remove a file from quarantine across multiple devices</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fea5a-202">![隔离](images/autoir-quarantine-file-1.png)</span><span class="sxs-lookup"><span data-stu-id="fea5a-202">![Quarantine file](images/autoir-quarantine-file-1.png)</span></span>

1. <span data-ttu-id="fea5a-203">转到操作中心 [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-203">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-204">在" **历史记录"** 选项卡上，选择操作类型为"隔离 **文件"的文件**。</span><span class="sxs-lookup"><span data-stu-id="fea5a-204">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="fea5a-205">在屏幕右侧窗格中，选择"应用到此文件的 **X** 更多实例"，然后选择"撤消 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-205">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

### <a name="restore-file-from-quarantine"></a><span data-ttu-id="fea5a-206">从隔离区还原文件</span><span class="sxs-lookup"><span data-stu-id="fea5a-206">Restore file from quarantine</span></span>

<span data-ttu-id="fea5a-207">如果在调查后确定文件是干净的，你可以回滚并从隔离区中删除文件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-207">You can roll back and remove a file from quarantine if you’ve determined that it’s clean after an investigation.</span></span> <span data-ttu-id="fea5a-208">在隔离文件的每台设备上运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="fea5a-208">Run the following command on each device where the file was quarantined.</span></span>

1. <span data-ttu-id="fea5a-209">在设备上打开提升的命令行提示符：</span><span class="sxs-lookup"><span data-stu-id="fea5a-209">Open an elevated command–line prompt on the device:</span></span>

   1. <span data-ttu-id="fea5a-210">转到“**开始**”并键入“_cmd_”。</span><span class="sxs-lookup"><span data-stu-id="fea5a-210">Go to **Start** and type _cmd_.</span></span>

   1. <span data-ttu-id="fea5a-211">右键单击命令 **提示符** ，然后选择 **以管理员角色运行**。</span><span class="sxs-lookup"><span data-stu-id="fea5a-211">Right–click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="fea5a-212">输入以下命令，然后按 **Enter：**</span><span class="sxs-lookup"><span data-stu-id="fea5a-212">Enter the following command, and press **Enter**:</span></span>

    ```console
    "ProgramFiles%\Windows Defender\MpCmdRun.exe" –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
    ```

    > [!NOTE]
    > <span data-ttu-id="fea5a-213">在某些情况下 **，ThreatName 可能** 显示为： `EUS:Win32/
CustomEnterpriseBlock!cl` 。</span><span class="sxs-lookup"><span data-stu-id="fea5a-213">In some scenarios, the **ThreatName** may appear as: `EUS:Win32/
CustomEnterpriseBlock!cl`.</span></span> <span data-ttu-id="fea5a-214">Defender for Endpoint 将还原最近 30 天内在此设备上隔离的所有自定义阻止文件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-214">Defender for Endpoint will restore all custom blocked files that were quarantined on this device in the last 30 days.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fea5a-215">作为潜在网络威胁隔离的文件可能无法恢复。</span><span class="sxs-lookup"><span data-stu-id="fea5a-215">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="fea5a-216">如果用户尝试在隔离后还原文件，则该文件可能无法访问。</span><span class="sxs-lookup"><span data-stu-id="fea5a-216">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="fea5a-217">这是因为系统不再具有访问该文件的网络凭据。</span><span class="sxs-lookup"><span data-stu-id="fea5a-217">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="fea5a-218">通常，这是临时登录到系统或共享文件夹且访问令牌过期的结果。</span><span class="sxs-lookup"><span data-stu-id="fea5a-218">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

3. <span data-ttu-id="fea5a-219">在屏幕右侧窗格中，选择"应用到此文件的 **X** 更多实例"，然后选择"撤消 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-219">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span> 


## <a name="part-3-review-or-define-exclusions"></a><span data-ttu-id="fea5a-220">第 3 部分：查看或定义排除项</span><span class="sxs-lookup"><span data-stu-id="fea5a-220">Part 3: Review or define exclusions</span></span>

<span data-ttu-id="fea5a-221">排除项是指定为修正操作例外的实体，如文件或 URL。</span><span class="sxs-lookup"><span data-stu-id="fea5a-221">An exclusion is an entity, such as a file or URL, that you specify as an exception to remediation actions.</span></span> <span data-ttu-id="fea5a-222">排除的实体仍可以检测到，但不对实体执行修正操作。</span><span class="sxs-lookup"><span data-stu-id="fea5a-222">The excluded entity can still get detected, but no remediation actions are taken on that entity.</span></span> <span data-ttu-id="fea5a-223">也就是说，Microsoft Defender for Endpoint 不会停止、将检测到的文件或进程发送到隔离、删除或以其他方式更改。</span><span class="sxs-lookup"><span data-stu-id="fea5a-223">That is, the detected file or process won’t be stopped, sent to quarantine, removed, or otherwise changed by Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="fea5a-224">若要定义 Microsoft Defender for Endpoint 中的排除项，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="fea5a-224">To define exclusions across Microsoft Defender for Endpoint, perform the following tasks:</span></span>
- [<span data-ttu-id="fea5a-225">定义 Microsoft Defender 防病毒的排除项</span><span class="sxs-lookup"><span data-stu-id="fea5a-225">Define exclusions for Microsoft Defender Antivirus</span></span>](#exclusions-for-microsoft-defender-antivirus)
- [<span data-ttu-id="fea5a-226">为 Microsoft Defender for Endpoint 创建"允许"指示器</span><span class="sxs-lookup"><span data-stu-id="fea5a-226">Create “allow” indicators for Microsoft Defender for Endpoint</span></span>](#indicators-for-microsoft-defender-for-endpoint)

> [!NOTE]
> <span data-ttu-id="fea5a-227">Microsoft Defender 防病毒排除项仅适用于防病毒保护，不适用于其他 Microsoft Defender for Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="fea5a-227">Microsoft Defender Antivirus exclusions apply only to antivirus protection, not across other Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="fea5a-228">若要广泛排除文件，请使用 Microsoft Defender 防病毒的排除项[](/microsoft-365/security/defender-endpoint/manage-indicators)和适用于终结点的 Microsoft Defender 自定义指示器。</span><span class="sxs-lookup"><span data-stu-id="fea5a-228">To exclude files broadly, use exclusions for Microsoft Defender Antivirus and [custom indicators](/microsoft-365/security/defender-endpoint/manage-indicators) for Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="fea5a-229">本节中的过程介绍如何定义排除项和指示器。</span><span class="sxs-lookup"><span data-stu-id="fea5a-229">The procedures in this section describe how to define exclusions and indicators.</span></span>

### <a name="exclusions-for-microsoft-defender-antivirus"></a><span data-ttu-id="fea5a-230">Microsoft Defender 防病毒的排除项</span><span class="sxs-lookup"><span data-stu-id="fea5a-230">Exclusions for Microsoft Defender Antivirus</span></span>

<span data-ttu-id="fea5a-231">通常，你无需为 Microsoft Defender 防病毒定义排除项。</span><span class="sxs-lookup"><span data-stu-id="fea5a-231">In general, you should not need to define exclusions for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="fea5a-232">请确保谨慎定义排除项，并且只包含导致误报的文件、文件夹、进程和进程打开的文件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-232">Make sure that you define exclusions sparingly, and that you only include the files, folders, processes, and process-opened files that are resulting in false positives.</span></span> <span data-ttu-id="fea5a-233">此外，请确保定期查看定义的排除项。</span><span class="sxs-lookup"><span data-stu-id="fea5a-233">In addition, make sure to review your defined exclusions regularly.</span></span> <span data-ttu-id="fea5a-234">我们建议使用[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)定义或编辑防病毒排除项;但是，可以使用其他方法，如组策略 ([](/azure/active-directory-domain-services/manage-group-policy)管理[Microsoft Defender for Endpoint](manage-atp-post-migration.md)) 。</span><span class="sxs-lookup"><span data-stu-id="fea5a-234">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to define or edit your antivirus exclusions; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

> [!TIP]
> <span data-ttu-id="fea5a-235">是否需要有关防病毒排除的帮助？</span><span class="sxs-lookup"><span data-stu-id="fea5a-235">Need help with antivirus exclusions?</span></span> <span data-ttu-id="fea5a-236">请参阅 [配置并验证 Microsoft Defender 防病毒扫描的排除项](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-236">See [Configure and validate exclusions for Microsoft Defender Antivirus scans](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-manage-antivirus-exclusions-for-existing-policies"></a><span data-ttu-id="fea5a-237">使用 Microsoft Endpoint Manager 管理现有策略 (的防病毒) </span><span class="sxs-lookup"><span data-stu-id="fea5a-237">Use Microsoft Endpoint Manager to manage antivirus exclusions (for existing policies)</span></span>

1. <span data-ttu-id="fea5a-238">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-238">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-239">选择 **"终结点**  >  **安全防病毒"，** 然后选择现有策略。</span><span class="sxs-lookup"><span data-stu-id="fea5a-239">Choose **Endpoint security** > **Antivirus**, and then select an existing policy.</span></span> <span data-ttu-id="fea5a-240"> (如果没有现有策略，或者想要创建新策略，请 [跳至下](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions) 一步) 。</span><span class="sxs-lookup"><span data-stu-id="fea5a-240">(If you don’t have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)).</span></span>

3. <span data-ttu-id="fea5a-241">选择 **"属性"，** 在"**配置设置"旁边**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-241">Choose **Properties**, and next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="fea5a-242">展开 **"Microsoft Defender 防病毒排除项"，** 然后指定排除项。</span><span class="sxs-lookup"><span data-stu-id="fea5a-242">Expand **Microsoft Defender Antivirus Exclusions** and then specify your exclusions.</span></span>

5. <span data-ttu-id="fea5a-243">选择 **"审阅 + 保存"，** 然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-243">Choose **Review + save**, and then choose **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions"></a><span data-ttu-id="fea5a-244">使用 Microsoft Endpoint Manager 创建排除项的新防病毒策略</span><span class="sxs-lookup"><span data-stu-id="fea5a-244">Use Microsoft Endpoint Manager to create a new antivirus policy with exclusions</span></span>

1. <span data-ttu-id="fea5a-245">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-245">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-246">选择 **"终结点安全**  >  **防病毒**  >  **+ 创建策略"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-246">Choose **Endpoint security** > **Antivirus** > **+ Create Policy**.</span></span> 

3. <span data-ttu-id="fea5a-247">选择平台 (如 **Windows 10 和更高版本\*\*\*\*、macOS** 或 **Windows 10** 和 Windows Server) 。</span><span class="sxs-lookup"><span data-stu-id="fea5a-247">Select a platform (such as **Windows 10 and later**, **macOS**, or **Windows 10 and Windows Server**).</span></span>

4. <span data-ttu-id="fea5a-248">对于 **"配置文件**"，选择 **"Microsoft Defender 防病毒排除** 项"，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-248">For **Profile**, select **Microsoft Defender Antivirus exclusions**, and then choose **Create**.</span></span>

5. <span data-ttu-id="fea5a-249">指定配置文件的名称和说明，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-249">Specify a name and description for the profile, and then choose **Next**.</span></span>

6. <span data-ttu-id="fea5a-250">在"**配置设置"** 选项卡上，指定防病毒排除项，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-250">On the **Configuration settings** tab, specify your antivirus exclusions, and then choose **Next**.</span></span>

7. <span data-ttu-id="fea5a-251">在" **范围标记** "选项卡上，如果您在组织中使用范围标记，请为要创建的策略指定范围标记。</span><span class="sxs-lookup"><span data-stu-id="fea5a-251">On the **Scope tags** tab, if you are using scope tags in your organization, specify scope tags for the policy you are creating.</span></span> <span data-ttu-id="fea5a-252"> (范围 [标记](/mem/intune/fundamentals/scope-tags).) </span><span class="sxs-lookup"><span data-stu-id="fea5a-252">(See [Scope tags](/mem/intune/fundamentals/scope-tags).)</span></span>

8. <span data-ttu-id="fea5a-253">在"**分配**"选项卡上，指定应应用策略的用户和组，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-253">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="fea5a-254"> (如果需要分配帮助，请参阅在 [Microsoft Intune](/mem/intune/configuration/device-profile-assign)中分配用户和设备) </span><span class="sxs-lookup"><span data-stu-id="fea5a-254">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

9. <span data-ttu-id="fea5a-255">在"**查看 + 创建"** 选项卡上，查看设置，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-255">On the **Review + create** tab, review the settings, and then choose **Create**.</span></span>

### <a name="indicators-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="fea5a-256">适用于终结点的 Microsoft Defender 指示器</span><span class="sxs-lookup"><span data-stu-id="fea5a-256">Indicators for Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="fea5a-257">[尤其是](/microsoft-365/security/defender-endpoint/manage-indicators) (泄露指示器或 IoCs) 使安全运营团队能够定义实体的检测、防护和排除。</span><span class="sxs-lookup"><span data-stu-id="fea5a-257">[Indicators](/microsoft-365/security/defender-endpoint/manage-indicators) (specifically, indicators of compromise, or IoCs) enable your security operations team to define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="fea5a-258">例如，可以在 Microsoft Defender for Endpoint 的扫描和修正操作中指定要省略的某些文件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-258">For example, you can specify certain files to be omitted from scans and remediation actions in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="fea5a-259">或者，指示器可用于对某些文件、IP 地址或 URL 生成警报。</span><span class="sxs-lookup"><span data-stu-id="fea5a-259">Or, indicators can be used to generate alerts for certain files, IP addresses, or URLs.</span></span>

<span data-ttu-id="fea5a-260">若要将实体指定为 Microsoft Defender for Endpoint 的排除项，请为这些实体创建"允许"指示器。</span><span class="sxs-lookup"><span data-stu-id="fea5a-260">To specify entities as exclusions for Microsoft Defender for Endpoint, create "allow" indicators for those entities.</span></span> <span data-ttu-id="fea5a-261">Microsoft Defender for Endpoint 中的此类"允许"[](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)指示器适用于下一代[](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)保护、终结点检测和响应以及自动调查[&修正](/microsoft-365/security/defender-endpoint/automated-investigations)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-261">Such "allow" indicators in Microsoft Defender for Endpoint apply to [next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), [endpoint detection and response](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response), and [automated investigation & remediation](/microsoft-365/security/defender-endpoint/automated-investigations).</span></span>

<span data-ttu-id="fea5a-262">"允许"指示器可用于：</span><span class="sxs-lookup"><span data-stu-id="fea5a-262">"Allow" indicators can be created for:</span></span>

- [<span data-ttu-id="fea5a-263">Files</span><span class="sxs-lookup"><span data-stu-id="fea5a-263">Files</span></span>](#indicators-for-files)
- [<span data-ttu-id="fea5a-264">IP 地址、URL 和域</span><span class="sxs-lookup"><span data-stu-id="fea5a-264">IP addresses, URLs, and domains</span></span>](#indicators-for-ip-addresses-urls-or-domains)
- [<span data-ttu-id="fea5a-265">应用程序证书</span><span class="sxs-lookup"><span data-stu-id="fea5a-265">Application certificates</span></span>](#indicators-for-application-certificates)

![指示器类型图](images/false-positives-indicators.png)

#### <a name="indicators-for-files"></a><span data-ttu-id="fea5a-267">文件指示器</span><span class="sxs-lookup"><span data-stu-id="fea5a-267">Indicators for files</span></span>

<span data-ttu-id="fea5a-268">为 [文件（](/microsoft-365/security/defender-endpoint/indicator-file)如可执行文件）创建"允许"指示器时，它有助于防止组织使用的文件被阻止。</span><span class="sxs-lookup"><span data-stu-id="fea5a-268">When you [create an "allow" indicator for a file, such as an executable](/microsoft-365/security/defender-endpoint/indicator-file), it helps prevent files that your organization is using from being blocked.</span></span> <span data-ttu-id="fea5a-269">文件可以包括可移植的可执行 (PE) 文件，如 和 `.exe` `.dll` 文件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-269">Files can include portable executable (PE) files, such as `.exe` and `.dll` files.</span></span> 

<span data-ttu-id="fea5a-270">创建文件指示器之前，请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="fea5a-270">Before you create indicators for files, make sure the following requirements are met:</span></span>
- <span data-ttu-id="fea5a-271">Microsoft Defender 防病毒配置了启用基于云的保护 (请参阅管理基于云的 [保护](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)) </span><span class="sxs-lookup"><span data-stu-id="fea5a-271">Microsoft Defender Antivirus is configured with cloud-based protection enabled (see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus))</span></span>
- <span data-ttu-id="fea5a-272">反恶意软件客户端版本为 4.18.1901.x 或更高版本</span><span class="sxs-lookup"><span data-stu-id="fea5a-272">Antimalware client version is 4.18.1901.x or later</span></span> 
- <span data-ttu-id="fea5a-273">设备运行的是 Windows 10 版本 1703 或更高版本;Windows Server 2016;或 Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="fea5a-273">Devices are running Windows 10, version 1703 or later; Windows Server 2016; or Windows Server 2019</span></span> 
- <span data-ttu-id="fea5a-274">" [阻止或允许"功能已打开](/microsoft-365/security/defender-endpoint/advanced-features)</span><span class="sxs-lookup"><span data-stu-id="fea5a-274">The [Block or allow feature is turned on](/microsoft-365/security/defender-endpoint/advanced-features)</span></span> 

#### <a name="indicators-for-ip-addresses-urls-or-domains"></a><span data-ttu-id="fea5a-275">IP 地址、URL 或域的指示器</span><span class="sxs-lookup"><span data-stu-id="fea5a-275">Indicators for IP addresses, URLs, or domains</span></span>

<span data-ttu-id="fea5a-276">为 [IP 地址、URL](/microsoft-365/security/defender-endpoint/indicator-ip-domain)或域创建"允许"指示器时，它有助于防止组织使用的站点或 IP 地址被阻止。</span><span class="sxs-lookup"><span data-stu-id="fea5a-276">When you [create an "allow" indicator for an IP address, URL, or domain](/microsoft-365/security/defender-endpoint/indicator-ip-domain), it helps prevent the sites or IP addresses your organization uses from being blocked.</span></span>

<span data-ttu-id="fea5a-277">为 IP 地址、URL 或域创建指示器之前，请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="fea5a-277">Before you create indicators for IP addresses, URLs, or domains, make sure the following requirements are met:</span></span>
- <span data-ttu-id="fea5a-278">Defender for Endpoint 中的网络保护在阻止模式下启用 (请参阅启用 [网络保护](/microsoft-365/security/defender-endpoint/enable-network-protection)) </span><span class="sxs-lookup"><span data-stu-id="fea5a-278">Network protection in Defender for Endpoint is enabled in block mode (see [Enable network protection](/microsoft-365/security/defender-endpoint/enable-network-protection))</span></span>
- <span data-ttu-id="fea5a-279">反恶意软件客户端版本为 4.18.1906.x 或更高版本</span><span class="sxs-lookup"><span data-stu-id="fea5a-279">Antimalware client version is 4.18.1906.x or later</span></span> 
- <span data-ttu-id="fea5a-280">设备运行的是 Windows 10 版本 1709 或更高版本</span><span class="sxs-lookup"><span data-stu-id="fea5a-280">Devices are running Windows 10, version 1709, or later</span></span> 

<span data-ttu-id="fea5a-281">自定义网络指示器在 Microsoft Defender 安全中心内打开， ([高级功能](/microsoft-365/security/defender-endpoint/advanced-features)) </span><span class="sxs-lookup"><span data-stu-id="fea5a-281">Custom network indicators are turned on in the Microsoft Defender Security Center (see [Advanced features](/microsoft-365/security/defender-endpoint/advanced-features))</span></span>   

#### <a name="indicators-for-application-certificates"></a><span data-ttu-id="fea5a-282">应用程序证书指示器</span><span class="sxs-lookup"><span data-stu-id="fea5a-282">Indicators for application certificates</span></span> 

<span data-ttu-id="fea5a-283">为 [应用程序证书创建"允许](/microsoft-365/security/defender-endpoint/indicator-certificates)"指示器时，它有助于防止组织使用的应用程序（如内部开发的应用程序）被阻止。</span><span class="sxs-lookup"><span data-stu-id="fea5a-283">When you [create an "allow" indicator for an application certificate](/microsoft-365/security/defender-endpoint/indicator-certificates), it helps prevent applications, such as internally developed applications, that your organization uses from being blocked.</span></span> <span data-ttu-id="fea5a-284">`.CER` 或 `.PEM` 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="fea5a-284">`.CER` or `.PEM` file extensions are supported.</span></span>   

<span data-ttu-id="fea5a-285">创建应用程序证书指示器之前，请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="fea5a-285">Before you create indicators for application certificates, make sure the following requirements are met:</span></span>
- <span data-ttu-id="fea5a-286">Microsoft Defender 防病毒配置了启用基于云的保护 (请参阅管理基于云的 [保护](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)) </span><span class="sxs-lookup"><span data-stu-id="fea5a-286">Microsoft Defender Antivirus is configured with cloud-based protection enabled (see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus))</span></span>
- <span data-ttu-id="fea5a-287">反恶意软件客户端版本为 4.18.1901.x 或更高版本</span><span class="sxs-lookup"><span data-stu-id="fea5a-287">Antimalware client version is 4.18.1901.x or later</span></span> 
- <span data-ttu-id="fea5a-288">设备运行的是 Windows 10 版本 1703 或更高版本;Windows Server 2016;或 Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="fea5a-288">Devices are running Windows 10, version 1703 or later; Windows Server 2016; or Windows Server 2019</span></span> 
- <span data-ttu-id="fea5a-289">病毒和威胁防护定义是最新的</span><span class="sxs-lookup"><span data-stu-id="fea5a-289">Virus and threat protection definitions are up to date</span></span>  

> [!TIP]
> <span data-ttu-id="fea5a-290">创建指示器时，可以一个一个地定义它们，也可以一次导入多个项。</span><span class="sxs-lookup"><span data-stu-id="fea5a-290">When you create indicators, you can define them one by one, or import multiple items at once.</span></span> <span data-ttu-id="fea5a-291">请记住，单个租户的指示器限制为 15，000 个。</span><span class="sxs-lookup"><span data-stu-id="fea5a-291">Keep in mind there's a limit of 15,000 indicators for a single tenant.</span></span> <span data-ttu-id="fea5a-292">而且，您可能需要首先收集某些详细信息，例如文件哈希信息。</span><span class="sxs-lookup"><span data-stu-id="fea5a-292">And, you might need to gather certain details first, such as file hash information.</span></span> <span data-ttu-id="fea5a-293">请确保先查看先决条件，然后再 [创建指示器](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-293">Make sure to review the prerequisites before you [create indicators](manage-indicators.md).</span></span> 

## <a name="part-4-submit-a-file-for-analysis"></a><span data-ttu-id="fea5a-294">第 4 部分：提交文件进行分析</span><span class="sxs-lookup"><span data-stu-id="fea5a-294">Part 4: Submit a file for analysis</span></span>

<span data-ttu-id="fea5a-295">你可以将实体（如文件和无文件检测）提交给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="fea5a-295">You can submit entities, such as files and fileless detections, to Microsoft for analysis.</span></span> <span data-ttu-id="fea5a-296">Microsoft 安全研究人员分析所有提交，其结果有助于通知 Microsoft Defender 终结点威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="fea5a-296">Microsoft security researchers analyze all submissions, and their results help inform Microsoft Defender for Endpoint threat protection capabilities.</span></span> <span data-ttu-id="fea5a-297">当你在提交网站登录时，你可以跟踪你的提交。</span><span class="sxs-lookup"><span data-stu-id="fea5a-297">When you sign in at the submission site, you can track your submissions.</span></span>

### <a name="submit-a-file-for-analysis"></a><span data-ttu-id="fea5a-298">提交文件进行分析</span><span class="sxs-lookup"><span data-stu-id="fea5a-298">Submit a file for analysis</span></span>

<span data-ttu-id="fea5a-299">如果文件被错误地检测为恶意或丢失，请按照以下步骤提交文件进行分析。</span><span class="sxs-lookup"><span data-stu-id="fea5a-299">If you have a file that was either wrongly detected as malicious or was missed, follow these steps to submit the file for analysis.</span></span>

1. <span data-ttu-id="fea5a-300">查看以下指南： [提交文件进行分析](/windows/security/threat-protection/intelligence/submission-guide)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-300">Review the guidelines here: [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="fea5a-301">访问 Microsoft 安全智能提交 [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) () ，然后提交你的 (提交) 。</span><span class="sxs-lookup"><span data-stu-id="fea5a-301">Visit the Microsoft Security Intelligence submission site ([https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission)), and submit your file(s).</span></span>

### <a name="submit-a-fileless-detection-for-analysis"></a><span data-ttu-id="fea5a-302">提交无文件检测进行分析</span><span class="sxs-lookup"><span data-stu-id="fea5a-302">Submit a fileless detection for analysis</span></span>

<span data-ttu-id="fea5a-303">如果根据行为检测到恶意软件，并且您没有文件，您可以提交 `Mpsupport.cab` 文件进行分析。</span><span class="sxs-lookup"><span data-stu-id="fea5a-303">If something was detected as malware based on behavior, and you don’t have a file, you can submit your `Mpsupport.cab` file for analysis.</span></span> <span data-ttu-id="fea5a-304">可以使用 Windows 10 上的 Microsoft 恶意软件防护工具Command-Line实用程序 (MPCmdRun.exe) *.cab* 文件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-304">You can get the *.cab* file by using the Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) tool on Windows 10.</span></span>

1.  <span data-ttu-id="fea5a-305">转到 ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` ，然后以 `MpCmdRun.exe` 管理员角色运行。</span><span class="sxs-lookup"><span data-stu-id="fea5a-305">Go to ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`, and then run `MpCmdRun.exe` as an administrator.</span></span>

2.  <span data-ttu-id="fea5a-306">键入 `mpcmdrun.exe -GetFiles` ，然后按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-306">Type `mpcmdrun.exe -GetFiles`, and then press **Enter**.</span></span>
   <span data-ttu-id="fea5a-307">生成了一个包含各种诊断日志的 .cab 文件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-307">A .cab file is generated that contains various diagnostic logs.</span></span> <span data-ttu-id="fea5a-308">文件的位置在命令提示符的输出中指定。</span><span class="sxs-lookup"><span data-stu-id="fea5a-308">The location of the file is specified in the output of the command prompt.</span></span> <span data-ttu-id="fea5a-309">默认情况下，位置为 `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` 。</span><span class="sxs-lookup"><span data-stu-id="fea5a-309">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

3.  <span data-ttu-id="fea5a-310">查看以下指南： [提交文件进行分析](/windows/security/threat-protection/intelligence/submission-guide)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-310">Review the guidelines here: [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

4.  <span data-ttu-id="fea5a-311">访问 Microsoft 安全智能提交站点 [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) () ，然后提交 .cab 文件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-311">Visit the Microsoft Security Intelligence submission site ([https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission)), and submit your .cab files.</span></span>

### <a name="what-happens-after-a-file-is-submitted"></a><span data-ttu-id="fea5a-312">提交文件后会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="fea5a-312">What happens after a file is submitted?</span></span>

<span data-ttu-id="fea5a-313">我们的系统会立即扫描你的提交，以在分析员开始处理你的案例之前提供最新决定。</span><span class="sxs-lookup"><span data-stu-id="fea5a-313">Your submission is immediately scanned by our systems to give you the latest determination even before an analyst starts handling your case.</span></span> <span data-ttu-id="fea5a-314">分析员可能已经提交和处理了文件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-314">It’s possible that a file might have already been submitted and processed by an analyst.</span></span> <span data-ttu-id="fea5a-315">在这种情况下，迅速作出决定。</span><span class="sxs-lookup"><span data-stu-id="fea5a-315">In those cases, a determination is made quickly.</span></span>

<span data-ttu-id="fea5a-316">对于尚未处理的提交，将按如下方式对提交进行优先分析：</span><span class="sxs-lookup"><span data-stu-id="fea5a-316">For submissions that were not already processed, they are prioritized for analysis as follows:</span></span>

- <span data-ttu-id="fea5a-317">对于可能会影响大量计算机的流行文件，其优先级更高。</span><span class="sxs-lookup"><span data-stu-id="fea5a-317">Prevalent files with the potential to impact large numbers of computers are given a higher priority.</span></span>
- <span data-ttu-id="fea5a-318">经过身份验证的客户（尤其是具有有效软件保障 ([或使用) 的企业 ](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx)客户）的优先级更高。</span><span class="sxs-lookup"><span data-stu-id="fea5a-318">Authenticated customers, especially enterprise customers with valid [Software Assurance IDs (SAIDs)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx), are given a higher priority.</span></span>
- <span data-ttu-id="fea5a-319">由 SAID 持有者标记为高优先级的提交将被立即关注。</span><span class="sxs-lookup"><span data-stu-id="fea5a-319">Submissions flagged as high priority by SAID holders are given immediate attention.</span></span>

<span data-ttu-id="fea5a-320">若要检查有关你的提交的更新，请在 Microsoft 安全智能提交 [网站登录](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-320">To check for updates regarding your submission, sign in at the [Microsoft Security Intelligence submission site](https://www.microsoft.com/wdsi/filesubmission).</span></span> 

> [!TIP]
> <span data-ttu-id="fea5a-321">若要了解更多信息，请参阅 [提交文件进行分析](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-321">To learn more, see [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions).</span></span>

## <a name="part-5-review-and-adjust-your-threat-protection-settings"></a><span data-ttu-id="fea5a-322">第 5 部分：查看和调整威胁防护设置</span><span class="sxs-lookup"><span data-stu-id="fea5a-322">Part 5: Review and adjust your threat protection settings</span></span>

<span data-ttu-id="fea5a-323">Microsoft Defender for Endpoint 提供各种选项，包括针对各种特性和功能微调设置的功能。</span><span class="sxs-lookup"><span data-stu-id="fea5a-323">Microsoft Defender for Endpoint offers a wide variety of options, including the ability to fine-tune settings for various features and capabilities.</span></span> <span data-ttu-id="fea5a-324">如果收到大量误报，请务必查看组织的威胁防护设置。</span><span class="sxs-lookup"><span data-stu-id="fea5a-324">If you’re getting numerous false positives, make sure to review your organization’s threat protection settings.</span></span> <span data-ttu-id="fea5a-325">您可能需要进行一些调整以：</span><span class="sxs-lookup"><span data-stu-id="fea5a-325">You might need to make some adjustments to:</span></span>

- [<span data-ttu-id="fea5a-326">云保护</span><span class="sxs-lookup"><span data-stu-id="fea5a-326">Cloud-delivered protection</span></span>](#cloud-delivered-protection)
- [<span data-ttu-id="fea5a-327">针对可能不需要的应用程序的修正</span><span class="sxs-lookup"><span data-stu-id="fea5a-327">Remediation for potentially unwanted applications</span></span>](#remediation-for-potentially-unwanted-applications)
- [<span data-ttu-id="fea5a-328">自动调查和修复</span><span class="sxs-lookup"><span data-stu-id="fea5a-328">Automated investigation and remediation</span></span>](#automated-investigation-and-remediation)

### <a name="cloud-delivered-protection"></a><span data-ttu-id="fea5a-329">云保护</span><span class="sxs-lookup"><span data-stu-id="fea5a-329">Cloud-delivered protection</span></span>

<span data-ttu-id="fea5a-330">检查云提供的 Microsoft Defender 防病毒保护级别。</span><span class="sxs-lookup"><span data-stu-id="fea5a-330">Check your cloud-delivered protection level for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="fea5a-331">默认情况下，云提供的保护设置为"未配置"，这与大多数组织的正常保护级别相对应。 </span><span class="sxs-lookup"><span data-stu-id="fea5a-331">By default, cloud-delivered protection is set to **Not configured**, which corresponds to a normal level of protection for most organizations.</span></span> <span data-ttu-id="fea5a-332">如果云提供的保护设置为 **高**、高 **+** 或 **零容** 限，则可能会遇到更多误报。</span><span class="sxs-lookup"><span data-stu-id="fea5a-332">If your cloud-delivered protection is set to **High**, **High +**, or **Zero tolerance**, you might experience a higher number of false positives.</span></span>

> [!TIP]
> <span data-ttu-id="fea5a-333">若要详细了解如何配置云保护，请参阅指定 [云保护级别](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-333">To learn more about configuring your cloud-delivered protection, see [Specify the cloud-delivered protection level](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="fea5a-334">我们建议使用[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)编辑或设置云提供的保护设置;但是，可以使用其他方法，如组策略 ([](/azure/active-directory-domain-services/manage-group-policy)管理[Microsoft Defender for Endpoint](manage-atp-post-migration.md)) 。</span><span class="sxs-lookup"><span data-stu-id="fea5a-334">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to edit or set your cloud-delivered protection settings; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-review-and-edit-cloud-delivered-protection-settings-for-existing-policies"></a><span data-ttu-id="fea5a-335">使用 Microsoft Endpoint Manager 查看和编辑云提供的保护设置 (现有策略) </span><span class="sxs-lookup"><span data-stu-id="fea5a-335">Use Microsoft Endpoint Manager to review and edit cloud-delivered protection settings (for existing policies)</span></span>

1. <span data-ttu-id="fea5a-336">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-336">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-337">选择 **"终结点**  >  **安全防病毒"，** 然后选择现有策略。</span><span class="sxs-lookup"><span data-stu-id="fea5a-337">Choose **Endpoint security** > **Antivirus** and then select an existing policy.</span></span> <span data-ttu-id="fea5a-338"> (如果没有现有策略，或者想要创建新策略，请 [跳至下](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy) 一步) 。</span><span class="sxs-lookup"><span data-stu-id="fea5a-338">(If you don’t have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)).</span></span>

3. <span data-ttu-id="fea5a-339">在 **"管理"** 下，选择"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-339">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="fea5a-340">然后，在"配置 **设置"旁边，选择**"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-340">Then, next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="fea5a-341">展开 **云保护**，然后查看云提供的保护 **级别行中的当前** 设置。</span><span class="sxs-lookup"><span data-stu-id="fea5a-341">Expand **Cloud protection**, and review your current setting in the **Cloud-delivered protection level** row.</span></span> <span data-ttu-id="fea5a-342">我们建议将云提供的保护设置为"未配置 **"，** 这将提供强大的保护，同时降低误报的可能性。</span><span class="sxs-lookup"><span data-stu-id="fea5a-342">We recommend setting cloud-delivered protection to **Not configured**, which provides strong protection while reducing the chances of getting false positives.</span></span>

5. <span data-ttu-id="fea5a-343">选择 **"审阅 + 保存"，** 然后选择"**保存"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-343">Choose **Review + save**, and then **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy"></a><span data-ttu-id="fea5a-344">使用 Microsoft Endpoint Manager 为新策略设置 (云保护设置) </span><span class="sxs-lookup"><span data-stu-id="fea5a-344">Use Microsoft Endpoint Manager to set cloud-delivered protection settings (for a new policy)</span></span>

1. <span data-ttu-id="fea5a-345">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-345">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-346">选择 **"终结点安全**  >  **防病毒**  >  **+ 创建策略"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-346">Choose **Endpoint security** > **Antivirus** > **+ Create policy**.</span></span>

3. <span data-ttu-id="fea5a-347">对于 **"** 平台"，选择一个选项，然后选择"配置文件"，选择"防病毒"或 **"Microsoft Defender** 防病毒 (具体选项取决于你为 **平台** 选择) 然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-347">For **Platform**, select an option, and then for **Profile**, select **Antivirus** or **Microsoft Defender Antivirus** (the specific option depends on what you selected for **Platform**.) Then choose **Create**.</span></span>

4. <span data-ttu-id="fea5a-348">在 **"基本信息"** 选项卡上，指定策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="fea5a-348">On the **Basics** tab, specify a name and description for the policy.</span></span> <span data-ttu-id="fea5a-349">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fea5a-349">Then choose **Next**.</span></span>

5. <span data-ttu-id="fea5a-350">在" **配置设置"** 选项卡上，展开 **"云保护**"，并指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="fea5a-350">On the **Configuration settings** tab, expand **Cloud protection**, and specify the following settings:</span></span>
   - <span data-ttu-id="fea5a-351">将 **"启用云保护"设置为\*\*\*\*"是"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-351">Set **Turn on cloud-delivered protection** to **Yes**.</span></span>
   - <span data-ttu-id="fea5a-352">将 **云提供的保护级别设置为\*\*\*\*"未配置"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-352">Set **Cloud-delivered protection level** to **Not configured**.</span></span> <span data-ttu-id="fea5a-353"> (此级别在默认情况下提供强大的保护级别，同时减少误报的可能性。) </span><span class="sxs-lookup"><span data-stu-id="fea5a-353">(This level provides a strong level of protection by default while reducing the chances of getting false positives.)</span></span>

6. <span data-ttu-id="fea5a-354">在" **范围标记** "选项卡上，如果您在组织中使用范围标记，请为策略指定范围标记。</span><span class="sxs-lookup"><span data-stu-id="fea5a-354">On the **Scope tags** tab, if you are using scope tags in your organization, specify scope tags for the policy.</span></span> <span data-ttu-id="fea5a-355"> (范围 [标记](/mem/intune/fundamentals/scope-tags).) </span><span class="sxs-lookup"><span data-stu-id="fea5a-355">(See [Scope tags](/mem/intune/fundamentals/scope-tags).)</span></span>

7. <span data-ttu-id="fea5a-356">在"**分配**"选项卡上，指定应应用策略的用户和组，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-356">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="fea5a-357"> (如果需要分配帮助，请参阅在 [Microsoft Intune](/mem/intune/configuration/device-profile-assign)中分配用户和设备) </span><span class="sxs-lookup"><span data-stu-id="fea5a-357">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

8. <span data-ttu-id="fea5a-358">在"**查看 + 创建"** 选项卡上，查看设置，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-358">On the **Review + create** tab, review the settings, and then choose **Create**.</span></span>  

### <a name="remediation-for-potentially-unwanted-applications"></a><span data-ttu-id="fea5a-359">针对可能不需要的应用程序的修正</span><span class="sxs-lookup"><span data-stu-id="fea5a-359">Remediation for potentially unwanted applications</span></span>

<span data-ttu-id="fea5a-360">PUA (可能不需要) 是一类软件，可能会导致设备运行缓慢、显示意外广告或安装可能意外或不需要的其他软件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-360">Potentially unwanted applications (PUA) are a category of software that can cause devices to run slowly, display unexpected ads, or install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="fea5a-361">PUA 的示例包括广告软件、捆绑软件和与安全产品行为不同的软件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-361">Examples of PUA include advertising software, bundling software, and evasion software that behaves differently with security products.</span></span> <span data-ttu-id="fea5a-362">尽管 PUA 不被视为恶意软件，但某些类型的软件是基于其行为和信誉的 PUA。</span><span class="sxs-lookup"><span data-stu-id="fea5a-362">Although PUA is not considered malware, some kinds of software are PUA based on their behavior and reputation.</span></span>

> [!TIP]
> <span data-ttu-id="fea5a-363">若要了解有关 PUA 的更多信息，请参阅 [检测并阻止可能不需要的应用程序](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-363">To learn more about PUA, see [Detect and block potentially unwanted applications](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus).</span></span>
 
<span data-ttu-id="fea5a-364">根据你的组织使用的应用，你可能会因 PUA 保护设置而收到误报。</span><span class="sxs-lookup"><span data-stu-id="fea5a-364">Depending on the apps your organization is using, you might be getting false positives as a result of your PUA protection settings.</span></span> <span data-ttu-id="fea5a-365">如有必要，请考虑在审核模式下运行一段时间的 PUA 保护，或将 PUA 保护应用于组织中设备的子集。</span><span class="sxs-lookup"><span data-stu-id="fea5a-365">If necessary, consider running PUA protection in audit mode for a while, or apply PUA protection to a subset of devices in your organization.</span></span> <span data-ttu-id="fea5a-366">PUA 保护可以针对 Microsoft Edge 浏览器和 Microsoft Defender 防病毒进行配置。</span><span class="sxs-lookup"><span data-stu-id="fea5a-366">PUA protection can be configured for the Microsoft Edge browser and for Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="fea5a-367">我们建议使用[Microsoft Endpoint Manager](/mem/endpoint-manager-overview)编辑或设置 PUA 保护设置;但是，可以使用其他方法，如组策略 ([](/azure/active-directory-domain-services/manage-group-policy)管理[Microsoft Defender for Endpoint](manage-atp-post-migration.md)) 。</span><span class="sxs-lookup"><span data-stu-id="fea5a-367">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to edit or set PUA protection settings; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-edit-pua-protection-for-existing-configuration-profiles"></a><span data-ttu-id="fea5a-368">使用 Microsoft Endpoint Manager 编辑现有配置文件 (PUA 保护) </span><span class="sxs-lookup"><span data-stu-id="fea5a-368">Use Microsoft Endpoint Manager to edit PUA protection (for existing configuration profiles)</span></span>

1. <span data-ttu-id="fea5a-369">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-369">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-370">选择 **"设备**  >  **配置文件"，** 然后选择现有策略。</span><span class="sxs-lookup"><span data-stu-id="fea5a-370">Choose **Devices** > **Configuration profiles**, and then select an existing policy.</span></span> <span data-ttu-id="fea5a-371"> (如果没有现有策略，或者要创建新策略，请 [跳到下](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile)一过程 .) </span><span class="sxs-lookup"><span data-stu-id="fea5a-371">(If you don’t have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile).)</span></span>

3. <span data-ttu-id="fea5a-372">在 **"管理"** 下，**选择"属性**"，然后在"配置 **设置"旁边**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-372">Under **Manage**, choose **Properties**, and then, next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="fea5a-373">在配置 **设置选项卡** 上，向下滚动并展开 **Microsoft Defender 防病毒**。</span><span class="sxs-lookup"><span data-stu-id="fea5a-373">On the **Configuration settings** tab, scroll down and expand **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="fea5a-374">将 **"检测可能不需要的应用程序"设置为\*\*\*\*"审核"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-374">Set **Detect potentially unwanted applications** to **Audit**.</span></span> <span data-ttu-id="fea5a-375"> (你可以将其关闭，但通过使用审核模式，你将能够看到检测。) </span><span class="sxs-lookup"><span data-stu-id="fea5a-375">(You can turn it off, but by using audit mode, you will be able to see detections.)</span></span>

6. <span data-ttu-id="fea5a-376">选择 **"审阅 + 保存"，** 然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-376">Choose **Review + save**, and then choose **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile"></a><span data-ttu-id="fea5a-377">使用 Microsoft Endpoint Manager 为新的配置文件 (PUA 保护) </span><span class="sxs-lookup"><span data-stu-id="fea5a-377">Use Microsoft Endpoint Manager to set PUA protection (for a new configuration profile)</span></span>

1. <span data-ttu-id="fea5a-378">转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-378">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-379">选择 **"设备**  >  **配置文件**  >  **+ 创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-379">Choose **Devices** > **Configuration profiles** > **+ Create profile**.</span></span>

3. <span data-ttu-id="fea5a-380">对于 **"平台"，** 选择 **"Windows 10 及** 更高版本"，对于 **"配置文件**"，选择 **"设备限制"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-380">For the **Platform**, choose **Windows 10 and later**, and for **Profile**, select **Device restrictions**.</span></span>

4. <span data-ttu-id="fea5a-381">在 **"基本信息"** 选项卡上，指定策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="fea5a-381">On the **Basics** tab, specify a name and description for your policy.</span></span> <span data-ttu-id="fea5a-382">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fea5a-382">Then choose **Next**.</span></span>

5. <span data-ttu-id="fea5a-383">在配置 **设置选项卡** 上，向下滚动并展开 **Microsoft Defender 防病毒**。</span><span class="sxs-lookup"><span data-stu-id="fea5a-383">On the **Configuration settings** tab, scroll down and expand **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="fea5a-384">将 **"检测可能不需要的应用程序"设置为\*\*\*\*"审核"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-384">Set **Detect potentially unwanted applications** to **Audit**, and then choose **Next**.</span></span> <span data-ttu-id="fea5a-385"> (你可以关闭 PUA 保护，但通过使用审核模式，你将能够看到检测。) </span><span class="sxs-lookup"><span data-stu-id="fea5a-385">(You can turn off PUA protection, but by using audit mode, you will be able to see detections.)</span></span>

7. <span data-ttu-id="fea5a-386">在"**分配**"选项卡上，指定应应用策略的用户和组，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-386">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="fea5a-387"> (如果需要分配帮助，请参阅在 [Microsoft Intune](/mem/intune/configuration/device-profile-assign)中分配用户和设备) </span><span class="sxs-lookup"><span data-stu-id="fea5a-387">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

8. <span data-ttu-id="fea5a-388">在 **"适用性规则** "选项卡上，指定要包含或排除在策略中的操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="fea5a-388">On the **Applicability Rules** tab, specify the OS editions or versions to include or exclude from the policy.</span></span> <span data-ttu-id="fea5a-389">例如，你可以将策略设置为应用于 Windows 10 的某些版本的所有设备。</span><span class="sxs-lookup"><span data-stu-id="fea5a-389">For example, you can set the policy to be applied to all devices certain editions of Windows 10.</span></span> <span data-ttu-id="fea5a-390">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fea5a-390">Then choose **Next**.</span></span>

9. <span data-ttu-id="fea5a-391">在"**查看 + 创建**"选项卡上，查看设置，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-391">On the **Review + create** tab, review your settings, and, and then choose **Create**.</span></span>

### <a name="automated-investigation-and-remediation"></a><span data-ttu-id="fea5a-392">自动调查和修复</span><span class="sxs-lookup"><span data-stu-id="fea5a-392">Automated investigation and remediation</span></span>

<span data-ttu-id="fea5a-393">[AIR (](automated-investigations.md) 自动调查和) 功能旨在检查警报并立即采取措施来解决违规问题。</span><span class="sxs-lookup"><span data-stu-id="fea5a-393">[Automated investigation and remediation](automated-investigations.md) (AIR) capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="fea5a-394">触发警报并运行自动调查时，将针对调查的每个证据生成裁定。</span><span class="sxs-lookup"><span data-stu-id="fea5a-394">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="fea5a-395">裁定结果可以是 *"恶意"、"\*\*可疑"* 或 *"未找到威胁"。*</span><span class="sxs-lookup"><span data-stu-id="fea5a-395">Verdicts can be *Malicious*, *Suspicious*, or *No threats found*.</span></span> 

<span data-ttu-id="fea5a-396">根据为 [组织](/microsoft-365/security/defender-endpoint/automation-levels)设置的自动化级别和其他安全设置，将针对视为恶意或 *可疑的项目采取\*\*修正操作*。</span><span class="sxs-lookup"><span data-stu-id="fea5a-396">Depending on the [level of automation](/microsoft-365/security/defender-endpoint/automation-levels) set for your organization and other security settings, remediation actions are taken on artifacts that are considered to be *Malicious* or *Suspicious*.</span></span> <span data-ttu-id="fea5a-397">在某些情况下，将自动执行修正操作;其他情况下，修正操作是手动采取的，或仅在安全运营团队批准后执行。</span><span class="sxs-lookup"><span data-stu-id="fea5a-397">In some cases, remediation actions occur automatically; in other cases, remediation actions are taken manually or only upon approval by your security operations team.</span></span> 

- <span data-ttu-id="fea5a-398">[详细了解自动化级别](/microsoft-365/security/defender-endpoint/automation-levels);然后</span><span class="sxs-lookup"><span data-stu-id="fea5a-398">[Learn more about automation levels](/microsoft-365/security/defender-endpoint/automation-levels); and then</span></span> 
- <span data-ttu-id="fea5a-399">[在 Defender for Endpoint 中配置 AIR 功能](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation)。</span><span class="sxs-lookup"><span data-stu-id="fea5a-399">[Configure AIR capabilities in Defender for Endpoint](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fea5a-400">我们建议使用 *完全自动化* 进行自动调查和修正。</span><span class="sxs-lookup"><span data-stu-id="fea5a-400">We recommend using *Full automation* for automated investigation and remediation.</span></span> <span data-ttu-id="fea5a-401">不要因为误报而关闭这些功能。</span><span class="sxs-lookup"><span data-stu-id="fea5a-401">Don't turn these capabilities off because of a false positive.</span></span> <span data-ttu-id="fea5a-402">相反， [使用"允许"指示器定义](#indicators-for-microsoft-defender-for-endpoint)例外，并保留自动调查和修正集以自动采取适当操作。</span><span class="sxs-lookup"><span data-stu-id="fea5a-402">Instead, use ["allow" indicators to define exceptions](#indicators-for-microsoft-defender-for-endpoint), and keep automated investigation and remediation set to take appropriate actions automatically.</span></span> <span data-ttu-id="fea5a-403">遵循 [本指南](automation-levels.md#levels-of-automation) 有助于减少安全操作团队必须处理的警报数。</span><span class="sxs-lookup"><span data-stu-id="fea5a-403">Following [this guidance](automation-levels.md#levels-of-automation) helps reduce the number of alerts your security operations team must handle.</span></span> 

## <a name="still-need-help"></a><span data-ttu-id="fea5a-404">仍然需要帮助？</span><span class="sxs-lookup"><span data-stu-id="fea5a-404">Still need help?</span></span>

<span data-ttu-id="fea5a-405">如果已执行本文中所有步骤，但仍需要帮助，请联系技术支持人员。</span><span class="sxs-lookup"><span data-stu-id="fea5a-405">If you have worked through all the steps in this article and still need help, contact technical support.</span></span>

1. <span data-ttu-id="fea5a-406">转到 Microsoft Defender 安全中心 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="fea5a-406">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="fea5a-407">在右上角，选择问号 **" (？) "，** 然后选择 **"Microsoft 支持"。**</span><span class="sxs-lookup"><span data-stu-id="fea5a-407">In the upper right corner, select the question mark (**?**), and then select **Microsoft support**.</span></span>

3. <span data-ttu-id="fea5a-408">在" **支持助手** "窗口中，描述您的问题，然后发送邮件。</span><span class="sxs-lookup"><span data-stu-id="fea5a-408">In the **Support Assistant** window, describe your issue, and then send your message.</span></span> <span data-ttu-id="fea5a-409">可以从中打开服务请求。</span><span class="sxs-lookup"><span data-stu-id="fea5a-409">From there, you can open a service request.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fea5a-410">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fea5a-410">See also</span></span>

[<span data-ttu-id="fea5a-411">管理 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fea5a-411">Manage Microsoft Defender for Endpoint</span></span>](manage-atp-post-migration.md)

[<span data-ttu-id="fea5a-412">Microsoft Defender 安全中心概述</span><span class="sxs-lookup"><span data-stu-id="fea5a-412">Overview of Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use) 
