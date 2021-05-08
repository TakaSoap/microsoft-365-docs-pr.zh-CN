---
title: 管理 Microsoft Defender 防病毒更新和应用基线
description: 管理 Microsoft Defender 防病毒接收保护和产品更新方式。
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
ms.date: 05/06/2021
ms.openlocfilehash: 22a173d39c3ab8d1afd91a33b05e02e58da24aaa
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274552"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="5bfca-104">管理 Microsoft Defender 防病毒更新和应用基线</span><span class="sxs-lookup"><span data-stu-id="5bfca-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="5bfca-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5bfca-105">**Applies to:**</span></span>

- [<span data-ttu-id="5bfca-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5bfca-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="5bfca-107">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="5bfca-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="5bfca-108">有两种类型的更新与使 Microsoft Defender 防病毒保持最新有关：</span><span class="sxs-lookup"><span data-stu-id="5bfca-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="5bfca-109">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-109">Security intelligence updates</span></span>
- <span data-ttu-id="5bfca-110">产品更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5bfca-111">使 Microsoft Defender 防病毒保持最新至关重要，可确保你的设备具有防止新的恶意软件和攻击技术所需的最新技术和功能。</span><span class="sxs-lookup"><span data-stu-id="5bfca-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="5bfca-112">确保更新防病毒保护，即使 Microsoft Defender 防病毒在被动 [模式下运行](./microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="5bfca-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="5bfca-113">若要查看最新的引擎、平台和签名日期，请访问 Microsoft Defender 防病毒和其他 Microsoft 反 [恶意软件的安全智能更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="5bfca-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="5bfca-114">安全智能更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-114">Security intelligence updates</span></span>

<span data-ttu-id="5bfca-115">Microsoft Defender 防病毒 [使用云](cloud-protection-microsoft-defender-antivirus.md) 提供的保护 (也称为 Microsoft 高级保护服务或 MAPS) 并定期下载安全智能更新以提供保护。</span><span class="sxs-lookup"><span data-stu-id="5bfca-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="5bfca-116">更新以以下 KB 编号发布：</span><span class="sxs-lookup"><span data-stu-id="5bfca-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="5bfca-117">Microsoft Defender 防病毒：KB2267602</span><span class="sxs-lookup"><span data-stu-id="5bfca-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="5bfca-118">System Center Endpoint Protection：KB2461484</span><span class="sxs-lookup"><span data-stu-id="5bfca-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="5bfca-119">云提供的保护始终打开，并且需要与 Internet 的活动连接以正常运行。</span><span class="sxs-lookup"><span data-stu-id="5bfca-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="5bfca-120">安全智能更新按计划节奏进行， (策略策略配置) 。</span><span class="sxs-lookup"><span data-stu-id="5bfca-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="5bfca-121">有关详细信息，请参阅在 Microsoft Defender 防病毒中使用 Microsoft 云 [提供的保护](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="5bfca-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="5bfca-122">有关最近安全智能更新的列表，请参阅 Microsoft Defender 防病毒和其他 Microsoft 反 [恶意软件的安全智能更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="5bfca-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="5bfca-123">引擎更新包含在安全智能更新中，并按月发布。</span><span class="sxs-lookup"><span data-stu-id="5bfca-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="5bfca-124">产品更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-124">Product updates</span></span>

<span data-ttu-id="5bfca-125">Microsoft Defender 防病毒需要每月更新 [ (KB4052623](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform))  (称为平台更新 *) ，* 并且将接收 Windows 10 版本旁边的主要功能更新。</span><span class="sxs-lookup"><span data-stu-id="5bfca-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="5bfca-126">可以通过以下方法之一管理更新的分发：</span><span class="sxs-lookup"><span data-stu-id="5bfca-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="5bfca-127">Windows Server Update Service (WSUS) </span><span class="sxs-lookup"><span data-stu-id="5bfca-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="5bfca-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5bfca-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="5bfca-129">用于将 Microsoft 和 Windows 更新部署到网络中终结点的常用方法。</span><span class="sxs-lookup"><span data-stu-id="5bfca-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="5bfca-130">有关详细信息，请参阅管理 [Microsoft Defender 防病毒保护更新的源](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="5bfca-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="5bfca-131">每月更新会分期发布，从而在 Window Server Update Services 中显示 [多个程序包](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)。</span><span class="sxs-lookup"><span data-stu-id="5bfca-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="5bfca-132">每月平台和引擎版本</span><span class="sxs-lookup"><span data-stu-id="5bfca-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="5bfca-133">若要了解如何更新或安装平台更新，请参阅反恶意软件Windows Defender [更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="5bfca-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="5bfca-134">我们的所有更新都包含</span><span class="sxs-lookup"><span data-stu-id="5bfca-134">All our updates contain</span></span> 
- <span data-ttu-id="5bfca-135">性能改进;</span><span class="sxs-lookup"><span data-stu-id="5bfca-135">performance improvements;</span></span>
- <span data-ttu-id="5bfca-136">可服务性改进;和</span><span class="sxs-lookup"><span data-stu-id="5bfca-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="5bfca-137">集成改进 (云、Microsoft 365 Defender) 。</span><span class="sxs-lookup"><span data-stu-id="5bfca-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="5bfca-138">2021 年 4 月 (平台：4.19.2104.9|引擎：1.1.18100.5) </span><span class="sxs-lookup"><span data-stu-id="5bfca-138">April-2021 (Platform: 4.19.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="5bfca-139">&ensp;安全智能更新版本 **：1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="5bfca-140">&ensp;发布时间 **：2021 年 4 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="5bfca-141">&ensp;平台 **：4.19.2104.9**</span><span class="sxs-lookup"><span data-stu-id="5bfca-141">&ensp;Platform: **4.19.2104.9**</span></span>  
<span data-ttu-id="5bfca-142">&ensp;引擎 **：1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="5bfca-143">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="5bfca-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-144">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-144">What's new</span></span>
- <span data-ttu-id="5bfca-145">其他行为监视逻辑</span><span class="sxs-lookup"><span data-stu-id="5bfca-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="5bfca-146">改进了内核模式键记录器检测</span><span class="sxs-lookup"><span data-stu-id="5bfca-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="5bfca-147">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-147">Known Issues</span></span>
<span data-ttu-id="5bfca-148">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5bfca-149">2021 年 3 月 (平台：4.19.2103.7 |引擎：1.1.18000.5) </span><span class="sxs-lookup"><span data-stu-id="5bfca-149">March-2021 (Platform: 4.19.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="5bfca-150">&ensp;安全智能更新版本 **：1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="5bfca-151">&ensp;发布时间 **：2021 年 4 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="5bfca-152">&ensp;平台 **：4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="5bfca-152">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="5bfca-153">&ensp;引擎 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="5bfca-154">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="5bfca-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-155">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-155">What's new</span></span>

- <span data-ttu-id="5bfca-156">对行为监控引擎的改进</span><span class="sxs-lookup"><span data-stu-id="5bfca-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="5bfca-157">扩展的网络暴力攻击缓解措施</span><span class="sxs-lookup"><span data-stu-id="5bfca-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="5bfca-158">启用防篡改保护 [时的其他失败](prevent-changes-to-security-settings-with-tamper-protection.md) 篡改尝试事件生成</span><span class="sxs-lookup"><span data-stu-id="5bfca-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="5bfca-159">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-159">Known Issues</span></span>
<span data-ttu-id="5bfca-160">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5bfca-161">2021 年 2 月 (平台：4.19.2102.3 |引擎：1.1.17900.7) </span><span class="sxs-lookup"><span data-stu-id="5bfca-161">February-2021 (Platform: 4.19.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="5bfca-162">&ensp;安全智能更新版本 **：1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="5bfca-163">&ensp;已发布 **：2021 年 3 月 9 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="5bfca-164">&ensp;平台 **：4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="5bfca-164">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="5bfca-165">&ensp;引擎 **：1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="5bfca-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="5bfca-166">&ensp;支持阶段： **安全和关键更新**</span><span class="sxs-lookup"><span data-stu-id="5bfca-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-167">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-167">What's new</span></span>

- <span data-ttu-id="5bfca-168">通过防篡改保护 [改进了服务恢复](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="5bfca-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="5bfca-169">扩展防篡改保护作用域</span><span class="sxs-lookup"><span data-stu-id="5bfca-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="5bfca-170">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-170">Known Issues</span></span>
<span data-ttu-id="5bfca-171">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="5bfca-172">旧版本更新：仅技术升级支持</span><span class="sxs-lookup"><span data-stu-id="5bfca-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="5bfca-173">发布新程序包版本后，仅对前两个版本的支持减少到技术支持。</span><span class="sxs-lookup"><span data-stu-id="5bfca-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="5bfca-174">低于本部分中列出的版本，并且仅提供用于技术升级支持的版本。</span><span class="sxs-lookup"><span data-stu-id="5bfca-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="5bfca-175">2021 年 1 月 (平台：4.18.2101.9 |引擎：1.1.17800.5) </span><span class="sxs-lookup"><span data-stu-id="5bfca-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="5bfca-176">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="5bfca-177">&ensp;发布时间 **：2021 年 2 月 2 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="5bfca-178">&ensp;平台 **：4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="5bfca-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="5bfca-179">&ensp;引擎 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="5bfca-180">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-181">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-181">What's new</span></span>

- <span data-ttu-id="5bfca-182">Shellcode 攻击检测改进</span><span class="sxs-lookup"><span data-stu-id="5bfca-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="5bfca-183">提高了凭据窃取尝试的可见性</span><span class="sxs-lookup"><span data-stu-id="5bfca-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="5bfca-184">Microsoft Defender 防病毒服务中的反威胁功能的改进</span><span class="sxs-lookup"><span data-stu-id="5bfca-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="5bfca-185">改进了对 x64 ARM的支持</span><span class="sxs-lookup"><span data-stu-id="5bfca-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="5bfca-186">修复：实时保护执行初始检测后，EDR 阻止通知仍保留在威胁历史记录中</span><span class="sxs-lookup"><span data-stu-id="5bfca-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="5bfca-187">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-187">Known Issues</span></span>
<span data-ttu-id="5bfca-188">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5bfca-189">2020 年 11 月 (平台：4.18.2011.6 |引擎：1.1.17700.4) </span><span class="sxs-lookup"><span data-stu-id="5bfca-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="5bfca-190">&ensp;安全智能更新版本 **：1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="5bfca-191">&ensp;发布时间 **：2020 年 12 月 3 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="5bfca-192">&ensp;平台 **：4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="5bfca-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="5bfca-193">&ensp;引擎 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="5bfca-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="5bfca-194">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-195">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-195">What's new</span></span>

- <span data-ttu-id="5bfca-196">改进 [的 SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 状态支持日志记录</span><span class="sxs-lookup"><span data-stu-id="5bfca-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="5bfca-197">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-197">Known Issues</span></span>
<span data-ttu-id="5bfca-198">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5bfca-199">2020 年 10 月 (平台：4.18.2010.7 |引擎：1.1.17600.5) </span><span class="sxs-lookup"><span data-stu-id="5bfca-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="5bfca-200">&ensp;安全智能更新版本 **：1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="5bfca-201">&ensp;发布时间 **：2020 年 10 月 29 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="5bfca-202">&ensp;平台 **：4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="5bfca-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="5bfca-203">&ensp;引擎 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="5bfca-204">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-205">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-205">What's new</span></span>

- <span data-ttu-id="5bfca-206">特殊威胁类别的新说明</span><span class="sxs-lookup"><span data-stu-id="5bfca-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="5bfca-207">改进的模拟功能</span><span class="sxs-lookup"><span data-stu-id="5bfca-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="5bfca-208">改进了主机地址允许/阻止功能</span><span class="sxs-lookup"><span data-stu-id="5bfca-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="5bfca-209">Defender CSP 中用于忽略本地用户排除项合并的新选项</span><span class="sxs-lookup"><span data-stu-id="5bfca-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="5bfca-210">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-210">Known Issues</span></span>

<span data-ttu-id="5bfca-211">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="5bfca-212">2020 年 9 月 (平台：4.18.2009.7 |引擎：1.1.17500.4) </span><span class="sxs-lookup"><span data-stu-id="5bfca-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="5bfca-213">&ensp;安全智能更新版本 **：1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="5bfca-214">&ensp;发布时间 **：2020 年 10 月 1 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="5bfca-215">&ensp;平台 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="5bfca-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="5bfca-216">&ensp;引擎 **：1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="5bfca-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="5bfca-217">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-218">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-218">What's new</span></span>

- <span data-ttu-id="5bfca-219">需要管理员权限才能还原隔离中的文件</span><span class="sxs-lookup"><span data-stu-id="5bfca-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="5bfca-220">XML 格式事件现在受支持</span><span class="sxs-lookup"><span data-stu-id="5bfca-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="5bfca-221">忽略排除合并的云解决方案提供商支持</span><span class="sxs-lookup"><span data-stu-id="5bfca-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="5bfca-222">用于：</span><span class="sxs-lookup"><span data-stu-id="5bfca-222">New management interfaces for:</span></span>
   - <span data-ttu-id="5bfca-223">UDP 检查</span><span class="sxs-lookup"><span data-stu-id="5bfca-223">UDP Inspection</span></span>
   - <span data-ttu-id="5bfca-224">Server 2019 上的网络保护</span><span class="sxs-lookup"><span data-stu-id="5bfca-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="5bfca-225">网络保护的 IP 地址排除项</span><span class="sxs-lookup"><span data-stu-id="5bfca-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="5bfca-226">改进了对 TPM 测量的可见性</span><span class="sxs-lookup"><span data-stu-id="5bfca-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="5bfca-227">改进的 Office VBA 模块扫描</span><span class="sxs-lookup"><span data-stu-id="5bfca-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="5bfca-228">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-228">Known Issues</span></span>

<span data-ttu-id="5bfca-229">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="5bfca-230">2020 年 8 月 (平台：4.18.2008.9 |引擎：1.1.17400.5) </span><span class="sxs-lookup"><span data-stu-id="5bfca-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="5bfca-231">&ensp;安全智能更新版本 **：1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="5bfca-232">&ensp;发布时间 **：2020 年 8 月 27 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="5bfca-233">&ensp;平台 **：4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="5bfca-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="5bfca-234">&ensp;引擎 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="5bfca-235">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="5bfca-236">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-236">What's new</span></span>

- <span data-ttu-id="5bfca-237">添加更多遥测事件</span><span class="sxs-lookup"><span data-stu-id="5bfca-237">Add more telemetry events</span></span>
- <span data-ttu-id="5bfca-238">改进了扫描事件遥测</span><span class="sxs-lookup"><span data-stu-id="5bfca-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="5bfca-239">改进了内存扫描行为监视</span><span class="sxs-lookup"><span data-stu-id="5bfca-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="5bfca-240">改进的宏流扫描</span><span class="sxs-lookup"><span data-stu-id="5bfca-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="5bfca-241">已 `AMRunningMode` 添加到 Get-MpComputerStatus PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="5bfca-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="5bfca-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 将被忽略。</span><span class="sxs-lookup"><span data-stu-id="5bfca-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="5bfca-243">Microsoft Defender 防病毒在检测到其他防病毒程序时自动关闭自身。</span><span class="sxs-lookup"><span data-stu-id="5bfca-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="5bfca-244">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-244">Known Issues</span></span>
<span data-ttu-id="5bfca-245">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5bfca-246">2020 年 7 月 (平台：4.18.2007.8 |引擎：1.1.17300.4) </span><span class="sxs-lookup"><span data-stu-id="5bfca-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="5bfca-247">&ensp;安全智能更新版本 **：1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="5bfca-248">&ensp;发布时间 **：2020 年 7 月 28 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="5bfca-249">&ensp;平台 **：4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="5bfca-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="5bfca-250">&ensp;引擎 **：1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="5bfca-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="5bfca-251">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-252">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-252">What's new</span></span>

- <span data-ttu-id="5bfca-253">改进的 BITS 遥测</span><span class="sxs-lookup"><span data-stu-id="5bfca-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="5bfca-254">改进的验证码代码签名证书验证</span><span class="sxs-lookup"><span data-stu-id="5bfca-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="5bfca-255">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-255">Known Issues</span></span>
<span data-ttu-id="5bfca-256">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5bfca-257">2020 年 6 月 (平台：4.18.2006.10 |引擎：1.1.17200.2) </span><span class="sxs-lookup"><span data-stu-id="5bfca-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="5bfca-258">&ensp;安全智能更新版本 **：1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="5bfca-259">&ensp;发布时间 **：2020 年 6 月 22 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="5bfca-260">&ensp;平台 **：4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="5bfca-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="5bfca-261">&ensp;引擎 **：1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="5bfca-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="5bfca-262">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-263">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-263">What's new</span></span>

- <span data-ttu-id="5bfca-264">指定支持 [日志的位置的可能性](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="5bfca-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="5bfca-265">在被动模式下跳过主动的捕获扫描。</span><span class="sxs-lookup"><span data-stu-id="5bfca-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="5bfca-266">允许 Defender 更新按流量计费的连接</span><span class="sxs-lookup"><span data-stu-id="5bfca-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="5bfca-267">修复了禁用缓存时的性能调整</span><span class="sxs-lookup"><span data-stu-id="5bfca-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="5bfca-268">修复了注册表查询</span><span class="sxs-lookup"><span data-stu-id="5bfca-268">Fixed registry query</span></span> 
- <span data-ttu-id="5bfca-269">修复了 ADMX 中的扫描时间随机化</span><span class="sxs-lookup"><span data-stu-id="5bfca-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="5bfca-270">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-270">Known Issues</span></span>
<span data-ttu-id="5bfca-271">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5bfca-272">2020 年 5 月 (平台：4.18.2005.4 |引擎：1.1.17100.2) </span><span class="sxs-lookup"><span data-stu-id="5bfca-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="5bfca-273">&ensp;安全智能更新版本 **：1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="5bfca-274">&ensp;发布时间 **：2020 年 5 月 26 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="5bfca-275">&ensp;平台 **：4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="5bfca-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="5bfca-276">&ensp;引擎 **：1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="5bfca-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="5bfca-277">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-278">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-278">What's new</span></span>

- <span data-ttu-id="5bfca-279">改进了扫描事件的日志记录</span><span class="sxs-lookup"><span data-stu-id="5bfca-279">Improved logging for scan events</span></span>
- <span data-ttu-id="5bfca-280">改进了用户模式崩溃处理。</span><span class="sxs-lookup"><span data-stu-id="5bfca-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="5bfca-281">添加了防篡改保护的事件跟踪</span><span class="sxs-lookup"><span data-stu-id="5bfca-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="5bfca-282">修复了 AMSI 示例提交</span><span class="sxs-lookup"><span data-stu-id="5bfca-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="5bfca-283">修复了 AMSI 云阻止</span><span class="sxs-lookup"><span data-stu-id="5bfca-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="5bfca-284">修复了安全更新安装日志</span><span class="sxs-lookup"><span data-stu-id="5bfca-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="5bfca-285">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-285">Known Issues</span></span>
<span data-ttu-id="5bfca-286">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5bfca-287">2020 年 4 月 (平台：4.18.2004.6 |引擎：1.1.17000.2) </span><span class="sxs-lookup"><span data-stu-id="5bfca-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="5bfca-288">&ensp;安全智能更新版本 **：1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="5bfca-289">&ensp;发布时间 **：2020 年 4 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="5bfca-290">&ensp;平台 **：4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="5bfca-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="5bfca-291">&ensp;引擎 **：1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="5bfca-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="5bfca-292">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-293">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-293">What's new</span></span>
- <span data-ttu-id="5bfca-294">WDfilter 改进</span><span class="sxs-lookup"><span data-stu-id="5bfca-294">WDfilter improvements</span></span>
- <span data-ttu-id="5bfca-295">向攻击面减少检测事件添加更多可操作事件数据</span><span class="sxs-lookup"><span data-stu-id="5bfca-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="5bfca-296">诊断数据和 WMI 中的固定版本信息</span><span class="sxs-lookup"><span data-stu-id="5bfca-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="5bfca-297">修复了平台更新后 UI 中的平台版本不正确</span><span class="sxs-lookup"><span data-stu-id="5bfca-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="5bfca-298">用于无文件威胁防护的动态 URL intel</span><span class="sxs-lookup"><span data-stu-id="5bfca-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="5bfca-299">UEFI 扫描功能</span><span class="sxs-lookup"><span data-stu-id="5bfca-299">UEFI scan capability</span></span>
- <span data-ttu-id="5bfca-300">扩展更新日志记录</span><span class="sxs-lookup"><span data-stu-id="5bfca-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="5bfca-301">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-301">Known Issues</span></span>
<span data-ttu-id="5bfca-302">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="5bfca-303">2020 年 3 月 (平台：4.18.2003.8 |引擎：1.1.16900.2) </span><span class="sxs-lookup"><span data-stu-id="5bfca-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="5bfca-304">&ensp;安全智能更新版本 **：1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="5bfca-305">&ensp;已发布 **：2020 年 3 月 24 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="5bfca-306">&ensp;平台 **：4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="5bfca-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="5bfca-307">&ensp;引擎 **：1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="5bfca-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="5bfca-308">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="5bfca-309">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-309">What's new</span></span>

- <span data-ttu-id="5bfca-310">添加到[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 限制选项</span><span class="sxs-lookup"><span data-stu-id="5bfca-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="5bfca-311">改进诊断功能</span><span class="sxs-lookup"><span data-stu-id="5bfca-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="5bfca-312">将安全智能超时 (5 分钟) </span><span class="sxs-lookup"><span data-stu-id="5bfca-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="5bfca-313">扩展 AMSI 引擎内部日志功能</span><span class="sxs-lookup"><span data-stu-id="5bfca-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="5bfca-314">改进进程阻止通知</span><span class="sxs-lookup"><span data-stu-id="5bfca-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="5bfca-315">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-315">Known Issues</span></span>
<span data-ttu-id="5bfca-316">[**Fixed**]Microsoft Defender 防病毒在运行扫描时跳过文件。</span><span class="sxs-lookup"><span data-stu-id="5bfca-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="5bfca-317">2020 年 2 月 (平台： - |引擎：1.1.16800.2) </span><span class="sxs-lookup"><span data-stu-id="5bfca-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="5bfca-318">&ensp;安全智能更新版本 **：1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="5bfca-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="5bfca-319">&ensp;发布时间 **：2020 年 2 月 25 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="5bfca-320">&ensp;平台/客户端： **-**</span><span class="sxs-lookup"><span data-stu-id="5bfca-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="5bfca-321">&ensp;引擎 **：1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="5bfca-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="5bfca-322">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="5bfca-323">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="5bfca-324">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-324">Known Issues</span></span>
<span data-ttu-id="5bfca-325">无已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="5bfca-326">2020 年 1 月 (平台：4.18.2001.10 |引擎：1.1.16700.2) </span><span class="sxs-lookup"><span data-stu-id="5bfca-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="5bfca-327">安全智能更新版本 **：1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="5bfca-328">发布时间 **：2020 年 1 月 30 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="5bfca-329">平台/客户端 **：4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="5bfca-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="5bfca-330">引擎 **：1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="5bfca-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="5bfca-331">&ensp;支持阶段 **：仅支持 (升级)**</span><span class="sxs-lookup"><span data-stu-id="5bfca-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="5bfca-332">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-332">What's new</span></span>

- <span data-ttu-id="5bfca-333">WS2016 和 Exchange 上的固定 BSOD</span><span class="sxs-lookup"><span data-stu-id="5bfca-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="5bfca-334">当 TMP 重定向到网络路径时支持平台更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="5bfca-335">平台和引擎版本已添加到 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="5bfca-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="5bfca-336">将紧急签名更新扩展到 [被动模式](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="5bfca-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="5bfca-337">修复 4.18.1911.3 挂起</span><span class="sxs-lookup"><span data-stu-id="5bfca-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="5bfca-338">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-338">Known Issues</span></span>

<span data-ttu-id="5bfca-339">[**修复**] 使用现代待机模式 [的设备](/windows-hardware/design/device-experiences/modern-standby) 可能会遇到与Windows Defender筛选器驱动程序的挂起，导致保护间隙。</span><span class="sxs-lookup"><span data-stu-id="5bfca-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="5bfca-340">受影响的计算机向客户显示尚未更新到最新的反恶意软件平台。</span><span class="sxs-lookup"><span data-stu-id="5bfca-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="5bfca-341">此更新为：</span><span class="sxs-lookup"><span data-stu-id="5bfca-341">This update is:</span></span>
> - <span data-ttu-id="5bfca-342">运行较低版本的平台以支持 SHA2 的 RS1 设备需要;</span><span class="sxs-lookup"><span data-stu-id="5bfca-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="5bfca-343">对于有挂起问题的系统，具有重新启动标志;</span><span class="sxs-lookup"><span data-stu-id="5bfca-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="5bfca-344">在 2020 年 4 月重新发布，并且不会被更新的更新所取代，以保持将来的可用性;</span><span class="sxs-lookup"><span data-stu-id="5bfca-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="5bfca-345">因重启要求而分类为更新;和</span><span class="sxs-lookup"><span data-stu-id="5bfca-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="5bfca-346">仅与 Windows 更新 [一起提供](https://support.microsoft.com/help/4027667/windows-10-update)。</span><span class="sxs-lookup"><span data-stu-id="5bfca-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="5bfca-347">2019 年 11 月 (平台：4.18.1911.3 |引擎：1.1.16600.7) </span><span class="sxs-lookup"><span data-stu-id="5bfca-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="5bfca-348">安全智能更新版本 **：1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="5bfca-349">发布时间 **：2019 年 12 月 7 日**</span><span class="sxs-lookup"><span data-stu-id="5bfca-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="5bfca-350">平台 **：4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="5bfca-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="5bfca-351">引擎 **：1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="5bfca-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="5bfca-352">支持阶段： **不支持**</span><span class="sxs-lookup"><span data-stu-id="5bfca-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="5bfca-353">最近更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-353">What's new</span></span>

- <span data-ttu-id="5bfca-354">修复了 MpCmdRun 跟踪级别</span><span class="sxs-lookup"><span data-stu-id="5bfca-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="5bfca-355">修复了 WDFilter 版本信息</span><span class="sxs-lookup"><span data-stu-id="5bfca-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="5bfca-356">改进 PUA (通知) </span><span class="sxs-lookup"><span data-stu-id="5bfca-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="5bfca-357">添加 MRT 日志以支持文件</span><span class="sxs-lookup"><span data-stu-id="5bfca-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="5bfca-358">已知问题</span><span class="sxs-lookup"><span data-stu-id="5bfca-358">Known Issues</span></span>
<span data-ttu-id="5bfca-359">安装此更新后，设备需要跳转程序包 4.10.2001.10 才能更新到最新的平台版本。</span><span class="sxs-lookup"><span data-stu-id="5bfca-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="5bfca-360">Microsoft Defender 防病毒平台支持</span><span class="sxs-lookup"><span data-stu-id="5bfca-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="5bfca-361">平台和引擎更新按月提供。</span><span class="sxs-lookup"><span data-stu-id="5bfca-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="5bfca-362">若要完全受支持，请及时了解最新的平台更新。</span><span class="sxs-lookup"><span data-stu-id="5bfca-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="5bfca-363">我们的支持结构是动态的，根据最新平台版本的可用性，将发展为两个阶段：</span><span class="sxs-lookup"><span data-stu-id="5bfca-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="5bfca-364">**安全和关键更新服务阶段** - 运行最新平台版本时，你将有资格接收反恶意软件平台的安全和关键更新。</span><span class="sxs-lookup"><span data-stu-id="5bfca-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="5bfca-365">**技术支持 (仅在)** 阶段 - 发布新平台版本后，对早期版本 (N-2) 的支持将仅减少为技术支持。</span><span class="sxs-lookup"><span data-stu-id="5bfca-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="5bfca-366">不再支持 N-2 之前的平台版本。\*</span><span class="sxs-lookup"><span data-stu-id="5bfca-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="5bfca-367">\* 将继续为从 Windows 10 版本升级提供技术支持 (请参阅 [Windows 10](#platform-version-included-with-windows-10-releases) 版本) 到最新平台版本的平台版本。</span><span class="sxs-lookup"><span data-stu-id="5bfca-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="5bfca-368">在技术支持 (仅在) 阶段，商业上合理的支持事件将通过 Microsoft 客户服务 & 支持和 Microsoft 的托管支持产品/服务 (如 Premier Support) 提供。</span><span class="sxs-lookup"><span data-stu-id="5bfca-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="5bfca-369">如果支持事件需要上报开发以进一步提供指导、需要非安全更新或需要安全更新，将要求客户升级到最新平台版本或中间 (\*) 。</span><span class="sxs-lookup"><span data-stu-id="5bfca-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="5bfca-370">Windows 10 版本中包含的平台版本</span><span class="sxs-lookup"><span data-stu-id="5bfca-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="5bfca-371">下表提供了最新 Windows 10 版本附带的 Microsoft Defender 防病毒平台和引擎版本：</span><span class="sxs-lookup"><span data-stu-id="5bfca-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="5bfca-372">Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="5bfca-372">Windows 10 release</span></span>  |<span data-ttu-id="5bfca-373">平台版本</span><span class="sxs-lookup"><span data-stu-id="5bfca-373">Platform version</span></span>  |<span data-ttu-id="5bfca-374">引擎版本</span><span class="sxs-lookup"><span data-stu-id="5bfca-374">Engine version</span></span> |<span data-ttu-id="5bfca-375">支持阶段</span><span class="sxs-lookup"><span data-stu-id="5bfca-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="5bfca-376">2004 (20H1/20H2) </span><span class="sxs-lookup"><span data-stu-id="5bfca-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="5bfca-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="5bfca-377">4.18.1909.6</span></span> |<span data-ttu-id="5bfca-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="5bfca-378">1.1.17000.2</span></span> | <span data-ttu-id="5bfca-379">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="5bfca-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5bfca-380">1909 (19H2) </span><span class="sxs-lookup"><span data-stu-id="5bfca-380">1909  (19H2)</span></span> |<span data-ttu-id="5bfca-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="5bfca-381">4.18.1902.5</span></span> |<span data-ttu-id="5bfca-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="5bfca-382">1.1.16700.3</span></span> | <span data-ttu-id="5bfca-383">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="5bfca-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5bfca-384">1903 (19H1) </span><span class="sxs-lookup"><span data-stu-id="5bfca-384">1903  (19H1)</span></span> |<span data-ttu-id="5bfca-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="5bfca-385">4.18.1902.5</span></span> |<span data-ttu-id="5bfca-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="5bfca-386">1.1.15600.4</span></span> | <span data-ttu-id="5bfca-387">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="5bfca-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5bfca-388">1809 (RS5) </span><span class="sxs-lookup"><span data-stu-id="5bfca-388">1809  (RS5)</span></span> |<span data-ttu-id="5bfca-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="5bfca-389">4.18.1807.18075</span></span> |<span data-ttu-id="5bfca-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="5bfca-390">1.1.15000.2</span></span> | <span data-ttu-id="5bfca-391">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="5bfca-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5bfca-392">1803 (RS4) </span><span class="sxs-lookup"><span data-stu-id="5bfca-392">1803  (RS4)</span></span> |<span data-ttu-id="5bfca-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="5bfca-393">4.13.17134.1</span></span> |<span data-ttu-id="5bfca-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="5bfca-394">1.1.14600.4</span></span> | <span data-ttu-id="5bfca-395">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="5bfca-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5bfca-396">1709 (RS3) </span><span class="sxs-lookup"><span data-stu-id="5bfca-396">1709  (RS3)</span></span> |<span data-ttu-id="5bfca-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="5bfca-397">4.12.16299.15</span></span> |<span data-ttu-id="5bfca-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="5bfca-398">1.1.14104.0</span></span> | <span data-ttu-id="5bfca-399">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="5bfca-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5bfca-400">1703 (RS2) </span><span class="sxs-lookup"><span data-stu-id="5bfca-400">1703  (RS2)</span></span> |<span data-ttu-id="5bfca-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="5bfca-401">4.11.15603.2</span></span> |<span data-ttu-id="5bfca-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="5bfca-402">1.1.13504.0</span></span> | <span data-ttu-id="5bfca-403">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="5bfca-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="5bfca-404">1607 (RS1) </span><span class="sxs-lookup"><span data-stu-id="5bfca-404">1607 (RS1)</span></span> |<span data-ttu-id="5bfca-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="5bfca-405">4.10.14393.3683</span></span> |<span data-ttu-id="5bfca-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="5bfca-406">1.1.12805.0</span></span> | <span data-ttu-id="5bfca-407">仅支持技术 (升级) </span><span class="sxs-lookup"><span data-stu-id="5bfca-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="5bfca-408">有关Windows 10的信息，请参阅生命周期[Windows表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="5bfca-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="5bfca-409">DISM 部署映像服务和管理 (更新) </span><span class="sxs-lookup"><span data-stu-id="5bfca-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="5bfca-410">我们建议使用最新的防病毒和反恶意软件更新更新 Windows 10 (Enterprise、Pro 和家庭版) 、Windows Server 2019 和 Windows Server 2016 操作系统安装映像。</span><span class="sxs-lookup"><span data-stu-id="5bfca-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="5bfca-411">使操作系统安装映像保持最新有助于避免保护差距。</span><span class="sxs-lookup"><span data-stu-id="5bfca-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="5bfca-412">有关详细信息，请参阅适用于操作系统[安装映像Windows Microsoft Defender 更新](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="5bfca-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="5bfca-413">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="5bfca-413">1.1.2105.01</span></span></summary>

<span data-ttu-id="5bfca-414">&ensp;程序包版本 **：1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="5bfca-414">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="5bfca-415">&ensp;平台版本 **：4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="5bfca-415">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="5bfca-416">&ensp;引擎版本 **：1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="5bfca-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="5bfca-417">&ensp;签名版本 **：1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-417">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5bfca-418">修补程序</span><span class="sxs-lookup"><span data-stu-id="5bfca-418">Fixes</span></span>
- <span data-ttu-id="5bfca-419">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5bfca-420">其他信息</span><span class="sxs-lookup"><span data-stu-id="5bfca-420">Additional information</span></span>
- <span data-ttu-id="5bfca-421">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5bfca-422">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="5bfca-422">1.1.2104.01</span></span></summary>

<span data-ttu-id="5bfca-423">&ensp;程序包版本 **：1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="5bfca-423">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="5bfca-424">&ensp;平台版本 **：4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="5bfca-424">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="5bfca-425">&ensp;引擎版本 **：1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-425">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="5bfca-426">&ensp;签名版本 **：1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-426">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5bfca-427">修补程序</span><span class="sxs-lookup"><span data-stu-id="5bfca-427">Fixes</span></span>
- <span data-ttu-id="5bfca-428">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5bfca-429">其他信息</span><span class="sxs-lookup"><span data-stu-id="5bfca-429">Additional information</span></span>
- <span data-ttu-id="5bfca-430">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5bfca-431">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="5bfca-431">1.1.2103.01</span></span></summary>

<span data-ttu-id="5bfca-432">&ensp;程序包版本 **：1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="5bfca-432">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="5bfca-433">&ensp;平台版本 **：4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="5bfca-433">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="5bfca-434">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="5bfca-435">&ensp;签名版本 **：1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-435">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5bfca-436">修补程序</span><span class="sxs-lookup"><span data-stu-id="5bfca-436">Fixes</span></span>
- <span data-ttu-id="5bfca-437">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5bfca-438">其他信息</span><span class="sxs-lookup"><span data-stu-id="5bfca-438">Additional information</span></span>
- <span data-ttu-id="5bfca-439">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5bfca-440">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="5bfca-440">1.1.2102.03</span></span></summary>

<span data-ttu-id="5bfca-441">&ensp;程序包版本 **：1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="5bfca-441">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="5bfca-442">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="5bfca-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="5bfca-443">&ensp;引擎版本 **：1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="5bfca-444">&ensp;签名版本 **：1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-444">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5bfca-445">修补程序</span><span class="sxs-lookup"><span data-stu-id="5bfca-445">Fixes</span></span>
- <span data-ttu-id="5bfca-446">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5bfca-447">其他信息</span><span class="sxs-lookup"><span data-stu-id="5bfca-447">Additional information</span></span>
- <span data-ttu-id="5bfca-448">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5bfca-449">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="5bfca-449">1.1.2101.02</span></span></summary>

<span data-ttu-id="5bfca-450">&ensp;程序包版本 **：1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="5bfca-450">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="5bfca-451">&ensp;平台版本 **：4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="5bfca-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="5bfca-452">&ensp;引擎版本 **：1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="5bfca-452">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="5bfca-453">&ensp;签名版本 **：1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-453">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5bfca-454">修补程序</span><span class="sxs-lookup"><span data-stu-id="5bfca-454">Fixes</span></span>
- <span data-ttu-id="5bfca-455">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5bfca-456">其他信息</span><span class="sxs-lookup"><span data-stu-id="5bfca-456">Additional information</span></span>
- <span data-ttu-id="5bfca-457">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5bfca-458">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="5bfca-458">1.1.2012.01</span></span></summary>

<span data-ttu-id="5bfca-459">&ensp;程序包版本 **：1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="5bfca-459">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="5bfca-460">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="5bfca-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="5bfca-461">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="5bfca-462">&ensp;签名版本 **：1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-462">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5bfca-463">修补程序</span><span class="sxs-lookup"><span data-stu-id="5bfca-463">Fixes</span></span>
- <span data-ttu-id="5bfca-464">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5bfca-465">其他信息</span><span class="sxs-lookup"><span data-stu-id="5bfca-465">Additional information</span></span>
- <span data-ttu-id="5bfca-466">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5bfca-467">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="5bfca-467">1.1.2011.02</span></span></summary>

<span data-ttu-id="5bfca-468">&ensp;程序包版本 **：1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="5bfca-468">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="5bfca-469">&ensp;平台版本 **：4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="5bfca-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="5bfca-470">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="5bfca-471">&ensp;签名版本 **：1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-471">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5bfca-472">修补程序</span><span class="sxs-lookup"><span data-stu-id="5bfca-472">Fixes</span></span>
- <span data-ttu-id="5bfca-473">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5bfca-474">其他信息</span><span class="sxs-lookup"><span data-stu-id="5bfca-474">Additional information</span></span>
- <span data-ttu-id="5bfca-475">刷新Microsoft Defender 防病毒签名</span><span class="sxs-lookup"><span data-stu-id="5bfca-475">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5bfca-476">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="5bfca-476">1.1.2011.01</span></span></summary>

<span data-ttu-id="5bfca-477">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="5bfca-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="5bfca-478">&ensp;平台版本 **：4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="5bfca-478">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="5bfca-479">&ensp;引擎版本 **：1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="5bfca-480">&ensp;签名版本 **：1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-480">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5bfca-481">修补程序</span><span class="sxs-lookup"><span data-stu-id="5bfca-481">Fixes</span></span>
- <span data-ttu-id="5bfca-482">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5bfca-483">其他信息</span><span class="sxs-lookup"><span data-stu-id="5bfca-483">Additional information</span></span>
- <span data-ttu-id="5bfca-484">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-484">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="5bfca-485">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="5bfca-485">1.1.2009.10</span></span></summary>

<span data-ttu-id="5bfca-486">&ensp;程序包版本 **：1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="5bfca-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="5bfca-487">&ensp;平台版本 **：4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="5bfca-487">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="5bfca-488">&ensp;引擎版本 **：1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="5bfca-488">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="5bfca-489">&ensp;签名版本 **：1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="5bfca-489">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="5bfca-490">修补程序</span><span class="sxs-lookup"><span data-stu-id="5bfca-490">Fixes</span></span>
- <span data-ttu-id="5bfca-491">无</span><span class="sxs-lookup"><span data-stu-id="5bfca-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="5bfca-492">其他信息</span><span class="sxs-lookup"><span data-stu-id="5bfca-492">Additional information</span></span>
- <span data-ttu-id="5bfca-493">添加了对 Windows 10 RS1 或更高版本操作系统安装映像的支持。</span><span class="sxs-lookup"><span data-stu-id="5bfca-493">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="5bfca-494">其他资源</span><span class="sxs-lookup"><span data-stu-id="5bfca-494">Additional resources</span></span>

| <span data-ttu-id="5bfca-495">文章</span><span class="sxs-lookup"><span data-stu-id="5bfca-495">Article</span></span> | <span data-ttu-id="5bfca-496">说明</span><span class="sxs-lookup"><span data-stu-id="5bfca-496">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="5bfca-497">适用于操作系统安装映像Windows Microsoft Defender 更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-497">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="5bfca-498">查看适用于操作系统安装映像的反恶意软件更新程序包 (WIM 和 VHD 文件) 。</span><span class="sxs-lookup"><span data-stu-id="5bfca-498">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="5bfca-499">获取 Microsoft Defender 防病毒、Windows 10 (Enterprise、Pro、家庭版) 、Windows Server 2019 Windows Server 2016更新。</span><span class="sxs-lookup"><span data-stu-id="5bfca-499">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="5bfca-500">管理保护更新的下载和应用方式</span><span class="sxs-lookup"><span data-stu-id="5bfca-500">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="5bfca-501">保护更新可以通过多个源提供。</span><span class="sxs-lookup"><span data-stu-id="5bfca-501">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="5bfca-502">管理何时应下载和应用保护更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-502">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="5bfca-503">你可以计划应下载保护更新的时间。</span><span class="sxs-lookup"><span data-stu-id="5bfca-503">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="5bfca-504">管理过期终结点的更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-504">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="5bfca-505">如果终结点错过更新或计划扫描，可以在用户下次登录时强制进行更新或扫描。</span><span class="sxs-lookup"><span data-stu-id="5bfca-505">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="5bfca-506">管理基于事件的强制更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-506">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="5bfca-507">你可以将保护更新设置为在启动时或在某些云提供的保护事件之后下载。</span><span class="sxs-lookup"><span data-stu-id="5bfca-507">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="5bfca-508">管理移动设备和虚拟机 （VM） 的更新</span><span class="sxs-lookup"><span data-stu-id="5bfca-508">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="5bfca-509">你可以指定对移动设备和虚拟机特别有用的设置，例如是否应该使用电池电源进行更新。</span><span class="sxs-lookup"><span data-stu-id="5bfca-509">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
