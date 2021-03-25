---
title: Microsoft Defender for Endpoint 门户概述
description: Microsoft Defender 安全中心可以监视企业网络，并协助响应潜在高级永久性威胁 (APT) 数据泄露。
keywords: Microsoft Defender 安全中心， 门户， 网络安全威胁智能， 仪表板， 警报队列， 设备列表， 设置， 设备管理， 高级攻击
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa7f2df1f0164f24c7f4698e8aa0b699f4884c09
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186217"
---
# <a name="microsoft-defender-security-center-portal-overview"></a><span data-ttu-id="ccc6a-104">Microsoft Defender 安全中心门户概述</span><span class="sxs-lookup"><span data-stu-id="ccc6a-104">Microsoft Defender Security Center portal overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ccc6a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-105">**Applies to:**</span></span>
- [<span data-ttu-id="ccc6a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ccc6a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ccc6a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ccc6a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="ccc6a-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="ccc6a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ccc6a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink) 

<span data-ttu-id="ccc6a-110">企业安全团队可以使用 Microsoft Defender 安全中心监视和协助响应潜在高级永久性威胁活动或数据泄露的警报。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-110">Enterprise security teams can use Microsoft Defender Security Center to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span>

<span data-ttu-id="ccc6a-111">可以使用 [Microsoft Defender 安全中心](https://securitycenter.windows.com/) ：</span><span class="sxs-lookup"><span data-stu-id="ccc6a-111">You can use [Microsoft Defender Security Center](https://securitycenter.windows.com/) to:</span></span>

- <span data-ttu-id="ccc6a-112">查看、排序和会审来自终结点的警报</span><span class="sxs-lookup"><span data-stu-id="ccc6a-112">View, sort, and triage alerts from your endpoints</span></span>
- <span data-ttu-id="ccc6a-113">搜索有关观察到的指示器（如文件和 IP 地址）详细信息</span><span class="sxs-lookup"><span data-stu-id="ccc6a-113">Search for more information on observed indicators such as files and IP Addresses</span></span>
- <span data-ttu-id="ccc6a-114">更改适用于终结点的 Microsoft Defender 设置，包括时区并查看许可信息</span><span class="sxs-lookup"><span data-stu-id="ccc6a-114">Change Microsoft Defender for Endpoint settings, including time zone and review licensing information</span></span>

## <a name="microsoft-defender-security-center"></a><span data-ttu-id="ccc6a-115">Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="ccc6a-115">Microsoft Defender Security Center</span></span>

<span data-ttu-id="ccc6a-116">打开门户时，你将看到：</span><span class="sxs-lookup"><span data-stu-id="ccc6a-116">When you open the portal, you'll see:</span></span>

- <span data-ttu-id="ccc6a-117"> (1) 导航窗格 (选择导航窗格顶部的水平线以显示或隐藏它) </span><span class="sxs-lookup"><span data-stu-id="ccc6a-117">(1) Navigation pane (select the horizontal lines at the top of the navigation pane to show or hide it)</span></span>
- <span data-ttu-id="ccc6a-118"> (2) 搜索， 社区中心， 本地化， 帮助和支持， 反馈</span><span class="sxs-lookup"><span data-stu-id="ccc6a-118">(2) Search, Community center, Localization, Help and support, Feedback</span></span>

 ![适用于终结点的 Microsoft Defender 门户](images/mdatp-portal-overview.png)

> [!NOTE]
> <span data-ttu-id="ccc6a-120">仅在你的设备将 Microsoft Defender 防病毒用作默认的反恶意软件实时保护产品时，才显示与恶意软件相关的检测。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-120">Malware related detections will only appear if your devices are using Microsoft Defender Antivirus as the default real-time protection antimalware product.</span></span>

<span data-ttu-id="ccc6a-121">可以使用所有部分中可用的菜单选项在门户中导航。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-121">You can navigate through the portal using the menu options available in all sections.</span></span> <span data-ttu-id="ccc6a-122">有关每个部分的说明，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-122">Refer to the following table for a description of each section.</span></span>

<span data-ttu-id="ccc6a-123">区域</span><span class="sxs-lookup"><span data-stu-id="ccc6a-123">Area</span></span> | <span data-ttu-id="ccc6a-124">说明</span><span class="sxs-lookup"><span data-stu-id="ccc6a-124">Description</span></span>
:---|:---
<span data-ttu-id="ccc6a-125">**(1) 导航窗格**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-125">**(1) Navigation pane**</span></span> | <span data-ttu-id="ccc6a-126">使用导航窗格在仪表板、事件、**设备** 列表、**警报** 队列、**自动** 调查、高级搜寻、**报告**、合作伙伴 &  **API、** 威胁 &**漏洞** 管理、评估和教程、**服务** 运行状况、配置管理和设置之间移动。  </span><span class="sxs-lookup"><span data-stu-id="ccc6a-126">Use the navigation pane to move between **Dashboards**, **Incidents**, **Devices list**, **Alerts queue**, **Automated investigations**, **Advanced hunting**, **Reports**, **Partners & APIs**, **Threat & Vulnerability Management**, **Evaluation and tutorials**, **Service health**, **Configuration management**, and **Settings**.</span></span> <span data-ttu-id="ccc6a-127">选择导航窗格顶部的水平线以显示或隐藏它。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-127">Select the horizontal lines at the top of the navigation pane to show or hide it.</span></span>
<span data-ttu-id="ccc6a-128">**仪表板**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-128">**Dashboards**</span></span> | <span data-ttu-id="ccc6a-129">访问活动的自动调查、活动警报、自动调查统计信息、处于风险中的设备、处于风险中的用户、传感器问题的设备、服务运行状况、检测源和每日设备报告仪表板。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-129">Access the active automated investigations, active alerts, automated investigations statistics, devices at risk, users at risk, devices with sensor issues, service health, detection sources, and daily devices reporting dashboards.</span></span>
<span data-ttu-id="ccc6a-130">**事件**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-130">**Incidents**</span></span> | <span data-ttu-id="ccc6a-131">查看已聚合为事件的警报。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-131">View alerts that have been aggregated as incidents.</span></span>
<span data-ttu-id="ccc6a-132">**设备列表**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-132">**Devices list**</span></span> | <span data-ttu-id="ccc6a-133">显示已载入 Defender for Endpoint 的设备列表、有关它们的一些信息及其曝光和风险级别。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-133">Displays the list of devices that are onboarded to Defender for Endpoint, some information about them, and their exposure and risk levels.</span></span>
<span data-ttu-id="ccc6a-134">**警报队列**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-134">**Alerts queue**</span></span> | <span data-ttu-id="ccc6a-135">查看从组织中设备生成的警报。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-135">View alerts generated from devices in your organizations.</span></span>
<span data-ttu-id="ccc6a-136">**自动调查**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-136">**Automated investigations**</span></span> | <span data-ttu-id="ccc6a-137">显示网络中已进行的自动调查、触发警报、每个调查的状态以及其他详细信息，如调查的开始时间以及调查的持续时间。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-137">Displays automated investigations that have been conducted in the network, triggering alert, the status of each investigation and other details such as when the investigation started and the duration of the investigation.</span></span>
<span data-ttu-id="ccc6a-138">**高级搜寻**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-138">**Advanced hunting**</span></span> | <span data-ttu-id="ccc6a-139">借助高级搜寻，可以使用功能强大的搜索和查询工具在组织中主动搜寻和调查。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-139">Advanced hunting allows you to proactively hunt and investigate across your organization using a powerful search and query tool.</span></span>
<span data-ttu-id="ccc6a-140">**报表**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-140">**Reports**</span></span> | <span data-ttu-id="ccc6a-141">查看详细介绍威胁防护、设备运行状况和合规性、Web 保护和漏洞的图形。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-141">View graphs detailing threat protection, device health and compliance, web protection, and vulnerability.</span></span>
<span data-ttu-id="ccc6a-142">**合作伙伴& API**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-142">**Partners & APIs**</span></span> | <span data-ttu-id="ccc6a-143">查看受支持的合作伙伴连接，以增强平台的检测、调查和威胁智能功能。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-143">View supported partner connections, which enhance the detection, investigation, and threat intelligence capabilities of the platform.</span></span> <span data-ttu-id="ccc6a-144">还可以查看连接的应用程序、API 资源管理器、API 使用情况概述和数据导出设置。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-144">You can also view connected applications, the API explorer, API usage overview, and data export settings.</span></span>
<span data-ttu-id="ccc6a-145">**威胁&漏洞管理**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-145">**Threat & Vulnerability management**</span></span> | <span data-ttu-id="ccc6a-146">查看你的 Microsoft 设备安全分数、曝光分数、公开的设备、易受攻击的软件，并针对最高安全建议采取措施。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-146">View your Microsoft Secure Score for Devices, exposure score, exposed devices, vulnerable software, and take action on top security recommendations.</span></span>
<span data-ttu-id="ccc6a-147">**评估和教程**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-147">**Evaluation and tutorials**</span></span> | <span data-ttu-id="ccc6a-148">管理测试设备、攻击模拟和报告。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-148">Manage test devices, attack simulations, and reports.</span></span> <span data-ttu-id="ccc6a-149">在试用环境中通过指导性演练了解并体验 Defender for Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-149">Learn and experience the Defender for Endpoint capabilities through a guided walk-through in a trial environment.</span></span>
<span data-ttu-id="ccc6a-150">**服务运行状况**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-150">**Service health**</span></span> | <span data-ttu-id="ccc6a-151">提供有关 Defender for Endpoint 服务的当前状态的信息。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-151">Provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="ccc6a-152">你将能够验证服务运行状况是否正常或当前是否有问题。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-152">You'll be able to verify that the service health is healthy or if there are current issues.</span></span>
<span data-ttu-id="ccc6a-153">**配置管理**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-153">**Configuration management**</span></span> | <span data-ttu-id="ccc6a-154">显示已上线设备、组织的安全基线、预测分析、Web 保护范围，并允许你在设备上执行攻击面管理。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-154">Displays on-boarded devices, your organizations' security baseline, predictive analysis, web protection coverage, and allows you to perform attack surface management on your devices.</span></span>
<span data-ttu-id="ccc6a-155">**设置**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-155">**Settings**</span></span> | <span data-ttu-id="ccc6a-156">显示你在载入期间选择的设置，并允许你更新你的行业首选项和保留策略期限。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-156">Shows the settings you selected during onboarding and lets you update your industry preferences and retention policy period.</span></span> <span data-ttu-id="ccc6a-157">还可以设置其他配置设置，如权限、API、规则、设备管理、IT 服务管理和网络评估。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-157">You can also set other configuration settings such as permissions, APIs, rules, device management, IT service management, and network assessments.</span></span>
<span data-ttu-id="ccc6a-158">**(2) 搜索， 社区中心， 本地化， 帮助和支持， 反馈**</span><span class="sxs-lookup"><span data-stu-id="ccc6a-158">**(2) Search, Community center, Localization,  Help and support, Feedback**</span></span> | <span data-ttu-id="ccc6a-159">**搜索** - 按设备、文件、用户、URL、IP、漏洞、软件和建议进行搜索。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-159">**Search** - search by device, file, user, URL, IP, vulnerability, software, and recommendation.</span></span> </br></br> <span data-ttu-id="ccc6a-160">**社区中心** - 访问社区中心，了解、协作和共享产品体验。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-160">**Community center** - Access the Community center to learn, collaborate, and share experiences about the product.</span></span> </br></br>  <span data-ttu-id="ccc6a-161">**本地化** - 设置时区。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-161">**Localization** - Set time zones.</span></span> </br></br>  <span data-ttu-id="ccc6a-162">**帮助和支持** - 访问适用于终结点的 Defender 指南、Microsoft 和 Microsoft Premier 支持、许可证信息、模拟 & 教程、适用于终结点的 Defender 评估实验室，请咨询威胁专家。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-162">**Help and support** - Access the Defender for Endpoint guide, Microsoft and Microsoft Premier support, license information, simulations & tutorials, Defender for Endpoint evaluation lab, consult a threat expert.</span></span></br></br> <span data-ttu-id="ccc6a-163">**反馈** - 提供有关您喜欢或我们可以更好地执行哪些工作的评论。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-163">**Feedback** - Provide comments about what you like or what we can do better.</span></span>

> [!NOTE]
> <span data-ttu-id="ccc6a-164">对于具有高分辨率 DPI 缩放问题的设备，请参阅适用于高 DPI 设备的 [Windows](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices) 缩放问题，了解可能的解决方案。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-164">For devices with high resolution DPI scaling issues, please see [Windows scaling issues for high-DPI devices](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices) for possible solutions.</span></span>

## <a name="microsoft-defender-for-endpoint-icons"></a><span data-ttu-id="ccc6a-165">Microsoft Defender for Endpoint 图标</span><span class="sxs-lookup"><span data-stu-id="ccc6a-165">Microsoft Defender for Endpoint icons</span></span>

<span data-ttu-id="ccc6a-166">下表提供有关整个门户中使用的图标的信息：</span><span class="sxs-lookup"><span data-stu-id="ccc6a-166">The following table provides information on the icons used all throughout the portal:</span></span>

<span data-ttu-id="ccc6a-167">Icon</span><span class="sxs-lookup"><span data-stu-id="ccc6a-167">Icon</span></span> | <span data-ttu-id="ccc6a-168">说明</span><span class="sxs-lookup"><span data-stu-id="ccc6a-168">Description</span></span>
:---|:---
![ATP 徽标图标](images/atp-logo-icon.png)| <span data-ttu-id="ccc6a-170">适用于终结点的 Microsoft Defender 徽标</span><span class="sxs-lookup"><span data-stu-id="ccc6a-170">Microsoft Defender for Endpoint logo</span></span>
![警报图标](images/alert-icon.png)| <span data-ttu-id="ccc6a-172">警报 – 与高级攻击相关的活动指示。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-172">Alert – Indication of an activity correlated with advanced attacks.</span></span>
![检测图标](images/detection-icon.png)| <span data-ttu-id="ccc6a-174">检测 – 恶意软件威胁检测的指示。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-174">Detection – Indication of a malware threat detection.</span></span>
![活动威胁图标](images/active-threat-icon.png)| <span data-ttu-id="ccc6a-176">活动威胁 – 检测时主动执行的威胁。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-176">Active threat – Threats actively executing at the time of detection.</span></span>
![修正图标1](images/remediated-icon.png)| <span data-ttu-id="ccc6a-178">已修复 – 已从设备中删除的威胁。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-178">Remediated – Threat removed from the device.</span></span>
![未修复的图标](images/not-remediated-icon.png)| <span data-ttu-id="ccc6a-180">未修复 – 未从设备中删除的威胁。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-180">Not remediated – Threat not removed from the device.</span></span>
![Thunderbolt 图标](images/atp-thunderbolt-icon.png)| <span data-ttu-id="ccc6a-182">指示在警报进程树中触发 **警报的事件**。</span><span class="sxs-lookup"><span data-stu-id="ccc6a-182">Indicates events that triggered an alert in the **Alert process tree**.</span></span>
![设备图标](images/atp-machine-icon.png)| <span data-ttu-id="ccc6a-184">设备图标</span><span class="sxs-lookup"><span data-stu-id="ccc6a-184">Device icon</span></span>
![Microsoft Defender AV 事件图标](images/atp-windows-defender-av-events-icon.png)| <span data-ttu-id="ccc6a-186">Microsoft Defender 防病毒事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-186">Microsoft Defender Antivirus events</span></span>
![应用程序防护事件图标](images/atp-Application-Guard-events-icon.png)| <span data-ttu-id="ccc6a-188">Windows Defender应用程序防护事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-188">Windows Defender Application Guard events</span></span>
![Device Guard 事件图标](images/atp-Device-Guard-events-icon.png)| <span data-ttu-id="ccc6a-190">Windows Defender Device Guard 事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-190">Windows Defender Device Guard events</span></span>
![攻击防护事件图标](images/atp-Exploit-Guard-events-icon.png)| <span data-ttu-id="ccc6a-192">Windows Defender攻击防护事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-192">Windows Defender Exploit Guard events</span></span>
![SmartScreen 事件图标](images/atp-Smart-Screen-events-icon.png)| <span data-ttu-id="ccc6a-194">Windows Defender SmartScreen 事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-194">Windows Defender SmartScreen events</span></span>
![防火墙事件图标](images/atp-Firewall-events-icon.png)| <span data-ttu-id="ccc6a-196">Windows 防火墙事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-196">Windows Firewall events</span></span>
![响应操作图标](images/atp-respond-action-icon.png)| <span data-ttu-id="ccc6a-198">响应操作</span><span class="sxs-lookup"><span data-stu-id="ccc6a-198">Response action</span></span>
![进程事件图标](images/atp-process-event-icon.png)| <span data-ttu-id="ccc6a-200">处理事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-200">Process events</span></span>
![网络通信事件图标](images/atp-network-communications-icon.png)| <span data-ttu-id="ccc6a-202">网络事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-202">Network events</span></span>
![文件观察到的事件图标](images/atp-file-observed-icon.png)| <span data-ttu-id="ccc6a-204">文件事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-204">File  events</span></span>
![注册表事件图标](images/atp-registry-event-icon.png)| <span data-ttu-id="ccc6a-206">注册表事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-206">Registry events</span></span>
![模块加载 DLL 事件图标](images/atp-module-load-icon.png)| <span data-ttu-id="ccc6a-208">加载 DLL 事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-208">Load DLL events</span></span>
![其他事件图标](images/atp-Other-events-icon.png)| <span data-ttu-id="ccc6a-210">其他事件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-210">Other events</span></span>
![访问令牌修改图标](images/atp-access-token-modification-icon.png)| <span data-ttu-id="ccc6a-212">访问令牌修改</span><span class="sxs-lookup"><span data-stu-id="ccc6a-212">Access token modification</span></span>
![文件创建图标](images/atp-file-creation-icon.png)| <span data-ttu-id="ccc6a-214">文件创建</span><span class="sxs-lookup"><span data-stu-id="ccc6a-214">File creation</span></span>
![签名者图标](images/atp-signer-icon.png)| <span data-ttu-id="ccc6a-216">签名者</span><span class="sxs-lookup"><span data-stu-id="ccc6a-216">Signer</span></span>
![文件路径图标](images/atp-File-path-icon.png)| <span data-ttu-id="ccc6a-218">文件路径</span><span class="sxs-lookup"><span data-stu-id="ccc6a-218">File path</span></span>
![命令行图标](images/atp-command-line-icon.png)| <span data-ttu-id="ccc6a-220">命令行</span><span class="sxs-lookup"><span data-stu-id="ccc6a-220">Command line</span></span>
![未签名的文件图标](images/atp-unsigned-file-icon.png)| <span data-ttu-id="ccc6a-222">未签名文件</span><span class="sxs-lookup"><span data-stu-id="ccc6a-222">Unsigned file</span></span>
![进程树图标](images/atp-process-tree.png)| <span data-ttu-id="ccc6a-224">进程树</span><span class="sxs-lookup"><span data-stu-id="ccc6a-224">Process tree</span></span>
![内存分配图标](images/atp-memory-allocation-icon.png)| <span data-ttu-id="ccc6a-226">内存分配</span><span class="sxs-lookup"><span data-stu-id="ccc6a-226">Memory allocation</span></span>
![进程注入图标](images/atp-process-injection.png)| <span data-ttu-id="ccc6a-228">进程注入</span><span class="sxs-lookup"><span data-stu-id="ccc6a-228">Process injection</span></span>
![Powershell 命令运行图标](images/atp-powershell-command-run-icon.png)| <span data-ttu-id="ccc6a-230">Powershell 命令运行</span><span class="sxs-lookup"><span data-stu-id="ccc6a-230">Powershell command run</span></span>
![社区中心图标](images/atp-community-center.png) | <span data-ttu-id="ccc6a-232">社区中心</span><span class="sxs-lookup"><span data-stu-id="ccc6a-232">Community center</span></span>
![通知图标](images/atp-notifications.png) | <span data-ttu-id="ccc6a-234">通知</span><span class="sxs-lookup"><span data-stu-id="ccc6a-234">Notifications</span></span>
![未发现威胁](images/no-threats-found.png) | <span data-ttu-id="ccc6a-236">自动调查 - 未找到威胁</span><span class="sxs-lookup"><span data-stu-id="ccc6a-236">Automated investigation - no threats found</span></span>
![失败图标](images/failed.png) | <span data-ttu-id="ccc6a-238">自动调查 - 失败</span><span class="sxs-lookup"><span data-stu-id="ccc6a-238">Automated investigation - failed</span></span>
![部分修复的图标](images/partially-investigated.png) | <span data-ttu-id="ccc6a-240">自动调查 - 部分调查</span><span class="sxs-lookup"><span data-stu-id="ccc6a-240">Automated investigation - partially investigated</span></span>
![已由系统终止](images/terminated-by-system.png) | <span data-ttu-id="ccc6a-242">自动调查 - 由系统终止</span><span class="sxs-lookup"><span data-stu-id="ccc6a-242">Automated investigation - terminated by system</span></span>
![挂起图标](images/pending.png) | <span data-ttu-id="ccc6a-244">自动调查 - 挂起</span><span class="sxs-lookup"><span data-stu-id="ccc6a-244">Automated investigation - pending</span></span>
![正在运行图标](images/running.png) | <span data-ttu-id="ccc6a-246">自动调查 - 运行</span><span class="sxs-lookup"><span data-stu-id="ccc6a-246">Automated investigation - running</span></span>
![修正的图标2](images/remediated.png) | <span data-ttu-id="ccc6a-248">自动调查 - 已修正</span><span class="sxs-lookup"><span data-stu-id="ccc6a-248">Automated investigation - remediated</span></span>
![部分调查的图标](images/partially_remediated.png) | <span data-ttu-id="ccc6a-250">自动调查 - 部分修正</span><span class="sxs-lookup"><span data-stu-id="ccc6a-250">Automated investigation - partially remediated</span></span>
![威胁见解图标](images/tvm_bug_icon.png) | <span data-ttu-id="ccc6a-252">威胁&漏洞管理 - 威胁见解</span><span class="sxs-lookup"><span data-stu-id="ccc6a-252">Threat & Vulnerability Management - threat insights</span></span>
![可能的活动警报图标](images/tvm_alert_icon.png) | <span data-ttu-id="ccc6a-254">威胁&漏洞管理 - 可能的活动警报</span><span class="sxs-lookup"><span data-stu-id="ccc6a-254">Threat & Vulnerability Management - possible active alert</span></span>
![建议见解图标](images/tvm_insight_icon.png) | <span data-ttu-id="ccc6a-256">威胁&漏洞管理 - 建议见解</span><span class="sxs-lookup"><span data-stu-id="ccc6a-256">Threat & Vulnerability Management - recommendation insights</span></span>

## <a name="related-topics"></a><span data-ttu-id="ccc6a-257">相关主题</span><span class="sxs-lookup"><span data-stu-id="ccc6a-257">Related topics</span></span>

- [<span data-ttu-id="ccc6a-258">Microsoft Defender 安全中心概述</span><span class="sxs-lookup"><span data-stu-id="ccc6a-258">Overview of Microsoft Defender Security Center</span></span>](use.md)
- [<span data-ttu-id="ccc6a-259">查看安全操作仪表板</span><span class="sxs-lookup"><span data-stu-id="ccc6a-259">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="ccc6a-260">查看威胁&漏洞管理仪表板</span><span class="sxs-lookup"><span data-stu-id="ccc6a-260">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="ccc6a-261">查看威胁分析仪表板，采取建议的缓解操作</span><span class="sxs-lookup"><span data-stu-id="ccc6a-261">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
