---
title: 在 Microsoft 365 Defender 的 AIR 中处理误报或漏报
description: MICROSOFT 365 Defender 中的 AIR 是否遗漏或错误地检测到了某些内容？ 了解如何将误报或漏报提交给 Microsoft 进行分析。
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 误报， 漏报
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930350"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="af165-105">处理自动调查和响应功能中的误报/负数</span><span class="sxs-lookup"><span data-stu-id="af165-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="af165-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="af165-106">**Applies to:**</span></span>
- <span data-ttu-id="af165-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af165-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="af165-108">Microsoft 365 Defender [中的](mtp-autoir.md) 自动调查和响应功能是否遗漏或错误地检测到了某些内容？</span><span class="sxs-lookup"><span data-stu-id="af165-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="af165-109">你可以采取一些步骤来修复此问题。</span><span class="sxs-lookup"><span data-stu-id="af165-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="af165-110">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="af165-110">You can:</span></span>

- <span data-ttu-id="af165-111">[向 Microsoft 报告误报/负数](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="af165-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="af165-112">[根据需要调整警报 (](#adjust-an-alert-to-prevent-false-positives-from-recurring) 调整) ;and</span><span class="sxs-lookup"><span data-stu-id="af165-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="af165-113">[撤消在设备上采取的修正操作](#undo-a-remediation-action-that-was-taken-on-a-device)。</span><span class="sxs-lookup"><span data-stu-id="af165-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="af165-114">使用本文作为指南。</span><span class="sxs-lookup"><span data-stu-id="af165-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="af165-115">向 Microsoft 报告误报/负数进行分析</span><span class="sxs-lookup"><span data-stu-id="af165-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="af165-116">未接或检测错误的项目</span><span class="sxs-lookup"><span data-stu-id="af165-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="af165-117">服务</span><span class="sxs-lookup"><span data-stu-id="af165-117">Service</span></span>  |<span data-ttu-id="af165-118">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="af165-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="af165-119">- 电子邮件</span><span class="sxs-lookup"><span data-stu-id="af165-119">- Email message</span></span> <br/><span data-ttu-id="af165-120">- 电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="af165-120">- Email attachment</span></span> <br/><span data-ttu-id="af165-121">- 电子邮件中的 URL</span><span class="sxs-lookup"><span data-stu-id="af165-121">- URL in an email message</span></span><br/><span data-ttu-id="af165-122">- Office 文件的 URL</span><span class="sxs-lookup"><span data-stu-id="af165-122">- URL in an Office file</span></span>      |[<span data-ttu-id="af165-123">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="af165-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="af165-124">将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft 进行扫描</span><span class="sxs-lookup"><span data-stu-id="af165-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="af165-125">设备上文件或应用</span><span class="sxs-lookup"><span data-stu-id="af165-125">File or app on a device</span></span>    |[<span data-ttu-id="af165-126">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af165-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="af165-127">将文件提交给 Microsoft 进行恶意软件分析</span><span class="sxs-lookup"><span data-stu-id="af165-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="af165-128">调整警报以防止误报重复发生</span><span class="sxs-lookup"><span data-stu-id="af165-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="af165-129">方案</span><span class="sxs-lookup"><span data-stu-id="af165-129">Scenario</span></span> |<span data-ttu-id="af165-130">服务</span><span class="sxs-lookup"><span data-stu-id="af165-130">Service</span></span> |<span data-ttu-id="af165-131">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="af165-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="af165-132">- 合法使用触发警报</span><span class="sxs-lookup"><span data-stu-id="af165-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="af165-133">- 警报不准确</span><span class="sxs-lookup"><span data-stu-id="af165-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="af165-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="af165-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="af165-135">或</span><span class="sxs-lookup"><span data-stu-id="af165-135">or</span></span> <br/>[<span data-ttu-id="af165-136">Azure 高级威胁检测</span><span class="sxs-lookup"><span data-stu-id="af165-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="af165-137">在云应用安全门户中管理警报</span><span class="sxs-lookup"><span data-stu-id="af165-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="af165-138">文件、IP 地址、URL 或域在设备上被视为恶意软件，即使安全</span><span class="sxs-lookup"><span data-stu-id="af165-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="af165-139">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="af165-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="af165-140">使用"允许"操作创建自定义指示器</span><span class="sxs-lookup"><span data-stu-id="af165-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="af165-141">撤消在设备上采取的修正操作</span><span class="sxs-lookup"><span data-stu-id="af165-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="af165-142">如果在 Windows 10 设备 (等设备上采取修正操作) 并且该项目实际上不是威胁，你的安全运营团队可以在操作中心撤消修正[操作。](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="af165-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af165-143">在尝试执行 [以下任务之前](mtp-action-center.md#required-permissions-for-action-center-tasks) ，请确保你拥有必要的权限。</span><span class="sxs-lookup"><span data-stu-id="af165-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="af165-144">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="af165-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="af165-145">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="af165-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="af165-146">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="af165-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="af165-147">这将打开一个飞出。</span><span class="sxs-lookup"><span data-stu-id="af165-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="af165-148">使用筛选器缩小结果列表。</span><span class="sxs-lookup"><span data-stu-id="af165-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="af165-149">在选定项目的飞出中，选择" **打开调查"页**。</span><span class="sxs-lookup"><span data-stu-id="af165-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="af165-150">在调查详细信息视图中，选择" **操作"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="af165-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="af165-151">选择状态为"已完成"**的项目**，在"决策"列中查找链接（**如"已批准**"）。 </span><span class="sxs-lookup"><span data-stu-id="af165-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="af165-152">这将打开一个包含有关该操作的更多详细信息的飞出。</span><span class="sxs-lookup"><span data-stu-id="af165-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="af165-153">若要撤消该操作，请选择"**删除修正"。**</span><span class="sxs-lookup"><span data-stu-id="af165-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="af165-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af165-154">See also</span></span>

- [<span data-ttu-id="af165-155">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="af165-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="af165-156">在 Microsoft 365 Defender 中通过高级搜寻主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="af165-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
