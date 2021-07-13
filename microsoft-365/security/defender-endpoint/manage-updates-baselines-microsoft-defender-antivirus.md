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
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 07/12/2021
ms.openlocfilehash: 0179c620c8ba00c987395a800ed335644048283f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394961"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="ca870-104">管理Microsoft Defender 防病毒更新并应用基线</span><span class="sxs-lookup"><span data-stu-id="ca870-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="ca870-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ca870-105">**Applies to:**</span></span>

- [<span data-ttu-id="ca870-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ca870-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="ca870-107">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="ca870-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="ca870-108">保持Microsoft Defender 防病毒保持最新状态对于确保你的设备具有抵御新的恶意软件和攻击技术所需的最新技术和功能至关重要。</span><span class="sxs-lookup"><span data-stu-id="ca870-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="ca870-109">确保更新防病毒保护，即使Microsoft Defender 防病毒处于被动[模式。](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ca870-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="ca870-110">有两种类型的更新与使Microsoft Defender 防病毒保持最新有关：</span><span class="sxs-lookup"><span data-stu-id="ca870-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="ca870-111">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="ca870-111">Security intelligence updates</span></span>
- <span data-ttu-id="ca870-112">产品更新</span><span class="sxs-lookup"><span data-stu-id="ca870-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="ca870-113">To see the most current engine， platform， and signature date， visit the [Security intelligence updates for Microsoft Defender 防病毒 other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ca870-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="ca870-114">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="ca870-114">Security intelligence updates</span></span>

<span data-ttu-id="ca870-115">Microsoft Defender 防病毒云[提供的](cloud-protection-microsoft-defender-antivirus.md)保护 (也称为 Microsoft 高级保护服务或 MAPS) 并定期下载安全智能更新以提供保护。</span><span class="sxs-lookup"><span data-stu-id="ca870-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="ca870-116">更新以以下 KB 编号发布：</span><span class="sxs-lookup"><span data-stu-id="ca870-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="ca870-117">Microsoft Defender 防病毒：KB2267602</span><span class="sxs-lookup"><span data-stu-id="ca870-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="ca870-118">System Center Endpoint Protection：KB2461484</span><span class="sxs-lookup"><span data-stu-id="ca870-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="ca870-119">云提供的保护始终打开，并且需要与 Internet 的活动连接以正常运行。</span><span class="sxs-lookup"><span data-stu-id="ca870-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="ca870-120">安全智能更新按计划节奏进行， (策略策略配置) 。</span><span class="sxs-lookup"><span data-stu-id="ca870-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="ca870-121">有关详细信息，请参阅使用[Microsoft 云提供的Microsoft Defender 防病毒。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ca870-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="ca870-122">有关最近安全智能更新的列表，请参阅安全智能更新[Microsoft Defender 防病毒和其他 Microsoft 反恶意软件](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="ca870-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="ca870-123">引擎更新包含在安全智能更新中，并按月发布。</span><span class="sxs-lookup"><span data-stu-id="ca870-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="ca870-124">产品更新</span><span class="sxs-lookup"><span data-stu-id="ca870-124">Product updates</span></span>

<span data-ttu-id="ca870-125">Microsoft Defender 防病毒需要 [每月更新 (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)称为 *平台更新*。</span><span class="sxs-lookup"><span data-stu-id="ca870-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) known as *platform updates*.</span></span>

<span data-ttu-id="ca870-126">可以通过以下方法之一管理更新的分发：</span><span class="sxs-lookup"><span data-stu-id="ca870-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="ca870-127">WindowsWSUS (服务器更新) </span><span class="sxs-lookup"><span data-stu-id="ca870-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="ca870-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ca870-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="ca870-129">你用于部署 Microsoft 和Windows终结点更新的常用方法。</span><span class="sxs-lookup"><span data-stu-id="ca870-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="ca870-130">有关详细信息，请参阅管理保护Microsoft Defender 防病毒[源](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="ca870-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> - <span data-ttu-id="ca870-131">每月更新会分期发布，从而在 Window Server Update Services 中显示 [多个程序包](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="ca870-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>
> - <span data-ttu-id="ca870-132">本文列出了广泛发布频道中包含的更改。</span><span class="sxs-lookup"><span data-stu-id="ca870-132">This article lists changes that are included in the broad release channel.</span></span> <span data-ttu-id="ca870-133">[请参阅此处的最新广泛频道版本](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)。</span><span class="sxs-lookup"><span data-stu-id="ca870-133">[See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span></span> 
> - <span data-ttu-id="ca870-134">若要了解有关逐步推出过程以及有关下一版本详细信息，请参阅管理 Microsoft Defender 更新 [的逐步推出过程](manage-gradual-rollout.md)。</span><span class="sxs-lookup"><span data-stu-id="ca870-134">To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
> - <span data-ttu-id="ca870-135">若要了解有关安全智能更新的信息，请参阅[安全智能更新Microsoft Defender 防病毒和其他 Microsoft 反恶意软件](https://www.microsoft.com/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="ca870-135">To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/wdsi/defenderupdates).</span></span> 

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="ca870-136">每月平台和引擎版本</span><span class="sxs-lookup"><span data-stu-id="ca870-136">Monthly platform and engine versions</span></span>

<span data-ttu-id="ca870-137">若要了解如何更新或安装平台更新，请参阅反恶意软件Windows Defender[更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="ca870-137">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="ca870-138">我们的所有更新都包含</span><span class="sxs-lookup"><span data-stu-id="ca870-138">All our updates contain</span></span> 
- <span data-ttu-id="ca870-139">性能改进;</span><span class="sxs-lookup"><span data-stu-id="ca870-139">performance improvements;</span></span>
- <span data-ttu-id="ca870-140">可服务性改进;和</span><span class="sxs-lookup"><span data-stu-id="ca870-140">serviceability improvements; and</span></span> 
- <span data-ttu-id="ca870-141">云 (集成[改进](/microsoft-365/security/defender/microsoft-365-defender)Microsoft 365 Defender) 。</span><span class="sxs-lookup"><span data-stu-id="ca870-141">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="ca870-142">2021 年 6 月 (平台：4.18.2106.5 |引擎：1.1.18300.4) </span><span class="sxs-lookup"><span data-stu-id="ca870-142">June-2021 (Platform: 4.18.2106.5 | Engine: 1.1.18300.4)</span></span></summary>

<span data-ttu-id="ca870-143">&ensp;安全智能更新版本 **：1.343.17.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-143">&ensp;Security intelligence update version: **1.343.17.0**</span></span>  
<span data-ttu-id="ca870-144">&ensp;发布时间 **：2021 年 6 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-144">&ensp;Released: **June 28, 2021**</span></span>  
<span data-ttu-id="ca870-145">&ensp;平台 **：4.18.2106.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-145">&ensp;Platform: **4.18.2106.5**</span></span>  
<span data-ttu-id="ca870-146">&ensp;引擎 **：1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="ca870-146">&ensp;Engine: **1.1.18300.4**</span></span>  
<span data-ttu-id="ca870-147">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="ca870-147">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-148">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-148">What's new</span></span>
- <span data-ttu-id="ca870-149">用于管理 Microsoft Defender 更新的逐步推出过程的新控件。</span><span class="sxs-lookup"><span data-stu-id="ca870-149">New controls for managing the gradual rollout process of Microsoft Defender updates.</span></span> <span data-ttu-id="ca870-150">请参阅 [管理 Microsoft Defender 更新的逐步推出过程](manage-gradual-rollout.md)。</span><span class="sxs-lookup"><span data-stu-id="ca870-150">See [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
- <span data-ttu-id="ca870-151">对行为监视引擎的改进</span><span class="sxs-lookup"><span data-stu-id="ca870-151">Improvement to the behavior monitoring engine</span></span>
- <span data-ttu-id="ca870-152">反恶意软件定义的推出改进</span><span class="sxs-lookup"><span data-stu-id="ca870-152">Improvements to the rollout of antimalware definitions</span></span>
- <span data-ttu-id="ca870-153">扩展的边缘网络事件检查</span><span class="sxs-lookup"><span data-stu-id="ca870-153">Extended Edge network event inspections</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-154">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-154">Known Issues</span></span>
<span data-ttu-id="ca870-155">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-155">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ca870-156">2021 年 5 月 (平台：4.18.2105.4 |引擎：1.1.18200.4) </span><span class="sxs-lookup"><span data-stu-id="ca870-156">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="ca870-157">&ensp;安全智能更新版本 **：1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-157">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="ca870-158">&ensp;发布时间 **：2021 年 6 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-158">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="ca870-159">&ensp;平台 **：4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="ca870-159">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="ca870-160">&ensp;引擎 **：1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="ca870-160">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="ca870-161">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="ca870-161">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-162">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-162">What's new</span></span>
- <span data-ttu-id="ca870-163">对行为 [监视的改进](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="ca870-163">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="ca870-164">修复 [了网络保护](network-protection.md) 通知筛选功能</span><span class="sxs-lookup"><span data-stu-id="ca870-164">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-165">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-165">Known Issues</span></span>
<span data-ttu-id="ca870-166">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-166">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ca870-167">2021 年 4 月 (平台：4.18.2104.14 |引擎：1.1.18100.5) </span><span class="sxs-lookup"><span data-stu-id="ca870-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="ca870-168">&ensp;安全智能更新版本 **：1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-168">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="ca870-169">&ensp;发布时间 **：2021**  年 4 月 26 日 (引擎：1.1.18100.6 发布时间 2021 年 5 月 5 日) &ensp; 平台 **：4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="ca870-169">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="ca870-170">&ensp;引擎 **：1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-170">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="ca870-171">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="ca870-171">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-172">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-172">What's new</span></span>
- <span data-ttu-id="ca870-173">其他行为监视逻辑</span><span class="sxs-lookup"><span data-stu-id="ca870-173">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="ca870-174">改进了内核模式密钥记录器检测</span><span class="sxs-lookup"><span data-stu-id="ca870-174">Improved kernel mode key logger detection</span></span>
- <span data-ttu-id="ca870-175">添加了新控件来管理 Microsoft Defender 更新的逐步 [推出过程](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="ca870-175">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="ca870-176">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-176">Known Issues</span></span>
<span data-ttu-id="ca870-177">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-177">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="ca870-178">旧版本更新：仅技术升级支持</span><span class="sxs-lookup"><span data-stu-id="ca870-178">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="ca870-179">发布新程序包版本后，仅对前两个版本的支持减少到技术支持。</span><span class="sxs-lookup"><span data-stu-id="ca870-179">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="ca870-180">低于本部分中列出的版本，并且仅提供用于技术升级支持的版本。</span><span class="sxs-lookup"><span data-stu-id="ca870-180">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<details>
<summary> <span data-ttu-id="ca870-181">2021 年 3 月 (平台：4.18.2103.7 |引擎：1.1.18000.5) </span><span class="sxs-lookup"><span data-stu-id="ca870-181">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="ca870-182">&ensp;安全智能更新版本 **：1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-182">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="ca870-183">&ensp;发布时间 **：2021 年 4 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-183">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="ca870-184">&ensp;平台 **：4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="ca870-184">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="ca870-185">&ensp;引擎 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-185">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="ca870-186">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-186">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-187">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-187">What's new</span></span>

- <span data-ttu-id="ca870-188">对行为监控引擎的改进</span><span class="sxs-lookup"><span data-stu-id="ca870-188">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="ca870-189">扩展的网络暴力攻击缓解措施</span><span class="sxs-lookup"><span data-stu-id="ca870-189">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="ca870-190">启用防篡改保护 [时的其他失败](prevent-changes-to-security-settings-with-tamper-protection.md) 篡改尝试事件生成</span><span class="sxs-lookup"><span data-stu-id="ca870-190">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-191">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-191">Known Issues</span></span>
<span data-ttu-id="ca870-192">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-192">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ca870-193">2021 年 2 月 (平台：4.18.2102.3 |引擎：1.1.17900.7) </span><span class="sxs-lookup"><span data-stu-id="ca870-193">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="ca870-194">&ensp;安全智能更新版本 **：1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-194">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="ca870-195">&ensp;已发布 **：2021 年 3 月 9 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-195">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="ca870-196">&ensp;平台 **：4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="ca870-196">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="ca870-197">&ensp;引擎 **：1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="ca870-197">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="ca870-198">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-198">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-199">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-199">What's new</span></span>

- <span data-ttu-id="ca870-200">通过防篡改保护 [改进了服务恢复](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ca870-200">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="ca870-201">扩展防篡改保护作用域</span><span class="sxs-lookup"><span data-stu-id="ca870-201">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-202">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-202">Known Issues</span></span>
<span data-ttu-id="ca870-203">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-203">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ca870-204">2021 年 1 月 (平台：4.18.2101.9 |引擎：1.1.17800.5) </span><span class="sxs-lookup"><span data-stu-id="ca870-204">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="ca870-205">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-205">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ca870-206">&ensp;发布时间 **：2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-206">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="ca870-207">&ensp;平台 **：4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="ca870-207">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="ca870-208">&ensp;引擎 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-208">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="ca870-209">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-209">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-210">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-210">What's new</span></span>

- <span data-ttu-id="ca870-211">Shellcode 攻击检测改进</span><span class="sxs-lookup"><span data-stu-id="ca870-211">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="ca870-212">提高了凭据窃取尝试的可见性</span><span class="sxs-lookup"><span data-stu-id="ca870-212">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="ca870-213">改进服务中的反Microsoft Defender 防病毒功能</span><span class="sxs-lookup"><span data-stu-id="ca870-213">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="ca870-214">改进了对 x64 ARM的支持</span><span class="sxs-lookup"><span data-stu-id="ca870-214">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="ca870-215">修复：EDR执行初始检测后阻止通知仍保留在威胁历史记录中</span><span class="sxs-lookup"><span data-stu-id="ca870-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-216">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-216">Known Issues</span></span>
<span data-ttu-id="ca870-217">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-217">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ca870-218">2020 年 11 月 (平台：4.18.2011.6 |引擎：1.1.17700.4) </span><span class="sxs-lookup"><span data-stu-id="ca870-218">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="ca870-219">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-219">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ca870-220">&ensp;发布时间 **：2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-220">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="ca870-221">&ensp;平台 **：4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="ca870-221">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="ca870-222">&ensp;引擎 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ca870-222">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="ca870-223">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-223">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-224">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-224">What's new</span></span>

- <span data-ttu-id="ca870-225">改进 [的 SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 状态支持日志记录</span><span class="sxs-lookup"><span data-stu-id="ca870-225">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-226">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-226">Known Issues</span></span>
<span data-ttu-id="ca870-227">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-227">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ca870-228">2020 年 10 月 (平台：4.18.2010.7 |引擎：1.1.17600.5) </span><span class="sxs-lookup"><span data-stu-id="ca870-228">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="ca870-229">&ensp;安全智能更新版本 **：1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-229">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="ca870-230">&ensp;发布时间 **：2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-230">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="ca870-231">&ensp;平台 **：4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="ca870-231">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="ca870-232">&ensp;引擎 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-232">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="ca870-233">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-233">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-234">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-234">What's new</span></span>

- <span data-ttu-id="ca870-235">特殊威胁类别的新说明</span><span class="sxs-lookup"><span data-stu-id="ca870-235">New descriptions for special threat categories</span></span>
- <span data-ttu-id="ca870-236">改进的模拟功能</span><span class="sxs-lookup"><span data-stu-id="ca870-236">Improved emulation capabilities</span></span>
- <span data-ttu-id="ca870-237">改进了主机地址允许/阻止功能</span><span class="sxs-lookup"><span data-stu-id="ca870-237">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="ca870-238">Defender CSP 中用于忽略本地用户排除项合并的新选项</span><span class="sxs-lookup"><span data-stu-id="ca870-238">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-239">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-239">Known Issues</span></span>

<span data-ttu-id="ca870-240">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-240">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ca870-241">2020 年 9 月 (平台：4.18.2009.7 |引擎：1.1.17500.4) </span><span class="sxs-lookup"><span data-stu-id="ca870-241">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="ca870-242">&ensp;安全智能更新版本 **：1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-242">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="ca870-243">&ensp;发布时间 **：2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-243">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="ca870-244">&ensp;平台 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ca870-244">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="ca870-245">&ensp;引擎 **：1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="ca870-245">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="ca870-246">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-247">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-247">What's new</span></span>

- <span data-ttu-id="ca870-248">需要管理员权限才能还原隔离中的文件</span><span class="sxs-lookup"><span data-stu-id="ca870-248">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="ca870-249">XML 格式事件现在受支持</span><span class="sxs-lookup"><span data-stu-id="ca870-249">XML formatted events are now supported</span></span>
- <span data-ttu-id="ca870-250">忽略排除合并的云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="ca870-250">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="ca870-251">用于：</span><span class="sxs-lookup"><span data-stu-id="ca870-251">New management interfaces for:</span></span>
   - <span data-ttu-id="ca870-252">UDP 检查</span><span class="sxs-lookup"><span data-stu-id="ca870-252">UDP Inspection</span></span>
   - <span data-ttu-id="ca870-253">Server 2019 上的网络保护</span><span class="sxs-lookup"><span data-stu-id="ca870-253">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="ca870-254">网络保护的 IP 地址排除项</span><span class="sxs-lookup"><span data-stu-id="ca870-254">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="ca870-255">改进了对 TPM 测量的可见性</span><span class="sxs-lookup"><span data-stu-id="ca870-255">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="ca870-256">改进了 Office VBA 模块扫描</span><span class="sxs-lookup"><span data-stu-id="ca870-256">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-257">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-257">Known Issues</span></span>

<span data-ttu-id="ca870-258">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-258">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="ca870-259">2020 年 8 月 (平台：4.18.2008.9 |引擎：1.1.17400.5) </span><span class="sxs-lookup"><span data-stu-id="ca870-259">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="ca870-260">&ensp;安全智能更新版本 **：1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-260">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="ca870-261">&ensp;发布时间 **：2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-261">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="ca870-262">&ensp;平台 **：4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="ca870-262">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="ca870-263">&ensp;引擎 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-263">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="ca870-264">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-264">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="ca870-265">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-265">What's new</span></span>

- <span data-ttu-id="ca870-266">添加更多遥测事件</span><span class="sxs-lookup"><span data-stu-id="ca870-266">Add more telemetry events</span></span>
- <span data-ttu-id="ca870-267">改进了扫描事件遥测</span><span class="sxs-lookup"><span data-stu-id="ca870-267">Improved scan event telemetry</span></span>
- <span data-ttu-id="ca870-268">改进了内存扫描行为监视</span><span class="sxs-lookup"><span data-stu-id="ca870-268">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="ca870-269">改进的宏流扫描</span><span class="sxs-lookup"><span data-stu-id="ca870-269">Improved macro streams scanning</span></span>
- <span data-ttu-id="ca870-270">已 `AMRunningMode` 添加到 Get-MpComputerStatus PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="ca870-270">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="ca870-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="ca870-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="ca870-272">Microsoft Defender 防病毒检测到其他防病毒程序时自动关闭自身。</span><span class="sxs-lookup"><span data-stu-id="ca870-272">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="ca870-273">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-273">Known Issues</span></span>
<span data-ttu-id="ca870-274">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-274">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ca870-275">2020 年 7 月 (平台：4.18.2007.8 |引擎：1.1.17300.4) </span><span class="sxs-lookup"><span data-stu-id="ca870-275">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="ca870-276">&ensp;安全智能更新版本 **：1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-276">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="ca870-277">&ensp;发布时间 **：2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-277">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="ca870-278">&ensp;平台 **：4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="ca870-278">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="ca870-279">&ensp;引擎 **：1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="ca870-279">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="ca870-280">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-280">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-281">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-281">What's new</span></span>

- <span data-ttu-id="ca870-282">改进的 BITS 遥测</span><span class="sxs-lookup"><span data-stu-id="ca870-282">Improved telemetry for BITS</span></span>
- <span data-ttu-id="ca870-283">改进的验证码代码签名证书验证</span><span class="sxs-lookup"><span data-stu-id="ca870-283">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-284">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-284">Known Issues</span></span>
<span data-ttu-id="ca870-285">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-285">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ca870-286">2020 年 6 月 (平台：4.18.2006.10 |引擎：1.1.17200.2) </span><span class="sxs-lookup"><span data-stu-id="ca870-286">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="ca870-287">&ensp;安全智能更新版本 **：1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-287">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="ca870-288">&ensp;发布时间 **：2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-288">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="ca870-289">&ensp;平台 **：4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="ca870-289">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="ca870-290">&ensp;引擎 **：1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="ca870-290">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="ca870-291">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-291">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-292">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-292">What's new</span></span>

- <span data-ttu-id="ca870-293">指定支持 [日志的位置的可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="ca870-293">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="ca870-294">在被动模式下跳过主动的捕获扫描。</span><span class="sxs-lookup"><span data-stu-id="ca870-294">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="ca870-295">允许 Defender 更新按流量计费的连接</span><span class="sxs-lookup"><span data-stu-id="ca870-295">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="ca870-296">修复了禁用缓存时的性能调整</span><span class="sxs-lookup"><span data-stu-id="ca870-296">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="ca870-297">修复了注册表查询</span><span class="sxs-lookup"><span data-stu-id="ca870-297">Fixed registry query</span></span> 
- <span data-ttu-id="ca870-298">修复了 ADMX 中的扫描时间随机化</span><span class="sxs-lookup"><span data-stu-id="ca870-298">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-299">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-299">Known Issues</span></span>
<span data-ttu-id="ca870-300">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-300">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ca870-301">2020 年 5 月 (平台：4.18.2005.4 |引擎：1.1.17100.2) </span><span class="sxs-lookup"><span data-stu-id="ca870-301">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="ca870-302">&ensp;安全智能更新版本 **：1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-302">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="ca870-303">&ensp;发布时间 **：2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-303">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="ca870-304">&ensp;平台 **：4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="ca870-304">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="ca870-305">&ensp;引擎 **：1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="ca870-305">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="ca870-306">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-306">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-307">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-307">What's new</span></span>

- <span data-ttu-id="ca870-308">改进了扫描事件的日志记录</span><span class="sxs-lookup"><span data-stu-id="ca870-308">Improved logging for scan events</span></span>
- <span data-ttu-id="ca870-309">改进了用户模式崩溃处理。</span><span class="sxs-lookup"><span data-stu-id="ca870-309">Improved user mode crash handling.</span></span>
- <span data-ttu-id="ca870-310">添加了防篡改保护的事件跟踪</span><span class="sxs-lookup"><span data-stu-id="ca870-310">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="ca870-311">修复了 AMSI 示例提交</span><span class="sxs-lookup"><span data-stu-id="ca870-311">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="ca870-312">修复了 AMSI 云阻止</span><span class="sxs-lookup"><span data-stu-id="ca870-312">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="ca870-313">修复了安全更新安装日志</span><span class="sxs-lookup"><span data-stu-id="ca870-313">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-314">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-314">Known Issues</span></span>
<span data-ttu-id="ca870-315">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-315">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ca870-316">2020 年 4 月 (平台：4.18.2004.6 |引擎：1.1.17000.2) </span><span class="sxs-lookup"><span data-stu-id="ca870-316">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="ca870-317">&ensp;安全智能更新版本 **：1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-317">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="ca870-318">&ensp;发布时间 **：2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-318">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="ca870-319">&ensp;平台 **：4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="ca870-319">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="ca870-320">&ensp;引擎 **：1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="ca870-320">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="ca870-321">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-321">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-322">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-322">What's new</span></span>
- <span data-ttu-id="ca870-323">WDfilter 改进</span><span class="sxs-lookup"><span data-stu-id="ca870-323">WDfilter improvements</span></span>
- <span data-ttu-id="ca870-324">向攻击面减少检测事件添加更多可操作事件数据</span><span class="sxs-lookup"><span data-stu-id="ca870-324">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="ca870-325">诊断数据和 WMI 中的固定版本信息</span><span class="sxs-lookup"><span data-stu-id="ca870-325">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="ca870-326">修复了平台更新后 UI 中的平台版本不正确</span><span class="sxs-lookup"><span data-stu-id="ca870-326">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="ca870-327">用于无文件威胁防护的动态 URL intel</span><span class="sxs-lookup"><span data-stu-id="ca870-327">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="ca870-328">UEFI 扫描功能</span><span class="sxs-lookup"><span data-stu-id="ca870-328">UEFI scan capability</span></span>
- <span data-ttu-id="ca870-329">扩展更新日志记录</span><span class="sxs-lookup"><span data-stu-id="ca870-329">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="ca870-330">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-330">Known Issues</span></span>
<span data-ttu-id="ca870-331">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-331">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ca870-332">2020 年 3 月 (平台：4.18.2003.8 |引擎：1.1.16900.2) </span><span class="sxs-lookup"><span data-stu-id="ca870-332">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="ca870-333">&ensp;安全智能更新版本 **：1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-333">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="ca870-334">&ensp;已发布 **：2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-334">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="ca870-335">&ensp;平台 **：4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="ca870-335">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="ca870-336">&ensp;引擎 **：1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="ca870-336">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="ca870-337">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-337">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ca870-338">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-338">What's new</span></span>

- <span data-ttu-id="ca870-339">添加到[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 限制选项</span><span class="sxs-lookup"><span data-stu-id="ca870-339">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="ca870-340">改进诊断功能</span><span class="sxs-lookup"><span data-stu-id="ca870-340">Improve diagnostic capability</span></span>
- <span data-ttu-id="ca870-341">将安全智能超时 (5 分钟) </span><span class="sxs-lookup"><span data-stu-id="ca870-341">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="ca870-342">扩展 AMSI 引擎内部日志功能</span><span class="sxs-lookup"><span data-stu-id="ca870-342">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="ca870-343">改进进程阻止通知</span><span class="sxs-lookup"><span data-stu-id="ca870-343">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ca870-344">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-344">Known Issues</span></span>
<span data-ttu-id="ca870-345">[**Fixed**]Microsoft Defender 防病毒扫描时跳过文件。</span><span class="sxs-lookup"><span data-stu-id="ca870-345">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="ca870-346">2020 年 2 月 (平台： - |引擎：1.1.16800.2) </span><span class="sxs-lookup"><span data-stu-id="ca870-346">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="ca870-347">&ensp;安全智能更新版本 **：1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="ca870-347">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="ca870-348">&ensp;发布时间 **：2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-348">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="ca870-349">&ensp;平台/客户端： **-**</span><span class="sxs-lookup"><span data-stu-id="ca870-349">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="ca870-350">&ensp;引擎 **：1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="ca870-350">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="ca870-351">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-351">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ca870-352">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-352">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="ca870-353">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-353">Known Issues</span></span>
<span data-ttu-id="ca870-354">无已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-354">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ca870-355">2020 年 1 月 (平台：4.18.2001.10 |引擎：1.1.16700.2) </span><span class="sxs-lookup"><span data-stu-id="ca870-355">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="ca870-356">安全智能更新版本 **：1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-356">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="ca870-357">发布时间 **：2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-357">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="ca870-358">平台/客户端 **：4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="ca870-358">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="ca870-359">引擎 **：1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="ca870-359">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="ca870-360">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="ca870-360">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ca870-361">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-361">What's new</span></span>

- <span data-ttu-id="ca870-362">修复了 WS2016 上的 BSOD 与Exchange</span><span class="sxs-lookup"><span data-stu-id="ca870-362">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="ca870-363">当 TMP 重定向到网络路径时支持平台更新</span><span class="sxs-lookup"><span data-stu-id="ca870-363">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="ca870-364">平台和引擎版本已添加到 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ca870-364">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="ca870-365">将紧急签名更新扩展到 [被动模式](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ca870-365">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="ca870-366">修复 4.18.1911.3 挂起</span><span class="sxs-lookup"><span data-stu-id="ca870-366">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ca870-367">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-367">Known Issues</span></span>

<span data-ttu-id="ca870-368">[**修复**][使用新式待机](/windows-hardware/design/device-experiences/modern-standby)模式的设备可能会遇到与 Windows Defender 筛选器驱动程序的挂起，导致保护差距。</span><span class="sxs-lookup"><span data-stu-id="ca870-368">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="ca870-369">受影响的计算机向客户显示尚未更新到最新的反恶意软件平台。</span><span class="sxs-lookup"><span data-stu-id="ca870-369">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="ca870-370">此更新为：</span><span class="sxs-lookup"><span data-stu-id="ca870-370">This update is:</span></span>
> - <span data-ttu-id="ca870-371">运行较低版本的平台以支持 SHA2 的 RS1 设备需要;</span><span class="sxs-lookup"><span data-stu-id="ca870-371">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="ca870-372">对于有挂起问题的系统，具有重新启动标志;</span><span class="sxs-lookup"><span data-stu-id="ca870-372">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="ca870-373">在 2020 年 4 月重新发布，并且不会被更新的更新所取代，以保持将来的可用性;</span><span class="sxs-lookup"><span data-stu-id="ca870-373">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="ca870-374">因重启要求而分类为更新;和</span><span class="sxs-lookup"><span data-stu-id="ca870-374">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="ca870-375">仅提供与 Windows Update 一[起提供](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="ca870-375">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ca870-376">2019 年 11 月 (平台：4.18.1911.3 |引擎：1.1.16600.7) </span><span class="sxs-lookup"><span data-stu-id="ca870-376">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="ca870-377">安全智能更新版本 **：1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-377">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="ca870-378">发布时间 **：2019 年 12 月 7 日**</span><span class="sxs-lookup"><span data-stu-id="ca870-378">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="ca870-379">平台 **：4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="ca870-379">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="ca870-380">引擎 **：1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="ca870-380">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="ca870-381">支持阶段： **不支持**</span><span class="sxs-lookup"><span data-stu-id="ca870-381">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="ca870-382">最近更新</span><span class="sxs-lookup"><span data-stu-id="ca870-382">What's new</span></span>

- <span data-ttu-id="ca870-383">修复了 MpCmdRun 跟踪级别</span><span class="sxs-lookup"><span data-stu-id="ca870-383">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="ca870-384">修复了 WDFilter 版本信息</span><span class="sxs-lookup"><span data-stu-id="ca870-384">Fixed WDFilter version info</span></span>
- <span data-ttu-id="ca870-385">改进 PUA (通知) </span><span class="sxs-lookup"><span data-stu-id="ca870-385">Improve notifications (PUA)</span></span>
- <span data-ttu-id="ca870-386">添加 MRT 日志以支持文件</span><span class="sxs-lookup"><span data-stu-id="ca870-386">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ca870-387">已知问题</span><span class="sxs-lookup"><span data-stu-id="ca870-387">Known Issues</span></span>
<span data-ttu-id="ca870-388">安装此更新后，设备需要跳转程序包 4.18.2001.10 才能更新到最新的平台版本。</span><span class="sxs-lookup"><span data-stu-id="ca870-388">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="ca870-389">Microsoft Defender 防病毒平台支持</span><span class="sxs-lookup"><span data-stu-id="ca870-389">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="ca870-390">平台和引擎更新按月提供。</span><span class="sxs-lookup"><span data-stu-id="ca870-390">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="ca870-391">若要完全受支持，请及时了解最新的平台更新。</span><span class="sxs-lookup"><span data-stu-id="ca870-391">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="ca870-392">我们的支持结构是动态的，根据最新平台版本的可用性，将发展为两个阶段：</span><span class="sxs-lookup"><span data-stu-id="ca870-392">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="ca870-393">**安全和关键更新服务阶段** - 运行最新平台版本时，你将有资格接收反恶意软件平台的安全和关键更新。</span><span class="sxs-lookup"><span data-stu-id="ca870-393">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="ca870-394">**技术支持 (仅在)** 阶段 - 发布新平台版本后，对早期版本 (N-2) 的支持将仅减少为技术支持。</span><span class="sxs-lookup"><span data-stu-id="ca870-394">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="ca870-395">不再支持 N-2 之前的平台版本。\*</span><span class="sxs-lookup"><span data-stu-id="ca870-395">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="ca870-396">\*将继续为从 Windows 10 版本升级提供技术支持 (请参阅[Windows 10](#platform-version-included-with-windows-10-releases)版本中包含的平台版本) 到最新平台版本。</span><span class="sxs-lookup"><span data-stu-id="ca870-396">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="ca870-397">在技术支持 (仅在) 阶段，商业上合理的支持事件将通过 Microsoft 客户服务 & 支持和 Microsoft 的托管支持产品/服务 (如 Premier Support) 提供。</span><span class="sxs-lookup"><span data-stu-id="ca870-397">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="ca870-398">如果支持事件需要上报开发以进一步提供指导、需要非安全更新或需要安全更新，将要求客户升级到最新平台版本或中间 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="ca870-398">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="ca870-399">版本中包含的平台Windows 10版本</span><span class="sxs-lookup"><span data-stu-id="ca870-399">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="ca870-400">下表提供了最新 Microsoft Defender 防病毒 版本附带的 Microsoft Defender 防病毒 Windows 10 平台和引擎版本：</span><span class="sxs-lookup"><span data-stu-id="ca870-400">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="ca870-401">Windows 10发布</span><span class="sxs-lookup"><span data-stu-id="ca870-401">Windows 10 release</span></span>  |<span data-ttu-id="ca870-402">平台版本</span><span class="sxs-lookup"><span data-stu-id="ca870-402">Platform version</span></span>  |<span data-ttu-id="ca870-403">引擎版本</span><span class="sxs-lookup"><span data-stu-id="ca870-403">Engine version</span></span> |<span data-ttu-id="ca870-404">支持阶段</span><span class="sxs-lookup"><span data-stu-id="ca870-404">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="ca870-405">2004 (20H1/20H2) </span><span class="sxs-lookup"><span data-stu-id="ca870-405">2004  (20H1/20H2)</span></span> |<span data-ttu-id="ca870-406">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="ca870-406">4.18.1909.6</span></span> |<span data-ttu-id="ca870-407">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="ca870-407">1.1.17000.2</span></span> | <span data-ttu-id="ca870-408">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="ca870-408">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ca870-409">1909 (19H2) </span><span class="sxs-lookup"><span data-stu-id="ca870-409">1909  (19H2)</span></span> |<span data-ttu-id="ca870-410">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ca870-410">4.18.1902.5</span></span> |<span data-ttu-id="ca870-411">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="ca870-411">1.1.16700.3</span></span> | <span data-ttu-id="ca870-412">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="ca870-412">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ca870-413">1903 (19H1) </span><span class="sxs-lookup"><span data-stu-id="ca870-413">1903  (19H1)</span></span> |<span data-ttu-id="ca870-414">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ca870-414">4.18.1902.5</span></span> |<span data-ttu-id="ca870-415">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="ca870-415">1.1.15600.4</span></span> | <span data-ttu-id="ca870-416">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="ca870-416">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ca870-417">1809 (RS5) </span><span class="sxs-lookup"><span data-stu-id="ca870-417">1809  (RS5)</span></span> |<span data-ttu-id="ca870-418">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="ca870-418">4.18.1807.18075</span></span> |<span data-ttu-id="ca870-419">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="ca870-419">1.1.15000.2</span></span> | <span data-ttu-id="ca870-420">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="ca870-420">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ca870-421">1803 (RS4) </span><span class="sxs-lookup"><span data-stu-id="ca870-421">1803  (RS4)</span></span> |<span data-ttu-id="ca870-422">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="ca870-422">4.13.17134.1</span></span> |<span data-ttu-id="ca870-423">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="ca870-423">1.1.14600.4</span></span> | <span data-ttu-id="ca870-424">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="ca870-424">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ca870-425">1709 (RS3) </span><span class="sxs-lookup"><span data-stu-id="ca870-425">1709  (RS3)</span></span> |<span data-ttu-id="ca870-426">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="ca870-426">4.12.16299.15</span></span> |<span data-ttu-id="ca870-427">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="ca870-427">1.1.14104.0</span></span> | <span data-ttu-id="ca870-428">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="ca870-428">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ca870-429">1703 (RS2) </span><span class="sxs-lookup"><span data-stu-id="ca870-429">1703  (RS2)</span></span> |<span data-ttu-id="ca870-430">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="ca870-430">4.11.15603.2</span></span> |<span data-ttu-id="ca870-431">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="ca870-431">1.1.13504.0</span></span> | <span data-ttu-id="ca870-432">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="ca870-432">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ca870-433">1607 (RS1) </span><span class="sxs-lookup"><span data-stu-id="ca870-433">1607 (RS1)</span></span> |<span data-ttu-id="ca870-434">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="ca870-434">4.10.14393.3683</span></span> |<span data-ttu-id="ca870-435">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="ca870-435">1.1.12805.0</span></span> | <span data-ttu-id="ca870-436">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="ca870-436">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="ca870-437">有关Windows 10的信息，请参阅生命周期[Windows表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="ca870-437">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="ca870-438">DISM 部署映像服务和管理 (更新) </span><span class="sxs-lookup"><span data-stu-id="ca870-438">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="ca870-439">我们建议使用最新的防病毒和反恶意软件更新更新 Windows 10 (Enterprise、Pro 和家庭版) 、Windows Server 2019 和 Windows Server 2016 操作系统安装映像。</span><span class="sxs-lookup"><span data-stu-id="ca870-439">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="ca870-440">使操作系统安装映像保持最新有助于避免保护差距。</span><span class="sxs-lookup"><span data-stu-id="ca870-440">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="ca870-441">有关详细信息，请参阅适用于操作系统[安装映像Windows Microsoft Defender 更新](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="ca870-441">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="ca870-442">1.1.2107.02</span><span class="sxs-lookup"><span data-stu-id="ca870-442">1.1.2107.02</span></span></summary>

<span data-ttu-id="ca870-443">&ensp;程序包版本 **：1.1.2107.02**  </span><span class="sxs-lookup"><span data-stu-id="ca870-443">&ensp;Package version: **1.1.2107.02**  </span></span>  
<span data-ttu-id="ca870-444">&ensp;平台版本 **：4.18.2105.5** </span><span class="sxs-lookup"><span data-stu-id="ca870-444">&ensp;Platform version: **4.18.2105.5** </span></span>  
<span data-ttu-id="ca870-445">&ensp;引擎版本 **：1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="ca870-445">&ensp;Engine version: **1.1.18300.4**</span></span>  
<span data-ttu-id="ca870-446">&ensp;签名版本 **：1.343.658.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-446">&ensp;Signature version: **1.343.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ca870-447">修补程序</span><span class="sxs-lookup"><span data-stu-id="ca870-447">Fixes</span></span>
- <span data-ttu-id="ca870-448">无</span><span class="sxs-lookup"><span data-stu-id="ca870-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ca870-449">其他信息</span><span class="sxs-lookup"><span data-stu-id="ca870-449">Additional information</span></span>
- <span data-ttu-id="ca870-450">无</span><span class="sxs-lookup"><span data-stu-id="ca870-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ca870-451">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="ca870-451">1.1.2106.01</span></span></summary>

<span data-ttu-id="ca870-452">&ensp;程序包版本 **：1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="ca870-452">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="ca870-453">&ensp;平台版本 **：4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="ca870-453">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="ca870-454">&ensp;引擎版本 **：1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="ca870-454">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="ca870-455">&ensp;签名版本 **：1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-455">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ca870-456">修补程序</span><span class="sxs-lookup"><span data-stu-id="ca870-456">Fixes</span></span>
- <span data-ttu-id="ca870-457">无</span><span class="sxs-lookup"><span data-stu-id="ca870-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ca870-458">其他信息</span><span class="sxs-lookup"><span data-stu-id="ca870-458">Additional information</span></span>
- <span data-ttu-id="ca870-459">无</span><span class="sxs-lookup"><span data-stu-id="ca870-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ca870-460">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="ca870-460">1.1.2105.01</span></span></summary>

<span data-ttu-id="ca870-461">&ensp;程序包版本 **：1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="ca870-461">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="ca870-462">&ensp;平台版本 **：4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="ca870-462">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="ca870-463">&ensp;引擎版本 **：1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="ca870-463">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="ca870-464">&ensp;签名版本 **：1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-464">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ca870-465">修补程序</span><span class="sxs-lookup"><span data-stu-id="ca870-465">Fixes</span></span>
- <span data-ttu-id="ca870-466">无</span><span class="sxs-lookup"><span data-stu-id="ca870-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ca870-467">其他信息</span><span class="sxs-lookup"><span data-stu-id="ca870-467">Additional information</span></span>
- <span data-ttu-id="ca870-468">无</span><span class="sxs-lookup"><span data-stu-id="ca870-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ca870-469">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="ca870-469">1.1.2104.01</span></span></summary>

<span data-ttu-id="ca870-470">&ensp;程序包版本 **：1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="ca870-470">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="ca870-471">&ensp;平台版本 **：4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="ca870-471">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="ca870-472">&ensp;引擎版本 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-472">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="ca870-473">&ensp;签名版本 **：1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-473">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ca870-474">修补程序</span><span class="sxs-lookup"><span data-stu-id="ca870-474">Fixes</span></span>
- <span data-ttu-id="ca870-475">无</span><span class="sxs-lookup"><span data-stu-id="ca870-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ca870-476">其他信息</span><span class="sxs-lookup"><span data-stu-id="ca870-476">Additional information</span></span>
- <span data-ttu-id="ca870-477">无</span><span class="sxs-lookup"><span data-stu-id="ca870-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ca870-478">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="ca870-478">1.1.2103.01</span></span></summary>

<span data-ttu-id="ca870-479">&ensp;程序包版本 **：1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="ca870-479">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="ca870-480">&ensp;平台版本 **：4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="ca870-480">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="ca870-481">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-481">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ca870-482">&ensp;签名版本 **：1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-482">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ca870-483">修补程序</span><span class="sxs-lookup"><span data-stu-id="ca870-483">Fixes</span></span>
- <span data-ttu-id="ca870-484">无</span><span class="sxs-lookup"><span data-stu-id="ca870-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ca870-485">其他信息</span><span class="sxs-lookup"><span data-stu-id="ca870-485">Additional information</span></span>
- <span data-ttu-id="ca870-486">无</span><span class="sxs-lookup"><span data-stu-id="ca870-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ca870-487">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="ca870-487">1.1.2102.03</span></span></summary>

<span data-ttu-id="ca870-488">&ensp;程序包版本 **：1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="ca870-488">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="ca870-489">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ca870-489">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ca870-490">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-490">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ca870-491">&ensp;签名版本 **：1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-491">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ca870-492">修补程序</span><span class="sxs-lookup"><span data-stu-id="ca870-492">Fixes</span></span>
- <span data-ttu-id="ca870-493">无</span><span class="sxs-lookup"><span data-stu-id="ca870-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ca870-494">其他信息</span><span class="sxs-lookup"><span data-stu-id="ca870-494">Additional information</span></span>
- <span data-ttu-id="ca870-495">无</span><span class="sxs-lookup"><span data-stu-id="ca870-495">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ca870-496">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="ca870-496">1.1.2101.02</span></span></summary>

<span data-ttu-id="ca870-497">&ensp;程序包版本 **：1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="ca870-497">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="ca870-498">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ca870-498">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ca870-499">&ensp;引擎版本 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ca870-499">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="ca870-500">&ensp;签名版本 **：1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-500">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ca870-501">修补程序</span><span class="sxs-lookup"><span data-stu-id="ca870-501">Fixes</span></span>
- <span data-ttu-id="ca870-502">无</span><span class="sxs-lookup"><span data-stu-id="ca870-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ca870-503">其他信息</span><span class="sxs-lookup"><span data-stu-id="ca870-503">Additional information</span></span>
- <span data-ttu-id="ca870-504">无</span><span class="sxs-lookup"><span data-stu-id="ca870-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ca870-505">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="ca870-505">1.1.2012.01</span></span></summary>

<span data-ttu-id="ca870-506">&ensp;程序包版本 **：1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="ca870-506">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="ca870-507">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ca870-507">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ca870-508">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-508">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ca870-509">&ensp;签名版本 **：1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-509">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ca870-510">修补程序</span><span class="sxs-lookup"><span data-stu-id="ca870-510">Fixes</span></span>
- <span data-ttu-id="ca870-511">无</span><span class="sxs-lookup"><span data-stu-id="ca870-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ca870-512">其他信息</span><span class="sxs-lookup"><span data-stu-id="ca870-512">Additional information</span></span>
- <span data-ttu-id="ca870-513">无</span><span class="sxs-lookup"><span data-stu-id="ca870-513">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ca870-514">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="ca870-514">1.1.2011.02</span></span></summary>

<span data-ttu-id="ca870-515">&ensp;程序包版本 **：1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="ca870-515">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="ca870-516">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ca870-516">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ca870-517">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-517">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ca870-518">&ensp;签名版本 **：1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-518">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ca870-519">修补程序</span><span class="sxs-lookup"><span data-stu-id="ca870-519">Fixes</span></span>
- <span data-ttu-id="ca870-520">无</span><span class="sxs-lookup"><span data-stu-id="ca870-520">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ca870-521">其他信息</span><span class="sxs-lookup"><span data-stu-id="ca870-521">Additional information</span></span>
- <span data-ttu-id="ca870-522">刷新Microsoft Defender 防病毒签名</span><span class="sxs-lookup"><span data-stu-id="ca870-522">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ca870-523">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="ca870-523">1.1.2011.01</span></span></summary>

<span data-ttu-id="ca870-524">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ca870-524">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ca870-525">&ensp;平台版本 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ca870-525">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="ca870-526">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-526">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ca870-527">&ensp;签名版本 **：1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-527">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ca870-528">修补程序</span><span class="sxs-lookup"><span data-stu-id="ca870-528">Fixes</span></span>
- <span data-ttu-id="ca870-529">无</span><span class="sxs-lookup"><span data-stu-id="ca870-529">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ca870-530">其他信息</span><span class="sxs-lookup"><span data-stu-id="ca870-530">Additional information</span></span>
- <span data-ttu-id="ca870-531">无</span><span class="sxs-lookup"><span data-stu-id="ca870-531">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ca870-532">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="ca870-532">1.1.2009.10</span></span></summary>

<span data-ttu-id="ca870-533">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ca870-533">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ca870-534">&ensp;平台版本 **：4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="ca870-534">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="ca870-535">&ensp;引擎版本 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ca870-535">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="ca870-536">&ensp;签名版本 **：1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="ca870-536">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ca870-537">修补程序</span><span class="sxs-lookup"><span data-stu-id="ca870-537">Fixes</span></span>
- <span data-ttu-id="ca870-538">无</span><span class="sxs-lookup"><span data-stu-id="ca870-538">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ca870-539">其他信息</span><span class="sxs-lookup"><span data-stu-id="ca870-539">Additional information</span></span>
- <span data-ttu-id="ca870-540">添加了对 Windows 10 RS1 或更高版本操作系统安装映像的支持。</span><span class="sxs-lookup"><span data-stu-id="ca870-540">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="ca870-541">其他资源</span><span class="sxs-lookup"><span data-stu-id="ca870-541">Additional resources</span></span>

| <span data-ttu-id="ca870-542">文章</span><span class="sxs-lookup"><span data-stu-id="ca870-542">Article</span></span> | <span data-ttu-id="ca870-543">说明</span><span class="sxs-lookup"><span data-stu-id="ca870-543">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="ca870-544">适用于操作系统安装映像Windows Microsoft Defender 更新</span><span class="sxs-lookup"><span data-stu-id="ca870-544">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="ca870-545">查看适用于操作系统安装映像的反恶意软件更新程序包 (WIM 和 VHD 文件) 。</span><span class="sxs-lookup"><span data-stu-id="ca870-545">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="ca870-546">获取 Microsoft Defender 防病毒、Windows 10 (Enterprise、Pro、家庭版) 、Windows Server 2019 Windows Server 2016更新。</span><span class="sxs-lookup"><span data-stu-id="ca870-546">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="ca870-547">管理保护更新的下载和应用方式</span><span class="sxs-lookup"><span data-stu-id="ca870-547">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ca870-548">保护更新可以通过多个源提供。</span><span class="sxs-lookup"><span data-stu-id="ca870-548">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="ca870-549">管理何时应下载和应用保护更新</span><span class="sxs-lookup"><span data-stu-id="ca870-549">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="ca870-550">你可以计划应下载保护更新的时间。</span><span class="sxs-lookup"><span data-stu-id="ca870-550">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="ca870-551">管理过期终结点的更新</span><span class="sxs-lookup"><span data-stu-id="ca870-551">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="ca870-552">如果终结点错过更新或计划扫描，可以在用户下次登录时强制进行更新或扫描。</span><span class="sxs-lookup"><span data-stu-id="ca870-552">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="ca870-553">管理基于事件的强制更新</span><span class="sxs-lookup"><span data-stu-id="ca870-553">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ca870-554">你可以将保护更新设置为在启动时或在某些云提供的保护事件之后下载。</span><span class="sxs-lookup"><span data-stu-id="ca870-554">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="ca870-555">管理移动设备和虚拟机 （VM） 的更新</span><span class="sxs-lookup"><span data-stu-id="ca870-555">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="ca870-556">你可以指定对移动设备和虚拟机特别有用的设置，例如是否应该使用电池电源进行更新。</span><span class="sxs-lookup"><span data-stu-id="ca870-556">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
