---
title: Microsoft 365 安全中心中的设备监控和报告
description: 介绍如何确保你的设备安全、最新和发现组织中的潜在威胁
keywords: security、恶意软件、Microsoft 365、M365、security center、monitor、report、devices
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: cecc84c1df3ccba3eea75d29aa5f293909d5d51f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600159"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="14a92-104">Microsoft 365 安全中心中的设备监控和报告</span><span class="sxs-lookup"><span data-stu-id="14a92-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="14a92-105">确保你的设备在 Microsoft 365 安全中心中安全、保持最新并找出潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="14a92-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="14a92-106">查看设备警报</span><span class="sxs-lookup"><span data-stu-id="14a92-106">View device alerts</span></span>

<span data-ttu-id="14a92-107">从 Microsoft Defender ATP 获取有关你的设备上的入侵活动和其他威胁的最新警报（适用于 E5 许可证）。</span><span class="sxs-lookup"><span data-stu-id="14a92-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="14a92-108">Microsoft 365 安全中心使用你首选的工作流在较高的层次上有效地监视这些警报。</span><span class="sxs-lookup"><span data-stu-id="14a92-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="14a92-109">监视高影响警报</span><span class="sxs-lookup"><span data-stu-id="14a92-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="14a92-110">每个 Microsoft Defender ATP 警报都有相应的严重性（高、中、低或信息），指示其对网络的潜在影响（如果无人值守）。</span><span class="sxs-lookup"><span data-stu-id="14a92-110">Each Microsoft Defender ATP alert has a corresponding severity (high, medium, low, or informational) that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="14a92-111">使用**设备警报严重级别**卡专门关注更严重且可能需要立即响应的警报。</span><span class="sxs-lookup"><span data-stu-id="14a92-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="14a92-112">在此卡片中，可以查看有关 Microsoft Defender 安全中心门户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="14a92-112">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![设备警报严重级别卡片](../images/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="14a92-114">了解警报的来源</span><span class="sxs-lookup"><span data-stu-id="14a92-114">Understand sources of alerts</span></span>

<span data-ttu-id="14a92-115">Microsoft Defender ATP 利用各种安全传感器和智能源中的数据来生成警报。</span><span class="sxs-lookup"><span data-stu-id="14a92-115">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="14a92-116">例如，它可以使用 Windows Defender 防病毒和第三方反恶意软件中的检测信息，以及通过 web 服务 API 提供的自定义威胁智能。</span><span class="sxs-lookup"><span data-stu-id="14a92-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="14a92-117">**设备警报检测**源卡按来源显示警报的分布情况。</span><span class="sxs-lookup"><span data-stu-id="14a92-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="14a92-118">此卡片可帮助您跟踪与某些来源（尤其是自定义源）相关的活动。</span><span class="sxs-lookup"><span data-stu-id="14a92-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="14a92-119">您还可以使用此操作来重点关注来自未配置为自动阻止恶意活动或组件的传感器发出的警报。</span><span class="sxs-lookup"><span data-stu-id="14a92-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![设备警报检测源卡](../images/device-alert-detection-sources.png)

<span data-ttu-id="14a92-121">在此卡片中，可以查看有关 Microsoft Defender 安全中心门户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="14a92-121">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="14a92-122">了解触发警报的威胁类型</span><span class="sxs-lookup"><span data-stu-id="14a92-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="14a92-123">Microsoft Defender ATP 将每个警报分类到一个类别，表示攻击链中的某个阶段或威胁组件的类型。</span><span class="sxs-lookup"><span data-stu-id="14a92-123">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="14a92-124">例如，检测到的威胁活动可能会被分类为 "横向移动"，以指示有人尝试访问网络上的其他设备。</span><span class="sxs-lookup"><span data-stu-id="14a92-124">For example, a detected threat activity might be categorized as "lateral movement" to indicate that there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="14a92-125">在攻击者获取初始 foothold 之后，也可能发生此活动。</span><span class="sxs-lookup"><span data-stu-id="14a92-125">The activity has also likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="14a92-126">检测到威胁组件时，可能会将其广泛划分为恶意软件，或者更具体地说是作为勒索软件、凭据偷窃或其他类型的恶意软件或不需要的软件。</span><span class="sxs-lookup"><span data-stu-id="14a92-126">When detected, a threat component might either be classified broadly as malware, or more specifically as ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="14a92-127">**设备威胁类别**卡片显示了将警报分布到这些类别中的情况。</span><span class="sxs-lookup"><span data-stu-id="14a92-127">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="14a92-128">您可以使用此信息来确定与社会工程手段尝试相比可能具有更高影响的威胁活动（如凭据盗用尝试）。</span><span class="sxs-lookup"><span data-stu-id="14a92-128">You can use this information to identify threat activity, such as credential theft attempts, that can have higher impact compared to social engineering attempts.</span></span> <span data-ttu-id="14a92-129">您还可以使用此信息监视与勒索软件类似的潜在破坏性威胁。</span><span class="sxs-lookup"><span data-stu-id="14a92-129">You can also use this information to monitor for potentially destructive threats like ransomware.</span></span>

![设备威胁类别卡片](../images/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="14a92-131">监视活动警报</span><span class="sxs-lookup"><span data-stu-id="14a92-131">Monitor active alerts</span></span>

<span data-ttu-id="14a92-132">**设备警报状态**卡指示尚未解决且可能需要注意的警报的数量。</span><span class="sxs-lookup"><span data-stu-id="14a92-132">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="14a92-133">在此卡片中，可以查看有关 Microsoft Defender 安全中心门户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="14a92-133">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![设备警报状态卡片](../images/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="14a92-135">监视已解决警报的分类</span><span class="sxs-lookup"><span data-stu-id="14a92-135">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="14a92-136">在解决 Microsoft Defender ATP 警报时，您的安全人员可以指定是否已将警报验证为：</span><span class="sxs-lookup"><span data-stu-id="14a92-136">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="14a92-137">真正的警报，用于标识实际的违规活动或威胁组件</span><span class="sxs-lookup"><span data-stu-id="14a92-137">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="14a92-138">未正确检测到正常活动的假警报</span><span class="sxs-lookup"><span data-stu-id="14a92-138">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="14a92-139">**设备警报分类**卡显示已解决的警报是否已分类为 "真" 或 "假" 通知。</span><span class="sxs-lookup"><span data-stu-id="14a92-139">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="14a92-140">在此卡片中，可以查看有关 Microsoft Defender 安全中心门户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="14a92-140">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="14a92-141">注意：在某些情况下，分类信息对某些通知不可用。</span><span class="sxs-lookup"><span data-stu-id="14a92-141">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![设备警报分类卡](../images/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="14a92-143">监视已解决警报的确定</span><span class="sxs-lookup"><span data-stu-id="14a92-143">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="14a92-144">除了在解决方案解析过程中对警报是否为 true 或 false 进行分类之外，您的安全人员可以确定在验证警报时发现的正常或恶意活动的类型。</span><span class="sxs-lookup"><span data-stu-id="14a92-144">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="14a92-145">**设备警报确定**卡显示为每个警报提供的决定。</span><span class="sxs-lookup"><span data-stu-id="14a92-145">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="14a92-146">**Apt.**：高级持久威胁，表明检测到的活动或威胁组件是旨在获取受影响网络中的 foothold 的完善的安全漏洞的一部分</span><span class="sxs-lookup"><span data-stu-id="14a92-146">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="14a92-147">**恶意软件**：恶意文件或代码</span><span class="sxs-lookup"><span data-stu-id="14a92-147">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="14a92-148">**安全人员**：安全人员执行的正常活动</span><span class="sxs-lookup"><span data-stu-id="14a92-148">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="14a92-149">**安全测试**：旨在模拟实际威胁并预期触发安全传感器并生成警报的活动或组件</span><span class="sxs-lookup"><span data-stu-id="14a92-149">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="14a92-150">不**需要的软件**：不会被视为恶意的应用程序和其他软件，但也违反了策略或可接受的使用标准</span><span class="sxs-lookup"><span data-stu-id="14a92-150">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="14a92-151">**其他**：不属于所提供类型的任何其他确定</span><span class="sxs-lookup"><span data-stu-id="14a92-151">**Others**: any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="14a92-152">在此卡片中，可以查看 Microsoft Defender 安全中心中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="14a92-152">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![设备警报确定卡](../images/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="14a92-154">了解哪些设备有风险</span><span class="sxs-lookup"><span data-stu-id="14a92-154">Understand which devices are at risk</span></span>

<span data-ttu-id="14a92-155">**设备保护**显示设备的风险级别。</span><span class="sxs-lookup"><span data-stu-id="14a92-155">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="14a92-156">风险级别基于设备上的警报的类型和严重性等因素。</span><span class="sxs-lookup"><span data-stu-id="14a92-156">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![设备保护卡](../images/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="14a92-158">监视和报告 Intune 管理的设备的状态</span><span class="sxs-lookup"><span data-stu-id="14a92-158">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="14a92-159">以下报告包含在 Intune 中注册的设备的数据。</span><span class="sxs-lookup"><span data-stu-id="14a92-159">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="14a92-160">不包括来自 unenrolled 设备的数据。</span><span class="sxs-lookup"><span data-stu-id="14a92-160">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="14a92-161">只有全局管理员才能查看这些卡片。</span><span class="sxs-lookup"><span data-stu-id="14a92-161">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="14a92-162">Intune 注册的设备数据包括：</span><span class="sxs-lookup"><span data-stu-id="14a92-162">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="14a92-163">设备合规性</span><span class="sxs-lookup"><span data-stu-id="14a92-163">Device compliance</span></span>
* <span data-ttu-id="14a92-164">具有活动恶意软件的设备</span><span class="sxs-lookup"><span data-stu-id="14a92-164">Devices with active malware</span></span>
* <span data-ttu-id="14a92-165">设备上的恶意软件类型</span><span class="sxs-lookup"><span data-stu-id="14a92-165">Types of malware on devices</span></span>
* <span data-ttu-id="14a92-166">设备上的恶意软件</span><span class="sxs-lookup"><span data-stu-id="14a92-166">Malware on devices</span></span>
* <span data-ttu-id="14a92-167">包含恶意软件检测的设备</span><span class="sxs-lookup"><span data-stu-id="14a92-167">Devices with malware detections</span></span>
* <span data-ttu-id="14a92-168">包含恶意软件检测的用户</span><span class="sxs-lookup"><span data-stu-id="14a92-168">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="14a92-169">监视设备合规性</span><span class="sxs-lookup"><span data-stu-id="14a92-169">Monitor device compliance</span></span>

<span data-ttu-id="14a92-170">**设备符合性**显示在 Intune 中注册的设备数量符合配置策略。</span><span class="sxs-lookup"><span data-stu-id="14a92-170">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![设备合规性卡](../images/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="14a92-172">发现包含恶意软件检测的设备</span><span class="sxs-lookup"><span data-stu-id="14a92-172">Discover devices with malware detections</span></span>

<span data-ttu-id="14a92-173">**设备恶意软件检测**提供了未完全解决的包含恶意软件的 Intune 注册设备的数量。</span><span class="sxs-lookup"><span data-stu-id="14a92-173">**Device malware detections** provide the number of Intune enrolled devices with malware that have not been fully resolved.</span></span> <span data-ttu-id="14a92-174">这可能是由于挂起的操作、重新启动、完全扫描、手动用户操作或更正操作未成功完成造成的。</span><span class="sxs-lookup"><span data-stu-id="14a92-174">This can be due to pending actions, a restart, a full scan, manual user actions, or if the remediation action did not complete successfully.</span></span>

![设备恶意软件检测卡片](../images/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="14a92-176">了解检测到的恶意软件的类型</span><span class="sxs-lookup"><span data-stu-id="14a92-176">Understand the types of malware detected</span></span>

<span data-ttu-id="14a92-177">**设备上的恶意软件类型**显示在 Intune 中注册的设备上检测到的不同类型的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="14a92-177">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="14a92-178">您可以调查 Microsoft 365 安全中心中的每种类型。</span><span class="sxs-lookup"><span data-stu-id="14a92-178">You can investigate each type in the Microsoft 365 security center.</span></span>

![设备卡上的恶意软件类型](../images/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="14a92-180">了解在你的设备上检测到的特定恶意软件</span><span class="sxs-lookup"><span data-stu-id="14a92-180">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="14a92-181">**设备上的恶意软件**提供在设备上检测到的特定恶意软件的列表。</span><span class="sxs-lookup"><span data-stu-id="14a92-181">**Malware on devices** provide a list of the specific malware detected on your devices.</span></span>

![设备卡上的恶意软件](../images/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="14a92-183">了解哪些设备具有最多的恶意软件</span><span class="sxs-lookup"><span data-stu-id="14a92-183">Understand which devices have the most malware</span></span>

<span data-ttu-id="14a92-184">**带有恶意软件检测的设备**显示哪些设备具有最多的恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="14a92-184">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="14a92-185">在 Microsoft 365 安全中心中，可以调查恶意软件是处于活动状态、使用设备的用户及其在 Intune 中的管理状态。</span><span class="sxs-lookup"><span data-stu-id="14a92-185">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![包含恶意软件检测卡片的设备](../images/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="14a92-187">了解哪些用户具有最多恶意软件的设备</span><span class="sxs-lookup"><span data-stu-id="14a92-187">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="14a92-188">**具有恶意软件检测的用户**显示具有最多恶意软件检测到的设备的用户。</span><span class="sxs-lookup"><span data-stu-id="14a92-188">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="14a92-189">在 Microsoft 365 安全中心中，可以查看为每个用户分配了多少个设备，以及有关每个设备和恶意软件类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="14a92-189">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![具有恶意软件检测卡片的用户](../images/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="14a92-191">监视和管理 ASR 规则部署和检测</span><span class="sxs-lookup"><span data-stu-id="14a92-191">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="14a92-192">[攻击面减少（ASR）规则](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)可帮助阻止使用者查找恶意软件时通常使用的操作和应用程序感染设备。</span><span class="sxs-lookup"><span data-stu-id="14a92-192">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="14a92-193">这些规则控制何时以及如何运行可执行文件。</span><span class="sxs-lookup"><span data-stu-id="14a92-193">These rules control when and how executables can run.</span></span> <span data-ttu-id="14a92-194">例如，可以阻止 JavaScript 或 VBScript 启动下载的可执行文件、阻止来自 Office 宏的 Win32 API 调用或阻止从 USB 驱动器运行的进程。</span><span class="sxs-lookup"><span data-stu-id="14a92-194">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![攻击面缩减卡片](../images/attack-surface-reduction-rules.png)

<span data-ttu-id="14a92-196">**攻击面减少规则**卡提供了跨设备部署规则的概述。</span><span class="sxs-lookup"><span data-stu-id="14a92-196">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="14a92-197">卡片上的顶栏显示了以下部署模式中的设备总数：</span><span class="sxs-lookup"><span data-stu-id="14a92-197">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="14a92-198">**阻止模式**：至少有一个配置为阻止检测到的活动的一个规则的设备</span><span class="sxs-lookup"><span data-stu-id="14a92-198">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="14a92-199">**审核模式**：没有设置为阻止检测到的活动的设备，但至少有一个规则集来审核检测到的活动</span><span class="sxs-lookup"><span data-stu-id="14a92-199">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="14a92-200">**Off**：关闭所有 ASR 规则的设备</span><span class="sxs-lookup"><span data-stu-id="14a92-200">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="14a92-201">此卡片的下半部分按规则显示设备上的设置。</span><span class="sxs-lookup"><span data-stu-id="14a92-201">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="14a92-202">每条栏指示设置为阻止或审核检测或完全关闭规则的设备的数量。</span><span class="sxs-lookup"><span data-stu-id="14a92-202">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="14a92-203">查看 ASR 检测</span><span class="sxs-lookup"><span data-stu-id="14a92-203">View ASR detections</span></span>

<span data-ttu-id="14a92-204">若要查看有关网络中的 ASR 规则检测的详细信息，请选择 "查看**受攻击面减少的规则**卡片上的**检测**"。</span><span class="sxs-lookup"><span data-stu-id="14a92-204">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="14a92-205">将打开 "详细报告" 页中的 "**检测**到" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="14a92-205">The **Detections** tab in the detailed report page will open.</span></span>

![检测项选项卡](../images/detections-tab.png)

<span data-ttu-id="14a92-207">页面顶部的图表显示了已被阻止或审核的时间堆栈检测中的检测项。</span><span class="sxs-lookup"><span data-stu-id="14a92-207">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="14a92-208">底部的表列出了最近检测到的内容。</span><span class="sxs-lookup"><span data-stu-id="14a92-208">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="14a92-209">使用表中的以下信息来了解检测项的性质：</span><span class="sxs-lookup"><span data-stu-id="14a92-209">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="14a92-210">**检测到的文件**：文件（通常为脚本或文档），其内容触发了可疑的攻击活动</span><span class="sxs-lookup"><span data-stu-id="14a92-210">**Detected file**: the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="14a92-211">**规则**：描述规则旨在捕获的攻击活动的名称。</span><span class="sxs-lookup"><span data-stu-id="14a92-211">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="14a92-212">阅读有关现有 ASR 规则的信息</span><span class="sxs-lookup"><span data-stu-id="14a92-212">Read about existing ASR rules</span></span>
* <span data-ttu-id="14a92-213">**源应用**：加载或执行了触发可疑攻击活动的内容的应用程序。</span><span class="sxs-lookup"><span data-stu-id="14a92-213">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="14a92-214">这可能是合法的应用程序，如 web 浏览器、Office 应用程序或 PowerShell 等系统工具</span><span class="sxs-lookup"><span data-stu-id="14a92-214">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="14a92-215">**Publisher**：发布源应用程序的供应商</span><span class="sxs-lookup"><span data-stu-id="14a92-215">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="14a92-216">查看设备 ASR 规则设置</span><span class="sxs-lookup"><span data-stu-id="14a92-216">Review device ASR rule settings</span></span>

<span data-ttu-id="14a92-217">在 "**攻击面降低规则**报告" 页上，转到 "**配置**" 选项卡以查看各个设备的规则设置。</span><span class="sxs-lookup"><span data-stu-id="14a92-217">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="14a92-218">选择一个设备，以获取有关每个规则是处于阻止模式、审核模式还是完全关闭状态的详细信息。</span><span class="sxs-lookup"><span data-stu-id="14a92-218">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

!["配置" 选项卡](../images/configuration-tab.png)

<span data-ttu-id="14a92-220">Microsoft Intune 为你的 ASR 规则提供管理功能。</span><span class="sxs-lookup"><span data-stu-id="14a92-220">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="14a92-221">如果要更新设置，请选择选项卡中的 "**配置设备**" 下的 "**启动**"，以在 Intune 上打开 "设备管理"。</span><span class="sxs-lookup"><span data-stu-id="14a92-221">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="14a92-222">从 ASR 规则中排除文件</span><span class="sxs-lookup"><span data-stu-id="14a92-222">Exclude files from ASR rules</span></span>

<span data-ttu-id="14a92-223">Microsoft 365 security center 根据攻击面减少规则收集[您可能要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules)从检测中排除的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="14a92-223">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="14a92-224">通过排除文件，可以减少误报检测，并更自信地在阻止模式下部署攻击面降低规则。</span><span class="sxs-lookup"><span data-stu-id="14a92-224">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="14a92-225">排除在 Microsoft Intune 上进行管理，但 Microsoft 365 安全中心提供了分析工具，可帮助您了解这些文件。</span><span class="sxs-lookup"><span data-stu-id="14a92-225">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="14a92-226">若要开始收集要排除的文件，请转到**攻击面减少规则**报告页中的 "**添加排除**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="14a92-226">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="14a92-227">该工具将分析所有攻击面减少规则的检测项，但[只有某些规则支持排除](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)项。</span><span class="sxs-lookup"><span data-stu-id="14a92-227">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![添加排除选项卡](../images/add-exclusions-tab.png)

<span data-ttu-id="14a92-229">该表列出了受攻击面减少规则检测到的所有文件名。</span><span class="sxs-lookup"><span data-stu-id="14a92-229">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="14a92-230">您可以选择文件以查看排除它们的影响：</span><span class="sxs-lookup"><span data-stu-id="14a92-230">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="14a92-231">检测项的少多少</span><span class="sxs-lookup"><span data-stu-id="14a92-231">How many fewer detections</span></span>
* <span data-ttu-id="14a92-232">多少较少的设备报告检测</span><span class="sxs-lookup"><span data-stu-id="14a92-232">How many fewer devices report the detections</span></span>

<span data-ttu-id="14a92-233">若要获取所选文件的完整路径的列表以供排除，请选择 "**获取排除路径**"。</span><span class="sxs-lookup"><span data-stu-id="14a92-233">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="14a92-234">用于 ASR 规则**块凭据的日志从 Windows 本地安全颁发机构子系统（lsass.exe）** 捕获源应用**lsass**（如检测到的文件）。</span><span class="sxs-lookup"><span data-stu-id="14a92-234">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**, a normal system file, as the detected file.</span></span> <span data-ttu-id="14a92-235">因此，生成的排除路径列表将包含此文件。</span><span class="sxs-lookup"><span data-stu-id="14a92-235">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="14a92-236">若要排除触发此规则而不是**lsass.exe**的文件，请使用源应用的路径，而不是检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="14a92-236">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="14a92-237">若要查找源应用程序，请对此特定规则运行以下[高级搜寻查询](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)（由规则 ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2）：</span><span class="sxs-lookup"><span data-stu-id="14a92-237">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="14a92-238">检查要排除的文件</span><span class="sxs-lookup"><span data-stu-id="14a92-238">Check files for exclusion</span></span>

<span data-ttu-id="14a92-239">在从 ASR 中排除文件之前，我们建议您检查该文件以确定它是否确实不是恶意的。</span><span class="sxs-lookup"><span data-stu-id="14a92-239">Before excluding a file from ASR, we recommend that you inspect the file to determine if it is indeed not malicious.</span></span>

<span data-ttu-id="14a92-240">若要查看文件，请使用 Microsoft Defender 安全中心上的[文件信息页面](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files)。</span><span class="sxs-lookup"><span data-stu-id="14a92-240">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="14a92-241">页面提供了传播信息以及 VirusTotal 防病毒检测比率。</span><span class="sxs-lookup"><span data-stu-id="14a92-241">The page provides prevalence information as well as the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="14a92-242">您还可以使用页面提交文件进行深入分析。</span><span class="sxs-lookup"><span data-stu-id="14a92-242">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="14a92-243">若要在 Microsoft Defender 安全中心中查找检测到的文件，请使用以下高级搜寻查询搜索所有 ASR 检测：</span><span class="sxs-lookup"><span data-stu-id="14a92-243">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="14a92-244">在结果中使用**SHA1**或**InitiatingProcessSHA1**在 Microsoft Defender 安全中心中使用通用搜索栏搜索文件。</span><span class="sxs-lookup"><span data-stu-id="14a92-244">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
