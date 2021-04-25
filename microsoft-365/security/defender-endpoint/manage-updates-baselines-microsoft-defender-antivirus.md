---
title: 管理 Microsoft Defender 防病毒更新和应用基线
description: 管理 Microsoft Defender 防病毒接收保护和产品更新方式。
keywords: 更新， 安全基线， 保护， 计划更新， 强制更新， 移动更新， wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ae17aa6e2cb0cefd460ef0db0730570af8c84bb8
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995029"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="42334-104">管理 Microsoft Defender 防病毒更新和应用基线</span><span class="sxs-lookup"><span data-stu-id="42334-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="42334-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="42334-105">**Applies to:**</span></span>

- [<span data-ttu-id="42334-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="42334-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="42334-107">Microsoft Defender 防病毒软件</span><span class="sxs-lookup"><span data-stu-id="42334-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="42334-108">有两种类型的更新与使 Microsoft Defender 防病毒保持最新有关：</span><span class="sxs-lookup"><span data-stu-id="42334-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="42334-109">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="42334-109">Security intelligence updates</span></span>
- <span data-ttu-id="42334-110">产品更新</span><span class="sxs-lookup"><span data-stu-id="42334-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42334-111">使 Microsoft Defender 防病毒保持最新至关重要，可确保你的设备具有防止新的恶意软件和攻击技术所需的最新技术和功能。</span><span class="sxs-lookup"><span data-stu-id="42334-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="42334-112">确保更新防病毒保护，即使 Microsoft Defender 防病毒在被动 [模式下运行](./microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="42334-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="42334-113">若要查看最新的引擎、平台和签名日期，请访问 Microsoft Defender 防病毒和其他 Microsoft 反 [恶意软件的安全智能更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="42334-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="42334-114">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="42334-114">Security intelligence updates</span></span>

<span data-ttu-id="42334-115">Microsoft Defender 防病毒 [使用云](cloud-protection-microsoft-defender-antivirus.md) 提供的保护 (也称为 Microsoft 高级保护服务或 MAPS) 并定期下载安全智能更新以提供保护。</span><span class="sxs-lookup"><span data-stu-id="42334-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="42334-116">更新以以下 KB 编号发布：</span><span class="sxs-lookup"><span data-stu-id="42334-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="42334-117">Microsoft Defender 防病毒：KB2267602</span><span class="sxs-lookup"><span data-stu-id="42334-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="42334-118">System Center Endpoint Protection：KB2461484</span><span class="sxs-lookup"><span data-stu-id="42334-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="42334-119">云提供的保护始终打开，并且需要与 Internet 的活动连接以正常运行。</span><span class="sxs-lookup"><span data-stu-id="42334-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="42334-120">安全智能更新按计划节奏进行， (策略策略配置) 。</span><span class="sxs-lookup"><span data-stu-id="42334-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="42334-121">有关详细信息，请参阅在 Microsoft Defender 防病毒中使用 Microsoft 云 [提供的保护](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="42334-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="42334-122">有关最近安全智能更新的列表，请参阅 Microsoft Defender 防病毒和其他 Microsoft 反 [恶意软件的安全智能更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="42334-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="42334-123">引擎更新包含在安全智能更新中，并按月发布。</span><span class="sxs-lookup"><span data-stu-id="42334-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="42334-124">产品更新</span><span class="sxs-lookup"><span data-stu-id="42334-124">Product updates</span></span>

<span data-ttu-id="42334-125">Microsoft Defender 防病毒需要每月更新 [ (KB4052623](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform))  (称为平台更新 *) ，* 并且将接收 Windows 10 版本旁边的主要功能更新。</span><span class="sxs-lookup"><span data-stu-id="42334-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="42334-126">可以通过以下方法之一管理更新的分发：</span><span class="sxs-lookup"><span data-stu-id="42334-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="42334-127">Windows Server Update Service (WSUS) </span><span class="sxs-lookup"><span data-stu-id="42334-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="42334-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="42334-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="42334-129">用于将 Microsoft 和 Windows 更新部署到网络中终结点的常用方法。</span><span class="sxs-lookup"><span data-stu-id="42334-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="42334-130">有关详细信息，请参阅管理 [Microsoft Defender 防病毒保护更新的源](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="42334-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="42334-131">每月更新会分期发布，从而在 Window Server Update Services 中显示 [多个程序包](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="42334-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="42334-132">每月平台和引擎版本</span><span class="sxs-lookup"><span data-stu-id="42334-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="42334-133">若要了解如何更新或安装平台更新，请参阅反恶意软件Windows Defender [更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="42334-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="42334-134">我们的所有更新都包含</span><span class="sxs-lookup"><span data-stu-id="42334-134">All our updates contain</span></span> 
- <span data-ttu-id="42334-135">性能改进;</span><span class="sxs-lookup"><span data-stu-id="42334-135">performance improvements;</span></span>
- <span data-ttu-id="42334-136">可服务性改进;和</span><span class="sxs-lookup"><span data-stu-id="42334-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="42334-137">集成改进 (云、Microsoft 365 Defender) 。</span><span class="sxs-lookup"><span data-stu-id="42334-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="42334-138">2021 年 3 月 (平台：4.18.2103.7 |引擎：1.1.18000.5) </span><span class="sxs-lookup"><span data-stu-id="42334-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="42334-139">&ensp;安全智能更新版本 **：1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="42334-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="42334-140">&ensp;发布时间 **：2021 年 4 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="42334-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="42334-141">&ensp;平台 **：4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="42334-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="42334-142">&ensp;引擎 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="42334-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="42334-143">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="42334-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="42334-144">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-144">What's new</span></span>

- <span data-ttu-id="42334-145">对行为监控引擎的改进</span><span class="sxs-lookup"><span data-stu-id="42334-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="42334-146">扩展的网络暴力攻击缓解措施</span><span class="sxs-lookup"><span data-stu-id="42334-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="42334-147">启用防篡改保护 [时的其他失败](prevent-changes-to-security-settings-with-tamper-protection.md) 篡改尝试事件生成</span><span class="sxs-lookup"><span data-stu-id="42334-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="42334-148">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-148">Known Issues</span></span>
<span data-ttu-id="42334-149">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="42334-150">2021 年 2 月 (平台：4.18.2102.3 |引擎：1.1.17900.7) </span><span class="sxs-lookup"><span data-stu-id="42334-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="42334-151">&ensp;安全智能更新版本 **：1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="42334-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="42334-152">&ensp;已发布 **：2021 年 3 月 9 日**</span><span class="sxs-lookup"><span data-stu-id="42334-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="42334-153">&ensp;平台 **：4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="42334-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="42334-154">&ensp;引擎 **：1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="42334-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="42334-155">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="42334-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="42334-156">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-156">What's new</span></span>

- <span data-ttu-id="42334-157">通过防篡改保护 [改进了服务恢复](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="42334-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="42334-158">扩展防篡改保护作用域</span><span class="sxs-lookup"><span data-stu-id="42334-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="42334-159">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-159">Known Issues</span></span>
<span data-ttu-id="42334-160">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="42334-161">2021 年 1 月 (平台：4.18.2101.9 |引擎：1.1.17800.5) </span><span class="sxs-lookup"><span data-stu-id="42334-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="42334-162">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="42334-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="42334-163">&ensp;发布时间 **：2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="42334-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="42334-164">&ensp;平台 **：4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="42334-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="42334-165">&ensp;引擎 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="42334-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="42334-166">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="42334-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="42334-167">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-167">What's new</span></span>

- <span data-ttu-id="42334-168">Shellcode 攻击检测改进</span><span class="sxs-lookup"><span data-stu-id="42334-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="42334-169">提高了凭据窃取尝试的可见性</span><span class="sxs-lookup"><span data-stu-id="42334-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="42334-170">Microsoft Defender 防病毒服务中的反威胁功能的改进</span><span class="sxs-lookup"><span data-stu-id="42334-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="42334-171">改进了对 x64 ARM的支持</span><span class="sxs-lookup"><span data-stu-id="42334-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="42334-172">修复：实时保护执行初始检测后，EDR 阻止通知仍保留在威胁历史记录中</span><span class="sxs-lookup"><span data-stu-id="42334-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="42334-173">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-173">Known Issues</span></span>
<span data-ttu-id="42334-174">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="42334-175">旧版本更新：仅技术升级支持</span><span class="sxs-lookup"><span data-stu-id="42334-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="42334-176">发布新程序包版本后，仅对前两个版本的支持减少到技术支持。</span><span class="sxs-lookup"><span data-stu-id="42334-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="42334-177">低于本部分中列出的版本，并且仅提供用于技术升级支持的版本。</span><span class="sxs-lookup"><span data-stu-id="42334-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="42334-178">2020 年 11 月 (平台：4.18.2011.6 |引擎：1.1.17700.4) </span><span class="sxs-lookup"><span data-stu-id="42334-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="42334-179">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="42334-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="42334-180">&ensp;发布时间 **：2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="42334-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="42334-181">&ensp;平台 **：4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="42334-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="42334-182">&ensp;引擎 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="42334-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="42334-183">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="42334-183">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="42334-184">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-184">What's new</span></span>

- <span data-ttu-id="42334-185">改进 [的 SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 状态支持日志记录</span><span class="sxs-lookup"><span data-stu-id="42334-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="42334-186">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-186">Known Issues</span></span>
<span data-ttu-id="42334-187">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="42334-188">2020 年 10 月 (平台：4.18.2010.7 |引擎：1.1.17600.5) </span><span class="sxs-lookup"><span data-stu-id="42334-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="42334-189">&ensp;安全智能更新版本 **：1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="42334-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="42334-190">&ensp;发布时间 **：2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="42334-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="42334-191">&ensp;平台 **：4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="42334-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="42334-192">&ensp;引擎 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="42334-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="42334-193">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="42334-193">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="42334-194">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-194">What's new</span></span>

- <span data-ttu-id="42334-195">特殊威胁类别的新说明</span><span class="sxs-lookup"><span data-stu-id="42334-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="42334-196">改进的模拟功能</span><span class="sxs-lookup"><span data-stu-id="42334-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="42334-197">改进了主机地址允许/阻止功能</span><span class="sxs-lookup"><span data-stu-id="42334-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="42334-198">Defender CSP 中用于忽略本地用户排除项合并的新选项</span><span class="sxs-lookup"><span data-stu-id="42334-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="42334-199">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-199">Known Issues</span></span>

<span data-ttu-id="42334-200">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="42334-201">2020 年 9 月 (平台：4.18.2009.7 |引擎：1.1.17500.4) </span><span class="sxs-lookup"><span data-stu-id="42334-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="42334-202">&ensp;安全智能更新版本 **：1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="42334-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="42334-203">&ensp;发布时间 **：2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="42334-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="42334-204">&ensp;平台 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="42334-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="42334-205">&ensp;引擎 **：1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="42334-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="42334-206">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="42334-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="42334-207">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-207">What's new</span></span>

- <span data-ttu-id="42334-208">需要管理员权限才能还原隔离中的文件</span><span class="sxs-lookup"><span data-stu-id="42334-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="42334-209">XML 格式事件现在受支持</span><span class="sxs-lookup"><span data-stu-id="42334-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="42334-210">忽略排除合并的云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="42334-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="42334-211">用于：</span><span class="sxs-lookup"><span data-stu-id="42334-211">New management interfaces for:</span></span>
   - <span data-ttu-id="42334-212">UDP 检查</span><span class="sxs-lookup"><span data-stu-id="42334-212">UDP Inspection</span></span>
   - <span data-ttu-id="42334-213">Server 2019 上的网络保护</span><span class="sxs-lookup"><span data-stu-id="42334-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="42334-214">网络保护的 IP 地址排除项</span><span class="sxs-lookup"><span data-stu-id="42334-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="42334-215">改进了对 TPM 测量的可见性</span><span class="sxs-lookup"><span data-stu-id="42334-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="42334-216">改进的 Office VBA 模块扫描</span><span class="sxs-lookup"><span data-stu-id="42334-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="42334-217">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-217">Known Issues</span></span>

<span data-ttu-id="42334-218">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="42334-219">2020 年 8 月 (平台：4.18.2008.9 |引擎：1.1.17400.5) </span><span class="sxs-lookup"><span data-stu-id="42334-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="42334-220">&ensp;安全智能更新版本 **：1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="42334-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="42334-221">&ensp;发布时间 **：2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="42334-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="42334-222">&ensp;平台 **：4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="42334-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="42334-223">&ensp;引擎 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="42334-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="42334-224">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="42334-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="42334-225">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-225">What's new</span></span>

- <span data-ttu-id="42334-226">添加更多遥测事件</span><span class="sxs-lookup"><span data-stu-id="42334-226">Add more telemetry events</span></span>
- <span data-ttu-id="42334-227">改进了扫描事件遥测</span><span class="sxs-lookup"><span data-stu-id="42334-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="42334-228">改进了内存扫描行为监视</span><span class="sxs-lookup"><span data-stu-id="42334-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="42334-229">改进的宏流扫描</span><span class="sxs-lookup"><span data-stu-id="42334-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="42334-230">已 `AMRunningMode` 添加到 Get-MpComputerStatus PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="42334-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="42334-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="42334-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="42334-232">Microsoft Defender 防病毒在检测到其他防病毒程序时自动关闭自身。</span><span class="sxs-lookup"><span data-stu-id="42334-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="42334-233">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-233">Known Issues</span></span>
<span data-ttu-id="42334-234">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="42334-235">2020 年 7 月 (平台：4.18.2007.8 |引擎：1.1.17300.4) </span><span class="sxs-lookup"><span data-stu-id="42334-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="42334-236">&ensp;安全智能更新版本 **：1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="42334-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="42334-237">&ensp;发布时间 **：2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="42334-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="42334-238">&ensp;平台 **：4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="42334-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="42334-239">&ensp;引擎 **：1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="42334-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="42334-240">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="42334-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="42334-241">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-241">What's new</span></span>

- <span data-ttu-id="42334-242">改进的 BITS 遥测</span><span class="sxs-lookup"><span data-stu-id="42334-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="42334-243">改进的验证码代码签名证书验证</span><span class="sxs-lookup"><span data-stu-id="42334-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="42334-244">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-244">Known Issues</span></span>
<span data-ttu-id="42334-245">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="42334-246">2020 年 6 月 (平台：4.18.2006.10 |引擎：1.1.17200.2) </span><span class="sxs-lookup"><span data-stu-id="42334-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="42334-247">&ensp;安全智能更新版本 **：1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="42334-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="42334-248">&ensp;发布时间 **：2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="42334-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="42334-249">&ensp;平台 **：4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="42334-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="42334-250">&ensp;引擎 **：1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="42334-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="42334-251">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="42334-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="42334-252">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-252">What's new</span></span>

- <span data-ttu-id="42334-253">指定支持 [日志的位置的可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="42334-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="42334-254">在被动模式下跳过主动的捕获扫描。</span><span class="sxs-lookup"><span data-stu-id="42334-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="42334-255">允许 Defender 更新按流量计费的连接</span><span class="sxs-lookup"><span data-stu-id="42334-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="42334-256">修复了禁用缓存时的性能调整</span><span class="sxs-lookup"><span data-stu-id="42334-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="42334-257">修复了注册表查询</span><span class="sxs-lookup"><span data-stu-id="42334-257">Fixed registry query</span></span> 
- <span data-ttu-id="42334-258">修复了 ADMX 中的扫描时间随机化</span><span class="sxs-lookup"><span data-stu-id="42334-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="42334-259">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-259">Known Issues</span></span>
<span data-ttu-id="42334-260">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="42334-261">2020 年 5 月 (平台：4.18.2005.4 |引擎：1.1.17100.2) </span><span class="sxs-lookup"><span data-stu-id="42334-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="42334-262">&ensp;安全智能更新版本 **：1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="42334-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="42334-263">&ensp;发布时间 **：2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="42334-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="42334-264">&ensp;平台 **：4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="42334-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="42334-265">&ensp;引擎 **：1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="42334-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="42334-266">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="42334-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="42334-267">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-267">What's new</span></span>

- <span data-ttu-id="42334-268">改进了扫描事件的日志记录</span><span class="sxs-lookup"><span data-stu-id="42334-268">Improved logging for scan events</span></span>
- <span data-ttu-id="42334-269">改进了用户模式崩溃处理。</span><span class="sxs-lookup"><span data-stu-id="42334-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="42334-270">添加了防篡改保护的事件跟踪</span><span class="sxs-lookup"><span data-stu-id="42334-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="42334-271">修复了 AMSI 示例提交</span><span class="sxs-lookup"><span data-stu-id="42334-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="42334-272">修复了 AMSI 云阻止</span><span class="sxs-lookup"><span data-stu-id="42334-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="42334-273">修复了安全更新安装日志</span><span class="sxs-lookup"><span data-stu-id="42334-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="42334-274">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-274">Known Issues</span></span>
<span data-ttu-id="42334-275">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="42334-276">2020 年 4 月 (平台：4.18.2004.6 |引擎：1.1.17000.2) </span><span class="sxs-lookup"><span data-stu-id="42334-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="42334-277">&ensp;安全智能更新版本 **：1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="42334-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="42334-278">&ensp;发布时间 **：2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="42334-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="42334-279">&ensp;平台 **：4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="42334-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="42334-280">&ensp;引擎 **：1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="42334-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="42334-281">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="42334-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="42334-282">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-282">What's new</span></span>
- <span data-ttu-id="42334-283">WDfilter 改进</span><span class="sxs-lookup"><span data-stu-id="42334-283">WDfilter improvements</span></span>
- <span data-ttu-id="42334-284">向攻击面减少检测事件添加更多可操作事件数据</span><span class="sxs-lookup"><span data-stu-id="42334-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="42334-285">诊断数据和 WMI 中的固定版本信息</span><span class="sxs-lookup"><span data-stu-id="42334-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="42334-286">修复了平台更新后 UI 中的平台版本不正确</span><span class="sxs-lookup"><span data-stu-id="42334-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="42334-287">用于无文件威胁防护的动态 URL intel</span><span class="sxs-lookup"><span data-stu-id="42334-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="42334-288">UEFI 扫描功能</span><span class="sxs-lookup"><span data-stu-id="42334-288">UEFI scan capability</span></span>
- <span data-ttu-id="42334-289">扩展更新日志记录</span><span class="sxs-lookup"><span data-stu-id="42334-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="42334-290">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-290">Known Issues</span></span>
<span data-ttu-id="42334-291">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="42334-292">2020 年 3 月 (平台：4.18.2003.8 |引擎：1.1.16900.2) </span><span class="sxs-lookup"><span data-stu-id="42334-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="42334-293">&ensp;安全智能更新版本 **：1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="42334-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="42334-294">&ensp;已发布 **：2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="42334-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="42334-295">&ensp;平台 **：4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="42334-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="42334-296">&ensp;引擎 **：1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="42334-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="42334-297">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="42334-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="42334-298">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-298">What's new</span></span>

- <span data-ttu-id="42334-299">添加到[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 限制选项</span><span class="sxs-lookup"><span data-stu-id="42334-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="42334-300">改进诊断功能</span><span class="sxs-lookup"><span data-stu-id="42334-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="42334-301">将安全智能超时 (5 分钟) </span><span class="sxs-lookup"><span data-stu-id="42334-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="42334-302">扩展 AMSI 引擎内部日志功能</span><span class="sxs-lookup"><span data-stu-id="42334-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="42334-303">改进进程阻止通知</span><span class="sxs-lookup"><span data-stu-id="42334-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="42334-304">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-304">Known Issues</span></span>
<span data-ttu-id="42334-305">[**Fixed**]Microsoft Defender 防病毒在运行扫描时跳过文件。</span><span class="sxs-lookup"><span data-stu-id="42334-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="42334-306">2020 年 2 月 (平台： - |引擎：1.1.16800.2) </span><span class="sxs-lookup"><span data-stu-id="42334-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="42334-307">&ensp;安全智能更新版本 **：1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="42334-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="42334-308">&ensp;发布时间 **：2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="42334-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="42334-309">&ensp;平台/客户端： **-**</span><span class="sxs-lookup"><span data-stu-id="42334-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="42334-310">&ensp;引擎 **：1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="42334-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="42334-311">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="42334-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="42334-312">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="42334-313">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-313">Known Issues</span></span>
<span data-ttu-id="42334-314">无已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="42334-315">2020 年 1 月 (平台：4.18.2001.10 |引擎：1.1.16700.2) </span><span class="sxs-lookup"><span data-stu-id="42334-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="42334-316">安全智能更新版本 **：1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="42334-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="42334-317">发布时间 **：2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="42334-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="42334-318">平台/客户端 **：4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="42334-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="42334-319">引擎 **：1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="42334-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="42334-320">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="42334-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="42334-321">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-321">What's new</span></span>

- <span data-ttu-id="42334-322">WS2016 和 Exchange 上的固定 BSOD</span><span class="sxs-lookup"><span data-stu-id="42334-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="42334-323">当 TMP 重定向到网络路径时支持平台更新</span><span class="sxs-lookup"><span data-stu-id="42334-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="42334-324">平台和引擎版本已添加到 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="42334-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="42334-325">将紧急签名更新扩展到 [被动模式](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="42334-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="42334-326">修复 4.18.1911.3 挂起</span><span class="sxs-lookup"><span data-stu-id="42334-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="42334-327">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-327">Known Issues</span></span>

<span data-ttu-id="42334-328">[**修复**] 使用现代待机模式 [的设备](/windows-hardware/design/device-experiences/modern-standby) 可能会遇到与Windows Defender筛选器驱动程序的挂起，导致保护间隙。</span><span class="sxs-lookup"><span data-stu-id="42334-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="42334-329">受影响的计算机向客户显示尚未更新到最新的反恶意软件平台。</span><span class="sxs-lookup"><span data-stu-id="42334-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="42334-330">此更新为：</span><span class="sxs-lookup"><span data-stu-id="42334-330">This update is:</span></span>
> - <span data-ttu-id="42334-331">运行较低版本的平台以支持 SHA2 的 RS1 设备需要;</span><span class="sxs-lookup"><span data-stu-id="42334-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="42334-332">对于有挂起问题的系统，具有重新启动标志;</span><span class="sxs-lookup"><span data-stu-id="42334-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="42334-333">在 2020 年 4 月重新发布，并且不会被更新的更新所取代，以保持将来的可用性;</span><span class="sxs-lookup"><span data-stu-id="42334-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="42334-334">因重启要求而分类为更新;和</span><span class="sxs-lookup"><span data-stu-id="42334-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="42334-335">仅与 Windows 更新 [一起提供](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="42334-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="42334-336">2019 年 11 月 (平台：4.18.1911.3 |引擎：1.1.16600.7) </span><span class="sxs-lookup"><span data-stu-id="42334-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="42334-337">安全智能更新版本 **：1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="42334-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="42334-338">发布时间 **：2019 年 12 月 7 日**</span><span class="sxs-lookup"><span data-stu-id="42334-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="42334-339">平台 **：4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="42334-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="42334-340">引擎 **：1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="42334-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="42334-341">支持阶段： **不支持**</span><span class="sxs-lookup"><span data-stu-id="42334-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="42334-342">最近更新</span><span class="sxs-lookup"><span data-stu-id="42334-342">What's new</span></span>

- <span data-ttu-id="42334-343">修复了 MpCmdRun 跟踪级别</span><span class="sxs-lookup"><span data-stu-id="42334-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="42334-344">修复了 WDFilter 版本信息</span><span class="sxs-lookup"><span data-stu-id="42334-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="42334-345">改进 PUA (通知) </span><span class="sxs-lookup"><span data-stu-id="42334-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="42334-346">添加 MRT 日志以支持文件</span><span class="sxs-lookup"><span data-stu-id="42334-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="42334-347">已知问题</span><span class="sxs-lookup"><span data-stu-id="42334-347">Known Issues</span></span>
<span data-ttu-id="42334-348">安装此更新后，设备需要跳转程序包 4.10.2001.10 才能更新到最新的平台版本。</span><span class="sxs-lookup"><span data-stu-id="42334-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="42334-349">Microsoft Defender 防病毒平台支持</span><span class="sxs-lookup"><span data-stu-id="42334-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="42334-350">平台和引擎更新按月提供。</span><span class="sxs-lookup"><span data-stu-id="42334-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="42334-351">若要完全受支持，请及时了解最新的平台更新。</span><span class="sxs-lookup"><span data-stu-id="42334-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="42334-352">我们的支持结构是动态的，根据最新平台版本的可用性，将发展为两个阶段：</span><span class="sxs-lookup"><span data-stu-id="42334-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="42334-353">**安全和关键更新服务阶段** - 运行最新平台版本时，你将有资格接收反恶意软件平台的安全和关键更新。</span><span class="sxs-lookup"><span data-stu-id="42334-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="42334-354">**技术支持 (仅在)** 阶段 - 发布新平台版本后，对早期版本 (N-2) 的支持将仅减少为技术支持。</span><span class="sxs-lookup"><span data-stu-id="42334-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="42334-355">不再支持 N-2 之前的平台版本。\*</span><span class="sxs-lookup"><span data-stu-id="42334-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="42334-356">\* 将继续为从 Windows 10 版本升级提供技术支持 (请参阅 [Windows 10](#platform-version-included-with-windows-10-releases) 版本) 到最新平台版本的平台版本。</span><span class="sxs-lookup"><span data-stu-id="42334-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="42334-357">在技术支持 (仅在) 阶段，商业上合理的支持事件将通过 Microsoft 客户服务 & 支持和 Microsoft 的托管支持产品/服务 (如 Premier Support) 提供。</span><span class="sxs-lookup"><span data-stu-id="42334-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="42334-358">如果支持事件需要上报开发以进一步提供指导、需要非安全更新或需要安全更新，将要求客户升级到最新平台版本或中间 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="42334-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="42334-359">Windows 10 版本中包含的平台版本</span><span class="sxs-lookup"><span data-stu-id="42334-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="42334-360">下表提供了最新 Windows 10 版本附带的 Microsoft Defender 防病毒平台和引擎版本：</span><span class="sxs-lookup"><span data-stu-id="42334-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="42334-361">Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="42334-361">Windows 10 release</span></span>  |<span data-ttu-id="42334-362">平台版本</span><span class="sxs-lookup"><span data-stu-id="42334-362">Platform version</span></span>  |<span data-ttu-id="42334-363">引擎版本</span><span class="sxs-lookup"><span data-stu-id="42334-363">Engine version</span></span> |<span data-ttu-id="42334-364">支持阶段</span><span class="sxs-lookup"><span data-stu-id="42334-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="42334-365">2004 (20H1/20H2) </span><span class="sxs-lookup"><span data-stu-id="42334-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="42334-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="42334-366">4.18.1909.6</span></span> |<span data-ttu-id="42334-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="42334-367">1.1.17000.2</span></span> | <span data-ttu-id="42334-368">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="42334-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="42334-369">1909 (19H2) </span><span class="sxs-lookup"><span data-stu-id="42334-369">1909  (19H2)</span></span> |<span data-ttu-id="42334-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="42334-370">4.18.1902.5</span></span> |<span data-ttu-id="42334-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="42334-371">1.1.16700.3</span></span> | <span data-ttu-id="42334-372">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="42334-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="42334-373">1903 (19H1) </span><span class="sxs-lookup"><span data-stu-id="42334-373">1903  (19H1)</span></span> |<span data-ttu-id="42334-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="42334-374">4.18.1902.5</span></span> |<span data-ttu-id="42334-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="42334-375">1.1.15600.4</span></span> | <span data-ttu-id="42334-376">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="42334-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="42334-377">1809 (RS5) </span><span class="sxs-lookup"><span data-stu-id="42334-377">1809  (RS5)</span></span> |<span data-ttu-id="42334-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="42334-378">4.18.1807.18075</span></span> |<span data-ttu-id="42334-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="42334-379">1.1.15000.2</span></span> | <span data-ttu-id="42334-380">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="42334-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="42334-381">1803 (RS4) </span><span class="sxs-lookup"><span data-stu-id="42334-381">1803  (RS4)</span></span> |<span data-ttu-id="42334-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="42334-382">4.13.17134.1</span></span> |<span data-ttu-id="42334-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="42334-383">1.1.14600.4</span></span> | <span data-ttu-id="42334-384">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="42334-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="42334-385">1709 (RS3) </span><span class="sxs-lookup"><span data-stu-id="42334-385">1709  (RS3)</span></span> |<span data-ttu-id="42334-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="42334-386">4.12.16299.15</span></span> |<span data-ttu-id="42334-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="42334-387">1.1.14104.0</span></span> | <span data-ttu-id="42334-388">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="42334-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="42334-389">1703 (RS2) </span><span class="sxs-lookup"><span data-stu-id="42334-389">1703  (RS2)</span></span> |<span data-ttu-id="42334-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="42334-390">4.11.15603.2</span></span> |<span data-ttu-id="42334-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="42334-391">1.1.13504.0</span></span> | <span data-ttu-id="42334-392">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="42334-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="42334-393">1607 (RS1) </span><span class="sxs-lookup"><span data-stu-id="42334-393">1607 (RS1)</span></span> |<span data-ttu-id="42334-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="42334-394">4.10.14393.3683</span></span> |<span data-ttu-id="42334-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="42334-395">1.1.12805.0</span></span> | <span data-ttu-id="42334-396">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="42334-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="42334-397">有关 Windows 10 版本信息，请参阅 [Windows 生命周期事实数据表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="42334-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="42334-398">DISM 部署映像服务和管理 (更新) </span><span class="sxs-lookup"><span data-stu-id="42334-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="42334-399">我们建议使用最新的防病毒和反恶意软件更新更新 Windows 10 (企业版、专业版和家庭版) 、Windows Server 2019 和 Windows Server 2016 操作系统安装映像。</span><span class="sxs-lookup"><span data-stu-id="42334-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="42334-400">使操作系统安装映像保持最新有助于避免保护差距。</span><span class="sxs-lookup"><span data-stu-id="42334-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="42334-401">有关详细信息，请参阅 [Windows 操作系统安装映像的 Microsoft Defender 更新](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="42334-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="42334-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="42334-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="42334-403">&ensp;程序包版本 **：1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="42334-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="42334-404">&ensp;平台版本 **：4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="42334-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="42334-405">&ensp;引擎版本 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="42334-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="42334-406">&ensp;签名版本 **：1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="42334-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="42334-407">修补程序</span><span class="sxs-lookup"><span data-stu-id="42334-407">Fixes</span></span>
- <span data-ttu-id="42334-408">无</span><span class="sxs-lookup"><span data-stu-id="42334-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="42334-409">其他信息</span><span class="sxs-lookup"><span data-stu-id="42334-409">Additional information</span></span>
- <span data-ttu-id="42334-410">无</span><span class="sxs-lookup"><span data-stu-id="42334-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="42334-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="42334-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="42334-412">&ensp;程序包版本 **：1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="42334-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="42334-413">&ensp;平台版本 **：4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="42334-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="42334-414">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="42334-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="42334-415">&ensp;签名版本 **：1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="42334-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="42334-416">修补程序</span><span class="sxs-lookup"><span data-stu-id="42334-416">Fixes</span></span>
- <span data-ttu-id="42334-417">无</span><span class="sxs-lookup"><span data-stu-id="42334-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="42334-418">其他信息</span><span class="sxs-lookup"><span data-stu-id="42334-418">Additional information</span></span>
- <span data-ttu-id="42334-419">无</span><span class="sxs-lookup"><span data-stu-id="42334-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="42334-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="42334-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="42334-421">&ensp;程序包版本 **：1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="42334-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="42334-422">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="42334-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="42334-423">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="42334-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="42334-424">&ensp;签名版本 **：1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="42334-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="42334-425">修补程序</span><span class="sxs-lookup"><span data-stu-id="42334-425">Fixes</span></span>
- <span data-ttu-id="42334-426">无</span><span class="sxs-lookup"><span data-stu-id="42334-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="42334-427">其他信息</span><span class="sxs-lookup"><span data-stu-id="42334-427">Additional information</span></span>
- <span data-ttu-id="42334-428">无</span><span class="sxs-lookup"><span data-stu-id="42334-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="42334-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="42334-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="42334-430">&ensp;程序包版本 **：1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="42334-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="42334-431">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="42334-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="42334-432">&ensp;引擎版本 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="42334-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="42334-433">&ensp;签名版本 **：1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="42334-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="42334-434">修补程序</span><span class="sxs-lookup"><span data-stu-id="42334-434">Fixes</span></span>
- <span data-ttu-id="42334-435">无</span><span class="sxs-lookup"><span data-stu-id="42334-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="42334-436">其他信息</span><span class="sxs-lookup"><span data-stu-id="42334-436">Additional information</span></span>
- <span data-ttu-id="42334-437">无</span><span class="sxs-lookup"><span data-stu-id="42334-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="42334-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="42334-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="42334-439">&ensp;程序包版本 **：1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="42334-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="42334-440">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="42334-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="42334-441">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="42334-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="42334-442">&ensp;签名版本 **：1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="42334-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="42334-443">修补程序</span><span class="sxs-lookup"><span data-stu-id="42334-443">Fixes</span></span>
- <span data-ttu-id="42334-444">无</span><span class="sxs-lookup"><span data-stu-id="42334-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="42334-445">其他信息</span><span class="sxs-lookup"><span data-stu-id="42334-445">Additional information</span></span>
- <span data-ttu-id="42334-446">无</span><span class="sxs-lookup"><span data-stu-id="42334-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="42334-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="42334-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="42334-448">&ensp;程序包版本 **：1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="42334-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="42334-449">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="42334-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="42334-450">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="42334-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="42334-451">&ensp;签名版本 **：1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="42334-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="42334-452">修补程序</span><span class="sxs-lookup"><span data-stu-id="42334-452">Fixes</span></span>
- <span data-ttu-id="42334-453">无</span><span class="sxs-lookup"><span data-stu-id="42334-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="42334-454">其他信息</span><span class="sxs-lookup"><span data-stu-id="42334-454">Additional information</span></span>
- <span data-ttu-id="42334-455">刷新的 Microsoft Defender 防病毒签名</span><span class="sxs-lookup"><span data-stu-id="42334-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="42334-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="42334-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="42334-457">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="42334-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="42334-458">&ensp;平台版本 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="42334-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="42334-459">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="42334-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="42334-460">&ensp;签名版本 **：1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="42334-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="42334-461">修补程序</span><span class="sxs-lookup"><span data-stu-id="42334-461">Fixes</span></span>
- <span data-ttu-id="42334-462">无</span><span class="sxs-lookup"><span data-stu-id="42334-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="42334-463">其他信息</span><span class="sxs-lookup"><span data-stu-id="42334-463">Additional information</span></span>
- <span data-ttu-id="42334-464">无</span><span class="sxs-lookup"><span data-stu-id="42334-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="42334-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="42334-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="42334-466">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="42334-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="42334-467">&ensp;平台版本 **：4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="42334-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="42334-468">&ensp;引擎版本 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="42334-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="42334-469">&ensp;签名版本 **：1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="42334-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="42334-470">修补程序</span><span class="sxs-lookup"><span data-stu-id="42334-470">Fixes</span></span>
- <span data-ttu-id="42334-471">无</span><span class="sxs-lookup"><span data-stu-id="42334-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="42334-472">其他信息</span><span class="sxs-lookup"><span data-stu-id="42334-472">Additional information</span></span>
- <span data-ttu-id="42334-473">添加了对 Windows 10 RS1 或更高版本操作系统安装映像的支持。</span><span class="sxs-lookup"><span data-stu-id="42334-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="42334-474">其他资源</span><span class="sxs-lookup"><span data-stu-id="42334-474">Additional resources</span></span>

| <span data-ttu-id="42334-475">文章</span><span class="sxs-lookup"><span data-stu-id="42334-475">Article</span></span> | <span data-ttu-id="42334-476">说明</span><span class="sxs-lookup"><span data-stu-id="42334-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="42334-477">Windows 操作系统安装映像的 Microsoft Defender 更新</span><span class="sxs-lookup"><span data-stu-id="42334-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="42334-478">查看适用于操作系统安装映像的反恶意软件更新程序包 (WIM 和 VHD 文件) 。</span><span class="sxs-lookup"><span data-stu-id="42334-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="42334-479">获取 Windows 10 (Enterprise、Pro 和 Home 版本) 、Windows Server 2019 和 Windows Server 2016 安装映像的 Microsoft Defender 防病毒更新。</span><span class="sxs-lookup"><span data-stu-id="42334-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="42334-480">管理保护更新的下载和应用方式</span><span class="sxs-lookup"><span data-stu-id="42334-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="42334-481">保护更新可以通过多个源提供。</span><span class="sxs-lookup"><span data-stu-id="42334-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="42334-482">管理何时应下载和应用保护更新</span><span class="sxs-lookup"><span data-stu-id="42334-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="42334-483">你可以计划应下载保护更新的时间。</span><span class="sxs-lookup"><span data-stu-id="42334-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="42334-484">管理过期终结点的更新</span><span class="sxs-lookup"><span data-stu-id="42334-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="42334-485">如果终结点错过更新或计划扫描，可以在用户下次登录时强制进行更新或扫描。</span><span class="sxs-lookup"><span data-stu-id="42334-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="42334-486">管理基于事件的强制更新</span><span class="sxs-lookup"><span data-stu-id="42334-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="42334-487">你可以将保护更新设置为在启动时或在某些云提供的保护事件之后下载。</span><span class="sxs-lookup"><span data-stu-id="42334-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="42334-488">管理移动设备和虚拟机 （VM） 的更新</span><span class="sxs-lookup"><span data-stu-id="42334-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="42334-489">你可以指定对移动设备和虚拟机特别有用的设置，例如是否应该使用电池电源进行更新。</span><span class="sxs-lookup"><span data-stu-id="42334-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
