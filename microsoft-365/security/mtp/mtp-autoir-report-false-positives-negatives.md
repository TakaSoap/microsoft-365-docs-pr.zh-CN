---
title: 在 Microsoft 365 Defender 中处理空中误报或漏报
description: Microsoft 365 Defender 中的无线检测到缺少或错误地检测到了什么东西？ 了解如何向 Microsoft 提交误报或漏报以进行分析。
keywords: 自动化、调查、警报、触发器、操作、修正、误报、假负
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 92ad4a96665a5355bce7e3546f8c52779f770927
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843728"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="a5224-105">处理自动调查和响应功能中的误报/否定</span><span class="sxs-lookup"><span data-stu-id="a5224-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a5224-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a5224-106">**Applies to:**</span></span>
- <span data-ttu-id="a5224-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5224-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="a5224-108">是否在 Microsoft 365 Defender 中执行了 [自动化调查和响应功能，](mtp-autoir.md) 或错误地检测到了某些内容？</span><span class="sxs-lookup"><span data-stu-id="a5224-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="a5224-109">您可以采取一些步骤来修复它。</span><span class="sxs-lookup"><span data-stu-id="a5224-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="a5224-110">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a5224-110">You can:</span></span>

- <span data-ttu-id="a5224-111">[向 Microsoft 报告误报/负数，](#report-a-false-positivenegative-to-microsoft-for-analysis)或者</span><span class="sxs-lookup"><span data-stu-id="a5224-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="a5224-112">根据需要[调整通知](#adjust-an-alert-to-prevent-false-positives-from-recurring) () ;并</span><span class="sxs-lookup"><span data-stu-id="a5224-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="a5224-113">[撤消对设备所执行的修正操作](#undo-a-remediation-action-that-was-taken-on-a-device)。</span><span class="sxs-lookup"><span data-stu-id="a5224-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="a5224-114">将本文用作指南。</span><span class="sxs-lookup"><span data-stu-id="a5224-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="a5224-115">将误报/负数报告给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="a5224-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="a5224-116">缺少或错误地检测到项目</span><span class="sxs-lookup"><span data-stu-id="a5224-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="a5224-117">服务</span><span class="sxs-lookup"><span data-stu-id="a5224-117">Service</span></span>  |<span data-ttu-id="a5224-118">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="a5224-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a5224-119">-电子邮件</span><span class="sxs-lookup"><span data-stu-id="a5224-119">- Email message</span></span> <br/><span data-ttu-id="a5224-120">-电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="a5224-120">- Email attachment</span></span> <br/><span data-ttu-id="a5224-121">-电子邮件中的 URL</span><span class="sxs-lookup"><span data-stu-id="a5224-121">- URL in an email message</span></span><br/><span data-ttu-id="a5224-122">-Office 文件中的 URL</span><span class="sxs-lookup"><span data-stu-id="a5224-122">- URL in an Office file</span></span>      |[<span data-ttu-id="a5224-123">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a5224-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="a5224-124">将可疑的垃圾邮件、网络钓鱼、Url 和文件提交给 Microsoft 进行扫描</span><span class="sxs-lookup"><span data-stu-id="a5224-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="a5224-125">设备上的文件或应用</span><span class="sxs-lookup"><span data-stu-id="a5224-125">File or app on a device</span></span>    |[<span data-ttu-id="a5224-126">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a5224-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="a5224-127">将文件提交给 Microsoft 进行恶意软件分析</span><span class="sxs-lookup"><span data-stu-id="a5224-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="a5224-128">调整警报以防止定期误报</span><span class="sxs-lookup"><span data-stu-id="a5224-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="a5224-129">应用场景</span><span class="sxs-lookup"><span data-stu-id="a5224-129">Scenario</span></span> |<span data-ttu-id="a5224-130">服务</span><span class="sxs-lookup"><span data-stu-id="a5224-130">Service</span></span> |<span data-ttu-id="a5224-131">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="a5224-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="a5224-132">-警报由合法使用触发</span><span class="sxs-lookup"><span data-stu-id="a5224-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="a5224-133">-警报不准确</span><span class="sxs-lookup"><span data-stu-id="a5224-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="a5224-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a5224-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="a5224-135">或</span><span class="sxs-lookup"><span data-stu-id="a5224-135">or</span></span> <br/>[<span data-ttu-id="a5224-136">Azure 高级威胁检测</span><span class="sxs-lookup"><span data-stu-id="a5224-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="a5224-137">在云应用安全门户中管理通知</span><span class="sxs-lookup"><span data-stu-id="a5224-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="a5224-138">即使是安全的，文件、IP 地址、URL 或域也会在设备上被视为恶意软件</span><span class="sxs-lookup"><span data-stu-id="a5224-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="a5224-139">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a5224-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="a5224-140">创建具有 "允许" 操作的自定义指示器</span><span class="sxs-lookup"><span data-stu-id="a5224-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="a5224-141">撤消对设备执行的修正操作</span><span class="sxs-lookup"><span data-stu-id="a5224-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="a5224-142">如果对设备执行了修正操作 (例如 Windows 10 设备) 并且该项目实际上不是威胁，则安全操作团队可以撤消 [操作中心](mtp-action-center.md)中的修正操作。</span><span class="sxs-lookup"><span data-stu-id="a5224-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5224-143">在尝试执行以下任务之前，请确保您具有 [所需的权限](mtp-action-center.md#required-permissions-for-action-center-tasks) 。</span><span class="sxs-lookup"><span data-stu-id="a5224-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="a5224-144">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="a5224-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="a5224-145">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="a5224-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="a5224-146">在 " **历史记录** " 选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="a5224-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="a5224-147">这将打开一个浮出控件。</span><span class="sxs-lookup"><span data-stu-id="a5224-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="a5224-148">使用筛选器缩小结果列表。</span><span class="sxs-lookup"><span data-stu-id="a5224-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="a5224-149">在选定项的浮出控件中，选择 " **打开调查页面** "。</span><span class="sxs-lookup"><span data-stu-id="a5224-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="a5224-150">在调查详细信息视图中，选择 " **操作** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="a5224-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="a5224-151">选择 "已 **完成** " 状态的项目，并在 " **决策** " 列中查找链接（如 " **已批准** "）。</span><span class="sxs-lookup"><span data-stu-id="a5224-151">Select an item that has status of **Completed** , and look for a link, such as **Approved** , in the **Decisions** column.</span></span> <span data-ttu-id="a5224-152">这将打开一个浮出控件，其中包含有关操作的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="a5224-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="a5224-153">若要撤消操作，请选择 " **删除修正** "。</span><span class="sxs-lookup"><span data-stu-id="a5224-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5224-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5224-154">See also</span></span>

- [<span data-ttu-id="a5224-155">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="a5224-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="a5224-156">在 Microsoft 365 Defender 中主动查找具有高级搜寻的威胁</span><span class="sxs-lookup"><span data-stu-id="a5224-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
