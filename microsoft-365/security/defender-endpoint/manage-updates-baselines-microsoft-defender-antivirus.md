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
ms.date: 06/08/2021
ms.openlocfilehash: ccbb57d781196e352e0fed456a1f7cb43eb17300
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822270"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="69562-104">管理Microsoft Defender 防病毒更新并应用基线</span><span class="sxs-lookup"><span data-stu-id="69562-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="69562-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="69562-105">**Applies to:**</span></span>

- [<span data-ttu-id="69562-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="69562-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="69562-107">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="69562-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="69562-108">有两种类型的更新与使Microsoft Defender 防病毒保持最新有关：</span><span class="sxs-lookup"><span data-stu-id="69562-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="69562-109">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="69562-109">Security intelligence updates</span></span>
- <span data-ttu-id="69562-110">产品更新</span><span class="sxs-lookup"><span data-stu-id="69562-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69562-111">保持Microsoft Defender 防病毒保持最新状态对于确保你的设备具有抵御新的恶意软件和攻击技术所需的最新技术和功能至关重要。</span><span class="sxs-lookup"><span data-stu-id="69562-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="69562-112">确保更新防病毒保护，即使Microsoft Defender 防病毒处于被动[模式。](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="69562-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="69562-113">To see the most current engine， platform， and signature date， visit the [Security intelligence updates for Microsoft Defender 防病毒 other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="69562-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="69562-114">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="69562-114">Security intelligence updates</span></span>

<span data-ttu-id="69562-115">Microsoft Defender 防病毒云[提供的](cloud-protection-microsoft-defender-antivirus.md)保护 (也称为 Microsoft 高级保护服务或 MAPS) 并定期下载安全智能更新以提供保护。</span><span class="sxs-lookup"><span data-stu-id="69562-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="69562-116">更新以以下 KB 编号发布：</span><span class="sxs-lookup"><span data-stu-id="69562-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="69562-117">Microsoft Defender 防病毒：KB2267602</span><span class="sxs-lookup"><span data-stu-id="69562-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="69562-118">System Center Endpoint Protection：KB2461484</span><span class="sxs-lookup"><span data-stu-id="69562-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="69562-119">云提供的保护始终打开，并且需要与 Internet 的活动连接以正常运行。</span><span class="sxs-lookup"><span data-stu-id="69562-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="69562-120">安全智能更新按计划节奏进行， (策略策略配置) 。</span><span class="sxs-lookup"><span data-stu-id="69562-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="69562-121">有关详细信息，请参阅使用[Microsoft 云提供的Microsoft Defender 防病毒。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="69562-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="69562-122">有关最近安全智能更新的列表，请参阅安全智能更新[Microsoft Defender 防病毒和其他 Microsoft 反恶意软件](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="69562-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="69562-123">引擎更新包含在安全智能更新中，并按月发布。</span><span class="sxs-lookup"><span data-stu-id="69562-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="69562-124">产品更新</span><span class="sxs-lookup"><span data-stu-id="69562-124">Product updates</span></span>

<span data-ttu-id="69562-125">Microsoft Defender 防病毒需要每月更新 [ (KB4052623](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform))  (称为平台更新 *) ，* 并且将在 Windows 10 版本旁边接收主要功能更新。</span><span class="sxs-lookup"><span data-stu-id="69562-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="69562-126">可以通过以下方法之一管理更新的分发：</span><span class="sxs-lookup"><span data-stu-id="69562-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="69562-127">WindowsWSUS (服务器更新) </span><span class="sxs-lookup"><span data-stu-id="69562-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="69562-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="69562-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="69562-129">你用于部署 Microsoft 和Windows终结点更新的常用方法。</span><span class="sxs-lookup"><span data-stu-id="69562-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="69562-130">有关详细信息，请参阅管理保护Microsoft Defender 防病毒[源](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="69562-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="69562-131">每月更新会分期发布，从而在 Window Server Update Services 中显示 [多个程序包](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="69562-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="69562-132">每月平台和引擎版本</span><span class="sxs-lookup"><span data-stu-id="69562-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="69562-133">若要了解如何更新或安装平台更新，请参阅反恶意软件Windows Defender[更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="69562-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="69562-134">我们的所有更新都包含</span><span class="sxs-lookup"><span data-stu-id="69562-134">All our updates contain</span></span> 
- <span data-ttu-id="69562-135">性能改进;</span><span class="sxs-lookup"><span data-stu-id="69562-135">performance improvements;</span></span>
- <span data-ttu-id="69562-136">可服务性改进;和</span><span class="sxs-lookup"><span data-stu-id="69562-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="69562-137">集成改进 (云[，Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)) 。</span><span class="sxs-lookup"><span data-stu-id="69562-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="69562-138">2021 年 5 月 (平台：4.18.2105.4 |引擎：1.1.18200.4) </span><span class="sxs-lookup"><span data-stu-id="69562-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="69562-139">&ensp;安全智能更新版本 **：1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="69562-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="69562-140">&ensp;发布时间 **：2021 年 6 月 4 日**</span><span class="sxs-lookup"><span data-stu-id="69562-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="69562-141">&ensp;平台 **：4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="69562-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="69562-142">&ensp;引擎 **：1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="69562-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="69562-143">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="69562-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-144">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-144">What's new</span></span>
- <span data-ttu-id="69562-145">对行为 [监视的改进](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="69562-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="69562-146">修复 [了网络保护](network-protection.md) 通知筛选功能</span><span class="sxs-lookup"><span data-stu-id="69562-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-147">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-147">Known Issues</span></span>
<span data-ttu-id="69562-148">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="69562-149">2021 年 4 月 (平台：4.18.2104.14 |引擎：1.1.18100.5) </span><span class="sxs-lookup"><span data-stu-id="69562-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="69562-150">&ensp;安全智能更新版本 **：1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="69562-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="69562-151">&ensp;发布时间 **：2021 年 4 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="69562-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="69562-152">&ensp;平台 **：4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="69562-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="69562-153">&ensp;引擎 **：1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="69562-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="69562-154">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="69562-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-155">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-155">What's new</span></span>
- <span data-ttu-id="69562-156">其他行为监视逻辑</span><span class="sxs-lookup"><span data-stu-id="69562-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="69562-157">改进了内核模式键记录器检测</span><span class="sxs-lookup"><span data-stu-id="69562-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="69562-158">添加了新控件来管理 Microsoft Defender 更新的逐步 [推出过程](updates.md)</span><span class="sxs-lookup"><span data-stu-id="69562-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-159">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-159">Known Issues</span></span>
<span data-ttu-id="69562-160">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="69562-161">2021 年 3 月 (平台：4.18.2103.7 |引擎：1.1.18000.5) </span><span class="sxs-lookup"><span data-stu-id="69562-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="69562-162">&ensp;安全智能更新版本 **：1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="69562-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="69562-163">&ensp;发布时间 **：2021 年 4 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="69562-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="69562-164">&ensp;平台 **：4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="69562-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="69562-165">&ensp;引擎 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="69562-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="69562-166">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="69562-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-167">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-167">What's new</span></span>

- <span data-ttu-id="69562-168">对行为监控引擎的改进</span><span class="sxs-lookup"><span data-stu-id="69562-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="69562-169">扩展的网络暴力攻击缓解措施</span><span class="sxs-lookup"><span data-stu-id="69562-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="69562-170">启用防篡改保护 [时的其他失败](prevent-changes-to-security-settings-with-tamper-protection.md) 篡改尝试事件生成</span><span class="sxs-lookup"><span data-stu-id="69562-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-171">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-171">Known Issues</span></span>
<span data-ttu-id="69562-172">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="69562-173">旧版本更新：仅技术升级支持</span><span class="sxs-lookup"><span data-stu-id="69562-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="69562-174">发布新程序包版本后，仅对前两个版本的支持减少到技术支持。</span><span class="sxs-lookup"><span data-stu-id="69562-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="69562-175">低于本部分中列出的版本，并且仅提供用于技术升级支持的版本。</span><span class="sxs-lookup"><span data-stu-id="69562-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="69562-176">2021 年 2 月 (平台：4.18.2102.3 |引擎：1.1.17900.7) </span><span class="sxs-lookup"><span data-stu-id="69562-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="69562-177">&ensp;安全智能更新版本 **：1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="69562-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="69562-178">&ensp;已发布 **：2021 年 3 月 9 日**</span><span class="sxs-lookup"><span data-stu-id="69562-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="69562-179">&ensp;平台 **：4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="69562-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="69562-180">&ensp;引擎 **：1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="69562-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="69562-181">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-182">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-182">What's new</span></span>

- <span data-ttu-id="69562-183">通过防篡改保护 [改进了服务恢复](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="69562-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="69562-184">扩展防篡改保护作用域</span><span class="sxs-lookup"><span data-stu-id="69562-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-185">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-185">Known Issues</span></span>
<span data-ttu-id="69562-186">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="69562-187">2021 年 1 月 (平台：4.18.2101.9 |引擎：1.1.17800.5) </span><span class="sxs-lookup"><span data-stu-id="69562-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="69562-188">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="69562-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="69562-189">&ensp;发布时间 **：2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="69562-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="69562-190">&ensp;平台 **：4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="69562-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="69562-191">&ensp;引擎 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="69562-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="69562-192">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-193">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-193">What's new</span></span>

- <span data-ttu-id="69562-194">Shellcode 攻击检测改进</span><span class="sxs-lookup"><span data-stu-id="69562-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="69562-195">提高了凭据窃取尝试的可见性</span><span class="sxs-lookup"><span data-stu-id="69562-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="69562-196">改进服务中的反Microsoft Defender 防病毒功能</span><span class="sxs-lookup"><span data-stu-id="69562-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="69562-197">改进了对 x64 ARM的支持</span><span class="sxs-lookup"><span data-stu-id="69562-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="69562-198">修复：EDR执行初始检测后阻止通知仍保留在威胁历史记录中</span><span class="sxs-lookup"><span data-stu-id="69562-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-199">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-199">Known Issues</span></span>
<span data-ttu-id="69562-200">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="69562-201">2020 年 11 月 (平台：4.18.2011.6 |引擎：1.1.17700.4) </span><span class="sxs-lookup"><span data-stu-id="69562-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="69562-202">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="69562-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="69562-203">&ensp;发布时间 **：2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="69562-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="69562-204">&ensp;平台 **：4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="69562-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="69562-205">&ensp;引擎 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="69562-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="69562-206">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-207">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-207">What's new</span></span>

- <span data-ttu-id="69562-208">改进 [的 SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 状态支持日志记录</span><span class="sxs-lookup"><span data-stu-id="69562-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-209">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-209">Known Issues</span></span>
<span data-ttu-id="69562-210">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="69562-211">2020 年 10 月 (平台：4.18.2010.7 |引擎：1.1.17600.5) </span><span class="sxs-lookup"><span data-stu-id="69562-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="69562-212">&ensp;安全智能更新版本 **：1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="69562-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="69562-213">&ensp;发布时间 **：2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="69562-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="69562-214">&ensp;平台 **：4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="69562-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="69562-215">&ensp;引擎 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="69562-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="69562-216">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-217">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-217">What's new</span></span>

- <span data-ttu-id="69562-218">特殊威胁类别的新说明</span><span class="sxs-lookup"><span data-stu-id="69562-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="69562-219">改进的模拟功能</span><span class="sxs-lookup"><span data-stu-id="69562-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="69562-220">改进了主机地址允许/阻止功能</span><span class="sxs-lookup"><span data-stu-id="69562-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="69562-221">Defender CSP 中用于忽略本地用户排除项合并的新选项</span><span class="sxs-lookup"><span data-stu-id="69562-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-222">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-222">Known Issues</span></span>

<span data-ttu-id="69562-223">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="69562-224">2020 年 9 月 (平台：4.18.2009.7 |引擎：1.1.17500.4) </span><span class="sxs-lookup"><span data-stu-id="69562-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="69562-225">&ensp;安全智能更新版本 **：1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="69562-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="69562-226">&ensp;发布时间 **：2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="69562-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="69562-227">&ensp;平台 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="69562-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="69562-228">&ensp;引擎 **：1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="69562-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="69562-229">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-230">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-230">What's new</span></span>

- <span data-ttu-id="69562-231">需要管理员权限才能还原隔离中的文件</span><span class="sxs-lookup"><span data-stu-id="69562-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="69562-232">XML 格式事件现在受支持</span><span class="sxs-lookup"><span data-stu-id="69562-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="69562-233">忽略排除合并的云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="69562-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="69562-234">用于：</span><span class="sxs-lookup"><span data-stu-id="69562-234">New management interfaces for:</span></span>
   - <span data-ttu-id="69562-235">UDP 检查</span><span class="sxs-lookup"><span data-stu-id="69562-235">UDP Inspection</span></span>
   - <span data-ttu-id="69562-236">Server 2019 上的网络保护</span><span class="sxs-lookup"><span data-stu-id="69562-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="69562-237">网络保护的 IP 地址排除项</span><span class="sxs-lookup"><span data-stu-id="69562-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="69562-238">改进了对 TPM 测量的可见性</span><span class="sxs-lookup"><span data-stu-id="69562-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="69562-239">改进了 Office VBA 模块扫描</span><span class="sxs-lookup"><span data-stu-id="69562-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-240">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-240">Known Issues</span></span>

<span data-ttu-id="69562-241">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="69562-242">2020 年 8 月 (平台：4.18.2008.9 |引擎：1.1.17400.5) </span><span class="sxs-lookup"><span data-stu-id="69562-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="69562-243">&ensp;安全智能更新版本 **：1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="69562-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="69562-244">&ensp;发布时间 **：2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="69562-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="69562-245">&ensp;平台 **：4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="69562-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="69562-246">&ensp;引擎 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="69562-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="69562-247">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="69562-248">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-248">What's new</span></span>

- <span data-ttu-id="69562-249">添加更多遥测事件</span><span class="sxs-lookup"><span data-stu-id="69562-249">Add more telemetry events</span></span>
- <span data-ttu-id="69562-250">改进了扫描事件遥测</span><span class="sxs-lookup"><span data-stu-id="69562-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="69562-251">改进了内存扫描行为监视</span><span class="sxs-lookup"><span data-stu-id="69562-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="69562-252">改进的宏流扫描</span><span class="sxs-lookup"><span data-stu-id="69562-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="69562-253">已 `AMRunningMode` 添加到 Get-MpComputerStatus PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="69562-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="69562-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="69562-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="69562-255">Microsoft Defender 防病毒检测到其他防病毒程序时自动关闭自身。</span><span class="sxs-lookup"><span data-stu-id="69562-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="69562-256">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-256">Known Issues</span></span>
<span data-ttu-id="69562-257">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="69562-258">2020 年 7 月 (平台：4.18.2007.8 |引擎：1.1.17300.4) </span><span class="sxs-lookup"><span data-stu-id="69562-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="69562-259">&ensp;安全智能更新版本 **：1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="69562-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="69562-260">&ensp;发布时间 **：2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="69562-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="69562-261">&ensp;平台 **：4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="69562-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="69562-262">&ensp;引擎 **：1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="69562-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="69562-263">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-264">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-264">What's new</span></span>

- <span data-ttu-id="69562-265">改进的 BITS 遥测</span><span class="sxs-lookup"><span data-stu-id="69562-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="69562-266">改进的验证码代码签名证书验证</span><span class="sxs-lookup"><span data-stu-id="69562-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-267">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-267">Known Issues</span></span>
<span data-ttu-id="69562-268">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="69562-269">2020 年 6 月 (平台：4.18.2006.10 |引擎：1.1.17200.2) </span><span class="sxs-lookup"><span data-stu-id="69562-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="69562-270">&ensp;安全智能更新版本 **：1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="69562-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="69562-271">&ensp;发布时间 **：2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="69562-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="69562-272">&ensp;平台 **：4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="69562-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="69562-273">&ensp;引擎 **：1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="69562-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="69562-274">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-275">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-275">What's new</span></span>

- <span data-ttu-id="69562-276">指定支持 [日志的位置的可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="69562-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="69562-277">在被动模式下跳过主动的捕获扫描。</span><span class="sxs-lookup"><span data-stu-id="69562-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="69562-278">允许 Defender 更新按流量计费的连接</span><span class="sxs-lookup"><span data-stu-id="69562-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="69562-279">修复了禁用缓存时的性能调整</span><span class="sxs-lookup"><span data-stu-id="69562-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="69562-280">修复了注册表查询</span><span class="sxs-lookup"><span data-stu-id="69562-280">Fixed registry query</span></span> 
- <span data-ttu-id="69562-281">修复了 ADMX 中的扫描时间随机化</span><span class="sxs-lookup"><span data-stu-id="69562-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-282">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-282">Known Issues</span></span>
<span data-ttu-id="69562-283">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="69562-284">2020 年 5 月 (平台：4.18.2005.4 |引擎：1.1.17100.2) </span><span class="sxs-lookup"><span data-stu-id="69562-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="69562-285">&ensp;安全智能更新版本 **：1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="69562-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="69562-286">&ensp;发布时间 **：2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="69562-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="69562-287">&ensp;平台 **：4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="69562-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="69562-288">&ensp;引擎 **：1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="69562-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="69562-289">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-290">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-290">What's new</span></span>

- <span data-ttu-id="69562-291">改进了扫描事件的日志记录</span><span class="sxs-lookup"><span data-stu-id="69562-291">Improved logging for scan events</span></span>
- <span data-ttu-id="69562-292">改进了用户模式崩溃处理。</span><span class="sxs-lookup"><span data-stu-id="69562-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="69562-293">添加了防篡改保护的事件跟踪</span><span class="sxs-lookup"><span data-stu-id="69562-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="69562-294">修复了 AMSI 示例提交</span><span class="sxs-lookup"><span data-stu-id="69562-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="69562-295">修复了 AMSI 云阻止</span><span class="sxs-lookup"><span data-stu-id="69562-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="69562-296">修复了安全更新安装日志</span><span class="sxs-lookup"><span data-stu-id="69562-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-297">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-297">Known Issues</span></span>
<span data-ttu-id="69562-298">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="69562-299">2020 年 4 月 (平台：4.18.2004.6 |引擎：1.1.17000.2) </span><span class="sxs-lookup"><span data-stu-id="69562-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="69562-300">&ensp;安全智能更新版本 **：1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="69562-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="69562-301">&ensp;发布时间 **：2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="69562-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="69562-302">&ensp;平台 **：4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="69562-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="69562-303">&ensp;引擎 **：1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="69562-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="69562-304">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-305">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-305">What's new</span></span>
- <span data-ttu-id="69562-306">WDfilter 改进</span><span class="sxs-lookup"><span data-stu-id="69562-306">WDfilter improvements</span></span>
- <span data-ttu-id="69562-307">向攻击面减少检测事件添加更多可操作事件数据</span><span class="sxs-lookup"><span data-stu-id="69562-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="69562-308">诊断数据和 WMI 中的固定版本信息</span><span class="sxs-lookup"><span data-stu-id="69562-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="69562-309">修复了平台更新后 UI 中的平台版本不正确</span><span class="sxs-lookup"><span data-stu-id="69562-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="69562-310">用于无文件威胁防护的动态 URL intel</span><span class="sxs-lookup"><span data-stu-id="69562-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="69562-311">UEFI 扫描功能</span><span class="sxs-lookup"><span data-stu-id="69562-311">UEFI scan capability</span></span>
- <span data-ttu-id="69562-312">扩展更新日志记录</span><span class="sxs-lookup"><span data-stu-id="69562-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="69562-313">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-313">Known Issues</span></span>
<span data-ttu-id="69562-314">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="69562-315">2020 年 3 月 (平台：4.18.2003.8 |引擎：1.1.16900.2) </span><span class="sxs-lookup"><span data-stu-id="69562-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="69562-316">&ensp;安全智能更新版本 **：1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="69562-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="69562-317">&ensp;已发布 **：2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="69562-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="69562-318">&ensp;平台 **：4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="69562-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="69562-319">&ensp;引擎 **：1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="69562-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="69562-320">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="69562-321">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-321">What's new</span></span>

- <span data-ttu-id="69562-322">添加到[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 限制选项</span><span class="sxs-lookup"><span data-stu-id="69562-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="69562-323">改进诊断功能</span><span class="sxs-lookup"><span data-stu-id="69562-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="69562-324">将安全智能超时 (5 分钟) </span><span class="sxs-lookup"><span data-stu-id="69562-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="69562-325">扩展 AMSI 引擎内部日志功能</span><span class="sxs-lookup"><span data-stu-id="69562-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="69562-326">改进进程阻止通知</span><span class="sxs-lookup"><span data-stu-id="69562-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="69562-327">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-327">Known Issues</span></span>
<span data-ttu-id="69562-328">[**Fixed**]Microsoft Defender 防病毒扫描时跳过文件。</span><span class="sxs-lookup"><span data-stu-id="69562-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="69562-329">2020 年 2 月 (平台： - |引擎：1.1.16800.2) </span><span class="sxs-lookup"><span data-stu-id="69562-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="69562-330">&ensp;安全智能更新版本 **：1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="69562-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="69562-331">&ensp;发布时间 **：2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="69562-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="69562-332">&ensp;平台/客户端： **-**</span><span class="sxs-lookup"><span data-stu-id="69562-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="69562-333">&ensp;引擎 **：1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="69562-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="69562-334">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="69562-335">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="69562-336">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-336">Known Issues</span></span>
<span data-ttu-id="69562-337">无已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="69562-338">2020 年 1 月 (平台：4.18.2001.10 |引擎：1.1.16700.2) </span><span class="sxs-lookup"><span data-stu-id="69562-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="69562-339">安全智能更新版本 **：1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="69562-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="69562-340">发布时间 **：2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="69562-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="69562-341">平台/客户端 **：4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="69562-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="69562-342">引擎 **：1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="69562-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="69562-343">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="69562-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="69562-344">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-344">What's new</span></span>

- <span data-ttu-id="69562-345">修复了 WS2016 上的 BSOD 与Exchange</span><span class="sxs-lookup"><span data-stu-id="69562-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="69562-346">当 TMP 重定向到网络路径时支持平台更新</span><span class="sxs-lookup"><span data-stu-id="69562-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="69562-347">平台和引擎版本已添加到 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="69562-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="69562-348">将紧急签名更新扩展到 [被动模式](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="69562-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="69562-349">修复 4.18.1911.3 挂起</span><span class="sxs-lookup"><span data-stu-id="69562-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="69562-350">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-350">Known Issues</span></span>

<span data-ttu-id="69562-351">[**修复**][使用新式待机](/windows-hardware/design/device-experiences/modern-standby)模式的设备可能会遇到与 Windows Defender 筛选器驱动程序的挂起，导致保护差距。</span><span class="sxs-lookup"><span data-stu-id="69562-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="69562-352">受影响的计算机向客户显示尚未更新到最新的反恶意软件平台。</span><span class="sxs-lookup"><span data-stu-id="69562-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="69562-353">此更新为：</span><span class="sxs-lookup"><span data-stu-id="69562-353">This update is:</span></span>
> - <span data-ttu-id="69562-354">运行较低版本的平台以支持 SHA2 的 RS1 设备需要;</span><span class="sxs-lookup"><span data-stu-id="69562-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="69562-355">对于有挂起问题的系统，具有重新启动标志;</span><span class="sxs-lookup"><span data-stu-id="69562-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="69562-356">在 2020 年 4 月重新发布，并且不会被更新的更新所取代，以保持将来的可用性;</span><span class="sxs-lookup"><span data-stu-id="69562-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="69562-357">因重启要求而分类为更新;和</span><span class="sxs-lookup"><span data-stu-id="69562-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="69562-358">仅提供与 Windows Update 一[起提供](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="69562-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="69562-359">2019 年 11 月 (平台：4.18.1911.3 |引擎：1.1.16600.7) </span><span class="sxs-lookup"><span data-stu-id="69562-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="69562-360">安全智能更新版本 **：1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="69562-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="69562-361">发布时间 **：2019 年 12 月 7 日**</span><span class="sxs-lookup"><span data-stu-id="69562-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="69562-362">平台 **：4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="69562-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="69562-363">引擎 **：1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="69562-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="69562-364">支持阶段： **不支持**</span><span class="sxs-lookup"><span data-stu-id="69562-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="69562-365">最近更新</span><span class="sxs-lookup"><span data-stu-id="69562-365">What's new</span></span>

- <span data-ttu-id="69562-366">修复了 MpCmdRun 跟踪级别</span><span class="sxs-lookup"><span data-stu-id="69562-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="69562-367">修复了 WDFilter 版本信息</span><span class="sxs-lookup"><span data-stu-id="69562-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="69562-368">改进 PUA (通知) </span><span class="sxs-lookup"><span data-stu-id="69562-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="69562-369">添加 MRT 日志以支持文件</span><span class="sxs-lookup"><span data-stu-id="69562-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="69562-370">已知问题</span><span class="sxs-lookup"><span data-stu-id="69562-370">Known Issues</span></span>
<span data-ttu-id="69562-371">安装此更新后，设备需要跳转程序包 4.18.2001.10 才能更新到最新的平台版本。</span><span class="sxs-lookup"><span data-stu-id="69562-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="69562-372">Microsoft Defender 防病毒平台支持</span><span class="sxs-lookup"><span data-stu-id="69562-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="69562-373">平台和引擎更新按月提供。</span><span class="sxs-lookup"><span data-stu-id="69562-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="69562-374">若要完全受支持，请及时了解最新的平台更新。</span><span class="sxs-lookup"><span data-stu-id="69562-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="69562-375">我们的支持结构是动态的，根据最新平台版本的可用性，将发展为两个阶段：</span><span class="sxs-lookup"><span data-stu-id="69562-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="69562-376">**安全和关键更新服务阶段** - 运行最新平台版本时，你将有资格接收反恶意软件平台的安全和关键更新。</span><span class="sxs-lookup"><span data-stu-id="69562-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="69562-377">**技术支持 (仅在)** 阶段 - 发布新平台版本后，对早期版本 (N-2) 的支持将仅减少为技术支持。</span><span class="sxs-lookup"><span data-stu-id="69562-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="69562-378">不再支持 N-2 之前的平台版本。\*</span><span class="sxs-lookup"><span data-stu-id="69562-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="69562-379">\*将继续为从 Windows 10 版本升级提供技术支持 (请参阅[Windows 10](#platform-version-included-with-windows-10-releases)版本中包含的平台版本) 到最新平台版本。</span><span class="sxs-lookup"><span data-stu-id="69562-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="69562-380">在技术支持 (仅在) 阶段，商业上合理的支持事件将通过 Microsoft 客户服务 & 支持和 Microsoft 的托管支持产品/服务 (如 Premier Support) 提供。</span><span class="sxs-lookup"><span data-stu-id="69562-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="69562-381">如果支持事件需要上报开发以进一步提供指导、需要非安全更新或需要安全更新，将要求客户升级到最新平台版本或中间 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="69562-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="69562-382">版本中包含的平台Windows 10版本</span><span class="sxs-lookup"><span data-stu-id="69562-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="69562-383">下表提供了最新 Microsoft Defender 防病毒 版本附带的 Microsoft Defender 防病毒 Windows 10 平台和引擎版本：</span><span class="sxs-lookup"><span data-stu-id="69562-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="69562-384">Windows 10发布</span><span class="sxs-lookup"><span data-stu-id="69562-384">Windows 10 release</span></span>  |<span data-ttu-id="69562-385">平台版本</span><span class="sxs-lookup"><span data-stu-id="69562-385">Platform version</span></span>  |<span data-ttu-id="69562-386">引擎版本</span><span class="sxs-lookup"><span data-stu-id="69562-386">Engine version</span></span> |<span data-ttu-id="69562-387">支持阶段</span><span class="sxs-lookup"><span data-stu-id="69562-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="69562-388">2004 (20H1/20H2) </span><span class="sxs-lookup"><span data-stu-id="69562-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="69562-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="69562-389">4.18.1909.6</span></span> |<span data-ttu-id="69562-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="69562-390">1.1.17000.2</span></span> | <span data-ttu-id="69562-391">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="69562-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="69562-392">1909 (19H2) </span><span class="sxs-lookup"><span data-stu-id="69562-392">1909  (19H2)</span></span> |<span data-ttu-id="69562-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="69562-393">4.18.1902.5</span></span> |<span data-ttu-id="69562-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="69562-394">1.1.16700.3</span></span> | <span data-ttu-id="69562-395">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="69562-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="69562-396">1903 (19H1) </span><span class="sxs-lookup"><span data-stu-id="69562-396">1903  (19H1)</span></span> |<span data-ttu-id="69562-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="69562-397">4.18.1902.5</span></span> |<span data-ttu-id="69562-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="69562-398">1.1.15600.4</span></span> | <span data-ttu-id="69562-399">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="69562-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="69562-400">1809 (RS5) </span><span class="sxs-lookup"><span data-stu-id="69562-400">1809  (RS5)</span></span> |<span data-ttu-id="69562-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="69562-401">4.18.1807.18075</span></span> |<span data-ttu-id="69562-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="69562-402">1.1.15000.2</span></span> | <span data-ttu-id="69562-403">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="69562-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="69562-404">1803 (RS4) </span><span class="sxs-lookup"><span data-stu-id="69562-404">1803  (RS4)</span></span> |<span data-ttu-id="69562-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="69562-405">4.13.17134.1</span></span> |<span data-ttu-id="69562-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="69562-406">1.1.14600.4</span></span> | <span data-ttu-id="69562-407">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="69562-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="69562-408">1709 (RS3) </span><span class="sxs-lookup"><span data-stu-id="69562-408">1709  (RS3)</span></span> |<span data-ttu-id="69562-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="69562-409">4.12.16299.15</span></span> |<span data-ttu-id="69562-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="69562-410">1.1.14104.0</span></span> | <span data-ttu-id="69562-411">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="69562-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="69562-412">1703 (RS2) </span><span class="sxs-lookup"><span data-stu-id="69562-412">1703  (RS2)</span></span> |<span data-ttu-id="69562-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="69562-413">4.11.15603.2</span></span> |<span data-ttu-id="69562-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="69562-414">1.1.13504.0</span></span> | <span data-ttu-id="69562-415">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="69562-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="69562-416">1607 (RS1) </span><span class="sxs-lookup"><span data-stu-id="69562-416">1607 (RS1)</span></span> |<span data-ttu-id="69562-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="69562-417">4.10.14393.3683</span></span> |<span data-ttu-id="69562-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="69562-418">1.1.12805.0</span></span> | <span data-ttu-id="69562-419">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="69562-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="69562-420">有关Windows 10的信息，请参阅生命周期[Windows表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="69562-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="69562-421">DISM 部署映像服务和管理 (更新) </span><span class="sxs-lookup"><span data-stu-id="69562-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="69562-422">我们建议使用最新的防病毒和反恶意软件更新更新 Windows 10 (Enterprise、Pro 和家庭版) 、Windows Server 2019 和 Windows Server 2016 操作系统安装映像。</span><span class="sxs-lookup"><span data-stu-id="69562-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="69562-423">使操作系统安装映像保持最新有助于避免保护差距。</span><span class="sxs-lookup"><span data-stu-id="69562-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="69562-424">有关详细信息，请参阅适用于操作系统[安装映像Windows Microsoft Defender 更新](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="69562-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="69562-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="69562-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="69562-426">&ensp;程序包版本 **：1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="69562-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="69562-427">&ensp;平台版本 **：4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="69562-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="69562-428">&ensp;引擎版本 **：1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="69562-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="69562-429">&ensp;签名版本 **：1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="69562-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="69562-430">修补程序</span><span class="sxs-lookup"><span data-stu-id="69562-430">Fixes</span></span>
- <span data-ttu-id="69562-431">无</span><span class="sxs-lookup"><span data-stu-id="69562-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="69562-432">其他信息</span><span class="sxs-lookup"><span data-stu-id="69562-432">Additional information</span></span>
- <span data-ttu-id="69562-433">无</span><span class="sxs-lookup"><span data-stu-id="69562-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="69562-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="69562-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="69562-435">&ensp;程序包版本 **：1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="69562-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="69562-436">&ensp;平台版本 **：4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="69562-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="69562-437">&ensp;引擎版本 **：1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="69562-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="69562-438">&ensp;签名版本 **：1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="69562-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="69562-439">修补程序</span><span class="sxs-lookup"><span data-stu-id="69562-439">Fixes</span></span>
- <span data-ttu-id="69562-440">无</span><span class="sxs-lookup"><span data-stu-id="69562-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="69562-441">其他信息</span><span class="sxs-lookup"><span data-stu-id="69562-441">Additional information</span></span>
- <span data-ttu-id="69562-442">无</span><span class="sxs-lookup"><span data-stu-id="69562-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="69562-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="69562-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="69562-444">&ensp;程序包版本 **：1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="69562-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="69562-445">&ensp;平台版本 **：4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="69562-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="69562-446">&ensp;引擎版本 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="69562-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="69562-447">&ensp;签名版本 **：1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="69562-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="69562-448">修补程序</span><span class="sxs-lookup"><span data-stu-id="69562-448">Fixes</span></span>
- <span data-ttu-id="69562-449">无</span><span class="sxs-lookup"><span data-stu-id="69562-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="69562-450">其他信息</span><span class="sxs-lookup"><span data-stu-id="69562-450">Additional information</span></span>
- <span data-ttu-id="69562-451">无</span><span class="sxs-lookup"><span data-stu-id="69562-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="69562-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="69562-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="69562-453">&ensp;程序包版本 **：1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="69562-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="69562-454">&ensp;平台版本 **：4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="69562-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="69562-455">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="69562-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="69562-456">&ensp;签名版本 **：1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="69562-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="69562-457">修补程序</span><span class="sxs-lookup"><span data-stu-id="69562-457">Fixes</span></span>
- <span data-ttu-id="69562-458">无</span><span class="sxs-lookup"><span data-stu-id="69562-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="69562-459">其他信息</span><span class="sxs-lookup"><span data-stu-id="69562-459">Additional information</span></span>
- <span data-ttu-id="69562-460">无</span><span class="sxs-lookup"><span data-stu-id="69562-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="69562-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="69562-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="69562-462">&ensp;程序包版本 **：1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="69562-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="69562-463">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="69562-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="69562-464">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="69562-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="69562-465">&ensp;签名版本 **：1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="69562-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="69562-466">修补程序</span><span class="sxs-lookup"><span data-stu-id="69562-466">Fixes</span></span>
- <span data-ttu-id="69562-467">无</span><span class="sxs-lookup"><span data-stu-id="69562-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="69562-468">其他信息</span><span class="sxs-lookup"><span data-stu-id="69562-468">Additional information</span></span>
- <span data-ttu-id="69562-469">无</span><span class="sxs-lookup"><span data-stu-id="69562-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="69562-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="69562-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="69562-471">&ensp;程序包版本 **：1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="69562-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="69562-472">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="69562-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="69562-473">&ensp;引擎版本 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="69562-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="69562-474">&ensp;签名版本 **：1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="69562-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="69562-475">修补程序</span><span class="sxs-lookup"><span data-stu-id="69562-475">Fixes</span></span>
- <span data-ttu-id="69562-476">无</span><span class="sxs-lookup"><span data-stu-id="69562-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="69562-477">其他信息</span><span class="sxs-lookup"><span data-stu-id="69562-477">Additional information</span></span>
- <span data-ttu-id="69562-478">无</span><span class="sxs-lookup"><span data-stu-id="69562-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="69562-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="69562-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="69562-480">&ensp;程序包版本 **：1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="69562-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="69562-481">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="69562-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="69562-482">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="69562-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="69562-483">&ensp;签名版本 **：1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="69562-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="69562-484">修补程序</span><span class="sxs-lookup"><span data-stu-id="69562-484">Fixes</span></span>
- <span data-ttu-id="69562-485">无</span><span class="sxs-lookup"><span data-stu-id="69562-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="69562-486">其他信息</span><span class="sxs-lookup"><span data-stu-id="69562-486">Additional information</span></span>
- <span data-ttu-id="69562-487">无</span><span class="sxs-lookup"><span data-stu-id="69562-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="69562-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="69562-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="69562-489">&ensp;程序包版本 **：1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="69562-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="69562-490">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="69562-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="69562-491">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="69562-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="69562-492">&ensp;签名版本 **：1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="69562-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="69562-493">修补程序</span><span class="sxs-lookup"><span data-stu-id="69562-493">Fixes</span></span>
- <span data-ttu-id="69562-494">无</span><span class="sxs-lookup"><span data-stu-id="69562-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="69562-495">其他信息</span><span class="sxs-lookup"><span data-stu-id="69562-495">Additional information</span></span>
- <span data-ttu-id="69562-496">刷新Microsoft Defender 防病毒签名</span><span class="sxs-lookup"><span data-stu-id="69562-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="69562-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="69562-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="69562-498">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="69562-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="69562-499">&ensp;平台版本 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="69562-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="69562-500">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="69562-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="69562-501">&ensp;签名版本 **：1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="69562-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="69562-502">修补程序</span><span class="sxs-lookup"><span data-stu-id="69562-502">Fixes</span></span>
- <span data-ttu-id="69562-503">无</span><span class="sxs-lookup"><span data-stu-id="69562-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="69562-504">其他信息</span><span class="sxs-lookup"><span data-stu-id="69562-504">Additional information</span></span>
- <span data-ttu-id="69562-505">无</span><span class="sxs-lookup"><span data-stu-id="69562-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="69562-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="69562-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="69562-507">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="69562-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="69562-508">&ensp;平台版本 **：4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="69562-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="69562-509">&ensp;引擎版本 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="69562-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="69562-510">&ensp;签名版本 **：1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="69562-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="69562-511">修补程序</span><span class="sxs-lookup"><span data-stu-id="69562-511">Fixes</span></span>
- <span data-ttu-id="69562-512">无</span><span class="sxs-lookup"><span data-stu-id="69562-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="69562-513">其他信息</span><span class="sxs-lookup"><span data-stu-id="69562-513">Additional information</span></span>
- <span data-ttu-id="69562-514">添加了对 Windows 10 RS1 或更高版本操作系统安装映像的支持。</span><span class="sxs-lookup"><span data-stu-id="69562-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="69562-515">其他资源</span><span class="sxs-lookup"><span data-stu-id="69562-515">Additional resources</span></span>

| <span data-ttu-id="69562-516">文章</span><span class="sxs-lookup"><span data-stu-id="69562-516">Article</span></span> | <span data-ttu-id="69562-517">说明</span><span class="sxs-lookup"><span data-stu-id="69562-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="69562-518">适用于操作系统安装映像Windows Microsoft Defender 更新</span><span class="sxs-lookup"><span data-stu-id="69562-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="69562-519">查看适用于操作系统安装映像的反恶意软件更新程序包 (WIM 和 VHD 文件) 。</span><span class="sxs-lookup"><span data-stu-id="69562-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="69562-520">获取 Microsoft Defender 防病毒、Windows 10 (Enterprise、Pro、家庭版) 、Windows Server 2019 Windows Server 2016更新。</span><span class="sxs-lookup"><span data-stu-id="69562-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="69562-521">管理保护更新的下载和应用方式</span><span class="sxs-lookup"><span data-stu-id="69562-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="69562-522">保护更新可以通过多个源提供。</span><span class="sxs-lookup"><span data-stu-id="69562-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="69562-523">管理何时应下载和应用保护更新</span><span class="sxs-lookup"><span data-stu-id="69562-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="69562-524">你可以计划应下载保护更新的时间。</span><span class="sxs-lookup"><span data-stu-id="69562-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="69562-525">管理过期终结点的更新</span><span class="sxs-lookup"><span data-stu-id="69562-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="69562-526">如果终结点错过更新或计划扫描，可以在用户下次登录时强制进行更新或扫描。</span><span class="sxs-lookup"><span data-stu-id="69562-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="69562-527">管理基于事件的强制更新</span><span class="sxs-lookup"><span data-stu-id="69562-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="69562-528">你可以将保护更新设置为在启动时或在某些云提供的保护事件之后下载。</span><span class="sxs-lookup"><span data-stu-id="69562-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="69562-529">管理移动设备和虚拟机 （VM） 的更新</span><span class="sxs-lookup"><span data-stu-id="69562-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="69562-530">你可以指定对移动设备和虚拟机特别有用的设置，例如是否应该使用电池电源进行更新。</span><span class="sxs-lookup"><span data-stu-id="69562-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
