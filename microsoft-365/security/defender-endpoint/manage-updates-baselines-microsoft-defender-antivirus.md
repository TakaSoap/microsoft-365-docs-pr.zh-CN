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
ms.date: 06/14/2021
ms.openlocfilehash: 1c7ff52398e048aa34fd9c5ab3d8edd1004ea5ec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929439"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="3c631-104">管理Microsoft Defender 防病毒更新并应用基线</span><span class="sxs-lookup"><span data-stu-id="3c631-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="3c631-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="3c631-105">**Applies to:**</span></span>

- [<span data-ttu-id="3c631-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3c631-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="3c631-107">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="3c631-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="3c631-108">保持Microsoft Defender 防病毒保持最新状态对于确保你的设备具有抵御新的恶意软件和攻击技术所需的最新技术和功能至关重要。</span><span class="sxs-lookup"><span data-stu-id="3c631-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="3c631-109">确保更新防病毒保护，即使Microsoft Defender 防病毒处于被动[模式。](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="3c631-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="3c631-110">有两种类型的更新与使Microsoft Defender 防病毒保持最新有关：</span><span class="sxs-lookup"><span data-stu-id="3c631-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="3c631-111">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="3c631-111">Security intelligence updates</span></span>
- <span data-ttu-id="3c631-112">产品更新</span><span class="sxs-lookup"><span data-stu-id="3c631-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="3c631-113">To see the most current engine， platform， and signature date， visit the [Security intelligence updates for Microsoft Defender 防病毒 other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="3c631-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="3c631-114">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="3c631-114">Security intelligence updates</span></span>

<span data-ttu-id="3c631-115">Microsoft Defender 防病毒云[提供的](cloud-protection-microsoft-defender-antivirus.md)保护 (也称为 Microsoft 高级保护服务或 MAPS) 并定期下载安全智能更新以提供保护。</span><span class="sxs-lookup"><span data-stu-id="3c631-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="3c631-116">更新以以下 KB 编号发布：</span><span class="sxs-lookup"><span data-stu-id="3c631-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="3c631-117">Microsoft Defender 防病毒：KB2267602</span><span class="sxs-lookup"><span data-stu-id="3c631-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="3c631-118">System Center Endpoint Protection：KB2461484</span><span class="sxs-lookup"><span data-stu-id="3c631-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="3c631-119">云提供的保护始终打开，并且需要与 Internet 的活动连接以正常运行。</span><span class="sxs-lookup"><span data-stu-id="3c631-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="3c631-120">安全智能更新按计划节奏进行， (策略策略配置) 。</span><span class="sxs-lookup"><span data-stu-id="3c631-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="3c631-121">有关详细信息，请参阅使用[Microsoft 云提供的Microsoft Defender 防病毒。](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3c631-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="3c631-122">有关最近安全智能更新的列表，请参阅安全智能更新[Microsoft Defender 防病毒和其他 Microsoft 反恶意软件](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="3c631-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="3c631-123">引擎更新包含在安全智能更新中，并按月发布。</span><span class="sxs-lookup"><span data-stu-id="3c631-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="3c631-124">产品更新</span><span class="sxs-lookup"><span data-stu-id="3c631-124">Product updates</span></span>

<span data-ttu-id="3c631-125">Microsoft Defender 防病毒需要每月更新 [ (KB4052623](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform))  (称为平台更新 *) ，* 并且将在 Windows 10 版本旁边接收主要功能更新。</span><span class="sxs-lookup"><span data-stu-id="3c631-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="3c631-126">可以通过以下方法之一管理更新的分发：</span><span class="sxs-lookup"><span data-stu-id="3c631-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="3c631-127">WindowsWSUS (服务器更新) </span><span class="sxs-lookup"><span data-stu-id="3c631-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="3c631-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3c631-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="3c631-129">你用于部署 Microsoft 和Windows终结点更新的常用方法。</span><span class="sxs-lookup"><span data-stu-id="3c631-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="3c631-130">有关详细信息，请参阅管理保护Microsoft Defender 防病毒[源](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="3c631-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="3c631-131">每月更新会分期发布，从而在 Window Server Update Services 中显示 [多个程序包](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="3c631-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="3c631-132">每月平台和引擎版本</span><span class="sxs-lookup"><span data-stu-id="3c631-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="3c631-133">若要了解如何更新或安装平台更新，请参阅反恶意软件Windows Defender[更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="3c631-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="3c631-134">我们的所有更新都包含</span><span class="sxs-lookup"><span data-stu-id="3c631-134">All our updates contain</span></span> 
- <span data-ttu-id="3c631-135">性能改进;</span><span class="sxs-lookup"><span data-stu-id="3c631-135">performance improvements;</span></span>
- <span data-ttu-id="3c631-136">可服务性改进;和</span><span class="sxs-lookup"><span data-stu-id="3c631-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="3c631-137">集成改进 (云[，Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)) 。</span><span class="sxs-lookup"><span data-stu-id="3c631-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/><br/>
<details>
<summary> <span data-ttu-id="3c631-138">2021 年 5 月 (平台：4.18.2105.4 |引擎：1.1.18200.4) </span><span class="sxs-lookup"><span data-stu-id="3c631-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="3c631-139">&ensp;安全智能更新版本 **：1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="3c631-140">&ensp;发布时间 **：2021 年 6 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-140">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="3c631-141">&ensp;平台 **：4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="3c631-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="3c631-142">&ensp;引擎 **：1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="3c631-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="3c631-143">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="3c631-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-144">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-144">What's new</span></span>
- <span data-ttu-id="3c631-145">对行为 [监视的改进](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="3c631-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="3c631-146">修复 [了网络保护](network-protection.md) 通知筛选功能</span><span class="sxs-lookup"><span data-stu-id="3c631-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-147">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-147">Known Issues</span></span>
<span data-ttu-id="3c631-148">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3c631-149">2021 年 4 月 (平台：4.18.2104.14 |引擎：1.1.18100.5) </span><span class="sxs-lookup"><span data-stu-id="3c631-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="3c631-150">&ensp;安全智能更新版本 **：1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="3c631-151">&ensp;发布时间 **：2021**  年 4 月 26 日 (引擎：1.1.18100.6 发布时间 2021 年 5 月 5 日) &ensp; 平台 **：4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="3c631-151">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="3c631-152">&ensp;引擎 **：1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="3c631-153">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="3c631-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-154">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-154">What's new</span></span>
- <span data-ttu-id="3c631-155">其他行为监视逻辑</span><span class="sxs-lookup"><span data-stu-id="3c631-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="3c631-156">改进了内核模式键记录器检测</span><span class="sxs-lookup"><span data-stu-id="3c631-156">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-157">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-157">Known Issues</span></span>
<span data-ttu-id="3c631-158">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-158">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3c631-159">2021 年 3 月 (平台：4.18.2103.7 |引擎：1.1.18000.5) </span><span class="sxs-lookup"><span data-stu-id="3c631-159">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="3c631-160">&ensp;安全智能更新版本 **：1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-160">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="3c631-161">&ensp;发布时间 **：2021 年 4 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-161">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="3c631-162">&ensp;平台 **：4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="3c631-162">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="3c631-163">&ensp;引擎 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-163">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="3c631-164">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="3c631-164">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-165">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-165">What's new</span></span>

- <span data-ttu-id="3c631-166">对行为监控引擎的改进</span><span class="sxs-lookup"><span data-stu-id="3c631-166">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="3c631-167">扩展的网络暴力攻击缓解措施</span><span class="sxs-lookup"><span data-stu-id="3c631-167">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="3c631-168">启用防篡改保护 [时的其他失败](prevent-changes-to-security-settings-with-tamper-protection.md) 篡改尝试事件生成</span><span class="sxs-lookup"><span data-stu-id="3c631-168">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-169">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-169">Known Issues</span></span>
<span data-ttu-id="3c631-170">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-170">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="3c631-171">旧版本更新：仅技术升级支持</span><span class="sxs-lookup"><span data-stu-id="3c631-171">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="3c631-172">发布新程序包版本后，仅对前两个版本的支持减少到技术支持。</span><span class="sxs-lookup"><span data-stu-id="3c631-172">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="3c631-173">低于本部分中列出的版本，并且仅提供用于技术升级支持的版本。</span><span class="sxs-lookup"><span data-stu-id="3c631-173">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="3c631-174">2021 年 2 月 (平台：4.18.2102.3 |引擎：1.1.17900.7) </span><span class="sxs-lookup"><span data-stu-id="3c631-174">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="3c631-175">&ensp;安全智能更新版本 **：1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-175">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="3c631-176">&ensp;已发布 **：2021 年 3 月 9 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-176">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="3c631-177">&ensp;平台 **：4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="3c631-177">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="3c631-178">&ensp;引擎 **：1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="3c631-178">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="3c631-179">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-179">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-180">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-180">What's new</span></span>

- <span data-ttu-id="3c631-181">通过防篡改保护 [改进了服务恢复](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="3c631-181">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="3c631-182">扩展防篡改保护作用域</span><span class="sxs-lookup"><span data-stu-id="3c631-182">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-183">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-183">Known Issues</span></span>
<span data-ttu-id="3c631-184">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-184">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3c631-185">2021 年 1 月 (平台：4.18.2101.9 |引擎：1.1.17800.5) </span><span class="sxs-lookup"><span data-stu-id="3c631-185">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="3c631-186">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-186">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="3c631-187">&ensp;发布时间 **：2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-187">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="3c631-188">&ensp;平台 **：4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="3c631-188">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="3c631-189">&ensp;引擎 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-189">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="3c631-190">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-190">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-191">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-191">What's new</span></span>

- <span data-ttu-id="3c631-192">Shellcode 攻击检测改进</span><span class="sxs-lookup"><span data-stu-id="3c631-192">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="3c631-193">提高了凭据窃取尝试的可见性</span><span class="sxs-lookup"><span data-stu-id="3c631-193">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="3c631-194">改进服务中的反Microsoft Defender 防病毒功能</span><span class="sxs-lookup"><span data-stu-id="3c631-194">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="3c631-195">改进了对 x64 ARM的支持</span><span class="sxs-lookup"><span data-stu-id="3c631-195">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="3c631-196">修复：EDR执行初始检测后阻止通知仍保留在威胁历史记录中</span><span class="sxs-lookup"><span data-stu-id="3c631-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-197">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-197">Known Issues</span></span>
<span data-ttu-id="3c631-198">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3c631-199">2020 年 11 月 (平台：4.18.2011.6 |引擎：1.1.17700.4) </span><span class="sxs-lookup"><span data-stu-id="3c631-199">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="3c631-200">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-200">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="3c631-201">&ensp;发布时间 **：2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-201">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="3c631-202">&ensp;平台 **：4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="3c631-202">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="3c631-203">&ensp;引擎 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="3c631-203">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="3c631-204">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-205">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-205">What's new</span></span>

- <span data-ttu-id="3c631-206">改进 [的 SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 状态支持日志记录</span><span class="sxs-lookup"><span data-stu-id="3c631-206">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-207">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-207">Known Issues</span></span>
<span data-ttu-id="3c631-208">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-208">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3c631-209">2020 年 10 月 (平台：4.18.2010.7 |引擎：1.1.17600.5) </span><span class="sxs-lookup"><span data-stu-id="3c631-209">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="3c631-210">&ensp;安全智能更新版本 **：1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-210">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="3c631-211">&ensp;发布时间 **：2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-211">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="3c631-212">&ensp;平台 **：4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="3c631-212">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="3c631-213">&ensp;引擎 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-213">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="3c631-214">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-214">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-215">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-215">What's new</span></span>

- <span data-ttu-id="3c631-216">特殊威胁类别的新说明</span><span class="sxs-lookup"><span data-stu-id="3c631-216">New descriptions for special threat categories</span></span>
- <span data-ttu-id="3c631-217">改进的模拟功能</span><span class="sxs-lookup"><span data-stu-id="3c631-217">Improved emulation capabilities</span></span>
- <span data-ttu-id="3c631-218">改进了主机地址允许/阻止功能</span><span class="sxs-lookup"><span data-stu-id="3c631-218">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="3c631-219">Defender CSP 中用于忽略本地用户排除项合并的新选项</span><span class="sxs-lookup"><span data-stu-id="3c631-219">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-220">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-220">Known Issues</span></span>

<span data-ttu-id="3c631-221">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-221">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="3c631-222">2020 年 9 月 (平台：4.18.2009.7 |引擎：1.1.17500.4) </span><span class="sxs-lookup"><span data-stu-id="3c631-222">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="3c631-223">&ensp;安全智能更新版本 **：1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-223">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="3c631-224">&ensp;发布时间 **：2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-224">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="3c631-225">&ensp;平台 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="3c631-225">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="3c631-226">&ensp;引擎 **：1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="3c631-226">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="3c631-227">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-227">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-228">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-228">What's new</span></span>

- <span data-ttu-id="3c631-229">需要管理员权限才能还原隔离中的文件</span><span class="sxs-lookup"><span data-stu-id="3c631-229">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="3c631-230">XML 格式事件现在受支持</span><span class="sxs-lookup"><span data-stu-id="3c631-230">XML formatted events are now supported</span></span>
- <span data-ttu-id="3c631-231">忽略排除合并的云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="3c631-231">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="3c631-232">用于：</span><span class="sxs-lookup"><span data-stu-id="3c631-232">New management interfaces for:</span></span>
   - <span data-ttu-id="3c631-233">UDP 检查</span><span class="sxs-lookup"><span data-stu-id="3c631-233">UDP Inspection</span></span>
   - <span data-ttu-id="3c631-234">Server 2019 上的网络保护</span><span class="sxs-lookup"><span data-stu-id="3c631-234">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="3c631-235">网络保护的 IP 地址排除项</span><span class="sxs-lookup"><span data-stu-id="3c631-235">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="3c631-236">改进了对 TPM 测量的可见性</span><span class="sxs-lookup"><span data-stu-id="3c631-236">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="3c631-237">改进了 Office VBA 模块扫描</span><span class="sxs-lookup"><span data-stu-id="3c631-237">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-238">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-238">Known Issues</span></span>

<span data-ttu-id="3c631-239">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-239">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="3c631-240">2020 年 8 月 (平台：4.18.2008.9 |引擎：1.1.17400.5) </span><span class="sxs-lookup"><span data-stu-id="3c631-240">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="3c631-241">&ensp;安全智能更新版本 **：1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-241">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="3c631-242">&ensp;发布时间 **：2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-242">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="3c631-243">&ensp;平台 **：4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="3c631-243">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="3c631-244">&ensp;引擎 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-244">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="3c631-245">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-245">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="3c631-246">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-246">What's new</span></span>

- <span data-ttu-id="3c631-247">添加更多遥测事件</span><span class="sxs-lookup"><span data-stu-id="3c631-247">Add more telemetry events</span></span>
- <span data-ttu-id="3c631-248">改进了扫描事件遥测</span><span class="sxs-lookup"><span data-stu-id="3c631-248">Improved scan event telemetry</span></span>
- <span data-ttu-id="3c631-249">改进了内存扫描行为监视</span><span class="sxs-lookup"><span data-stu-id="3c631-249">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="3c631-250">改进的宏流扫描</span><span class="sxs-lookup"><span data-stu-id="3c631-250">Improved macro streams scanning</span></span>
- <span data-ttu-id="3c631-251">已 `AMRunningMode` 添加到 Get-MpComputerStatus PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3c631-251">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="3c631-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="3c631-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="3c631-253">Microsoft Defender 防病毒检测到其他防病毒程序时自动关闭自身。</span><span class="sxs-lookup"><span data-stu-id="3c631-253">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="3c631-254">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-254">Known Issues</span></span>
<span data-ttu-id="3c631-255">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-255">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="3c631-256">2020 年 7 月 (平台：4.18.2007.8 |引擎：1.1.17300.4) </span><span class="sxs-lookup"><span data-stu-id="3c631-256">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="3c631-257">&ensp;安全智能更新版本 **：1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-257">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="3c631-258">&ensp;发布时间 **：2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-258">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="3c631-259">&ensp;平台 **：4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="3c631-259">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="3c631-260">&ensp;引擎 **：1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="3c631-260">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="3c631-261">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-261">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-262">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-262">What's new</span></span>

- <span data-ttu-id="3c631-263">改进的 BITS 遥测</span><span class="sxs-lookup"><span data-stu-id="3c631-263">Improved telemetry for BITS</span></span>
- <span data-ttu-id="3c631-264">改进的验证码代码签名证书验证</span><span class="sxs-lookup"><span data-stu-id="3c631-264">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-265">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-265">Known Issues</span></span>
<span data-ttu-id="3c631-266">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-266">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="3c631-267">2020 年 6 月 (平台：4.18.2006.10 |引擎：1.1.17200.2) </span><span class="sxs-lookup"><span data-stu-id="3c631-267">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="3c631-268">&ensp;安全智能更新版本 **：1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-268">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="3c631-269">&ensp;发布时间 **：2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-269">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="3c631-270">&ensp;平台 **：4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="3c631-270">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="3c631-271">&ensp;引擎 **：1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="3c631-271">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="3c631-272">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-272">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-273">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-273">What's new</span></span>

- <span data-ttu-id="3c631-274">指定支持 [日志的位置的可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="3c631-274">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="3c631-275">在被动模式下跳过主动的捕获扫描。</span><span class="sxs-lookup"><span data-stu-id="3c631-275">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="3c631-276">允许 Defender 更新按流量计费的连接</span><span class="sxs-lookup"><span data-stu-id="3c631-276">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="3c631-277">修复了禁用缓存时的性能调整</span><span class="sxs-lookup"><span data-stu-id="3c631-277">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="3c631-278">修复了注册表查询</span><span class="sxs-lookup"><span data-stu-id="3c631-278">Fixed registry query</span></span> 
- <span data-ttu-id="3c631-279">修复了 ADMX 中的扫描时间随机化</span><span class="sxs-lookup"><span data-stu-id="3c631-279">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-280">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-280">Known Issues</span></span>
<span data-ttu-id="3c631-281">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-281">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="3c631-282">2020 年 5 月 (平台：4.18.2005.4 |引擎：1.1.17100.2) </span><span class="sxs-lookup"><span data-stu-id="3c631-282">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="3c631-283">&ensp;安全智能更新版本 **：1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-283">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="3c631-284">&ensp;发布时间 **：2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-284">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="3c631-285">&ensp;平台 **：4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="3c631-285">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="3c631-286">&ensp;引擎 **：1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="3c631-286">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="3c631-287">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-287">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-288">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-288">What's new</span></span>

- <span data-ttu-id="3c631-289">改进了扫描事件的日志记录</span><span class="sxs-lookup"><span data-stu-id="3c631-289">Improved logging for scan events</span></span>
- <span data-ttu-id="3c631-290">改进了用户模式崩溃处理。</span><span class="sxs-lookup"><span data-stu-id="3c631-290">Improved user mode crash handling.</span></span>
- <span data-ttu-id="3c631-291">添加了防篡改保护的事件跟踪</span><span class="sxs-lookup"><span data-stu-id="3c631-291">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="3c631-292">修复了 AMSI 示例提交</span><span class="sxs-lookup"><span data-stu-id="3c631-292">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="3c631-293">修复了 AMSI 云阻止</span><span class="sxs-lookup"><span data-stu-id="3c631-293">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="3c631-294">修复了安全更新安装日志</span><span class="sxs-lookup"><span data-stu-id="3c631-294">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-295">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-295">Known Issues</span></span>
<span data-ttu-id="3c631-296">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-296">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="3c631-297">2020 年 4 月 (平台：4.18.2004.6 |引擎：1.1.17000.2) </span><span class="sxs-lookup"><span data-stu-id="3c631-297">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="3c631-298">&ensp;安全智能更新版本 **：1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-298">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="3c631-299">&ensp;发布时间 **：2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-299">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="3c631-300">&ensp;平台 **：4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="3c631-300">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="3c631-301">&ensp;引擎 **：1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="3c631-301">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="3c631-302">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-302">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-303">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-303">What's new</span></span>
- <span data-ttu-id="3c631-304">WDfilter 改进</span><span class="sxs-lookup"><span data-stu-id="3c631-304">WDfilter improvements</span></span>
- <span data-ttu-id="3c631-305">向攻击面减少检测事件添加更多可操作事件数据</span><span class="sxs-lookup"><span data-stu-id="3c631-305">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="3c631-306">诊断数据和 WMI 中的固定版本信息</span><span class="sxs-lookup"><span data-stu-id="3c631-306">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="3c631-307">修复了平台更新后 UI 中的平台版本不正确</span><span class="sxs-lookup"><span data-stu-id="3c631-307">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="3c631-308">用于无文件威胁防护的动态 URL intel</span><span class="sxs-lookup"><span data-stu-id="3c631-308">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="3c631-309">UEFI 扫描功能</span><span class="sxs-lookup"><span data-stu-id="3c631-309">UEFI scan capability</span></span>
- <span data-ttu-id="3c631-310">扩展更新日志记录</span><span class="sxs-lookup"><span data-stu-id="3c631-310">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="3c631-311">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-311">Known Issues</span></span>
<span data-ttu-id="3c631-312">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-312">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="3c631-313">2020 年 3 月 (平台：4.18.2003.8 |引擎：1.1.16900.2) </span><span class="sxs-lookup"><span data-stu-id="3c631-313">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="3c631-314">&ensp;安全智能更新版本 **：1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-314">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="3c631-315">&ensp;已发布 **：2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-315">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="3c631-316">&ensp;平台 **：4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="3c631-316">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="3c631-317">&ensp;引擎 **：1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="3c631-317">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="3c631-318">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-318">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="3c631-319">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-319">What's new</span></span>

- <span data-ttu-id="3c631-320">添加到[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 限制选项</span><span class="sxs-lookup"><span data-stu-id="3c631-320">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="3c631-321">改进诊断功能</span><span class="sxs-lookup"><span data-stu-id="3c631-321">Improve diagnostic capability</span></span>
- <span data-ttu-id="3c631-322">将安全智能超时 (5 分钟) </span><span class="sxs-lookup"><span data-stu-id="3c631-322">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="3c631-323">扩展 AMSI 引擎内部日志功能</span><span class="sxs-lookup"><span data-stu-id="3c631-323">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="3c631-324">改进进程阻止通知</span><span class="sxs-lookup"><span data-stu-id="3c631-324">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="3c631-325">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-325">Known Issues</span></span>
<span data-ttu-id="3c631-326">[**Fixed**]Microsoft Defender 防病毒扫描时跳过文件。</span><span class="sxs-lookup"><span data-stu-id="3c631-326">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="3c631-327">2020 年 2 月 (平台： - |引擎：1.1.16800.2) </span><span class="sxs-lookup"><span data-stu-id="3c631-327">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="3c631-328">&ensp;安全智能更新版本 **：1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="3c631-328">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="3c631-329">&ensp;发布时间 **：2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-329">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="3c631-330">&ensp;平台/客户端： **-**</span><span class="sxs-lookup"><span data-stu-id="3c631-330">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="3c631-331">&ensp;引擎 **：1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="3c631-331">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="3c631-332">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-332">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="3c631-333">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-333">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="3c631-334">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-334">Known Issues</span></span>
<span data-ttu-id="3c631-335">无已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-335">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="3c631-336">2020 年 1 月 (平台：4.18.2001.10 |引擎：1.1.16700.2) </span><span class="sxs-lookup"><span data-stu-id="3c631-336">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="3c631-337">安全智能更新版本 **：1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-337">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="3c631-338">发布时间 **：2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-338">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="3c631-339">平台/客户端 **：4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="3c631-339">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="3c631-340">引擎 **：1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="3c631-340">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="3c631-341">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="3c631-341">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="3c631-342">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-342">What's new</span></span>

- <span data-ttu-id="3c631-343">修复了 WS2016 上的 BSOD 与Exchange</span><span class="sxs-lookup"><span data-stu-id="3c631-343">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="3c631-344">当 TMP 重定向到网络路径时支持平台更新</span><span class="sxs-lookup"><span data-stu-id="3c631-344">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="3c631-345">平台和引擎版本已添加到 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="3c631-345">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="3c631-346">将紧急签名更新扩展到 [被动模式](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="3c631-346">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="3c631-347">修复 4.18.1911.3 挂起</span><span class="sxs-lookup"><span data-stu-id="3c631-347">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="3c631-348">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-348">Known Issues</span></span>

<span data-ttu-id="3c631-349">[**修复**][使用新式待机](/windows-hardware/design/device-experiences/modern-standby)模式的设备可能会遇到与 Windows Defender 筛选器驱动程序的挂起，导致保护差距。</span><span class="sxs-lookup"><span data-stu-id="3c631-349">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="3c631-350">受影响的计算机向客户显示尚未更新到最新的反恶意软件平台。</span><span class="sxs-lookup"><span data-stu-id="3c631-350">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="3c631-351">此更新为：</span><span class="sxs-lookup"><span data-stu-id="3c631-351">This update is:</span></span>
> - <span data-ttu-id="3c631-352">运行较低版本的平台以支持 SHA2 的 RS1 设备需要;</span><span class="sxs-lookup"><span data-stu-id="3c631-352">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="3c631-353">对于有挂起问题的系统，具有重新启动标志;</span><span class="sxs-lookup"><span data-stu-id="3c631-353">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="3c631-354">在 2020 年 4 月重新发布，并且不会被更新的更新所取代，以保持将来的可用性;</span><span class="sxs-lookup"><span data-stu-id="3c631-354">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="3c631-355">因重启要求而分类为更新;和</span><span class="sxs-lookup"><span data-stu-id="3c631-355">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="3c631-356">仅提供与 Windows Update 一[起提供](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="3c631-356">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="3c631-357">2019 年 11 月 (平台：4.18.1911.3 |引擎：1.1.16600.7) </span><span class="sxs-lookup"><span data-stu-id="3c631-357">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="3c631-358">安全智能更新版本 **：1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-358">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="3c631-359">发布时间 **：2019 年 12 月 7 日**</span><span class="sxs-lookup"><span data-stu-id="3c631-359">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="3c631-360">平台 **：4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="3c631-360">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="3c631-361">引擎 **：1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="3c631-361">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="3c631-362">支持阶段： **不支持**</span><span class="sxs-lookup"><span data-stu-id="3c631-362">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="3c631-363">最近更新</span><span class="sxs-lookup"><span data-stu-id="3c631-363">What's new</span></span>

- <span data-ttu-id="3c631-364">修复了 MpCmdRun 跟踪级别</span><span class="sxs-lookup"><span data-stu-id="3c631-364">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="3c631-365">修复了 WDFilter 版本信息</span><span class="sxs-lookup"><span data-stu-id="3c631-365">Fixed WDFilter version info</span></span>
- <span data-ttu-id="3c631-366">改进 PUA (通知) </span><span class="sxs-lookup"><span data-stu-id="3c631-366">Improve notifications (PUA)</span></span>
- <span data-ttu-id="3c631-367">添加 MRT 日志以支持文件</span><span class="sxs-lookup"><span data-stu-id="3c631-367">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="3c631-368">已知问题</span><span class="sxs-lookup"><span data-stu-id="3c631-368">Known Issues</span></span>
<span data-ttu-id="3c631-369">安装此更新后，设备需要跳转程序包 4.18.2001.10 才能更新到最新的平台版本。</span><span class="sxs-lookup"><span data-stu-id="3c631-369">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="3c631-370">Microsoft Defender 防病毒平台支持</span><span class="sxs-lookup"><span data-stu-id="3c631-370">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="3c631-371">平台和引擎更新按月提供。</span><span class="sxs-lookup"><span data-stu-id="3c631-371">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="3c631-372">若要完全受支持，请及时了解最新的平台更新。</span><span class="sxs-lookup"><span data-stu-id="3c631-372">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="3c631-373">我们的支持结构是动态的，根据最新平台版本的可用性，将发展为两个阶段：</span><span class="sxs-lookup"><span data-stu-id="3c631-373">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="3c631-374">**安全和关键更新服务阶段** - 运行最新平台版本时，你将有资格接收反恶意软件平台的安全和关键更新。</span><span class="sxs-lookup"><span data-stu-id="3c631-374">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="3c631-375">**技术支持 (仅在)** 阶段 - 发布新平台版本后，对早期版本 (N-2) 的支持将仅减少为技术支持。</span><span class="sxs-lookup"><span data-stu-id="3c631-375">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="3c631-376">不再支持 N-2 之前的平台版本。\*</span><span class="sxs-lookup"><span data-stu-id="3c631-376">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="3c631-377">\*将继续为从 Windows 10 版本升级提供技术支持 (请参阅[Windows 10](#platform-version-included-with-windows-10-releases)版本中包含的平台版本) 到最新平台版本。</span><span class="sxs-lookup"><span data-stu-id="3c631-377">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="3c631-378">在技术支持 (仅在) 阶段，商业上合理的支持事件将通过 Microsoft 客户服务 & 支持和 Microsoft 的托管支持产品/服务 (如 Premier Support) 提供。</span><span class="sxs-lookup"><span data-stu-id="3c631-378">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="3c631-379">如果支持事件需要上报开发以进一步提供指导、需要非安全更新或需要安全更新，将要求客户升级到最新平台版本或中间 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="3c631-379">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="3c631-380">版本中包含的平台Windows 10版本</span><span class="sxs-lookup"><span data-stu-id="3c631-380">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="3c631-381">下表提供了最新 Microsoft Defender 防病毒 版本附带的 Microsoft Defender 防病毒 Windows 10 平台和引擎版本：</span><span class="sxs-lookup"><span data-stu-id="3c631-381">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="3c631-382">Windows 10发布</span><span class="sxs-lookup"><span data-stu-id="3c631-382">Windows 10 release</span></span>  |<span data-ttu-id="3c631-383">平台版本</span><span class="sxs-lookup"><span data-stu-id="3c631-383">Platform version</span></span>  |<span data-ttu-id="3c631-384">引擎版本</span><span class="sxs-lookup"><span data-stu-id="3c631-384">Engine version</span></span> |<span data-ttu-id="3c631-385">支持阶段</span><span class="sxs-lookup"><span data-stu-id="3c631-385">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="3c631-386">2004 (20H1/20H2) </span><span class="sxs-lookup"><span data-stu-id="3c631-386">2004  (20H1/20H2)</span></span> |<span data-ttu-id="3c631-387">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="3c631-387">4.18.1909.6</span></span> |<span data-ttu-id="3c631-388">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="3c631-388">1.1.17000.2</span></span> | <span data-ttu-id="3c631-389">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="3c631-389">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3c631-390">1909 (19H2) </span><span class="sxs-lookup"><span data-stu-id="3c631-390">1909  (19H2)</span></span> |<span data-ttu-id="3c631-391">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="3c631-391">4.18.1902.5</span></span> |<span data-ttu-id="3c631-392">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="3c631-392">1.1.16700.3</span></span> | <span data-ttu-id="3c631-393">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="3c631-393">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3c631-394">1903 (19H1) </span><span class="sxs-lookup"><span data-stu-id="3c631-394">1903  (19H1)</span></span> |<span data-ttu-id="3c631-395">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="3c631-395">4.18.1902.5</span></span> |<span data-ttu-id="3c631-396">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="3c631-396">1.1.15600.4</span></span> | <span data-ttu-id="3c631-397">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="3c631-397">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3c631-398">1809 (RS5) </span><span class="sxs-lookup"><span data-stu-id="3c631-398">1809  (RS5)</span></span> |<span data-ttu-id="3c631-399">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="3c631-399">4.18.1807.18075</span></span> |<span data-ttu-id="3c631-400">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="3c631-400">1.1.15000.2</span></span> | <span data-ttu-id="3c631-401">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="3c631-401">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3c631-402">1803 (RS4) </span><span class="sxs-lookup"><span data-stu-id="3c631-402">1803  (RS4)</span></span> |<span data-ttu-id="3c631-403">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="3c631-403">4.13.17134.1</span></span> |<span data-ttu-id="3c631-404">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="3c631-404">1.1.14600.4</span></span> | <span data-ttu-id="3c631-405">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="3c631-405">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3c631-406">1709 (RS3) </span><span class="sxs-lookup"><span data-stu-id="3c631-406">1709  (RS3)</span></span> |<span data-ttu-id="3c631-407">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="3c631-407">4.12.16299.15</span></span> |<span data-ttu-id="3c631-408">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="3c631-408">1.1.14104.0</span></span> | <span data-ttu-id="3c631-409">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="3c631-409">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3c631-410">1703 (RS2) </span><span class="sxs-lookup"><span data-stu-id="3c631-410">1703  (RS2)</span></span> |<span data-ttu-id="3c631-411">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="3c631-411">4.11.15603.2</span></span> |<span data-ttu-id="3c631-412">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="3c631-412">1.1.13504.0</span></span> | <span data-ttu-id="3c631-413">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="3c631-413">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="3c631-414">1607 (RS1) </span><span class="sxs-lookup"><span data-stu-id="3c631-414">1607 (RS1)</span></span> |<span data-ttu-id="3c631-415">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="3c631-415">4.10.14393.3683</span></span> |<span data-ttu-id="3c631-416">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="3c631-416">1.1.12805.0</span></span> | <span data-ttu-id="3c631-417">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="3c631-417">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="3c631-418">有关Windows 10的信息，请参阅生命周期[Windows表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="3c631-418">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="3c631-419">DISM 部署映像服务和管理 (更新) </span><span class="sxs-lookup"><span data-stu-id="3c631-419">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="3c631-420">我们建议使用最新的防病毒和反恶意软件更新更新 Windows 10 (Enterprise、Pro 和家庭版) 、Windows Server 2019 和 Windows Server 2016 操作系统安装映像。</span><span class="sxs-lookup"><span data-stu-id="3c631-420">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="3c631-421">使操作系统安装映像保持最新有助于避免保护差距。</span><span class="sxs-lookup"><span data-stu-id="3c631-421">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="3c631-422">有关详细信息，请参阅适用于操作系统[安装映像Windows Microsoft Defender 更新](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="3c631-422">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="3c631-423">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="3c631-423">1.1.2106.01</span></span></summary>

<span data-ttu-id="3c631-424">&ensp;程序包版本 **：1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="3c631-424">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="3c631-425">&ensp;平台版本 **：4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="3c631-425">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="3c631-426">&ensp;引擎版本 **：1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="3c631-426">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="3c631-427">&ensp;签名版本 **：1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-427">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3c631-428">修补程序</span><span class="sxs-lookup"><span data-stu-id="3c631-428">Fixes</span></span>
- <span data-ttu-id="3c631-429">无</span><span class="sxs-lookup"><span data-stu-id="3c631-429">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3c631-430">其他信息</span><span class="sxs-lookup"><span data-stu-id="3c631-430">Additional information</span></span>
- <span data-ttu-id="3c631-431">无</span><span class="sxs-lookup"><span data-stu-id="3c631-431">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3c631-432">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="3c631-432">1.1.2105.01</span></span></summary>

<span data-ttu-id="3c631-433">&ensp;程序包版本 **：1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="3c631-433">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="3c631-434">&ensp;平台版本 **：4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="3c631-434">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="3c631-435">&ensp;引擎版本 **：1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="3c631-435">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="3c631-436">&ensp;签名版本 **：1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-436">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3c631-437">修补程序</span><span class="sxs-lookup"><span data-stu-id="3c631-437">Fixes</span></span>
- <span data-ttu-id="3c631-438">无</span><span class="sxs-lookup"><span data-stu-id="3c631-438">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3c631-439">其他信息</span><span class="sxs-lookup"><span data-stu-id="3c631-439">Additional information</span></span>
- <span data-ttu-id="3c631-440">无</span><span class="sxs-lookup"><span data-stu-id="3c631-440">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3c631-441">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="3c631-441">1.1.2104.01</span></span></summary>

<span data-ttu-id="3c631-442">&ensp;程序包版本 **：1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="3c631-442">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="3c631-443">&ensp;平台版本 **：4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="3c631-443">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="3c631-444">&ensp;引擎版本 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-444">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="3c631-445">&ensp;签名版本 **：1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-445">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3c631-446">修补程序</span><span class="sxs-lookup"><span data-stu-id="3c631-446">Fixes</span></span>
- <span data-ttu-id="3c631-447">无</span><span class="sxs-lookup"><span data-stu-id="3c631-447">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3c631-448">其他信息</span><span class="sxs-lookup"><span data-stu-id="3c631-448">Additional information</span></span>
- <span data-ttu-id="3c631-449">无</span><span class="sxs-lookup"><span data-stu-id="3c631-449">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3c631-450">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="3c631-450">1.1.2103.01</span></span></summary>

<span data-ttu-id="3c631-451">&ensp;程序包版本 **：1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="3c631-451">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="3c631-452">&ensp;平台版本 **：4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="3c631-452">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="3c631-453">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-453">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="3c631-454">&ensp;签名版本 **：1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-454">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3c631-455">修补程序</span><span class="sxs-lookup"><span data-stu-id="3c631-455">Fixes</span></span>
- <span data-ttu-id="3c631-456">无</span><span class="sxs-lookup"><span data-stu-id="3c631-456">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3c631-457">其他信息</span><span class="sxs-lookup"><span data-stu-id="3c631-457">Additional information</span></span>
- <span data-ttu-id="3c631-458">无</span><span class="sxs-lookup"><span data-stu-id="3c631-458">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3c631-459">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="3c631-459">1.1.2102.03</span></span></summary>

<span data-ttu-id="3c631-460">&ensp;程序包版本 **：1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="3c631-460">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="3c631-461">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="3c631-461">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="3c631-462">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-462">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="3c631-463">&ensp;签名版本 **：1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-463">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3c631-464">修补程序</span><span class="sxs-lookup"><span data-stu-id="3c631-464">Fixes</span></span>
- <span data-ttu-id="3c631-465">无</span><span class="sxs-lookup"><span data-stu-id="3c631-465">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3c631-466">其他信息</span><span class="sxs-lookup"><span data-stu-id="3c631-466">Additional information</span></span>
- <span data-ttu-id="3c631-467">无</span><span class="sxs-lookup"><span data-stu-id="3c631-467">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3c631-468">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="3c631-468">1.1.2101.02</span></span></summary>

<span data-ttu-id="3c631-469">&ensp;程序包版本 **：1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="3c631-469">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="3c631-470">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="3c631-470">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="3c631-471">&ensp;引擎版本 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="3c631-471">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="3c631-472">&ensp;签名版本 **：1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-472">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3c631-473">修补程序</span><span class="sxs-lookup"><span data-stu-id="3c631-473">Fixes</span></span>
- <span data-ttu-id="3c631-474">无</span><span class="sxs-lookup"><span data-stu-id="3c631-474">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3c631-475">其他信息</span><span class="sxs-lookup"><span data-stu-id="3c631-475">Additional information</span></span>
- <span data-ttu-id="3c631-476">无</span><span class="sxs-lookup"><span data-stu-id="3c631-476">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3c631-477">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="3c631-477">1.1.2012.01</span></span></summary>

<span data-ttu-id="3c631-478">&ensp;程序包版本 **：1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="3c631-478">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="3c631-479">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="3c631-479">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="3c631-480">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-480">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="3c631-481">&ensp;签名版本 **：1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-481">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3c631-482">修补程序</span><span class="sxs-lookup"><span data-stu-id="3c631-482">Fixes</span></span>
- <span data-ttu-id="3c631-483">无</span><span class="sxs-lookup"><span data-stu-id="3c631-483">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3c631-484">其他信息</span><span class="sxs-lookup"><span data-stu-id="3c631-484">Additional information</span></span>
- <span data-ttu-id="3c631-485">无</span><span class="sxs-lookup"><span data-stu-id="3c631-485">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3c631-486">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="3c631-486">1.1.2011.02</span></span></summary>

<span data-ttu-id="3c631-487">&ensp;程序包版本 **：1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="3c631-487">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="3c631-488">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="3c631-488">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="3c631-489">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-489">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="3c631-490">&ensp;签名版本 **：1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-490">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3c631-491">修补程序</span><span class="sxs-lookup"><span data-stu-id="3c631-491">Fixes</span></span>
- <span data-ttu-id="3c631-492">无</span><span class="sxs-lookup"><span data-stu-id="3c631-492">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3c631-493">其他信息</span><span class="sxs-lookup"><span data-stu-id="3c631-493">Additional information</span></span>
- <span data-ttu-id="3c631-494">刷新Microsoft Defender 防病毒签名</span><span class="sxs-lookup"><span data-stu-id="3c631-494">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3c631-495">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="3c631-495">1.1.2011.01</span></span></summary>

<span data-ttu-id="3c631-496">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="3c631-496">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="3c631-497">&ensp;平台版本 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="3c631-497">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="3c631-498">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-498">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="3c631-499">&ensp;签名版本 **：1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-499">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3c631-500">修补程序</span><span class="sxs-lookup"><span data-stu-id="3c631-500">Fixes</span></span>
- <span data-ttu-id="3c631-501">无</span><span class="sxs-lookup"><span data-stu-id="3c631-501">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3c631-502">其他信息</span><span class="sxs-lookup"><span data-stu-id="3c631-502">Additional information</span></span>
- <span data-ttu-id="3c631-503">无</span><span class="sxs-lookup"><span data-stu-id="3c631-503">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="3c631-504">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="3c631-504">1.1.2009.10</span></span></summary>

<span data-ttu-id="3c631-505">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="3c631-505">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="3c631-506">&ensp;平台版本 **：4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="3c631-506">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="3c631-507">&ensp;引擎版本 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="3c631-507">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="3c631-508">&ensp;签名版本 **：1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="3c631-508">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="3c631-509">修补程序</span><span class="sxs-lookup"><span data-stu-id="3c631-509">Fixes</span></span>
- <span data-ttu-id="3c631-510">无</span><span class="sxs-lookup"><span data-stu-id="3c631-510">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="3c631-511">其他信息</span><span class="sxs-lookup"><span data-stu-id="3c631-511">Additional information</span></span>
- <span data-ttu-id="3c631-512">添加了对 Windows 10 RS1 或更高版本操作系统安装映像的支持。</span><span class="sxs-lookup"><span data-stu-id="3c631-512">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="3c631-513">其他资源</span><span class="sxs-lookup"><span data-stu-id="3c631-513">Additional resources</span></span>

| <span data-ttu-id="3c631-514">文章</span><span class="sxs-lookup"><span data-stu-id="3c631-514">Article</span></span> | <span data-ttu-id="3c631-515">说明</span><span class="sxs-lookup"><span data-stu-id="3c631-515">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="3c631-516">适用于操作系统安装映像Windows Microsoft Defender 更新</span><span class="sxs-lookup"><span data-stu-id="3c631-516">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="3c631-517">查看适用于操作系统安装映像的反恶意软件更新程序包 (WIM 和 VHD 文件) 。</span><span class="sxs-lookup"><span data-stu-id="3c631-517">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="3c631-518">获取 Microsoft Defender 防病毒、Windows 10 (Enterprise、Pro、家庭版) 、Windows Server 2019 Windows Server 2016更新。</span><span class="sxs-lookup"><span data-stu-id="3c631-518">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="3c631-519">管理保护更新的下载和应用方式</span><span class="sxs-lookup"><span data-stu-id="3c631-519">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="3c631-520">保护更新可以通过多个源提供。</span><span class="sxs-lookup"><span data-stu-id="3c631-520">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="3c631-521">管理何时应下载和应用保护更新</span><span class="sxs-lookup"><span data-stu-id="3c631-521">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="3c631-522">你可以计划应下载保护更新的时间。</span><span class="sxs-lookup"><span data-stu-id="3c631-522">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="3c631-523">管理过期终结点的更新</span><span class="sxs-lookup"><span data-stu-id="3c631-523">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="3c631-524">如果终结点错过更新或计划扫描，可以在用户下次登录时强制进行更新或扫描。</span><span class="sxs-lookup"><span data-stu-id="3c631-524">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="3c631-525">管理基于事件的强制更新</span><span class="sxs-lookup"><span data-stu-id="3c631-525">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="3c631-526">你可以将保护更新设置为在启动时或在某些云提供的保护事件之后下载。</span><span class="sxs-lookup"><span data-stu-id="3c631-526">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="3c631-527">管理移动设备和虚拟机 （VM） 的更新</span><span class="sxs-lookup"><span data-stu-id="3c631-527">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="3c631-528">你可以指定对移动设备和虚拟机特别有用的设置，例如是否应该使用电池电源进行更新。</span><span class="sxs-lookup"><span data-stu-id="3c631-528">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
