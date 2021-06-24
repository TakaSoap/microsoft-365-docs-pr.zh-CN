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
ms.date: 06/23/2021
ms.openlocfilehash: 88be32a2c1e9204629682ec678f80ab6daf701f4
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105328"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="d2b6c-104">管理Microsoft Defender 防病毒更新并应用基线</span><span class="sxs-lookup"><span data-stu-id="d2b6c-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="d2b6c-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-105">**Applies to:**</span></span>

- [<span data-ttu-id="d2b6c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d2b6c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="d2b6c-107">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d2b6c-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="d2b6c-108">保持Microsoft Defender 防病毒保持最新状态对于确保你的设备具有抵御新的恶意软件和攻击技术所需的最新技术和功能至关重要。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="d2b6c-109">确保更新防病毒保护，即使Microsoft Defender 防病毒处于被动[模式。](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="d2b6c-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="d2b6c-110">有两种类型的更新与使Microsoft Defender 防病毒保持最新有关：</span><span class="sxs-lookup"><span data-stu-id="d2b6c-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="d2b6c-111">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-111">Security intelligence updates</span></span>
- <span data-ttu-id="d2b6c-112">产品更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="d2b6c-113">To see the most current engine， platform， and signature date， visit the [Security intelligence updates for Microsoft Defender 防病毒 other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="d2b6c-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="d2b6c-114">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-114">Security intelligence updates</span></span>

<span data-ttu-id="d2b6c-115">Microsoft Defender 防病毒云[提供的](cloud-protection-microsoft-defender-antivirus.md)保护 (也称为 Microsoft 高级保护服务或 MAPS) 并定期下载安全智能更新以提供保护。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="d2b6c-116">更新以以下 KB 编号发布：</span><span class="sxs-lookup"><span data-stu-id="d2b6c-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="d2b6c-117">Microsoft Defender 防病毒：KB2267602</span><span class="sxs-lookup"><span data-stu-id="d2b6c-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="d2b6c-118">System Center Endpoint Protection：KB2461484</span><span class="sxs-lookup"><span data-stu-id="d2b6c-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="d2b6c-119">云提供的保护始终打开，并且需要与 Internet 的活动连接以正常运行。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="d2b6c-120">安全智能更新按计划节奏进行， (策略策略配置) 。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="d2b6c-121">有关详细信息，请参阅使用[Microsoft 云提供的Microsoft Defender 防病毒。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d2b6c-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="d2b6c-122">有关最近安全智能更新的列表，请参阅安全智能更新[Microsoft Defender 防病毒和其他 Microsoft 反恶意软件](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="d2b6c-123">引擎更新包含在安全智能更新中，并按月发布。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="d2b6c-124">产品更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-124">Product updates</span></span>

<span data-ttu-id="d2b6c-125">Microsoft Defender 防病毒需要每月更新 [ (KB4052623](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform))  (称为平台更新 *) ，* 并且将在 Windows 10 版本旁边接收主要功能更新。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="d2b6c-126">可以通过以下方法之一管理更新的分发：</span><span class="sxs-lookup"><span data-stu-id="d2b6c-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="d2b6c-127">WindowsWSUS (服务器更新) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="d2b6c-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d2b6c-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="d2b6c-129">你用于部署 Microsoft 和Windows终结点更新的常用方法。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="d2b6c-130">有关详细信息，请参阅管理保护Microsoft Defender 防病毒[源](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="d2b6c-131">每月更新会分期发布，从而在 Window Server Update Services 中显示 [多个程序包](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="d2b6c-132">每月平台和引擎版本</span><span class="sxs-lookup"><span data-stu-id="d2b6c-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="d2b6c-133">若要了解如何更新或安装平台更新，请参阅反恶意软件Windows Defender[更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="d2b6c-134">我们的所有更新都包含</span><span class="sxs-lookup"><span data-stu-id="d2b6c-134">All our updates contain</span></span> 
- <span data-ttu-id="d2b6c-135">性能改进;</span><span class="sxs-lookup"><span data-stu-id="d2b6c-135">performance improvements;</span></span>
- <span data-ttu-id="d2b6c-136">可服务性改进;和</span><span class="sxs-lookup"><span data-stu-id="d2b6c-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="d2b6c-137">云 (集成[改进](/microsoft-365/security/defender/microsoft-365-defender)Microsoft 365 Defender) 。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/><br/>
<details>
<summary> <span data-ttu-id="d2b6c-138">2021 年 5 月 (平台：4.18.2105.4 |引擎：1.1.18200.4) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="d2b6c-139">&ensp;安全智能更新版本 **：1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="d2b6c-140">&ensp;发布时间 **：2021 年 6 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-140">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="d2b6c-141">&ensp;平台 **：4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="d2b6c-142">&ensp;引擎 **：1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="d2b6c-143">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-144">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-144">What's new</span></span>
- <span data-ttu-id="d2b6c-145">对行为 [监视的改进](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="d2b6c-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="d2b6c-146">修复 [了网络保护](network-protection.md) 通知筛选功能</span><span class="sxs-lookup"><span data-stu-id="d2b6c-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="d2b6c-147">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-147">Known Issues</span></span>
<span data-ttu-id="d2b6c-148">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d2b6c-149">2021 年 4 月 (平台：4.18.2104.14 |引擎：1.1.18100.5) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="d2b6c-150">&ensp;安全智能更新版本 **：1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="d2b6c-151">&ensp;发布时间 **：2021**  年 4 月 26 日 (引擎：1.1.18100.6 发布时间 2021 年 5 月 5 日) &ensp; 平台 **：4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-151">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="d2b6c-152">&ensp;引擎 **：1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="d2b6c-153">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-154">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-154">What's new</span></span>
- <span data-ttu-id="d2b6c-155">其他行为监视逻辑</span><span class="sxs-lookup"><span data-stu-id="d2b6c-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="d2b6c-156">改进了内核模式键记录器检测</span><span class="sxs-lookup"><span data-stu-id="d2b6c-156">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="d2b6c-157">添加了新控件来管理 Microsoft Defender 更新的逐步 [推出过程](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="d2b6c-157">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="d2b6c-158">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-158">Known Issues</span></span>
<span data-ttu-id="d2b6c-159">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-159">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d2b6c-160">2021 年 3 月 (平台：4.18.2103.7 |引擎：1.1.18000.5) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-160">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="d2b6c-161">&ensp;安全智能更新版本 **：1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-161">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="d2b6c-162">&ensp;发布时间 **：2021 年 4 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-162">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="d2b6c-163">&ensp;平台 **：4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-163">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="d2b6c-164">&ensp;引擎 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-164">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="d2b6c-165">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-165">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-166">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-166">What's new</span></span>

- <span data-ttu-id="d2b6c-167">对行为监控引擎的改进</span><span class="sxs-lookup"><span data-stu-id="d2b6c-167">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="d2b6c-168">扩展的网络暴力攻击缓解措施</span><span class="sxs-lookup"><span data-stu-id="d2b6c-168">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="d2b6c-169">启用防篡改保护 [时的其他失败](prevent-changes-to-security-settings-with-tamper-protection.md) 篡改尝试事件生成</span><span class="sxs-lookup"><span data-stu-id="d2b6c-169">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="d2b6c-170">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-170">Known Issues</span></span>
<span data-ttu-id="d2b6c-171">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="d2b6c-172">旧版本更新：仅技术升级支持</span><span class="sxs-lookup"><span data-stu-id="d2b6c-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="d2b6c-173">发布新程序包版本后，仅对前两个版本的支持减少到技术支持。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="d2b6c-174">低于本部分中列出的版本，并且仅提供用于技术升级支持的版本。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="d2b6c-175">2021 年 2 月 (平台：4.18.2102.3 |引擎：1.1.17900.7) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-175">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="d2b6c-176">&ensp;安全智能更新版本 **：1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-176">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="d2b6c-177">&ensp;已发布 **：2021 年 3 月 9 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-177">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="d2b6c-178">&ensp;平台 **：4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-178">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="d2b6c-179">&ensp;引擎 **：1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-179">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="d2b6c-180">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-181">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-181">What's new</span></span>

- <span data-ttu-id="d2b6c-182">通过防篡改保护 [改进了服务恢复](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="d2b6c-182">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="d2b6c-183">扩展防篡改保护作用域</span><span class="sxs-lookup"><span data-stu-id="d2b6c-183">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="d2b6c-184">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-184">Known Issues</span></span>
<span data-ttu-id="d2b6c-185">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-185">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d2b6c-186">2021 年 1 月 (平台：4.18.2101.9 |引擎：1.1.17800.5) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-186">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="d2b6c-187">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-187">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="d2b6c-188">&ensp;发布时间 **：2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-188">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="d2b6c-189">&ensp;平台 **：4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-189">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="d2b6c-190">&ensp;引擎 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-190">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="d2b6c-191">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-191">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-192">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-192">What's new</span></span>

- <span data-ttu-id="d2b6c-193">Shellcode 攻击检测改进</span><span class="sxs-lookup"><span data-stu-id="d2b6c-193">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="d2b6c-194">提高了凭据窃取尝试的可见性</span><span class="sxs-lookup"><span data-stu-id="d2b6c-194">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="d2b6c-195">改进服务中的反Microsoft Defender 防病毒功能</span><span class="sxs-lookup"><span data-stu-id="d2b6c-195">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="d2b6c-196">改进了对 x64 ARM的支持</span><span class="sxs-lookup"><span data-stu-id="d2b6c-196">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="d2b6c-197">修复：EDR执行初始检测后阻止通知仍保留在威胁历史记录中</span><span class="sxs-lookup"><span data-stu-id="d2b6c-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="d2b6c-198">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-198">Known Issues</span></span>
<span data-ttu-id="d2b6c-199">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-199">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d2b6c-200">2020 年 11 月 (平台：4.18.2011.6 |引擎：1.1.17700.4) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-200">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="d2b6c-201">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-201">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="d2b6c-202">&ensp;发布时间 **：2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-202">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="d2b6c-203">&ensp;平台 **：4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-203">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="d2b6c-204">&ensp;引擎 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-204">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="d2b6c-205">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-205">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-206">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-206">What's new</span></span>

- <span data-ttu-id="d2b6c-207">改进 [的 SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 状态支持日志记录</span><span class="sxs-lookup"><span data-stu-id="d2b6c-207">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="d2b6c-208">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-208">Known Issues</span></span>
<span data-ttu-id="d2b6c-209">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-209">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d2b6c-210">2020 年 10 月 (平台：4.18.2010.7 |引擎：1.1.17600.5) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-210">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="d2b6c-211">&ensp;安全智能更新版本 **：1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-211">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="d2b6c-212">&ensp;发布时间 **：2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-212">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="d2b6c-213">&ensp;平台 **：4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-213">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="d2b6c-214">&ensp;引擎 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-214">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="d2b6c-215">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-215">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-216">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-216">What's new</span></span>

- <span data-ttu-id="d2b6c-217">特殊威胁类别的新说明</span><span class="sxs-lookup"><span data-stu-id="d2b6c-217">New descriptions for special threat categories</span></span>
- <span data-ttu-id="d2b6c-218">改进的模拟功能</span><span class="sxs-lookup"><span data-stu-id="d2b6c-218">Improved emulation capabilities</span></span>
- <span data-ttu-id="d2b6c-219">改进了主机地址允许/阻止功能</span><span class="sxs-lookup"><span data-stu-id="d2b6c-219">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="d2b6c-220">Defender CSP 中用于忽略本地用户排除项合并的新选项</span><span class="sxs-lookup"><span data-stu-id="d2b6c-220">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="d2b6c-221">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-221">Known Issues</span></span>

<span data-ttu-id="d2b6c-222">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-222">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d2b6c-223">2020 年 9 月 (平台：4.18.2009.7 |引擎：1.1.17500.4) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-223">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="d2b6c-224">&ensp;安全智能更新版本 **：1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-224">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="d2b6c-225">&ensp;发布时间 **：2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-225">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="d2b6c-226">&ensp;平台 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-226">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="d2b6c-227">&ensp;引擎 **：1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-227">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="d2b6c-228">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-228">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-229">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-229">What's new</span></span>

- <span data-ttu-id="d2b6c-230">需要管理员权限才能还原隔离中的文件</span><span class="sxs-lookup"><span data-stu-id="d2b6c-230">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="d2b6c-231">XML 格式事件现在受支持</span><span class="sxs-lookup"><span data-stu-id="d2b6c-231">XML formatted events are now supported</span></span>
- <span data-ttu-id="d2b6c-232">忽略排除合并的云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="d2b6c-232">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="d2b6c-233">用于：</span><span class="sxs-lookup"><span data-stu-id="d2b6c-233">New management interfaces for:</span></span>
   - <span data-ttu-id="d2b6c-234">UDP 检查</span><span class="sxs-lookup"><span data-stu-id="d2b6c-234">UDP Inspection</span></span>
   - <span data-ttu-id="d2b6c-235">Server 2019 上的网络保护</span><span class="sxs-lookup"><span data-stu-id="d2b6c-235">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="d2b6c-236">网络保护的 IP 地址排除项</span><span class="sxs-lookup"><span data-stu-id="d2b6c-236">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="d2b6c-237">改进了对 TPM 测量的可见性</span><span class="sxs-lookup"><span data-stu-id="d2b6c-237">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="d2b6c-238">改进了 Office VBA 模块扫描</span><span class="sxs-lookup"><span data-stu-id="d2b6c-238">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="d2b6c-239">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-239">Known Issues</span></span>

<span data-ttu-id="d2b6c-240">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-240">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="d2b6c-241">2020 年 8 月 (平台：4.18.2008.9 |引擎：1.1.17400.5) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-241">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="d2b6c-242">&ensp;安全智能更新版本 **：1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-242">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="d2b6c-243">&ensp;发布时间 **：2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-243">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="d2b6c-244">&ensp;平台 **：4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-244">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="d2b6c-245">&ensp;引擎 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-245">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="d2b6c-246">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="d2b6c-247">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-247">What's new</span></span>

- <span data-ttu-id="d2b6c-248">添加更多遥测事件</span><span class="sxs-lookup"><span data-stu-id="d2b6c-248">Add more telemetry events</span></span>
- <span data-ttu-id="d2b6c-249">改进了扫描事件遥测</span><span class="sxs-lookup"><span data-stu-id="d2b6c-249">Improved scan event telemetry</span></span>
- <span data-ttu-id="d2b6c-250">改进了内存扫描行为监视</span><span class="sxs-lookup"><span data-stu-id="d2b6c-250">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="d2b6c-251">改进的宏流扫描</span><span class="sxs-lookup"><span data-stu-id="d2b6c-251">Improved macro streams scanning</span></span>
- <span data-ttu-id="d2b6c-252">已 `AMRunningMode` 添加到 Get-MpComputerStatus PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="d2b6c-252">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="d2b6c-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="d2b6c-254">Microsoft Defender 防病毒检测到其他防病毒程序时自动关闭自身。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-254">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="d2b6c-255">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-255">Known Issues</span></span>
<span data-ttu-id="d2b6c-256">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d2b6c-257">2020 年 7 月 (平台：4.18.2007.8 |引擎：1.1.17300.4) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-257">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="d2b6c-258">&ensp;安全智能更新版本 **：1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-258">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="d2b6c-259">&ensp;发布时间 **：2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-259">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="d2b6c-260">&ensp;平台 **：4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-260">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="d2b6c-261">&ensp;引擎 **：1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-261">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="d2b6c-262">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-263">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-263">What's new</span></span>

- <span data-ttu-id="d2b6c-264">改进的 BITS 遥测</span><span class="sxs-lookup"><span data-stu-id="d2b6c-264">Improved telemetry for BITS</span></span>
- <span data-ttu-id="d2b6c-265">改进的验证码代码签名证书验证</span><span class="sxs-lookup"><span data-stu-id="d2b6c-265">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="d2b6c-266">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-266">Known Issues</span></span>
<span data-ttu-id="d2b6c-267">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-267">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d2b6c-268">2020 年 6 月 (平台：4.18.2006.10 |引擎：1.1.17200.2) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-268">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="d2b6c-269">&ensp;安全智能更新版本 **：1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-269">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="d2b6c-270">&ensp;发布时间 **：2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-270">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="d2b6c-271">&ensp;平台 **：4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-271">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="d2b6c-272">&ensp;引擎 **：1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-272">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="d2b6c-273">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-273">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-274">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-274">What's new</span></span>

- <span data-ttu-id="d2b6c-275">指定支持 [日志的位置的可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="d2b6c-275">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="d2b6c-276">在被动模式下跳过主动的捕获扫描。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-276">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="d2b6c-277">允许 Defender 更新按流量计费的连接</span><span class="sxs-lookup"><span data-stu-id="d2b6c-277">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="d2b6c-278">修复了禁用缓存时的性能调整</span><span class="sxs-lookup"><span data-stu-id="d2b6c-278">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="d2b6c-279">修复了注册表查询</span><span class="sxs-lookup"><span data-stu-id="d2b6c-279">Fixed registry query</span></span> 
- <span data-ttu-id="d2b6c-280">修复了 ADMX 中的扫描时间随机化</span><span class="sxs-lookup"><span data-stu-id="d2b6c-280">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="d2b6c-281">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-281">Known Issues</span></span>
<span data-ttu-id="d2b6c-282">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-282">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d2b6c-283">2020 年 5 月 (平台：4.18.2005.4 |引擎：1.1.17100.2) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-283">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="d2b6c-284">&ensp;安全智能更新版本 **：1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-284">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="d2b6c-285">&ensp;发布时间 **：2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-285">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="d2b6c-286">&ensp;平台 **：4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-286">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="d2b6c-287">&ensp;引擎 **：1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-287">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="d2b6c-288">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-288">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-289">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-289">What's new</span></span>

- <span data-ttu-id="d2b6c-290">改进了扫描事件的日志记录</span><span class="sxs-lookup"><span data-stu-id="d2b6c-290">Improved logging for scan events</span></span>
- <span data-ttu-id="d2b6c-291">改进了用户模式崩溃处理。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-291">Improved user mode crash handling.</span></span>
- <span data-ttu-id="d2b6c-292">添加了防篡改保护的事件跟踪</span><span class="sxs-lookup"><span data-stu-id="d2b6c-292">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="d2b6c-293">修复了 AMSI 示例提交</span><span class="sxs-lookup"><span data-stu-id="d2b6c-293">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="d2b6c-294">修复了 AMSI 云阻止</span><span class="sxs-lookup"><span data-stu-id="d2b6c-294">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="d2b6c-295">修复了安全更新安装日志</span><span class="sxs-lookup"><span data-stu-id="d2b6c-295">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="d2b6c-296">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-296">Known Issues</span></span>
<span data-ttu-id="d2b6c-297">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-297">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d2b6c-298">2020 年 4 月 (平台：4.18.2004.6 |引擎：1.1.17000.2) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-298">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="d2b6c-299">&ensp;安全智能更新版本 **：1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-299">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="d2b6c-300">&ensp;发布时间 **：2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-300">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="d2b6c-301">&ensp;平台 **：4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-301">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="d2b6c-302">&ensp;引擎 **：1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-302">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="d2b6c-303">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-303">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-304">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-304">What's new</span></span>
- <span data-ttu-id="d2b6c-305">WDfilter 改进</span><span class="sxs-lookup"><span data-stu-id="d2b6c-305">WDfilter improvements</span></span>
- <span data-ttu-id="d2b6c-306">向攻击面减少检测事件添加更多可操作事件数据</span><span class="sxs-lookup"><span data-stu-id="d2b6c-306">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="d2b6c-307">诊断数据和 WMI 中的固定版本信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-307">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="d2b6c-308">修复了平台更新后 UI 中的平台版本不正确</span><span class="sxs-lookup"><span data-stu-id="d2b6c-308">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="d2b6c-309">用于无文件威胁防护的动态 URL intel</span><span class="sxs-lookup"><span data-stu-id="d2b6c-309">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="d2b6c-310">UEFI 扫描功能</span><span class="sxs-lookup"><span data-stu-id="d2b6c-310">UEFI scan capability</span></span>
- <span data-ttu-id="d2b6c-311">扩展更新日志记录</span><span class="sxs-lookup"><span data-stu-id="d2b6c-311">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="d2b6c-312">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-312">Known Issues</span></span>
<span data-ttu-id="d2b6c-313">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-313">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d2b6c-314">2020 年 3 月 (平台：4.18.2003.8 |引擎：1.1.16900.2) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-314">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="d2b6c-315">&ensp;安全智能更新版本 **：1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-315">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="d2b6c-316">&ensp;已发布 **：2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-316">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="d2b6c-317">&ensp;平台 **：4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-317">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="d2b6c-318">&ensp;引擎 **：1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-318">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="d2b6c-319">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-319">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d2b6c-320">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-320">What's new</span></span>

- <span data-ttu-id="d2b6c-321">添加到[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 限制选项</span><span class="sxs-lookup"><span data-stu-id="d2b6c-321">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="d2b6c-322">改进诊断功能</span><span class="sxs-lookup"><span data-stu-id="d2b6c-322">Improve diagnostic capability</span></span>
- <span data-ttu-id="d2b6c-323">将安全智能超时 (5 分钟) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-323">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="d2b6c-324">扩展 AMSI 引擎内部日志功能</span><span class="sxs-lookup"><span data-stu-id="d2b6c-324">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="d2b6c-325">改进进程阻止通知</span><span class="sxs-lookup"><span data-stu-id="d2b6c-325">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="d2b6c-326">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-326">Known Issues</span></span>
<span data-ttu-id="d2b6c-327">[**Fixed**]Microsoft Defender 防病毒扫描时跳过文件。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-327">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="d2b6c-328">2020 年 2 月 (平台： - |引擎：1.1.16800.2) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-328">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="d2b6c-329">&ensp;安全智能更新版本 **：1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="d2b6c-329">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="d2b6c-330">&ensp;发布时间 **：2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-330">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="d2b6c-331">&ensp;平台/客户端： **-**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-331">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="d2b6c-332">&ensp;引擎 **：1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-332">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="d2b6c-333">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-333">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="d2b6c-334">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-334">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="d2b6c-335">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-335">Known Issues</span></span>
<span data-ttu-id="d2b6c-336">无已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-336">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="d2b6c-337">2020 年 1 月 (平台：4.18.2001.10 |引擎：1.1.16700.2) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-337">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="d2b6c-338">安全智能更新版本 **：1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-338">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="d2b6c-339">发布时间 **：2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-339">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="d2b6c-340">平台/客户端 **：4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-340">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="d2b6c-341">引擎 **：1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-341">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="d2b6c-342">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-342">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="d2b6c-343">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-343">What's new</span></span>

- <span data-ttu-id="d2b6c-344">修复了 WS2016 上的 BSOD 与Exchange</span><span class="sxs-lookup"><span data-stu-id="d2b6c-344">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="d2b6c-345">当 TMP 重定向到网络路径时支持平台更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-345">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="d2b6c-346">平台和引擎版本已添加到 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="d2b6c-346">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="d2b6c-347">将紧急签名更新扩展到 [被动模式](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="d2b6c-347">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="d2b6c-348">修复 4.18.1911.3 挂起</span><span class="sxs-lookup"><span data-stu-id="d2b6c-348">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="d2b6c-349">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-349">Known Issues</span></span>

<span data-ttu-id="d2b6c-350">[**修复**][使用新式待机](/windows-hardware/design/device-experiences/modern-standby)模式的设备可能会遇到与 Windows Defender 筛选器驱动程序的挂起，导致保护差距。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="d2b6c-351">受影响的计算机向客户显示尚未更新到最新的反恶意软件平台。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-351">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="d2b6c-352">此更新为：</span><span class="sxs-lookup"><span data-stu-id="d2b6c-352">This update is:</span></span>
> - <span data-ttu-id="d2b6c-353">运行较低版本的平台以支持 SHA2 的 RS1 设备需要;</span><span class="sxs-lookup"><span data-stu-id="d2b6c-353">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="d2b6c-354">对于有挂起问题的系统，具有重新启动标志;</span><span class="sxs-lookup"><span data-stu-id="d2b6c-354">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="d2b6c-355">在 2020 年 4 月重新发布，并且不会被更新的更新所取代，以保持将来的可用性;</span><span class="sxs-lookup"><span data-stu-id="d2b6c-355">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="d2b6c-356">因重启要求而分类为更新;和</span><span class="sxs-lookup"><span data-stu-id="d2b6c-356">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="d2b6c-357">仅提供与 Windows Update 一[起提供](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-357">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="d2b6c-358">2019 年 11 月 (平台：4.18.1911.3 |引擎：1.1.16600.7) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-358">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="d2b6c-359">安全智能更新版本 **：1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-359">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="d2b6c-360">发布时间 **：2019 年 12 月 7 日**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-360">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="d2b6c-361">平台 **：4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-361">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="d2b6c-362">引擎 **：1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-362">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="d2b6c-363">支持阶段： **不支持**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-363">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="d2b6c-364">最近更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-364">What's new</span></span>

- <span data-ttu-id="d2b6c-365">修复了 MpCmdRun 跟踪级别</span><span class="sxs-lookup"><span data-stu-id="d2b6c-365">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="d2b6c-366">修复了 WDFilter 版本信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-366">Fixed WDFilter version info</span></span>
- <span data-ttu-id="d2b6c-367">改进 PUA (通知) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-367">Improve notifications (PUA)</span></span>
- <span data-ttu-id="d2b6c-368">添加 MRT 日志以支持文件</span><span class="sxs-lookup"><span data-stu-id="d2b6c-368">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="d2b6c-369">已知问题</span><span class="sxs-lookup"><span data-stu-id="d2b6c-369">Known Issues</span></span>
<span data-ttu-id="d2b6c-370">安装此更新后，设备需要跳转程序包 4.18.2001.10 才能更新到最新的平台版本。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-370">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="d2b6c-371">Microsoft Defender 防病毒平台支持</span><span class="sxs-lookup"><span data-stu-id="d2b6c-371">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="d2b6c-372">平台和引擎更新按月提供。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-372">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="d2b6c-373">若要完全受支持，请及时了解最新的平台更新。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-373">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="d2b6c-374">我们的支持结构是动态的，根据最新平台版本的可用性，将发展为两个阶段：</span><span class="sxs-lookup"><span data-stu-id="d2b6c-374">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="d2b6c-375">**安全和关键更新服务阶段** - 运行最新平台版本时，你将有资格接收反恶意软件平台的安全和关键更新。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-375">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="d2b6c-376">**技术支持 (仅在)** 阶段 - 发布新平台版本后，对早期版本 (N-2) 的支持将仅减少为技术支持。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-376">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="d2b6c-377">不再支持 N-2 之前的平台版本。\*</span><span class="sxs-lookup"><span data-stu-id="d2b6c-377">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="d2b6c-378">\*将继续为从 Windows 10 版本升级提供技术支持 (请参阅[Windows 10](#platform-version-included-with-windows-10-releases)版本中包含的平台版本) 到最新平台版本。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-378">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="d2b6c-379">在技术支持 (仅在) 阶段，商业上合理的支持事件将通过 Microsoft 客户服务 & 支持和 Microsoft 的托管支持产品/服务 (如 Premier Support) 提供。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-379">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="d2b6c-380">如果支持事件需要上报开发以进一步提供指导、需要非安全更新或需要安全更新，将要求客户升级到最新平台版本或中间 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-380">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="d2b6c-381">版本中包含的平台Windows 10版本</span><span class="sxs-lookup"><span data-stu-id="d2b6c-381">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="d2b6c-382">下表提供了最新 Microsoft Defender 防病毒 版本附带的 Microsoft Defender 防病毒 Windows 10 平台和引擎版本：</span><span class="sxs-lookup"><span data-stu-id="d2b6c-382">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="d2b6c-383">Windows 10发布</span><span class="sxs-lookup"><span data-stu-id="d2b6c-383">Windows 10 release</span></span>  |<span data-ttu-id="d2b6c-384">平台版本</span><span class="sxs-lookup"><span data-stu-id="d2b6c-384">Platform version</span></span>  |<span data-ttu-id="d2b6c-385">引擎版本</span><span class="sxs-lookup"><span data-stu-id="d2b6c-385">Engine version</span></span> |<span data-ttu-id="d2b6c-386">支持阶段</span><span class="sxs-lookup"><span data-stu-id="d2b6c-386">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="d2b6c-387">2004 (20H1/20H2) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-387">2004  (20H1/20H2)</span></span> |<span data-ttu-id="d2b6c-388">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="d2b6c-388">4.18.1909.6</span></span> |<span data-ttu-id="d2b6c-389">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="d2b6c-389">1.1.17000.2</span></span> | <span data-ttu-id="d2b6c-390">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-390">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d2b6c-391">1909 (19H2) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-391">1909  (19H2)</span></span> |<span data-ttu-id="d2b6c-392">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="d2b6c-392">4.18.1902.5</span></span> |<span data-ttu-id="d2b6c-393">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="d2b6c-393">1.1.16700.3</span></span> | <span data-ttu-id="d2b6c-394">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-394">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d2b6c-395">1903 (19H1) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-395">1903  (19H1)</span></span> |<span data-ttu-id="d2b6c-396">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="d2b6c-396">4.18.1902.5</span></span> |<span data-ttu-id="d2b6c-397">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="d2b6c-397">1.1.15600.4</span></span> | <span data-ttu-id="d2b6c-398">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-398">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d2b6c-399">1809 (RS5) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-399">1809  (RS5)</span></span> |<span data-ttu-id="d2b6c-400">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="d2b6c-400">4.18.1807.18075</span></span> |<span data-ttu-id="d2b6c-401">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="d2b6c-401">1.1.15000.2</span></span> | <span data-ttu-id="d2b6c-402">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-402">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d2b6c-403">1803 (RS4) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-403">1803  (RS4)</span></span> |<span data-ttu-id="d2b6c-404">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="d2b6c-404">4.13.17134.1</span></span> |<span data-ttu-id="d2b6c-405">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="d2b6c-405">1.1.14600.4</span></span> | <span data-ttu-id="d2b6c-406">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-406">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d2b6c-407">1709 (RS3) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-407">1709  (RS3)</span></span> |<span data-ttu-id="d2b6c-408">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="d2b6c-408">4.12.16299.15</span></span> |<span data-ttu-id="d2b6c-409">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="d2b6c-409">1.1.14104.0</span></span> | <span data-ttu-id="d2b6c-410">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-410">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d2b6c-411">1703 (RS2) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-411">1703  (RS2)</span></span> |<span data-ttu-id="d2b6c-412">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="d2b6c-412">4.11.15603.2</span></span> |<span data-ttu-id="d2b6c-413">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="d2b6c-413">1.1.13504.0</span></span> | <span data-ttu-id="d2b6c-414">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-414">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d2b6c-415">1607 (RS1) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-415">1607 (RS1)</span></span> |<span data-ttu-id="d2b6c-416">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="d2b6c-416">4.10.14393.3683</span></span> |<span data-ttu-id="d2b6c-417">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="d2b6c-417">1.1.12805.0</span></span> | <span data-ttu-id="d2b6c-418">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-418">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="d2b6c-419">有关Windows 10的信息，请参阅生命周期[Windows表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-419">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="d2b6c-420">DISM 部署映像服务和管理 (更新) </span><span class="sxs-lookup"><span data-stu-id="d2b6c-420">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="d2b6c-421">我们建议使用最新的防病毒和反恶意软件更新更新 Windows 10 (Enterprise、Pro 和家庭版) 、Windows Server 2019 和 Windows Server 2016 操作系统安装映像。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-421">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="d2b6c-422">使操作系统安装映像保持最新有助于避免保护差距。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-422">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="d2b6c-423">有关详细信息，请参阅适用于操作系统[安装映像Windows Microsoft Defender 更新](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-423">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="d2b6c-424">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="d2b6c-424">1.1.2106.01</span></span></summary>

<span data-ttu-id="d2b6c-425">&ensp;程序包版本 **：1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="d2b6c-425">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="d2b6c-426">&ensp;平台版本 **：4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="d2b6c-426">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="d2b6c-427">&ensp;引擎版本 **：1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-427">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="d2b6c-428">&ensp;签名版本 **：1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-428">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d2b6c-429">修补程序</span><span class="sxs-lookup"><span data-stu-id="d2b6c-429">Fixes</span></span>
- <span data-ttu-id="d2b6c-430">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-430">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d2b6c-431">其他信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-431">Additional information</span></span>
- <span data-ttu-id="d2b6c-432">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-432">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d2b6c-433">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="d2b6c-433">1.1.2105.01</span></span></summary>

<span data-ttu-id="d2b6c-434">&ensp;程序包版本 **：1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="d2b6c-434">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="d2b6c-435">&ensp;平台版本 **：4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="d2b6c-435">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="d2b6c-436">&ensp;引擎版本 **：1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-436">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="d2b6c-437">&ensp;签名版本 **：1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-437">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d2b6c-438">修补程序</span><span class="sxs-lookup"><span data-stu-id="d2b6c-438">Fixes</span></span>
- <span data-ttu-id="d2b6c-439">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-439">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d2b6c-440">其他信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-440">Additional information</span></span>
- <span data-ttu-id="d2b6c-441">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-441">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d2b6c-442">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="d2b6c-442">1.1.2104.01</span></span></summary>

<span data-ttu-id="d2b6c-443">&ensp;程序包版本 **：1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="d2b6c-443">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="d2b6c-444">&ensp;平台版本 **：4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="d2b6c-444">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="d2b6c-445">&ensp;引擎版本 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-445">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="d2b6c-446">&ensp;签名版本 **：1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-446">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d2b6c-447">修补程序</span><span class="sxs-lookup"><span data-stu-id="d2b6c-447">Fixes</span></span>
- <span data-ttu-id="d2b6c-448">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d2b6c-449">其他信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-449">Additional information</span></span>
- <span data-ttu-id="d2b6c-450">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d2b6c-451">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="d2b6c-451">1.1.2103.01</span></span></summary>

<span data-ttu-id="d2b6c-452">&ensp;程序包版本 **：1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="d2b6c-452">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="d2b6c-453">&ensp;平台版本 **：4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="d2b6c-453">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="d2b6c-454">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-454">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="d2b6c-455">&ensp;签名版本 **：1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-455">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d2b6c-456">修补程序</span><span class="sxs-lookup"><span data-stu-id="d2b6c-456">Fixes</span></span>
- <span data-ttu-id="d2b6c-457">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d2b6c-458">其他信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-458">Additional information</span></span>
- <span data-ttu-id="d2b6c-459">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d2b6c-460">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="d2b6c-460">1.1.2102.03</span></span></summary>

<span data-ttu-id="d2b6c-461">&ensp;程序包版本 **：1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="d2b6c-461">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="d2b6c-462">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="d2b6c-462">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="d2b6c-463">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-463">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="d2b6c-464">&ensp;签名版本 **：1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-464">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d2b6c-465">修补程序</span><span class="sxs-lookup"><span data-stu-id="d2b6c-465">Fixes</span></span>
- <span data-ttu-id="d2b6c-466">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d2b6c-467">其他信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-467">Additional information</span></span>
- <span data-ttu-id="d2b6c-468">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d2b6c-469">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="d2b6c-469">1.1.2101.02</span></span></summary>

<span data-ttu-id="d2b6c-470">&ensp;程序包版本 **：1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="d2b6c-470">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="d2b6c-471">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="d2b6c-471">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="d2b6c-472">&ensp;引擎版本 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-472">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="d2b6c-473">&ensp;签名版本 **：1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-473">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d2b6c-474">修补程序</span><span class="sxs-lookup"><span data-stu-id="d2b6c-474">Fixes</span></span>
- <span data-ttu-id="d2b6c-475">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d2b6c-476">其他信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-476">Additional information</span></span>
- <span data-ttu-id="d2b6c-477">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d2b6c-478">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="d2b6c-478">1.1.2012.01</span></span></summary>

<span data-ttu-id="d2b6c-479">&ensp;程序包版本 **：1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="d2b6c-479">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="d2b6c-480">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="d2b6c-480">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="d2b6c-481">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-481">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="d2b6c-482">&ensp;签名版本 **：1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-482">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d2b6c-483">修补程序</span><span class="sxs-lookup"><span data-stu-id="d2b6c-483">Fixes</span></span>
- <span data-ttu-id="d2b6c-484">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d2b6c-485">其他信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-485">Additional information</span></span>
- <span data-ttu-id="d2b6c-486">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d2b6c-487">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="d2b6c-487">1.1.2011.02</span></span></summary>

<span data-ttu-id="d2b6c-488">&ensp;程序包版本 **：1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="d2b6c-488">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="d2b6c-489">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="d2b6c-489">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="d2b6c-490">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-490">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="d2b6c-491">&ensp;签名版本 **：1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-491">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d2b6c-492">修补程序</span><span class="sxs-lookup"><span data-stu-id="d2b6c-492">Fixes</span></span>
- <span data-ttu-id="d2b6c-493">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d2b6c-494">其他信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-494">Additional information</span></span>
- <span data-ttu-id="d2b6c-495">刷新Microsoft Defender 防病毒签名</span><span class="sxs-lookup"><span data-stu-id="d2b6c-495">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d2b6c-496">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="d2b6c-496">1.1.2011.01</span></span></summary>

<span data-ttu-id="d2b6c-497">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="d2b6c-497">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="d2b6c-498">&ensp;平台版本 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-498">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="d2b6c-499">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="d2b6c-500">&ensp;签名版本 **：1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-500">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d2b6c-501">修补程序</span><span class="sxs-lookup"><span data-stu-id="d2b6c-501">Fixes</span></span>
- <span data-ttu-id="d2b6c-502">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d2b6c-503">其他信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-503">Additional information</span></span>
- <span data-ttu-id="d2b6c-504">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d2b6c-505">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="d2b6c-505">1.1.2009.10</span></span></summary>

<span data-ttu-id="d2b6c-506">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="d2b6c-506">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="d2b6c-507">&ensp;平台版本 **：4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="d2b6c-507">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="d2b6c-508">&ensp;引擎版本 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-508">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="d2b6c-509">&ensp;签名版本 **：1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="d2b6c-509">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d2b6c-510">修补程序</span><span class="sxs-lookup"><span data-stu-id="d2b6c-510">Fixes</span></span>
- <span data-ttu-id="d2b6c-511">无</span><span class="sxs-lookup"><span data-stu-id="d2b6c-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d2b6c-512">其他信息</span><span class="sxs-lookup"><span data-stu-id="d2b6c-512">Additional information</span></span>
- <span data-ttu-id="d2b6c-513">添加了对 Windows 10 RS1 或更高版本操作系统安装映像的支持。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-513">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="d2b6c-514">其他资源</span><span class="sxs-lookup"><span data-stu-id="d2b6c-514">Additional resources</span></span>

| <span data-ttu-id="d2b6c-515">文章</span><span class="sxs-lookup"><span data-stu-id="d2b6c-515">Article</span></span> | <span data-ttu-id="d2b6c-516">说明</span><span class="sxs-lookup"><span data-stu-id="d2b6c-516">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="d2b6c-517">适用于操作系统安装映像Windows Microsoft Defender 更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-517">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="d2b6c-518">查看适用于操作系统安装映像的反恶意软件更新程序包 (WIM 和 VHD 文件) 。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-518">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="d2b6c-519">获取 Microsoft Defender 防病毒、Windows 10 (Enterprise、Pro、家庭版) 、Windows Server 2019 Windows Server 2016更新。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-519">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="d2b6c-520">管理保护更新的下载和应用方式</span><span class="sxs-lookup"><span data-stu-id="d2b6c-520">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="d2b6c-521">保护更新可以通过多个源提供。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-521">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="d2b6c-522">管理何时应下载和应用保护更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-522">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="d2b6c-523">你可以计划应下载保护更新的时间。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-523">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="d2b6c-524">管理过期终结点的更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-524">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="d2b6c-525">如果终结点错过更新或计划扫描，可以在用户下次登录时强制进行更新或扫描。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-525">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="d2b6c-526">管理基于事件的强制更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-526">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="d2b6c-527">你可以将保护更新设置为在启动时或在某些云提供的保护事件之后下载。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-527">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="d2b6c-528">管理移动设备和虚拟机 （VM） 的更新</span><span class="sxs-lookup"><span data-stu-id="d2b6c-528">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="d2b6c-529">你可以指定对移动设备和虚拟机特别有用的设置，例如是否应该使用电池电源进行更新。</span><span class="sxs-lookup"><span data-stu-id="d2b6c-529">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
