---
title: 如何在 Microsoft 威胁防护中报告空气中的误报或虚假否定
description: 无线在 Microsoft 威胁防护中是否已错过或错误地检测到了什么？ 了解如何向 Microsoft 提交误报或漏报以进行分析。
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
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 44c90c6c9394b1f9fee34b8eb068bb7c232c4d78
ms.sourcegitcommit: a6686a68b068adec29b72f998ac9bc95992981df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2020
ms.locfileid: "41627968"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="0e6a4-105">如何报告自动调查和响应功能中的误报/否定</span><span class="sxs-lookup"><span data-stu-id="0e6a4-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="0e6a4-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0e6a4-106">**Applies to:**</span></span>
- <span data-ttu-id="0e6a4-107">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="0e6a4-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0e6a4-108">在 Microsoft 威胁防护中是否进行了[自动化调查和响应功能](mtp-autoir.md)丢失或错误地检测到了什么？</span><span class="sxs-lookup"><span data-stu-id="0e6a4-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="0e6a4-109">您可以采取一些步骤来修复它。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="0e6a4-110">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0e6a4-110">You can:</span></span>
- <span data-ttu-id="0e6a4-111">[向 Microsoft 报告误报/负数，](#report-a-false-positivenegative-to-microsoft-for-analysis)或者</span><span class="sxs-lookup"><span data-stu-id="0e6a4-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="0e6a4-112">[调整通知](#adjust-an-alert-to-prevent-false-positives-from-recurring)（如果需要）;并</span><span class="sxs-lookup"><span data-stu-id="0e6a4-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="0e6a4-113">[撤消对设备所执行的修正操作](#undo-a-remediation-action-that-was-taken-on-a-device)。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="0e6a4-114">将本文用作指南。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="0e6a4-115">将误报/负数报告给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="0e6a4-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="0e6a4-116">缺少或错误地检测到项目</span><span class="sxs-lookup"><span data-stu-id="0e6a4-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="0e6a4-117">服务</span><span class="sxs-lookup"><span data-stu-id="0e6a4-117">Service</span></span>  |<span data-ttu-id="0e6a4-118">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="0e6a4-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0e6a4-119">-电子邮件</span><span class="sxs-lookup"><span data-stu-id="0e6a4-119">- Email message</span></span> <br/><span data-ttu-id="0e6a4-120">-电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="0e6a4-120">- Email attachment</span></span> <br/><span data-ttu-id="0e6a4-121">-电子邮件中的 URL</span><span class="sxs-lookup"><span data-stu-id="0e6a4-121">- URL in an email message</span></span><br/><span data-ttu-id="0e6a4-122">-Office 文件中的 URL</span><span class="sxs-lookup"><span data-stu-id="0e6a4-122">- URL in an Office file</span></span>      |[<span data-ttu-id="0e6a4-123">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="0e6a4-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="0e6a4-124">将可疑的垃圾邮件、网络钓鱼、Url 和文件提交到 Microsoft for Office 365 扫描</span><span class="sxs-lookup"><span data-stu-id="0e6a4-124">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="0e6a4-125">设备上的文件或应用</span><span class="sxs-lookup"><span data-stu-id="0e6a4-125">File or app on a device</span></span>    |[<span data-ttu-id="0e6a4-126">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="0e6a4-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="0e6a4-127">将文件提交给 Microsoft 进行恶意软件分析</span><span class="sxs-lookup"><span data-stu-id="0e6a4-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="0e6a4-128">调整警报以防止定期误报</span><span class="sxs-lookup"><span data-stu-id="0e6a4-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="0e6a4-129">方案</span><span class="sxs-lookup"><span data-stu-id="0e6a4-129">Scenario</span></span> |<span data-ttu-id="0e6a4-130">服务</span><span class="sxs-lookup"><span data-stu-id="0e6a4-130">Service</span></span> |<span data-ttu-id="0e6a4-131">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="0e6a4-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="0e6a4-132">-警报由合法使用触发</span><span class="sxs-lookup"><span data-stu-id="0e6a4-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="0e6a4-133">-警报不准确</span><span class="sxs-lookup"><span data-stu-id="0e6a4-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="0e6a4-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0e6a4-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="0e6a4-135">或</span><span class="sxs-lookup"><span data-stu-id="0e6a4-135">or</span></span> <br/>[<span data-ttu-id="0e6a4-136">Azure 高级威胁检测</span><span class="sxs-lookup"><span data-stu-id="0e6a4-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="0e6a4-137">在云应用安全门户中管理通知</span><span class="sxs-lookup"><span data-stu-id="0e6a4-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="0e6a4-138">即使是安全的，文件、IP 地址、URL 或域也会在设备上被视为恶意软件</span><span class="sxs-lookup"><span data-stu-id="0e6a4-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="0e6a4-139">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="0e6a4-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="0e6a4-140">创建具有 "允许" 操作的自定义指示器</span><span class="sxs-lookup"><span data-stu-id="0e6a4-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="0e6a4-141">撤消对设备执行的修正操作</span><span class="sxs-lookup"><span data-stu-id="0e6a4-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="0e6a4-142">如果对设备（如 Windows 10 设备）和实际清除的项执行了修正操作，则安全操作团队可以撤消[操作中心](mtp-action-center.md)中的修正操作。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item that is actually clean, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e6a4-143">在尝试执行以下任务之前，请确保您具有[所需的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="0e6a4-144">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="0e6a4-145">在“导航”窗格中，选择“操作中心”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="0e6a4-146">在 "**历史记录**" 选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="0e6a4-147">这将打开一个浮出控件。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="0e6a4-148">使用筛选器缩小结果列表。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="0e6a4-149">在选定项的浮出控件中，选择 "**打开调查页面**"。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="0e6a4-150">在调查详细信息视图中，选择 "**操作**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="0e6a4-151">选择 "已**完成**" 状态的项目，并在 "**决策**" 列中查找链接（如 "**已批准**"）。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="0e6a4-152">这将打开一个浮出控件，其中包含有关操作的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="0e6a4-153">若要撤消操作，请选择 "**删除修正**"。</span><span class="sxs-lookup"><span data-stu-id="0e6a4-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="0e6a4-154">相关文章</span><span class="sxs-lookup"><span data-stu-id="0e6a4-154">Related articles</span></span>

- [<span data-ttu-id="0e6a4-155">批准或拒绝与自动调查和响应相关的操作</span><span class="sxs-lookup"><span data-stu-id="0e6a4-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="0e6a4-156">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="0e6a4-156">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="0e6a4-157">通过 Microsoft 威胁防护中的高级搜寻主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="0e6a4-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
