---
title: 设备监控&报告 - 安全中心
description: 介绍如何使设备保持安全、最新并发现组织中的潜在威胁
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视器， 报告， 设备
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930494"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="91961-104">Microsoft 365 安全中心中的设备监视和报告</span><span class="sxs-lookup"><span data-stu-id="91961-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="91961-105">确保设备安全、最新，并发现 Microsoft 365 安全中心中的潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="91961-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="91961-106">查看设备警报</span><span class="sxs-lookup"><span data-stu-id="91961-106">View device alerts</span></span>

<span data-ttu-id="91961-107">从适用于终结点的 Microsoft Defender (获取有关你的设备上泄露活动和其他威胁) 。</span><span class="sxs-lookup"><span data-stu-id="91961-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender for Endpoint (available with an E5 license).</span></span> <span data-ttu-id="91961-108">Microsoft 365 安全中心使用你的首选工作流有效地在高级别监视这些警报。</span><span class="sxs-lookup"><span data-stu-id="91961-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="91961-109">监视高影响警报</span><span class="sxs-lookup"><span data-stu-id="91961-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="91961-110">每个 Microsoft Defender for Endpoint 警报都有一个对应的严重性 (高、中、低或信息) 。</span><span class="sxs-lookup"><span data-stu-id="91961-110">Each Microsoft Defender for Endpoint alert has a corresponding severity (high, medium, low, or informational).</span></span> <span data-ttu-id="91961-111">如果无人值守，则表明对网络的潜在影响。</span><span class="sxs-lookup"><span data-stu-id="91961-111">It indicates potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="91961-112">使用 **"设备警报严重性** "卡专门关注更严重且可能需要立即响应的警报。</span><span class="sxs-lookup"><span data-stu-id="91961-112">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="91961-113">通过此卡，可以查看 Microsoft Defender 安全中心门户上更多信息。</span><span class="sxs-lookup"><span data-stu-id="91961-113">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![设备警报严重性卡片](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="91961-115">了解警报源</span><span class="sxs-lookup"><span data-stu-id="91961-115">Understand sources of alerts</span></span>

<span data-ttu-id="91961-116">Microsoft Defender for Endpoint 利用来自各种安全传感器和智能源的数据来生成警报。</span><span class="sxs-lookup"><span data-stu-id="91961-116">Microsoft Defender for Endpoint leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="91961-117">例如，它可以使用来自 Microsoft Defender 防病毒和第三方反恶意软件的检测信息。</span><span class="sxs-lookup"><span data-stu-id="91961-117">For example, it can use detection information from Microsoft Defender Antivirus and third-party antimalware.</span></span> <span data-ttu-id="91961-118">它还可以使用通过 Web 服务 API 提供的你自己的自定义威胁情报。</span><span class="sxs-lookup"><span data-stu-id="91961-118">It can also use your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="91961-119">设备 **警报检测** 源卡按源显示警报的分布。</span><span class="sxs-lookup"><span data-stu-id="91961-119">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="91961-120">跟踪与特定源（尤其是自定义源）相关的活动。</span><span class="sxs-lookup"><span data-stu-id="91961-120">Track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="91961-121">您还可以使用该卡重点关注来自未配置为自动阻止恶意活动或组件的传感器的警报。</span><span class="sxs-lookup"><span data-stu-id="91961-121">You can also use the card to focus on alerts coming from sensors that aren't configured to automatically block malicious activity or components.</span></span>

![设备警报检测源卡](../../media/device-alert-detection-sources.png)

<span data-ttu-id="91961-123">通过此卡，可以查看 Microsoft Defender 安全中心门户上的信息。</span><span class="sxs-lookup"><span data-stu-id="91961-123">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="91961-124">了解触发警报的威胁类型</span><span class="sxs-lookup"><span data-stu-id="91961-124">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="91961-125">Microsoft Defender for Endpoint 将每个警报分类为表示攻击链中的特定阶段或威胁组件类型的类别。</span><span class="sxs-lookup"><span data-stu-id="91961-125">Microsoft Defender for Endpoint sorts each alert into a category representing a certain stage in the attack chain or type of threat component.</span></span> <span data-ttu-id="91961-126">例如，检测到的威胁活动可能归类为"横向移动"，以指示已尝试访问网络的其他设备。</span><span class="sxs-lookup"><span data-stu-id="91961-126">For example, a detected threat activity might be categorized as "lateral movement" to indicate there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="91961-127">活动可能在攻击者获得初始页脚之后发生。</span><span class="sxs-lookup"><span data-stu-id="91961-127">The activity has likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="91961-128">检测到威胁组件时，可能会将威胁组件大致分类为恶意软件或特定威胁类型。</span><span class="sxs-lookup"><span data-stu-id="91961-128">When detected, a threat component might be classified broadly as malware or specifically as a specific threat type.</span></span> <span data-ttu-id="91961-129">具体包括勒索软件、凭据窃取或其他类型的恶意或不需要的软件。</span><span class="sxs-lookup"><span data-stu-id="91961-129">Specifics include ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="91961-130">设备 **威胁类别** 卡片显示警报分布到这些类别。</span><span class="sxs-lookup"><span data-stu-id="91961-130">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="91961-131">使用此信息可标识通常比社交工程尝试影响更高的威胁活动，如凭据盗窃尝试。</span><span class="sxs-lookup"><span data-stu-id="91961-131">Use this information to identify threat activity, such as credential theft attempts, that usually have higher impact than social engineering attempts.</span></span> <span data-ttu-id="91961-132">还可以监视勒索软件等潜在破坏性威胁。</span><span class="sxs-lookup"><span data-stu-id="91961-132">You can also to monitor for potentially destructive threats like ransomware.</span></span>

![设备威胁类别卡片](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="91961-134">监视活动警报</span><span class="sxs-lookup"><span data-stu-id="91961-134">Monitor active alerts</span></span>

<span data-ttu-id="91961-135">设备 **警报状态** 卡指示尚未解决并可能需要注意的警报数。</span><span class="sxs-lookup"><span data-stu-id="91961-135">The **Device alert status** card indicates the number of alerts that haven't been resolved and may require attention.</span></span> <span data-ttu-id="91961-136">通过此卡，可以查看 Microsoft Defender 安全中心门户上更多信息。</span><span class="sxs-lookup"><span data-stu-id="91961-136">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![设备警报状态卡](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="91961-138">监视已解决警报的分类</span><span class="sxs-lookup"><span data-stu-id="91961-138">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="91961-139">解决 Microsoft Defender for Endpoint 警报时，安全人员可以指定警报是否已验证为：</span><span class="sxs-lookup"><span data-stu-id="91961-139">When resolving a Microsoft Defender for Endpoint alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="91961-140">标识实际泄露活动或威胁组件的真实警报</span><span class="sxs-lookup"><span data-stu-id="91961-140">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="91961-141">错误检测到正常活动的假警报</span><span class="sxs-lookup"><span data-stu-id="91961-141">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="91961-142">设备 **警报分类** 卡显示已解决的警报是否已分类为 true 或 false 警报。</span><span class="sxs-lookup"><span data-stu-id="91961-142">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="91961-143">通过此卡，可以查看 Microsoft Defender 安全中心门户上的信息。</span><span class="sxs-lookup"><span data-stu-id="91961-143">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="91961-144">注意：在某些情况下，分类信息对某些警报不可用。</span><span class="sxs-lookup"><span data-stu-id="91961-144">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![设备警报分类卡](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="91961-146">监视已解决警报的确定</span><span class="sxs-lookup"><span data-stu-id="91961-146">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="91961-147">除了在解决过程中对警报进行分类外，安全人员还可以确定警报是真还是假。</span><span class="sxs-lookup"><span data-stu-id="91961-147">Along with classifying whether an alert is true or false during resolution, your security staff can provide a determination.</span></span> <span data-ttu-id="91961-148">确定指示在验证警报时找到的正常或恶意活动的类型。</span><span class="sxs-lookup"><span data-stu-id="91961-148">A determination indicates the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="91961-149">设备 **警报确定** 卡片显示针对每个警报提供的决定。</span><span class="sxs-lookup"><span data-stu-id="91961-149">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="91961-150">**APT**： 高级永久性威胁，指示检测到的活动或威胁组件是复杂漏洞的一部分，旨在在受影响的网络中取得位置</span><span class="sxs-lookup"><span data-stu-id="91961-150">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="91961-151">**恶意软件**：恶意文件或代码</span><span class="sxs-lookup"><span data-stu-id="91961-151">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="91961-152">**安全人员**：安全人员执行的正常活动</span><span class="sxs-lookup"><span data-stu-id="91961-152">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="91961-153">**安全测试**：旨在模拟实际威胁并预期触发安全传感器并生成警报的活动或组件</span><span class="sxs-lookup"><span data-stu-id="91961-153">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="91961-154">**不需要的软件**：不被视为恶意但违反策略或可接受使用标准的应用和其他软件</span><span class="sxs-lookup"><span data-stu-id="91961-154">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="91961-155">**其他**：任何不属于提供类型下的其他确定</span><span class="sxs-lookup"><span data-stu-id="91961-155">**Others**: any other determination that doesn't fall under the provided types</span></span>

<span data-ttu-id="91961-156">在此卡中，可以在 Microsoft Defender 安全中心查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="91961-156">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![设备警报确定卡](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="91961-158">了解哪些设备存在风险</span><span class="sxs-lookup"><span data-stu-id="91961-158">Understand which devices are at risk</span></span>

<span data-ttu-id="91961-159">**设备** 保护显示设备的风险级别。</span><span class="sxs-lookup"><span data-stu-id="91961-159">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="91961-160">风险级别基于诸如设备上警报的类型和严重性等因素。</span><span class="sxs-lookup"><span data-stu-id="91961-160">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![设备保护卡](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="91961-162">监视并报告 Intune 托管设备的状态</span><span class="sxs-lookup"><span data-stu-id="91961-162">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="91961-163">以下报告包含 Intune 中注册的设备的数据。</span><span class="sxs-lookup"><span data-stu-id="91961-163">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="91961-164">不包括来自注销设备的数据。</span><span class="sxs-lookup"><span data-stu-id="91961-164">Data from unenrolled devices isn't included.</span></span> <span data-ttu-id="91961-165">只有全局管理员可以查看这些卡片。</span><span class="sxs-lookup"><span data-stu-id="91961-165">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="91961-166">Intune 注册的设备数据包括：</span><span class="sxs-lookup"><span data-stu-id="91961-166">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="91961-167">设备合规性</span><span class="sxs-lookup"><span data-stu-id="91961-167">Device compliance</span></span>
* <span data-ttu-id="91961-168">具有活动恶意软件的设备</span><span class="sxs-lookup"><span data-stu-id="91961-168">Devices with active malware</span></span>
* <span data-ttu-id="91961-169">设备上恶意软件的类型</span><span class="sxs-lookup"><span data-stu-id="91961-169">Types of malware on devices</span></span>
* <span data-ttu-id="91961-170">设备上恶意软件</span><span class="sxs-lookup"><span data-stu-id="91961-170">Malware on devices</span></span>
* <span data-ttu-id="91961-171">具有恶意软件检测的设备</span><span class="sxs-lookup"><span data-stu-id="91961-171">Devices with malware detections</span></span>
* <span data-ttu-id="91961-172">具有恶意软件检测的用户</span><span class="sxs-lookup"><span data-stu-id="91961-172">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="91961-173">监视设备合规性</span><span class="sxs-lookup"><span data-stu-id="91961-173">Monitor device compliance</span></span>

<span data-ttu-id="91961-174">**设备** 合规性显示 Intune 中注册的符合配置策略的设备数。</span><span class="sxs-lookup"><span data-stu-id="91961-174">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![设备合规性卡](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="91961-176">发现具有恶意软件检测的设备</span><span class="sxs-lookup"><span data-stu-id="91961-176">Discover devices with malware detections</span></span>

<span data-ttu-id="91961-177">**设备恶意软件检测** 提供 Intune 注册的具有尚未完全解决的恶意软件的设备的数量。</span><span class="sxs-lookup"><span data-stu-id="91961-177">**Device malware detections** provide the number of Intune enrolled devices with malware that hasn't been fully resolved.</span></span> <span data-ttu-id="91961-178">缺少解决方案可能是由于挂起的操作、重新启动、完全扫描、手动用户操作或修正操作未成功完成。</span><span class="sxs-lookup"><span data-stu-id="91961-178">A lack of resolution can be because of pending actions, a restart, a full scan, manual user actions, or if the remediation action was not successfully completed.</span></span>

![设备恶意软件检测卡](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="91961-180">了解检测到的恶意软件类型</span><span class="sxs-lookup"><span data-stu-id="91961-180">Understand the types of malware detected</span></span>

<span data-ttu-id="91961-181">**设备上恶意软件的类型** 显示已在 Intune 中注册的设备上检测到的不同类型的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="91961-181">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="91961-182">你可以调查 Microsoft 365 安全中心中的每种类型。</span><span class="sxs-lookup"><span data-stu-id="91961-182">You can investigate each type in the Microsoft 365 security center.</span></span>

![设备卡上的恶意软件类型](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="91961-184">了解在设备上检测到的特定恶意软件</span><span class="sxs-lookup"><span data-stu-id="91961-184">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="91961-185">**设备上恶意软件** 提供在设备上检测到的特定恶意软件的列表。</span><span class="sxs-lookup"><span data-stu-id="91961-185">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![设备卡上的恶意软件](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="91961-187">了解恶意软件最多的设备</span><span class="sxs-lookup"><span data-stu-id="91961-187">Understand which devices have the most malware</span></span>

<span data-ttu-id="91961-188">**具有恶意软件检测的设备** 显示哪些设备具有最多的恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="91961-188">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="91961-189">在 Microsoft 365 安全中心中，你可以调查恶意软件是否处于活动状态、使用设备的人以及 Intune 中的管理状态。</span><span class="sxs-lookup"><span data-stu-id="91961-189">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![具有恶意软件检测卡的设备](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="91961-191">了解哪些用户使用恶意软件最多的设备</span><span class="sxs-lookup"><span data-stu-id="91961-191">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="91961-192">**具有恶意软件检测的用户** 向具有最多恶意软件检测的设备的用户显示。</span><span class="sxs-lookup"><span data-stu-id="91961-192">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="91961-193">在 Microsoft 365 安全中心中，你可以查看分配给每个用户的设备数，以及有关每台设备和恶意软件类型详细信息。</span><span class="sxs-lookup"><span data-stu-id="91961-193">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![具有恶意软件检测卡的用户](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a><span data-ttu-id="91961-195">监视和管理攻击面减少规则部署和检测</span><span class="sxs-lookup"><span data-stu-id="91961-195">Monitor and manage attack surface reduction rule deployment and detections</span></span>

<span data-ttu-id="91961-196">[攻击面 (ASR) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) 规则有助于防止寻找攻击的恶意软件感染设备通常使用的操作和应用。</span><span class="sxs-lookup"><span data-stu-id="91961-196">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="91961-197">这些规则控制何时以及如何运行可执行文件。</span><span class="sxs-lookup"><span data-stu-id="91961-197">These rules control when and how executables can run.</span></span> <span data-ttu-id="91961-198">例如，可阻止 JavaScript 或 VBScript 启动下载的可执行文件，阻止来自 Office 宏的 Win32 API 调用，或者阻止通过 USB 驱动器运行的进程。</span><span class="sxs-lookup"><span data-stu-id="91961-198">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![攻击面减少卡](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="91961-200">**攻击面减少规则** 卡提供了有关跨设备部署规则的概述。</span><span class="sxs-lookup"><span data-stu-id="91961-200">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="91961-201">卡上的顶栏显示了处于以下部署模式的总设备数：</span><span class="sxs-lookup"><span data-stu-id="91961-201">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="91961-202">**阻止模式**：至少配置了一个规则以阻止检测到的活动的设备</span><span class="sxs-lookup"><span data-stu-id="91961-202">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="91961-203">**审核模式**：未设置阻止检测到的活动的规则的设备，但至少有一规则集审核检测到的活动</span><span class="sxs-lookup"><span data-stu-id="91961-203">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="91961-204">**关闭**：所有 ASR 规则均已关闭的设备</span><span class="sxs-lookup"><span data-stu-id="91961-204">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="91961-205">此卡的下半部分按规则显示各设备的设置。</span><span class="sxs-lookup"><span data-stu-id="91961-205">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="91961-206">每个栏指示设置为阻止、审核检测或已完全关闭规则的设备数量。</span><span class="sxs-lookup"><span data-stu-id="91961-206">Each bar indicates the number of devices that are set to block, audit detection, or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="91961-207">查看 ASR 检测</span><span class="sxs-lookup"><span data-stu-id="91961-207">View ASR detections</span></span>

<span data-ttu-id="91961-208">若要查看有关网络中 ASR 规则检测的详细信息，请选择"攻击面减少规则卡上的查看 **检测**"。</span><span class="sxs-lookup"><span data-stu-id="91961-208">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="91961-209">详细 **报告页** 中的"检测"选项卡将打开。</span><span class="sxs-lookup"><span data-stu-id="91961-209">The **Detections** tab in the detailed report page will open.</span></span>

!["检测"选项卡](../../media/detections-tab.png)

<span data-ttu-id="91961-211">页面顶部的图表显示随着时间的推移堆栈检测被阻止或审核的检测。</span><span class="sxs-lookup"><span data-stu-id="91961-211">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="91961-212">底部的表中列出了最近的检测项。</span><span class="sxs-lookup"><span data-stu-id="91961-212">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="91961-213">使用表中的以下信息了解检测的性质：</span><span class="sxs-lookup"><span data-stu-id="91961-213">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="91961-214">**检测到的文件**：文件，通常为脚本或文档，其内容触发了可疑的攻击活动</span><span class="sxs-lookup"><span data-stu-id="91961-214">**Detected file**: the file, typically a script or document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="91961-215">**规则**：描述规则旨在捕获的攻击活动的名称。</span><span class="sxs-lookup"><span data-stu-id="91961-215">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="91961-216">阅读现有 ASR 规则</span><span class="sxs-lookup"><span data-stu-id="91961-216">Read about existing ASR rules</span></span>
* <span data-ttu-id="91961-217">**源应用**：加载或执行触发可疑攻击活动的内容的应用程序。</span><span class="sxs-lookup"><span data-stu-id="91961-217">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="91961-218">它可以是合法应用程序，如 Web 浏览器、Office 应用程序或 PowerShell 等系统工具</span><span class="sxs-lookup"><span data-stu-id="91961-218">It could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="91961-219">**发布者**：发布源应用的供应商</span><span class="sxs-lookup"><span data-stu-id="91961-219">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="91961-220">查看设备 ASR 规则设置</span><span class="sxs-lookup"><span data-stu-id="91961-220">Review device ASR rule settings</span></span>

<span data-ttu-id="91961-221">在" **攻击面减少规则** 报告"页中，转到"配置 **"选项卡查看** 单个设备的规则设置。</span><span class="sxs-lookup"><span data-stu-id="91961-221">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="91961-222">选择设备可获取有关每个规则是位于阻止模式、审核模式还是完全关闭状态的详细信息。</span><span class="sxs-lookup"><span data-stu-id="91961-222">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![配置选项卡](../../media/configuration-tab.png)

<span data-ttu-id="91961-224">Microsoft Intune 为 ASR 规则提供管理功能。</span><span class="sxs-lookup"><span data-stu-id="91961-224">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="91961-225">如果要更新设置，请在选项卡中的"配置设备"下选择"开始使用"，以在 Intune 上打开设备管理。</span><span class="sxs-lookup"><span data-stu-id="91961-225">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="91961-226">从 ASR 规则中排除文件</span><span class="sxs-lookup"><span data-stu-id="91961-226">Exclude files from ASR rules</span></span>

<span data-ttu-id="91961-227">Microsoft 365 安全中心收集你可能希望通过[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules)攻击面减少规则从检测中排除的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="91961-227">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="91961-228">通过排除文件，你可以减少误报检测，并更放心地在阻止模式下部署攻击面减少规则。</span><span class="sxs-lookup"><span data-stu-id="91961-228">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="91961-229">排除项在 Microsoft Intune 上管理，但 Microsoft 365 安全中心提供了分析工具来帮助你了解文件。</span><span class="sxs-lookup"><span data-stu-id="91961-229">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="91961-230">若要开始收集要排除的文件，请转到攻击面减少规则报告页中的"添加排除项 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="91961-230">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="91961-231">该工具分析所有攻击面减少规则的检测，但只有一 [些规则支持排除项](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)。</span><span class="sxs-lookup"><span data-stu-id="91961-231">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![添加排除项选项卡](../../media/add-exclusions-tab.png)

<span data-ttu-id="91961-233">该表列出了攻击面减少规则检测到的所有文件名。</span><span class="sxs-lookup"><span data-stu-id="91961-233">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="91961-234">可以选择文件，查看排除这些文件的影响：</span><span class="sxs-lookup"><span data-stu-id="91961-234">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="91961-235">检测次数减少</span><span class="sxs-lookup"><span data-stu-id="91961-235">How many fewer detections</span></span>
* <span data-ttu-id="91961-236">报告检测的设备数量减少</span><span class="sxs-lookup"><span data-stu-id="91961-236">How many fewer devices report the detections</span></span>

<span data-ttu-id="91961-237">若要获取具有排除的完整路径的选定文件的列表，请选择 **"获取排除路径"。**</span><span class="sxs-lookup"><span data-stu-id="91961-237">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="91961-238">ASR 规则阻止从 Windows 本地安全机构子系统 **(lsass.exe** 中窃取凭据) 捕获源应用 **lsass.exe。**</span><span class="sxs-lookup"><span data-stu-id="91961-238">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**.</span></span> <span data-ttu-id="91961-239">它是正常的系统文件，但捕获为检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="91961-239">It is a normal system file, but captured as the detected file.</span></span> <span data-ttu-id="91961-240">因此，生成的排除路径列表将包含此文件。</span><span class="sxs-lookup"><span data-stu-id="91961-240">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="91961-241">若要排除触发此规则的文件，而不是lsass.exe，请使用源应用的路径，而不是检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="91961-241">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="91961-242">若要找到源应用，请为此特定规则[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)运行以下高级搜寻查询 (规则 ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2) ：</span><span class="sxs-lookup"><span data-stu-id="91961-242">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="91961-243">检查文件是否排除</span><span class="sxs-lookup"><span data-stu-id="91961-243">Check files for exclusion</span></span>

<span data-ttu-id="91961-244">在从 ASR 中排除文件之前，建议您检查该文件以确定该文件是否确实不是恶意文件。</span><span class="sxs-lookup"><span data-stu-id="91961-244">Before excluding a file from ASR, we recommend that you inspect the file to determine if it's indeed not malicious.</span></span>

<span data-ttu-id="91961-245">若要查看文件，请使用 Microsoft Defender 安全中心 [上的](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) 文件信息页。</span><span class="sxs-lookup"><span data-stu-id="91961-245">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="91961-246">该页面提供普遍程度信息和 VirusTotal 防病毒检测比率。</span><span class="sxs-lookup"><span data-stu-id="91961-246">The page provides prevalence information and the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="91961-247">您还可以使用该页面提交文件进行深入分析。</span><span class="sxs-lookup"><span data-stu-id="91961-247">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="91961-248">若要在 Microsoft Defender 安全中心中查找检测到的文件，请通过以下高级搜寻查询搜索所有 ASR 检测：</span><span class="sxs-lookup"><span data-stu-id="91961-248">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="91961-249">使用 **结果中的 SHA1** 或 **InitiatingProcessSHA1，** 使用 Microsoft Defender 安全中心中的通用搜索栏搜索文件。</span><span class="sxs-lookup"><span data-stu-id="91961-249">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
