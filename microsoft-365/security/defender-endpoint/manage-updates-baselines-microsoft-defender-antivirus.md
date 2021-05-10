---
title: 管理Microsoft Defender 防病毒更新并应用基线
description: 管理 Microsoft Defender 防病毒如何接收保护和产品更新。
keywords: 更新， 安全基线， 保护， 计划更新， 强制更新， 移动更新， wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 05/08/2021
ms.openlocfilehash: 4f2b931018d49affa2d94ddf1a147c4fd2e02085
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302072"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="c1aa0-104">管理Microsoft Defender 防病毒更新并应用基线</span><span class="sxs-lookup"><span data-stu-id="c1aa0-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="c1aa0-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-105">**Applies to:**</span></span>

- [<span data-ttu-id="c1aa0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c1aa0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="c1aa0-107">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="c1aa0-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="c1aa0-108">有两种类型的更新与使Microsoft Defender 防病毒保持最新有关：</span><span class="sxs-lookup"><span data-stu-id="c1aa0-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="c1aa0-109">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-109">Security intelligence updates</span></span>
- <span data-ttu-id="c1aa0-110">产品更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1aa0-111">保持Microsoft Defender 防病毒保持最新状态对于确保你的设备具有抵御新的恶意软件和攻击技术所需的最新技术和功能至关重要。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="c1aa0-112">确保更新防病毒保护，即使Microsoft Defender 防病毒处于被动[模式。](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="c1aa0-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="c1aa0-113">To see the most current engine， platform， and signature date， visit the [Security intelligence updates for Microsoft Defender 防病毒 other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="c1aa0-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="c1aa0-114">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-114">Security intelligence updates</span></span>

<span data-ttu-id="c1aa0-115">Microsoft Defender 防病毒云[提供的](cloud-protection-microsoft-defender-antivirus.md)保护 (也称为 Microsoft 高级保护服务或 MAPS) 并定期下载安全智能更新以提供保护。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="c1aa0-116">更新以以下 KB 编号发布：</span><span class="sxs-lookup"><span data-stu-id="c1aa0-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="c1aa0-117">Microsoft Defender 防病毒：KB2267602</span><span class="sxs-lookup"><span data-stu-id="c1aa0-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="c1aa0-118">System Center Endpoint Protection：KB2461484</span><span class="sxs-lookup"><span data-stu-id="c1aa0-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="c1aa0-119">云提供的保护始终打开，并且需要与 Internet 的活动连接以正常运行。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="c1aa0-120">安全智能更新按计划节奏进行， (策略策略配置) 。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="c1aa0-121">有关详细信息，请参阅使用[Microsoft 云提供的Microsoft Defender 防病毒。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c1aa0-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="c1aa0-122">有关最近安全智能更新的列表，请参阅安全智能更新[Microsoft Defender 防病毒和其他 Microsoft 反恶意软件](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="c1aa0-123">引擎更新包含在安全智能更新中，并按月发布。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="c1aa0-124">产品更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-124">Product updates</span></span>

<span data-ttu-id="c1aa0-125">Microsoft Defender 防病毒需要每月更新 [ (KB4052623](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform))  (称为平台更新 *) ，* 并且将在 Windows 10 版本旁边接收主要功能更新。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="c1aa0-126">可以通过以下方法之一管理更新的分发：</span><span class="sxs-lookup"><span data-stu-id="c1aa0-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="c1aa0-127">WindowsWSUS (服务器更新) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="c1aa0-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c1aa0-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="c1aa0-129">你用于部署 Microsoft 和Windows终结点更新的常用方法。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="c1aa0-130">有关详细信息，请参阅管理保护Microsoft Defender 防病毒[源](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="c1aa0-131">每月更新会分期发布，从而在 Window Server Update Services 中显示 [多个程序包](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="c1aa0-132">每月平台和引擎版本</span><span class="sxs-lookup"><span data-stu-id="c1aa0-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="c1aa0-133">若要了解如何更新或安装平台更新，请参阅反恶意软件Windows Defender[更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="c1aa0-134">我们的所有更新都包含</span><span class="sxs-lookup"><span data-stu-id="c1aa0-134">All our updates contain</span></span> 
- <span data-ttu-id="c1aa0-135">性能改进;</span><span class="sxs-lookup"><span data-stu-id="c1aa0-135">performance improvements;</span></span>
- <span data-ttu-id="c1aa0-136">可服务性改进;和</span><span class="sxs-lookup"><span data-stu-id="c1aa0-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="c1aa0-137">集成改进 (云，Microsoft 365 Defender) 。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="c1aa0-138">2021 年 4 月 (平台：4.18.2104.9|引擎：1.1.18100.5) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-138">April-2021 (Platform: 4.18.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="c1aa0-139">&ensp;安全智能更新版本 **：1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="c1aa0-140">&ensp;发布时间 **：2021 年 4 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="c1aa0-141">&ensp;平台 **：4.18.2104.9**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-141">&ensp;Platform: **4.18.2104.9**</span></span>  
<span data-ttu-id="c1aa0-142">&ensp;引擎 **：1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="c1aa0-143">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-144">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-144">What's new</span></span>
- <span data-ttu-id="c1aa0-145">其他行为监视逻辑</span><span class="sxs-lookup"><span data-stu-id="c1aa0-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="c1aa0-146">改进了内核模式键记录器检测</span><span class="sxs-lookup"><span data-stu-id="c1aa0-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1aa0-147">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-147">Known Issues</span></span>
<span data-ttu-id="c1aa0-148">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1aa0-149">2021 年 3 月 (平台：4.18.2103.7 |引擎：1.1.18000.5) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-149">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="c1aa0-150">&ensp;安全智能更新版本 **：1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="c1aa0-151">&ensp;发布时间 **：2021 年 4 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="c1aa0-152">&ensp;平台 **：4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-152">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="c1aa0-153">&ensp;引擎 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="c1aa0-154">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-155">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-155">What's new</span></span>

- <span data-ttu-id="c1aa0-156">对行为监控引擎的改进</span><span class="sxs-lookup"><span data-stu-id="c1aa0-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="c1aa0-157">扩展的网络暴力攻击缓解措施</span><span class="sxs-lookup"><span data-stu-id="c1aa0-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="c1aa0-158">启用防篡改保护 [时的其他失败](prevent-changes-to-security-settings-with-tamper-protection.md) 篡改尝试事件生成</span><span class="sxs-lookup"><span data-stu-id="c1aa0-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1aa0-159">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-159">Known Issues</span></span>
<span data-ttu-id="c1aa0-160">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c1aa0-161">2021 年 2 月 (平台：4.18.2102.3 |引擎：1.1.17900.7) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-161">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="c1aa0-162">&ensp;安全智能更新版本 **：1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="c1aa0-163">&ensp;已发布 **：2021 年 3 月 9 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="c1aa0-164">&ensp;平台 **：4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-164">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="c1aa0-165">&ensp;引擎 **：1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="c1aa0-166">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-167">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-167">What's new</span></span>

- <span data-ttu-id="c1aa0-168">通过防篡改保护 [改进了服务恢复](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c1aa0-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="c1aa0-169">扩展防篡改保护作用域</span><span class="sxs-lookup"><span data-stu-id="c1aa0-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1aa0-170">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-170">Known Issues</span></span>
<span data-ttu-id="c1aa0-171">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="c1aa0-172">旧版本更新：仅技术升级支持</span><span class="sxs-lookup"><span data-stu-id="c1aa0-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="c1aa0-173">发布新程序包版本后，仅对前两个版本的支持减少到技术支持。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="c1aa0-174">低于本部分中列出的版本，并且仅提供用于技术升级支持的版本。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="c1aa0-175">2021 年 1 月 (平台：4.18.2101.9 |引擎：1.1.17800.5) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="c1aa0-176">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="c1aa0-177">&ensp;发布时间 **：2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="c1aa0-178">&ensp;平台 **：4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="c1aa0-179">&ensp;引擎 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="c1aa0-180">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-181">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-181">What's new</span></span>

- <span data-ttu-id="c1aa0-182">Shellcode 攻击检测改进</span><span class="sxs-lookup"><span data-stu-id="c1aa0-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="c1aa0-183">提高了凭据窃取尝试的可见性</span><span class="sxs-lookup"><span data-stu-id="c1aa0-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="c1aa0-184">改进服务中的反Microsoft Defender 防病毒功能</span><span class="sxs-lookup"><span data-stu-id="c1aa0-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="c1aa0-185">改进了对 x64 ARM的支持</span><span class="sxs-lookup"><span data-stu-id="c1aa0-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="c1aa0-186">修复：EDR执行初始检测后阻止通知仍保留在威胁历史记录中</span><span class="sxs-lookup"><span data-stu-id="c1aa0-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1aa0-187">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-187">Known Issues</span></span>
<span data-ttu-id="c1aa0-188">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c1aa0-189">2020 年 11 月 (平台：4.18.2011.6 |引擎：1.1.17700.4) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="c1aa0-190">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="c1aa0-191">&ensp;发布时间 **：2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="c1aa0-192">&ensp;平台 **：4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="c1aa0-193">&ensp;引擎 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="c1aa0-194">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-195">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-195">What's new</span></span>

- <span data-ttu-id="c1aa0-196">改进 [的 SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 状态支持日志记录</span><span class="sxs-lookup"><span data-stu-id="c1aa0-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1aa0-197">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-197">Known Issues</span></span>
<span data-ttu-id="c1aa0-198">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c1aa0-199">2020 年 10 月 (平台：4.18.2010.7 |引擎：1.1.17600.5) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="c1aa0-200">&ensp;安全智能更新版本 **：1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="c1aa0-201">&ensp;发布时间 **：2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="c1aa0-202">&ensp;平台 **：4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="c1aa0-203">&ensp;引擎 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="c1aa0-204">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-205">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-205">What's new</span></span>

- <span data-ttu-id="c1aa0-206">特殊威胁类别的新说明</span><span class="sxs-lookup"><span data-stu-id="c1aa0-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="c1aa0-207">改进的模拟功能</span><span class="sxs-lookup"><span data-stu-id="c1aa0-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="c1aa0-208">改进了主机地址允许/阻止功能</span><span class="sxs-lookup"><span data-stu-id="c1aa0-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="c1aa0-209">Defender CSP 中用于忽略本地用户排除项合并的新选项</span><span class="sxs-lookup"><span data-stu-id="c1aa0-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1aa0-210">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-210">Known Issues</span></span>

<span data-ttu-id="c1aa0-211">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="c1aa0-212">2020 年 9 月 (平台：4.18.2009.7 |引擎：1.1.17500.4) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="c1aa0-213">&ensp;安全智能更新版本 **：1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="c1aa0-214">&ensp;发布时间 **：2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="c1aa0-215">&ensp;平台 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="c1aa0-216">&ensp;引擎 **：1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="c1aa0-217">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-218">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-218">What's new</span></span>

- <span data-ttu-id="c1aa0-219">需要管理员权限才能还原隔离中的文件</span><span class="sxs-lookup"><span data-stu-id="c1aa0-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="c1aa0-220">XML 格式事件现在受支持</span><span class="sxs-lookup"><span data-stu-id="c1aa0-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="c1aa0-221">忽略排除合并的云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="c1aa0-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="c1aa0-222">用于：</span><span class="sxs-lookup"><span data-stu-id="c1aa0-222">New management interfaces for:</span></span>
   - <span data-ttu-id="c1aa0-223">UDP 检查</span><span class="sxs-lookup"><span data-stu-id="c1aa0-223">UDP Inspection</span></span>
   - <span data-ttu-id="c1aa0-224">Server 2019 上的网络保护</span><span class="sxs-lookup"><span data-stu-id="c1aa0-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="c1aa0-225">网络保护的 IP 地址排除项</span><span class="sxs-lookup"><span data-stu-id="c1aa0-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="c1aa0-226">改进了对 TPM 测量的可见性</span><span class="sxs-lookup"><span data-stu-id="c1aa0-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="c1aa0-227">改进了 Office VBA 模块扫描</span><span class="sxs-lookup"><span data-stu-id="c1aa0-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1aa0-228">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-228">Known Issues</span></span>

<span data-ttu-id="c1aa0-229">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="c1aa0-230">2020 年 8 月 (平台：4.18.2008.9 |引擎：1.1.17400.5) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="c1aa0-231">&ensp;安全智能更新版本 **：1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="c1aa0-232">&ensp;发布时间 **：2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="c1aa0-233">&ensp;平台 **：4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="c1aa0-234">&ensp;引擎 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="c1aa0-235">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="c1aa0-236">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-236">What's new</span></span>

- <span data-ttu-id="c1aa0-237">添加更多遥测事件</span><span class="sxs-lookup"><span data-stu-id="c1aa0-237">Add more telemetry events</span></span>
- <span data-ttu-id="c1aa0-238">改进了扫描事件遥测</span><span class="sxs-lookup"><span data-stu-id="c1aa0-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="c1aa0-239">改进了内存扫描行为监视</span><span class="sxs-lookup"><span data-stu-id="c1aa0-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="c1aa0-240">改进的宏流扫描</span><span class="sxs-lookup"><span data-stu-id="c1aa0-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="c1aa0-241">已 `AMRunningMode` 添加到 Get-MpComputerStatus PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="c1aa0-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="c1aa0-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="c1aa0-243">Microsoft Defender 防病毒检测到其他防病毒程序时自动关闭自身。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="c1aa0-244">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-244">Known Issues</span></span>
<span data-ttu-id="c1aa0-245">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1aa0-246">2020 年 7 月 (平台：4.18.2007.8 |引擎：1.1.17300.4) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="c1aa0-247">&ensp;安全智能更新版本 **：1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="c1aa0-248">&ensp;发布时间 **：2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="c1aa0-249">&ensp;平台 **：4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="c1aa0-250">&ensp;引擎 **：1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="c1aa0-251">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-252">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-252">What's new</span></span>

- <span data-ttu-id="c1aa0-253">改进的 BITS 遥测</span><span class="sxs-lookup"><span data-stu-id="c1aa0-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="c1aa0-254">改进的验证码代码签名证书验证</span><span class="sxs-lookup"><span data-stu-id="c1aa0-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1aa0-255">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-255">Known Issues</span></span>
<span data-ttu-id="c1aa0-256">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1aa0-257">2020 年 6 月 (平台：4.18.2006.10 |引擎：1.1.17200.2) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="c1aa0-258">&ensp;安全智能更新版本 **：1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="c1aa0-259">&ensp;发布时间 **：2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="c1aa0-260">&ensp;平台 **：4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="c1aa0-261">&ensp;引擎 **：1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="c1aa0-262">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-263">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-263">What's new</span></span>

- <span data-ttu-id="c1aa0-264">指定支持 [日志的位置的可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="c1aa0-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="c1aa0-265">在被动模式下跳过主动的捕获扫描。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="c1aa0-266">允许 Defender 更新按流量计费的连接</span><span class="sxs-lookup"><span data-stu-id="c1aa0-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="c1aa0-267">修复了禁用缓存时的性能调整</span><span class="sxs-lookup"><span data-stu-id="c1aa0-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="c1aa0-268">修复了注册表查询</span><span class="sxs-lookup"><span data-stu-id="c1aa0-268">Fixed registry query</span></span> 
- <span data-ttu-id="c1aa0-269">修复了 ADMX 中的扫描时间随机化</span><span class="sxs-lookup"><span data-stu-id="c1aa0-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1aa0-270">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-270">Known Issues</span></span>
<span data-ttu-id="c1aa0-271">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1aa0-272">2020 年 5 月 (平台：4.18.2005.4 |引擎：1.1.17100.2) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="c1aa0-273">&ensp;安全智能更新版本 **：1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="c1aa0-274">&ensp;发布时间 **：2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="c1aa0-275">&ensp;平台 **：4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="c1aa0-276">&ensp;引擎 **：1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="c1aa0-277">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-278">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-278">What's new</span></span>

- <span data-ttu-id="c1aa0-279">改进了扫描事件的日志记录</span><span class="sxs-lookup"><span data-stu-id="c1aa0-279">Improved logging for scan events</span></span>
- <span data-ttu-id="c1aa0-280">改进了用户模式崩溃处理。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="c1aa0-281">添加了防篡改保护的事件跟踪</span><span class="sxs-lookup"><span data-stu-id="c1aa0-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="c1aa0-282">修复了 AMSI 示例提交</span><span class="sxs-lookup"><span data-stu-id="c1aa0-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="c1aa0-283">修复了 AMSI 云阻止</span><span class="sxs-lookup"><span data-stu-id="c1aa0-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="c1aa0-284">修复了安全更新安装日志</span><span class="sxs-lookup"><span data-stu-id="c1aa0-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1aa0-285">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-285">Known Issues</span></span>
<span data-ttu-id="c1aa0-286">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1aa0-287">2020 年 4 月 (平台：4.18.2004.6 |引擎：1.1.17000.2) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="c1aa0-288">&ensp;安全智能更新版本 **：1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="c1aa0-289">&ensp;发布时间 **：2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="c1aa0-290">&ensp;平台 **：4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="c1aa0-291">&ensp;引擎 **：1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="c1aa0-292">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-293">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-293">What's new</span></span>
- <span data-ttu-id="c1aa0-294">WDfilter 改进</span><span class="sxs-lookup"><span data-stu-id="c1aa0-294">WDfilter improvements</span></span>
- <span data-ttu-id="c1aa0-295">向攻击面减少检测事件添加更多可操作事件数据</span><span class="sxs-lookup"><span data-stu-id="c1aa0-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="c1aa0-296">诊断数据和 WMI 中的固定版本信息</span><span class="sxs-lookup"><span data-stu-id="c1aa0-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="c1aa0-297">修复了平台更新后 UI 中的平台版本不正确</span><span class="sxs-lookup"><span data-stu-id="c1aa0-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="c1aa0-298">用于无文件威胁防护的动态 URL intel</span><span class="sxs-lookup"><span data-stu-id="c1aa0-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="c1aa0-299">UEFI 扫描功能</span><span class="sxs-lookup"><span data-stu-id="c1aa0-299">UEFI scan capability</span></span>
- <span data-ttu-id="c1aa0-300">扩展更新日志记录</span><span class="sxs-lookup"><span data-stu-id="c1aa0-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="c1aa0-301">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-301">Known Issues</span></span>
<span data-ttu-id="c1aa0-302">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1aa0-303">2020 年 3 月 (平台：4.18.2003.8 |引擎：1.1.16900.2) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="c1aa0-304">&ensp;安全智能更新版本 **：1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="c1aa0-305">&ensp;已发布 **：2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="c1aa0-306">&ensp;平台 **：4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="c1aa0-307">&ensp;引擎 **：1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="c1aa0-308">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="c1aa0-309">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-309">What's new</span></span>

- <span data-ttu-id="c1aa0-310">添加到[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 限制选项</span><span class="sxs-lookup"><span data-stu-id="c1aa0-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="c1aa0-311">改进诊断功能</span><span class="sxs-lookup"><span data-stu-id="c1aa0-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="c1aa0-312">将安全智能超时 (5 分钟) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="c1aa0-313">扩展 AMSI 引擎内部日志功能</span><span class="sxs-lookup"><span data-stu-id="c1aa0-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="c1aa0-314">改进进程阻止通知</span><span class="sxs-lookup"><span data-stu-id="c1aa0-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c1aa0-315">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-315">Known Issues</span></span>
<span data-ttu-id="c1aa0-316">[**Fixed**]Microsoft Defender 防病毒扫描时跳过文件。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="c1aa0-317">2020 年 2 月 (平台： - |引擎：1.1.16800.2) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="c1aa0-318">&ensp;安全智能更新版本 **：1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="c1aa0-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="c1aa0-319">&ensp;发布时间 **：2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="c1aa0-320">&ensp;平台/客户端： **-**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="c1aa0-321">&ensp;引擎 **：1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="c1aa0-322">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="c1aa0-323">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="c1aa0-324">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-324">Known Issues</span></span>
<span data-ttu-id="c1aa0-325">无已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1aa0-326">2020 年 1 月 (平台：4.18.2001.10 |引擎：1.1.16700.2) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="c1aa0-327">安全智能更新版本 **：1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="c1aa0-328">发布时间 **：2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="c1aa0-329">平台/客户端 **：4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="c1aa0-330">引擎 **：1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="c1aa0-331">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="c1aa0-332">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-332">What's new</span></span>

- <span data-ttu-id="c1aa0-333">修复了 WS2016 上的 BSOD 与Exchange</span><span class="sxs-lookup"><span data-stu-id="c1aa0-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="c1aa0-334">当 TMP 重定向到网络路径时支持平台更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="c1aa0-335">平台和引擎版本已添加到 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="c1aa0-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="c1aa0-336">将紧急签名更新扩展到 [被动模式](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="c1aa0-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="c1aa0-337">修复 4.18.1911.3 挂起</span><span class="sxs-lookup"><span data-stu-id="c1aa0-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c1aa0-338">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-338">Known Issues</span></span>

<span data-ttu-id="c1aa0-339">[**修复**][使用新式待机](/windows-hardware/design/device-experiences/modern-standby)模式的设备可能会遇到与 Windows Defender 筛选器驱动程序的挂起，导致保护差距。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="c1aa0-340">受影响的计算机向客户显示尚未更新到最新的反恶意软件平台。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="c1aa0-341">此更新为：</span><span class="sxs-lookup"><span data-stu-id="c1aa0-341">This update is:</span></span>
> - <span data-ttu-id="c1aa0-342">运行较低版本的平台以支持 SHA2 的 RS1 设备需要;</span><span class="sxs-lookup"><span data-stu-id="c1aa0-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="c1aa0-343">对于有挂起问题的系统，具有重新启动标志;</span><span class="sxs-lookup"><span data-stu-id="c1aa0-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="c1aa0-344">在 2020 年 4 月重新发布，并且不会被更新的更新所取代，以保持将来的可用性;</span><span class="sxs-lookup"><span data-stu-id="c1aa0-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="c1aa0-345">因重启要求而分类为更新;和</span><span class="sxs-lookup"><span data-stu-id="c1aa0-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="c1aa0-346">仅提供与 Windows Update 一[起提供](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="c1aa0-347">2019 年 11 月 (平台：4.18.1911.3 |引擎：1.1.16600.7) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="c1aa0-348">安全智能更新版本 **：1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="c1aa0-349">发布时间 **：2019 年 12 月 7 日**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="c1aa0-350">平台 **：4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="c1aa0-351">引擎 **：1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="c1aa0-352">支持阶段： **不支持**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="c1aa0-353">最近更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-353">What's new</span></span>

- <span data-ttu-id="c1aa0-354">修复了 MpCmdRun 跟踪级别</span><span class="sxs-lookup"><span data-stu-id="c1aa0-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="c1aa0-355">修复了 WDFilter 版本信息</span><span class="sxs-lookup"><span data-stu-id="c1aa0-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="c1aa0-356">改进 PUA (通知) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="c1aa0-357">添加 MRT 日志以支持文件</span><span class="sxs-lookup"><span data-stu-id="c1aa0-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="c1aa0-358">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1aa0-358">Known Issues</span></span>
<span data-ttu-id="c1aa0-359">安装此更新后，设备需要跳转程序包 4.10.2001.10 才能更新到最新的平台版本。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="c1aa0-360">Microsoft Defender 防病毒平台支持</span><span class="sxs-lookup"><span data-stu-id="c1aa0-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="c1aa0-361">平台和引擎更新按月提供。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="c1aa0-362">若要完全受支持，请及时了解最新的平台更新。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="c1aa0-363">我们的支持结构是动态的，根据最新平台版本的可用性，将发展为两个阶段：</span><span class="sxs-lookup"><span data-stu-id="c1aa0-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="c1aa0-364">**安全和关键更新服务阶段** - 运行最新平台版本时，你将有资格接收反恶意软件平台的安全和关键更新。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="c1aa0-365">**技术支持 (仅在)** 阶段 - 发布新平台版本后，对早期版本 (N-2) 的支持将仅减少为技术支持。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="c1aa0-366">不再支持 N-2 之前的平台版本。\*</span><span class="sxs-lookup"><span data-stu-id="c1aa0-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="c1aa0-367">\*将继续为从 Windows 10 版本升级提供技术支持 (请参阅[Windows 10](#platform-version-included-with-windows-10-releases)版本中包含的平台版本) 到最新平台版本。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="c1aa0-368">在技术支持 (仅在) 阶段，商业上合理的支持事件将通过 Microsoft 客户服务 & 支持和 Microsoft 的托管支持产品/服务 (如 Premier Support) 提供。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="c1aa0-369">如果支持事件需要上报开发以进一步提供指导、需要非安全更新或需要安全更新，将要求客户升级到最新平台版本或中间 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="c1aa0-370">版本中包含的平台Windows 10版本</span><span class="sxs-lookup"><span data-stu-id="c1aa0-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="c1aa0-371">下表提供了最新 Microsoft Defender 防病毒 版本附带的 Microsoft Defender 防病毒 Windows 10 平台和引擎版本：</span><span class="sxs-lookup"><span data-stu-id="c1aa0-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="c1aa0-372">Windows 10发布</span><span class="sxs-lookup"><span data-stu-id="c1aa0-372">Windows 10 release</span></span>  |<span data-ttu-id="c1aa0-373">平台版本</span><span class="sxs-lookup"><span data-stu-id="c1aa0-373">Platform version</span></span>  |<span data-ttu-id="c1aa0-374">引擎版本</span><span class="sxs-lookup"><span data-stu-id="c1aa0-374">Engine version</span></span> |<span data-ttu-id="c1aa0-375">支持阶段</span><span class="sxs-lookup"><span data-stu-id="c1aa0-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="c1aa0-376">2004 (20H1/20H2) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="c1aa0-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="c1aa0-377">4.18.1909.6</span></span> |<span data-ttu-id="c1aa0-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="c1aa0-378">1.1.17000.2</span></span> | <span data-ttu-id="c1aa0-379">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1aa0-380">1909 (19H2) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-380">1909  (19H2)</span></span> |<span data-ttu-id="c1aa0-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="c1aa0-381">4.18.1902.5</span></span> |<span data-ttu-id="c1aa0-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="c1aa0-382">1.1.16700.3</span></span> | <span data-ttu-id="c1aa0-383">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1aa0-384">1903 (19H1) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-384">1903  (19H1)</span></span> |<span data-ttu-id="c1aa0-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="c1aa0-385">4.18.1902.5</span></span> |<span data-ttu-id="c1aa0-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="c1aa0-386">1.1.15600.4</span></span> | <span data-ttu-id="c1aa0-387">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1aa0-388">1809 (RS5) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-388">1809  (RS5)</span></span> |<span data-ttu-id="c1aa0-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="c1aa0-389">4.18.1807.18075</span></span> |<span data-ttu-id="c1aa0-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="c1aa0-390">1.1.15000.2</span></span> | <span data-ttu-id="c1aa0-391">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1aa0-392">1803 (RS4) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-392">1803  (RS4)</span></span> |<span data-ttu-id="c1aa0-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="c1aa0-393">4.13.17134.1</span></span> |<span data-ttu-id="c1aa0-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="c1aa0-394">1.1.14600.4</span></span> | <span data-ttu-id="c1aa0-395">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1aa0-396">1709 (RS3) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-396">1709  (RS3)</span></span> |<span data-ttu-id="c1aa0-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="c1aa0-397">4.12.16299.15</span></span> |<span data-ttu-id="c1aa0-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="c1aa0-398">1.1.14104.0</span></span> | <span data-ttu-id="c1aa0-399">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1aa0-400">1703 (RS2) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-400">1703  (RS2)</span></span> |<span data-ttu-id="c1aa0-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="c1aa0-401">4.11.15603.2</span></span> |<span data-ttu-id="c1aa0-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="c1aa0-402">1.1.13504.0</span></span> | <span data-ttu-id="c1aa0-403">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="c1aa0-404">1607 (RS1) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-404">1607 (RS1)</span></span> |<span data-ttu-id="c1aa0-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="c1aa0-405">4.10.14393.3683</span></span> |<span data-ttu-id="c1aa0-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="c1aa0-406">1.1.12805.0</span></span> | <span data-ttu-id="c1aa0-407">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="c1aa0-408">有关Windows 10的信息，请参阅生命周期[Windows表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="c1aa0-409">DISM 部署映像服务和管理 (更新) </span><span class="sxs-lookup"><span data-stu-id="c1aa0-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="c1aa0-410">我们建议使用最新的防病毒和反恶意软件更新更新 Windows 10 (Enterprise、Pro 和家庭版) 、Windows Server 2019 和 Windows Server 2016 操作系统安装映像。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="c1aa0-411">使操作系统安装映像保持最新有助于避免保护差距。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="c1aa0-412">有关详细信息，请参阅适用于操作系统[安装映像Windows Microsoft Defender 更新](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="c1aa0-413">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="c1aa0-413">1.1.2105.01</span></span></summary>

<span data-ttu-id="c1aa0-414">&ensp;程序包版本 **：1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="c1aa0-414">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="c1aa0-415">&ensp;平台版本 **：4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="c1aa0-415">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="c1aa0-416">&ensp;引擎版本 **：1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="c1aa0-417">&ensp;签名版本 **：1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-417">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1aa0-418">修补程序</span><span class="sxs-lookup"><span data-stu-id="c1aa0-418">Fixes</span></span>
- <span data-ttu-id="c1aa0-419">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1aa0-420">其他信息</span><span class="sxs-lookup"><span data-stu-id="c1aa0-420">Additional information</span></span>
- <span data-ttu-id="c1aa0-421">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1aa0-422">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="c1aa0-422">1.1.2104.01</span></span></summary>

<span data-ttu-id="c1aa0-423">&ensp;程序包版本 **：1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="c1aa0-423">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="c1aa0-424">&ensp;平台版本 **：4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="c1aa0-424">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="c1aa0-425">&ensp;引擎版本 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-425">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="c1aa0-426">&ensp;签名版本 **：1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-426">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1aa0-427">修补程序</span><span class="sxs-lookup"><span data-stu-id="c1aa0-427">Fixes</span></span>
- <span data-ttu-id="c1aa0-428">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1aa0-429">其他信息</span><span class="sxs-lookup"><span data-stu-id="c1aa0-429">Additional information</span></span>
- <span data-ttu-id="c1aa0-430">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1aa0-431">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="c1aa0-431">1.1.2103.01</span></span></summary>

<span data-ttu-id="c1aa0-432">&ensp;程序包版本 **：1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="c1aa0-432">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="c1aa0-433">&ensp;平台版本 **：4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="c1aa0-433">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="c1aa0-434">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="c1aa0-435">&ensp;签名版本 **：1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-435">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1aa0-436">修补程序</span><span class="sxs-lookup"><span data-stu-id="c1aa0-436">Fixes</span></span>
- <span data-ttu-id="c1aa0-437">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1aa0-438">其他信息</span><span class="sxs-lookup"><span data-stu-id="c1aa0-438">Additional information</span></span>
- <span data-ttu-id="c1aa0-439">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1aa0-440">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="c1aa0-440">1.1.2102.03</span></span></summary>

<span data-ttu-id="c1aa0-441">&ensp;程序包版本 **：1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="c1aa0-441">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="c1aa0-442">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="c1aa0-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="c1aa0-443">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="c1aa0-444">&ensp;签名版本 **：1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-444">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1aa0-445">修补程序</span><span class="sxs-lookup"><span data-stu-id="c1aa0-445">Fixes</span></span>
- <span data-ttu-id="c1aa0-446">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1aa0-447">其他信息</span><span class="sxs-lookup"><span data-stu-id="c1aa0-447">Additional information</span></span>
- <span data-ttu-id="c1aa0-448">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1aa0-449">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="c1aa0-449">1.1.2101.02</span></span></summary>

<span data-ttu-id="c1aa0-450">&ensp;程序包版本 **：1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="c1aa0-450">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="c1aa0-451">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="c1aa0-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="c1aa0-452">&ensp;引擎版本 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-452">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="c1aa0-453">&ensp;签名版本 **：1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-453">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1aa0-454">修补程序</span><span class="sxs-lookup"><span data-stu-id="c1aa0-454">Fixes</span></span>
- <span data-ttu-id="c1aa0-455">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1aa0-456">其他信息</span><span class="sxs-lookup"><span data-stu-id="c1aa0-456">Additional information</span></span>
- <span data-ttu-id="c1aa0-457">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1aa0-458">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="c1aa0-458">1.1.2012.01</span></span></summary>

<span data-ttu-id="c1aa0-459">&ensp;程序包版本 **：1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="c1aa0-459">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="c1aa0-460">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="c1aa0-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="c1aa0-461">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c1aa0-462">&ensp;签名版本 **：1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-462">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1aa0-463">修补程序</span><span class="sxs-lookup"><span data-stu-id="c1aa0-463">Fixes</span></span>
- <span data-ttu-id="c1aa0-464">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1aa0-465">其他信息</span><span class="sxs-lookup"><span data-stu-id="c1aa0-465">Additional information</span></span>
- <span data-ttu-id="c1aa0-466">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1aa0-467">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="c1aa0-467">1.1.2011.02</span></span></summary>

<span data-ttu-id="c1aa0-468">&ensp;程序包版本 **：1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="c1aa0-468">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="c1aa0-469">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="c1aa0-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="c1aa0-470">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c1aa0-471">&ensp;签名版本 **：1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-471">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1aa0-472">修补程序</span><span class="sxs-lookup"><span data-stu-id="c1aa0-472">Fixes</span></span>
- <span data-ttu-id="c1aa0-473">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1aa0-474">其他信息</span><span class="sxs-lookup"><span data-stu-id="c1aa0-474">Additional information</span></span>
- <span data-ttu-id="c1aa0-475">刷新Microsoft Defender 防病毒签名</span><span class="sxs-lookup"><span data-stu-id="c1aa0-475">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1aa0-476">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="c1aa0-476">1.1.2011.01</span></span></summary>

<span data-ttu-id="c1aa0-477">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="c1aa0-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="c1aa0-478">&ensp;平台版本 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-478">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="c1aa0-479">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="c1aa0-480">&ensp;签名版本 **：1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-480">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1aa0-481">修补程序</span><span class="sxs-lookup"><span data-stu-id="c1aa0-481">Fixes</span></span>
- <span data-ttu-id="c1aa0-482">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1aa0-483">其他信息</span><span class="sxs-lookup"><span data-stu-id="c1aa0-483">Additional information</span></span>
- <span data-ttu-id="c1aa0-484">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-484">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="c1aa0-485">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="c1aa0-485">1.1.2009.10</span></span></summary>

<span data-ttu-id="c1aa0-486">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="c1aa0-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="c1aa0-487">&ensp;平台版本 **：4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="c1aa0-487">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="c1aa0-488">&ensp;引擎版本 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-488">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="c1aa0-489">&ensp;签名版本 **：1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="c1aa0-489">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="c1aa0-490">修补程序</span><span class="sxs-lookup"><span data-stu-id="c1aa0-490">Fixes</span></span>
- <span data-ttu-id="c1aa0-491">无</span><span class="sxs-lookup"><span data-stu-id="c1aa0-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="c1aa0-492">其他信息</span><span class="sxs-lookup"><span data-stu-id="c1aa0-492">Additional information</span></span>
- <span data-ttu-id="c1aa0-493">添加了对 Windows 10 RS1 或更高版本操作系统安装映像的支持。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-493">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="c1aa0-494">其他资源</span><span class="sxs-lookup"><span data-stu-id="c1aa0-494">Additional resources</span></span>

| <span data-ttu-id="c1aa0-495">文章</span><span class="sxs-lookup"><span data-stu-id="c1aa0-495">Article</span></span> | <span data-ttu-id="c1aa0-496">说明</span><span class="sxs-lookup"><span data-stu-id="c1aa0-496">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="c1aa0-497">适用于操作系统安装映像Windows Microsoft Defender 更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-497">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="c1aa0-498">查看适用于操作系统安装映像的反恶意软件更新程序包 (WIM 和 VHD 文件) 。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-498">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="c1aa0-499">获取 Microsoft Defender 防病毒、Windows 10 (Enterprise、Pro、家庭版) 、Windows Server 2019 Windows Server 2016更新。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-499">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="c1aa0-500">管理保护更新的下载和应用方式</span><span class="sxs-lookup"><span data-stu-id="c1aa0-500">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="c1aa0-501">保护更新可以通过多个源提供。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-501">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="c1aa0-502">管理何时应下载和应用保护更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-502">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="c1aa0-503">你可以计划应下载保护更新的时间。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-503">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="c1aa0-504">管理过期终结点的更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-504">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="c1aa0-505">如果终结点错过更新或计划扫描，可以在用户下次登录时强制进行更新或扫描。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-505">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="c1aa0-506">管理基于事件的强制更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-506">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="c1aa0-507">你可以将保护更新设置为在启动时或在某些云提供的保护事件之后下载。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-507">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="c1aa0-508">管理移动设备和虚拟机 （VM） 的更新</span><span class="sxs-lookup"><span data-stu-id="c1aa0-508">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="c1aa0-509">你可以指定对移动设备和虚拟机特别有用的设置，例如是否应该使用电池电源进行更新。</span><span class="sxs-lookup"><span data-stu-id="c1aa0-509">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
